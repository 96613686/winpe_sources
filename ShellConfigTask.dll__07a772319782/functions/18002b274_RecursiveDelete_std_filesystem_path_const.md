# RecursiveDelete(std::filesystem::path const &)

- ea: `0x18002b274`
- end: `0x18002b7d8`
- name: `?RecursiveDelete@@YAJAEBVpath@filesystem@std@@@Z`
- size: `1380`
- prototype: `__int64 __fastcall(const struct std::filesystem::path *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x18002b274`
- `0x18002eb00`
- `0x18002ebe0`

## callees

- `0x180002590`
- `0x18000aaf4`
- `0x18000ab14`
- `0x18000f29c`
- `0x180013890`
- `0x18002062c`
- `0x180025280`
- `0x18002869c`
- `0x180029348`
- `0x18002a744`
- `0x18002a788`
- `0x18002b274`
- `0x18002b840`
- `0x18002dccc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b3a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b427`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b6cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b787`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b799`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b3a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b427`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b6cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b787`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b799`
- `ntdll!NtQueryDirectoryFile` at `0x18002b3ef`
- `ntdll!NtQueryDirectoryFile` at `0x18002b742`
- `ntdll!NtQueryDirectoryFile` at `0x18002b3ef`
- `ntdll!NtQueryDirectoryFile` at `0x18002b742`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b2d6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b620`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b2d6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b620`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002b44a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002b673`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002b44a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002b673`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18002b367`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18002b367`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18002b418`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18002b778`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18002b418`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18002b778`

## string_xrefs

- `0x18002b2ed`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`
- `0x18002b32e`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`
- `0x18002b38d`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`
- `0x18002b5cc`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
__int64 __fastcall RecursiveDelete(const struct std::filesystem::path *a1)
{
  const struct std::filesystem::path *v1; // r12
  HANDLE FileW; // rax
  const char *v3; // r9
  void *v4; // rbx
  int matched; // eax
  unsigned int *v7; // rax
  unsigned int *v8; // r15
  NTSTATUS v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  NTSTATUS v12; // edi
  unsigned int v13; // edi
  void *v14; // rdx
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int *v17; // rdi
  wchar_t **v18; // rdx
  size_t v19; // r8
  const wchar_t *v20; // rcx
  wchar_t *v21; // rax
  unsigned __int64 v22; // rdx
  wchar_t **v23; // rcx
  int v24; // eax
  char *v25; // rsi
  const WCHAR *v26; // rcx
  char *v27; // rax
  unsigned int v28; // r8d
  const char *v29; // r9
  void *v30; // rdx
  unsigned int v31; // r8d
  unsigned int v32; // r8d
  const char *v33; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-108h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-108h]
  bool v36; // [rsp+60h] [rbp-C8h] BYREF
  char FileInformation[3]; // [rsp+61h] [rbp-C7h] BYREF
  int v38; // [rsp+64h] [rbp-C4h]
  char *v39; // [rsp+68h] [rbp-C0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-B8h] BYREF
  HANDLE v41; // [rsp+80h] [rbp-A8h]
  unsigned int *v42; // [rsp+88h] [rbp-A0h]
  wchar_t *S1[2]; // [rsp+90h] [rbp-98h] BYREF
  size_t N; // [rsp+A0h] [rbp-88h]
  unsigned __int64 v45; // [rsp+A8h] [rbp-80h]
  __int128 v46; // [rsp+B0h] [rbp-78h] BYREF
  __int64 v47; // [rsp+C0h] [rbp-68h]
  __int64 v48; // [rsp+C8h] [rbp-60h]
  LPCWSTR lpFileName[4]; // [rsp+D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v1 = a1;
  v38 = 0;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const struct std::filesystem::path **)a1;
  FileW = CreateFileW((LPCWSTR)a1, 0x110081u, 7u, 0, 3u, 0x2000000u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x51,
             (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
             v3);
  v41 = FileW;
  v36 = 0;
  matched = DoesExpectedPathMatchFinalPath(FileW, v1, &v36);
  if ( matched < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
      (const char *)(unsigned int)matched,
      dwCreationDisposition);
LABEL_57:
    if ( v4 )
      CloseHandle(v4);
    return 2147942406LL;
  }
  if ( !v36 )
    goto LABEL_57;
  v7 = (unsigned int *)VirtualAlloc(0, 0x10000u, 0x1000u, 4u);
  v8 = v7;
  v42 = v7;
  if ( !v7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
    if ( v4 )
      CloseHandle(v4);
    return 2147942414LL;
  }
  IoStatusBlock = 0;
  v9 = NtQueryDirectoryFile(v4, 0, 0, 0, &IoStatusBlock, v7, 0x10000u, FileDirectoryInformation, 0, 0, 1u);
  v12 = v9;
  if ( v9 < 0 )
  {
    v13 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            v10,
            v11,
            (const char *)(unsigned int)v9,
            dwCreationDispositiona);
    VirtualFree(v8, 0, 0x8000u);
    if ( v4 )
      CloseHandle(v4);
    return v13;
  }
  FileInformation[0] = 1;
  if ( !SetFileInformationByHandle(v4, FileDispositionInfo, FileInformation, 1u) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x83, v15, v16);
