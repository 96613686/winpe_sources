# System.Xaml.XamlReaderSettings::.ctor_0

- ea: `0x2470`
- end: `0x24c2`
- name: `System.Xaml.XamlReaderSettings::.ctor_0`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x6690`

## callees

- `0x23a0`
- `0x23b0`
- `0x23c0`
- `0x23d0`
- `0x23e0`
- `0x23f0`
- `0x2400`
- `0x2410`
- `0x2420`
- `0x2430`
- `0x2440`
- `0x2450`
- `0x2460`
- `0x2470`

## pseudocode

```c

```

## disassembly

```asm
0x2470  ldarg.0
0x2471  call     instance void System.Xaml.XamlReaderSettings::.ctor()
0x2476  ldarg.1
0x2477  brfalse.s loc_24C1
0x2479  ldarg.0
0x247a  ldarg.1
0x247b  callvirt instance bool System.Xaml.XamlReaderSettings::get_AllowProtectedMembersOnRoot()
0x2480  call     instance void System.Xaml.XamlReaderSettings::set_AllowProtectedMembersOnRoot(bool value)
0x2485  ldarg.0
0x2486  ldarg.1
0x2487  callvirt instance bool System.Xaml.XamlReaderSettings::get_ProvideLineInfo()
0x248c  call     instance void System.Xaml.XamlReaderSettings::set_ProvideLineInfo(bool value)
0x2491  ldarg.0
0x2492  ldarg.1
0x2493  callvirt instance class [System]System.Uri System.Xaml.XamlReaderSettings::get_BaseUri()
0x2498  call     instance void System.Xaml.XamlReaderSettings::set_BaseUri(class [System]System.Uri value)
0x249d  ldarg.0
0x249e  ldarg.1
0x249f  callvirt instance class [mscorlib]System.Reflection.Assembly System.Xaml.XamlReaderSettings::get_LocalAssembly()
0x24a4  call     instance void System.Xaml.XamlReaderSettings::set_LocalAssembly(class [mscorlib]System.Reflection.Assembly value)
0x24a9  ldarg.0
0x24aa  ldarg.1
0x24ab  callvirt instance bool System.Xaml.XamlReaderSettings::get_IgnoreUidsOnPropertyElements()
0x24b0  call     instance void System.Xaml.XamlReaderSettings::set_IgnoreUidsOnPropertyElements(bool value)
0x24b5  ldarg.0
0x24b6  ldarg.1
0x24b7  callvirt instance bool System.Xaml.XamlReaderSettings::get_ValuesMustBeString()
0x24bc  call     instance void System.Xaml.XamlReaderSettings::set_ValuesMustBeString(bool value)
0x24c1  ret
```
