# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18002252c`
- end: `0x1800225cd`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800225d4`
- `0x1800231a8`

## callees

- `0x18000c6e0`
- `0x1800134d4`
- `0x18002252c`
- `0x1800229a0`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x1800225b4`
- `OLE32!CoTaskMemFree` at `0x1800225b4`

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
    tip2::details::shared_data<1,0,0>::evaluate_and_report(a1, v8);
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x18002252c  push    rbx
0x18002252e  sub     rsp, 60h
0x180022532  mov     rax, cs:__security_cookie
0x180022539  xor     rax, rsp
0x18002253c  mov     [rsp+68h+var_18], rax
0x180022541  cmp     dword ptr [rcx+0E8h], 0
0x180022548  xorps   xmm0, xmm0
0x18002254b  movups  [rsp+68h+var_48], xmm0
0x180022550  mov     rbx, rcx
0x180022553  movups  xmmword ptr [rsp+68h+pv], xmm0
0x180022558  movups  [rsp+68h+var_28], xmm0
0x18002255d  jbe     short loc_180022562
0x18002255f  or      edx, 8
0x180022562  mov     r8d, [rcx+0B8h]
0x180022569  lea     r9, [rsp+68h+var_48]
0x18002256e  mov     rcx, [rcx+0F0h]
0x180022575  mov     qword ptr [rbx+0F0h], 0
0x180022580  call    TestQueryData
0x180022585  test    eax, eax
0x180022587  jz      short loc_1800225AF
0x180022589  mov     eax, dword ptr [rsp+68h+pv+4]
0x18002258d  or      [rbx+40h], eax
0x180022590  cmp     [rsp+68h+pv+8], 0
0x180022596  jnz     short loc_1800225A2
0x180022598  mov     eax, dword ptr [rsp+68h+pv]
0x18002259c  mov     [rbx+0B8h], eax
0x1800225a2  mov     rdx, qword ptr [rsp+68h+var_28]
0x1800225a7  mov     rcx, rbx
0x1800225aa  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x1800225af  mov     rcx, [rsp+68h+pv+8]; pv
0x1800225b4  call    cs:__imp_CoTaskMemFree
0x1800225ba  mov     rcx, [rsp+68h+var_18]
0x1800225bf  xor     rcx, rsp; StackCookie
0x1800225c2  call    __security_check_cookie
0x1800225c7  add     rsp, 60h
0x1800225cb  pop     rbx
0x1800225cc  retn
```
