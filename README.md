<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>基礎から応用まで学ぶ生成AI活用講座</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/tailwindcss/2.2.19/tailwind.min.css" rel="stylesheet">
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" rel="stylesheet">
    <style>
        :root {
            --primary-color: #6366f1;
            --secondary-color: #10b981;
            --accent-color: #8b5cf6;
            --background-color: #f9fafb;
            --text-color: #1f2937;
        }
        
        body {
            font-family: 'Hiragino Sans', 'Hiragino Kaku Gothic ProN', 'Noto Sans JP', sans-serif;
            background-color: var(--background-color);
            color: var(--text-color);
        }
        
        .sidebar {
            background-color: var(--primary-color);
            color: white;
        }
        
        .course-card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .course-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }
        
        .progress-bar {
            background-color: #e5e7eb;
            border-radius: 9999px;
            height: 8px;
            overflow: hidden;
        }
        
        .progress-value {
            background-color: var(--primary-color);
            height: 100%;
        }
        
        .badge {
            background-color: var(--accent-color);
            color: white;
            padding: 2px 8px;
            border-radius: 9999px;
            font-size: 0.75rem;
        }
        
        .topic-card {
            transition: transform 0.2s ease;
        }
        
        .topic-card:hover {
            transform: scale(1.03);
        }
        
        .btn-primary {
            background-color: var(--primary-color);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 0.375rem;
            font-weight: 500;
            transition: background-color 0.2s ease;
        }
        
        .btn-primary:hover {
            background-color: #5253cc;
        }
        
        /* アニメーション効果 */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .animate-fade-in {
            animation: fadeIn 0.5s ease-out forwards;
        }
        
        /* カスタムスクロールバー */
        ::-webkit-scrollbar {
            width: 8px;
        }
        
        ::-webkit-scrollbar-track {
            background: #f1f1f1;
        }
        
        ::-webkit-scrollbar-thumb {
            background: #d1d5db;
            border-radius: 4px;
        }
        
        ::-webkit-scrollbar-thumb:hover {
            background: #9ca3af;
        }
    </style>
