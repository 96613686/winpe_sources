# Common::Deployment::RecursiveCreateDirectory(ushort const *)

- ea: `0x1800dfa90`
- end: `0x1800dfbf3`
- name: `?RecursiveCreateDirectory@Deployment@Common@@YAJPEBG@Z`
- size: `355`
- prototype: `int(Common::Deployment *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800de860`
- `0x1800dea78`
- `0x1800df378`

## callees

- `0x180098bf4`
- `0x1800dfa90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfb5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfb5e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800dfba1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800dfba1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800dfb54`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800dfb54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dfbd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dfbd8`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800dfb0e`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800dfb0e`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800dfab6`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800dfab6`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x1800dfadd`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x1800dfadd`

## string_xrefs

- `0x1800dfaf5`: `onecore\admin\appmodel\common\utilities.cpp`

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
0x1800dfa90  mov     [rsp-18h+arg_0], rbx
0x1800dfa95  mov     [rsp-18h+arg_18], rsi
0x1800dfa9a  push    rbp
0x1800dfa9b  push    rdi
0x1800dfa9c  push    r15; int
0x1800dfa9e  mov     rbp, rsp
0x1800dfaa1  sub     rsp, 20h
0x1800dfaa5  xor     esi, esi
0x1800dfaa7  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x1800dfaab  mov     [rbp+ppszRootEnd], rsi
0x1800dfaaf  mov     [rbp+ppszPathOut], rsi
0x1800dfab3  lea     edx, [rsi+1]; dwFlags
0x1800dfab6  call    cs:__imp_PathAllocCanonicalize
0x1800dfabc  mov     ebx, eax
0x1800dfabe  test    eax, eax
0x1800dfac0  jns     short loc_1800DFAC9
0x1800dfac2  mov     edx, 922h
0x1800dfac7  jmp     short loc_1800DFAEE
0x1800dfac9  mov     rcx, [rbp+ppszPathOut]; pszPath
0x1800dfacd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800dfad1  inc     rdx
0x1800dfad4  cmp     [rcx+rdx*2], si
0x1800dfad8  jnz     short loc_1800DFAD1
0x1800dfada  inc     rdx; cchPath
0x1800dfadd  call    cs:__imp_PathCchRemoveBackslash
0x1800dfae3  mov     ebx, eax
0x1800dfae5  test    eax, eax
0x1800dfae7  jns     short loc_1800DFB06
0x1800dfae9  mov     edx, 928h; void *
0x1800dfaee  mov     r9d, eax; char *
0x1800dfaf1  mov     rcx, [rbp+18h]; this
0x1800dfaf5  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x1800dfafc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dfb01  jmp     loc_1800DFBD4
0x1800dfb06  mov     rcx, [rbp+ppszPathOut]; pszPath
0x1800dfb0a  lea     rdx, [rbp+ppszRootEnd]; ppszRootEnd
0x1800dfb0e  call    cs:__imp_PathCchSkipRoot
0x1800dfb14  mov     ebx, eax
0x1800dfb16  test    eax, eax
0x1800dfb18  jns     short loc_1800DFB21
0x1800dfb1a  mov     edx, 92Bh
0x1800dfb1f  jmp     short loc_1800DFAEE
0x1800dfb21  mov     rcx, [rbp+ppszRootEnd]
0x1800dfb25  mov     r15d, 5Ch ; '\'
0x1800dfb2b  cmp     si, [rcx]
0x1800dfb2e  setz    dil
0x1800dfb32  test    dil, dil
0x1800dfb35  jnz     loc_1800DFBD2
0x1800dfb3b  cmp     si, [rcx]
0x1800dfb3e  jnz     short loc_1800DFB45
0x1800dfb40  mov     dil, 1
0x1800dfb43  jmp     short loc_1800DFB4E
0x1800dfb45  cmp     r15w, [rcx]
0x1800dfb49  jnz     short loc_1800DFBC5
0x1800dfb4b  mov     [rcx], si
0x1800dfb4e  mov     rcx, [rbp+ppszPathOut]; lpPathName
0x1800dfb52  xor     edx, edx; lpSecurityAttributes
0x1800dfb54  call    cs:__imp_CreateDirectoryW
0x1800dfb5a  test    eax, eax
0x1800dfb5c  jnz     short loc_1800DFBB4
0x1800dfb5e  call    cs:__imp_GetLastError
0x1800dfb64  mov     ebx, eax
0x1800dfb66  test    eax, eax
0x1800dfb68  jle     short loc_1800DFB73
0x1800dfb6a  movzx   ebx, ax
0x1800dfb6d  or      ebx, 80070000h
0x1800dfb73  cmp     ebx, 800700B7h
0x1800dfb79  jz      short loc_1800DFB9D
0x1800dfb7b  cmp     ebx, 80070005h
0x1800dfb81  jz      short loc_1800DFB9D
0x1800dfb83  cmp     ebx, 80070003h
0x1800dfb89  jnz     short loc_1800DFBB0
0x1800dfb8b  mov     ebx, 800700B7h
0x1800dfb90  mov     r9d, ebx
0x1800dfb93  mov     edx, 95Bh
0x1800dfb98  jmp     loc_1800DFAF1
0x1800dfb9d  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x1800dfba1  call    cs:__imp_GetFileAttributesW
0x1800dfba7  cmp     eax, 0FFFFFFFFh
0x1800dfbaa  jz      short loc_1800DFBB4
0x1800dfbac  test    al, 10h
0x1800dfbae  jnz     short loc_1800DFBB4
0x1800dfbb0  test    ebx, ebx
0x1800dfbb2  js      short loc_1800DFB90
0x1800dfbb4  test    dil, dil
0x1800dfbb7  jnz     short loc_1800DFBC1
0x1800dfbb9  mov     rax, [rbp+ppszRootEnd]
0x1800dfbbd  mov     [rax], r15w
0x1800dfbc1  mov     rcx, [rbp+ppszRootEnd]
0x1800dfbc5  add     rcx, 2
0x1800dfbc9  mov     [rbp+ppszRootEnd], rcx
0x1800dfbcd  jmp     loc_1800DFB32
0x1800dfbd2  mov     ebx, esi
0x1800dfbd4  mov     rcx, [rbp+ppszPathOut]; hMem
0x1800dfbd8  call    cs:__imp_LocalFree
0x1800dfbde  mov     rsi, [rsp+20h+arg_18]
0x1800dfbe3  mov     eax, ebx
0x1800dfbe5  mov     rbx, [rsp+20h+arg_0]
0x1800dfbea  add     rsp, 20h
0x1800dfbee  pop     r15
0x1800dfbf0  pop     rdi
0x1800dfbf1  pop     rbp
0x1800dfbf2  retn
```
