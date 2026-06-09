# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x1800368cc`
- end: `0x18003697c`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180036038`
- `0x180047dc4`

## callees

- `0x180027bc8`
- `0x18002cd20`
- `0x1800368cc`
- `0x180036b70`
- `0x1800384a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036963`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036963`

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
0x1800368cc  push    rbx
0x1800368ce  sub     rsp, 60h
0x1800368d2  mov     rax, cs:__security_cookie
0x1800368d9  xor     rax, rsp
0x1800368dc  mov     [rsp+68h+var_18], rax
0x1800368e1  cmp     dword ptr [rcx+0E8h], 0
0x1800368e8  xorps   xmm0, xmm0
0x1800368eb  movups  [rsp+68h+var_48], xmm0
0x1800368f0  mov     rbx, rcx
0x1800368f3  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1800368f8  movups  [rsp+68h+var_28], xmm0
0x1800368fd  jbe     short loc_180036902
0x1800368ff  or      edx, 8
0x180036902  mov     r8d, [rcx+0B8h]
0x180036909  lea     r9, [rsp+68h+var_48]
0x18003690e  mov     rcx, [rcx+0F0h]
0x180036915  mov     qword ptr [rbx+0F0h], 0
0x180036920  call    TestQueryData
0x180036925  test    eax, eax
0x180036927  jz      short loc_18003695E
0x180036929  mov     eax, dword ptr [rsp+68h+pv+4]
0x18003692d  or      [rbx+40h], eax
0x180036930  cmp     [rsp+68h+pv+8], 0
0x180036936  jz      short loc_180036947
0x180036938  lea     rdx, [rsp+68h+var_48]
0x18003693d  mov     rcx, rbx
0x180036940  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180036945  jmp     short loc_180036951
0x180036947  mov     eax, dword ptr [rsp+68h+pv]
0x18003694b  mov     [rbx+0B8h], eax
0x180036951  mov     rdx, qword ptr [rsp+68h+var_28]
0x180036956  mov     rcx, rbx
0x180036959  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x18003695e  mov     rcx, [rsp+68h+pv+8]; pv
0x180036963  call    cs:__imp_CoTaskMemFree
0x180036969  mov     rcx, [rsp+68h+var_18]
0x18003696e  xor     rcx, rsp; StackCookie
0x180036971  call    __security_check_cookie
0x180036976  add     rsp, 60h
0x18003697a  pop     rbx
0x18003697b  retn
```
