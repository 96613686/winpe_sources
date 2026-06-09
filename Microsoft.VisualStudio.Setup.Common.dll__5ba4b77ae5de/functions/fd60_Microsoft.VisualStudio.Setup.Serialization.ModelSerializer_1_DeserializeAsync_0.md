# Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1::DeserializeAsync_0

- ea: `0xfd60`
- end: `0xfda3`
- name: `Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1::DeserializeAsync_0`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xc1a0`

## string_xrefs

- `0xfd81`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0xfd60  newobj   instance void class <>c__DisplayClass44_0<var<u1>>::.ctor()
0xfd65  stloc.0
0xfd66  ldloc.0
0xfd67  ldarg.2
0xfd68  stfld    valuetype [mscorlib]System.Threading.CancellationToken class <>c__DisplayClass44_0<var<u1>>::token
0xfd6d  ldloc.0
0xfd6e  ldarg.0
0xfd6f  stfld    class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>> class <>c__DisplayClass44_0<var<u1>>::<>4__this
0xfd74  ldloc.0
0xfd75  ldarg.1
0xfd76  stfld    class [mscorlib]System.IO.TextReader class <>c__DisplayClass44_0<var<u1>>::reader
0xfd7b  ldloc.0
0xfd7c  ldfld    class [mscorlib]System.IO.TextReader class <>c__DisplayClass44_0<var<u1>>::reader
0xfd81  ldstr    aReader// "reader"
0xfd86  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xfd8b  ldloc.0
0xfd8c  ldftn    instance var<u1> class <>c__DisplayClass44_0<var<u1>>::<DeserializeAsync>b__0()
0xfd92  newobj   instance void class [mscorlib]System.Func`1<var<u1>>::.ctor(object, native int)
0xfd97  ldloc.0
0xfd98  ldfld    valuetype [mscorlib]System.Threading.CancellationToken class <>c__DisplayClass44_0<var<u1>>::token
0xfd9d  call     T0x2B000074
0xfda2  ret
```
