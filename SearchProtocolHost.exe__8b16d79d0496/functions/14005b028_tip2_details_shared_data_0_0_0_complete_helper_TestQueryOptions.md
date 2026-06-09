# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x14005b028`
- end: `0x14005b0c9`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14005affc`
- `0x14005b6f8`

## callees

- `0x140005240`
- `0x140039f70`
- `0x14005b028`
- `0x14005b42c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005b0b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005b0b0`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::complete_helper(__int64 a1, __int64 a2)
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
    if ( !pv[1] )
      *(_DWORD *)(a1 + 184) = pv[0];
    tip2::details::shared_data<0,0,0>::evaluate_and_report(a1, v8);
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x14005b028  push    rbx
0x14005b02a  sub     rsp, 60h
0x14005b02e  mov     rax, cs:__security_cookie
0x14005b035  xor     rax, rsp
0x14005b038  mov     [rsp+68h+var_18], rax
0x14005b03d  cmp     dword ptr [rcx+0E8h], 0
0x14005b044  xorps   xmm0, xmm0
0x14005b047  movups  [rsp+68h+var_48], xmm0
0x14005b04c  mov     rbx, rcx
0x14005b04f  movups  xmmword ptr [rsp+68h+pv], xmm0
0x14005b054  movups  [rsp+68h+var_28], xmm0
0x14005b059  jbe     short loc_14005B05E
0x14005b05b  or      edx, 8
0x14005b05e  mov     r8d, [rcx+0B8h]
0x14005b065  lea     r9, [rsp+68h+var_48]
0x14005b06a  mov     rcx, [rcx+0F0h]
0x14005b071  mov     qword ptr [rbx+0F0h], 0
0x14005b07c  call    TestQueryData
0x14005b081  test    eax, eax
0x14005b083  jz      short loc_14005B0AB
0x14005b085  mov     eax, dword ptr [rsp+68h+pv+4]
0x14005b089  or      [rbx+40h], eax
0x14005b08c  cmp     [rsp+68h+pv+8], 0
0x14005b092  jnz     short loc_14005B09E
0x14005b094  mov     eax, dword ptr [rsp+68h+pv]
0x14005b098  mov     [rbx+0B8h], eax
0x14005b09e  mov     rdx, qword ptr [rsp+68h+var_28]
0x14005b0a3  mov     rcx, rbx
0x14005b0a6  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x14005b0ab  mov     rcx, [rsp+68h+pv+8]; pv
0x14005b0b0  call    cs:__imp_CoTaskMemFree
0x14005b0b6  mov     rcx, [rsp+68h+var_18]
0x14005b0bb  xor     rcx, rsp; StackCookie
0x14005b0be  call    __security_check_cookie
0x14005b0c3  add     rsp, 60h
0x14005b0c7  pop     rbx
0x14005b0c8  retn
```
