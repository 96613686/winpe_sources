# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::ReplaceFileName

- ea: `0x1950`
- end: `0x1b6a`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::ReplaceFileName`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x28d0`

## callees

- `0x1950`
- `0x3e60`

## pseudocode

```c

```

## disassembly

```asm
0x1950  ldstr    asc_5248// ""
0x1955  stloc.0
0x1956  ldc.i4.0
0x1957  stloc.1
0x1958  br       loc_1B5C
0x195d  ldarg.0
0x195e  ldloc.1
0x195f  ldc.i4.1
0x1960  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1965  stloc.2
0x1966  ldloc.2
0x1967  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x196c  stloc.3
0x196d  ldloc.3
0x196e  ldc.i4   0x390CAEFB
0x1973  bgt.un.s loc_19E1
0x1975  ldloc.3
0x1976  ldc.i4   0x290C95CB
0x197b  bgt.un.s loc_19A3
0x197d  ldloc.3
0x197e  ldc.i4   0x230C8C59
0x1983  beq      loc_1B2E
0x1988  ldloc.3
0x1989  ldc.i4   0x270C92A5
0x198e  beq      loc_1B1F
0x1993  ldloc.3
0x1994  ldc.i4   0x290C95CB
0x1999  beq      loc_1AF2
0x199e  br       loc_1B49
0x19a3  ldloc.3
0x19a4  ldc.i4   0x2E0C9DAA
0x19a9  bgt.un.s loc_19C6
0x19ab  ldloc.3
0x19ac  ldc.i4   0x2A0C975E
0x19b1  beq      loc_1A4A
0x19b6  ldloc.3
0x19b7  ldc.i4   0x2E0C9DAA
0x19bc  beq      loc_1AE3
0x19c1  br       loc_1B49
0x19c6  ldloc.3
0x19c7  ldc.i4   0x2F0C9F3D
0x19cc  beq      loc_1A89
0x19d1  ldloc.3
0x19d2  ldc.i4   0x390CAEFB
0x19d7  beq      loc_1AB3
0x19dc  br       loc_1B49
0x19e1  ldloc.3
0x19e2  ldc.i4   0x3F0CB86D
0x19e7  bgt.un.s loc_1A0F
0x19e9  ldloc.3
0x19ea  ldc.i4   0x3A0CB08E
0x19ef  beq      loc_1A74
0x19f4  ldloc.3
0x19f5  ldc.i4   0x3B0CB221
0x19fa  beq      loc_1AC5
0x19ff  ldloc.3
0x1a00  ldc.i4   0x3F0CB86D
0x1a05  beq      loc_1A9E
0x1a0a  br       loc_1B49
0x1a0f  ldloc.3
0x1a10  ldc.i4   0xD90C17DB
0x1a15  bgt.un.s loc_1A2F
0x1a17  ldloc.3
0x1a18  ldc.i4   0xD80C1648
0x1a1d  beq      loc_1B10
0x1a22  ldloc.3
0x1a23  ldc.i4   0xD90C17DB
0x1a28  beq.s    loc_1A5F
0x1a2a  br       loc_1B49
0x1a2f  ldloc.3
0x1a30  ldc.i4   0xDE0C1FBA
0x1a35  beq      loc_1B01
0x1a3a  ldloc.3
0x1a3b  ldc.i4   0xF90C4A3B
0x1a40  beq      loc_1AD4
0x1a45  br       loc_1B49
0x1a4a  ldloc.2
0x1a4b  ldstr    asc_55EA// "/"
0x1a50  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1a55  brtrue   loc_1B3B
0x1a5a  br       loc_1B49
0x1a5f  ldloc.2
0x1a60  ldstr    asc_55E6// "\\"
0x1a65  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1a6a  brtrue   loc_1B3B
0x1a6f  br       loc_1B49
0x1a74  ldloc.2
0x1a75  ldstr    asc_55EE// "?"
0x1a7a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1a7f  brtrue   loc_1B3B
0x1a84  br       loc_1B49
0x1a89  ldloc.2
0x1a8a  ldstr    asc_55F2// "*"
0x1a8f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1a94  brtrue   loc_1B3B
0x1a99  br       loc_1B49
0x1a9e  ldloc.2
0x1a9f  ldstr    asc_55F6// ":"
0x1aa4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1aa9  brtrue   loc_1B3B
0x1aae  br       loc_1B49
0x1ab3  ldloc.2
0x1ab4  ldstr    asc_55FA// "<"
0x1ab9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1abe  brtrue.s loc_1B3B
0x1ac0  br       loc_1B49
0x1ac5  ldloc.2
0x1ac6  ldstr    asc_55FE// ">"
0x1acb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ad0  brtrue.s loc_1B3B
0x1ad2  br.s     loc_1B49
0x1ad4  ldloc.2
0x1ad5  ldstr    asc_5602// "|"
0x1ada  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1adf  brtrue.s loc_1B3B
0x1ae1  br.s     loc_1B49
0x1ae3  ldloc.2
0x1ae4  ldstr    asc_5606// "+"
0x1ae9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1aee  brtrue.s loc_1B3B
0x1af0  br.s     loc_1B49
0x1af2  ldloc.2
0x1af3  ldstr    asc_560A// ","
0x1af8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1afd  brtrue.s loc_1B3B
0x1aff  br.s     loc_1B49
0x1b01  ldloc.2
0x1b02  ldstr    asc_560E// "["
0x1b07  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b0c  brtrue.s loc_1B3B
0x1b0e  br.s     loc_1B49
0x1b10  ldloc.2
0x1b11  ldstr    asc_5612// "]"
0x1b16  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b1b  brtrue.s loc_1B3B
0x1b1d  br.s     loc_1B49
0x1b1f  ldloc.2
0x1b20  ldstr    asc_5616// "\""
0x1b25  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b2a  brtrue.s loc_1B3B
0x1b2c  br.s     loc_1B49
0x1b2e  ldloc.2
0x1b2f  ldstr    asc_561A// "&"
0x1b34  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b39  brfalse.s loc_1B49
0x1b3b  ldloc.0
0x1b3c  ldstr    asc_5244// "_"
0x1b41  call     string [mscorlib]System.String::Concat(string, string)
0x1b46  stloc.0
0x1b47  br.s     loc_1B58
0x1b49  ldloc.0
0x1b4a  ldarg.0
0x1b4b  ldloc.1
0x1b4c  ldc.i4.1
0x1b4d  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1b52  call     string [mscorlib]System.String::Concat(string, string)
0x1b57  stloc.0
0x1b58  ldloc.1
0x1b59  ldc.i4.1
0x1b5a  add
0x1b5b  stloc.1
0x1b5c  ldloc.1
0x1b5d  ldarg.0
0x1b5e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1b63  blt      loc_195D
0x1b68  ldloc.0
0x1b69  ret
```
