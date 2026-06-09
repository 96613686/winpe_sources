# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18003c4cc`
- end: `0x18003c57c`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180036f38`
- `0x18003b320`

## callees

- `0x1800032b0`
- `0x18003c4cc`
- `0x18003c738`
- `0x18003cbf4`
- `0x18003fab0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c563`

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
0x18003c4cc  push    rbx
0x18003c4ce  sub     rsp, 60h
0x18003c4d2  mov     rax, cs:__security_cookie
0x18003c4d9  xor     rax, rsp
0x18003c4dc  mov     [rsp+68h+var_18], rax
0x18003c4e1  cmp     dword ptr [rcx+0E8h], 0
0x18003c4e8  xorps   xmm0, xmm0
0x18003c4eb  movups  [rsp+68h+var_48], xmm0
0x18003c4f0  mov     rbx, rcx
0x18003c4f3  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18003c4f8  movups  [rsp+68h+var_28], xmm0
0x18003c4fd  jbe     short loc_18003C502
0x18003c4ff  or      edx, 8
0x18003c502  mov     r8d, [rcx+0B8h]
0x18003c509  lea     r9, [rsp+68h+var_48]
0x18003c50e  mov     rcx, [rcx+0F0h]
0x18003c515  mov     qword ptr [rbx+0F0h], 0
0x18003c520  call    TestQueryData
0x18003c525  test    eax, eax
0x18003c527  jz      short loc_18003C55E
0x18003c529  mov     eax, dword ptr [rsp+68h+pv+4]
0x18003c52d  or      [rbx+40h], eax
0x18003c530  cmp     [rsp+68h+pv+8], 0
0x18003c536  jz      short loc_18003C547
0x18003c538  lea     rdx, [rsp+68h+var_48]
0x18003c53d  mov     rcx, rbx
0x18003c540  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18003c545  jmp     short loc_18003C551
0x18003c547  mov     eax, dword ptr [rsp+68h+pv]
0x18003c54b  mov     [rbx+0B8h], eax
0x18003c551  mov     rdx, qword ptr [rsp+68h+var_28]
0x18003c556  mov     rcx, rbx
0x18003c559  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x18003c55e  mov     rcx, [rsp+68h+pv+8]; pv
0x18003c563  call    cs:__imp_CoTaskMemFree
0x18003c569  mov     rcx, [rsp+68h+var_18]
0x18003c56e  xor     rcx, rsp; StackCookie
0x18003c571  call    __security_check_cookie
0x18003c576  add     rsp, 60h
0x18003c57a  pop     rbx
0x18003c57b  retn
```
