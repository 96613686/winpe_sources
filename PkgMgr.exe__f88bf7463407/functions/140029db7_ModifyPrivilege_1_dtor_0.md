# _ModifyPrivilege_::_1_::dtor$0

- ea: `0x140029db7`
- end: `0x140029dc3`
- name: `_ModifyPrivilege_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x14000abf0`

## pseudocode

```c
int __fastcall ModifyPrivilege_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::details::lambda_call__ModifyPrivilege_::_2_::_lambda_1___::_lambda_call__ModifyPrivilege_::_2_::_lambda_1___((void ***)(a2 + 72));
}

```

## disassembly

```asm
0x140029db7  lea     rcx, [rdx+48h]
0x140029dbe  jmp     wil__details__lambda_call__ModifyPrivilege____2____lambda_1______lambda_call__ModifyPrivilege____2____lambda_1___
```
