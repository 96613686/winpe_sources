# Microsoft.VisualStudio.Setup.Cache.CommonExtensions::IsInstalled

- ea: `0x18f40`
- end: `0x18f6f`
- name: `Microsoft.VisualStudio.Setup.Cache.CommonExtensions::IsInstalled`
- size: `47`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x16d00`
- `0x17660`
- `0x1d7a0`

## callees

- `0xc1a0`
- `0x18f40`
- `0x19880`
- `0x1a980`
- `0x1bc70`

## pseudocode

```c

```

## disassembly

```asm
0x18f40  ldarg.0
0x18f41  ldstr    aManager// "manager"
0x18f46  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x18f4b  ldarg.1
0x18f4c  ldstr    aIdentity// "identity"
0x18f51  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x18f56  ldarg.0
0x18f57  callvirt instance class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.ICacheManager::GetInstance()
0x18f5c  stloc.0
0x18f5d  ldloc.0
0x18f5e  brfalse.s loc_18F6D
0x18f60  ldloc.0
0x18f61  callvirt instance class Microsoft.VisualStudio.Setup.Cache.PackageReferenceCollection Microsoft.VisualStudio.Setup.Cache.Instance::get_Packages()
0x18f66  ldarg.1
0x18f67  callvirt instance bool Microsoft.VisualStudio.Setup.Cache.PackageReferenceCollection::Contains(class Microsoft.VisualStudio.Setup.IPackageIdentity identity)
0x18f6c  ret
0x18f6d  ldc.i4.0
0x18f6e  ret
```
