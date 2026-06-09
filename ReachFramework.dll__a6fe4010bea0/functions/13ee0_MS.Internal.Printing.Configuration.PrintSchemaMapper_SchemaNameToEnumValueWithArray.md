# MS.Internal.Printing.Configuration.PrintSchemaMapper::SchemaNameToEnumValueWithArray

- ea: `0x13ee0`
- end: `0x13f03`
- name: `MS.Internal.Printing.Configuration.PrintSchemaMapper::SchemaNameToEnumValueWithArray`
- size: `35`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0xe0c0`
- `0xe330`
- `0xe7d0`
- `0xead0`
- `0xf1a0`
- `0xf440`
- `0xf980`
- `0xfba0`
- `0xfdc0`
- `0x10520`
- `0x10a40`
- `0x10c60`
- `0x10e80`
- `0x110a0`
- `0x112c0`
- `0x114c0`
- `0x13f10`
- `0x16c10`

## callees

- `0x13ee0`

## pseudocode

```c

```

## disassembly

```asm
0x13ee0  ldc.i4.m1
0x13ee1  stloc.0
0x13ee2  ldc.i4.1
0x13ee3  stloc.1
0x13ee4  br.s     loc_13EFB
0x13ee6  ldarg.0
0x13ee7  ldloc.1
0x13ee8  ldelem.ref
0x13ee9  ldarg.2
0x13eea  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13eef  brfalse.s loc_13EF7
0x13ef1  ldarg.1
0x13ef2  ldloc.1
0x13ef3  ldelem.i4
0x13ef4  stloc.0
0x13ef5  br.s     loc_13F01
0x13ef7  ldloc.1
0x13ef8  ldc.i4.1
0x13ef9  add
0x13efa  stloc.1
0x13efb  ldloc.1
0x13efc  ldarg.0
0x13efd  ldlen
0x13efe  conv.i4
0x13eff  blt.s    loc_13EE6
0x13f01  ldloc.0
0x13f02  ret
```
