# RecursiveScanDirectory(ushort const *,int,long (*const)(DIRECTORY_SCAN_STATE,ushort const *,_WIN32_FIND_DATAW *,void *),void *)

- ea: `0x1800201d8`
- end: `0x1800203e8`
- name: `?RecursiveScanDirectory@@YAJPEBGHQ6AJW4DIRECTORY_SCAN_STATE@@0PEAU_WIN32_FIND_DATAW@@PEAX@Z3@Z`
- size: `528`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, __int64 (__fastcall *)(__int64, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *), void *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013870`
- `0x180018508`
- `0x18001ff7c`
- `0x18002016c`
- `0x1800201d8`

## callees

- `0x1800201d8`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020353`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800202c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800203b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800203bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800203c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800202c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800203b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800203bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800203c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020222`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020222`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18002026b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800202e6`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18002026b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800202e6`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180020246`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180020246`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180020282`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180020282`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002036d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800203a1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002036d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800203a1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002033d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002033d`

## pseudocode

```c
__int64 __fastcall RecursiveScanDirectory(
        const unsigned __int16 *a1,
        int a2,
        __int64 (__fastcall *a3)(__int64, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *),
        void *a4)
{
  int v6; // r15d
  struct _WIN32_FIND_DATAW *v8; // rdi
  int v9; // ebx
  HANDLE FirstFileW; // rsi
  BOOL i; // eax
  __int64 v12; // rcx
  int v13; // eax
  signed int LastError; // eax
  PWSTR ppszPathOut; // [rsp+30h] [rbp-10h] BYREF
  PCWSTR pszPathIn; // [rsp+80h] [rbp+40h] BYREF
  int v18; // [rsp+88h] [rbp+48h]

  v18 = a2;
  pszPathIn = 0;
  ppszPathOut = 0;
  v6 = a2;
  if ( !a1 || !a3 )
  {
    v8 = 0;
    v9 = -2147024809;
    goto LABEL_32;
  }
  v8 = (struct _WIN32_FIND_DATAW *)LocalAlloc(0, 0x250u);
  if ( !v8 )
  {
    v9 = -2147024882;
    goto LABEL_32;
  }
  v9 = PathAllocCanonicalize(a1, 1u, &ppszPathOut);
  if ( v9 >= 0 )
  {
    v9 = PathAllocCombine(ppszPathOut, L"*", 1u, (PWSTR *)&pszPathIn);
    if ( v9 >= 0 )
    {
      FirstFileW = FindFirstFileW(pszPathIn, v8);
      if ( FirstFileW == (HANDLE)-1LL )
      {
LABEL_27:
        if ( v6 )
          v9 = a3(1, a1, v8, a4);
        goto LABEL_32;
      }
      for ( i = 1; ; i = FindNextFileW(FirstFileW, v8) )
      {
        if ( !i )
        {
          if ( GetLastError() == 18 )
          {
            FindClose(FirstFileW);
            v6 = v18;
            goto LABEL_27;
          }
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_30:
          FindClose(FirstFileW);
          goto LABEL_32;
        }
        if ( v8->cFileName[0] != 46 || v8->cFileName[1] && (v8->cFileName[1] != 46 || v8->cFileName[2]) )
          break;
LABEL_22:
        ;
      }
      LocalFree((HLOCAL)pszPathIn);
      pszPathIn = 0;
      v9 = PathAllocCombine(ppszPathOut, v8->cFileName, 1u, (PWSTR *)&pszPathIn);
      if ( v9 < 0 )
        goto LABEL_30;
      if ( (v8->dwFileAttributes & 0x10) != 0 )
      {
        if ( (v8->dwFileAttributes & 0x400) == 0 )
        {
          v13 = RecursiveScanDirectory(
                  pszPathIn,
                  1,
                  (int (__high *const)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *))a3,
                  a4);
          goto LABEL_21;
        }
        v12 = 1;
      }
      else
      {
        v12 = 0;
      }
      v13 = a3(v12, pszPathIn, v8, a4);
LABEL_21:
      v9 = v13;
      if ( v13 < 0 )
        goto LABEL_30;
      goto LABEL_22;
    }
  }
