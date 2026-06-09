# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180037e68`
- end: `0x180037f18`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180034ca0`
- `0x180037e3c`
- `0x180039190`
- `0x1800428ac`

## callees

- `0x180009190`
- `0x18002c8f8`
- `0x180037e68`
- `0x180038098`
- `0x18003847c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037eff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037eff`

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
0x180037e68  push    rbx
0x180037e6a  sub     rsp, 60h
0x180037e6e  mov     rax, cs:__security_cookie
0x180037e75  xor     rax, rsp
0x180037e78  mov     [rsp+68h+var_18], rax
0x180037e7d  cmp     dword ptr [rcx+0E8h], 0
0x180037e84  xorps   xmm0, xmm0
0x180037e87  movups  [rsp+68h+var_48], xmm0
0x180037e8c  mov     rbx, rcx
0x180037e8f  movups  xmmword ptr [rsp+68h+pv], xmm0
0x180037e94  movups  [rsp+68h+var_28], xmm0
0x180037e99  jbe     short loc_180037E9E
0x180037e9b  or      edx, 8
0x180037e9e  mov     r8d, [rcx+0B8h]
0x180037ea5  lea     r9, [rsp+68h+var_48]
0x180037eaa  mov     rcx, [rcx+0F0h]
0x180037eb1  mov     qword ptr [rbx+0F0h], 0
0x180037ebc  call    TestQueryData
0x180037ec1  test    eax, eax
0x180037ec3  jz      short loc_180037EFA
0x180037ec5  mov     eax, dword ptr [rsp+68h+pv+4]
0x180037ec9  or      [rbx+40h], eax
0x180037ecc  cmp     [rsp+68h+pv+8], 0
0x180037ed2  jz      short loc_180037EE3
0x180037ed4  lea     rdx, [rsp+68h+var_48]
0x180037ed9  mov     rcx, rbx
0x180037edc  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180037ee1  jmp     short loc_180037EED
0x180037ee3  mov     eax, dword ptr [rsp+68h+pv]
0x180037ee7  mov     [rbx+0B8h], eax
0x180037eed  mov     rdx, qword ptr [rsp+68h+var_28]
0x180037ef2  mov     rcx, rbx
0x180037ef5  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x180037efa  mov     rcx, [rsp+68h+pv+8]; pv
0x180037eff  call    cs:__imp_CoTaskMemFree
0x180037f05  mov     rcx, [rsp+68h+var_18]
0x180037f0a  xor     rcx, rsp; StackCookie
0x180037f0d  call    __security_check_cookie
0x180037f12  add     rsp, 60h
0x180037f16  pop     rbx
0x180037f17  retn
```
