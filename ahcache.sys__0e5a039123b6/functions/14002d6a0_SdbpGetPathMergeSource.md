# SdbpGetPathMergeSource

- ea: `0x14002d6a0`
- end: `0x14002d784`
- name: `SdbpGetPathMergeSource`
- size: `228`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, installer_update, broker_com_uri`

## callees

- `0x1400079f0`
- `0x14002d6a0`
- `0x14003e364`
- `0x140040970`
- `0x140040a5c`

## string_xrefs

- `0x14002d72d`: `AslPathCombine failed [%x]`
- `0x14002d73e`: `SdbpGetPathMergeSource`

## pseudocode

```c
__int64 __fastcall SdbpGetPathMergeSource(_WORD *a1, unsigned __int64 a2, const wchar_t *a3)
{
  const wchar_t *v3; // r10
  int v7; // eax
  unsigned int v8; // ebx
  wchar_t pszSrc[24]; // [rsp+30h] [rbp-268h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-238h] BYREF

  v3 = a3;
  wcscpy(pszSrc, L"\\MergeSdbFsSource");
  if ( a2 < 0x15 )
    return 3221225507LL;
  *a1 = 0;
  pszDest[0] = 0;
  if ( !a3 )
    v3 = &::pszSrc;
  v7 = AslPathCombine(pszSrc, v3, pszDest, 0x104u);
  v8 = v7;
  if ( v7 >= 0 )
    return (unsigned int)SdbpGetPathAppPatch(a1, a2, pszDest);
  else
    AslLogCallPrintf(1, "SdbpGetPathMergeSource", 1136, "AslPathCombine failed [%x]", v7);
  return v8;
}

```

## disassembly

```asm
0x14002d6a0  push    rbx
0x14002d6a2  push    rsi
0x14002d6a3  push    rdi
0x14002d6a4  sub     rsp, 280h
0x14002d6ab  mov     rax, cs:__security_cookie
0x14002d6b2  xor     rax, rsp
0x14002d6b5  mov     [rsp+298h+var_28], rax
0x14002d6bd  mov     r10, r8
0x14002d6c0  mov     rsi, rdx
0x14002d6c3  mov     rdi, rcx
0x14002d6c6  movups  xmm0, xmmword ptr cs:aMergesdbfiless; "\\MergeSdbFilesSource"
0x14002d6cd  movups  xmm1, xmmword ptr cs:aMergesdbfiless+10h; "bFilesSource"
0x14002d6d4  movups  xmmword ptr [rsp+298h+pszSrc], xmm0
0x14002d6d9  movups  xmm0, xmmword ptr cs:aMergesdbfiless+1Ah; "sSource"
0x14002d6e0  movups  [rsp+298h+var_258], xmm1
0x14002d6e5  movups  [rsp+298h+var_258+0Ah], xmm0
0x14002d6ea  cmp     rdx, 15h
0x14002d6ee  jnb     short loc_14002D6F7
0x14002d6f0  mov     eax, 0C0000023h
0x14002d6f5  jmp     short loc_14002D768
0x14002d6f7  xor     eax, eax
0x14002d6f9  lea     r8, [rsp+298h+pszDest]; pszDest
0x14002d6fe  mov     [rcx], ax
0x14002d701  test    r10, r10
0x14002d704  mov     [rsp+298h+pszDest], ax
0x14002d709  lea     rcx, [rsp+298h+pszSrc]; pszSrc
0x14002d70e  lea     rax, pszSrc
0x14002d715  mov     r9d, 104h; cchDest
0x14002d71b  cmovz   r10, rax
0x14002d71f  mov     rdx, r10; NTSTRSAFE_PCWSTR
0x14002d722  call    AslPathCombine
0x14002d727  mov     ebx, eax
0x14002d729  test    eax, eax
0x14002d72b  jns     short loc_14002D751
0x14002d72d  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x14002d734  mov     [rsp+298h+var_278], eax
0x14002d738  mov     r8d, 470h
0x14002d73e  lea     rdx, aSdbpgetpathmer; "SdbpGetPathMergeSource"
0x14002d745  mov     ecx, 1
0x14002d74a  call    AslLogCallPrintf
0x14002d74f  jmp     short loc_14002D766
0x14002d751  xor     r9d, r9d
0x14002d754  lea     r8, [rsp+298h+pszDest]
0x14002d759  mov     rdx, rsi
0x14002d75c  mov     rcx, rdi
0x14002d75f  call    SdbpGetPathAppPatch
0x14002d764  mov     ebx, eax
0x14002d766  mov     eax, ebx
0x14002d768  mov     rcx, [rsp+298h+var_28]
0x14002d770  xor     rcx, rsp; StackCookie
0x14002d773  call    __security_check_cookie
0x14002d778  add     rsp, 280h
0x14002d77f  pop     rdi
0x14002d780  pop     rsi
0x14002d781  pop     rbx
0x14002d782  retn
```
