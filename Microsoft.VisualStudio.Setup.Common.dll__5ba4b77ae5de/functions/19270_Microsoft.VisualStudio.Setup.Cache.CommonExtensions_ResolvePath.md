# Microsoft.VisualStudio.Setup.Cache.CommonExtensions::ResolvePath

- ea: `0x19270`
- end: `0x192a2`
- name: `Microsoft.VisualStudio.Setup.Cache.CommonExtensions::ResolvePath`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0x19270`
- `0x19ac0`

## string_xrefs

- `0x1927c`: `relativePath`

## pseudocode

```c

```

## disassembly

```asm
0x19270  ldarg.0
0x19271  ldstr    aInstance// "instance"
0x19276  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1927b  ldarg.1
0x1927c  ldstr    aRelativepath// "relativePath"
0x19281  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x19286  ldarg.0
0x19287  callvirt instance string Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstallationPath()
0x1928c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19291  brtrue.s loc_192A0
0x19293  ldarg.0
0x19294  callvirt instance string Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstallationPath()
0x19299  ldarg.1
0x1929a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1929f  ret
0x192a0  ldnull
0x192a1  ret
```
