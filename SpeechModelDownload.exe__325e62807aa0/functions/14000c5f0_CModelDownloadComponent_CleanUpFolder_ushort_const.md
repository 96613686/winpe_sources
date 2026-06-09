# CModelDownloadComponent::CleanUpFolder(ushort const *)

- ea: `0x14000c5f0`
- end: `0x14000c941`
- name: `?CleanUpFolder@CModelDownloadComponent@@AEAAJPEBG@Z`
- size: `849`
- prototype: `__int64 __fastcall(WCHAR *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000c948`
- `0x14000cd18`

## callees

- `0x140002600`
- `0x1400028d8`
- `0x1400030dc`
- `0x140003540`
- `0x14000985c`
- `0x14000c5f0`
- `0x14000ee60`
- `0x14000f4d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14000c699`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14000c794`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14000c699`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14000c794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c7c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c7c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c846`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c811`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c8f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c811`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c8f9`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x14000c7bd`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x14000c838`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x14000c7bd`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x14000c838`
- `api-ms-win-core-file-l1-1-0!UnlockFile` at `0x14000c802`
- `api-ms-win-core-file-l1-1-0!UnlockFile` at `0x14000c802`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000c81f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000c81f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000c6ba`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000c7a5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000c6ba`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000c7a5`

## string_xrefs

- `0x14000c655`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1833)`
- `0x14000c65c`: `CModelDownloadComponent::CleanUpFolder`
- `0x14000c6ae`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1837)`
- `0x14000c6d0`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1845)`
- `0x14000c6e8`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1850)`
- `0x14000c714`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1857)`
- `0x14000c75a`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1862)`
- `0x14000c8cd`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1871)`
- `0x14000c8b6`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1877)`
- `0x14000c7d7`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1884)`
- `0x14000c888`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1896)`
- `0x14000c871`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1904)`
- `0x14000c89f`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1910)`
- `0x14000c85a`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1917)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::CleanUpFolder(WCHAR *this, const unsigned __int16 *a2)
{
  char *v4; // r15
  unsigned __int16 *v5; // r14
  int ModelFilesRootPathExists; // eax
  unsigned int v7; // ebx
  __int64 v8; // r8
  DWORD FileAttributesW; // eax
  unsigned __int16 *v10; // rax
  unsigned int v11; // r8d
  int v12; // eax
  int v13; // edi
  __int64 v14; // r8
  const WCHAR *v15; // rsi
  DWORD v16; // eax
  signed int LastError; // eax
  char *v18; // rcx
  signed int v19; // eax
  unsigned int i; // edi
  char *v21; // rcx
  unsigned int v23[4]; // [rsp+30h] [rbp-458h] BYREF
  HANDLE hFile[128]; // [rsp+40h] [rbp-448h] BYREF

  memset_0(hFile, 0, sizeof(hFile));
  v4 = (char *)(this + 582);
  v23[0] = 0;
  v5 = 0;
  ModelFilesRootPathExists = CModelDownloadComponent::GetModelFilesRootPathExists(this + 582);
  v7 = ModelFilesRootPathExists;
  if ( ModelFilesRootPathExists >= 0 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&v4[2 * v8] );
    if ( (unsigned int)_o__wcsnicmp(this + 582, a2) )
    {
      v7 = -2147418113;
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::CleanUpFolder",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1837)",
        -2147418113);
    }
    else
    {
      FileAttributesW = GetFileAttributesW(a2);
      if ( FileAttributesW == -1 )
      {
        v7 = -2147024809;
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::CleanUpFolder",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1845)",
          -2147024809);
      }
      else if ( (FileAttributesW & 0x10) != 0 )
      {
        v10 = (unsigned __int16 *)operator new[](0x10500u, (const struct std::nothrow_t *)std::nothrow);
        v5 = v10;
        if ( v10 )
        {
          memset_0(v10, 0, 0x10500u);
          v12 = CModelDownloadComponent::GatherFilesExclusiveMode(
                  (CModelDownloadComponent *)this,
                  a2,
                  v11,
                  hFile,
                  (unsigned __int16 (*const)[261])v5,
                  v23);
          v7 = v12;
          if ( v12 >= 0 )
          {
            v13 = 0;
            if ( v23[0] )
            {
              while ( 1 )
              {
                v14 = -1;
                do
                  ++v14;
                while ( *(_WORD *)&v4[2 * v14] );
                v15 = &v5[261 * v13];
                if ( (unsigned int)_o__wcsnicmp(v4, v15) )
                  break;
                v16 = GetFileAttributesW(v15);
                if ( v16 == -1 )
                {
                  v7 = -2147418113;
                  DoTraceMessage(
                    2,
                    "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                    &NLInternal::s_tracingPrefix,
                    L"CModelDownloadComponent::CleanUpFolder",
                    L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1877)",
                    -2147418113);
                  goto LABEL_38;
                }
                if ( (v16 & 0x10) != 0 )
                {
                  if ( !RemoveDirectoryW(v15) )
                  {
                    LastError = GetLastError();
                    v7 = LastError;
                    if ( LastError < 0 )
                    {
                      DoTraceMessage(
                        2,
                        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                        &NLInternal::s_tracingPrefix,
                        L"CModelDownloadComponent::CleanUpFolder",
                        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1884)",
                        LastError);
                      goto LABEL_38;
                    }
                  }
                }
                else
                {
                  v18 = (char *)hFile[v13];
                  if ( (unsigned __int64)(v18 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
                  {
                    v7 = -2147418113;
                    DoTraceMessage(
                      2,
                      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                      &NLInternal::s_tracingPrefix,
                      L"CModelDownloadComponent::CleanUpFolder",
                      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1910)",
                      -2147418113);
                    goto LABEL_38;
                  }
                  if ( !UnlockFile(v18, 0, 0, 0xFFFFFFFF, 0xFFFFFFFF) )
                  {
                    v7 = -2147418113;
                    DoTraceMessage(
                      2,
                      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                      &NLInternal::s_tracingPrefix,
                      L"CModelDownloadComponent::CleanUpFolder",
                      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1896)",
                      -2147418113);
                    goto LABEL_38;
                  }
                  CloseHandle(hFile[v13]);
                  hFile[v13] = 0;
                  if ( !DeleteFileW(v15) )
                  {
                    v7 = -2147418113;
                    DoTraceMessage(
                      2,
                      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                      &NLInternal::s_tracingPrefix,
                      L"CModelDownloadComponent::CleanUpFolder",
                      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1904)",
                      -2147418113);
                    goto LABEL_38;
                  }
                }
                if ( ++v13 >= v23[0] )
                  goto LABEL_29;
              }
              v7 = -2147418113;
              DoTraceMessage(
                2,
                "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                &NLInternal::s_tracingPrefix,
                L"CModelDownloadComponent::CleanUpFolder",
                L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1871)",
                -2147418113);
            }
            else
            {
LABEL_29:
              if ( RemoveDirectoryW(a2) || (v19 = GetLastError(), v7 = v19, v19 >= 0) )
                v23[0] = 0;
              else
                DoTraceMessage(
                  2,
                  "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                  &NLInternal::s_tracingPrefix,
                  L"CModelDownloadComponent::CleanUpFolder",
                  L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1917)",
                  v19);
            }
          }
          else
          {
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              &NLInternal::s_tracingPrefix,
              L"CModelDownloadComponent::CleanUpFolder",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1862)",
              v12);
          }
        }
        else
        {
          v7 = -2147024882;
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            &NLInternal::s_tracingPrefix,
            L"CModelDownloadComponent::CleanUpFolder",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1857)",
            -2147024882);
        }
      }
      else
      {
        v7 = -2147024809;
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::CleanUpFolder",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1850)",
          -2147024809);
      }
    }
  }
  else
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::CleanUpFolder",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1833)",
      ModelFilesRootPathExists);
  }
LABEL_38:
  for ( i = 0; i < v23[0]; ++i )
  {
    v21 = (char *)hFile[i];
    if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v21);
  }
  if ( v5 )
    operator delete(v5);
  return v7;
}

```

