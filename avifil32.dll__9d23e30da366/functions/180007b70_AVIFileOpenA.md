# AVIFileOpenA

- ea: `0x180007b70`
- end: `0x180007bfa`
- name: `AVIFileOpenA`
- size: `138`
- prototype: `HRESULT __stdcall(PAVIFILE *ppfile, LPCSTR szFile, UINT uMode, LPCLSID lpHandler)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800083d0`

## callees

- `0x180007b70`
- `0x180007c00`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180007b8c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180007b8c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007ba0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007ba0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007be5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007be5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007bc9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007bc9`

## pseudocode

```c
HRESULT __stdcall AVIFileOpenA(PAVIFILE *ppfile, LPCSTR szFile, UINT uMode, LPCLSID lpHandler)
{
  int cchWideChar; // esi
  WCHAR *lpWideCharStr; // rax
  WCHAR *v10; // rdi
  HRESULT v12; // ebx

  cchWideChar = lstrlenA(szFile) + 1;
  lpWideCharStr = (WCHAR *)LocalAlloc(0x40u, 2LL * cchWideChar);
  v10 = lpWideCharStr;
  if ( !lpWideCharStr )
    return -2147205017;
  MultiByteToWideChar(0, 0, szFile, -1, lpWideCharStr, cchWideChar);
  v12 = AVIFileOpenW(ppfile, v10, uMode, lpHandler);
  LocalFree(v10);
  return v12;
}

```

## disassembly

```asm
0x180007b70  push    rbx; AVIFileOpen
0x180007b72  push    rbp
0x180007b73  push    rsi
0x180007b74  push    rdi
0x180007b75  push    r14
0x180007b77  push    r15
0x180007b79  sub     rsp, 38h
0x180007b7d  mov     r15, rcx
0x180007b80  mov     rbp, r9
0x180007b83  mov     rcx, rdx; lpString
0x180007b86  mov     r14d, r8d
0x180007b89  mov     rbx, rdx
0x180007b8c  call    cs:__imp_lstrlenA
0x180007b92  mov     ecx, 40h ; '@'; uFlags
0x180007b97  lea     esi, [rax+1]
0x180007b9a  movsxd  rdx, esi
0x180007b9d  add     rdx, rdx; uBytes
0x180007ba0  call    cs:__imp_LocalAlloc
0x180007ba6  mov     rdi, rax
0x180007ba9  test    rax, rax
0x180007bac  jnz     short loc_180007BB5
0x180007bae  mov     eax, 80044067h
0x180007bb3  jmp     short loc_180007BED
0x180007bb5  mov     [rsp+68h+cchWideChar], esi; cchWideChar
0x180007bb9  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180007bbd  mov     r8, rbx; lpMultiByteStr
0x180007bc0  mov     [rsp+68h+lpWideCharStr], rdi; lpWideCharStr
0x180007bc5  xor     edx, edx; dwFlags
0x180007bc7  xor     ecx, ecx; CodePage
0x180007bc9  call    cs:__imp_MultiByteToWideChar
0x180007bcf  mov     r9, rbp; lpHandler
0x180007bd2  mov     r8d, r14d; uMode
0x180007bd5  mov     rdx, rdi; szFile
0x180007bd8  mov     rcx, r15; ppfile
0x180007bdb  call    AVIFileOpenW
0x180007be0  mov     rcx, rdi; hMem
0x180007be3  mov     ebx, eax
0x180007be5  call    cs:__imp_LocalFree
0x180007beb  mov     eax, ebx
0x180007bed  add     rsp, 38h
0x180007bf1  pop     r15
0x180007bf3  pop     r14
0x180007bf5  pop     rdi
0x180007bf6  pop     rsi
0x180007bf7  pop     rbp
0x180007bf8  pop     rbx
0x180007bf9  retn
```
