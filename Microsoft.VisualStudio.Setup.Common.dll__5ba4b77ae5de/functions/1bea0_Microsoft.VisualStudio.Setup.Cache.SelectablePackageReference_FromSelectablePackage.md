# Microsoft.VisualStudio.Setup.Cache.SelectablePackageReference::FromSelectablePackage

- ea: `0x1bea0`
- end: `0x1bed0`
- name: `Microsoft.VisualStudio.Setup.Cache.SelectablePackageReference::FromSelectablePackage`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5a40`
- `0x8340`
- `0xc1a0`
- `0x1b920`
- `0x1bee0`
- `0x1bf00`
- `0x1bfd0`

## pseudocode

```c

```

## disassembly

```asm
0x1bea0  ldarg.0
0x1bea1  ldstr    aPackage// "package"
0x1bea6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1beab  newobj   instance void Microsoft.VisualStudio.Setup.Cache.SelectablePackageReference::.ctor()
0x1beb0  dup
0x1beb1  ldarg.0
0x1beb2  call     void Microsoft.VisualStudio.Setup.Cache.PackageReference::InitializePackageReference(class Microsoft.VisualStudio.Setup.Cache.PackageReference reference, class Microsoft.VisualStudio.Setup.IPackageIdentity identity)
0x1beb7  dup
0x1beb8  ldarg.0
0x1beb9  call     valuetype Microsoft.VisualStudio.Setup.SelectedState Microsoft.VisualStudio.Setup.Extensions::GetSelectedState(class Microsoft.VisualStudio.Setup.IPackage package)
0x1bebe  callvirt instance void Microsoft.VisualStudio.Setup.Cache.SelectablePackageReference::set_SelectedState(valuetype Microsoft.VisualStudio.Setup.SelectedState value)
0x1bec3  dup
0x1bec4  ldarg.0
0x1bec5  callvirt instance valuetype Microsoft.VisualStudio.Setup.UserSelectedState Microsoft.VisualStudio.Setup.ISelectablePackage::get_UserSelectedState()
0x1beca  callvirt instance void Microsoft.VisualStudio.Setup.Cache.SelectablePackageReference::set_UserSelectedState(valuetype Microsoft.VisualStudio.Setup.UserSelectedState value)
0x1becf  ret
```
