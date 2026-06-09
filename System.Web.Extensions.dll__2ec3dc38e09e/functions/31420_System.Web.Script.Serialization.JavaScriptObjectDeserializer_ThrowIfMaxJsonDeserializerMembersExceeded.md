# System.Web.Script.Serialization.JavaScriptObjectDeserializer::ThrowIfMaxJsonDeserializerMembersExceeded

- ea: `0x31420`
- end: `0x3144c`
- name: `System.Web.Script.Serialization.JavaScriptObjectDeserializer::ThrowIfMaxJsonDeserializerMembersExceeded`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x31170`

## callees

- `0x31420`

## string_xrefs

- `0x31428`: `CollectionCountExceeded_JavaScriptObjectDeserializer`

## pseudocode

```c

```

## disassembly

```asm
0x31420  ldarg.1
0x31421  call     int32 [System.Web]System.Web.Util.AppSettings::get_MaxJsonDeserializerMembers()
0x31426  blt.s    loc_3144B
0x31428  ldstr    aCollectioncoun// "CollectionCountExceeded_JavaScriptObjec"...
0x3142d  ldc.i4.1
0x3142e  newarr   [mscorlib]System.Object
0x31433  dup
0x31434  ldc.i4.0
0x31435  call     int32 [System.Web]System.Web.Util.AppSettings::get_MaxJsonDeserializerMembers()
0x3143a  box      [mscorlib]System.Int32
0x3143f  stelem.ref
0x31440  call     string [System.Web]System.Web.SR::GetString(string, object[])
0x31445  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3144a  throw
0x3144b  ret
```
