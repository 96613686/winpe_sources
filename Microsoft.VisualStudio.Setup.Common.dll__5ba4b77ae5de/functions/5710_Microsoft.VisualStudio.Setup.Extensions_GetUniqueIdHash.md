# Microsoft.VisualStudio.Setup.Extensions::GetUniqueIdHash

- ea: `0x5710`
- end: `0x5748`
- name: `Microsoft.VisualStudio.Setup.Extensions::GetUniqueIdHash`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x81e0`
- `0x8260`
- `0xc1a0`
- `0x11ac0`

## string_xrefs

- `0x571c`: `hashingService`

## pseudocode

```c

```

## disassembly

```asm
0x5710  ldarg.0
0x5711  ldstr    aPackageidentit// "packageIdentity"
0x5716  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x571b  ldarg.1
0x571c  ldstr    aHashingservice// "hashingService"
0x5721  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x5726  ldarg.0
0x5727  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x572c  stloc.0
0x572d  ldarg.1
0x572e  ldloc.0
0x572f  ldc.i4.1
0x5730  callvirt instance string Microsoft.VisualStudio.Setup.Services.IHashingService::GetHashOfString(string value, valuetype Microsoft.VisualStudio.Setup.Services.HashAlgorithms algorithm)
0x5735  stloc.0
0x5736  ldarg.0
0x5737  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x573c  ldstr    asc_1F876// "."
0x5741  ldloc.0
0x5742  call     string [mscorlib]System.String::Concat(string, string, string)
0x5747  ret
```