LABEL_32:
  LocalFree(ppszPathOut);
  LocalFree((HLOCAL)pszPathIn);
  LocalFree(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800201d8  mov     [rsp-38h+arg_10], rbx
0x1800201dd  mov     [rsp-38h+arg_8], edx
0x1800201e1  push    rbp
0x1800201e2  push    rsi
0x1800201e3  push    rdi
0x1800201e4  push    r12
0x1800201e6  push    r13
0x1800201e8  push    r14
0x1800201ea  push    r15
0x1800201ec  mov     rbp, rsp
0x1800201ef  sub     rsp, 40h
0x1800201f3  xor     esi, esi
0x1800201f5  mov     r13, r9
0x1800201f8  mov     [rbp+pszPathIn], rsi
0x1800201fc  mov     r14, r8
0x1800201ff  mov     [rbp+ppszPathOut], rsi
0x180020203  mov     r15d, edx
0x180020206  mov     r12, rcx
0x180020209  test    rcx, rcx
0x18002020c  jz      loc_1800203A9
0x180020212  test    r8, r8
0x180020215  jz      loc_1800203A9
0x18002021b  mov     edx, 250h; uBytes
0x180020220  xor     ecx, ecx; uFlags
0x180020222  call    cs:__imp_LocalAlloc
0x180020228  mov     rdi, rax
0x18002022b  test    rax, rax
0x18002022e  jnz     short loc_18002023A
0x180020230  mov     ebx, 8007000Eh
0x180020235  jmp     loc_1800203B1
0x18002023a  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x18002023e  mov     edx, 1; dwFlags
0x180020243  mov     rcx, r12; pszPathIn
0x180020246  call    cs:__imp_PathAllocCanonicalize
0x18002024c  mov     ebx, eax
0x18002024e  test    eax, eax
0x180020250  js      loc_1800203B1
0x180020256  mov     rcx, [rbp+ppszPathOut]; pszPathIn
0x18002025a  lea     r9, [rbp+pszPathIn]; ppszPathOut
0x18002025e  mov     r8d, 1; dwFlags
0x180020264  lea     rdx, asc_18002A358; "*"
0x18002026b  call    cs:__imp_PathAllocCombine
0x180020271  mov     ebx, eax
0x180020273  test    eax, eax
0x180020275  js      loc_1800203B1
0x18002027b  mov     rcx, [rbp+pszPathIn]; lpFileName
0x18002027f  mov     rdx, rdi; lpFindFileData
0x180020282  call    cs:__imp_FindFirstFileW
0x180020288  mov     rsi, rax
0x18002028b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002028f  jz      loc_18002037B
0x180020295  mov     eax, 1
0x18002029a  xor     ecx, ecx
0x18002029c  test    eax, eax
0x18002029e  jz      loc_180020348
0x1800202a4  cmp     word ptr [rdi+2Ch], 2Eh ; '.'
0x1800202a9  jnz     short loc_1800202C2
0x1800202ab  cmp     [rdi+2Eh], cx
0x1800202af  jz      loc_180020337
0x1800202b5  cmp     word ptr [rdi+2Eh], 2Eh ; '.'
0x1800202ba  jnz     short loc_1800202C2
0x1800202bc  cmp     [rdi+30h], cx
0x1800202c0  jz      short loc_180020337
0x1800202c2  mov     rcx, [rbp+pszPathIn]; hMem
0x1800202c6  call    cs:__imp_LocalFree
0x1800202cc  mov     rcx, [rbp+ppszPathOut]; pszPathIn
0x1800202d0  lea     r9, [rbp+pszPathIn]; ppszPathOut
0x1800202d4  mov     r8d, 1; dwFlags
0x1800202da  mov     [rbp+pszPathIn], 0
0x1800202e2  lea     rdx, [rdi+2Ch]; pszMore
0x1800202e6  call    cs:__imp_PathAllocCombine
0x1800202ec  mov     ebx, eax
0x1800202ee  test    eax, eax
0x1800202f0  js      loc_18002039E
0x1800202f6  test    byte ptr [rdi], 10h
0x1800202f9  mov     r9, r13; void *
0x1800202fc  jz      short loc_180020320
0x1800202fe  test    dword ptr [rdi], 400h
0x180020304  jz      short loc_18002030D
0x180020306  mov     ecx, 1
0x18002030b  jmp     short loc_180020322
0x18002030d  mov     rcx, [rbp+pszPathIn]; unsigned __int16 *
0x180020311  mov     r8, r14; int (__high *)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *)
0x180020314  mov     edx, 1; int
0x180020319  call    ?RecursiveScanDirectory@@YAJPEBGHQ6AJW4DIRECTORY_SCAN_STATE@@0PEAU_WIN32_FIND_DATAW@@PEAX@Z3@Z; RecursiveScanDirectory(ushort const *,int,long (*const)(DIRECTORY_SCAN_STATE,ushort const *,_WIN32_FIND_DATAW *,void *),void *)
0x18002031e  jmp     short loc_180020331
0x180020320  xor     ecx, ecx
0x180020322  mov     rdx, [rbp+pszPathIn]
0x180020326  mov     r8, rdi
0x180020329  mov     rax, r14
0x18002032c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020331  mov     ebx, eax
0x180020333  test    eax, eax
0x180020335  js      short loc_18002039E
0x180020337  mov     rdx, rdi; lpFindFileData
0x18002033a  mov     rcx, rsi; hFindFile
0x18002033d  call    cs:__imp_FindNextFileW
0x180020343  jmp     loc_18002029A
0x180020348  call    cs:__imp_GetLastError
0x18002034e  cmp     eax, 12h
0x180020351  jz      short loc_18002036A
0x180020353  call    cs:__imp_GetLastError
0x180020359  mov     ebx, eax
0x18002035b  test    eax, eax
0x18002035d  jle     short loc_18002039E
0x18002035f  movzx   ebx, ax
0x180020362  or      ebx, 80070000h
0x180020368  jmp     short loc_18002039E
0x18002036a  mov     rcx, rsi; hFindFile
0x18002036d  call    cs:__imp_FindClose
0x180020373  mov     r15d, [rbp+arg_8]
0x180020377  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002037b  test    r15d, r15d
0x18002037e  jz      short loc_180020398
0x180020380  mov     r9, r13
0x180020383  mov     r8, rdi
0x180020386  mov     rdx, r12
0x180020389  mov     ecx, 1
0x18002038e  mov     rax, r14
0x180020391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020396  mov     ebx, eax
0x180020398  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002039c  jz      short loc_1800203B1
0x18002039e  mov     rcx, rsi; hFindFile
0x1800203a1  call    cs:__imp_FindClose
0x1800203a7  jmp     short loc_1800203B1
0x1800203a9  mov     rdi, rsi
0x1800203ac  mov     ebx, 80070057h
0x1800203b1  mov     rcx, [rbp+ppszPathOut]; hMem
0x1800203b5  call    cs:__imp_LocalFree
0x1800203bb  mov     rcx, [rbp+pszPathIn]; hMem
0x1800203bf  call    cs:__imp_LocalFree
0x1800203c5  mov     rcx, rdi; hMem
0x1800203c8  call    cs:__imp_LocalFree
0x1800203ce  mov     eax, ebx
0x1800203d0  mov     rbx, [rsp+40h+arg_10]
0x1800203d8  add     rsp, 40h
0x1800203dc  pop     r15
0x1800203de  pop     r14
0x1800203e0  pop     r13
0x1800203e2  pop     r12
0x1800203e4  pop     rdi
0x1800203e5  pop     rsi
0x1800203e6  pop     rbp
0x1800203e7  retn
```
