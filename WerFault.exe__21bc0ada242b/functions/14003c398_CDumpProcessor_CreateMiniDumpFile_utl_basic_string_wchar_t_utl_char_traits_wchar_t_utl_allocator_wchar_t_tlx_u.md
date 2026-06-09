# CDumpProcessor::CreateMiniDumpFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x14003c398`
- end: `0x14003c8d9`
- name: `?CreateMiniDumpFile@CDumpProcessor@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `1345`
- prototype: `__int64 __fastcall(__int64, __int64, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14003be5c`
- `0x14003cf94`

## callees

- `0x140002470`
- `0x140002728`
- `0x140005430`
- `0x14000c8a0`
- `0x1400126dc`
- `0x140015458`
- `0x140034d9c`
- `0x14003902c`
- `0x14003c398`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c4a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c5bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c7e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c4a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c5bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c7e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c69c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c723`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c85d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c8aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c69c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c723`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c85d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c8aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14003c586`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14003c586`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003c5fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003c5fe`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x14003c594`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x14003c594`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14003c4fc`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14003c4fc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003c67f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003c67f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003c86d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003c86d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14003c5b5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14003c5b5`
- `RPCRT4!UuidCreate` at `0x14003c737`
- `RPCRT4!UuidCreate` at `0x14003c737`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14003c49f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14003c49f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003c466`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003c896`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003c466`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003c896`

## string_xrefs

- `0x14003c74e`: `UuidCreate failed`
- `0x14003c42a`: `CDumpProcessor::CreateMiniDumpFile`
- `0x14003c54b`: `CDumpProcessor::CreateMiniDumpFile`
- `0x14003c7c3`: `CDumpProcessor::CreateMiniDumpFile`
- `0x14003c832`: `CDumpProcessor::CreateMiniDumpFile`
- `0x14003c4c8`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed`
- `0x14003c53b`: `Unable to create the folder %ws`
- `0x14003c6ed`: `Copy failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDumpProcessor::CreateMiniDumpFile(__int64 a1, __int64 a2, void **a3)
{
  void *v6; // rdi
  signed int v7; // ebx
  const wchar_t *v8; // rsi
  signed int v9; // eax
  signed int v10; // eax
  const wchar_t *v11; // rdx
  signed int LastError; // eax
  int v13; // r14d
  HANDLE v14; // rbx
  void *v15; // rcx
  void *v16; // rcx
  RPC_STATUS v17; // eax
  signed int v18; // eax
  void *v19; // rcx
  WCHAR *v20; // rcx
  wil::details *dwCreationDisposition; // [rsp+20h] [rbp-69h]
  wil::details *dwCreationDispositiona; // [rsp+20h] [rbp-69h]
  wil::details *dwCreationDispositionb; // [rsp+20h] [rbp-69h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-61h]
  const char *hTemplateFile; // [rsp+30h] [rbp-59h]
  const char *hTemplateFilea; // [rsp+30h] [rbp-59h]
  const char *hTemplateFileb; // [rsp+30h] [rbp-59h]
  __int64 v29; // [rsp+38h] [rbp-51h]
  HLOCAL hMem; // [rsp+40h] [rbp-49h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+48h] [rbp-41h] BYREF
  HANDLE v32; // [rsp+50h] [rbp-39h]
  LPCWSTR lpFileName; // [rsp+58h] [rbp-31h] BYREF
  const WCHAR *v34; // [rsp+60h] [rbp-29h]
  _WORD v35[8]; // [rsp+68h] [rbp-21h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-11h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+80h] [rbp-9h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+E8h] [rbp+5Fh]

  SystemTimeAsFileTime = 0;
  LocalFileTime = 0;
  SystemTime = 0;
  v6 = 0;
  v32 = 0;
  hMem = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  lpFileName = v35;
  v34 = v35;
  v35[0] = 0;
  if ( a2 || a3 )
  {
    v8 = *(const wchar_t **)(a1 + 88);
    if ( v8 && *v8 )
    {
      hMem = 0;
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)", 1u, &hMem, 0) )
      {
        SecurityAttributes.nLength = 24;
        SecurityAttributes.bInheritHandle = 0;
        SecurityAttributes.lpSecurityDescriptor = hMem;
        if ( CreateDirectoryW(v8, &SecurityAttributes) || GetLastError() == 183 )
        {
          UtilSetPathToSoftReserve(v8);
          UtilPruneFolder(v8, v11, *(_DWORD *)(a1 + 152) - 1);
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          if ( FileTimeToLocalFileTime(&SystemTimeAsFileTime, &LocalFileTime) )
          {
            *(struct _FILETIME *)(a1 + 8504) = LocalFileTime;
            if ( FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
            {
              v13 = 1;
              while ( 1 )
              {
                LODWORD(v29) = v13;
                LODWORD(hTemplateFile) = GetTickCount();
                dwFlagsAndAttributes[0] = SystemTime.wYear % 0x64u;
                LODWORD(dwCreationDisposition) = SystemTime.wDay;
                v7 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                       &lpFileName,
                       L"%s\\%2.2d%2.2d%2.2d-%u-%2.2d.dmp",
                       v8,
                       SystemTime.wMonth,
                       dwCreationDisposition,
                       *(_QWORD *)dwFlagsAndAttributes,
                       hTemplateFile,
                       v29);
                if ( v7 < 0 )
                {
                  LODWORD(dwCreationDispositiona) = v7;
                  wil::details::in1diag4::Log_HrMsg(
                    retaddr,
                    (void *)0x290,
                    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
                    "CDumpProcessor::CreateMiniDumpFile",
                    dwCreationDispositiona,
                    (int)"Sprintf failed",
                    hTemplateFilea);
                  goto LABEL_56;
                }
                v14 = CreateFileW(lpFileName, 0x40040000u, 0, &SecurityAttributes, 1u, 0x80u, 0);
                v15 = v6;
                v6 = v14;
                v32 = v14;
                if ( (unsigned __int64)v15 + 1 > 1 )
                  CloseHandle(v15);
                if ( (unsigned __int64)v14 + 1 > 1 )
                  break;
                if ( (unsigned int)++v13 >= 0x64 )
                {
                  v7 = -2147467259;
                  goto LABEL_56;
                }
              }
              if ( a2
                && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                       a2,
                                       lpFileName) )
              {
                v7 = -2147024882;
                LODWORD(dwCreationDisposition) = -2147024882;
                wil::details::in1diag4::Log_HrMsg(
                  retaddr,
                  (void *)0x2B0,
                  (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
                  "CDumpProcessor::CreateMiniDumpFile",
                  dwCreationDisposition,
                  (int)"Copy failed",
                  hTemplateFile);
                goto LABEL_56;
              }
              if ( a3 )
              {
                v6 = 0;
                v32 = 0;
                v16 = *a3;
                *a3 = v14;
                if ( (unsigned __int64)v16 + 1 > 1 )
                  CloseHandle(v16);
              }
              *(_OWORD *)(a1 + 8512) = 0;
              v17 = UuidCreate((UUID *)(a1 + 8512));
              v7 = v17;
              if ( !v17 || v17 == 1824 )
              {
                v7 = 0;
                goto LABEL_60;
              }
              LODWORD(dwCreationDisposition) = v17;
              wil::details::in1diag4::Log_Win32Msg(
                retaddr,
                (void *)0x51B,
                (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
                "CDumpProcessor::GenerateIntegratorReportId",
                dwCreationDisposition,
                (unsigned int)"UuidCreate failed",
                hTemplateFile);
              if ( v7 > 0 )
                v7 = (unsigned __int16)v7 | 0x80070000;
              if ( v7 >= 0 )
                v7 = -2147467259;
              LODWORD(dwCreationDispositionb) = v7;
              wil::details::in1diag4::Log_HrMsg(
                retaddr,
                (void *)0x2BE,
                (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
                "CDumpProcessor::CreateMiniDumpFile",
                dwCreationDispositionb,
                (int)"GenerateIntegratorReportId failed",
                hTemplateFileb);
            }
            else
            {
              LastError = GetLastError();
              v7 = LastError;
              if ( LastError > 0 )
                v7 = (unsigned __int16)LastError | 0x80070000;
              if ( v7 >= 0 )
                v7 = -2147467259;
              LODWORD(dwCreationDisposition) = v7;
              wil::details::in1diag4::Log_HrMsg(
                retaddr,
                (void *)0x27E,
                (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
                "CDumpProcessor::CreateMiniDumpFile",
                dwCreationDisposition,
                (int)"FileTimeToSystemTime failed",
                hTemplateFile);
            }
          }
          else
          {
            v18 = GetLastError();
            v7 = v18;
            if ( v18 > 0 )
              v7 = (unsigned __int16)v18 | 0x80070000;
            if ( v7 >= 0 )
              v7 = -2147467259;
            LODWORD(dwCreationDisposition) = v7;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x274,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
              "CDumpProcessor::CreateMiniDumpFile",
              dwCreationDisposition,
              (int)"FileTimeToLocalTime failed",
              hTemplateFile);
          }
        }
        else
        {
          v10 = GetLastError();
          v7 = v10;
          if ( v10 > 0 )
            v7 = (unsigned __int16)v10 | 0x80070000;
          if ( v7 >= 0 )
            v7 = -2147467259;
          LODWORD(dwCreationDisposition) = v7;
          wil::details::in1diag4::Log_HrMsg(
            retaddr,
            (void *)0x25D,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
            "CDumpProcessor::CreateMiniDumpFile",
            dwCreationDisposition,
            (int)"Unable to create the folder %ws",
            (const char *)v8);
        }
      }
      else
      {
        v9 = GetLastError();
        v7 = v9;
        if ( v9 > 0 )
          v7 = (unsigned __int16)v9 | 0x80070000;
        if ( v7 >= 0 )
          v7 = -2147467259;
        LODWORD(dwCreationDisposition) = v7;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x24E,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
          "CDumpProcessor::CreateMiniDumpFile",
          dwCreationDisposition,
          (int)"ConvertStringSecurityDescriptorToSecurityDescriptor failed",
          hTemplateFile);
      }
    }
    else
    {
      v7 = -2147467259;
      LODWORD(dwCreationDisposition) = -2147467259;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x241,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
        "CDumpProcessor::CreateMiniDumpFile",
        dwCreationDisposition,
        (int)"Minidumpdir not set",
        hTemplateFile);
    }
LABEL_56:
    v19 = v6;
    v6 = 0;
    v32 = 0;
    if ( (unsigned __int64)v19 + 1 > 1 )
      CloseHandle(v19);
    v20 = (WCHAR *)lpFileName;
    if ( lpFileName != v34 )
    {
      DeleteFileW(lpFileName);
LABEL_60:
      v20 = (WCHAR *)lpFileName;
    }
    if ( v20 != v35 )
      operator delete(v20, (const struct std::nothrow_t *)&std::nothrow);
    if ( hMem )
      LocalFree(hMem);
    if ( (unsigned __int64)v6 + 1 > 1 )
      CloseHandle(v6);
  }
  else
  {
    v7 = -2147024809;
    LODWORD(dwCreationDisposition) = -2147024809;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x235,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
      "CDumpProcessor::CreateMiniDumpFile",
      dwCreationDisposition,
      (int)"Invalid args",
      hTemplateFile);
    if ( lpFileName != v35 )
      operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14003c398  mov     [rsp-8+arg_18], rbx
0x14003c39d  push    rbp
0x14003c39e  push    rsi
0x14003c39f  push    rdi
0x14003c3a0  push    r12
0x14003c3a2  push    r13
0x14003c3a4  push    r14
0x14003c3a6  push    r15
0x14003c3a8  lea     rbp, [rsp-27h]
0x14003c3ad  sub     rsp, 0B0h
0x14003c3b4  mov     rax, cs:__security_cookie
0x14003c3bb  xor     rax, rsp
0x14003c3be  mov     [rbp+57h+var_38], rax
0x14003c3c2  mov     r15, r8
0x14003c3c5  mov     r12, rdx
0x14003c3c8  mov     r13, rcx
0x14003c3cb  xor     r14d, r14d
0x14003c3ce  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r14
0x14003c3d2  mov     qword ptr [rbp+57h+LocalFileTime.dwLowDateTime], r14
0x14003c3d6  xorps   xmm0, xmm0
0x14003c3d9  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x14003c3dd  mov     edi, r14d
0x14003c3e0  mov     [rbp+57h+var_90], r14
0x14003c3e4  mov     [rbp+57h+hMem], r14
0x14003c3e8  xor     eax, eax
0x14003c3ea  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x14003c3ee  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x14003c3f2  lea     rax, [rbp+57h+var_78]
0x14003c3f6  mov     [rbp+57h+lpFileName], rax
0x14003c3fa  lea     rax, [rbp+57h+var_78]
0x14003c3fe  mov     [rbp+57h+var_80], rax
0x14003c402  mov     [rbp+57h+var_78], r14w
0x14003c407  test    rdx, rdx
0x14003c40a  jnz     short loc_14003C472
0x14003c40c  test    r8, r8
0x14003c40f  jnz     short loc_14003C472
0x14003c411  mov     rcx, [rbp+5Fh]; this
0x14003c415  lea     rax, aInvalidArgs; "Invalid args"
0x14003c41c  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; int
0x14003c421  mov     ebx, 80070057h
0x14003c426  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx; wil::details *
0x14003c42a  lea     r9, aCdumpprocessor_2; "CDumpProcessor::CreateMiniDumpFile"
0x14003c431  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c438  mov     edx, 235h; void *
0x14003c43d  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003c442  nop
0x14003c443  lea     rax, [rbp+57h+var_78]
0x14003c447  mov     rcx, [rbp+57h+lpFileName]; void *
0x14003c44b  cmp     rcx, rax
0x14003c44e  jz      short loc_14003C45D
0x14003c450  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003c457  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003c45c  nop
0x14003c45d  mov     rcx, [rbp+57h+hMem]; hMem
0x14003c461  test    rcx, rcx
0x14003c464  jz      short loc_14003C46D
0x14003c466  call    cs:__imp_LocalFree
0x14003c46c  nop
0x14003c46d  jmp     loc_14003C8B0
0x14003c472  mov     rsi, [rcx+58h]
0x14003c476  test    rsi, rsi
0x14003c479  jz      loc_14003C816
0x14003c47f  cmp     [rsi], r14w
0x14003c483  jz      loc_14003C816
0x14003c489  mov     [rbp+57h+hMem], r14
0x14003c48d  xor     r9d, r9d; SecurityDescriptorSize
0x14003c490  lea     r8, [rbp+57h+hMem]; SecurityDescriptor
0x14003c494  lea     edx, [r9+1]; StringSDRevision
0x14003c498  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x14003c49f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14003c4a5  test    eax, eax
0x14003c4a7  jnz     short loc_14003C4E2
0x14003c4a9  call    cs:__imp_GetLastError
0x14003c4af  mov     ebx, eax
0x14003c4b1  test    eax, eax
0x14003c4b3  jle     short loc_14003C4BE
0x14003c4b5  movzx   ebx, ax
0x14003c4b8  or      ebx, 80070000h
0x14003c4be  mov     eax, 80004005h
0x14003c4c3  test    ebx, ebx
0x14003c4c5  cmovns  ebx, eax
0x14003c4c8  lea     rax, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x14003c4cf  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x14003c4d4  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx
0x14003c4d8  mov     edx, 24Eh
0x14003c4dd  jmp     loc_14003C832
0x14003c4e2  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x14003c4e9  mov     [rbp+57h+SecurityAttributes.bInheritHandle], r14d
0x14003c4ed  mov     rax, [rbp+57h+hMem]
0x14003c4f1  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x14003c4f5  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x14003c4f9  mov     rcx, rsi; lpPathName
0x14003c4fc  call    cs:__imp_CreateDirectoryW
0x14003c502  test    eax, eax
0x14003c504  jnz     short loc_14003C568
0x14003c506  call    cs:__imp_GetLastError
0x14003c50c  cmp     eax, 0B7h
0x14003c511  jz      short loc_14003C568
0x14003c513  call    cs:__imp_GetLastError
0x14003c519  mov     ebx, eax
0x14003c51b  test    eax, eax
0x14003c51d  jle     short loc_14003C528
0x14003c51f  movzx   ebx, ax
0x14003c522  or      ebx, 80070000h
0x14003c528  mov     eax, 80004005h
0x14003c52d  test    ebx, ebx
0x14003c52f  cmovns  ebx, eax
0x14003c532  mov     rcx, [rbp+5Fh]; this
0x14003c536  mov     [rsp+0E0h+hTemplateFile], rsi; char *
0x14003c53b  lea     rax, aUnableToCreate; "Unable to create the folder %ws"
0x14003c542  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; int
0x14003c547  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx; wil::details *
0x14003c54b  lea     r9, aCdumpprocessor_2; "CDumpProcessor::CreateMiniDumpFile"
0x14003c552  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c559  mov     edx, 25Dh; void *
0x14003c55e  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003c563  jmp     loc_14003C849
0x14003c568  mov     rcx, rsi; wchar_t *
0x14003c56b  call    ?UtilSetPathToSoftReserve@@YAJPEB_W@Z; UtilSetPathToSoftReserve(wchar_t const *)
0x14003c570  mov     r8d, [r13+98h]
0x14003c577  dec     r8d; unsigned int
0x14003c57a  mov     rcx, rsi; wchar_t *
0x14003c57d  call    ?UtilPruneFolder@@YAJPEB_W0K@Z; UtilPruneFolder(wchar_t const *,wchar_t const *,ulong)
0x14003c582  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14003c586  call    cs:__imp_GetSystemTimeAsFileTime
0x14003c58c  lea     rdx, [rbp+57h+LocalFileTime]; lpLocalFileTime
0x14003c590  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime
0x14003c594  call    cs:__imp_FileTimeToLocalFileTime
0x14003c59a  test    eax, eax
0x14003c59c  jz      loc_14003C7E0
0x14003c5a2  mov     rax, qword ptr [rbp+57h+LocalFileTime.dwLowDateTime]
0x14003c5a6  mov     [r13+2138h], rax
0x14003c5ad  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x14003c5b1  lea     rcx, [rbp+57h+LocalFileTime]; lpFileTime
0x14003c5b5  call    cs:__imp_FileTimeToSystemTime
0x14003c5bb  test    eax, eax
0x14003c5bd  jnz     short loc_14003C5F8
0x14003c5bf  call    cs:__imp_GetLastError
0x14003c5c5  mov     ebx, eax
0x14003c5c7  test    eax, eax
0x14003c5c9  jle     short loc_14003C5D4
0x14003c5cb  movzx   ebx, ax
0x14003c5ce  or      ebx, 80070000h
0x14003c5d4  mov     eax, 80004005h
0x14003c5d9  test    ebx, ebx
0x14003c5db  cmovns  ebx, eax
0x14003c5de  lea     rax, aFiletimetosyst; "FileTimeToSystemTime failed"
0x14003c5e5  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x14003c5ea  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx
0x14003c5ee  mov     edx, 27Eh
0x14003c5f3  jmp     loc_14003C832
0x14003c5f8  mov     r14d, 1
0x14003c5fe  call    cs:__imp_GetTickCount
0x14003c604  mov     r8d, eax
0x14003c607  movzx   r10d, [rbp+57h+SystemTime.wYear]
0x14003c60c  mov     eax, 51EB851Fh
0x14003c611  mul     r10d
0x14003c614  shr     edx, 5
0x14003c617  imul    ecx, edx, 64h ; 'd'
0x14003c61a  sub     r10d, ecx
0x14003c61d  movzx   ecx, [rbp+57h+SystemTime.wDay]
0x14003c621  movzx   r9d, [rbp+57h+SystemTime.wMonth]
0x14003c626  mov     dword ptr [rsp+0E0h+var_A8], r14d
0x14003c62b  mov     dword ptr [rsp+0E0h+hTemplateFile], r8d; char *
0x14003c630  mov     [rsp+0E0h+dwFlagsAndAttributes], r10d
0x14003c635  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ecx
0x14003c639  mov     r8, rsi
0x14003c63c  lea     rdx, aS22d22d22dU22d; "%s\\%2.2d%2.2d%2.2d-%u-%2.2d.dmp"
0x14003c643  lea     rcx, [rbp+57h+lpFileName]
0x14003c647  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14003c64c  mov     ebx, eax
0x14003c64e  test    eax, eax
0x14003c650  js      loc_14003C7AF
0x14003c656  mov     [rsp+0E0h+hTemplateFile], 0; char *
0x14003c65f  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14003c667  mov     dword ptr [rsp+0E0h+dwCreationDisposition], 1; dwCreationDisposition
0x14003c66f  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x14003c673  xor     r8d, r8d; dwShareMode
0x14003c676  mov     edx, 40040000h; dwDesiredAccess
0x14003c67b  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x14003c67f  call    cs:__imp_CreateFileW
0x14003c685  mov     rbx, rax
0x14003c688  mov     rcx, rdi; hObject
0x14003c68b  mov     rdi, rax
0x14003c68e  mov     [rbp+57h+var_90], rax
0x14003c692  lea     rdx, [rcx+1]
0x14003c696  cmp     rdx, 1
0x14003c69a  jbe     short loc_14003C6A2
0x14003c69c  call    cs:__imp_CloseHandle
0x14003c6a2  lea     rcx, [rbx+1]
0x14003c6a6  cmp     rcx, 1
0x14003c6aa  ja      short loc_14003C6C6
0x14003c6ac  inc     r14d
0x14003c6af  cmp     r14d, 64h ; 'd'
0x14003c6b3  jb      loc_14003C5FE
0x14003c6b9  mov     ebx, 80004005h
0x14003c6be  xor     r14d, r14d
0x14003c6c1  jmp     loc_14003C849
0x14003c6c6  xor     r14d, r14d
0x14003c6c9  test    r12, r12
0x14003c6cc  jz      short loc_14003C707
0x14003c6ce  mov     r8, [rbp+57h+var_80]
0x14003c6d2  mov     rdx, [rbp+57h+lpFileName]
0x14003c6d6  sub     r8, rdx
0x14003c6d9  sar     r8, 1
0x14003c6dc  mov     rcx, r12
0x14003c6df  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003c6e4  test    al, al
0x14003c6e6  jnz     short loc_14003C707
0x14003c6e8  mov     ebx, 8007000Eh
0x14003c6ed  lea     rax, aCopyFailed; "Copy failed"
0x14003c6f4  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x14003c6f9  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx
0x14003c6fd  mov     edx, 2B0h
0x14003c702  jmp     loc_14003C832
0x14003c707  test    r15, r15
0x14003c70a  jz      short loc_14003C729
0x14003c70c  mov     rdi, r14
0x14003c70f  mov     [rbp+57h+var_90], r14
0x14003c713  mov     rcx, [r15]; hObject
0x14003c716  mov     [r15], rbx
0x14003c719  lea     rax, [rcx+1]
0x14003c71d  cmp     rax, 1
0x14003c721  jbe     short loc_14003C729
0x14003c723  call    cs:__imp_CloseHandle
0x14003c729  lea     rcx, [r13+2140h]; Uuid
0x14003c730  xorps   xmm0, xmm0
0x14003c733  movdqu  xmmword ptr [rcx], xmm0
0x14003c737  call    cs:__imp_UuidCreate
0x14003c73d  mov     ebx, eax
0x14003c73f  test    eax, eax
0x14003c741  jz      short loc_14003C7A7
0x14003c743  cmp     eax, 720h
0x14003c748  jz      short loc_14003C7A7
0x14003c74a  mov     rcx, [rbp+5Fh]; this
0x14003c74e  lea     rax, aUuidcreateFail; "UuidCreate failed"
0x14003c755  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; unsigned int
0x14003c75a  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx; wil::details *
0x14003c75e  lea     r9, aCdumpprocessor_0; "CDumpProcessor::GenerateIntegratorRepor"...
0x14003c765  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c76c  mov     edx, 51Bh; void *
0x14003c771  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14003c776  test    ebx, ebx
0x14003c778  jle     short loc_14003C783
0x14003c77a  movzx   ebx, bx
0x14003c77d  or      ebx, 80070000h
0x14003c783  mov     eax, 80004005h
0x14003c788  test    ebx, ebx
0x14003c78a  cmovns  ebx, eax
0x14003c78d  lea     rax, aGenerateintegr; "GenerateIntegratorReportId failed"
0x14003c794  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x14003c799  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx
0x14003c79d  mov     edx, 2BEh
0x14003c7a2  jmp     loc_14003C832
0x14003c7a7  mov     ebx, r14d
0x14003c7aa  jmp     loc_14003C873
0x14003c7af  mov     rcx, [rbp+5Fh]; this
0x14003c7b3  lea     rax, aSprintfFailed; "Sprintf failed"
0x14003c7ba  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; int
0x14003c7bf  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx; wil::details *
0x14003c7c3  lea     r9, aCdumpprocessor_2; "CDumpProcessor::CreateMiniDumpFile"
0x14003c7ca  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c7d1  mov     edx, 290h; void *
0x14003c7d6  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003c7db  jmp     loc_14003C6BE
0x14003c7e0  call    cs:__imp_GetLastError
0x14003c7e6  mov     ebx, eax
0x14003c7e8  test    eax, eax
0x14003c7ea  jle     short loc_14003C7F5
0x14003c7ec  movzx   ebx, ax
0x14003c7ef  or      ebx, 80070000h
0x14003c7f5  mov     eax, 80004005h
0x14003c7fa  test    ebx, ebx
0x14003c7fc  cmovns  ebx, eax
0x14003c7ff  lea     rax, aFiletimetoloca; "FileTimeToLocalTime failed"
0x14003c806  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x14003c80b  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx
0x14003c80f  mov     edx, 274h
0x14003c814  jmp     short loc_14003C832
0x14003c816  mov     eax, 80004005h
0x14003c81b  mov     ebx, eax
0x14003c81d  lea     rdx, aMinidumpdirNot; "Minidumpdir not set"
0x14003c824  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rdx; int
0x14003c829  mov     dword ptr [rsp+0E0h+dwCreationDisposition], eax; wil::details *
0x14003c82d  mov     edx, 241h; void *
0x14003c832  lea     r9, aCdumpprocessor_2; "CDumpProcessor::CreateMiniDumpFile"
0x14003c839  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c840  mov     rcx, [rbp+5Fh]; this
0x14003c844  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003c849  mov     rcx, rdi; hObject
0x14003c84c  mov     rdi, r14
0x14003c84f  mov     [rbp+57h+var_90], r14
0x14003c853  lea     rax, [rcx+1]
0x14003c857  cmp     rax, 1
0x14003c85b  jbe     short loc_14003C863
0x14003c85d  call    cs:__imp_CloseHandle
0x14003c863  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x14003c867  cmp     rcx, [rbp+57h+var_80]
0x14003c86b  jz      short loc_14003C877
0x14003c86d  call    cs:__imp_DeleteFileW
  ... truncated ...
```
