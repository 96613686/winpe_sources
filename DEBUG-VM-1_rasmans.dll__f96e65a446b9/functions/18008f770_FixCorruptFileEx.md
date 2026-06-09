# FixCorruptFileEx

- ea: `0x18008f770`
- end: `0x18008fab9`
- name: `FixCorruptFileEx`
- size: `841`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180090220`

## callees

- `0x180002294`
- `0x1800022ac`
- `0x18000e564`
- `0x18008f770`
- `0x18008fc18`
- `0x18008fd24`
- `0x1800e71ee`
- `0x1800e7260`

## import_xrefs

- `msvcrt!calloc` at `0x18008fa11`
- `msvcrt!calloc` at `0x18008fa11`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008f7db`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008f7db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f7c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f7c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f802`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f834`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f9f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008fa70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008fa7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f802`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f834`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f9f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008fa70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008fa7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fa59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fa59`
- `RPCRT4!RpcImpersonateClient` at `0x18008f7bd`
- `RPCRT4!RpcImpersonateClient` at `0x18008f83c`
- `RPCRT4!RpcImpersonateClient` at `0x18008f7bd`
- `RPCRT4!RpcImpersonateClient` at `0x18008f83c`
- `RPCRT4!RpcRevertToSelf` at `0x18008f808`
- `RPCRT4!RpcRevertToSelf` at `0x18008fa93`
- `RPCRT4!RpcRevertToSelf` at `0x18008f808`
- `RPCRT4!RpcRevertToSelf` at `0x18008fa93`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18008f7f0`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18008f7f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f924`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f924`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008fa88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008fa88`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008f976`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008f99d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008f976`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008f99d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18008f9ee`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18008fa4f`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18008f9ee`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18008fa4f`

## pseudocode

```c
void __fastcall FixCorruptFileEx(__int64 a1)
{
  WCHAR *v1; // rbx
  HANDLE CurrentThread; // rax
  void *v3; // rdi
  BOOL v4; // r15d
  WCHAR *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rax
  WCHAR v9; // cx
  unsigned int v10; // r12d
  unsigned int v11; // edi
  unsigned __int16 *v12; // rsi
  HANDLE FileW; // r14
  __int64 v14; // rdi
  char *v15; // rax
  void *v16; // rbx
  void *v17; // r8
  char FileInformation[8]; // [rsp+40h] [rbp-29h] BYREF
  void *DuplicateTokenHandle; // [rsp+48h] [rbp-21h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-19h] BYREF
  wchar_t v21; // [rsp+58h] [rbp-11h]
  __int64 v22; // [rsp+60h] [rbp-9h] BYREF
  wchar_t v23; // [rsp+68h] [rbp-1h]

  if ( a1 )
  {
    v1 = (WCHAR *)(a1 + 52);
    if ( a1 != -52 )
    {
      TokenHandle = (void *)-1LL;
      DuplicateTokenHandle = (void *)-1LL;
      if ( !RpcImpersonateClient(0) )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
        {
          if ( !DuplicateToken(TokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
            DuplicateTokenHandle = (void *)-1LL;
          CloseHandle(TokenHandle);
        }
        RpcRevertToSelf();
      }
      v3 = DuplicateTokenHandle;
      if ( DuplicateTokenHandle == (void *)-1LL )
      {
        v4 = 0;
      }
      else
      {
        if ( !(unsigned int)IsPhoneBookPathValidEx(DuplicateTokenHandle, v1) )
        {
          CloseHandle(v3);
          return;
        }
        CloseHandle(v3);
        v4 = RpcImpersonateClient(0) == 0;
      }
      v5 = v1;
      v6 = 260;
      do
      {
        if ( !*v5 )
          break;
        ++v5;
        --v6;
      }
      while ( v6 );
      v7 = (260 - v6) & -(__int64)(v6 != 0);
      if ( !v6 || !v7 )
        goto LABEL_42;
      v23 = aBad[4];
      v22 = *(_QWORD *)L".bad";
      v21 = aPbk_0[4];
      v8 = (260 - v6) & -(__int64)(v6 != 0);
      TokenHandle = *(void **)L".pbk";
      while ( 1 )
      {
        v9 = v1[v8 - 1];
        if ( v9 == 46 )
          break;
        if ( v9 != 92 && v9 != 47 )
        {
          if ( --v8 )
            continue;
        }
        goto LABEL_42;
      }
      if ( !&v1[v8 - 1] )
        goto LABEL_42;
      if ( wcsicmp_0(&v1[v8 - 1], (const wchar_t *)&TokenHandle) )
        goto LABEL_42;
      v11 = v7 + 5;
      v10 = v11;
      DuplicateTokenHandle = (void *)(2LL * v11);
      v12 = (unsigned __int16 *)LocalAlloc(0x40u, (SIZE_T)DuplicateTokenHandle);
      if ( !v12 )
        goto LABEL_42;
      StringCchPrintfW(v12, v11, L"%s%s", v1, &v22);
      FileW = CreateFileW(v1, 0x10000u, 3u, 0, 3u, 0, 0);
      v14 = (__int64)CreateFileW(v12, 0x10000u, 3u, 0, 3u, 0, 0);
      if ( FileW != (HANDLE)-1LL && !(unsigned int)IsFileNotSymlink(FileW, v1) )
      {
        if ( v14 != -1 )
        {
          if ( (unsigned int)IsFileNotSymlink((HANDLE)v14, v12) )
          {
LABEL_38:
            CloseHandle((HANDLE)v14);
LABEL_39:
            if ( FileW == (HANDLE)-1LL )
            {
LABEL_41:
              LocalFree(v12);
LABEL_42:
              if ( v4 )
                RpcRevertToSelf();
              return;
            }
LABEL_40:
            CloseHandle(FileW);
            goto LABEL_41;
          }
          FileInformation[0] = 1;
          SetFileInformationByHandle((HANDLE)v14, FileDispositionInfo, FileInformation, 1u);
          CloseHandle((HANDLE)v14);
          v14 = -1;
        }
        v15 = (char *)calloc(1u, 2 * v10 + 22);
        v16 = v15;
        if ( !v15 )
          goto LABEL_40;
        v17 = DuplicateTokenHandle;
        *((_DWORD *)v15 + 4) = 2 * v10;
        *v15 = 0;
        *((_QWORD *)v15 + 1) = 0;
        memcpy_0(v15 + 20, v12, (size_t)v17);
        if ( !SetFileInformationByHandle(FileW, FileRenameInfo, v16, 2 * v10 + 22) )
          GetLastError();
        free_0(v16);
      }
      if ( v14 == -1 )
        goto LABEL_39;
      goto LABEL_38;
    }
  }
}

```

## disassembly

```asm
0x18008f770  test    rcx, rcx
0x18008f773  jz      locret_18008FAB8
0x18008f779  push    rbp
0x18008f77a  push    rbx
0x18008f77b  push    rsi
0x18008f77c  push    rdi
0x18008f77d  push    r12
0x18008f77f  push    r13
0x18008f781  push    r14
0x18008f783  push    r15
0x18008f785  lea     rbp, [rsp-1Fh]
0x18008f78a  sub     rsp, 88h
0x18008f791  mov     rax, cs:__security_cookie
0x18008f798  xor     rax, rsp
0x18008f79b  mov     [rbp+57h+var_50], rax
0x18008f79f  xor     r13d, r13d
0x18008f7a2  lea     rbx, [rcx+34h]
0x18008f7a6  test    rbx, rbx
0x18008f7a9  jz      loc_18008FA99
0x18008f7af  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008f7b3  xor     ecx, ecx; BindingHandle
0x18008f7b5  mov     [rbp+57h+TokenHandle], rsi
0x18008f7b9  mov     [rbp+57h+DuplicateTokenHandle], rsi
0x18008f7bd  call    cs:__imp_RpcImpersonateClient
0x18008f7c3  test    eax, eax
0x18008f7c5  jnz     short loc_18008F80E
0x18008f7c7  call    cs:__imp_GetCurrentThread
0x18008f7cd  mov     rcx, rax; ThreadHandle
0x18008f7d0  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18008f7d4  lea     edx, [rsi+0Fh]; DesiredAccess
0x18008f7d7  lea     r8d, [r13+1]; OpenAsSelf
0x18008f7db  call    cs:__imp_OpenThreadToken
0x18008f7e1  test    eax, eax
0x18008f7e3  jz      short loc_18008F808
0x18008f7e5  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x18008f7e9  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18008f7ed  lea     edx, [rsi+3]; ImpersonationLevel
0x18008f7f0  call    cs:__imp_DuplicateToken
0x18008f7f6  test    eax, eax
0x18008f7f8  jnz     short loc_18008F7FE
0x18008f7fa  mov     [rbp+57h+DuplicateTokenHandle], rsi
0x18008f7fe  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18008f802  call    cs:__imp_CloseHandle
0x18008f808  call    cs:__imp_RpcRevertToSelf
0x18008f80e  mov     rdi, [rbp+57h+DuplicateTokenHandle]
0x18008f812  cmp     rdi, rsi
0x18008f815  jz      short loc_18008F84D
0x18008f817  mov     rdx, rbx; lpString2
0x18008f81a  mov     rcx, rdi; hToken
0x18008f81d  call    IsPhoneBookPathValidEx
0x18008f822  mov     rcx, rdi; hObject
0x18008f825  test    eax, eax
0x18008f827  jnz     short loc_18008F834
0x18008f829  call    cs:__imp_CloseHandle
0x18008f82f  jmp     loc_18008FA99
0x18008f834  call    cs:__imp_CloseHandle
0x18008f83a  xor     ecx, ecx; BindingHandle
0x18008f83c  call    cs:__imp_RpcImpersonateClient
0x18008f842  test    eax, eax
0x18008f844  mov     r15d, r13d
0x18008f847  setz    r15b
0x18008f84b  jmp     short loc_18008F850
0x18008f84d  mov     r15d, r13d
0x18008f850  mov     edx, 104h
0x18008f855  mov     rax, rbx
0x18008f858  mov     ecx, edx
0x18008f85a  cmp     [rax], r13w
0x18008f85e  jz      short loc_18008F86A
0x18008f860  add     rax, 2
0x18008f864  sub     rcx, 1
0x18008f868  jnz     short loc_18008F85A
0x18008f86a  sub     rdx, rcx
0x18008f86d  mov     rax, rcx
0x18008f870  neg     rax
0x18008f873  sbb     rdi, rdi
0x18008f876  and     rdi, rdx
0x18008f879  test    rcx, rcx
0x18008f87c  jz      loc_18008FA8E
0x18008f882  test    rdi, rdi
0x18008f885  jz      loc_18008FA8E
0x18008f88b  movzx   eax, word ptr cs:aBad+8; ""
0x18008f892  movsd   xmm0, qword ptr cs:aBad; ".bad"
0x18008f89a  mov     [rbp+57h+var_58], ax
0x18008f89e  movzx   eax, word ptr cs:aPbk_0+8; ""
0x18008f8a5  movsd   [rbp+57h+var_60], xmm0
0x18008f8aa  movsd   xmm0, qword ptr cs:aPbk_0; ".pbk"
0x18008f8b2  mov     [rbp+57h+var_68], ax
0x18008f8b6  mov     rax, rdi
0x18008f8b9  movsd   [rbp+57h+TokenHandle], xmm0
0x18008f8be  movzx   ecx, word ptr [rbx+rax*2-2]
0x18008f8c3  lea     r8, [rbx-2]
0x18008f8c7  lea     r8, [r8+rax*2]
0x18008f8cb  cmp     cx, 2Eh ; '.'
0x18008f8cf  jz      short loc_18008F8F0
0x18008f8d1  cmp     cx, 5Ch ; '\'
0x18008f8d5  jz      loc_18008FA8E
0x18008f8db  cmp     cx, 2Fh ; '/'
0x18008f8df  jz      loc_18008FA8E
0x18008f8e5  sub     rax, 1
0x18008f8e9  jnz     short loc_18008F8BE
0x18008f8eb  jmp     loc_18008FA8E
0x18008f8f0  test    r8, r8
0x18008f8f3  jz      loc_18008FA8E
0x18008f8f9  lea     rdx, [rbp+57h+TokenHandle]; String2
0x18008f8fd  mov     rcx, r8; String1
0x18008f900  call    _wcsicmp_0
0x18008f905  test    eax, eax
0x18008f907  jnz     loc_18008FA8E
0x18008f90d  lea     r12d, [rdi+5]
0x18008f911  mov     ecx, 40h ; '@'; uFlags
0x18008f916  lea     rax, [r12+r12]
0x18008f91a  mov     edi, r12d
0x18008f91d  mov     rdx, rax; uBytes
0x18008f920  mov     [rbp+57h+DuplicateTokenHandle], rax
0x18008f924  call    cs:__imp_LocalAlloc
0x18008f92a  mov     rsi, rax
0x18008f92d  test    rax, rax
0x18008f930  jz      loc_18008FA8E
0x18008f936  lea     rax, [rbp+57h+var_60]
0x18008f93a  mov     r9, rbx
0x18008f93d  lea     r8, aSS_3; "%s%s"
0x18008f944  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x18008f949  mov     edx, edi; unsigned __int64
0x18008f94b  mov     rcx, rsi; unsigned __int16 *
0x18008f94e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008f953  mov     eax, 3
0x18008f958  mov     [rsp+0C0h+hTemplateFile], r13; hTemplateFile
0x18008f95d  mov     edi, 10000h
0x18008f962  mov     [rsp+0C0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x18008f967  mov     r8d, eax; dwShareMode
0x18008f96a  mov     [rsp+0C0h+dwCreationDisposition], eax; dwCreationDisposition
0x18008f96e  xor     r9d, r9d; lpSecurityAttributes
0x18008f971  mov     edx, edi; dwDesiredAccess
0x18008f973  mov     rcx, rbx; lpFileName
0x18008f976  call    cs:__imp_CreateFileW
0x18008f97c  mov     [rsp+0C0h+hTemplateFile], r13; hTemplateFile
0x18008f981  xor     r9d, r9d; lpSecurityAttributes
0x18008f984  mov     r14, rax
0x18008f987  mov     [rsp+0C0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x18008f98c  mov     eax, 3
0x18008f991  mov     edx, edi; dwDesiredAccess
0x18008f993  mov     r8d, eax; dwShareMode
0x18008f996  mov     [rsp+0C0h+dwCreationDisposition], eax; dwCreationDisposition
0x18008f99a  mov     rcx, rsi; lpFileName
0x18008f99d  call    cs:__imp_CreateFileW
0x18008f9a3  mov     rdi, rax
0x18008f9a6  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18008f9aa  jz      loc_18008FA67
0x18008f9b0  mov     rdx, rbx; String1
0x18008f9b3  mov     rcx, r14; hFile
0x18008f9b6  call    IsFileNotSymlink
0x18008f9bb  test    eax, eax
0x18008f9bd  jnz     loc_18008FA67
0x18008f9c3  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18008f9c7  jz      short loc_18008FA01
0x18008f9c9  mov     rdx, rsi; String1
0x18008f9cc  mov     rcx, rdi; hFile
0x18008f9cf  call    IsFileNotSymlink
0x18008f9d4  test    eax, eax
0x18008f9d6  jnz     loc_18008FA6D
0x18008f9dc  lea     r9d, [rax+1]; dwBufferSize
0x18008f9e0  mov     [rbp+57h+FileInformation], 1
0x18008f9e4  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x18008f9e8  mov     rcx, rdi; hFile
0x18008f9eb  lea     edx, [rax+4]; FileInformationClass
0x18008f9ee  call    cs:__imp_SetFileInformationByHandle
0x18008f9f4  mov     rcx, rdi; hObject
0x18008f9f7  call    cs:__imp_CloseHandle
0x18008f9fd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008fa01  lea     r13d, ds:16h[r12*2]
0x18008fa09  mov     ecx, 1; Count
0x18008fa0e  mov     edx, r13d; Size
0x18008fa11  call    cs:__imp_calloc
0x18008fa17  mov     rbx, rax
0x18008fa1a  test    rax, rax
0x18008fa1d  jz      short loc_18008FA7C
0x18008fa1f  mov     r8, [rbp+57h+DuplicateTokenHandle]; Size
0x18008fa23  lea     ecx, [r12+r12]
0x18008fa27  mov     [rax+10h], ecx
0x18008fa2a  mov     rdx, rsi; Src
0x18008fa2d  lea     rcx, [rax+14h]; void *
0x18008fa31  mov     byte ptr [rax], 0
0x18008fa34  mov     qword ptr [rax+8], 0
0x18008fa3c  call    memcpy_0
0x18008fa41  mov     r9d, r13d; dwBufferSize
0x18008fa44  mov     r8, rbx; lpFileInformation
0x18008fa47  mov     edx, 3; FileInformationClass
0x18008fa4c  mov     rcx, r14; hFile
0x18008fa4f  call    cs:__imp_SetFileInformationByHandle
0x18008fa55  test    eax, eax
0x18008fa57  jnz     short loc_18008FA5F
0x18008fa59  call    cs:__imp_GetLastError
0x18008fa5f  mov     rcx, rbx; Block
0x18008fa62  call    free_0
0x18008fa67  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18008fa6b  jz      short loc_18008FA76
0x18008fa6d  mov     rcx, rdi; hObject
0x18008fa70  call    cs:__imp_CloseHandle
0x18008fa76  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18008fa7a  jz      short loc_18008FA85
0x18008fa7c  mov     rcx, r14; hObject
0x18008fa7f  call    cs:__imp_CloseHandle
0x18008fa85  mov     rcx, rsi; hMem
0x18008fa88  call    cs:__imp_LocalFree
0x18008fa8e  test    r15d, r15d
0x18008fa91  jz      short loc_18008FA99
0x18008fa93  call    cs:__imp_RpcRevertToSelf
0x18008fa99  mov     rcx, [rbp+57h+var_50]
0x18008fa9d  xor     rcx, rsp; StackCookie
0x18008faa0  call    __security_check_cookie
0x18008faa5  add     rsp, 88h
0x18008faac  pop     r15
0x18008faae  pop     r14
0x18008fab0  pop     r13
0x18008fab2  pop     r12
0x18008fab4  pop     rdi
0x18008fab5  pop     rsi
0x18008fab6  pop     rbx
0x18008fab7  pop     rbp
0x18008fab8  retn
```
