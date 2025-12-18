<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>刘力菀 - 个人简历</title>
    <style>
        /* 全局样式重置 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "微软雅黑", "楷体_GB2312", sans-serif;
        }

        body {
            background-color: #fffef5; /* 淡奶油黄背景 */
            color: #333;
            line-height: 1.7;
            padding-bottom: 80px;
        }

        /* 顶部导航栏：可点击切换模块 */
        .nav-tab {
            background-color: #f9f6e8; /* 浅黄导航背景 */
            border-bottom: 3px solid #f0e68c; /* 核心淡黄色 */
            position: sticky;
            top: 0;
            z-index: 99;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
        }

        .nav-tab ul {
            list-style: none;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 5px;
        }

        .nav-tab li {
            margin: 0;
        }

        .nav-tab button {
            background: transparent;
            border: none;
            padding: 15px 20px;
            font-size: 1rem;
            font-weight: bold;
            color: #666;
            cursor: pointer;
            transition: all 0.3s ease;
            border-bottom: 3px solid transparent;
        }

        .nav-tab button.active {
            color: #8b7d3f; /* 深黄文字 */
            border-bottom: 3px solid #f0e68c; /* 淡黄色下划线 */
            background-color: #fff9e6;
        }

        .nav-tab button:hover {
            color: #8b7d3f;
            background-color: #fff9e6;
        }

        /* 头部横幅 */
        .header {
            background: linear-gradient(135deg, #f9f6e8, #f0e68c); /* 淡黄色渐变 */
            text-align: center;
            padding: 60px 20px;
            color: #8b7d3f;
        }

        .header h1 {
            font-size: 2.8rem;
            margin-bottom: 10px;
        }

        .header p {
            font-size: 1.2rem;
            opacity: 0.9;
        }

        /* 头像区域 */
        .avatar-box {
            text-align: center;
            margin: -50px auto 30px;
            width: 180px;
            height: 180px;
            border-radius: 50%;
            border: 8px solid #fff;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            overflow: hidden;
        }

        .avatar {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .avatar-box:hover .avatar {
            transform: scale(1.1);
        }

        /* 内容容器 */
        .content-container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* 模块样式：默认隐藏，点击切换显示 */
        .module {
            display: none;
            background: #fff;
            border-radius: 16px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            border-top: 5px solid #f0e68c; /* 淡黄色顶边 */
        }

        .module.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* 模块标题 */
        .module h2 {
            color: #8b7d3f;
            font-size: 1.8rem;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #f9f6e8;
        }

        .module h3 {
            color: #666;
            font-size: 1.3rem;
            margin: 20px 0 10px;
        }

        /* 个人信息列表 */
        .info-list {
            list-style: none;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .info-list li {
            padding: 15px;
            background: #f9f6e8;
            border-radius: 10px;
            font-size: 1.1rem;
        }

        .info-list li span {
            font-weight: bold;
            color: #8b7d3f;
            margin-right: 8px;
        }

        /* 技能/证书标签 */
        .tag-group {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-top: 20px;
        }

        .tag {
            background: #f9f6e8;
            color: #8b7d3f;
            padding: 8px 18px;
            border-radius: 20px;
            font-size: 0.95rem;
            font-weight: 500;
            border: 1px solid #f0e68c;
        }

        .tag.highlight {
            background: #f0e68c;
            color: #8b7d3f;
            font-weight: bold;
        }

        /* 经历/项目卡片 */
        .card {
            background: #f9f6e8;
            border-left: 4px solid #f0e68c;
            padding: 20px;
            border-radius: 0 10px 10px 0;
            margin-bottom: 20px;
            transition: transform 0.3s ease;
        }

        .card:hover {
            transform: translateX(5px);
        }

        .card h4 {
            color: #8b7d3f;
            margin-bottom: 10px;
            font-size: 1.2rem;
        }

        .card p, .card ul {
            color: #666;
            line-height: 1.6;
        }

        .card ul {
            margin-left: 20px;
            margin-top: 8px;
        }

        /* ========== 优化后的联系方式样式 ========== */
        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 20px;
            margin-top: 25px;
        }

        .contact-card {
            background: #f9f6e8;
            border-radius: 12px;
            padding: 25px 15px;
            text-align: center;
            border: 2px solid #f0e68c;
            transition: all 0.3s ease;
        }

        .contact-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 8px 15px rgba(240, 230, 140, 0.2);
        }

        .contact-icon {
            font-size: 2.5rem;
            color: #8b7d3f;
            margin-bottom: 15px;
            display: block;
        }

        .contact-card h4 {
            color: #8b7d3f;
            font-size: 1.1rem;
            margin-bottom: 10px;
        }

        .contact-card p {
            color: #666;
            line-height: 1.5;
            margin: 5px 0;
        }

        .contact-card a {
            color: #8b7d3f;
            text-decoration: none;
            font-weight: 500;
        }

        .contact-card a:hover {
            text-decoration: underline;
        }

        .contact-desc {
            text-align: center;
            color: #666;
            margin-top: 30px;
            font-size: 1rem;
        }
        /* ========== 联系方式样式结束 ========== */

        /* 返回顶部按钮：固定定位 */
        .back-to-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background-color: #f0e68c;
            color: #8b7d3f;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            text-decoration: none;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
        }

        .back-to-top.show {
            opacity: 1;
            visibility: visible;
        }

        .back-to-top:hover {
            background-color: #e6d86c;
            transform: translateY(-3px);
        }

        /* 响应式适配 */
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2rem;
            }

            .nav-tab button {
                padding: 12px 15px;
                font-size: 0.9rem;
            }

            .info-list {
                grid-template-columns: 1fr;
            }

            .module {
                padding: 20px;
            }

            .contact-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
    <!-- 引入图标库 -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css">
