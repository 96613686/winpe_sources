# Common::Deployment::RecursiveCreateDirectory(ushort const *)

- ea: `0x180056c2c`
- end: `0x180056dbe`
- name: `?RecursiveCreateDirectory@Deployment@Common@@YAJPEBG@Z`
- size: `402`
- prototype: `int(Common::Deployment *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800079d0`
- `0x180092880`
- `0x1801861f0`

## callees

- `0x18001adb4`
- `0x180056c2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056d16`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180056d5f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180056d5f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180056d06`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180056d06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056d9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056d9c`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x180056c7f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x180056c7f`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180056c52`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180056c52`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x180056cb6`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x180056cb6`

## string_xrefs

- `0x180056c9d`: `onecore\admin\appmodel\common\utilities.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::RecursiveCreateDirectory(const WCHAR *this, const unsigned __int16 *a2)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rdx
  unsigned __int64 v6; // r9
  PCWSTR v7; // rcx
  bool v8; // di
  signed int LastError; // eax
  DWORD FileAttributesW; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  PCWSTR ppszRootEnd; // [rsp+48h] [rbp+28h] BYREF
  PWSTR ppszPathOut; // [rsp+50h] [rbp+30h] BYREF

  ppszRootEnd = 0;
  ppszPathOut = 0;
  v2 = PathAllocCanonicalize(this, 1u, &ppszPathOut);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 2338;
    goto LABEL_7;
  }
  v5 = -1;
  do
    ++v5;
  while ( ppszPathOut[v5] );
  v2 = PathCchRemoveBackslash(ppszPathOut, v5 + 1);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 2344;
    goto LABEL_7;
  }
  v2 = PathCchSkipRoot(ppszPathOut, &ppszRootEnd);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v7 = ppszRootEnd;
    v8 = *ppszRootEnd == 0;
    while ( 1 )
    {
      if ( v8 )
      {
        v3 = 0;
        goto LABEL_33;
      }
      if ( *v7 )
      {
        if ( *v7 != 92 )
          goto LABEL_31;
        *v7 = 0;
      }
      else
      {
        v8 = 1;
      }
      if ( !CreateDirectoryW(ppszPathOut, 0) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 != -2147024713 && v3 != -2147024891 )
        {
          if ( v3 == -2147024893 )
          {
            v3 = -2147024713;
LABEL_24:
            v6 = v3;
            v4 = 2395;
            goto LABEL_8;
          }
LABEL_27:
          if ( (v3 & 0x80000000) != 0 )
            goto LABEL_24;
          goto LABEL_28;
        }
        FileAttributesW = GetFileAttributesW(ppszPathOut);
        if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
          goto LABEL_27;
      }
LABEL_28:
      if ( !v8 )
        *ppszRootEnd = 92;
      v7 = ppszRootEnd;
LABEL_31:
      ppszRootEnd = ++v7;
    }
  }
  v4 = 2347;
LABEL_7:
  v6 = (unsigned int)v2;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
    (const char *)v6,
    savedregs);
LABEL_33:
  LocalFree(ppszPathOut);
  return v3;
}

