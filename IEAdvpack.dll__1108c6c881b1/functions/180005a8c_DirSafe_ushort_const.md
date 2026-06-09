# DirSafe(ushort const *)

- ea: `0x180005a8c`
- end: `0x180005d07`
- name: `?DirSafe@@YAJPEBG@Z`
- size: `635`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000b240`

## callees

- `0x1800022bc`
- `0x180002c74`
- `0x180005a8c`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x180005b1d`
- `KERNEL32!GetWindowsDirectoryW` at `0x180005b1d`
- `KERNEL32!CompareStringW` at `0x180005b6d`
- `KERNEL32!CompareStringW` at `0x180005ba1`
- `KERNEL32!CompareStringW` at `0x180005c03`
- `KERNEL32!CompareStringW` at `0x180005c64`
- `KERNEL32!CompareStringW` at `0x180005cc1`
- `KERNEL32!CompareStringW` at `0x180005b6d`
- `KERNEL32!CompareStringW` at `0x180005ba1`
- `KERNEL32!CompareStringW` at `0x180005c03`
- `KERNEL32!CompareStringW` at `0x180005c64`
- `KERNEL32!CompareStringW` at `0x180005cc1`
- `KERNEL32!GetShortPathNameW` at `0x180005c7c`
- `KERNEL32!GetShortPathNameW` at `0x180005c7c`
- `KERNEL32!GetSystemDirectoryW` at `0x180005bbe`
- `KERNEL32!GetSystemDirectoryW` at `0x180005bbe`

## pseudocode

