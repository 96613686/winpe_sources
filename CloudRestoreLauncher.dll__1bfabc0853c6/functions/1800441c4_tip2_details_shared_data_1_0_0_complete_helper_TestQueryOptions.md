# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x1800441c4`
- end: `0x180044274`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004427c`
- `0x18004581c`

## callees

- `0x18000c6e0`
- `0x1800134d4`
- `0x1800229a0`
- `0x1800441c4`
- `0x1800444e8`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x18004425b`
- `OLE32!CoTaskMemFree` at `0x18004425b`

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
0x1800441c4  push    rbx
0x1800441c6  sub     rsp, 60h
0x1800441ca  mov     rax, cs:__security_cookie
0x1800441d1  xor     rax, rsp
0x1800441d4  mov     [rsp+68h+var_18], rax
0x1800441d9  cmp     dword ptr [rcx+0E8h], 0
0x1800441e0  xorps   xmm0, xmm0
0x1800441e3  movups  [rsp+68h+var_48], xmm0
0x1800441e8  mov     rbx, rcx
0x1800441eb  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1800441f0  movups  [rsp+68h+var_28], xmm0
0x1800441f5  jbe     short loc_1800441FA
0x1800441f7  or      edx, 8
0x1800441fa  mov     r8d, [rcx+0B8h]
0x180044201  lea     r9, [rsp+68h+var_48]
0x180044206  mov     rcx, [rcx+0F0h]
0x18004420d  mov     qword ptr [rbx+0F0h], 0
0x180044218  call    TestQueryData
0x18004421d  test    eax, eax
0x18004421f  jz      short loc_180044256
0x180044221  mov     eax, dword ptr [rsp+68h+pv+4]
0x180044225  or      [rbx+40h], eax
0x180044228  cmp     [rsp+68h+pv+8], 0
0x18004422e  jz      short loc_18004423F
0x180044230  lea     rdx, [rsp+68h+var_48]
0x180044235  mov     rcx, rbx
0x180044238  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18004423d  jmp     short loc_180044249
0x18004423f  mov     eax, dword ptr [rsp+68h+pv]
0x180044243  mov     [rbx+0B8h], eax
0x180044249  mov     rdx, qword ptr [rsp+68h+var_28]
0x18004424e  mov     rcx, rbx
0x180044251  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x180044256  mov     rcx, [rsp+68h+pv+8]; pv
0x18004425b  call    cs:__imp_CoTaskMemFree
0x180044261  mov     rcx, [rsp+68h+var_18]
0x180044266  xor     rcx, rsp; StackCookie
0x180044269  call    __security_check_cookie
0x18004426e  add     rsp, 60h
0x180044272  pop     rbx
0x180044273  retn
```