LABEL_18:
  if ( v12 >= 0 )
  {
    v17 = v8;
    while ( 1 )
    {
      if ( !v17 )
      {
        v12 = NtQueryDirectoryFile(v4, 0, 0, 0, &IoStatusBlock, v8, 0x10000u, FileDirectoryInformation, 0, 0, 0);
        goto LABEL_18;
      }
      *(_OWORD *)S1 = 0;
      N = 0;
      v45 = 0;
      std::wstring::_Construct<1,unsigned short const *>(S1, v17 + 16, (unsigned __int64)v17[15] >> 1);
      v18 = S1;
      if ( v45 > 7 )
        v18 = (wchar_t **)S1[0];
      v46 = 0;
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v46, v18, N);
      std::filesystem::operator/(lpFileName, v1, (std::filesystem *)&v46);
      std::wstring::~wstring(&v46);
      v19 = N;
      v20 = (const wchar_t *)S1;
      v21 = S1[0];
      v22 = v45;
      if ( v45 > 7 )
        v20 = S1[0];
      if ( N == 1 )
      {
        if ( !wmemcmp(v20, L".", 1u) )
          goto LABEL_46;
        v22 = v45;
        v19 = N;
        v21 = S1[0];
      }
      v23 = S1;
      if ( v22 > 7 )
        v23 = (wchar_t **)v21;
      if ( v19 != 2 || wmemcmp((const wchar_t *)v23, L"..", 2u) )
      {
        if ( (v17[14] & 0x10) != 0 )
        {
          v24 = RecursiveDelete((const struct std::filesystem::path *)lpFileName);
          if ( v24 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x93,
              (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
              (const char *)(unsigned int)v24,
              dwCreationDispositiona);
        }
        else
        {
          v25 = 0;
          v26 = (const WCHAR *)lpFileName;
          if ( lpFileName[3] > (LPCWSTR)7 )
            v26 = lpFileName[0];
          v27 = (char *)CreateFileW(v26, 0x110000u, 7u, 0, 3u, 0x80u, 0);
          if ( v27 == (char *)-1LL )
          {
            wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xBC, v28, v29);
          }
          else
          {
            v25 = v27;
            v39 = v27;
            v36 = 0;
            if ( (int)DoesExpectedPathMatchFinalPath(v27, (const struct std::filesystem::path *)lpFileName, &v36) >= 0
              && v36 )
            {
              v36 = 1;
              if ( !SetFileInformationByHandle(v25, FileDispositionInfo, &v36, 1u) )
                wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xB3, v32, v33);
            }
            else
            {
              wil::details::in1diag3::Log_Hr(retaddr, v30, v31, (const char *)0x800700A1LL, dwCreationDispositiona);
            }
          }
          if ( (unsigned __int64)(v25 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v25);
        }
      }
LABEL_46:
      v38 |= 3u;
      std::wstring::~wstring(lpFileName);
      std::wstring::~wstring(S1);
      if ( *v17 )
        v17 = (unsigned int *)((char *)v17 + *v17);
      else
        v17 = 0;
    }
  }
  if ( v12 != -2147483642 )
    wil::details::in1diag3::Log_NtStatus(retaddr, v14, v15, (const char *)(unsigned int)v12, dwCreationDispositiona);
  if ( v8 )
    VirtualFree(v8, 0, 0x8000u);
  if ( v4 )
    CloseHandle(v4);
  return 0;
}

