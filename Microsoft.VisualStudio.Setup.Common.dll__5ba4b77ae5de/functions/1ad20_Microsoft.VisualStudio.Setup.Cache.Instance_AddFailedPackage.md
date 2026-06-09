# Microsoft.VisualStudio.Setup.Cache.Instance::AddFailedPackage

- ea: `0x1ad20`
- end: `0x1ad5b`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::AddFailedPackage`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0x194e0`
- `0x1aa60`
- `0x1ad20`
- `0x1afb0`

## pseudocode

```c

```

## disassembly

```asm
0x1ad20  ldarg.1
0x1ad21  ldstr    aFailedpackager// "failedPackageReference"
0x1ad26  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1ad2b  ldarg.0
0x1ad2c  ldfld    object Microsoft.VisualStudio.Setup.Cache.Instance::syncRoot
0x1ad31  stloc.0
0x1ad32  ldc.i4.0
0x1ad33  stloc.1
0x1ad34  ldloc.0
0x1ad35  ldloca.s 1
0x1ad37  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1ad3c  ldarg.0
0x1ad3d  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::EnsureErrorStateInitialized()
0x1ad42  ldarg.0
0x1ad43  call     instance class Microsoft.VisualStudio.Setup.Cache.ErrorState Microsoft.VisualStudio.Setup.Cache.Instance::get_Errors()
0x1ad48  ldarg.1
0x1ad49  callvirt instance void Microsoft.VisualStudio.Setup.Cache.ErrorState::AddPackageFailure(class Microsoft.VisualStudio.Setup.Cache.FailedPackageReference failedPackageReference)
0x1ad4e  leave.s  loc_1AD5A
0x1ad50  ldloc.1
0x1ad51  brfalse.s loc_1AD59
0x1ad53  ldloc.0
0x1ad54  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1ad59  endfinally
0x1ad5a  ret
```
