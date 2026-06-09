# Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1::Deserialize_0

- ea: `0xfc70`
- end: `0xfc98`
- name: `Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1::Deserialize_0`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0xfc70`
- `0x10210`

## string_xrefs

- `0xfc71`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0xfc70  ldarg.1
0xfc71  ldstr    aReader// "reader"
0xfc76  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xfc7b  ldarg.1
0xfc7c  newobj   instance void Microsoft.VisualStudio.Setup.Serialization.OptimizedJsonTextReader::.ctor(class [mscorlib]System.IO.TextReader reader)
0xfc81  stloc.0
0xfc82  ldarg.0
0xfc83  ldloc.0
0xfc84  call     instance var<u1> class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::Deserialize(!!T0)
0xfc89  stloc.1
0xfc8a  leave.s  loc_FC96
0xfc8c  ldloc.0
0xfc8d  brfalse.s loc_FC95
0xfc8f  ldloc.0
0xfc90  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfc95  endfinally
0xfc96  ldloc.1
0xfc97  ret
```
