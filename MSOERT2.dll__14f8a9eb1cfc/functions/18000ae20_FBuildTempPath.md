# FBuildTempPath

- ea: `0x18000ae20`
- end: `0x18000aeed`
- name: `FBuildTempPath`
- size: `205`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, LPSTR, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001150`
- `0x18000ae20`
- `0x18000af00`
- `0x180011930`
- `0x180014010`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18000aeab`
- `KERNEL32!WideCharToMultiByte` at `0x18000aeab`

## pseudocode

```c
WCHAR *__fastcall FBuildTempPath(LPCCH lpMultiByteStr, LPSTR a2, unsigned int a3, int a4)
{
  WCHAR *result; // rax
  unsigned __int16 *v8; // rbp
  unsigned int v9; // esi
  LPCWCH lpWideCharStr; // [rsp+40h] [rbp-38h] BYREF

  result = PszToUnicode(0, lpMultiByteStr);
  lpWideCharStr = 0;
  v8 = result;
  if ( result )
  {
    v9 = 0;
    MemAlloc((void **)&lpWideCharStr, 2 * a3);
    if ( lpWideCharStr )
    {
      v9 = FBuildTempPathW(v8, (unsigned __int16 *)lpWideCharStr, a3, a4);
      if ( v9 )
        WideCharToMultiByte(0, 0, lpWideCharStr, -1, a2, a3, 0, 0);
    }
    ((void (__fastcall *)(LPMALLOC, unsigned __int16 *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v8);
    ((void (__fastcall *)(LPMALLOC, LPCWCH))g_pMalloc->lpVtbl->Free)(g_pMalloc, lpWideCharStr);
    return (WCHAR *)v9;
  }
  return result;
}

```

## disassembly

```asm
0x18000ae20  push    rbp
0x18000ae22  push    rsi
0x18000ae23  push    rdi
0x18000ae24  push    r14
0x18000ae26  push    r15
0x18000ae28  sub     rsp, 50h
0x18000ae2c  mov     r14, rdx
0x18000ae2f  mov     r15d, r9d
0x18000ae32  mov     rdx, rcx; lpMultiByteStr
0x18000ae35  mov     edi, r8d
0x18000ae38  xor     ecx, ecx; CodePage
0x18000ae3a  call    PszToUnicode
0x18000ae3f  mov     [rsp+78h+lpWideCharStr], 0
0x18000ae48  mov     rbp, rax
0x18000ae4b  test    rax, rax
0x18000ae4e  jz      loc_18000AEE1
0x18000ae54  lea     edx, [rdi+rdi]; unsigned int
0x18000ae57  xor     esi, esi
0x18000ae59  lea     rcx, [rsp+78h+lpWideCharStr]; void **
0x18000ae5e  call    ?MemAlloc@@YAHPEAPEAXK@Z; MemAlloc(void * *,ulong)
0x18000ae63  cmp     [rsp+78h+lpWideCharStr], rsi
0x18000ae68  jz      short loc_18000AEB1
0x18000ae6a  mov     rdx, [rsp+78h+lpWideCharStr]; unsigned __int16 *
0x18000ae6f  mov     r9d, r15d
0x18000ae72  mov     r8d, edi; unsigned __int64
0x18000ae75  mov     rcx, rbp; unsigned __int16 *
0x18000ae78  call    FBuildTempPathW
0x18000ae7d  mov     esi, eax
0x18000ae7f  test    eax, eax
0x18000ae81  jz      short loc_18000AEB1
0x18000ae83  mov     r8, [rsp+78h+lpWideCharStr]; lpWideCharStr
0x18000ae88  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000ae8c  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000ae95  xor     edx, edx; dwFlags
0x18000ae97  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x18000aea0  xor     ecx, ecx; CodePage
0x18000aea2  mov     [rsp+78h+cbMultiByte], edi; cbMultiByte
0x18000aea6  mov     [rsp+78h+lpMultiByteStr], r14; lpMultiByteStr
0x18000aeab  call    cs:__imp_WideCharToMultiByte
0x18000aeb1  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000aeb8  mov     rdx, rbp
0x18000aebb  mov     rax, [rcx]
0x18000aebe  mov     rax, [rax+28h]
0x18000aec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec7  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000aece  mov     rdx, [rsp+78h+lpWideCharStr]
0x18000aed3  mov     rax, [rcx]
0x18000aed6  mov     rax, [rax+28h]
0x18000aeda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aedf  mov     eax, esi
0x18000aee1  add     rsp, 50h
0x18000aee5  pop     r15
0x18000aee7  pop     r14
0x18000aee9  pop     rdi
0x18000aeea  pop     rsi
0x18000aeeb  pop     rbp
0x18000aeec  retn
```
