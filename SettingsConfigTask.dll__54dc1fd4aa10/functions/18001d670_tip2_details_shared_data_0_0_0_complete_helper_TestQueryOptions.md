# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18001d670`
- end: `0x18001d711`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d718`
- `0x18001f674`

## callees

- `0x1800021d0`
- `0x18001d670`
- `0x18001e6f8`
- `0x1800219a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d6f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d6f8`

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
0x18001d670  push    rbx
0x18001d672  sub     rsp, 60h
0x18001d676  mov     rax, cs:__security_cookie
0x18001d67d  xor     rax, rsp
0x18001d680  mov     [rsp+68h+var_18], rax
0x18001d685  cmp     dword ptr [rcx+0E8h], 0
0x18001d68c  xorps   xmm0, xmm0
0x18001d68f  movups  [rsp+68h+var_48], xmm0
0x18001d694  mov     rbx, rcx
0x18001d697  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18001d69c  movups  [rsp+68h+var_28], xmm0
0x18001d6a1  jbe     short loc_18001D6A6
0x18001d6a3  or      edx, 8
0x18001d6a6  mov     r8d, [rcx+0B8h]
0x18001d6ad  lea     r9, [rsp+68h+var_48]
0x18001d6b2  mov     rcx, [rcx+0F0h]
0x18001d6b9  mov     qword ptr [rbx+0F0h], 0
0x18001d6c4  call    TestQueryData
0x18001d6c9  test    eax, eax
0x18001d6cb  jz      short loc_18001D6F3
0x18001d6cd  mov     eax, dword ptr [rsp+68h+pv+4]
0x18001d6d1  or      [rbx+40h], eax
0x18001d6d4  cmp     [rsp+68h+pv+8], 0
0x18001d6da  jnz     short loc_18001D6E6
0x18001d6dc  mov     eax, dword ptr [rsp+68h+pv]
0x18001d6e0  mov     [rbx+0B8h], eax
0x18001d6e6  mov     rdx, qword ptr [rsp+68h+var_28]
0x18001d6eb  mov     rcx, rbx
0x18001d6ee  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x18001d6f3  mov     rcx, [rsp+68h+pv+8]; pv
0x18001d6f8  call    cs:__imp_CoTaskMemFree
0x18001d6fe  mov     rcx, [rsp+68h+var_18]
0x18001d703  xor     rcx, rsp; StackCookie
0x18001d706  call    __security_check_cookie
0x18001d70b  add     rsp, 60h
0x18001d70f  pop     rbx
0x18001d710  retn
```
