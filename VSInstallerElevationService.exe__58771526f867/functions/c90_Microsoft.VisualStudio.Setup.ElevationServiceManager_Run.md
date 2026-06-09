# Microsoft.VisualStudio.Setup.ElevationServiceManager::Run

- ea: `0xc90`
- end: `0xcb3`
- name: `Microsoft.VisualStudio.Setup.ElevationServiceManager::Run`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1200`

## callees

- `0xd60`

## pseudocode

```c

```

## disassembly

```asm
0xc90  ldarg.0
0xc91  ldarg.0
0xc92  call     instance class Microsoft.VisualStudio.Setup.IPipe Microsoft.VisualStudio.Setup.ElevationServiceManager::CreatePipe()
0xc97  stfld    class Microsoft.VisualStudio.Setup.IPipe Microsoft.VisualStudio.Setup.ElevationServiceManager::pipe
0xc9c  ldarg.0
0xc9d  ldftn    instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.ElevationServiceManager::RunServiceAsync()
0xca3  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task>::.ctor(object, native int)
0xca8  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::Run(class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task>)
0xcad  call     void [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.TplExtensions::Forget(class [mscorlib]System.Threading.Tasks.Task)
0xcb2  ret
```
