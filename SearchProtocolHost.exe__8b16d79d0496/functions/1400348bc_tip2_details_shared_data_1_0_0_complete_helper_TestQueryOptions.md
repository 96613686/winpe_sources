# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x1400348bc`
- end: `0x14003496c`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000efb8`
- `0x14002d100`

## callees

- `0x140005240`
- `0x1400348bc`
- `0x140034cb0`
- `0x140035494`
- `0x140039f70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140034953`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140034953`

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
0x1400348bc  push    rbx
0x1400348be  sub     rsp, 60h
0x1400348c2  mov     rax, cs:__security_cookie
0x1400348c9  xor     rax, rsp
0x1400348cc  mov     [rsp+68h+var_18], rax
0x1400348d1  cmp     dword ptr [rcx+0E8h], 0
0x1400348d8  xorps   xmm0, xmm0
0x1400348db  movups  [rsp+68h+var_48], xmm0
0x1400348e0  mov     rbx, rcx
0x1400348e3  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1400348e8  movups  [rsp+68h+var_28], xmm0
0x1400348ed  jbe     short loc_1400348F2
0x1400348ef  or      edx, 8
0x1400348f2  mov     r8d, [rcx+0B8h]
0x1400348f9  lea     r9, [rsp+68h+var_48]
0x1400348fe  mov     rcx, [rcx+0F0h]
0x140034905  mov     qword ptr [rbx+0F0h], 0
0x140034910  call    TestQueryData
0x140034915  test    eax, eax
0x140034917  jz      short loc_14003494E
0x140034919  mov     eax, dword ptr [rsp+68h+pv+4]
0x14003491d  or      [rbx+40h], eax
0x140034920  cmp     [rsp+68h+pv+8], 0
0x140034926  jz      short loc_140034937
0x140034928  lea     rdx, [rsp+68h+var_48]
0x14003492d  mov     rcx, rbx
0x140034930  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x140034935  jmp     short loc_140034941
0x140034937  mov     eax, dword ptr [rsp+68h+pv]
0x14003493b  mov     [rbx+0B8h], eax
0x140034941  mov     rdx, qword ptr [rsp+68h+var_28]
0x140034946  mov     rcx, rbx
0x140034949  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x14003494e  mov     rcx, [rsp+68h+pv+8]; pv
0x140034953  call    cs:__imp_CoTaskMemFree
0x140034959  mov     rcx, [rsp+68h+var_18]
0x14003495e  xor     rcx, rsp; StackCookie
0x140034961  call    __security_check_cookie
0x140034966  add     rsp, 60h
0x14003496a  pop     rbx
0x14003496b  retn
```