</head>
<body>
    <!-- 顶部导航栏：可点击切换模块 -->
    <div class="nav-tab">
        <ul>
            <li><button class="tab-btn active" data-tab="intro">个人简介</button></li>
            <li><button class="tab-btn" data-tab="education">教育经历</button></li>
            <li><button class="tab-btn" data-tab="skills">专业技能</button></li>
            <li><button class="tab-btn" data-tab="cert">证书荣誉</button></li>
            <li><button class="tab-btn" data-tab="project">项目经历</button></li>
            <li><button class="tab-btn" data-tab="intern">实习经历</button></li>
            <li><button class="tab-btn" data-tab="eval">个人评价</button></li>
            <li><button class="tab-btn" data-tab="contact">联系方式</button></li>
        </ul>
    </div>

    <!-- 头部横幅 -->
    <div class="header">
        <h1>刘力菀</h1>
        <p>大连海洋大学 | 数据科学与大数据技术 | 19岁 | 大数据分析方向</p>
    </div>

    <!-- 头像 -->
    <div class="avatar-box">
        <img src="Youku Files/11.jpg" alt="刘力菀的照片" class="avatar">
        <!-- 替换为你的照片路径，与HTML文件同目录即可 -->
    </div>

    <!-- 内容容器 -->
    <div class="content-container">
        <!-- 个人简介模块 -->
        <div class="module active" id="intro">
            <h2>个人简介</h2>
            <ul class="info-list">
                <li><span>姓名：</span>刘力菀</li>
                <li><span>性别：</span>女</li>
                <li><span>年龄：</span>19岁</li>
                <li><span>院校：</span>大连海洋大学</li>
                <li><span>专业：</span>数据科学与大数据技术</li>
                <li><span>年级：</span>2024级本科在读</li>
                <li><span>学号：</span>2405180227</li>
                <li><span>政治面貌：</span>群众</li>
            </ul>
            <p style="margin-top: 20px; line-height: 1.8; color: #666;">
                现就读于大连海洋大学数据科学与大数据技术专业，大一在读学生。对大数据分析、数据挖掘与机器学习领域拥有强烈兴趣，
                具备扎实的Python编程基础与数据分析思维，熟练掌握SQL数据库操作和数据可视化工具。在校期间积极参与专业竞赛与科研项目，
                曾参与校园大数据分析竞赛并获奖，具备良好的团队协作能力与问题解决能力。课余时间自主学习Hadoop、Spark等大数据框架，
                致力于将理论知识转化为实际应用，目标成为一名优秀的大数据分析师。
            </p>
        </div>

        <!-- 教育经历模块 -->
        <div class="module" id="education">
            <h2>教育经历</h2>
            <div class="card">
                <h4>大连海洋大学 | 数据科学与大数据技术 | 本科 | 2024.09 - 至今</h4>
                <p><strong>主修课程：</strong>Python程序设计、大数据导论、数据结构、数据库原理、操作系统、计算机网络、机器学习基础、Hadoop分布式系统、Spark大数据处理、数据可视化、数据挖掘技术、统计学基础</p>
                <p><strong>学业表现：</strong>学业成绩排名专业前10%，综合测评成绩92分，获校级二等奖学金，多次获得“学习标兵”称号</p>
                <p><strong>校园活动：</strong>加入学校大数据社团，参与每周技术分享会；担任班级学习委员，组织专业学习小组活动</p>
            </div>
            <div class="card">
                <h4>XX市第一中学 | 理科重点班 | 2021.09 - 2024.06</h4>
                <p><strong>学业表现：</strong>高考总分620分，数学135分、英语128分，理科综合240分</p>
                <p><strong>获奖情况：</strong>高中数学竞赛市级二等奖、全国中学生英语能力竞赛省级三等奖</p>
            </div>
        </div>

        <!-- 专业技能模块 -->
        <div class="module" id="skills">
            <h2>专业技能</h2>
            <h3>编程语言与工具</h3>
            <div class="tag-group">
                <span class="tag highlight">Python (熟练)</span>
                <span class="tag highlight">SQL (熟练)</span>
                <span class="tag">HTML/CSS (掌握)</span>
                <span class="tag">Java (基础)</span>
                <span class="tag">Excel (精通)</span>
                <span class="tag">Tableau (掌握)</span>
            </div>

            <h3>数据分析库与框架</h3>
            <div class="tag-group">
                <span class="tag highlight">Pandas (熟练)</span>
                <span class="tag highlight">NumPy (熟练)</span>
                <span class="tag highlight">Matplotlib (熟练)</span>
                <span class="tag">Seaborn (掌握)</span>
                <span class="tag">Scikit-learn (基础)</span>
                <span class="tag">Hadoop (了解)</span>
                <span class="tag">Spark (了解)</span>
            </div>

            <h3>数据处理能力</h3>
            <div class="tag-group">
                <span class="tag">数据清洗</span>
                <span class="tag">特征工程</span>
                <span class="tag">数据可视化</span>
                <span class="tag">统计分析</span>
                <span class="tag">数据库设计</span>
                <span class="tag">分布式计算</span>
            </div>

            <h3>软技能</h3>
            <div class="tag-group">
                <span class="tag">团队协作</span>
                <span class="tag">文档撰写</span>
                <span class="tag">问题解决</span>
                <span class="tag">自主学习</span>
                <span class="tag">演讲表达</span>
            </div>
        </div>

        <!-- 证书荣誉模块 -->
        <div class="module" id="cert">
            <h2>证书与荣誉</h2>
            <h3>专业证书</h3>
            <div class="tag-group">
                <span class="tag highlight">全国计算机二级（Python）</span>
                <span class="tag highlight">大学英语四级（568分）</span>
                <span class="tag">SQL工程师认证（基础级）</span>
                <span class="tag">阿里云大数据助理工程师（ACA）备考中</span>
            </div>

            <h3>获奖荣誉</h3>
            <div class="card">
                <h4>大连海洋大学校级二等奖学金 | 2024-2025学年</h4>
                <p>学业成绩专业前10%，综合表现优异，获奖比例约10%</p>
            </div>
            <div class="card">
                <h4>大连海洋大学大数据分析竞赛三等奖 | 2025年4月</h4>
                <p>团队项目《校园学生消费行为数据分析与预测》，负责数据清洗、可视化与结论分析，获校级三等奖</p>
            </div>
            <div class="card">
                <h4>大连海洋大学“优秀团员” | 2025年5月</h4>
                <p>基于思想表现、学业成绩与校园活动参与度评选，全院仅20人获此荣誉</p>
            </div>
        </div>

        <!-- 项目经历模块 -->
        <div class="module" id="project">
            <h2>项目经历</h2>
            <div class="card">
                <h4>校园学生消费行为数据分析 | 2025.03 - 2025.04</h4>
                <p><strong>项目角色：</strong>核心开发人员</p>
                <p><strong>项目描述：</strong>基于校园一卡通消费数据，分析学生消费习惯、食堂就餐规律与消费能力差异，为校园商业服务优化提供数据支撑</p>
                <ul>
                    <li>使用Python的Pandas库完成10万条消费数据的清洗，处理缺失值、异常值，数据完整度提升至98%</li>
                    <li>通过Matplotlib制作消费趋势图、食堂就餐时段分布图等12张可视化图表</li>
                    <li>运用统计学方法分析不同年级、专业的消费差异，得出3项核心结论并撰写分析报告</li>
                </ul>
                <p><strong>技术栈：</strong>Python、Pandas、Matplotlib、SQL、统计学</p>
            </div>
            <div class="card">
                <h4>个人博客网站开发（大数据学习笔记） | 2025.01 - 2025.03</h4>
                <p><strong>项目角色：</strong>独立开发</p>
                <p><strong>项目描述：</strong>搭建个人大数据学习笔记博客，记录Python编程、数据分析等学习过程与知识点总结</p>
                <ul>
                    <li>使用HTML/CSS/JavaScript完成前端页面开发，实现响应式布局与导航功能</li>
                    <li>使用MySQL搭建简易数据库，实现文章的增删改查功能</li>
                    <li>部署至本地服务器，累计发布学习笔记20余篇，访问量超500次</li>
                </ul>
                <p><strong>技术栈：</strong>HTML、CSS、JavaScript、MySQL、Flask（基础）</p>
            </div>
        </div>

        <!-- 实习经历模块 -->
        <div class="module" id="intern">
            <h2>实习经历（虚构）</h2>
            <div class="card">
                <h4>XX科技有限公司 | 大数据分析实习生 | 2025.07 - 2025.09</h4>
                <p><strong>实习内容：</strong>协助大数据团队完成用户行为数据分析、数据可视化与业务报告撰写工作</p>
                <ul>
                    <li>负责电商平台用户行为数据的清洗与预处理，日处理数据量约50万条，使用Pandas提升数据处理效率30%</li>
                    <li>运用Matplotlib与Seaborn制作日/周/月用户留存、转化、复购等核心指标可视化报表，为产品迭代提供数据依据</li>
                    <li>学习Spark框架，参与分布式日志数据处理任务，完成基础的数据过滤与统计工作</li>
                    <li>撰写每周数据分析报告，累计输出10份报告，其中3项分析结论被产品部门采纳</li>
                </ul>
                <p><strong>实习收获：</strong>掌握企业级大数据分析流程，提升了数据处理与业务分析能力，熟悉了Spark分布式计算的基础使用</p>
            </div>
        </div>

        <!-- 个人评价模块 -->
        <div class="module" id="eval">
            <h2>个人评价</h2>
            <div class="card">
                <h4>学习能力</h4>
                <p>具备极强的自主学习能力，能够快速掌握新的技术与工具。例如，通过线上课程与官方文档，仅用1个月掌握Python数据分析核心库的使用，
                3个月完成大数据分析竞赛项目开发。在校期间保持每周阅读2篇技术博客、学习1个新知识点的习惯。</p>
            </div>
            <div class="card">
                <h4>专业素养</h4>
                <p>拥有严谨的数据分析思维，注重数据的真实性与逻辑性，在项目中坚持“数据说话”的原则。具备良好的代码规范意识，
                编写的代码注释完整、结构清晰，便于团队协作与后期维护。</p>
            </div>
            <div class="card">
                <h4>团队协作</h4>
                <p>在竞赛与项目中担任过团队核心成员，能够与团队成员高效沟通，明确分工，发挥各自优势。擅长倾听他人意见，
                同时敢于提出自己的想法，在团队中起到了技术支撑与沟通协调的作用。</p>
            </div>
            <div class="card">
                <h4>职业规划</h4>
                <p>短期目标：扎实掌握大数据分析与挖掘的核心技术，考取阿里云大数据工程师认证，参与更多企业级项目实践；
                长期目标：成为一名资深大数据分析师，能够独立负责大型数据分析项目，为企业决策提供专业的数据支撑。</p>
            </div>
        </div>

        <!-- 优化后的联系方式模块 -->
        <div class="module" id="contact">
            <h2>联系方式</h2>
            <div class="contact-container">
                <div class="contact-card">
                    <i class="fa fa-envelope-o contact-icon"></i>
                    <h4>电子邮箱</h4>
                    <p>liuliwan@dlou.edu.cn</p>
                    <p>liuliwan@example.com</p>
                </div>
                <div class="contact-card">
                    <i class="fa fa-phone contact-icon"></i>
                    <h4>联系电话</h4>
                    <p>13800138000（虚拟）</p>
                    <p>13900139000（虚拟）</p>
                </div>
                <div class="contact-card">
                    <i class="fa fa-github contact-icon"></i>
                    <h4>GitHub仓库</h4>
                    <p>github.com/liuliwan</p>
                    <a href="https://github.com" target="_blank">点击访问</a>
                </div>
                <div class="contact-card">
                    <i class="fa fa-location-arrow contact-icon"></i>
                    <h4>所在地址</h4>
                    <p>辽宁省大连市沙河口区</p>
                    <p>大连海洋大学（黄海校区）</p>
                </div>
            </div>
            <p class="contact-desc">
                欢迎通过以上方式联系我，期待与您交流大数据相关技术与项目合作！
            </p>
        </div>
    </div>

    <!-- 返回顶部按钮 -->
    <button class="back-to-top" id="backToTop">↑</button>

    <script>
        // 1. 标签切换功能
        const tabBtns = document.querySelectorAll('.tab-btn');
        const modules = document.querySelectorAll('.module');

        tabBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                // 移除所有激活状态
                tabBtns.forEach(b => b.classList.remove('active'));
                modules.forEach(m => m.classList.remove('active'));

                // 添加当前激活状态
                btn.classList.add('active');
                const tabId = btn.getAttribute('data-tab');
                document.getElementById(tabId).classList.add('active');
            });
        });

        // 2. 返回顶部功能
        const backToTopBtn = document.getElementById('backToTop');

        window.addEventListener('scroll', () => {
            if (window.scrollY > 300) {
                backToTopBtn.classList.add('show');
            } else {
                backToTopBtn.classList.remove('show');
            }
        });

        backToTopBtn.addEventListener('click', () => {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });
    </script>
</body>
</html>
