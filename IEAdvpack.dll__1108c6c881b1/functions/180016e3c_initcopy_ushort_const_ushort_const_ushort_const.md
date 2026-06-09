# initcopy(ushort const *,ushort const *,ushort const *)

- ea: `0x180016e3c`
- end: `0x18001700d`
- name: `?initcopy@@YAXPEBG00@Z`
- size: `465`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016268`

## callees

- `0x1800022bc`
- `0x180003180`
- `0x180016e3c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180016eeb`
- `KERNEL32!LocalFree` at `0x180016fb6`
- `KERNEL32!LocalFree` at `0x180016eeb`
- `KERNEL32!LocalFree` at `0x180016fb6`
- `KERNEL32!LocalAlloc` at `0x180016e74`
- `KERNEL32!LocalAlloc` at `0x180016e74`
- `KERNEL32!CompareStringW` at `0x180016f18`
- `KERNEL32!CompareStringW` at `0x180016fd9`
- `KERNEL32!CompareStringW` at `0x180016f18`
- `KERNEL32!CompareStringW` at `0x180016fd9`
- `KERNEL32!GetShortPathNameW` at `0x180016f48`
- `KERNEL32!GetShortPathNameW` at `0x180016f86`
- `KERNEL32!GetShortPathNameW` at `0x180016f48`
- `KERNEL32!GetShortPathNameW` at `0x180016f86`
- `KERNEL32!GetPrivateProfileSectionW` at `0x180016e9e`
- `KERNEL32!GetPrivateProfileSectionW` at `0x180016e9e`
- `KERNEL32!MoveFileExW` at `0x180016ff8`
- `KERNEL32!MoveFileExW` at `0x180016ff8`
- `KERNEL32!WritePrivateProfileSectionW` at `0x180016fad`
- `KERNEL32!WritePrivateProfileSectionW` at `0x180016fad`

## string_xrefs

- `0x180016e97`: `Rename`
- `0x180016fa6`: `Rename`

## pseudocode

```c
void __fastcall initcopy(const unsigned __int16 *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v3; // rbx
  WCHAR *v6; // rax
  WCHAR *v7; // r14
  DWORD PrivateProfileSectionW; // eax
  __int64 v9; // rbp
  __int64 v10; // rcx
  __int64 v11; // rax
  WCHAR *v12; // rdi
  __int64 v13; // rax
  const WCHAR *v14; // rdx
  DWORD v15; // r8d

  v3 = -1;
  if ( ctx )
  {
    if ( CompareStringW(0x7Fu, 1u, a3, -1, L"NUL", -1) == 2 )
    {
      v14 = 0;
      v15 = 4;
    }
    else
    {
      v15 = 5;
      v14 = a3;
    }
    MoveFileExW(a2, v14, v15);
  }
  else
  {
    while ( 1 )
    {
      v6 = (WCHAR *)LocalAlloc(0x40u, 2LL * nSize);
      v7 = v6;
      if ( !v6 )
        break;
      PrivateProfileSectionW = GetPrivateProfileSectionW(L"Rename", v6, nSize, L"wininit.ini");
      v9 = PrivateProfileSectionW;
      if ( PrivateProfileSectionW < nSize - 2 )
      {
        v10 = -1;
        do
          ++v10;
        while ( a3[v10] );
        v11 = -1;
        do
          ++v11;
        while ( a2[v11] );
        if ( v9 + v11 + v10 + 16 <= (unsigned __int64)nSize )
        {
          v12 = &v7[v9];
          if ( CompareStringW(0x7Fu, 1u, a3, -1, L"NUL", -1) == 2 )
            StringCchCopyW(&v7[v9], nSize - (unsigned int)v9, a3);
          else
            GetShortPathNameW(a3, &v7[v9], nSize - v9);
          StringCchCatW(&v7[v9], nSize - (unsigned int)v9, L"=");
          v13 = -1;
          do
            ++v13;
          while ( v12[v13] );
          GetShortPathNameW(a2, &v12[v13], nSize - v13 - v9);
          do
            ++v3;
          while ( v12[v3] );
          v12[v3 + 1] = 0;
          WritePrivateProfileSectionW(L"Rename", v7, L"wininit.ini");
          LocalFree(v7);
          return;
        }
      }
      nSize += 1024;
      LocalFree(v7);
    }
  }
}

