# 📦 Datagram Docker Setup Guide (Windows - GUI + Terminal)

## 🐳 Step 1: Install Docker Desktop

Download and install Docker Desktop for Windows:  
🔗 [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)

After installation:

- Make sure **WSL2 backend** is enabled.
- Restart your computer.

---

## ⚙️ Step 2: Enable Docker Startup on Boot

1. Open **Docker Desktop**.
2. Go to **Settings > General**.
3. ✅ Check: **"Start Docker Desktop when you log in"**
4. Click **Apply & Restart**.

---

## 🚀 Step 3: Run the Datagram Node Container

Open **Docker Desktop** and:

1. Click on the **Containers** tab.
2. Use the **Terminal icon** (▶) on any container (if exists), **or:**
   - Press `Ctrl + Shift + P` to open the Docker terminal globally, **or:**
   - Go to **Settings > Troubleshoot > Run Terminal**.

Once inside the Docker terminal, run the following:

> Replace `your_license_key` with your actual license key.

<pre>
docker run -d `
  --name datagram-node `
  --restart unless-stopped `
  -e LICENSE_KEY=your_license_key `
  itsaetrna/datagram-docker:latest
</pre>

Note: Use backticks (`) for line breaks in PowerShell (not `\`).

---

## 🧪 Step 4: Verify It’s Running

```bash
docker ps
```

You should see a running container named `datagram-node`.

---

## 🔁 Step 5: Confirm Auto-Restart Works

The `--restart unless-stopped` option ensures:

* The container auto-restarts when your PC or Docker restarts.
* It **won’t** restart if **you** manually stop it using:

```bash
docker stop datagram-node
```

### To Test:

* Reboot your system.
* Open Docker Desktop → **Containers** tab → See if `datagram-node` is **Running**.
* You can also check if it's connected by visiting your node dashboard.

---

## ✅ Done!

Your Datagram node will now run in a Docker container and start automatically on every Windows reboot.
