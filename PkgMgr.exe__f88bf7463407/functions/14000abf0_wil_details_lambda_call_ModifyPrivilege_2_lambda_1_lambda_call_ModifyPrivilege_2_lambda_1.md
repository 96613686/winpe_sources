# wil::details::lambda_call__ModifyPrivilege_::_2_::_lambda_1___::_lambda_call__ModifyPrivilege_::_2_::_lambda_1___

- ea: `0x14000abf0`
- end: `0x14000ac14`
- name: `wil::details::lambda_call__ModifyPrivilege_::_2_::_lambda_1___::_lambda_call__ModifyPrivilege_::_2_::_lambda_1___`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140029db7`

## callees

- `0x14000abf0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ac09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ac09`

## pseudocode

```c
int __fastcall wil::details::lambda_call__ModifyPrivilege_::_2_::_lambda_1___::_lambda_call__ModifyPrivilege_::_2_::_lambda_1___(
        void ***a1)
{
  void **v1; // rax
  void *v2; // rcx

  if ( *((_BYTE *)a1 + 8) )
  {
    *((_BYTE *)a1 + 8) = 0;
    v1 = *a1;
    v2 = **a1;
    if ( v2 )
      LODWORD(v1) = CloseHandle(v2);
  }
  return (int)v1;
}

```

## disassembly

```asm
0x14000abf0  sub     rsp, 28h
0x14000abf4  cmp     byte ptr [rcx+8], 0
0x14000abf8  jz      short loc_14000AC0F
0x14000abfa  mov     byte ptr [rcx+8], 0
0x14000abfe  mov     rax, [rcx]
0x14000ac01  mov     rcx, [rax]; hObject
0x14000ac04  test    rcx, rcx
0x14000ac07  jz      short loc_14000AC0F
0x14000ac09  call    cs:__imp_CloseHandle
0x14000ac0f  add     rsp, 28h
0x14000ac13  retn
```
