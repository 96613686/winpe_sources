# SdbpGetPathCustomSdb

- ea: `0x14002d5c0`
- end: `0x14002d69a`
- name: `SdbpGetPathCustomSdb`
- size: `218`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int64, const wchar_t *)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, installer_update, broker_com_uri`

## callees

- `0x1400079f0`
- `0x14002d5c0`
- `0x14003e364`
- `0x140040970`
- `0x140040a5c`

## string_xrefs

- `0x14002d643`: `AslPathCombine failed [%x]`
- `0x14002d654`: `SdbpGetPathCustomSdb`

## pseudocode

```c
__int64 __fastcall SdbpGetPathCustomSdb(_WORD *a1, unsigned __int64 a2, const wchar_t *a3)
{
  const wchar_t *v3; // r10
  int v7; // eax
  unsigned int v8; // ebx
  wchar_t pszSrc[16]; // [rsp+30h] [rbp-258h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-238h] BYREF

  v3 = a3;
  wcscpy(pszSrc, L"\\CustoSDB");
  if ( a2 < 0xB )
    return 3221225507LL;
  *a1 = 0;
  pszDest[0] = 0;
  if ( !a3 )
    v3 = &::pszSrc;
  v7 = AslPathCombine(pszSrc, v3, pszDest, 0x104u);
  v8 = v7;
  if ( v7 >= 0 )
    return (unsigned int)SdbpGetPathAppPatch(a1, a2, pszDest, 0);
  else
    AslLogCallPrintf(1, "SdbpGetPathCustomSdb", 1190, "AslPathCombine failed [%x]", v7);
  return v8;
}

```

## disassembly

```asm
0x14002d5c0  push    rbx
0x14002d5c2  push    rsi
0x14002d5c3  push    rdi
0x14002d5c4  sub     rsp, 270h
0x14002d5cb  mov     rax, cs:__security_cookie
0x14002d5d2  xor     rax, rsp
0x14002d5d5  mov     [rsp+288h+var_28], rax
0x14002d5dd  movsd   xmm1, qword ptr cs:aCustomsdb+0Eh; "SDB"
0x14002d5e5  mov     r10, r8
0x14002d5e8  mov     rsi, rdx
0x14002d5eb  mov     rdi, rcx
0x14002d5ee  movups  xmm0, xmmword ptr cs:aCustomsdb; "\\CustomSDB"
0x14002d5f5  movups  xmmword ptr [rsp+288h+pszSrc], xmm0
0x14002d5fa  movsd   qword ptr [rsp+288h+pszSrc+0Eh], xmm1
0x14002d600  cmp     rdx, 0Bh
0x14002d604  jnb     short loc_14002D60D
0x14002d606  mov     eax, 0C0000023h
0x14002d60b  jmp     short loc_14002D67E
0x14002d60d  xor     eax, eax
0x14002d60f  lea     r8, [rsp+288h+pszDest]; pszDest
0x14002d614  mov     [rcx], ax
0x14002d617  test    r10, r10
0x14002d61a  mov     [rsp+288h+pszDest], ax
0x14002d61f  lea     rcx, [rsp+288h+pszSrc]; pszSrc
0x14002d624  lea     rax, pszSrc
0x14002d62b  mov     r9d, 104h; cchDest
0x14002d631  cmovz   r10, rax
0x14002d635  mov     rdx, r10; NTSTRSAFE_PCWSTR
0x14002d638  call    AslPathCombine
0x14002d63d  mov     ebx, eax
0x14002d63f  test    eax, eax
0x14002d641  jns     short loc_14002D667
0x14002d643  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x14002d64a  mov     [rsp+288h+var_268], eax
0x14002d64e  mov     r8d, 4A6h
0x14002d654  lea     rdx, aSdbpgetpathcus; "SdbpGetPathCustomSdb"
0x14002d65b  mov     ecx, 1
0x14002d660  call    AslLogCallPrintf
0x14002d665  jmp     short loc_14002D67C
0x14002d667  xor     r9d, r9d
0x14002d66a  lea     r8, [rsp+288h+pszDest]
0x14002d66f  mov     rdx, rsi
0x14002d672  mov     rcx, rdi
0x14002d675  call    SdbpGetPathAppPatch
0x14002d67a  mov     ebx, eax
0x14002d67c  mov     eax, ebx
0x14002d67e  mov     rcx, [rsp+288h+var_28]
0x14002d686  xor     rcx, rsp; StackCookie
0x14002d689  call    __security_check_cookie
0x14002d68e  add     rsp, 270h
0x14002d695  pop     rdi
0x14002d696  pop     rsi
0x14002d697  pop     rbx
0x14002d698  retn
```
