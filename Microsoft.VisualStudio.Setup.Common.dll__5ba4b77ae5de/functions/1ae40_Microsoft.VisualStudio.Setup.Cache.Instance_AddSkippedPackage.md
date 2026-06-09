# Microsoft.VisualStudio.Setup.Cache.Instance::AddSkippedPackage

- ea: `0x1ae40`
- end: `0x1ae7b`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::AddSkippedPackage`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0x194f0`
- `0x1aa60`
- `0x1ae40`
- `0x1afb0`

## pseudocode

```c

```

## disassembly

```asm
0x1ae40  ldarg.1
0x1ae41  ldstr    aPackage// "package"
0x1ae46  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1ae4b  ldarg.0
0x1ae4c  ldfld    object Microsoft.VisualStudio.Setup.Cache.Instance::syncRoot
0x1ae51  stloc.0
0x1ae52  ldc.i4.0
0x1ae53  stloc.1
0x1ae54  ldloc.0
0x1ae55  ldloca.s 1
0x1ae57  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1ae5c  ldarg.0
0x1ae5d  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::EnsureErrorStateInitialized()
0x1ae62  ldarg.0
0x1ae63  call     instance class Microsoft.VisualStudio.Setup.Cache.ErrorState Microsoft.VisualStudio.Setup.Cache.Instance::get_Errors()
0x1ae68  ldarg.1
0x1ae69  callvirt instance void Microsoft.VisualStudio.Setup.Cache.ErrorState::AddSkippedPackage(class Microsoft.VisualStudio.Setup.IPackage package)
0x1ae6e  leave.s  loc_1AE7A
0x1ae70  ldloc.1
0x1ae71  brfalse.s loc_1AE79
0x1ae73  ldloc.0
0x1ae74  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1ae79  endfinally
0x1ae7a  ret
```
