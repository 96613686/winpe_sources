# Microsoft.VisualStudio.Setup.Cache.CommonExtensions::ContainsPath

- ea: `0x19080`
- end: `0x190b2`
- name: `Microsoft.VisualStudio.Setup.Cache.CommonExtensions::ContainsPath`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0xc1d0`
- `0xcfd0`
- `0x19080`
- `0x19ac0`

## pseudocode

```c

```

## disassembly

```asm
0x19080  ldarg.0
0x19081  ldstr    aInstance// "instance"
0x19086  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1908b  ldarg.1
0x1908c  ldstr    aPath_0// "path"
0x19091  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string s, string paramName)
0x19096  ldarg.0
0x19097  callvirt instance string Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstallationPath()
0x1909c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x190a1  brtrue.s loc_190B0
0x190a3  ldarg.1
0x190a4  ldarg.0
0x190a5  callvirt instance string Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstallationPath()
0x190aa  call     bool Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string fullPath, string path)
0x190af  ret
0x190b0  ldc.i4.0
0x190b1  ret
```
