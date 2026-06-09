# Microsoft.VisualStudio.Setup.Cache.PackageReference::FromIdentity

- ea: `0x1b900`
- end: `0x1b918`
- name: `Microsoft.VisualStudio.Setup.Cache.PackageReference::FromIdentity`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x194f0`
- `0x196f0`
- `0x1bc70`

## callees

- `0xc1a0`
- `0x1b920`
- `0x1bc30`

## pseudocode

```c

```

## disassembly

```asm
0x1b900  ldarg.0
0x1b901  ldstr    aIdentity// "identity"
0x1b906  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1b90b  newobj   instance void Microsoft.VisualStudio.Setup.Cache.PackageReference::.ctor()
0x1b910  dup
0x1b911  ldarg.0
0x1b912  call     void Microsoft.VisualStudio.Setup.Cache.PackageReference::InitializePackageReference(class Microsoft.VisualStudio.Setup.Cache.PackageReference reference, class Microsoft.VisualStudio.Setup.IPackageIdentity identity)
0x1b917  ret
```
