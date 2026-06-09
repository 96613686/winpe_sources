# Microsoft.BIServer.Configuration.Dumper::ContainsExcludedException

- ea: `0x21b0`
- end: `0x21dd`
- name: `Microsoft.BIServer.Configuration.Dumper::ContainsExcludedException`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x21e0`

## callees

- `0x21b0`

## pseudocode

```c

```

## disassembly

```asm
0x21b0  ldarg.1
0x21b1  brtrue.s loc_21B5
0x21b3  ldc.i4.0
0x21b4  ret
0x21b5  ldarg.1
0x21b6  stloc.0
0x21b7  ldarg.0
0x21b8  ldfld    class [System]System.Collections.Generic.ISet`1<string> Microsoft.BIServer.Configuration.Dumper::_errorsExcluded
0x21bd  ldloc.0
0x21be  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x21c3  callvirt instance string [mscorlib]System.Object::ToString()
0x21c8  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x21cd  brfalse.s loc_21D1
0x21cf  ldc.i4.1
0x21d0  ret
0x21d1  ldloc.0
0x21d2  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x21d7  stloc.0
0x21d8  ldloc.0
0x21d9  brtrue.s loc_21B7
0x21db  ldc.i4.0
0x21dc  ret
```