</head>
<body>
    <div class="flex h-screen bg-gray-50">
        <!-- サイドバー -->
        <div class="sidebar w-64 flex-shrink-0 flex flex-col shadow-lg z-10 animate-fade-in" style="animation-delay: 0.1s;">
            <!-- ロゴ -->
            <div class="p-4 flex items-center justify-between border-b border-indigo-700">
                <div class="flex items-center">
                    <div class="w-10 h-10 bg-white rounded-lg flex items-center justify-center mr-3">
                        <i class="fas fa-robot text-indigo-600 text-xl"></i>
                    </div>
                    <h1 class="text-xl font-bold">生成AI講座</h1>
                </div>
                <button class="text-white hover:bg-indigo-700 p-1 rounded focus:outline-none">
                    <i class="fas fa-bars"></i>
                </button>
            </div>
            
            <!-- ナビゲーションメニュー -->
            <nav class="flex-1 p-4 overflow-y-auto">
                <ul class="space-y-2">
                    <li class="bg-indigo-700 rounded p-2 flex items-center">
                        <i class="fas fa-home w-5 text-center"></i>
                        <span class="ml-3">ダッシュボード</span>
                    </li>
                    <li class="hover:bg-indigo-700 rounded p-2 flex items-center transition duration-150">
                        <i class="fas fa-book w-5 text-center"></i>
                        <span class="ml-3">マイコース</span>
                    </li>
                    <li class="hover:bg-indigo-700 rounded p-2 flex items-center transition duration-150">
                        <i class="fas fa-search w-5 text-center"></i>
                        <span class="ml-3">講座一覧</span>
                    </li>
                    <li class="hover:bg-indigo-700 rounded p-2 flex items-center transition duration-150">
                        <i class="fas fa-tasks w-5 text-center"></i>
                        <span class="ml-3">学習進捗</span>
                    </li>
                    <li class="hover:bg-indigo-700 rounded p-2 flex items-center transition duration-150">
                        <i class="fas fa-certificate w-5 text-center"></i>
                        <span class="ml-3">修了証明書</span>
                    </li>
                </ul>
            </nav>
            
            <!-- ユーザー情報 -->
            <div class="p-4 border-t border-indigo-700 flex items-center">
                <div class="w-10 h-10 bg-white rounded-full flex items-center justify-center text-indigo-600">
                    <i class="fas fa-user"></i>
                </div>
                <div class="ml-3">
                    <p class="text-sm font-medium">山田 太郎</p>
                    <p class="text-xs text-indigo-300">学習者</p>
                </div>
            </div>
        </div>
        
        <!-- メインコンテンツ -->
        <div class="flex-1 flex flex-col overflow-hidden">
            <!-- ヘッダー -->
            <header class="bg-white shadow-sm flex items-center justify-between p-4 animate-fade-in" style="animation-delay: 0.2s;">
                <div class="flex items-center rounded-lg bg-gray-100 px-3 py-2 w-64">
                    <i class="fas fa-search text-gray-500"></i>
                    <input
                        class="bg-transparent border-none ml-2 outline-none flex-1 text-sm"
                        placeholder="コースを検索..."
                    />
                </div>
                
                <div class="flex items-center">
                    <button class="p-2 rounded-full hover:bg-gray-100 relative mr-3">
                        <i class="far fa-question-circle text-gray-500"></i>
                    </button>
                    <button class="p-2 rounded-full hover:bg-gray-100 relative mr-3">
                        <i class="far fa-bell text-gray-500"></i>
                        <span class="absolute top-1 right-1 bg-red-500 rounded-full w-2 h-2"></span>
                    </button>
                    <div class="ml-1 flex items-center">
                        <button class="flex items-center text-gray-700 hover:bg-gray-100 rounded-full p-1">
                            <div class="w-8 h-8 bg-indigo-500 rounded-full flex items-center justify-center text-white">
                                <i class="fas fa-user text-sm"></i>
                            </div>
                            <span class="font-medium ml-2 mr-1 hidden sm:block">山田 太郎</span>
                            <i class="fas fa-chevron-down text-xs ml-1 text-gray-500 hidden sm:block"></i>
                        </button>
                    </div>
                </div>
            </header>
            
            <!-- メインコンテンツエリア -->
            <main class="flex-1 overflow-y-auto p-6 bg-gray-50">
                <!-- ウェルカムセクション -->
                <div class="bg-gradient-to-r from-indigo-600 to-purple-600 rounded-xl p-6 mb-8 text-white shadow-lg animate-fade-in" style="animation-delay: 0.3s;">
                    <div class="flex flex-col md:flex-row items-start md:items-center justify-between">
                        <div class="mb-4 md:mb-0">
                            <h1 class="text-2xl font-bold mb-2">生成AIの世界へようこそ！</h1>
                            <p class="mb-4 text-indigo-100">次のレベルのAIスキルを身につけましょう</p>
                            <p class="mb-1">あなたの学習進捗: <span class="font-bold">23%</span> 完了</p>
                            <div class="w-full max-w-md bg-white bg-opacity-30 rounded-full h-2 mb-4">
                                <div class="bg-white h-2 rounded-full w-1/4"></div>
                            </div>
                            <button class="bg-white text-indigo-600 px-4 py-2 rounded-lg font-medium hover:bg-opacity-90 transition flex items-center">
                                <i class="fas fa-play-circle mr-2"></i>
                                最後の学習を続ける
                            </button>
                        </div>
                        <div class="hidden md:block">
                            <div class="w-32 h-32 bg-white bg-opacity-10 rounded-full flex items-center justify-center">
                                <i class="fas fa-brain text-6xl text-white"></i>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- 進行中のコース -->
                <div class="mb-8 animate-fade-in" style="animation-delay: 0.4s;">
                    <div class="flex items-center justify-between mb-4">
                        <h3 class="text-lg font-semibold flex items-center">
                            <i class="fas fa-book-open mr-2 text-indigo-600"></i>
                            進行中のコース
                        </h3>
                        <button class="text-indigo-600 flex items-center text-sm hover:text-indigo-800 transition">
                            すべて表示 
                            <i class="fas fa-chevron-right ml-1 text-xs"></i>
                        </button>
                    </div>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                        <!-- コースカード 1 -->
                        <div class="course-card bg-white rounded-xl shadow-md overflow-hidden">
                            <div class="h-40 bg-gradient-to-br from-indigo-500 to-purple-600 p-4 text-white">
                                <div class="flex justify-between">
                                    <span class="badge">基礎編</span>
                                    <button class="text-white hover:text-indigo-200 transition">
                                        <i class="far fa-bookmark"></i>
                                    </button>
                                </div>
                                <div class="mt-8 flex justify-center">
                                    <i class="fas fa-lightbulb text-5xl text-yellow-300 opacity-80"></i>
                                </div>
                            </div>
                            <div class="p-5">
                                <h4 class="font-bold mb-2 text-gray-800">生成AIの基本概念と歴史</h4>
                                <div class="flex items-center text-sm text-gray-500 mb-3">
                                    <i class="far fa-clock mr-1"></i>
                                    <span>残り推定時間: 2.5時間</span>
                                </div>
                                <div class="progress-bar mb-1">
                                    <div class="progress-value w-3/5"></div>
                                </div>
                                <div class="flex justify-between items-center">
                                    <div class="text-xs text-gray-500">60% 完了</div>
                                    <button class="text-indigo-600 text-sm hover:text-indigo-800 transition">
                                        続ける <i class="fas fa-arrow-right ml-1 text-xs"></i>
                                    </button>
                                </div>
                            </div>
                        </div>
                        
                        <!-- コースカード 2 -->
                        <div class="course-card bg-white rounded-xl shadow-md overflow-hidden">
                            <div class="h-40 bg-gradient-to-br from-green-500 to-teal-600 p-4 text-white">
                                <div class="flex justify-between">
                                    <span class="badge" style="background-color: #059669;">実践編</span>
                                    <button class="text-white hover:text-green-200 transition">
                                        <i class="far fa-bookmark"></i>
                                    </button>
                                </div>
                                <div class="mt-8 flex justify-center">
                                    <i class="fas fa-keyboard text-5xl text-green-200 opacity-80"></i>
                                </div>
                            </div>
                            <div class="p-5">
                                <h4 class="font-bold mb-2 text-gray-800">テキスト生成AIの実践的活用法</h4>
                                <div class="flex items-center text-sm text-gray-500 mb-3">
                                    <i class="far fa-clock mr-1"></i>
                                    <span>残り推定時間: 4時間</span>
                                </div>
                                <div class="progress-bar mb-1">
                                    <div class="progress-value w-1/4" style="background-color: #10b981;"></div>
                                </div>
                                <div class="flex justify-between items-center">
                                    <div class="text-xs text-gray-500">25% 完了</div>
                                    <button class="text-teal-600 text-sm hover:text-teal-800 transition">
                                        続ける <i class="fas fa-arrow-right ml-1 text-xs"></i>
                                    </button>
                                </div>
                            </div>
                        </div>
                        
                        <!-- コースカード 3 -->
                        <div class="course-card bg-white rounded-xl shadow-md overflow-hidden">
                            <div class="h-40 bg-gradient-to-br from-blue-500 to-cyan-600 p-4 text-white">
                                <div class="flex justify-between">
                                    <span class="badge" style="background-color: #3b82f6;">実践編</span>
                                    <button class="text-white hover:text-blue-200 transition">
                                        <i class="fas fa-bookmark"></i>
                                    </button>
                                </div>
                                <div class="mt-8 flex justify-center">
                                    <i class="fas fa-image text-5xl text-blue-200 opacity-80"></i>
                                </div>
                            </div>
                            <div class="p-5">
                                <h4 class="font-bold mb-2 text-gray-800">画像生成AIの基本と応用</h4>
                                <div class="flex items-center text-sm text-gray-500 mb-3">
                                    <i class="far fa-clock mr-1"></i>
                                    <span>残り推定時間: 5.5時間</span>
                                </div>
                                <div class="progress-bar mb-1">
                                    <div class="progress-value w-1/12" style="background-color: #3b82f6;"></div>
                                </div>
                                <div class="flex justify-between items-center">
                                    <div class="text-xs text-gray-500">8% 完了</div>
                                    <button class="text-blue-600 text-sm hover:text-blue-800 transition">
                                        続ける <i class="fas fa-arrow-right ml-1 text-xs"></i>
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- 学習トピック -->
                <div class="mb-8 animate-fade-in" style="animation-delay: 0.5s;">
                    <div class="flex items-center justify-between mb-4">
                        <h3 class="text-lg font-semibold flex items-center">
                            <i class="fas fa-star mr-2 text-indigo-600"></i>
                            人気の学習トピック
                        </h3>
                    </div>
                    
                    <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
                        <div class="topic-card bg-white p-4 rounded-xl shadow-md text-center hover:shadow-lg transition cursor-pointer">
                            <div class="w-12 h-12 bg-indigo-100 rounded-full flex items-center justify-center mx-auto mb-3">
                                <i class="fas fa-comment-dots text-indigo-600"></i>
                            </div>
                            <h4 class="font-medium">プロンプト<br>エンジニアリング</h4>
                        </div>
                        
                        <div class="topic-card bg-white p-4 rounded-xl shadow-md text-center hover:shadow-lg transition cursor-pointer">
                            <div class="w-12 h-12 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-3">
                                <i class="fas fa-paint-brush text-green-600"></i>
                            </div>
                            <h4 class="font-medium">画像生成<br>テクニック</h4>
                        </div>
                        
                        <div class="topic-card bg-white p-4 rounded-xl shadow-md text-center hover:shadow-lg transition cursor-pointer">
                            <div class="w-12 h-12 bg-purple-100 rounded-full flex items-center justify-center mx-auto mb-3">
                                <i class="fas fa-chart-line text-purple-600"></i>
                            </div>
                            <h4 class="font-medium">AIモデルの<br>評価と選択</h4>
                        </div>
                        
                        <div class="topic-card bg-white p-4 rounded-xl shadow-md text-center hover:shadow-lg transition cursor-pointer">
                            <div class="w-12 h-12 bg-red-100 rounded-full flex items-center justify-center mx-auto mb-3">
                                <i class="fas fa-balance-scale text-red-600"></i>
                            </div>
                            <h4 class="font-medium">AIの倫理と<br>バイアス</h4>
                        </div>
                    </div>
                </div>
                
                <!-- 最近の達成 -->
                <div class="mb-8 animate-fade-in" style="animation-delay: 0.6s;">
                    <div class="flex items-center justify-between mb-4">
                        <h3 class="text-lg font-semibold flex items-center">
                            <i class="fas fa-trophy mr-2 text-indigo-600"></i>
                            最近の達成
                        </h3>
                    </div>
                    
                    <div class="bg-white rounded-xl shadow-md p-5">
                        <div class="flex items-center mb-4 pb-4 border-b">
                            <div class="w-12 h-12 bg-yellow-100 rounded-full flex items-center justify-center mr-4">
                                <i class="fas fa-certificate text-yellow-600"></i>
                            </div>
                            <div>
                                <h4 class="font-bold text-gray-800">「AIの基礎知識」モジュール修了</h4>
                                <p class="text-gray-500 text-sm">2週間前に達成</p>
                            </div>
                            <div class="ml-auto">
                                <button class="text-indigo-600 hover:text-indigo-800 text-sm font-medium">
                                    証明書を表示
                                </button>
                            </div>
                        </div>
                        
                        <div class="flex items-center">
                            <div class="w-12 h-12 bg-green-100 rounded-full flex items-center justify-center mr-4">
                                <i class="fas fa-fire text-green-600"></i>
                            </div>
                            <div>
                                <h4 class="font-bold text-gray-800">学習ストリーク 7日間達成</h4>
                                <p class="text-gray-500 text-sm">3日前に達成</p>
                            </div>
                            <div class="ml-auto">
                                <span class="inline-block bg-indigo-100 text-indigo-800 text-xs font-semibold px-2.5 py-1 rounded-full">
                                    +50 ポイント
                                </span>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- おすすめコース -->
                <div class="animate-fade-in" style="animation-delay: 0.7s;">
                    <div class="flex items-center justify-between mb-4">
                        <h3 class="text-lg font-semibold flex items-center">
                            <i class="fas fa-bolt mr-2 text-indigo-600"></i>
                            おすすめのコース
                        </h3>
                        <button class="text-indigo-600 flex items-center text-sm hover:text-indigo-800 transition">
                            すべて表示 
                            <i class="fas fa-chevron-right ml-1 text-xs"></i>
                        </button>
                    </div>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                        <!-- おすすめコース 1 -->
                        <div class="course-card bg-white rounded-xl shadow-md overflow-hidden">
                            <div class="h-40 bg-gradient-to-br from-yellow-500 to-orange-600 p-4 text-white">
                                <div class="flex justify-between">
                                    <span class="badge" style="background-color: #d97706;">応用編</span>
                                    <button class="text-white hover:text-yellow-200 transition">
                                        <i class="far fa-bookmark"></i>
                                    </button>
                                </div>
                                <div class="mt-8 flex justify-center">
                                    <i class="fas fa-briefcase text-5xl text-yellow-200 opacity-80"></i>
                                </div>
                            </div>
                            <div class="p-5">
                                <h4 class="font-bold mb-2 text-gray-800">業界別生成AI活用事例</h4>
                                <p class="text-gray-600 text-sm mb-4">マーケティング、医療、教育など様々な業界での生成AI活用例を学びます。</p>
                                <div class="flex items-center justify-between mb-4">
                                    <div class="flex items-center">
                                        <i class="fas fa-clock text-gray-400 mr-1"></i>
                                        <span class="text-xs text-gray-500">8時間</span>
                                    </div>
                                    <div class="flex items-center">
                                        <i class="fas fa-signal text-gray-400 mr-1"></i>
                                        <span class="text-xs text-gray-500">中級</span>
                                    </div>
                                    <div class="flex items-center">
                                        <i class="fas fa-user-graduate text-gray-400 mr-1"></i>
                                        <span class="text-xs text-gray-500">156人</span>
                                    </div>
                                </div>
                                <button class="w-full bg-indigo-600 text-white py-2 rounded-lg hover:bg-indigo-700 transition flex items-center justify-center">
                                    <i class="fas fa-play-circle mr-2"></i>
                                    コースを開始
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- フッター部分 -->
                <footer class="mt-12 text-center text-gray-500 text-sm animate-fade-in" style="animation-delay: 0.8s;">
                    <p>&copy; 2025 基礎から応用まで学ぶ生成AI活用講座</p>
                </footer>
            </main>
        </div>
    </div>

    <!-- メモ欄読み上げ機能のモーダル（例示） -->
    <div id="readAloudModal" class="hidden fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50">
        <div class="bg-white rounded-xl shadow-xl p-6 max-w-md w-full mx-4">
            <div class="flex justify-between items-center mb-4">
                <h3 class="text-lg font-bold text-gray-800">テキスト読み上げ設定</h3>
                <button class="text-gray-500 hover:text-gray-700">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div class="mb-4">
                <label class="block text-sm font-medium text-gray-700 mb-1">読み上げ音声</label>
                <select class="w-full border border-gray-300 rounded-md px-3 py-2 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500">
                    <option>日本語 - 女性</option>
                    <option>日本語 - 男性</option>
                    <option>英語 - 女性</option>
                    <option>英語 - 男性</option>
                </select>
            </div>
            
            <div class="mb-4">
                <label class="block text-sm font-medium text-gray-700 mb-1">読み上げ速度</label>
                <input type="range" min="0.5" max="2" step="0.1" value="1" class="w-full">
                <div class="flex justify-between text-xs text-gray-500 mt-1">
                    <span>遅い</span>
                    <span>標準</span>
                    <span>速い</span>
                </div>
            </div>
            
            <div class="mb-6">
                <label class="block text-sm font-medium text-gray-700 mb-1">読み上げテキスト</label>
                <textarea class="w-full border border-gray-300 rounded-md px-3 py-2 h-24 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500" placeholder="ここにナレーションテキストを入力してください...">生成AIは、データから学習し新しいコンテンツを作り出す人工知能技術です。この講座では、様々な生成AIの種類と活用方法について学びます。</textarea>
            </div>
            
            <div class="flex justify-end space-x-3">
                <button class="px-4 py-2 border border-gray-300 rounded-md text-gray-700 hover:bg-gray-50 transition">
                    キャンセル
                </button>
                <button class="px-4 py-2 bg-indigo-600 text-white rounded-md hover:bg-indigo-700 transition flex items-center">
                    <i class="fas fa-volume-up mr-2"></i>
                    読み上げを開始
                </button>
            </div>
        </div>
    </div>

    <!-- APIとの連携などを含むスクリプト部分 -->
    <script>
        // サイドバートグル機能
        document.addEventListener('DOMContentLoaded', function() {
            // 実際のアプリケーションでは、ここにさらに多くのインタラクション処理を追加します
            // 例: モーダル表示、API連携、コース選択処理など
        });
        
        // 音声読み上げ機能のシミュレーション（実際の実装ではWebSpeech APIなどを使用）
        function readAloudText(text, voice, rate) {
            // 実際の実装ではここでテキスト読み上げAPIを呼び出します
            console.log(`Reading aloud: "${text}" with voice "${voice}" at rate ${rate}`);
        }
    </script>
