# Microsoft.BIServer.Configuration.ConfigReader::get_Applications

- ea: `0x1010`
- end: `0x101c`
- name: `Microsoft.BIServer.Configuration.ConfigReader::get_Applications`
- size: `12`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1250`
- `0x12b0`

## pseudocode

```c

```

## disassembly

```asm
0x1010  ldarg.0
0x1011  ldfld    class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application>> Microsoft.BIServer.Configuration.ConfigReader::_applications
0x1016  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application>>::get_Value()
0x101b  ret
```
