# Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::Initialize

- ea: `0x1b2c0`
- end: `0x1b355`
- name: `Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::Initialize`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x11b00`
- `0x11f10`
- `0x11f80`
- `0x1a990`
- `0x1a9a0`
- `0x1b2c0`
- `0x1b3f0`
- `0x1b4b0`

## pseudocode

```c

```

## disassembly

```asm
0x1b2c0  ldarg.0
0x1b2c1  call     instance void Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::SetLocalState()
0x1b2c6  ldarg.0
0x1b2c7  call     instance bool Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::HasProduct()
0x1b2cc  brfalse.s loc_1B2E1
0x1b2ce  ldarg.0
0x1b2cf  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b2d4  dup
0x1b2d5  callvirt instance valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::get_State()
0x1b2da  ldc.i4.2
0x1b2db  or
0x1b2dc  callvirt instance void Microsoft.VisualStudio.Setup.Cache.Instance::set_State(valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState value)
0x1b2e1  ldarg.0
0x1b2e2  ldfld    class Microsoft.VisualStudio.Setup.Services.IRestartManager Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::restartManager
0x1b2e7  brfalse.s loc_1B327
0x1b2e9  ldarg.0
0x1b2ea  ldfld    class Microsoft.VisualStudio.Setup.Services.IRestartManager Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::restartManager
0x1b2ef  ldarg.0
0x1b2f0  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::OnRebootRequired(object source, class [mscorlib]System.EventArgs args)
0x1b2f6  newobj   instance void class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs>::.ctor(object, native int)
0x1b2fb  callvirt instance void Microsoft.VisualStudio.Setup.Services.IRestartManager::add_RebootRequired(class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs> value)
0x1b300  ldarg.0
0x1b301  ldfld    class Microsoft.VisualStudio.Setup.Services.IRestartManager Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::restartManager
0x1b306  ldarg.0
0x1b307  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b30c  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IRestartManager::RebootRequiredSemaphoreExists([opt] class Microsoft.VisualStudio.Setup.Cache.IInstance instance)
0x1b311  brtrue.s loc_1B354
0x1b313  ldarg.0
0x1b314  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b319  dup
0x1b31a  callvirt instance valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::get_State()
0x1b31f  ldc.i4.4
0x1b320  or
0x1b321  callvirt instance void Microsoft.VisualStudio.Setup.Cache.Instance::set_State(valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState value)
0x1b326  ret
0x1b327  ldarg.0
0x1b328  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b32d  dup
0x1b32e  callvirt instance valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::get_State()
0x1b333  ldc.i4.4
0x1b334  or
0x1b335  callvirt instance void Microsoft.VisualStudio.Setup.Cache.Instance::set_State(valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState value)
0x1b33a  ldarg.0
0x1b33b  ldfld    class Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::logger
0x1b340  dup
0x1b341  brtrue.s loc_1B345
0x1b343  pop
0x1b344  ret
0x1b345  ldstr    aNoRestartManag// "No restart manager available. Assuming "...
0x1b34a  call     T0x2B000016
0x1b34f  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string format, object[] args)
0x1b354  ret
```
