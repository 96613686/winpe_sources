# Microsoft.VisualStudio.Setup.WorkPrimaryProcess::GrabSingletonLock

- ea: `0x34f0`
- end: `0x3515`
- name: `Microsoft.VisualStudio.Setup.WorkPrimaryProcess::GrabSingletonLock`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x34f0`

## string_xrefs

- `0x34f1`: `services`
- `0x3509`: `Another Visual Studio installation is running. You'll need to close it before you continue.`

## pseudocode

```c

```

## disassembly

```asm
0x34f0  ldarg.1
0x34f1  ldstr    aServices// "services"
0x34f6  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x34fb  ldarg.1
0x34fc  ldc.i4.1
0x34fd  call     T0x2B000030
0x3502  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ISingletonService::GetSingletonLock()
0x3507  brtrue.s loc_3514
0x3509  ldstr    aAnotherVisualS// "Another Visual Studio installation is r"...
0x350e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3513  throw
0x3514  ret
```