</body>
</html>
                                </button>
                            </div>
                        </div>
                        
                        <!-- おすすめコース 3 -->
                        <div class="course-card bg-white rounded-xl shadow-md overflow-hidden">
                            <div class="h-40 bg-gradient-to-br from-purple-500 to-pink-600 p-4 text-white">
                                <div class="flex justify-between">
                                    <span class="badge" style="background-color: #8b5cf6;">最新動向</span>
                                    <button class="text-white hover:text-purple-200 transition">
                                        <i class="far fa-bookmark"></i>
                                    </button>
                                </div>
                                <div class="mt-8 flex justify-center">
                                    <i class="fas fa-rocket text-5xl text-purple-200 opacity-80"></i>
                                </div>
                            </div>
                            <div class="p-5">
                                <h4 class="font-bold mb-2 text-gray-800">最新生成AIモデルの動向と展望</h4>
                                <p class="text-gray-600 text-sm mb-4">最新の生成AIモデルの進化と今後の展望について学びます。</p>
                                <div class="flex items-center justify-between mb-4">
                                    <div class="flex items-center">
                                        <i class="fas fa-clock text-gray-400 mr-1"></i>
                                        <span class="text-xs text-gray-500">6時間</span>
                                    </div>
                                    <div class="flex items-center">
                                        <i class="fas fa-signal text-gray-400 mr-1"></i>
                                        <span class="text-xs text-gray-500">中級</span>
                                    </div>
                                    <div class="flex items-center">
                                        <i class="fas fa-user-graduate text-gray-400 mr-1"></i>
                                        <span class="text-xs text-gray-500">203人</span>
                                    </div>
                                </div>
                                <button class="w-full bg-indigo-600 text-white py-2 rounded-lg hover:bg-indigo-700 transition flex items-center justify-center">
                                    <i class="fas fa-play-circle mr-2"></i>
                                    コースを開始
                                </button>
                            </div>
                        </div>
                        
                        <!-- おすすめコース 2 -->
                        <div class="course-card bg-white rounded-xl shadow-md overflow-hidden">
                            <div class="h-40 bg-gradient-to-br from-blue-500 to-cyan-600 p-4 text-white">
                                <div class="flex justify-between">
                                    <span class="badge" style="background-color: #3b82f6;">応用編</span>
                                    <button class="text-white hover:text-blue-200 transition">
                                        <i class="far fa-bookmark"></i>
                                    </button>
                                </div>
                                <div class="mt-8 flex justify-center">
                                    <i class="fas fa-cogs text-5xl text-blue-200 opacity-80"></i>
                                </div>
                            </div>
                            <div class="p-5">
                                <h4 class="font-bold mb-2 text-gray-800">独自AIモデルのファインチューニング</h4>
                                <p class="text-gray-600 text-sm mb-4">汎用AIモデルをカスタマイズし、特定のタスクに最適化する方法を学びます。</p>
                                <div class="flex items-center justify-between mb-4">
                                    <div class="flex items-center">
                                        <i class="fas fa-clock text-gray-400 mr-1"></i>
                                        <span class="text-xs text-gray-500">12時間</span>
                                    </div>
                                    <div class="flex items-center">
                                        <i class="fas fa-signal text-gray-400 mr-1"></i>
                                        <span class="text-xs text-gray-500">上級</span>
                                    </div>
                                    <div class="flex items-center">
                                        <i class="fas fa-user-graduate text-gray-400 mr-1"></i>
                                        <span class="text-xs text-gray-500">89人</span>
                                    </div>
                                </div>
                                <button class="w-full bg-indigo-600 text-white py-2 rounded-lg hover:bg-indigo-700 transition flex items-center justify-center">
                                    <i class="fas fa-play-circle mr-2"></i>
                                    コースを開始
