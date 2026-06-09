# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x1800231b4`
- end: `0x180023264`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002326c`
- `0x180024798`

## callees

- `0x180003560`
- `0x1800231b4`
- `0x1800234b8`
- `0x180023a04`
- `0x180026470`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002324b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002324b`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::complete_helper(__int64 a1, __int64 a2)
{
  bool v2; // zf
  __int64 v4; // r8
  __int64 v5; // rcx
  __int128 v6; // [rsp+20h] [rbp-48h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-38h]
  __int128 v8; // [rsp+40h] [rbp-28h]

  v2 = *(_DWORD *)(a1 + 232) == 0;
  v6 = 0;
  *(_OWORD *)pv = 0;
  v8 = 0;
  if ( !v2 )
    a2 = (unsigned int)a2 | 8;
  v4 = *(unsigned int *)(a1 + 184);
  v5 = *(_QWORD *)(a1 + 240);
  *(_QWORD *)(a1 + 240) = 0;
  if ( (unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64, __int128 *))TestQueryData)(v5, a2, v4, &v6) )
  {
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( pv[1] )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v6);
    else
      *(_DWORD *)(a1 + 184) = pv[0];
    tip2::details::shared_data<1,0,0>::evaluate_and_report(a1, v8);
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x1800231b4  push    rbx
0x1800231b6  sub     rsp, 60h
0x1800231ba  mov     rax, cs:__security_cookie
0x1800231c1  xor     rax, rsp
0x1800231c4  mov     [rsp+68h+var_18], rax
0x1800231c9  cmp     dword ptr [rcx+0E8h], 0
0x1800231d0  xorps   xmm0, xmm0
0x1800231d3  movups  [rsp+68h+var_48], xmm0
0x1800231d8  mov     rbx, rcx
0x1800231db  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1800231e0  movups  [rsp+68h+var_28], xmm0
0x1800231e5  jbe     short loc_1800231EA
0x1800231e7  or      edx, 8
0x1800231ea  mov     r8d, [rcx+0B8h]
0x1800231f1  lea     r9, [rsp+68h+var_48]
0x1800231f6  mov     rcx, [rcx+0F0h]
0x1800231fd  mov     qword ptr [rbx+0F0h], 0
0x180023208  call    TestQueryData
0x18002320d  test    eax, eax
0x18002320f  jz      short loc_180023246
0x180023211  mov     eax, dword ptr [rsp+68h+pv+4]
0x180023215  or      [rbx+40h], eax
0x180023218  cmp     [rsp+68h+pv+8], 0
0x18002321e  jz      short loc_18002322F
0x180023220  lea     rdx, [rsp+68h+var_48]
0x180023225  mov     rcx, rbx
0x180023228  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18002322d  jmp     short loc_180023239
0x18002322f  mov     eax, dword ptr [rsp+68h+pv]
0x180023233  mov     [rbx+0B8h], eax
0x180023239  mov     rdx, qword ptr [rsp+68h+var_28]
0x18002323e  mov     rcx, rbx
0x180023241  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x180023246  mov     rcx, [rsp+68h+pv+8]; pv
0x18002324b  call    cs:__imp_CoTaskMemFree
0x180023251  mov     rcx, [rsp+68h+var_18]
0x180023256  xor     rcx, rsp; StackCookie
0x180023259  call    __security_check_cookie
0x18002325e  add     rsp, 60h
0x180023262  pop     rbx
0x180023263  retn
```