```

## disassembly

```asm
0x180016e3c  push    rbx
0x180016e3e  push    rbp
0x180016e3f  push    rsi
0x180016e40  push    rdi
0x180016e41  push    r12
0x180016e43  push    r14
0x180016e45  push    r15
0x180016e47  sub     rsp, 30h
0x180016e4b  xor     r12d, r12d
0x180016e4e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016e52  cmp     cs:?ctx@@3UADVCONTEXTW@@A, r12w; ADVCONTEXTW ctx
0x180016e5a  mov     rsi, r8
0x180016e5d  mov     r15, rdx
0x180016e60  jnz     loc_180016FBE
0x180016e66  mov     edx, cs:nSize
0x180016e6c  mov     ecx, 40h ; '@'; uFlags
0x180016e71  add     rdx, rdx; uBytes
0x180016e74  call    cs:__imp_LocalAlloc
0x180016e7a  mov     r14, rax
0x180016e7d  test    rax, rax
0x180016e80  jz      loc_180016FFE
0x180016e86  mov     r8d, cs:nSize; nSize
0x180016e8d  lea     r9, pszMore; "wininit.ini"
0x180016e94  mov     rdx, rax; lpReturnedString
0x180016e97  lea     rcx, aRename; "Rename"
0x180016e9e  call    cs:__imp_GetPrivateProfileSectionW
0x180016ea4  mov     edx, cs:nSize
0x180016eaa  mov     ebp, eax
0x180016eac  lea     ecx, [rdx-2]
0x180016eaf  cmp     eax, ecx
0x180016eb1  jnb     short loc_180016EDC
0x180016eb3  mov     rcx, rbx
0x180016eb6  inc     rcx
0x180016eb9  cmp     [rsi+rcx*2], r12w
0x180016ebe  jnz     short loc_180016EB6
0x180016ec0  mov     rax, rbx
0x180016ec3  inc     rax
0x180016ec6  cmp     [r15+rax*2], r12w
0x180016ecb  jnz     short loc_180016EC3
0x180016ecd  add     rax, rbp
0x180016ed0  add     rcx, 10h
0x180016ed4  add     rcx, rax
0x180016ed7  cmp     rcx, rdx
0x180016eda  jbe     short loc_180016EF6
0x180016edc  add     edx, 400h
0x180016ee2  mov     rcx, r14; hMem
0x180016ee5  mov     cs:nSize, edx
0x180016eeb  call    cs:__imp_LocalFree
0x180016ef1  jmp     loc_180016E66
0x180016ef6  mov     edx, 1; dwCmpFlags
0x180016efb  mov     [rsp+68h+cchCount2], ebx; cchCount2
0x180016eff  lea     rax, aNul; "NUL"
0x180016f06  mov     r9d, ebx; cchCount1
0x180016f09  mov     r8, rsi; lpString1
0x180016f0c  mov     [rsp+68h+lpString2], rax; lpString2
0x180016f11  lea     rdi, [r14+rbp*2]
0x180016f15  lea     ecx, [rdx+7Eh]; Locale
0x180016f18  call    cs:__imp_CompareStringW
0x180016f1e  cmp     eax, 2
0x180016f21  jnz     short loc_180016F38
0x180016f23  mov     edx, cs:nSize
0x180016f29  mov     r8, rsi; unsigned __int16 *
0x180016f2c  sub     edx, ebp; unsigned __int64
0x180016f2e  mov     rcx, rdi; unsigned __int16 *
0x180016f31  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016f36  jmp     short loc_180016F4E
0x180016f38  mov     r8d, cs:nSize
0x180016f3f  mov     rdx, rdi; lpszShortPath
0x180016f42  sub     r8d, ebp; cchBuffer
0x180016f45  mov     rcx, rsi; lpszLongPath
0x180016f48  call    cs:__imp_GetShortPathNameW
0x180016f4e  mov     edx, cs:nSize
0x180016f54  lea     r8, asc_18001E830; "="
0x180016f5b  sub     edx, ebp; unsigned __int64
0x180016f5d  mov     rcx, rdi; unsigned __int16 *
0x180016f60  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016f65  mov     rax, rbx
0x180016f68  inc     rax
0x180016f6b  cmp     [rdi+rax*2], r12w
0x180016f70  jnz     short loc_180016F68
0x180016f72  mov     r8d, cs:nSize
0x180016f79  lea     rdx, [rdi+rax*2]; lpszShortPath
0x180016f7d  sub     r8d, eax
0x180016f80  mov     rcx, r15; lpszLongPath
0x180016f83  sub     r8d, ebp; cchBuffer
0x180016f86  call    cs:__imp_GetShortPathNameW
0x180016f8c  inc     rbx
0x180016f8f  cmp     [rdi+rbx*2], r12w
0x180016f94  jnz     short loc_180016F8C
0x180016f96  lea     r8, pszMore; "wininit.ini"
0x180016f9d  mov     [rdi+rbx*2+2], r12w
0x180016fa3  mov     rdx, r14; lpString
0x180016fa6  lea     rcx, aRename; "Rename"
0x180016fad  call    cs:__imp_WritePrivateProfileSectionW
0x180016fb3  mov     rcx, r14; hMem
0x180016fb6  call    cs:__imp_LocalFree
0x180016fbc  jmp     short loc_180016FFE
0x180016fbe  mov     edx, 1; dwCmpFlags
0x180016fc3  mov     [rsp+68h+cchCount2], ebx; cchCount2
0x180016fc7  lea     rax, aNul; "NUL"
0x180016fce  mov     r9d, ebx; cchCount1
0x180016fd1  mov     [rsp+68h+lpString2], rax; lpString2
0x180016fd6  lea     ecx, [rdx+7Eh]; Locale
0x180016fd9  call    cs:__imp_CompareStringW
0x180016fdf  mov     rcx, r15; lpExistingFileName
0x180016fe2  cmp     eax, 2
0x180016fe5  jnz     short loc_180016FEF
0x180016fe7  xor     edx, edx
0x180016fe9  lea     r8d, [rax+2]
0x180016fed  jmp     short loc_180016FF8
0x180016fef  mov     r8d, 5; dwFlags
0x180016ff5  mov     rdx, rsi; lpNewFileName
0x180016ff8  call    cs:__imp_MoveFileExW
0x180016ffe  add     rsp, 30h
0x180017002  pop     r15
0x180017004  pop     r14
0x180017006  pop     r12
0x180017008  pop     rdi
0x180017009  pop     rsi
0x18001700a  pop     rbp
0x18001700b  pop     rbx
0x18001700c  retn
```
