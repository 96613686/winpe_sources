# Microsoft.VisualStudio.Setup.Cache.ProductReference::FromIdentity

- ea: `0x1bca0`
- end: `0x1bccb`
- name: `Microsoft.VisualStudio.Setup.Cache.ProductReference::FromIdentity`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1b0c0`

## callees

- `0xc1a0`
- `0x1b920`
- `0x1bcd0`
- `0x1bd80`
- `0x1be80`

## pseudocode

```c

```

## disassembly

```asm
0x1bca0  ldarg.0
0x1bca1  ldstr    aIdentity// "identity"
0x1bca6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1bcab  newobj   instance void Microsoft.VisualStudio.Setup.Cache.ProductReference::.ctor()
0x1bcb0  dup
0x1bcb1  ldarg.1
0x1bcb2  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1bcb7  callvirt instance void Microsoft.VisualStudio.Setup.Cache.ProductReference::set_IsInstalled(valuetype [mscorlib]System.Nullable`1<bool> value)
0x1bcbc  dup
0x1bcbd  ldarg.0
0x1bcbe  call     void Microsoft.VisualStudio.Setup.Cache.PackageReference::InitializePackageReference(class Microsoft.VisualStudio.Setup.Cache.PackageReference reference, class Microsoft.VisualStudio.Setup.IPackageIdentity identity)
0x1bcc3  dup
0x1bcc4  ldarg.0
0x1bcc5  call     void Microsoft.VisualStudio.Setup.Cache.ProductReference::InitializeProductReference(class Microsoft.VisualStudio.Setup.Cache.ProductReference reference, class Microsoft.VisualStudio.Setup.IPackageIdentity identity)
0x1bcca  ret
```
