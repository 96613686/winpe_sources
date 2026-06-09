# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareArrays

- ea: `0x1ac0`
- end: `0x1d97`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareArrays`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2df0`

## callees

- `0x1ac0`

## pseudocode

```c

```

## disassembly

```asm
0x1ac0  ldarg.1
0x1ac1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1ac6  stloc.0
0x1ac7  ldloc.0
0x1ac8  ldtoken  bool[]
0x1acd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ad2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1ad7  brfalse.s loc_1AEC
0x1ad9  ldarg.0
0x1ada  ldarg.1
0x1adb  castclass bool[]
0x1ae0  ldarg.2
0x1ae1  castclass bool[]
0x1ae6  call     T0x2B00000B
0x1aeb  ret
0x1aec  ldloc.0
0x1aed  ldtoken  char[]
0x1af2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1af7  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1afc  brfalse.s loc_1B11
0x1afe  ldarg.0
0x1aff  ldarg.1
0x1b00  castclass char[]
0x1b05  ldarg.2
0x1b06  castclass char[]
0x1b0b  call     T0x2B00000C
0x1b10  ret
0x1b11  ldloc.0
0x1b12  ldtoken  int8[]
0x1b17  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b1c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1b21  brfalse.s loc_1B36
0x1b23  ldarg.0
0x1b24  ldarg.1
0x1b25  castclass int8[]
0x1b2a  ldarg.2
0x1b2b  castclass int8[]
0x1b30  call     T0x2B00000D
0x1b35  ret
0x1b36  ldloc.0
0x1b37  ldtoken  unsigned int8[]
0x1b3c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b41  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1b46  brfalse.s loc_1B5B
0x1b48  ldarg.0
0x1b49  ldarg.1
0x1b4a  castclass unsigned int8[]
0x1b4f  ldarg.2
0x1b50  castclass unsigned int8[]
0x1b55  call     T0x2B00000E
0x1b5a  ret
0x1b5b  ldloc.0
0x1b5c  ldtoken  int16[]
0x1b61  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b66  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1b6b  brfalse.s loc_1B80
0x1b6d  ldarg.0
0x1b6e  ldarg.1
0x1b6f  castclass int16[]
0x1b74  ldarg.2
0x1b75  castclass int16[]
0x1b7a  call     T0x2B00000F
0x1b7f  ret
0x1b80  ldloc.0
0x1b81  ldtoken  unsigned int16[]
0x1b86  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b8b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1b90  brfalse.s loc_1BA5
0x1b92  ldarg.0
0x1b93  ldarg.1
0x1b94  castclass unsigned int16[]
0x1b99  ldarg.2
0x1b9a  castclass unsigned int16[]
0x1b9f  call     T0x2B000010
0x1ba4  ret
0x1ba5  ldloc.0
0x1ba6  ldtoken  int32[]
0x1bab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bb0  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1bb5  brfalse.s loc_1BCA
0x1bb7  ldarg.0
0x1bb8  ldarg.1
0x1bb9  castclass int32[]
0x1bbe  ldarg.2
0x1bbf  castclass int32[]
0x1bc4  call     T0x2B000011
0x1bc9  ret
0x1bca  ldloc.0
0x1bcb  ldtoken  unsigned int32[]
0x1bd0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd5  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1bda  brfalse.s loc_1BEF
0x1bdc  ldarg.0
0x1bdd  ldarg.1
0x1bde  castclass unsigned int32[]
0x1be3  ldarg.2
0x1be4  castclass unsigned int32[]
0x1be9  call     T0x2B000012
0x1bee  ret
0x1bef  ldloc.0
0x1bf0  ldtoken  int64[]
0x1bf5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bfa  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1bff  brfalse.s loc_1C14
0x1c01  ldarg.0
0x1c02  ldarg.1
0x1c03  castclass int64[]
0x1c08  ldarg.2
0x1c09  castclass int64[]
0x1c0e  call     T0x2B000013
0x1c13  ret
0x1c14  ldloc.0
0x1c15  ldtoken  unsigned int64[]
0x1c1a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c1f  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c24  brfalse.s loc_1C39
0x1c26  ldarg.0
0x1c27  ldarg.1
0x1c28  castclass unsigned int64[]
0x1c2d  ldarg.2
0x1c2e  castclass unsigned int64[]
0x1c33  call     T0x2B000014
0x1c38  ret
0x1c39  ldloc.0
0x1c3a  ldtoken  float32[]
0x1c3f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c44  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c49  brfalse.s loc_1C5E
0x1c4b  ldarg.0
0x1c4c  ldarg.1
0x1c4d  castclass float32[]
0x1c52  ldarg.2
0x1c53  castclass float32[]
0x1c58  call     T0x2B000015
0x1c5d  ret
0x1c5e  ldloc.0
0x1c5f  ldtoken  float64[]
0x1c64  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c69  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c6e  brfalse.s loc_1C83
0x1c70  ldarg.0
0x1c71  ldarg.1
0x1c72  castclass float64[]
0x1c77  ldarg.2
0x1c78  castclass float64[]
0x1c7d  call     T0x2B000016
0x1c82  ret
0x1c83  ldloc.0
0x1c84  ldtoken  valuetype [mscorlib]System.Decimal[]
0x1c89  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c8e  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c93  brfalse.s loc_1CA8
0x1c95  ldarg.0
0x1c96  ldarg.1
0x1c97  castclass valuetype [mscorlib]System.Decimal[]
0x1c9c  ldarg.2
0x1c9d  castclass valuetype [mscorlib]System.Decimal[]
0x1ca2  call     T0x2B000017
0x1ca7  ret
0x1ca8  ldloc.0
0x1ca9  ldtoken  valuetype [mscorlib]System.DateTime[]
0x1cae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1cb3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1cb8  brfalse.s loc_1CCD
0x1cba  ldarg.0
0x1cbb  ldarg.1
0x1cbc  castclass valuetype [mscorlib]System.DateTime[]
0x1cc1  ldarg.2
0x1cc2  castclass valuetype [mscorlib]System.DateTime[]
0x1cc7  call     T0x2B000018
0x1ccc  ret
0x1ccd  ldloc.0
0x1cce  ldtoken  valuetype [mscorlib]System.DateTimeOffset[]
0x1cd3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1cd8  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1cdd  brfalse.s loc_1CF2
0x1cdf  ldarg.0
0x1ce0  ldarg.1
0x1ce1  castclass valuetype [mscorlib]System.DateTimeOffset[]
0x1ce6  ldarg.2
0x1ce7  castclass valuetype [mscorlib]System.DateTimeOffset[]
0x1cec  call     T0x2B000019
0x1cf1  ret
0x1cf2  ldloc.0
0x1cf3  ldtoken  valuetype [mscorlib]System.TimeSpan[]
0x1cf8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1cfd  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1d02  brfalse.s loc_1D17
0x1d04  ldarg.0
0x1d05  ldarg.1
0x1d06  castclass valuetype [mscorlib]System.TimeSpan[]
0x1d0b  ldarg.2
0x1d0c  castclass valuetype [mscorlib]System.TimeSpan[]
0x1d11  call     T0x2B00001A
0x1d16  ret
0x1d17  ldloc.0
0x1d18  ldtoken  string[]
0x1d1d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d22  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1d27  brfalse.s loc_1D3C
0x1d29  ldarg.0
0x1d2a  ldarg.1
0x1d2b  castclass string[]
0x1d30  ldarg.2
0x1d31  castclass string[]
0x1d36  call     T0x2B00001B
0x1d3b  ret
0x1d3c  ldloc.0
0x1d3d  ldtoken  object[]
0x1d42  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d47  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1d4c  brfalse.s loc_1D61
0x1d4e  ldarg.0
0x1d4f  ldarg.1
0x1d50  castclass object[]
0x1d55  ldarg.2
0x1d56  castclass object[]
0x1d5b  call     T0x2B00001C
0x1d60  ret
0x1d61  ldloc.0
0x1d62  ldtoken  valuetype [mscorlib]System.Guid[]
0x1d67  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d6c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1d71  brfalse.s loc_1D86
0x1d73  ldarg.0
0x1d74  ldarg.1
0x1d75  castclass valuetype [mscorlib]System.Guid[]
0x1d7a  ldarg.2
0x1d7b  castclass valuetype [mscorlib]System.Guid[]
0x1d80  call     T0x2B00001D
0x1d85  ret
0x1d86  ldstr    aSertUnsupporte// "SERT: UnsupportedType: {0}"
0x1d8b  ldloc.0
0x1d8c  call     string [mscorlib]System.String::Format(string, object)
0x1d91  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1d96  throw
```
