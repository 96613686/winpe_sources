# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18001d5b8`
- end: `0x18001d668`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800126a4`
- `0x18001d564`

## callees

- `0x1800021d0`
- `0x18001d5b8`
- `0x18001dcf4`
- `0x18001e4bc`
- `0x1800219a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d64f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d64f`

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
0x18001d5b8  push    rbx
0x18001d5ba  sub     rsp, 60h
0x18001d5be  mov     rax, cs:__security_cookie
0x18001d5c5  xor     rax, rsp
0x18001d5c8  mov     [rsp+68h+var_18], rax
0x18001d5cd  cmp     dword ptr [rcx+0E8h], 0
0x18001d5d4  xorps   xmm0, xmm0
0x18001d5d7  movups  [rsp+68h+var_48], xmm0
0x18001d5dc  mov     rbx, rcx
0x18001d5df  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18001d5e4  movups  [rsp+68h+var_28], xmm0
0x18001d5e9  jbe     short loc_18001D5EE
0x18001d5eb  or      edx, 8
0x18001d5ee  mov     r8d, [rcx+0B8h]
0x18001d5f5  lea     r9, [rsp+68h+var_48]
0x18001d5fa  mov     rcx, [rcx+0F0h]
0x18001d601  mov     qword ptr [rbx+0F0h], 0
0x18001d60c  call    TestQueryData
0x18001d611  test    eax, eax
0x18001d613  jz      short loc_18001D64A
0x18001d615  mov     eax, dword ptr [rsp+68h+pv+4]
0x18001d619  or      [rbx+40h], eax
0x18001d61c  cmp     [rsp+68h+pv+8], 0
0x18001d622  jz      short loc_18001D633
0x18001d624  lea     rdx, [rsp+68h+var_48]
0x18001d629  mov     rcx, rbx
0x18001d62c  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18001d631  jmp     short loc_18001D63D
0x18001d633  mov     eax, dword ptr [rsp+68h+pv]
0x18001d637  mov     [rbx+0B8h], eax
0x18001d63d  mov     rdx, qword ptr [rsp+68h+var_28]
0x18001d642  mov     rcx, rbx
0x18001d645  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x18001d64a  mov     rcx, [rsp+68h+pv+8]; pv
0x18001d64f  call    cs:__imp_CoTaskMemFree
0x18001d655  mov     rcx, [rsp+68h+var_18]
0x18001d65a  xor     rcx, rsp; StackCookie
0x18001d65d  call    __security_check_cookie
0x18001d662  add     rsp, 60h
0x18001d666  pop     rbx
0x18001d667  retn
```
