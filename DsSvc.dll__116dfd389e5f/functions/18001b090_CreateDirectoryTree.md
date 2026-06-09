# CreateDirectoryTree

- ea: `0x18001b090`
- end: `0x18001b1cf`
- name: `CreateDirectoryTree`
- size: `319`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x18001a654`

## callees

- `0x180003483`
- `0x18001b090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b13d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b13d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001b133`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001b133`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001b196`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001b196`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18001b0f7`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18001b0f7`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x18001b0df`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x18001b0df`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18001b0bb`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18001b0bb`

## pseudocode

```c
__int64 __fastcall CreateDirectoryTree(const WCHAR *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  PCWSTR v3; // rcx
  int v4; // edi
  signed int LastError; // eax
  DWORD FileAttributesW; // eax
  PCWSTR ppszRootEnd; // [rsp+48h] [rbp+28h] BYREF
  PWSTR ppszPathOut; // [rsp+50h] [rbp+30h] BYREF

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
          while ( 1 )
          {
            if ( !*v3 )
            {
              v4 = 1;
              goto LABEL_12;
            }
            if ( *v3 == 92 )
              break;
LABEL_30:
            ppszRootEnd = ++v3;
            if ( v4 )
              goto LABEL_19;
          }
          *v3 = 0;
LABEL_12:
          if ( !CreateDirectoryW(ppszPathOut, 0) )
          {
            LastError = GetLastError();
            v1 = LastError;
            if ( LastError > 0 )
              v1 = (unsigned __int16)LastError | 0x80070000;
            if ( v1 != -2147024713 && v1 != -2147024891 )
            {
              if ( v1 == -2147024893 )
              {
                v1 = -2147024713;
                goto LABEL_19;
              }
              goto LABEL_24;
            }
            FileAttributesW = GetFileAttributesW(ppszPathOut);
            if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
            {
LABEL_24:
              if ( v1 < 0 )
                goto LABEL_19;
              goto LABEL_27;
            }
            v1 = 0;
          }
LABEL_27:
          if ( !v4 )
            *ppszRootEnd = 92;
          v3 = ppszRootEnd;
          goto LABEL_30;
        }
      }
    }
  }
LABEL_19:
  if ( ppszPathOut )
    LocalFree_0(ppszPathOut);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001b090  mov     [rsp-18h+arg_0], rbx
0x18001b095  mov     [rsp-18h+arg_18], rsi
0x18001b09a  mov     [rsp-18h+ppszRootEnd], rdx
0x18001b09f  push    rbp
0x18001b0a0  push    rdi
0x18001b0a1  push    r15
0x18001b0a3  mov     rbp, rsp
0x18001b0a6  sub     rsp, 20h
0x18001b0aa  xor     esi, esi
0x18001b0ac  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x18001b0b0  mov     [rbp+ppszRootEnd], rsi
0x18001b0b4  mov     [rbp+ppszPathOut], rsi
0x18001b0b8  lea     edx, [rsi+1]; dwFlags
0x18001b0bb  call    cs:__imp_PathAllocCanonicalize
0x18001b0c1  mov     ebx, eax
0x18001b0c3  test    eax, eax
0x18001b0c5  js      loc_18001B16F
0x18001b0cb  mov     rcx, [rbp+ppszPathOut]; pszPath
0x18001b0cf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001b0d3  inc     rdx
0x18001b0d6  cmp     [rcx+rdx*2], si
0x18001b0da  jnz     short loc_18001B0D3
0x18001b0dc  inc     rdx; cchPath
0x18001b0df  call    cs:__imp_PathCchRemoveBackslash
0x18001b0e5  mov     ebx, eax
0x18001b0e7  test    eax, eax
0x18001b0e9  js      loc_18001B16F
0x18001b0ef  mov     rcx, [rbp+ppszPathOut]; pszPath
0x18001b0f3  lea     rdx, [rbp+ppszRootEnd]; ppszRootEnd
0x18001b0f7  call    cs:__imp_PathCchSkipRoot
0x18001b0fd  mov     ebx, eax
0x18001b0ff  test    eax, eax
0x18001b101  js      short loc_18001B16F
0x18001b103  mov     rcx, [rbp+ppszRootEnd]
0x18001b107  cmp     si, [rcx]
0x18001b10a  jz      short loc_18001B16F
0x18001b10c  mov     edi, esi
0x18001b10e  mov     r15d, 5Ch ; '\'
0x18001b114  cmp     si, [rcx]
0x18001b117  jnz     short loc_18001B120
0x18001b119  mov     edi, 1
0x18001b11e  jmp     short loc_18001B12D
0x18001b120  cmp     r15w, [rcx]
0x18001b124  jnz     loc_18001B1BD
0x18001b12a  mov     [rcx], si
0x18001b12d  mov     rcx, [rbp+ppszPathOut]; lpPathName
0x18001b131  xor     edx, edx; lpSecurityAttributes
0x18001b133  call    cs:__imp_CreateDirectoryW
0x18001b139  test    eax, eax
0x18001b13b  jnz     short loc_18001B1AD
0x18001b13d  call    cs:__imp_GetLastError
0x18001b143  mov     ebx, eax
0x18001b145  test    eax, eax
0x18001b147  jle     short loc_18001B152
0x18001b149  movzx   ebx, ax
0x18001b14c  or      ebx, 80070000h
0x18001b152  cmp     ebx, 800700B7h
0x18001b158  jz      short loc_18001B192
0x18001b15a  cmp     ebx, 80070005h
0x18001b160  jz      short loc_18001B192
0x18001b162  cmp     ebx, 80070003h
0x18001b168  jnz     short loc_18001B1A5
0x18001b16a  mov     ebx, 800700B7h
0x18001b16f  mov     rcx, [rbp+ppszPathOut]; hMem
0x18001b173  test    rcx, rcx
0x18001b176  jz      short loc_18001B17D
0x18001b178  call    LocalFree_0
0x18001b17d  mov     rsi, [rsp+20h+arg_18]
0x18001b182  mov     eax, ebx
0x18001b184  mov     rbx, [rsp+20h+arg_0]
0x18001b189  add     rsp, 20h
0x18001b18d  pop     r15
0x18001b18f  pop     rdi
0x18001b190  pop     rbp
0x18001b191  retn
0x18001b192  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x18001b196  call    cs:__imp_GetFileAttributesW
0x18001b19c  cmp     eax, 0FFFFFFFFh
0x18001b19f  jz      short loc_18001B1AB
0x18001b1a1  test    al, 10h
0x18001b1a3  jnz     short loc_18001B1AB
0x18001b1a5  test    ebx, ebx
0x18001b1a7  js      short loc_18001B16F
0x18001b1a9  jmp     short loc_18001B1AD
0x18001b1ab  mov     ebx, esi
0x18001b1ad  test    edi, edi
0x18001b1af  jnz     short loc_18001B1B9
0x18001b1b1  mov     rax, [rbp+ppszRootEnd]
0x18001b1b5  mov     [rax], r15w
0x18001b1b9  mov     rcx, [rbp+ppszRootEnd]
0x18001b1bd  add     rcx, 2
0x18001b1c1  mov     [rbp+ppszRootEnd], rcx
0x18001b1c5  test    edi, edi
0x18001b1c7  jz      loc_18001B114
0x18001b1cd  jmp     short loc_18001B16F
```
