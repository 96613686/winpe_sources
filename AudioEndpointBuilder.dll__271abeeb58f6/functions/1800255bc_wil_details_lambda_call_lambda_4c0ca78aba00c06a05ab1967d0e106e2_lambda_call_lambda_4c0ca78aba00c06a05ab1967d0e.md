# wil::details::lambda_call__lambda_4c0ca78aba00c06a05ab1967d0e106e2___::_lambda_call__lambda_4c0ca78aba00c06a05ab1967d0e106e2___

- ea: `0x1800255bc`
- end: `0x18002560d`
- name: `wil::details::lambda_call__lambda_4c0ca78aba00c06a05ab1967d0e106e2___::_lambda_call__lambda_4c0ca78aba00c06a05ab1967d0e106e2___`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180066350`

## callees

- `0x1800255bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255f6`

## pseudocode

```c
LPVOID *__fastcall wil::details::lambda_call__lambda_4c0ca78aba00c06a05ab1967d0e106e2___::_lambda_call__lambda_4c0ca78aba00c06a05ab1967d0e106e2___(
        __int64 a1)
{
  LPVOID *result; // rax
  void *v3; // rcx

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    v3 = **(void ***)a1;
    if ( v3 )
    {
      CoTaskMemFree(v3);
      **(_QWORD **)a1 = 0;
    }
    result = *(LPVOID **)(a1 + 8);
    if ( *result )
    {
      CoTaskMemFree(*result);
      result = *(LPVOID **)(a1 + 8);
      *result = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800255bc  push    rbx
0x1800255be  sub     rsp, 20h
0x1800255c2  cmp     byte ptr [rcx+10h], 0
0x1800255c6  mov     rbx, rcx
0x1800255c9  jz      short loc_180025607
0x1800255cb  mov     byte ptr [rcx+10h], 0
0x1800255cf  mov     rax, [rcx]
0x1800255d2  mov     rcx, [rax]; pv
0x1800255d5  test    rcx, rcx
0x1800255d8  jz      short loc_1800255EA
0x1800255da  call    cs:__imp_CoTaskMemFree
0x1800255e0  mov     rax, [rbx]
0x1800255e3  mov     qword ptr [rax], 0
0x1800255ea  mov     rax, [rbx+8]
0x1800255ee  mov     rcx, [rax]; pv
0x1800255f1  test    rcx, rcx
0x1800255f4  jz      short loc_180025607
0x1800255f6  call    cs:__imp_CoTaskMemFree
0x1800255fc  mov     rax, [rbx+8]
0x180025600  mov     qword ptr [rax], 0
0x180025607  add     rsp, 20h
0x18002560b  pop     rbx
0x18002560c  retn
```
