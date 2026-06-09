# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180034728`
- end: `0x1800347d8`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028410`
- `0x1800346fc`

## callees

- `0x180002520`
- `0x18001b7f0`
- `0x180034728`
- `0x180034b08`
- `0x1800351bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800347bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800347bf`

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
0x180034728  push    rbx
0x18003472a  sub     rsp, 60h
0x18003472e  mov     rax, cs:__security_cookie
0x180034735  xor     rax, rsp
0x180034738  mov     [rsp+68h+var_18], rax
0x18003473d  cmp     dword ptr [rcx+0E8h], 0
0x180034744  xorps   xmm0, xmm0
0x180034747  movups  [rsp+68h+var_48], xmm0
0x18003474c  mov     rbx, rcx
0x18003474f  movups  xmmword ptr [rsp+68h+pv], xmm0
0x180034754  movups  [rsp+68h+var_28], xmm0
0x180034759  jbe     short loc_18003475E
0x18003475b  or      edx, 8
0x18003475e  mov     r8d, [rcx+0B8h]
0x180034765  lea     r9, [rsp+68h+var_48]
0x18003476a  mov     rcx, [rcx+0F0h]
0x180034771  mov     qword ptr [rbx+0F0h], 0
0x18003477c  call    TestQueryData
0x180034781  test    eax, eax
0x180034783  jz      short loc_1800347BA
0x180034785  mov     eax, dword ptr [rsp+68h+pv+4]
0x180034789  or      [rbx+40h], eax
0x18003478c  cmp     [rsp+68h+pv+8], 0
0x180034792  jz      short loc_1800347A3
0x180034794  lea     rdx, [rsp+68h+var_48]
0x180034799  mov     rcx, rbx
0x18003479c  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1800347a1  jmp     short loc_1800347AD
0x1800347a3  mov     eax, dword ptr [rsp+68h+pv]
0x1800347a7  mov     [rbx+0B8h], eax
0x1800347ad  mov     rdx, qword ptr [rsp+68h+var_28]
0x1800347b2  mov     rcx, rbx
0x1800347b5  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x1800347ba  mov     rcx, [rsp+68h+pv+8]; pv
0x1800347bf  call    cs:__imp_CoTaskMemFree
0x1800347c5  mov     rcx, [rsp+68h+var_18]
0x1800347ca  xor     rcx, rsp; StackCookie
0x1800347cd  call    __security_check_cookie
0x1800347d2  add     rsp, 60h
0x1800347d6  pop     rbx
0x1800347d7  retn
```
