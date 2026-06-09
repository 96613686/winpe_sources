# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x1400255ac`
- end: `0x14002565c`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001bc20`
- `0x140025580`

## callees

- `0x1400030a0`
- `0x1400185a0`
- `0x1400255ac`
- `0x1400256e8`
- `0x140025cd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025643`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025643`

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
0x1400255ac  push    rbx
0x1400255ae  sub     rsp, 60h
0x1400255b2  mov     rax, cs:__security_cookie
0x1400255b9  xor     rax, rsp
0x1400255bc  mov     [rsp+68h+var_18], rax
0x1400255c1  cmp     dword ptr [rcx+0E8h], 0
0x1400255c8  xorps   xmm0, xmm0
0x1400255cb  movups  [rsp+68h+var_48], xmm0
0x1400255d0  mov     rbx, rcx
0x1400255d3  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1400255d8  movups  [rsp+68h+var_28], xmm0
0x1400255dd  jbe     short loc_1400255E2
0x1400255df  or      edx, 8
0x1400255e2  mov     r8d, [rcx+0B8h]
0x1400255e9  lea     r9, [rsp+68h+var_48]
0x1400255ee  mov     rcx, [rcx+0F0h]
0x1400255f5  mov     qword ptr [rbx+0F0h], 0
0x140025600  call    TestQueryData
0x140025605  test    eax, eax
0x140025607  jz      short loc_14002563E
0x140025609  mov     eax, dword ptr [rsp+68h+pv+4]
0x14002560d  or      [rbx+40h], eax
0x140025610  cmp     [rsp+68h+pv+8], 0
0x140025616  jz      short loc_140025627
0x140025618  lea     rdx, [rsp+68h+var_48]
0x14002561d  mov     rcx, rbx
0x140025620  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x140025625  jmp     short loc_140025631
0x140025627  mov     eax, dword ptr [rsp+68h+pv]
0x14002562b  mov     [rbx+0B8h], eax
0x140025631  mov     rdx, qword ptr [rsp+68h+var_28]
0x140025636  mov     rcx, rbx
0x140025639  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x14002563e  mov     rcx, [rsp+68h+pv+8]; pv
0x140025643  call    cs:__imp_CoTaskMemFree
0x140025649  mov     rcx, [rsp+68h+var_18]
0x14002564e  xor     rcx, rsp; StackCookie
0x140025651  call    __security_check_cookie
0x140025656  add     rsp, 60h
0x14002565a  pop     rbx
0x14002565b  retn
```