```c
__int64 __fastcall DirSafe(const unsigned __int16 *a1)
{
  ULONG lpString2; // [rsp+20h] [rbp-E0h]
  ULONG lpString2d; // [rsp+20h] [rbp-E0h]
  ULONG lpString2a; // [rsp+20h] [rbp-E0h]
  ULONG lpString2b; // [rsp+20h] [rbp-E0h]
  ULONG lpString2c; // [rsp+20h] [rbp-E0h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+240h] [rbp+140h] BYREF

  if ( StringCchCopyW(pszPathOut, 0x104u, a1) < 0 )
    return 2147500037LL;
  PathIsUnc2((unsigned __int16 *)&word_18001DE6C);
  PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, &word_18001DE6C, lpString2);
  Buffer[0] = 0;
  GetWindowsDirectoryW(Buffer, 0x104u);
  PathIsUnc2((unsigned __int16 *)&word_18001DE6C);
  PathCchCombineEx(Buffer, 0x104u, Buffer, &word_18001DE6C, lpString2d);
  if ( CompareStringW(0x7Fu, 1u, pszPathOut, -1, Buffer, -1) == 2 )
    return 2147500037LL;
  Buffer[3] = 0;
  if ( CompareStringW(0x7Fu, 1u, pszPathOut, -1, Buffer, -1) == 2 )
    return 2147500037LL;
  Buffer[0] = 0;
  GetSystemDirectoryW(Buffer, 0x104u);
  PathIsUnc2((unsigned __int16 *)&word_18001DE6C);
  PathCchCombineEx(Buffer, 0x104u, Buffer, &word_18001DE6C, lpString2a);
  if ( CompareStringW(0x7Fu, 1u, pszPathOut, -1, Buffer, -1) == 2 )
    return 2147500037LL;
  Buffer[0] = 0;
  GetProgramFilesDir(Buffer, 0x104u);
  PathIsUnc2((unsigned __int16 *)&word_18001DE6C);
  PathCchCombineEx(Buffer, 0x104u, Buffer, &word_18001DE6C, lpString2b);
  if ( CompareStringW(0x7Fu, 1u, pszPathOut, -1, Buffer, -1) == 2 )
    return 2147500037LL;
  GetShortPathNameW(Buffer, Buffer, 0x104u);
  PathIsUnc2((unsigned __int16 *)&word_18001DE6C);
  PathCchCombineEx(Buffer, 0x104u, Buffer, &word_18001DE6C, lpString2c);
  return CompareStringW(0x7Fu, 1u, pszPathOut, -1, Buffer, -1) == 2 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180005a8c  mov     [rsp-8+arg_8], rbx
0x180005a91  mov     [rsp-8+arg_10], rsi
0x180005a96  push    rbp
0x180005a97  push    rdi
0x180005a98  push    r12
0x180005a9a  push    r14
0x180005a9c  push    r15
0x180005a9e  lea     rbp, [rsp-360h]
0x180005aa6  sub     rsp, 460h
0x180005aad  mov     rax, cs:__security_cookie
0x180005ab4  xor     rax, rsp
0x180005ab7  mov     [rbp+380h+var_30], rax
0x180005abe  mov     r8, rcx; unsigned __int16 *
0x180005ac1  mov     ebx, 104h
0x180005ac6  mov     edx, ebx; unsigned __int64
0x180005ac8  lea     rcx, [rbp+380h+pszPathOut]; unsigned __int16 *
0x180005acf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005ad4  test    eax, eax
0x180005ad6  js      loc_180005CD7
0x180005adc  lea     r12, IsBackslash
0x180005ae3  xor     edx, edx
0x180005ae5  lea     rsi, word_18001DE6C
0x180005aec  mov     r8, r12
0x180005aef  mov     rcx, rsi; unsigned __int16 *
0x180005af2  call    PathIsUnc2
0x180005af7  mov     r9, rsi; pszMore
0x180005afa  lea     r8, [rbp+380h+pszPathOut]; pszPathIn
0x180005b01  mov     edx, ebx; cchPathOut
0x180005b03  lea     rcx, [rbp+380h+pszPathOut]; pszPathOut
0x180005b0a  call    PathCchCombineEx
0x180005b0f  xor     eax, eax
0x180005b11  lea     rcx, [rsp+480h+Buffer]; lpBuffer
0x180005b16  mov     edx, ebx; uSize
0x180005b18  mov     [rsp+480h+Buffer], ax
0x180005b1d  call    cs:__imp_GetWindowsDirectoryW
0x180005b23  mov     r8, r12
0x180005b26  xor     edx, edx
0x180005b28  mov     rcx, rsi; unsigned __int16 *
0x180005b2b  call    PathIsUnc2
0x180005b30  mov     r9, rsi; pszMore
0x180005b33  lea     r8, [rsp+480h+Buffer]; pszPathIn
0x180005b38  mov     edx, ebx; cchPathOut
0x180005b3a  lea     rcx, [rsp+480h+Buffer]; pszPathOut
0x180005b3f  call    PathCchCombineEx
0x180005b44  or      edi, 0FFFFFFFFh
0x180005b47  lea     rax, [rsp+480h+Buffer]
0x180005b4c  mov     [rsp+480h+cchCount2], edi; cchCount2
0x180005b50  lea     r8, [rbp+380h+pszPathOut]; lpString1
0x180005b57  mov     r9d, edi; cchCount1
0x180005b5a  mov     [rsp+480h+lpString2], rax; lpString2
0x180005b5f  lea     r14d, [rdi+2]
0x180005b63  lea     r15d, [r14+7Eh]
0x180005b67  mov     edx, r14d; dwCmpFlags
0x180005b6a  mov     ecx, r15d; Locale
0x180005b6d  call    cs:__imp_CompareStringW
0x180005b73  cmp     eax, 2
0x180005b76  jz      loc_180005CD7
0x180005b7c  xor     eax, eax
0x180005b7e  mov     [rsp+480h+cchCount2], edi; cchCount2
0x180005b82  mov     [rsp+480h+var_44A], ax
0x180005b87  lea     r8, [rbp+380h+pszPathOut]; lpString1
0x180005b8e  lea     rax, [rsp+480h+Buffer]
0x180005b93  mov     r9d, edi; cchCount1
0x180005b96  mov     edx, r14d; dwCmpFlags
0x180005b99  mov     [rsp+480h+lpString2], rax; dwFlags
0x180005b9e  mov     ecx, r15d; Locale
0x180005ba1  call    cs:__imp_CompareStringW
0x180005ba7  cmp     eax, 2
0x180005baa  jz      loc_180005CD7
0x180005bb0  xor     eax, eax
0x180005bb2  lea     rcx, [rsp+480h+Buffer]; lpBuffer
0x180005bb7  mov     edx, ebx; uSize
0x180005bb9  mov     [rsp+480h+Buffer], ax
0x180005bbe  call    cs:__imp_GetSystemDirectoryW
0x180005bc4  mov     r8, r12
0x180005bc7  xor     edx, edx
0x180005bc9  mov     rcx, rsi; unsigned __int16 *
0x180005bcc  call    PathIsUnc2
0x180005bd1  mov     r9, rsi; pszMore
0x180005bd4  lea     r8, [rsp+480h+Buffer]; pszPathIn
0x180005bd9  mov     edx, ebx; cchPathOut
0x180005bdb  lea     rcx, [rsp+480h+Buffer]; pszPathOut
0x180005be0  call    PathCchCombineEx
0x180005be5  lea     rax, [rsp+480h+Buffer]
0x180005bea  mov     [rsp+480h+cchCount2], edi; cchCount2
0x180005bee  mov     r9d, edi; cchCount1
0x180005bf1  mov     [rsp+480h+lpString2], rax; dwFlags
0x180005bf6  lea     r8, [rbp+380h+pszPathOut]; lpString1
0x180005bfd  mov     edx, r14d; dwCmpFlags
0x180005c00  mov     ecx, r15d; Locale
0x180005c03  call    cs:__imp_CompareStringW
0x180005c09  cmp     eax, 2
0x180005c0c  jz      loc_180005CD7
0x180005c12  xor     eax, eax
0x180005c14  lea     rcx, [rsp+480h+Buffer]; unsigned __int16 *
0x180005c19  mov     edx, ebx; unsigned int
0x180005c1b  mov     [rsp+480h+Buffer], ax
0x180005c20  call    ?GetProgramFilesDir@@YAHPEAGK@Z; GetProgramFilesDir(ushort *,ulong)
0x180005c25  mov     r8, r12
0x180005c28  xor     edx, edx
0x180005c2a  mov     rcx, rsi; unsigned __int16 *
0x180005c2d  call    PathIsUnc2
0x180005c32  mov     r9, rsi; pszMore
0x180005c35  lea     r8, [rsp+480h+Buffer]; pszPathIn
0x180005c3a  mov     edx, ebx; cchPathOut
0x180005c3c  lea     rcx, [rsp+480h+Buffer]; pszPathOut
0x180005c41  call    PathCchCombineEx
0x180005c46  lea     rax, [rsp+480h+Buffer]
0x180005c4b  mov     [rsp+480h+cchCount2], edi; cchCount2
0x180005c4f  mov     r9d, edi; cchCount1
0x180005c52  mov     [rsp+480h+lpString2], rax; dwFlags
0x180005c57  lea     r8, [rbp+380h+pszPathOut]; lpString1
0x180005c5e  mov     edx, r14d; dwCmpFlags
0x180005c61  mov     ecx, r15d; Locale
0x180005c64  call    cs:__imp_CompareStringW
0x180005c6a  cmp     eax, 2
0x180005c6d  jz      short loc_180005CD7
0x180005c6f  mov     r8d, ebx; cchBuffer
0x180005c72  lea     rdx, [rsp+480h+Buffer]; lpszShortPath
0x180005c77  lea     rcx, [rsp+480h+Buffer]; lpszLongPath
0x180005c7c  call    cs:__imp_GetShortPathNameW
0x180005c82  mov     r8, r12
0x180005c85  xor     edx, edx
0x180005c87  mov     rcx, rsi; unsigned __int16 *
0x180005c8a  call    PathIsUnc2
0x180005c8f  mov     r9, rsi; pszMore
0x180005c92  lea     r8, [rsp+480h+Buffer]; pszPathIn
0x180005c97  mov     edx, ebx; cchPathOut
0x180005c99  lea     rcx, [rsp+480h+Buffer]; pszPathOut
0x180005c9e  call    PathCchCombineEx
0x180005ca3  lea     rax, [rsp+480h+Buffer]
0x180005ca8  mov     [rsp+480h+cchCount2], edi; cchCount2
0x180005cac  mov     r9d, edi; cchCount1
0x180005caf  mov     [rsp+480h+lpString2], rax; lpString2
0x180005cb4  lea     r8, [rbp+380h+pszPathOut]; lpString1
0x180005cbb  mov     edx, r14d; dwCmpFlags
0x180005cbe  mov     ecx, r15d; Locale
0x180005cc1  call    cs:__imp_CompareStringW
0x180005cc7  sub     eax, 2
0x180005cca  neg     eax
0x180005ccc  sbb     eax, eax
0x180005cce  not     eax
0x180005cd0  and     eax, 80004005h
0x180005cd5  jmp     short loc_180005CDC
0x180005cd7  mov     eax, 80004005h
0x180005cdc  mov     rcx, [rbp+380h+var_30]
0x180005ce3  xor     rcx, rsp; StackCookie
0x180005ce6  call    __security_check_cookie
0x180005ceb  lea     r11, [rsp+480h+var_20]
0x180005cf3  mov     rbx, [r11+38h]
0x180005cf7  mov     rsi, [r11+40h]
0x180005cfb  mov     rsp, r11
0x180005cfe  pop     r15
0x180005d00  pop     r14
0x180005d02  pop     r12
0x180005d04  pop     rdi
0x180005d05  pop     rbp
0x180005d06  retn
```
