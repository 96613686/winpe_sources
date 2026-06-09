# Microsoft.VisualStudio.Setup.Cache.Instance::SetRuntimeError

- ea: `0x1ad60`
- end: `0x1ad9b`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::SetRuntimeError`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x19000`

## callees

- `0xc1a0`
- `0x19480`
- `0x1aa60`
- `0x1ad60`
- `0x1afb0`

## pseudocode

```c

```

## disassembly

```asm
0x1ad60  ldarg.1
0x1ad61  ldstr    aException// "exception"
0x1ad66  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1ad6b  ldarg.0
0x1ad6c  ldfld    object Microsoft.VisualStudio.Setup.Cache.Instance::syncRoot
0x1ad71  stloc.0
0x1ad72  ldc.i4.0
0x1ad73  stloc.1
0x1ad74  ldloc.0
0x1ad75  ldloca.s 1
0x1ad77  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1ad7c  ldarg.0
0x1ad7d  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::EnsureErrorStateInitialized()
0x1ad82  ldarg.0
0x1ad83  call     instance class Microsoft.VisualStudio.Setup.Cache.ErrorState Microsoft.VisualStudio.Setup.Cache.Instance::get_Errors()
0x1ad88  ldarg.1
0x1ad89  callvirt instance void Microsoft.VisualStudio.Setup.Cache.ErrorState::set_RuntimeError(class [mscorlib]System.Exception value)
0x1ad8e  leave.s  loc_1AD9A
0x1ad90  ldloc.1
0x1ad91  brfalse.s loc_1AD99
0x1ad93  ldloc.0
0x1ad94  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1ad99  endfinally
0x1ad9a  ret
```
