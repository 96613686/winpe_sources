# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x1800763c8`
- end: `0x180076478`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800773c0`
- `0x180082ba0`

## callees

- `0x180057ac4`
- `0x180061320`
- `0x1800763c8`
- `0x180076870`
- `0x1800785e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007645f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007645f`

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
0x1800763c8  push    rbx
0x1800763ca  sub     rsp, 60h
0x1800763ce  mov     rax, cs:__security_cookie
0x1800763d5  xor     rax, rsp
0x1800763d8  mov     [rsp+68h+var_18], rax
0x1800763dd  cmp     dword ptr [rcx+0E8h], 0
0x1800763e4  xorps   xmm0, xmm0
0x1800763e7  movups  [rsp+68h+var_48], xmm0
0x1800763ec  mov     rbx, rcx
0x1800763ef  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1800763f4  movups  [rsp+68h+var_28], xmm0
0x1800763f9  jbe     short loc_1800763FE
0x1800763fb  or      edx, 8
0x1800763fe  mov     r8d, [rcx+0B8h]
0x180076405  lea     r9, [rsp+68h+var_48]
0x18007640a  mov     rcx, [rcx+0F0h]
0x180076411  mov     qword ptr [rbx+0F0h], 0
0x18007641c  call    TestQueryData
0x180076421  test    eax, eax
0x180076423  jz      short loc_18007645A
0x180076425  mov     eax, dword ptr [rsp+68h+pv+4]
0x180076429  or      [rbx+40h], eax
0x18007642c  cmp     [rsp+68h+pv+8], 0
0x180076432  jz      short loc_180076443
0x180076434  lea     rdx, [rsp+68h+var_48]
0x180076439  mov     rcx, rbx
0x18007643c  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180076441  jmp     short loc_18007644D
0x180076443  mov     eax, dword ptr [rsp+68h+pv]
0x180076447  mov     [rbx+0B8h], eax
0x18007644d  mov     rdx, qword ptr [rsp+68h+var_28]
0x180076452  mov     rcx, rbx
0x180076455  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x18007645a  mov     rcx, [rsp+68h+pv+8]; pv
0x18007645f  call    cs:__imp_CoTaskMemFree
0x180076465  mov     rcx, [rsp+68h+var_18]
0x18007646a  xor     rcx, rsp; StackCookie
0x18007646d  call    __security_check_cookie
0x180076472  add     rsp, 60h
0x180076476  pop     rbx
0x180076477  retn
```