## disassembly

```asm
0x14000c5f0  mov     [rsp+arg_10], rbx
0x14000c5f5  push    rbp
0x14000c5f6  push    rsi
0x14000c5f7  push    rdi
0x14000c5f8  push    r12
0x14000c5fa  push    r13
0x14000c5fc  push    r14
0x14000c5fe  push    r15
0x14000c600  sub     rsp, 450h
0x14000c607  mov     rax, cs:__security_cookie
0x14000c60e  xor     rax, rsp
0x14000c611  mov     [rsp+488h+var_48], rax
0x14000c619  mov     r12, rdx
0x14000c61c  mov     rdi, rcx
0x14000c61f  xor     edx, edx; Val
0x14000c621  lea     rcx, [rsp+488h+hFile]; void *
0x14000c626  mov     r8d, 400h; Size
0x14000c62c  call    memset_0
0x14000c631  xor     r13d, r13d
0x14000c634  lea     r15, [rdi+48Ch]
0x14000c63b  mov     rcx, r15; lpDst
0x14000c63e  mov     [rsp+488h+var_458], r13d
0x14000c643  mov     r14d, r13d
0x14000c646  call    ?GetModelFilesRootPathExists@CModelDownloadComponent@@CAJPEAG@Z; CModelDownloadComponent::GetModelFilesRootPathExists(ushort *)
0x14000c64b  mov     ebx, eax
0x14000c64d  test    eax, eax
0x14000c64f  jns     short loc_14000C685
0x14000c651  mov     dword ptr [rsp+488h+var_460], eax
0x14000c655  lea     rax, aOnecoreuapEndu_52; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c65c  lea     r9, aCmodeldownload_11; "CModelDownloadComponent::CleanUpFolder"
0x14000c663  mov     qword ptr [rsp+488h+nNumberOfBytesToUnlockHigh], rax
0x14000c668  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000c66f  mov     ecx, 2; int
0x14000c674  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000c67b  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000c680  jmp     loc_14000C8DE
0x14000c685  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000c689  inc     r8
0x14000c68c  cmp     [r15+r8*2], r13w
0x14000c691  jnz     short loc_14000C689
0x14000c693  mov     rdx, r12
0x14000c696  mov     rcx, r15
0x14000c699  call    cs:__imp__o__wcsnicmp
0x14000c69f  test    eax, eax
0x14000c6a1  jz      short loc_14000C6B7
0x14000c6a3  mov     eax, 8000FFFFh
0x14000c6a8  mov     ebx, eax
0x14000c6aa  mov     dword ptr [rsp+488h+var_460], eax
0x14000c6ae  lea     rax, aOnecoreuapEndu_3; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c6b5  jmp     short loc_14000C65C
0x14000c6b7  mov     rcx, r12; lpFileName
0x14000c6ba  call    cs:__imp_GetFileAttributesW
0x14000c6c0  cmp     eax, 0FFFFFFFFh
0x14000c6c3  jnz     short loc_14000C6D9
0x14000c6c5  mov     eax, 80070057h
0x14000c6ca  mov     ebx, eax
0x14000c6cc  mov     dword ptr [rsp+488h+var_460], eax
0x14000c6d0  lea     rax, aOnecoreuapEndu_108; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c6d7  jmp     short loc_14000C65C
0x14000c6d9  test    al, 10h
0x14000c6db  jnz     short loc_14000C6F4
0x14000c6dd  mov     eax, 80070057h
0x14000c6e2  mov     ebx, eax
0x14000c6e4  mov     dword ptr [rsp+488h+var_460], eax
0x14000c6e8  lea     rax, aOnecoreuapEndu_171; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c6ef  jmp     loc_14000C65C
0x14000c6f4  mov     ebx, 10500h
0x14000c6f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c700  mov     ecx, ebx; unsigned __int64
0x14000c702  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000c707  mov     r14, rax
0x14000c70a  test    rax, rax
0x14000c70d  jnz     short loc_14000C724
0x14000c70f  mov     ebx, 8007000Eh
0x14000c714  lea     rax, aOnecoreuapEndu_50; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c71b  mov     dword ptr [rsp+488h+var_460], ebx
0x14000c71f  jmp     loc_14000C65C
0x14000c724  mov     r8, rbx; Size
0x14000c727  xor     edx, edx; Val
0x14000c729  mov     rcx, r14; void *
0x14000c72c  call    memset_0
0x14000c731  lea     rax, [rsp+488h+var_458]
0x14000c736  mov     rdx, r12; unsigned __int16 *
0x14000c739  mov     [rsp+488h+var_460], rax; unsigned int *
0x14000c73e  lea     r9, [rsp+488h+hFile]; void **
0x14000c743  mov     rcx, rdi; this
0x14000c746  mov     qword ptr [rsp+488h+nNumberOfBytesToUnlockHigh], r14; unsigned __int16 (*)[261]
0x14000c74b  call    ?GatherFilesExclusiveMode@CModelDownloadComponent@@AEAAJPEBGKPEAPEAXQEAY0BAF@GPEAK@Z; CModelDownloadComponent::GatherFilesExclusiveMode(ushort const *,ulong,void * *,ushort (* const)[261],ulong *)
0x14000c750  mov     ebx, eax
0x14000c752  test    eax, eax
0x14000c754  jns     short loc_14000C766
0x14000c756  mov     dword ptr [rsp+488h+var_460], eax
0x14000c75a  lea     rax, aOnecoreuapEndu_152; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c761  jmp     loc_14000C65C
0x14000c766  mov     edi, r13d
0x14000c769  cmp     [rsp+488h+var_458], r13d
0x14000c76e  jbe     loc_14000C835
0x14000c774  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000c778  inc     r8
0x14000c77b  cmp     [r15+r8*2], r13w
0x14000c780  jnz     short loc_14000C778
0x14000c782  mov     ebp, edi
0x14000c784  mov     rcx, r15
0x14000c787  imul    rsi, rbp, 20Ah
0x14000c78e  add     rsi, r14
0x14000c791  mov     rdx, rsi
0x14000c794  call    cs:__imp__o__wcsnicmp
0x14000c79a  test    eax, eax
0x14000c79c  jnz     loc_14000C8C2
0x14000c7a2  mov     rcx, rsi; lpFileName
0x14000c7a5  call    cs:__imp_GetFileAttributesW
0x14000c7ab  or      edx, 0FFFFFFFFh
0x14000c7ae  cmp     eax, edx
0x14000c7b0  jz      loc_14000C8AB
0x14000c7b6  test    al, 10h
0x14000c7b8  jz      short loc_14000C7E3
0x14000c7ba  mov     rcx, rsi; lpPathName
0x14000c7bd  call    cs:__imp_RemoveDirectoryW
0x14000c7c3  test    eax, eax
0x14000c7c5  jnz     short loc_14000C829
0x14000c7c7  call    cs:__imp_GetLastError
0x14000c7cd  mov     ebx, eax
0x14000c7cf  test    eax, eax
0x14000c7d1  jns     short loc_14000C829
0x14000c7d3  mov     dword ptr [rsp+488h+var_460], eax
0x14000c7d7  lea     rax, aOnecoreuapEndu_173; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c7de  jmp     loc_14000C65C
0x14000c7e3  mov     rcx, [rsp+rbp*8+488h+hFile]; hFile
0x14000c7e8  lea     rax, [rcx-1]
0x14000c7ec  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000c7f0  ja      loc_14000C894
0x14000c7f6  mov     [rsp+488h+nNumberOfBytesToUnlockHigh], edx; nNumberOfBytesToUnlockHigh
0x14000c7fa  mov     r9d, edx; nNumberOfBytesToUnlockLow
0x14000c7fd  xor     edx, edx; dwFileOffsetLow
0x14000c7ff  xor     r8d, r8d; dwFileOffsetHigh
0x14000c802  call    cs:__imp_UnlockFile
0x14000c808  test    eax, eax
0x14000c80a  jz      short loc_14000C87D
0x14000c80c  mov     rcx, [rsp+rbp*8+488h+hFile]; hObject
0x14000c811  call    cs:__imp_CloseHandle
0x14000c817  mov     rcx, rsi; lpFileName
0x14000c81a  mov     [rsp+rbp*8+488h+hFile], r13
0x14000c81f  call    cs:__imp_DeleteFileW
0x14000c825  test    eax, eax
0x14000c827  jz      short loc_14000C866
0x14000c829  inc     edi
0x14000c82b  cmp     edi, [rsp+488h+var_458]
0x14000c82f  jb      loc_14000C774
0x14000c835  mov     rcx, r12; lpPathName
0x14000c838  call    cs:__imp_RemoveDirectoryW
0x14000c83e  test    eax, eax
0x14000c840  jnz     loc_14000C8D9
0x14000c846  call    cs:__imp_GetLastError
0x14000c84c  mov     ebx, eax
0x14000c84e  test    eax, eax
0x14000c850  jns     loc_14000C8D9
0x14000c856  mov     dword ptr [rsp+488h+var_460], eax
0x14000c85a  lea     rax, aOnecoreuapEndu_93; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c861  jmp     loc_14000C65C
0x14000c866  mov     eax, 8000FFFFh
0x14000c86b  mov     ebx, eax
0x14000c86d  mov     dword ptr [rsp+488h+var_460], eax
0x14000c871  lea     rax, aOnecoreuapEndu_165; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c878  jmp     loc_14000C65C
0x14000c87d  mov     eax, 8000FFFFh
0x14000c882  mov     ebx, eax
0x14000c884  mov     dword ptr [rsp+488h+var_460], eax
0x14000c888  lea     rax, aOnecoreuapEndu_65; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c88f  jmp     loc_14000C65C
0x14000c894  mov     eax, 8000FFFFh
0x14000c899  mov     ebx, eax
0x14000c89b  mov     dword ptr [rsp+488h+var_460], eax
0x14000c89f  lea     rax, aOnecoreuapEndu_64; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c8a6  jmp     loc_14000C65C
0x14000c8ab  mov     eax, 8000FFFFh
0x14000c8b0  mov     ebx, eax
0x14000c8b2  mov     dword ptr [rsp+488h+var_460], eax
0x14000c8b6  lea     rax, aOnecoreuapEndu_166; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c8bd  jmp     loc_14000C65C
0x14000c8c2  mov     eax, 8000FFFFh
0x14000c8c7  mov     ebx, eax
0x14000c8c9  mov     dword ptr [rsp+488h+var_460], eax
0x14000c8cd  lea     rax, aOnecoreuapEndu_39; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c8d4  jmp     loc_14000C65C
0x14000c8d9  mov     [rsp+488h+var_458], r13d
0x14000c8de  mov     edi, r13d
0x14000c8e1  cmp     [rsp+488h+var_458], r13d
0x14000c8e6  jbe     short loc_14000C907
0x14000c8e8  mov     eax, edi
0x14000c8ea  mov     rcx, [rsp+rax*8+488h+hFile]; hObject
0x14000c8ef  lea     rax, [rcx-1]
0x14000c8f3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000c8f7  ja      short loc_14000C8FF
0x14000c8f9  call    cs:__imp_CloseHandle
0x14000c8ff  inc     edi
0x14000c901  cmp     edi, [rsp+488h+var_458]
0x14000c905  jb      short loc_14000C8E8
0x14000c907  test    r14, r14
0x14000c90a  jz      short loc_14000C914
0x14000c90c  mov     rcx, r14; Block
0x14000c90f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c914  mov     eax, ebx
0x14000c916  mov     rcx, [rsp+488h+var_48]
0x14000c91e  xor     rcx, rsp; StackCookie
0x14000c921  call    __security_check_cookie
0x14000c926  mov     rbx, [rsp+488h+arg_10]
0x14000c92e  add     rsp, 450h
0x14000c935  pop     r15
0x14000c937  pop     r14
0x14000c939  pop     r13
0x14000c93b  pop     r12
0x14000c93d  pop     rdi
0x14000c93e  pop     rsi
0x14000c93f  pop     rbp
0x14000c940  retn
```
