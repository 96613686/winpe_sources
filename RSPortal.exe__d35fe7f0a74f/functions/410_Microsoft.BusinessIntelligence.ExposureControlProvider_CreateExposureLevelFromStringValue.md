# Microsoft.BusinessIntelligence.ExposureControlProvider::CreateExposureLevelFromStringValue

- ea: `0x410`
- end: `0x457`
- name: `Microsoft.BusinessIntelligence.ExposureControlProvider::CreateExposureLevelFromStringValue`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3f0`

## callees

- `0x410`

## pseudocode

```c

```

## disassembly

```asm
0x410  ldarg.1
0x411  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x416  brtrue.s loc_420
0x418  ldarg.1
0x419  callvirt instance string [mscorlib]System.String::Trim()
0x41e  starg.s  1
0x420  ldarg.1
0x421  ldstr    a1// "1"
0x426  call     bool [mscorlib]System.String::Equals(string, string)
0x42b  brfalse.s loc_431
0x42d  ldc.i4.1
0x42e  stloc.0
0x42f  br.s     loc_455
0x431  ldarg.1
0x432  ldstr    a2// "2"
0x437  call     bool [mscorlib]System.String::Equals(string, string)
0x43c  brfalse.s loc_442
0x43e  ldc.i4.2
0x43f  stloc.0
0x440  br.s     loc_455
0x442  ldarg.1
0x443  ldstr    a3// "3"
0x448  call     bool [mscorlib]System.String::Equals(string, string)
0x44d  brfalse.s loc_453
0x44f  ldc.i4.3
0x450  stloc.0
0x451  br.s     loc_455
0x453  ldc.i4.0
0x454  stloc.0
0x455  ldloc.0
0x456  ret
```
