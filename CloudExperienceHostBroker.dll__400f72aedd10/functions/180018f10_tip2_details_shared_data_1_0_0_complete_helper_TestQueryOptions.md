# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180018f10`
- end: `0x180018fc0`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012268`
- `0x180012dc0`

## callees

- `0x180009f30`
- `0x180018f10`
- `0x180019158`
- `0x180019638`
- `0x18001bae8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018fa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018fa7`

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
0x180018f10  push    rbx
0x180018f12  sub     rsp, 60h
0x180018f16  mov     rax, cs:__security_cookie
0x180018f1d  xor     rax, rsp
0x180018f20  mov     [rsp+68h+var_18], rax
0x180018f25  cmp     dword ptr [rcx+0E8h], 0
0x180018f2c  xorps   xmm0, xmm0
0x180018f2f  movups  [rsp+68h+var_48], xmm0
0x180018f34  mov     rbx, rcx
0x180018f37  movups  xmmword ptr [rsp+68h+pv], xmm0
0x180018f3c  movups  [rsp+68h+var_28], xmm0
0x180018f41  jbe     short loc_180018F46
0x180018f43  or      edx, 8
0x180018f46  mov     r8d, [rcx+0B8h]
0x180018f4d  lea     r9, [rsp+68h+var_48]
0x180018f52  mov     rcx, [rcx+0F0h]
0x180018f59  mov     qword ptr [rbx+0F0h], 0
0x180018f64  call    TestQueryData
0x180018f69  test    eax, eax
0x180018f6b  jz      short loc_180018FA2
0x180018f6d  mov     eax, dword ptr [rsp+68h+pv+4]
0x180018f71  or      [rbx+40h], eax
0x180018f74  cmp     [rsp+68h+pv+8], 0
0x180018f7a  jz      short loc_180018F8B
0x180018f7c  lea     rdx, [rsp+68h+var_48]
0x180018f81  mov     rcx, rbx
0x180018f84  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180018f89  jmp     short loc_180018F95
0x180018f8b  mov     eax, dword ptr [rsp+68h+pv]
0x180018f8f  mov     [rbx+0B8h], eax
0x180018f95  mov     rdx, qword ptr [rsp+68h+var_28]
0x180018f9a  mov     rcx, rbx
0x180018f9d  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x180018fa2  mov     rcx, [rsp+68h+pv+8]; pv
0x180018fa7  call    cs:__imp_CoTaskMemFree
0x180018fad  mov     rcx, [rsp+68h+var_18]
0x180018fb2  xor     rcx, rsp; StackCookie
0x180018fb5  call    __security_check_cookie
0x180018fba  add     rsp, 60h
0x180018fbe  pop     rbx
0x180018fbf  retn
```