```

## disassembly

```asm
0x180056c2c  mov     [rsp-18h+arg_0], rbx
0x180056c31  mov     [rsp-18h+arg_18], rsi
0x180056c36  push    rbp
0x180056c37  push    rdi
0x180056c38  push    r15; int
0x180056c3a  mov     rbp, rsp
0x180056c3d  sub     rsp, 20h
0x180056c41  xor     esi, esi
0x180056c43  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x180056c47  mov     [rbp+ppszRootEnd], rsi
0x180056c4b  mov     [rbp+ppszPathOut], rsi
0x180056c4f  lea     edx, [rsi+1]; dwFlags
0x180056c52  call    cs:__imp_PathAllocCanonicalize
0x180056c59  nop     dword ptr [rax+rax+00h]
0x180056c5e  mov     ebx, eax
0x180056c60  test    eax, eax
0x180056c62  jns     short loc_180056C6B
0x180056c64  mov     edx, 922h
0x180056c69  jmp     short loc_180056C96
0x180056c6b  mov     rcx, [rbp+ppszPathOut]; pszPath
0x180056c6f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180056c73  inc     rdx
0x180056c76  cmp     [rcx+rdx*2], si
0x180056c7a  jnz     short loc_180056C73
0x180056c7c  inc     rdx; cchPath
0x180056c7f  call    cs:__imp_PathCchRemoveBackslash
0x180056c86  nop     dword ptr [rax+rax+00h]
0x180056c8b  mov     ebx, eax
0x180056c8d  test    eax, eax
0x180056c8f  jns     short loc_180056CAE
0x180056c91  mov     edx, 928h; void *
0x180056c96  mov     r9d, eax; char *
0x180056c99  mov     rcx, [rbp+18h]; this
0x180056c9d  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x180056ca4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056ca9  jmp     loc_180056D98
0x180056cae  mov     rcx, [rbp+ppszPathOut]; pszPath
0x180056cb2  lea     rdx, [rbp+ppszRootEnd]; ppszRootEnd
0x180056cb6  call    cs:__imp_PathCchSkipRoot
0x180056cbd  nop     dword ptr [rax+rax+00h]
0x180056cc2  mov     ebx, eax
0x180056cc4  test    eax, eax
0x180056cc6  jns     short loc_180056CCF
0x180056cc8  mov     edx, 92Bh
0x180056ccd  jmp     short loc_180056C96
0x180056ccf  mov     rcx, [rbp+ppszRootEnd]
0x180056cd3  mov     r15d, 5Ch ; '\'
0x180056cd9  cmp     si, [rcx]
0x180056cdc  setz    dil
0x180056ce0  test    dil, dil
0x180056ce3  jnz     loc_180056D96
0x180056ce9  cmp     si, [rcx]
0x180056cec  jnz     short loc_180056CF3
0x180056cee  mov     dil, 1
0x180056cf1  jmp     short loc_180056D00
0x180056cf3  cmp     r15w, [rcx]
0x180056cf7  jnz     loc_180056D89
0x180056cfd  mov     [rcx], si
0x180056d00  mov     rcx, [rbp+ppszPathOut]; lpPathName
0x180056d04  xor     edx, edx; lpSecurityAttributes
0x180056d06  call    cs:__imp_CreateDirectoryW
0x180056d0d  nop     dword ptr [rax+rax+00h]
0x180056d12  test    eax, eax
0x180056d14  jnz     short loc_180056D78
0x180056d16  call    cs:__imp_GetLastError
0x180056d1d  nop     dword ptr [rax+rax+00h]
0x180056d22  mov     ebx, eax
0x180056d24  test    eax, eax
0x180056d26  jle     short loc_180056D31
0x180056d28  movzx   ebx, ax
0x180056d2b  or      ebx, 80070000h
0x180056d31  cmp     ebx, 800700B7h
0x180056d37  jz      short loc_180056D5B
0x180056d39  cmp     ebx, 80070005h
0x180056d3f  jz      short loc_180056D5B
0x180056d41  cmp     ebx, 80070003h
0x180056d47  jnz     short loc_180056D74
0x180056d49  mov     ebx, 800700B7h
0x180056d4e  mov     r9d, ebx
0x180056d51  mov     edx, 95Bh
0x180056d56  jmp     loc_180056C99
0x180056d5b  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x180056d5f  call    cs:__imp_GetFileAttributesW
0x180056d66  nop     dword ptr [rax+rax+00h]
0x180056d6b  cmp     eax, 0FFFFFFFFh
0x180056d6e  jz      short loc_180056D78
0x180056d70  test    al, 10h
0x180056d72  jnz     short loc_180056D78
0x180056d74  test    ebx, ebx
0x180056d76  js      short loc_180056D4E
0x180056d78  test    dil, dil
0x180056d7b  jnz     short loc_180056D85
0x180056d7d  mov     rax, [rbp+ppszRootEnd]
0x180056d81  mov     [rax], r15w
0x180056d85  mov     rcx, [rbp+ppszRootEnd]
0x180056d89  add     rcx, 2
0x180056d8d  mov     [rbp+ppszRootEnd], rcx
0x180056d91  jmp     loc_180056CE0
0x180056d96  mov     ebx, esi
0x180056d98  mov     rcx, [rbp+ppszPathOut]; hMem
0x180056d9c  call    cs:__imp_LocalFree
0x180056da3  nop     dword ptr [rax+rax+00h]
0x180056da8  mov     rsi, [rsp+20h+arg_18]
0x180056dad  mov     eax, ebx
0x180056daf  mov     rbx, [rsp+20h+arg_0]
0x180056db4  add     rsp, 20h
0x180056db8  pop     r15
0x180056dba  pop     rdi
0x180056dbb  pop     rbp
0x180056dbc  retn
```