```

## disassembly

```asm
0x18002b274  mov     [rsp+arg_8], rbx
0x18002b279  mov     [rsp+arg_10], rsi
0x18002b27e  push    rdi
0x18002b27f  push    r12
0x18002b281  push    r13
0x18002b283  push    r14
0x18002b285  push    r15
0x18002b287  sub     rsp, 100h
0x18002b28e  mov     rax, cs:__security_cookie
0x18002b295  xor     rax, rsp
0x18002b298  mov     [rsp+128h+var_38], rax
0x18002b2a0  mov     r12, rcx
0x18002b2a3  xor     r13d, r13d
0x18002b2a6  mov     [rsp+128h+var_C4], r13d
0x18002b2ab  cmp     qword ptr [rcx+18h], 7
0x18002b2b0  jbe     short loc_18002B2B5
0x18002b2b2  mov     rcx, [rcx]; lpFileName
0x18002b2b5  mov     [rsp+128h+hTemplateFile], r13; hTemplateFile
0x18002b2ba  mov     [rsp+128h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002b2c2  mov     [rsp+128h+dwCreationDisposition], 3; int
0x18002b2ca  xor     r9d, r9d; lpSecurityAttributes
0x18002b2cd  mov     edx, 110081h; dwDesiredAccess
0x18002b2d2  lea     r8d, [r9+7]; dwShareMode
0x18002b2d6  call    cs:__imp_CreateFileW
0x18002b2dc  mov     rbx, rax
0x18002b2df  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b2e3  jnz     short loc_18002B302
0x18002b2e5  mov     rcx, [rsp+128h]; this
0x18002b2ed  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002b2f4  lea     edx, [rax+52h]; void *
0x18002b2f7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002b2fc  nop
0x18002b2fd  jmp     loc_18002B7AA
0x18002b302  mov     [rsp+128h+var_A8], rbx
0x18002b30a  mov     [rsp+128h+var_C8], r13b
0x18002b30f  lea     r8, [rsp+128h+var_C8]; bool *
0x18002b314  mov     rdx, r12; struct std::filesystem::path *
0x18002b317  mov     rcx, rbx; void *
0x18002b31a  call    ?DoesExpectedPathMatchFinalPath@@YAJPEAXAEBVpath@filesystem@std@@PEA_N@Z; DoesExpectedPathMatchFinalPath(void *,std::filesystem::path const &,bool *)
0x18002b31f  mov     rcx, [rsp+128h]; this
0x18002b327  test    eax, eax
0x18002b329  jns     short loc_18002B344
0x18002b32b  mov     r9d, eax; char *
0x18002b32e  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002b335  mov     edx, 56h ; 'V'; void *
0x18002b33a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002b33f  jmp     loc_18002B791
0x18002b344  cmp     [rsp+128h+var_C8], r13b
0x18002b349  jz      loc_18002B791
0x18002b34f  mov     r14d, 4
0x18002b355  mov     r9d, r14d; flProtect
0x18002b358  mov     esi, 10000h
0x18002b35d  mov     r8d, 1000h; flAllocationType
0x18002b363  mov     edx, esi; dwSize
0x18002b365  xor     ecx, ecx; lpAddress
0x18002b367  call    cs:__imp_VirtualAlloc
0x18002b36d  mov     r15, rax
0x18002b370  mov     [rsp+128h+var_A0], rax
0x18002b378  test    rax, rax
0x18002b37b  jnz     short loc_18002B3B2
0x18002b37d  mov     rcx, [rsp+128h]; this
0x18002b385  mov     edi, 8007000Eh
0x18002b38a  mov     r9d, edi; char *
0x18002b38d  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002b394  lea     edx, [rax+6Ah]; void *
0x18002b397  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b39c  nop
0x18002b39d  test    rbx, rbx
0x18002b3a0  jz      short loc_18002B3AB
0x18002b3a2  mov     rcx, rbx; hObject
0x18002b3a5  call    cs:__imp_CloseHandle
0x18002b3ab  mov     eax, edi
0x18002b3ad  jmp     loc_18002B7AA
0x18002b3b2  xorps   xmm0, xmm0
0x18002b3b5  movups  xmmword ptr [rsp+128h+IoStatusBlock], xmm0
0x18002b3ba  mov     [rsp+128h+RestartScan], 1; RestartScan
0x18002b3bf  mov     [rsp+128h+FileName], r13; FileName
0x18002b3c4  mov     [rsp+128h+ReturnSingleEntry], r13b; ReturnSingleEntry
0x18002b3c9  mov     [rsp+128h+FileInformationClass], 1; FileInformationClass
0x18002b3d1  mov     dword ptr [rsp+128h+hTemplateFile], esi; Length
0x18002b3d5  mov     qword ptr [rsp+128h+dwFlagsAndAttributes], r15; FileInformation
0x18002b3da  lea     rax, [rsp+128h+IoStatusBlock]
0x18002b3df  mov     qword ptr [rsp+128h+dwCreationDisposition], rax; int
0x18002b3e4  xor     r9d, r9d; ApcContext
0x18002b3e7  xor     r8d, r8d; ApcRoutine
0x18002b3ea  xor     edx, edx; Event
0x18002b3ec  mov     rcx, rbx; FileHandle
0x18002b3ef  call    cs:__imp_NtQueryDirectoryFile
0x18002b3f5  mov     edi, eax
0x18002b3f7  test    eax, eax
0x18002b3f9  jns     short loc_18002B434
0x18002b3fb  mov     rcx, [rsp+128h]; this
0x18002b403  mov     r9d, eax; char *
0x18002b406  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002b40b  mov     edi, eax
0x18002b40d  xor     edx, edx; dwSize
0x18002b40f  mov     r8d, 8000h; dwFreeType
0x18002b415  mov     rcx, r15; lpAddress
0x18002b418  call    cs:__imp_VirtualFree
0x18002b41e  nop
0x18002b41f  test    rbx, rbx
0x18002b422  jz      short loc_18002B42D
0x18002b424  mov     rcx, rbx; hObject
0x18002b427  call    cs:__imp_CloseHandle
0x18002b42d  mov     eax, edi
0x18002b42f  jmp     loc_18002B7AA
0x18002b434  mov     [rsp+128h+FileInformation], 1
0x18002b439  mov     r9d, 1; dwBufferSize
0x18002b43f  lea     r8, [rsp+128h+FileInformation]; lpFileInformation
0x18002b444  mov     edx, r14d; FileInformationClass
0x18002b447  mov     rcx, rbx; hFile
0x18002b44a  call    cs:__imp_SetFileInformationByHandle
0x18002b450  mov     rcx, [rsp+128h]; this
0x18002b458  test    eax, eax
0x18002b45a  jnz     short loc_18002B466
0x18002b45c  mov     edx, 83h; void *
0x18002b461  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002b466  test    edi, edi
0x18002b468  js      loc_18002B74F
0x18002b46e  mov     rdi, r15
0x18002b471  mov     r14, r13
0x18002b474  cmp     rdi, r14
0x18002b477  jz      loc_18002B709
0x18002b47d  xorps   xmm0, xmm0
0x18002b480  movups  xmmword ptr [rsp+128h+S1], xmm0
0x18002b488  mov     [rsp+128h+N], r13
0x18002b490  mov     [rsp+128h+var_80], r13
0x18002b498  mov     r8d, [rdi+3Ch]
0x18002b49c  shr     r8, 1
0x18002b49f  lea     rdx, [rdi+40h]
0x18002b4a3  lea     rcx, [rsp+128h+S1]
0x18002b4ab  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002b4b0  nop
0x18002b4b1  lea     rdx, [rsp+128h+S1]
0x18002b4b9  cmp     [rsp+128h+var_80], 7
0x18002b4c2  cmova   rdx, [rsp+128h+S1]
0x18002b4cb  xorps   xmm0, xmm0
0x18002b4ce  movups  [rsp+128h+var_78], xmm0
0x18002b4d6  mov     [rsp+128h+var_68], r13
0x18002b4de  mov     [rsp+128h+var_60], r13
0x18002b4e6  mov     r8, [rsp+128h+N]
0x18002b4ee  lea     rcx, [rsp+128h+var_78]
0x18002b4f6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002b4fb  nop
0x18002b4fc  lea     r8, [rsp+128h+var_78]; this
0x18002b504  mov     rdx, r12; struct std::filesystem::path *
0x18002b507  lea     rcx, [rsp+128h+lpFileName]; Src
0x18002b50f  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18002b514  nop
0x18002b515  lea     rcx, [rsp+128h+var_78]
0x18002b51d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b522  mov     r8, [rsp+128h+N]; N
0x18002b52a  lea     rcx, [rsp+128h+S1]
0x18002b532  mov     rax, [rsp+128h+S1]
0x18002b53a  mov     rdx, [rsp+128h+var_80]
0x18002b542  cmp     rdx, 7
0x18002b546  cmova   rcx, rax; S1
0x18002b54a  cmp     r8, 1
0x18002b54e  jnz     short loc_18002B57C
0x18002b550  lea     rdx, S2; "."
0x18002b557  call    wmemcmp
0x18002b55c  test    eax, eax
0x18002b55e  jz      loc_18002B6D2
0x18002b564  mov     rdx, [rsp+128h+var_80]
0x18002b56c  mov     r8, [rsp+128h+N]; N
0x18002b574  mov     rax, [rsp+128h+S1]
0x18002b57c  lea     rcx, [rsp+128h+S1]
0x18002b584  cmp     rdx, 7
0x18002b588  cmova   rcx, rax; S1
0x18002b58c  cmp     r8, 2
0x18002b590  jnz     short loc_18002B5A6
0x18002b592  lea     rdx, asc_180037770; ".."
0x18002b599  call    wmemcmp
0x18002b59e  test    eax, eax
0x18002b5a0  jz      loc_18002B6D2
0x18002b5a6  test    byte ptr [rdi+38h], 10h
0x18002b5aa  jz      short loc_18002B5E2
0x18002b5ac  lea     rcx, [rsp+128h+lpFileName]; struct std::filesystem::path *
0x18002b5b4  call    ?RecursiveDelete@@YAJAEBVpath@filesystem@std@@@Z; RecursiveDelete(std::filesystem::path const &)
0x18002b5b9  mov     rcx, [rsp+128h]; this
0x18002b5c1  test    eax, eax
0x18002b5c3  jns     loc_18002B6D2
0x18002b5c9  mov     r9d, eax; char *
0x18002b5cc  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002b5d3  mov     edx, 93h; void *
0x18002b5d8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002b5dd  jmp     loc_18002B6D2
0x18002b5e2  mov     rsi, r13
0x18002b5e5  lea     rcx, [rsp+128h+lpFileName]
0x18002b5ed  cmp     [rsp+128h+var_40], 7
0x18002b5f6  cmova   rcx, [rsp+128h+lpFileName]; lpFileName
0x18002b5ff  mov     [rsp+128h+hTemplateFile], r13; hTemplateFile
0x18002b604  mov     [rsp+128h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002b60c  mov     [rsp+128h+dwCreationDisposition], 3; int
0x18002b614  xor     r9d, r9d; lpSecurityAttributes
0x18002b617  mov     edx, 110000h; dwDesiredAccess
0x18002b61c  lea     r8d, [r9+7]; dwShareMode
0x18002b620  call    cs:__imp_CreateFileW
0x18002b626  mov     r13, rax
0x18002b629  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b62d  jz      short loc_18002B6A9
0x18002b62f  mov     rsi, rax
0x18002b632  mov     [rsp+128h+var_C0], rax
0x18002b637  mov     [rsp+128h+var_C8], 0
0x18002b63c  lea     r8, [rsp+128h+var_C8]; bool *
0x18002b641  lea     rdx, [rsp+128h+lpFileName]; struct std::filesystem::path *
0x18002b649  mov     rcx, rax; void *
0x18002b64c  call    ?DoesExpectedPathMatchFinalPath@@YAJPEAXAEBVpath@filesystem@std@@PEA_N@Z; DoesExpectedPathMatchFinalPath(void *,std::filesystem::path const &,bool *)
0x18002b651  test    eax, eax
0x18002b653  js      short loc_18002B694
0x18002b655  cmp     [rsp+128h+var_C8], 0
0x18002b65a  jz      short loc_18002B694
0x18002b65c  mov     [rsp+128h+var_C8], 1
0x18002b661  mov     r9d, 1; dwBufferSize
0x18002b667  lea     r8, [rsp+128h+var_C8]; lpFileInformation
0x18002b66c  lea     edx, [r9+3]; FileInformationClass
0x18002b670  mov     rcx, rsi; hFile
0x18002b673  call    cs:__imp_SetFileInformationByHandle
0x18002b679  mov     rcx, [rsp+128h]; this
0x18002b681  xor     r13d, r13d
0x18002b684  test    eax, eax
0x18002b686  jnz     short loc_18002B6BE
0x18002b688  mov     edx, 0B3h; void *
0x18002b68d  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002b692  jmp     short loc_18002B6BE
0x18002b694  mov     rcx, [rsp+128h]; this
0x18002b69c  mov     r9d, 800700A1h; char *
0x18002b6a2  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18002b6a7  jmp     short loc_18002B6BB
0x18002b6a9  mov     rcx, [rsp+128h]; this
0x18002b6b1  mov     edx, 0BCh; void *
0x18002b6b6  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002b6bb  xor     r13d, r13d
0x18002b6be  lea     rax, [rsi-1]
0x18002b6c2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002b6c6  ja      short loc_18002B6D2
0x18002b6c8  mov     rcx, rsi; hObject
0x18002b6cb  call    cs:__imp_CloseHandle
0x18002b6d1  nop
0x18002b6d2  or      [rsp+128h+var_C4], 3
0x18002b6d7  lea     rcx, [rsp+128h+lpFileName]
0x18002b6df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b6e4  nop
0x18002b6e5  lea     rcx, [rsp+128h+S1]
0x18002b6ed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b6f2  cmp     [rdi], r13d
0x18002b6f5  jz      short loc_18002B701
0x18002b6f7  mov     eax, [rdi]
0x18002b6f9  add     rdi, rax
0x18002b6fc  jmp     loc_18002B474
0x18002b701  mov     rdi, r13
0x18002b704  jmp     loc_18002B474
0x18002b709  mov     [rsp+128h+RestartScan], r13b; RestartScan
0x18002b70e  mov     [rsp+128h+FileName], r13; FileName
0x18002b713  mov     [rsp+128h+ReturnSingleEntry], r13b; ReturnSingleEntry
0x18002b718  mov     [rsp+128h+FileInformationClass], 1; FileInformationClass
0x18002b720  mov     dword ptr [rsp+128h+hTemplateFile], 10000h; Length
0x18002b728  mov     qword ptr [rsp+128h+dwFlagsAndAttributes], r15; FileInformation
0x18002b72d  lea     rax, [rsp+128h+IoStatusBlock]
0x18002b732  mov     qword ptr [rsp+128h+dwCreationDisposition], rax; IoStatusBlock
0x18002b737  xor     r9d, r9d; ApcContext
0x18002b73a  xor     r8d, r8d; ApcRoutine
0x18002b73d  xor     edx, edx; Event
0x18002b73f  mov     rcx, rbx; FileHandle
0x18002b742  call    cs:__imp_NtQueryDirectoryFile
0x18002b748  mov     edi, eax
0x18002b74a  jmp     loc_18002B466
0x18002b74f  cmp     edi, 80000006h
0x18002b755  jz      short loc_18002B768
0x18002b757  mov     rcx, [rsp+128h]; this
0x18002b75f  mov     r9d, edi; char *
0x18002b762  call    ?Log_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_NtStatus(void *,uint,char const *,long)
0x18002b767  nop
0x18002b768  test    r15, r15
0x18002b76b  jz      short loc_18002B77F
0x18002b76d  xor     edx, edx; dwSize
0x18002b76f  mov     r8d, 8000h; dwFreeType
0x18002b775  mov     rcx, r15; lpAddress
0x18002b778  call    cs:__imp_VirtualFree
0x18002b77e  nop
0x18002b77f  test    rbx, rbx
0x18002b782  jz      short loc_18002B78D
0x18002b784  mov     rcx, rbx; hObject
0x18002b787  call    cs:__imp_CloseHandle
0x18002b78d  xor     eax, eax
0x18002b78f  jmp     short loc_18002B7AA
0x18002b791  test    rbx, rbx
0x18002b794  jz      short loc_18002B79F
0x18002b796  mov     rcx, rbx; hObject
0x18002b799  call    cs:__imp_CloseHandle
0x18002b79f  mov     eax, 80070006h
0x18002b7a4  jmp     short loc_18002B7AA
0x18002b7a6  mov     eax, [rsp+128h+var_C4]
0x18002b7aa  mov     rcx, [rsp+128h+var_38]
0x18002b7b2  xor     rcx, rsp; StackCookie
0x18002b7b5  call    __security_check_cookie
0x18002b7ba  lea     r11, [rsp+128h+var_28]
0x18002b7c2  mov     rbx, [r11+38h]
0x18002b7c6  mov     rsi, [r11+40h]
0x18002b7ca  mov     rsp, r11
  ... truncated ...
```
