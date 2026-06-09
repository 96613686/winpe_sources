# Wallet::FileUtils::RecursiveCreateDirectory(ushort const *)

- ea: `0x180036948`
- end: `0x180036a83`
- name: `?RecursiveCreateDirectory@FileUtils@Wallet@@YAJPEBG@Z`
- size: `315`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, reparse_path`

## callers

- `0x1800110f0`
- `0x180027434`
- `0x1800283c4`
- `0x180037ce0`

## callees

- `0x180036948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800369f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800369f0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800369e6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800369e6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180036a4a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180036a4a`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18003696e`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18003696e`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x180036992`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x180036992`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800369aa`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800369aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036a2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036a2b`

## pseudocode

```c
__int64 __fastcall Wallet::FileUtils::RecursiveCreateDirectory(const WCHAR *this, const unsigned __int16 *a2)
{
  int v2; // ebx
  __int64 v3; // rdx
  PCWSTR v4; // rcx
  int v5; // edi
  signed int LastError; // eax
  DWORD FileAttributesW; // eax
  PCWSTR ppszRootEnd; // [rsp+48h] [rbp+28h] BYREF
  PWSTR ppszPathOut; // [rsp+50h] [rbp+30h] BYREF

  ppszRootEnd = 0;
  ppszPathOut = 0;
  v2 = PathAllocCanonicalize(this, 1u, &ppszPathOut);
  if ( v2 >= 0 )
  {
    v3 = -1;
    do
      ++v3;
    while ( ppszPathOut[v3] );
    v2 = PathCchRemoveBackslash(ppszPathOut, v3 + 1);
    if ( v2 >= 0 )
    {
      v2 = PathCchSkipRoot(ppszPathOut, &ppszRootEnd);
      if ( v2 >= 0 )
      {
        v4 = ppszRootEnd;
        if ( *ppszRootEnd )
        {
          v5 = 0;
          while ( 1 )
          {
            if ( !*v4 )
            {
              v5 = 1;
              goto LABEL_12;
            }
            if ( *v4 == 92 )
              break;
LABEL_30:
            ppszRootEnd = ++v4;
            if ( v5 )
              goto LABEL_19;
          }
          *v4 = 0;
LABEL_12:
          if ( !CreateDirectoryW(ppszPathOut, 0) )
          {
            LastError = GetLastError();
            v2 = LastError;
            if ( LastError > 0 )
              v2 = (unsigned __int16)LastError | 0x80070000;
            if ( v2 != -2147024713 && v2 != -2147024891 )
            {
              if ( v2 == -2147024893 )
              {
                v2 = -2147024713;
                goto LABEL_19;
              }
              goto LABEL_24;
            }
            FileAttributesW = GetFileAttributesW(ppszPathOut);
            if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
            {
LABEL_24:
              if ( v2 < 0 )
                goto LABEL_19;
              goto LABEL_27;
            }
            v2 = 0;
          }
LABEL_27:
          if ( !v5 )
            *ppszRootEnd = 92;
          v4 = ppszRootEnd;
          goto LABEL_30;
        }
      }
    }
  }
LABEL_19:
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180036948  mov     [rsp-18h+arg_0], rbx
0x18003694d  mov     [rsp-18h+arg_18], rsi
0x180036952  push    rbp
0x180036953  push    rdi
0x180036954  push    r15
0x180036956  mov     rbp, rsp
0x180036959  sub     rsp, 20h
0x18003695d  xor     esi, esi
0x18003695f  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x180036963  mov     [rbp+ppszRootEnd], rsi
0x180036967  mov     [rbp+ppszPathOut], rsi
0x18003696b  lea     edx, [rsi+1]; dwFlags
0x18003696e  call    cs:__imp_PathAllocCanonicalize
0x180036974  mov     ebx, eax
0x180036976  test    eax, eax
0x180036978  js      loc_180036A22
0x18003697e  mov     rcx, [rbp+ppszPathOut]; pszPath
0x180036982  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180036986  inc     rdx
0x180036989  cmp     [rcx+rdx*2], si
0x18003698d  jnz     short loc_180036986
0x18003698f  inc     rdx; cchPath
0x180036992  call    cs:__imp_PathCchRemoveBackslash
0x180036998  mov     ebx, eax
0x18003699a  test    eax, eax
0x18003699c  js      loc_180036A22
0x1800369a2  mov     rcx, [rbp+ppszPathOut]; pszPath
0x1800369a6  lea     rdx, [rbp+ppszRootEnd]; ppszRootEnd
0x1800369aa  call    cs:__imp_PathCchSkipRoot
0x1800369b0  mov     ebx, eax
0x1800369b2  test    eax, eax
0x1800369b4  js      short loc_180036A22
0x1800369b6  mov     rcx, [rbp+ppszRootEnd]
0x1800369ba  cmp     si, [rcx]
0x1800369bd  jz      short loc_180036A22
0x1800369bf  mov     edi, esi
0x1800369c1  mov     r15d, 5Ch ; '\'
0x1800369c7  cmp     si, [rcx]
0x1800369ca  jnz     short loc_1800369D3
0x1800369cc  mov     edi, 1
0x1800369d1  jmp     short loc_1800369E0
0x1800369d3  cmp     r15w, [rcx]
0x1800369d7  jnz     loc_180036A71
0x1800369dd  mov     [rcx], si
0x1800369e0  mov     rcx, [rbp+ppszPathOut]; lpPathName
0x1800369e4  xor     edx, edx; lpSecurityAttributes
0x1800369e6  call    cs:__imp_CreateDirectoryW
0x1800369ec  test    eax, eax
0x1800369ee  jnz     short loc_180036A61
0x1800369f0  call    cs:__imp_GetLastError
0x1800369f6  mov     ebx, eax
0x1800369f8  test    eax, eax
0x1800369fa  jle     short loc_180036A05
0x1800369fc  movzx   ebx, ax
0x1800369ff  or      ebx, 80070000h
0x180036a05  cmp     ebx, 800700B7h
0x180036a0b  jz      short loc_180036A46
0x180036a0d  cmp     ebx, 80070005h
0x180036a13  jz      short loc_180036A46
0x180036a15  cmp     ebx, 80070003h
0x180036a1b  jnz     short loc_180036A59
0x180036a1d  mov     ebx, 800700B7h
0x180036a22  mov     rcx, [rbp+ppszPathOut]; hMem
0x180036a26  test    rcx, rcx
0x180036a29  jz      short loc_180036A31
0x180036a2b  call    cs:__imp_LocalFree
0x180036a31  mov     rsi, [rsp+20h+arg_18]
0x180036a36  mov     eax, ebx
0x180036a38  mov     rbx, [rsp+20h+arg_0]
0x180036a3d  add     rsp, 20h
0x180036a41  pop     r15
0x180036a43  pop     rdi
0x180036a44  pop     rbp
0x180036a45  retn
0x180036a46  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x180036a4a  call    cs:__imp_GetFileAttributesW
0x180036a50  cmp     eax, 0FFFFFFFFh
0x180036a53  jz      short loc_180036A5F
0x180036a55  test    al, 10h
0x180036a57  jnz     short loc_180036A5F
0x180036a59  test    ebx, ebx
0x180036a5b  js      short loc_180036A22
0x180036a5d  jmp     short loc_180036A61
0x180036a5f  mov     ebx, esi
0x180036a61  test    edi, edi
0x180036a63  jnz     short loc_180036A6D
0x180036a65  mov     rax, [rbp+ppszRootEnd]
0x180036a69  mov     [rax], r15w
0x180036a6d  mov     rcx, [rbp+ppszRootEnd]
0x180036a71  add     rcx, 2
0x180036a75  mov     [rbp+ppszRootEnd], rcx
0x180036a79  test    edi, edi
0x180036a7b  jz      loc_1800369C7
0x180036a81  jmp     short loc_180036A22
```
