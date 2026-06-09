# Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::SetLocalState

- ea: `0x1b4b0`
- end: `0x1b503`
- name: `Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::SetLocalState`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1b2c0`
- `0x1b360`
- `0x1b3a0`

## callees

- `0x11890`
- `0x1a670`
- `0x1a990`
- `0x1a9a0`
- `0x1b4b0`

## pseudocode

```c

```

## disassembly

```asm
0x1b4b0  ldarg.0
0x1b4b1  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b4b6  callvirt instance string Microsoft.VisualStudio.Setup.Cache.Instance::get_InstallationPath()
0x1b4bb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b4c0  brtrue.s loc_1B502
0x1b4c2  ldarg.0
0x1b4c3  ldfld    class Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::fileSystem
0x1b4c8  ldarg.0
0x1b4c9  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b4ce  callvirt instance string Microsoft.VisualStudio.Setup.Cache.Instance::get_InstallationPath()
0x1b4d3  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string path)
0x1b4d8  brfalse.s loc_1B4EE
0x1b4da  ldarg.0
0x1b4db  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b4e0  dup
0x1b4e1  callvirt instance valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::get_State()
0x1b4e6  ldc.i4.1
0x1b4e7  or
0x1b4e8  callvirt instance void Microsoft.VisualStudio.Setup.Cache.Instance::set_State(valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState value)
0x1b4ed  ret
0x1b4ee  ldarg.0
0x1b4ef  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b4f4  dup
0x1b4f5  callvirt instance valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::get_State()
0x1b4fa  ldc.i4.s 0xFE
0x1b4fc  and
0x1b4fd  callvirt instance void Microsoft.VisualStudio.Setup.Cache.Instance::set_State(valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState value)
0x1b502  ret
```
