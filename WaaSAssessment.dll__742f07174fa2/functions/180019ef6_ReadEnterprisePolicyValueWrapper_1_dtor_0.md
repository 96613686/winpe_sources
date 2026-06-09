# _ReadEnterprisePolicyValueWrapper_::_1_::dtor$0

- ea: `0x180019ef6`
- end: `0x180019f02`
- name: `_ReadEnterprisePolicyValueWrapper_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180019174`

## pseudocode

```c
__int64 __fastcall ReadEnterprisePolicyValueWrapper_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::details::lambda_call__lambda_1d38f8de06ea7cfbd666fe5880786ec8___::_lambda_call__lambda_1d38f8de06ea7cfbd666fe5880786ec8___(a2 + 32);
}

```

## disassembly

```asm
0x180019ef6  lea     rcx, [rdx+20h]
0x180019efd  jmp     wil__details__lambda_call__lambda_1d38f8de06ea7cfbd666fe5880786ec8______lambda_call__lambda_1d38f8de06ea7cfbd666fe5880786ec8___
```
