---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

# 欢迎来到我的网站<p>当前时间戳：<span id="timestamp-display">加载中...</span></p><script>

  // 替换为你的 Vercel 部署的 Go 服务 URL

  const apiUrl = "https://timestamp-go-iufft0824-wgdstrays-projects.vercel.app"; // 请替换为你的实际 URL



  fetch(apiUrl)    .then(response => {

      if (!response.ok) {

        throw new Error(`HTTP error! status: ${response.status}`);

      }

      return response.json();

    })

    .then(data => {

      document.getElementById("timestamp-display").textContent = data.timestamp;

    })

    .catch(error => {

      console.error("获取时间戳失败:", error);

      document.getElementById("timestamp-display").textContent = "获取失败";

    });

</script>
