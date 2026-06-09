# Microsoft.VisualStudio.Setup.Cache.FailedPackageReference::.ctor_0

- ea: `0x195b0`
- end: `0x19602`
- name: `Microsoft.VisualStudio.Setup.Cache.FailedPackageReference::.ctor_0`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x81f0`
- `0xc1a0`
- `0x19590`
- `0x195b0`
- `0x19640`
- `0x19660`
- `0x196a0`
- `0x196b0`
- `0x196f0`
- `0x1b920`
- `0x1b9f0`

## pseudocode

```c

```

## disassembly

```asm
0x195b0  ldarg.0
0x195b1  call     instance void Microsoft.VisualStudio.Setup.Cache.FailedPackageReference::.ctor()
0x195b6  ldarg.1
0x195b7  ldstr    aPackage// "package"
0x195bc  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x195c1  ldarg.0
0x195c2  ldarg.1
0x195c3  call     void Microsoft.VisualStudio.Setup.Cache.PackageReference::InitializePackageReference(class Microsoft.VisualStudio.Setup.Cache.PackageReference reference, class Microsoft.VisualStudio.Setup.IPackageIdentity identity)
0x195c8  ldarg.0
0x195c9  ldarg.s  4
0x195cb  call     instance void Microsoft.VisualStudio.Setup.Cache.FailedPackageReference::set_LogFilePath(string value)
0x195d0  ldarg.0
0x195d1  ldarg.2
0x195d2  call     instance void Microsoft.VisualStudio.Setup.Cache.FailedPackageReference::set_Description(string value)
0x195d7  ldarg.0
0x195d8  ldarg.s  5
0x195da  call     instance void Microsoft.VisualStudio.Setup.Cache.FailedPackageReference::set_Signature(string value)
0x195df  ldarg.0
0x195e0  ldarg.1
0x195e1  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0x195e6  call     instance void Microsoft.VisualStudio.Setup.Cache.PackageReference::set_Version(class [mscorlib]System.Version value)
0x195eb  ldarg.3
0x195ec  brfalse.s loc_195FA
0x195ee  ldarg.0
0x195ef  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Cache.FailedPackageReference::get_Details()
0x195f4  ldarg.3
0x195f5  call     T0x2B00002E
0x195fa  ldarg.0
0x195fb  ldarg.1
0x195fc  call     instance void Microsoft.VisualStudio.Setup.Cache.FailedPackageReference::AddAffectedPackages(class Microsoft.VisualStudio.Setup.IPackage package)
0x19601  ret
```
