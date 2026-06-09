# RecursiveScanDirectory(ushort const *,int,long (*const)(DIRECTORY_SCAN_STATE,ushort const *,_WIN32_FIND_DATAW *,void *),void *)

- ea: `0x18000d260`
- end: `0x18000d452`
- name: `?RecursiveScanDirectory@@YAJPEBGHQ6AJW4DIRECTORY_SCAN_STATE@@0PEAU_WIN32_FIND_DATAW@@PEAX@Z3@Z`
- size: `498`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, int (__high *const)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *), void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009220`
- `0x18000d260`

## callees

- `0x18000d240`
- `0x18000d260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3c7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000d2ff`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000d2ff`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000d3ae`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000d3ae`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000d3e1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000d40e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000d3e1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000d40e`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18000d2e8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18000d356`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18000d2e8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18000d356`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18000d2c3`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18000d2c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d29f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d29f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d336`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d422`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d42c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d435`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d336`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d422`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d42c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d435`

## pseudocode

```c
__int64 __fastcall RecursiveScanDirectory(
        const unsigned __int16 *a1,
        int a2,
        int (__high *const a3)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *),
        void *a4)
{
  struct _WIN32_FIND_DATAW *v7; // rdi
  int v8; // ebx
  HANDLE FirstFileW; // rsi
  __int64 v10; // rcx
  int v11; // eax
  signed int LastError; // eax
  PWSTR ppszPathOut; // [rsp+60h] [rbp+40h] BYREF
  PCWSTR pszPathIn; // [rsp+70h] [rbp+50h] BYREF

  pszPathIn = 0;
  ppszPathOut = 0;
  if ( !a1 )
  {
    v7 = 0;
    v8 = -2147024809;
    goto LABEL_29;
  }
  v7 = (struct _WIN32_FIND_DATAW *)LocalAlloc(0, 0x250u);
  if ( !v7 )
  {
    v8 = -2147024882;
    goto LABEL_29;
  }
  v8 = PathAllocCanonicalize(a1, 1u, &ppszPathOut);
  if ( v8 >= 0 )
  {
    v8 = PathAllocCombine(ppszPathOut, L"*", 1u, (PWSTR *)&pszPathIn);
    if ( v8 >= 0 )
    {
      FirstFileW = FindFirstFileW(pszPathIn, v7);
      if ( FirstFileW == (HANDLE)-1LL )
      {
LABEL_24:
        if ( a2 )
          v8 = FileSize(1, a1, v7, a4);
        goto LABEL_29;
      }
      while ( v7->cFileName[0] == 46 && (!v7->cFileName[1] || v7->cFileName[1] == 46 && !v7->cFileName[2]) )
      {
LABEL_19:
        if ( !FindNextFileW(FirstFileW, v7) )
        {
          if ( GetLastError() == 18 )
          {
            FindClose(FirstFileW);
            goto LABEL_24;
          }
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_27:
          FindClose(FirstFileW);
          goto LABEL_29;
        }
      }
      LocalFree((HLOCAL)pszPathIn);
      pszPathIn = 0;
      v8 = PathAllocCombine(ppszPathOut, v7->cFileName, 1u, (PWSTR *)&pszPathIn);
      if ( v8 < 0 )
        goto LABEL_27;
      if ( (v7->dwFileAttributes & 0x10) != 0 )
      {
        if ( (v7->dwFileAttributes & 0x400) == 0 )
        {
          v11 = RecursiveScanDirectory(
                  pszPathIn,
                  1,
                  (int (__high *const)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *))FileSize,
                  a4);
          goto LABEL_18;
        }
        v10 = 1;
      }
      else
      {
        v10 = 0;
      }
      v11 = FileSize(v10, pszPathIn, v7, a4);
LABEL_18:
      v8 = v11;
      if ( v11 < 0 )
        goto LABEL_27;
      goto LABEL_19;
    }
  }
LABEL_29:
  LocalFree(ppszPathOut);
  LocalFree((HLOCAL)pszPathIn);
  LocalFree(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d260  mov     [rsp-38h+arg_8], rbx
0x18000d265  mov     [rsp-38h+pszPathIn], r8
0x18000d26a  push    rbp
0x18000d26b  push    rsi
0x18000d26c  push    rdi
0x18000d26d  push    r12
0x18000d26f  push    r13
0x18000d271  push    r14
0x18000d273  push    r15
0x18000d275  mov     rbp, rsp
0x18000d278  sub     rsp, 20h
0x18000d27c  xor     esi, esi
0x18000d27e  mov     r15, r9
0x18000d281  mov     [rbp+pszPathIn], rsi
0x18000d285  mov     r13d, edx
0x18000d288  mov     [rbp+ppszPathOut], rsi
0x18000d28c  mov     r14, rcx
0x18000d28f  test    rcx, rcx
0x18000d292  jz      loc_18000D416
0x18000d298  mov     edx, 250h; uBytes
0x18000d29d  xor     ecx, ecx; uFlags
0x18000d29f  call    cs:__imp_LocalAlloc
0x18000d2a5  mov     rdi, rax
0x18000d2a8  test    rax, rax
0x18000d2ab  jnz     short loc_18000D2B7
0x18000d2ad  mov     ebx, 8007000Eh
0x18000d2b2  jmp     loc_18000D41E
0x18000d2b7  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x18000d2bb  mov     edx, 1; dwFlags
0x18000d2c0  mov     rcx, r14; pszPathIn
0x18000d2c3  call    cs:__imp_PathAllocCanonicalize
0x18000d2c9  mov     ebx, eax
0x18000d2cb  test    eax, eax
0x18000d2cd  js      loc_18000D41E
0x18000d2d3  mov     rcx, [rbp+ppszPathOut]; pszPathIn
0x18000d2d7  lea     r9, [rbp+pszPathIn]; ppszPathOut
0x18000d2db  mov     r8d, 1; dwFlags
0x18000d2e1  lea     rdx, asc_180013070; "*"
0x18000d2e8  call    cs:__imp_PathAllocCombine
0x18000d2ee  mov     ebx, eax
0x18000d2f0  test    eax, eax
0x18000d2f2  js      loc_18000D41E
0x18000d2f8  mov     rcx, [rbp+pszPathIn]; lpFileName
0x18000d2fc  mov     rdx, rdi; lpFindFileData
0x18000d2ff  call    cs:__imp_FindFirstFileW
0x18000d305  mov     rsi, rax
0x18000d308  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d30c  jz      loc_18000D3EB
0x18000d312  cmp     word ptr [rdi+2Ch], 2Eh ; '.'
0x18000d317  jnz     short loc_18000D332
0x18000d319  xor     eax, eax
0x18000d31b  cmp     [rdi+2Eh], ax
0x18000d31f  jz      loc_18000D3A8
0x18000d325  cmp     word ptr [rdi+2Eh], 2Eh ; '.'
0x18000d32a  jnz     short loc_18000D332
0x18000d32c  cmp     [rdi+30h], ax
0x18000d330  jz      short loc_18000D3A8
0x18000d332  mov     rcx, [rbp+pszPathIn]; hMem
0x18000d336  call    cs:__imp_LocalFree
0x18000d33c  mov     rcx, [rbp+ppszPathOut]; pszPathIn
0x18000d340  lea     r9, [rbp+pszPathIn]; ppszPathOut
0x18000d344  mov     r8d, 1; dwFlags
0x18000d34a  mov     [rbp+pszPathIn], 0
0x18000d352  lea     rdx, [rdi+2Ch]; pszMore
0x18000d356  call    cs:__imp_PathAllocCombine
0x18000d35c  mov     ebx, eax
0x18000d35e  test    eax, eax
0x18000d360  js      loc_18000D40B
0x18000d366  test    byte ptr [rdi], 10h
0x18000d369  mov     r9, r15; void *
0x18000d36c  jz      short loc_18000D394
0x18000d36e  test    dword ptr [rdi], 400h
0x18000d374  jz      short loc_18000D37D
0x18000d376  mov     ecx, 1
0x18000d37b  jmp     short loc_18000D396
0x18000d37d  mov     rcx, [rbp+pszPathIn]; unsigned __int16 *
0x18000d381  lea     r8, FileSize; int (__high *)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *)
0x18000d388  mov     edx, 1; int
0x18000d38d  call    ?RecursiveScanDirectory@@YAJPEBGHQ6AJW4DIRECTORY_SCAN_STATE@@0PEAU_WIN32_FIND_DATAW@@PEAX@Z3@Z; RecursiveScanDirectory(ushort const *,int,long (*const)(DIRECTORY_SCAN_STATE,ushort const *,_WIN32_FIND_DATAW *,void *),void *)
0x18000d392  jmp     short loc_18000D3A2
0x18000d394  xor     ecx, ecx
0x18000d396  mov     rdx, [rbp+pszPathIn]
0x18000d39a  mov     r8, rdi
0x18000d39d  call    FileSize
0x18000d3a2  mov     ebx, eax
0x18000d3a4  test    eax, eax
0x18000d3a6  js      short loc_18000D40B
0x18000d3a8  mov     rdx, rdi; lpFindFileData
0x18000d3ab  mov     rcx, rsi; hFindFile
0x18000d3ae  call    cs:__imp_FindNextFileW
0x18000d3b4  test    eax, eax
0x18000d3b6  jnz     loc_18000D312
0x18000d3bc  call    cs:__imp_GetLastError
0x18000d3c2  cmp     eax, 12h
0x18000d3c5  jz      short loc_18000D3DE
0x18000d3c7  call    cs:__imp_GetLastError
0x18000d3cd  mov     ebx, eax
0x18000d3cf  test    eax, eax
0x18000d3d1  jle     short loc_18000D40B
0x18000d3d3  movzx   ebx, ax
0x18000d3d6  or      ebx, 80070000h
0x18000d3dc  jmp     short loc_18000D40B
0x18000d3de  mov     rcx, rsi; hFindFile
0x18000d3e1  call    cs:__imp_FindClose
0x18000d3e7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000d3eb  test    r13d, r13d
0x18000d3ee  jz      short loc_18000D405
0x18000d3f0  mov     r9, r15
0x18000d3f3  mov     r8, rdi
0x18000d3f6  mov     rdx, r14
0x18000d3f9  mov     ecx, 1
0x18000d3fe  call    FileSize
0x18000d403  mov     ebx, eax
0x18000d405  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000d409  jz      short loc_18000D41E
0x18000d40b  mov     rcx, rsi; hFindFile
0x18000d40e  call    cs:__imp_FindClose
0x18000d414  jmp     short loc_18000D41E
0x18000d416  mov     rdi, rsi
0x18000d419  mov     ebx, 80070057h
0x18000d41e  mov     rcx, [rbp+ppszPathOut]; hMem
0x18000d422  call    cs:__imp_LocalFree
0x18000d428  mov     rcx, [rbp+pszPathIn]; hMem
0x18000d42c  call    cs:__imp_LocalFree
0x18000d432  mov     rcx, rdi; hMem
0x18000d435  call    cs:__imp_LocalFree
0x18000d43b  mov     eax, ebx
0x18000d43d  mov     rbx, [rsp+20h+arg_8]
0x18000d442  add     rsp, 20h
0x18000d446  pop     r15
0x18000d448  pop     r14
0x18000d44a  pop     r13
0x18000d44c  pop     r12
0x18000d44e  pop     rdi
0x18000d44f  pop     rsi
0x18000d450  pop     rbp
0x18000d451  retn
```
