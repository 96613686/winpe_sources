# LocationDirectoryUtils::RecursiveCreateDirectory(ushort const *)

- ea: `0x18004a100`
- end: `0x18004a25d`
- name: `?RecursiveCreateDirectory@LocationDirectoryUtils@@SAJPEBG@Z`
- size: `349`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x18000f1fc`
- `0x180049e94`
- `0x180100bbc`

## callees

- `0x18004a100`
- `0x1800a98c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a20c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a20c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004a1a9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004a1a9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004a1d4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004a1d4`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18004a134`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18004a134`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18004a170`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18004a170`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x18004a158`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x18004a158`

## pseudocode

```c
__int64 __fastcall LocationDirectoryUtils::RecursiveCreateDirectory(const unsigned __int16 *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  PCWSTR v3; // rcx
  int v4; // edi
  signed int LastError; // eax
  DWORD FileAttributesW; // eax
  PCWSTR ppszRootEnd; // [rsp+20h] [rbp-20h] BYREF
  PWSTR ppszPathOut; // [rsp+28h] [rbp-18h] BYREF

  ppszRootEnd = 0;
  ppszPathOut = 0;
  v1 = PathAllocCanonicalize(a1, 1u, &ppszPathOut);
  if ( v1 >= 0 )
  {
    v2 = -1;
    do
      ++v2;
    while ( ppszPathOut[v2] );
    v1 = PathCchRemoveBackslash(ppszPathOut, v2 + 1);
    if ( v1 >= 0 )
    {
      v1 = PathCchSkipRoot(ppszPathOut, &ppszRootEnd);
      if ( v1 >= 0 )
      {
        v3 = ppszRootEnd;
        if ( *ppszRootEnd )
        {
          v4 = 0;
          do
          {
            if ( *v3 )
            {
              if ( *v3 != 92 )
                goto LABEL_21;
              *v3 = 0;
            }
            else
            {
              v4 = 1;
            }
            if ( !CreateDirectoryW(ppszPathOut, 0) )
            {
              LastError = GetLastError();
              v1 = LastError;
              if ( LastError > 0 )
                v1 = (unsigned __int16)LastError | 0x80070000;
              if ( v1 != -2147024713 )
              {
                if ( v1 == -2147024893 )
                {
                  v1 = -2147024713;
                  break;
                }
                if ( v1 != -2147024891 )
                  goto LABEL_17;
              }
              FileAttributesW = GetFileAttributesW(ppszPathOut);
              if ( FileAttributesW == -1 || (FileAttributesW & 0x10) != 0 )
              {
                v1 = 0;
              }
              else
              {
LABEL_17:
                if ( v1 < 0 )
                  break;
              }
            }
            if ( !v4 )
              *ppszRootEnd = 92;
            v3 = ppszRootEnd;
LABEL_21:
            ppszRootEnd = ++v3;
          }
          while ( !v4 );
        }
      }
    }
  }
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18004a100  mov     [rsp-18h+arg_8], rbx
0x18004a105  mov     [rsp-18h+arg_10], rsi
0x18004a10a  push    rbp
0x18004a10b  push    rdi
0x18004a10c  push    r15
0x18004a10e  mov     rbp, rsp
0x18004a111  sub     rsp, 40h
0x18004a115  mov     rax, cs:__security_cookie
0x18004a11c  xor     rax, rsp
0x18004a11f  mov     [rbp+var_10], rax
0x18004a123  xor     esi, esi
0x18004a125  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x18004a129  mov     [rbp+ppszRootEnd], rsi
0x18004a12d  mov     [rbp+ppszPathOut], rsi
0x18004a131  lea     edx, [rsi+1]; dwFlags
0x18004a134  call    cs:__imp_PathAllocCanonicalize
0x18004a13a  mov     ebx, eax
0x18004a13c  test    eax, eax
0x18004a13e  js      loc_18004A203
0x18004a144  mov     rcx, [rbp+ppszPathOut]; pszPath
0x18004a148  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004a14c  inc     rdx
0x18004a14f  cmp     [rcx+rdx*2], si
0x18004a153  jnz     short loc_18004A14C
0x18004a155  inc     rdx; cchPath
0x18004a158  call    cs:__imp_PathCchRemoveBackslash
0x18004a15e  mov     ebx, eax
0x18004a160  test    eax, eax
0x18004a162  js      loc_18004A203
0x18004a168  mov     rcx, [rbp+ppszPathOut]; pszPath
0x18004a16c  lea     rdx, [rbp+ppszRootEnd]; ppszRootEnd
0x18004a170  call    cs:__imp_PathCchSkipRoot
0x18004a176  mov     ebx, eax
0x18004a178  test    eax, eax
0x18004a17a  js      loc_18004A203
0x18004a180  mov     rcx, [rbp+ppszRootEnd]
0x18004a184  cmp     si, [rcx]
0x18004a187  jz      short loc_18004A203
0x18004a189  mov     edi, esi
0x18004a18b  mov     r15d, 5Ch ; '\'
0x18004a191  cmp     si, [rcx]
0x18004a194  jz      loc_18004A237
0x18004a19a  cmp     r15w, [rcx]
0x18004a19e  jnz     short loc_18004A1F7
0x18004a1a0  mov     [rcx], si
0x18004a1a3  mov     rcx, [rbp+ppszPathOut]; lpPathName
0x18004a1a7  xor     edx, edx; lpSecurityAttributes
0x18004a1a9  call    cs:__imp_CreateDirectoryW
0x18004a1af  test    eax, eax
0x18004a1b1  jnz     short loc_18004A1E7
0x18004a1b3  call    cs:__imp_GetLastError
0x18004a1b9  mov     ebx, eax
0x18004a1bb  test    eax, eax
0x18004a1bd  jle     short loc_18004A1C8
0x18004a1bf  movzx   ebx, ax
0x18004a1c2  or      ebx, 80070000h
0x18004a1c8  cmp     ebx, 800700B7h
0x18004a1ce  jnz     short loc_18004A241
0x18004a1d0  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x18004a1d4  call    cs:__imp_GetFileAttributesW
0x18004a1da  cmp     eax, 0FFFFFFFFh
0x18004a1dd  jz      short loc_18004A233
0x18004a1df  test    al, 10h
0x18004a1e1  jnz     short loc_18004A233
0x18004a1e3  test    ebx, ebx
0x18004a1e5  js      short loc_18004A203
0x18004a1e7  test    edi, edi
0x18004a1e9  jnz     short loc_18004A1F3
0x18004a1eb  mov     rax, [rbp+ppszRootEnd]
0x18004a1ef  mov     [rax], r15w
0x18004a1f3  mov     rcx, [rbp+ppszRootEnd]
0x18004a1f7  add     rcx, 2
0x18004a1fb  mov     [rbp+ppszRootEnd], rcx
0x18004a1ff  test    edi, edi
0x18004a201  jz      short loc_18004A191
0x18004a203  mov     rcx, [rbp+ppszPathOut]; hMem
0x18004a207  test    rcx, rcx
0x18004a20a  jz      short loc_18004A212
0x18004a20c  call    cs:__imp_LocalFree
0x18004a212  mov     eax, ebx
0x18004a214  mov     rcx, [rbp+var_10]
0x18004a218  xor     rcx, rsp; StackCookie
0x18004a21b  call    __security_check_cookie
0x18004a220  mov     rbx, [rsp+40h+arg_8]
0x18004a225  mov     rsi, [rsp+40h+arg_10]
0x18004a22a  add     rsp, 40h
0x18004a22e  pop     r15
0x18004a230  pop     rdi
0x18004a231  pop     rbp
0x18004a232  retn
0x18004a233  mov     ebx, esi
0x18004a235  jmp     short loc_18004A1E7
0x18004a237  mov     edi, 1
0x18004a23c  jmp     loc_18004A1A3
0x18004a241  cmp     ebx, 80070003h
0x18004a247  jz      short loc_18004A256
0x18004a249  cmp     ebx, 80070005h
0x18004a24f  jnz     short loc_18004A1E3
0x18004a251  jmp     loc_18004A1D0
0x18004a256  mov     ebx, 800700B7h
0x18004a25b  jmp     short loc_18004A203
```
