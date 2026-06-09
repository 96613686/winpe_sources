# CDumpProcessor::CreateMiniDumpFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x14003ecdc`
- end: `0x14003f29a`
- name: `?CreateMiniDumpFile@CDumpProcessor@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `1470`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14003e750`
- `0x14003f95c`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400054e4`
- `0x14000ca20`
- `0x140012fb0`
- `0x140015fa8`
- `0x1400167a4`
- `0x1400372dc`
- `0x14003b56c`
- `0x14003ecdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003edfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ee66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ee79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ef3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003f182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003edfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ee66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ee79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ef3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003f182`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f02c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f0b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f205`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f264`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f02c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f0b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f205`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f264`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14003eef2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14003eef2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003ef82`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003ef82`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x14003ef06`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x14003ef06`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14003ee56`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14003ee56`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003f009`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003f009`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003f21b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003f21b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14003ef2d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14003ef2d`
- `RPCRT4!UuidCreate` at `0x14003f0d3`
- `RPCRT4!UuidCreate` at `0x14003f0d3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14003eded`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14003eded`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003edaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003f24a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003edaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003f24a`

## string_xrefs

- `0x14003f0f0`: `UuidCreate failed`
- `0x14003ed6e`: `CDumpProcessor::CreateMiniDumpFile`
- `0x14003eeb7`: `CDumpProcessor::CreateMiniDumpFile`
- `0x14003f165`: `CDumpProcessor::CreateMiniDumpFile`
- `0x14003f1da`: `CDumpProcessor::CreateMiniDumpFile`
- `0x14003ee22`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed`
- `0x14003eea7`: `Unable to create the folder %ws`
- `0x14003f083`: `Copy failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDumpProcessor::CreateMiniDumpFile(__int64 a1, __int64 a2, void **a3)
{
  void *v6; // rdi
  signed int v7; // ebx
  const wchar_t *v8; // rsi
  PSECURITY_DESCRIPTOR *v9; // rax
  signed int v10; // eax
  signed int v11; // eax
  const wchar_t *v12; // rdx
  signed int LastError; // eax
  int v14; // r14d
  HANDLE v15; // rbx
  void *v16; // rcx
  void *v17; // rcx
  RPC_STATUS v18; // eax
  signed int v19; // eax
  void *v20; // rcx
  WCHAR *v21; // rcx
  wil::details *dwCreationDisposition; // [rsp+20h] [rbp-69h]
  wil::details *dwCreationDispositiona; // [rsp+20h] [rbp-69h]
  wil::details *dwCreationDispositionb; // [rsp+20h] [rbp-69h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-61h]
  const char *hTemplateFile; // [rsp+30h] [rbp-59h]
  const char *hTemplateFilea; // [rsp+30h] [rbp-59h]
  const char *hTemplateFileb; // [rsp+30h] [rbp-59h]
  __int64 v30; // [rsp+38h] [rbp-51h]
  HLOCAL hMem; // [rsp+40h] [rbp-49h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+48h] [rbp-41h] BYREF
  HANDLE v33; // [rsp+50h] [rbp-39h]
  LPCWSTR lpFileName; // [rsp+58h] [rbp-31h] BYREF
  const WCHAR *v35; // [rsp+60h] [rbp-29h]
  _WORD v36[8]; // [rsp+68h] [rbp-21h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-11h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+80h] [rbp-9h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+E8h] [rbp+5Fh]

  SystemTimeAsFileTime = 0;
  LocalFileTime = 0;
  SystemTime = 0;
  v6 = 0;
  v33 = 0;
  hMem = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  lpFileName = v36;
  v35 = v36;
  v36[0] = 0;
  if ( a2 || a3 )
  {
    v8 = *(const wchar_t **)(a1 + 88);
    if ( v8 && *v8 )
    {
      v9 = (PSECURITY_DESCRIPTOR *)___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&hMem);
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)", 1u, v9, 0) )
      {
        SecurityAttributes.nLength = 24;
        SecurityAttributes.bInheritHandle = 0;
        SecurityAttributes.lpSecurityDescriptor = hMem;
        if ( CreateDirectoryW(v8, &SecurityAttributes) || GetLastError() == 183 )
        {
          UtilSetPathToSoftReserve(v8);
          UtilPruneFolder(v8, v12, *(_DWORD *)(a1 + 152) - 1);
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          if ( FileTimeToLocalFileTime(&SystemTimeAsFileTime, &LocalFileTime) )
          {
            *(struct _FILETIME *)(a1 + 8504) = LocalFileTime;
            if ( FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
            {
              v14 = 1;
              while ( 1 )
              {
                LODWORD(v30) = v14;
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
                       v30);
                if ( v7 < 0 )
                {
                  LODWORD(dwCreationDispositiona) = v7;
                  wil::details::in1diag4::Log_HrMsg(
                    retaddr,
                    (void *)0x28C,
                    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
                    "CDumpProcessor::CreateMiniDumpFile",
                    dwCreationDispositiona,
                    (int)"Sprintf failed",
                    hTemplateFilea);
                  goto LABEL_56;
                }
                v15 = CreateFileW(lpFileName, 0x40040000u, 0, &SecurityAttributes, 1u, 0x80u, 0);
                v16 = v6;
                v6 = v15;
                v33 = v15;
                if ( (unsigned __int64)v16 + 1 > 1 )
                  CloseHandle(v16);
                if ( (unsigned __int64)v15 + 1 > 1 )
                  break;
                if ( (unsigned int)++v14 >= 0x64 )
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
                  (void *)0x2AC,
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
                v33 = 0;
                v17 = *a3;
                *a3 = v15;
                if ( (unsigned __int64)v17 + 1 > 1 )
                  CloseHandle(v17);
              }
              *(_OWORD *)(a1 + 8512) = 0;
              v18 = UuidCreate((UUID *)(a1 + 8512));
              v7 = v18;
              if ( !v18 || v18 == 1824 )
              {
                v7 = 0;
                goto LABEL_60;
              }
              LODWORD(dwCreationDisposition) = v18;
              wil::details::in1diag4::Log_Win32Msg(
                retaddr,
                (void *)0x517,
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
                (void *)0x2BA,
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
                (void *)0x27A,
                (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
                "CDumpProcessor::CreateMiniDumpFile",
                dwCreationDisposition,
                (int)"FileTimeToSystemTime failed",
                hTemplateFile);
            }
          }
          else
          {
            v19 = GetLastError();
            v7 = v19;
            if ( v19 > 0 )
              v7 = (unsigned __int16)v19 | 0x80070000;
            if ( v7 >= 0 )
              v7 = -2147467259;
            LODWORD(dwCreationDisposition) = v7;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x270,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
              "CDumpProcessor::CreateMiniDumpFile",
              dwCreationDisposition,
              (int)"FileTimeToLocalTime failed",
              hTemplateFile);
          }
        }
        else
        {
          v11 = GetLastError();
          v7 = v11;
          if ( v11 > 0 )
            v7 = (unsigned __int16)v11 | 0x80070000;
          if ( v7 >= 0 )
            v7 = -2147467259;
          LODWORD(dwCreationDisposition) = v7;
          wil::details::in1diag4::Log_HrMsg(
            retaddr,
            (void *)0x259,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
            "CDumpProcessor::CreateMiniDumpFile",
            dwCreationDisposition,
            (int)"Unable to create the folder %ws",
            (const char *)v8);
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
          (void *)0x24A,
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
        (void *)0x23D,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
        "CDumpProcessor::CreateMiniDumpFile",
        dwCreationDisposition,
        (int)"Minidumpdir not set",
        hTemplateFile);
    }
LABEL_56:
    v20 = v6;
    v6 = 0;
    v33 = 0;
    if ( (unsigned __int64)v20 + 1 > 1 )
      CloseHandle(v20);
    v21 = (WCHAR *)lpFileName;
    if ( lpFileName != v35 )
    {
      DeleteFileW(lpFileName);
LABEL_60:
      v21 = (WCHAR *)lpFileName;
    }
    if ( v21 != v36 )
      operator delete(v21, (const struct std::nothrow_t *)&std::nothrow);
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
      (void *)0x231,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
      "CDumpProcessor::CreateMiniDumpFile",
      dwCreationDisposition,
      (int)"Invalid args",
      hTemplateFile);
    if ( lpFileName != v36 )
      operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14003ecdc  mov     [rsp-8+arg_18], rbx
0x14003ece1  push    rbp
0x14003ece2  push    rsi
0x14003ece3  push    rdi
0x14003ece4  push    r12
0x14003ece6  push    r13
0x14003ece8  push    r14
0x14003ecea  push    r15
0x14003ecec  lea     rbp, [rsp-27h]
0x14003ecf1  sub     rsp, 0B0h
0x14003ecf8  mov     rax, cs:__security_cookie
0x14003ecff  xor     rax, rsp
0x14003ed02  mov     [rbp+57h+var_38], rax
0x14003ed06  mov     r15, r8
0x14003ed09  mov     r12, rdx
0x14003ed0c  mov     r13, rcx
0x14003ed0f  xor     r14d, r14d
0x14003ed12  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r14
0x14003ed16  mov     qword ptr [rbp+57h+LocalFileTime.dwLowDateTime], r14
0x14003ed1a  xorps   xmm0, xmm0
0x14003ed1d  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x14003ed21  mov     edi, r14d
0x14003ed24  mov     [rbp+57h+var_90], r14
0x14003ed28  mov     [rbp+57h+hMem], r14
0x14003ed2c  xor     eax, eax
0x14003ed2e  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x14003ed32  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x14003ed36  lea     rax, [rbp+57h+var_78]
0x14003ed3a  mov     [rbp+57h+lpFileName], rax
0x14003ed3e  lea     rax, [rbp+57h+var_78]
0x14003ed42  mov     [rbp+57h+var_80], rax
0x14003ed46  mov     [rbp+57h+var_78], r14w
0x14003ed4b  test    rdx, rdx
0x14003ed4e  jnz     short loc_14003EDBC
0x14003ed50  test    r8, r8
0x14003ed53  jnz     short loc_14003EDBC
0x14003ed55  mov     rcx, [rbp+5Fh]; this
0x14003ed59  lea     rax, aInvalidArgs; "Invalid args"
0x14003ed60  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; int
0x14003ed65  mov     ebx, 80070057h
0x14003ed6a  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx; wil::details *
0x14003ed6e  lea     r9, aCdumpprocessor_2; "CDumpProcessor::CreateMiniDumpFile"
0x14003ed75  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003ed7c  mov     edx, 231h; void *
0x14003ed81  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ed86  nop
0x14003ed87  lea     rax, [rbp+57h+var_78]
0x14003ed8b  mov     rcx, [rbp+57h+lpFileName]; void *
0x14003ed8f  cmp     rcx, rax
0x14003ed92  jz      short loc_14003EDA1
0x14003ed94  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003ed9b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003eda0  nop
0x14003eda1  mov     rcx, [rbp+57h+hMem]; hMem
0x14003eda5  test    rcx, rcx
0x14003eda8  jz      short loc_14003EDB7
0x14003edaa  call    cs:__imp_LocalFree
0x14003edb1  nop     dword ptr [rax+rax+00h]
0x14003edb6  nop
0x14003edb7  jmp     loc_14003F270
0x14003edbc  mov     rsi, [rcx+58h]
0x14003edc0  test    rsi, rsi
0x14003edc3  jz      loc_14003F1BE
0x14003edc9  cmp     [rsi], r14w
0x14003edcd  jz      loc_14003F1BE
0x14003edd3  lea     rcx, [rbp+57h+hMem]
0x14003edd7  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x14003eddc  mov     r8, rax; SecurityDescriptor
0x14003eddf  xor     r9d, r9d; SecurityDescriptorSize
0x14003ede2  lea     edx, [r9+1]; StringSDRevision
0x14003ede6  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x14003eded  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14003edf4  nop     dword ptr [rax+rax+00h]
0x14003edf9  test    eax, eax
0x14003edfb  jnz     short loc_14003EE3C
0x14003edfd  call    cs:__imp_GetLastError
0x14003ee04  nop     dword ptr [rax+rax+00h]
0x14003ee09  mov     ebx, eax
0x14003ee0b  test    eax, eax
0x14003ee0d  jle     short loc_14003EE18
0x14003ee0f  movzx   ebx, ax
0x14003ee12  or      ebx, 80070000h
0x14003ee18  mov     eax, 80004005h
0x14003ee1d  test    ebx, ebx
0x14003ee1f  cmovns  ebx, eax
0x14003ee22  lea     rax, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x14003ee29  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x14003ee2e  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx
0x14003ee32  mov     edx, 24Ah
0x14003ee37  jmp     loc_14003F1DA
0x14003ee3c  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x14003ee43  mov     [rbp+57h+SecurityAttributes.bInheritHandle], r14d
0x14003ee47  mov     rax, [rbp+57h+hMem]
0x14003ee4b  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x14003ee4f  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x14003ee53  mov     rcx, rsi; lpPathName
0x14003ee56  call    cs:__imp_CreateDirectoryW
0x14003ee5d  nop     dword ptr [rax+rax+00h]
0x14003ee62  test    eax, eax
0x14003ee64  jnz     short loc_14003EED4
0x14003ee66  call    cs:__imp_GetLastError
0x14003ee6d  nop     dword ptr [rax+rax+00h]
0x14003ee72  cmp     eax, 0B7h
0x14003ee77  jz      short loc_14003EED4
0x14003ee79  call    cs:__imp_GetLastError
0x14003ee80  nop     dword ptr [rax+rax+00h]
0x14003ee85  mov     ebx, eax
0x14003ee87  test    eax, eax
0x14003ee89  jle     short loc_14003EE94
0x14003ee8b  movzx   ebx, ax
0x14003ee8e  or      ebx, 80070000h
0x14003ee94  mov     eax, 80004005h
0x14003ee99  test    ebx, ebx
0x14003ee9b  cmovns  ebx, eax
0x14003ee9e  mov     rcx, [rbp+5Fh]; this
0x14003eea2  mov     [rsp+0E0h+hTemplateFile], rsi; char *
0x14003eea7  lea     rax, aUnableToCreate; "Unable to create the folder %ws"
0x14003eeae  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; int
0x14003eeb3  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx; wil::details *
0x14003eeb7  lea     r9, aCdumpprocessor_2; "CDumpProcessor::CreateMiniDumpFile"
0x14003eebe  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003eec5  mov     edx, 259h; void *
0x14003eeca  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003eecf  jmp     loc_14003F1F1
0x14003eed4  mov     rcx, rsi; wchar_t *
0x14003eed7  call    ?UtilSetPathToSoftReserve@@YAJPEB_W@Z; UtilSetPathToSoftReserve(wchar_t const *)
0x14003eedc  mov     r8d, [r13+98h]
0x14003eee3  dec     r8d; unsigned int
0x14003eee6  mov     rcx, rsi; wchar_t *
0x14003eee9  call    ?UtilPruneFolder@@YAJPEB_W0K@Z; UtilPruneFolder(wchar_t const *,wchar_t const *,ulong)
0x14003eeee  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14003eef2  call    cs:__imp_GetSystemTimeAsFileTime
0x14003eef9  nop     dword ptr [rax+rax+00h]
0x14003eefe  lea     rdx, [rbp+57h+LocalFileTime]; lpLocalFileTime
0x14003ef02  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime
0x14003ef06  call    cs:__imp_FileTimeToLocalFileTime
0x14003ef0d  nop     dword ptr [rax+rax+00h]
0x14003ef12  test    eax, eax
0x14003ef14  jz      loc_14003F182
0x14003ef1a  mov     rax, qword ptr [rbp+57h+LocalFileTime.dwLowDateTime]
0x14003ef1e  mov     [r13+2138h], rax
0x14003ef25  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x14003ef29  lea     rcx, [rbp+57h+LocalFileTime]; lpFileTime
0x14003ef2d  call    cs:__imp_FileTimeToSystemTime
0x14003ef34  nop     dword ptr [rax+rax+00h]
0x14003ef39  test    eax, eax
0x14003ef3b  jnz     short loc_14003EF7C
0x14003ef3d  call    cs:__imp_GetLastError
0x14003ef44  nop     dword ptr [rax+rax+00h]
0x14003ef49  mov     ebx, eax
0x14003ef4b  test    eax, eax
0x14003ef4d  jle     short loc_14003EF58
0x14003ef4f  movzx   ebx, ax
0x14003ef52  or      ebx, 80070000h
0x14003ef58  mov     eax, 80004005h
0x14003ef5d  test    ebx, ebx
0x14003ef5f  cmovns  ebx, eax
0x14003ef62  lea     rax, aFiletimetosyst; "FileTimeToSystemTime failed"
0x14003ef69  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x14003ef6e  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx
0x14003ef72  mov     edx, 27Ah
0x14003ef77  jmp     loc_14003F1DA
0x14003ef7c  mov     r14d, 1
0x14003ef82  call    cs:__imp_GetTickCount
0x14003ef89  nop     dword ptr [rax+rax+00h]
0x14003ef8e  mov     r8d, eax
0x14003ef91  movzx   r10d, [rbp+57h+SystemTime.wYear]
0x14003ef96  mov     eax, 51EB851Fh
0x14003ef9b  mul     r10d
0x14003ef9e  shr     edx, 5
0x14003efa1  imul    ecx, edx, 64h ; 'd'
0x14003efa4  sub     r10d, ecx
0x14003efa7  movzx   ecx, [rbp+57h+SystemTime.wDay]
0x14003efab  movzx   r9d, [rbp+57h+SystemTime.wMonth]
0x14003efb0  mov     dword ptr [rsp+0E0h+var_A8], r14d
0x14003efb5  mov     dword ptr [rsp+0E0h+hTemplateFile], r8d; char *
0x14003efba  mov     [rsp+0E0h+dwFlagsAndAttributes], r10d
0x14003efbf  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ecx
0x14003efc3  mov     r8, rsi
0x14003efc6  lea     rdx, aS22d22d22dU22d; "%s\\%2.2d%2.2d%2.2d-%u-%2.2d.dmp"
0x14003efcd  lea     rcx, [rbp+57h+lpFileName]
0x14003efd1  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14003efd6  mov     ebx, eax
0x14003efd8  test    eax, eax
0x14003efda  js      loc_14003F151
0x14003efe0  mov     [rsp+0E0h+hTemplateFile], 0; char *
0x14003efe9  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14003eff1  mov     dword ptr [rsp+0E0h+dwCreationDisposition], 1; dwCreationDisposition
0x14003eff9  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x14003effd  xor     r8d, r8d; dwShareMode
0x14003f000  mov     edx, 40040000h; dwDesiredAccess
0x14003f005  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x14003f009  call    cs:__imp_CreateFileW
0x14003f010  nop     dword ptr [rax+rax+00h]
0x14003f015  mov     rbx, rax
0x14003f018  mov     rcx, rdi; hObject
0x14003f01b  mov     rdi, rax
0x14003f01e  mov     [rbp+57h+var_90], rax
0x14003f022  lea     rdx, [rcx+1]
0x14003f026  cmp     rdx, 1
0x14003f02a  jbe     short loc_14003F038
0x14003f02c  call    cs:__imp_CloseHandle
0x14003f033  nop     dword ptr [rax+rax+00h]
0x14003f038  lea     rcx, [rbx+1]
0x14003f03c  cmp     rcx, 1
0x14003f040  ja      short loc_14003F05C
0x14003f042  inc     r14d
0x14003f045  cmp     r14d, 64h ; 'd'
0x14003f049  jb      loc_14003EF82
0x14003f04f  mov     ebx, 80004005h
0x14003f054  xor     r14d, r14d
0x14003f057  jmp     loc_14003F1F1
0x14003f05c  xor     r14d, r14d
0x14003f05f  test    r12, r12
0x14003f062  jz      short loc_14003F09D
0x14003f064  mov     r8, [rbp+57h+var_80]
0x14003f068  mov     rdx, [rbp+57h+lpFileName]
0x14003f06c  sub     r8, rdx
0x14003f06f  sar     r8, 1
0x14003f072  mov     rcx, r12
0x14003f075  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003f07a  test    al, al
0x14003f07c  jnz     short loc_14003F09D
0x14003f07e  mov     ebx, 8007000Eh
0x14003f083  lea     rax, aCopyFailed; "Copy failed"
0x14003f08a  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x14003f08f  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx
0x14003f093  mov     edx, 2ACh
0x14003f098  jmp     loc_14003F1DA
0x14003f09d  test    r15, r15
0x14003f0a0  jz      short loc_14003F0C5
0x14003f0a2  mov     rdi, r14
0x14003f0a5  mov     [rbp+57h+var_90], r14
0x14003f0a9  mov     rcx, [r15]; hObject
0x14003f0ac  mov     [r15], rbx
0x14003f0af  lea     rax, [rcx+1]
0x14003f0b3  cmp     rax, 1
0x14003f0b7  jbe     short loc_14003F0C5
0x14003f0b9  call    cs:__imp_CloseHandle
0x14003f0c0  nop     dword ptr [rax+rax+00h]
0x14003f0c5  lea     rcx, [r13+2140h]; Uuid
0x14003f0cc  xorps   xmm0, xmm0
0x14003f0cf  movdqu  xmmword ptr [rcx], xmm0
0x14003f0d3  call    cs:__imp_UuidCreate
0x14003f0da  nop     dword ptr [rax+rax+00h]
0x14003f0df  mov     ebx, eax
0x14003f0e1  test    eax, eax
0x14003f0e3  jz      short loc_14003F149
0x14003f0e5  cmp     eax, 720h
0x14003f0ea  jz      short loc_14003F149
0x14003f0ec  mov     rcx, [rbp+5Fh]; this
0x14003f0f0  lea     rax, aUuidcreateFail; "UuidCreate failed"
0x14003f0f7  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; unsigned int
0x14003f0fc  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx; wil::details *
0x14003f100  lea     r9, aCdumpprocessor_0; "CDumpProcessor::GenerateIntegratorRepor"...
0x14003f107  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003f10e  mov     edx, 517h; void *
0x14003f113  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14003f118  test    ebx, ebx
0x14003f11a  jle     short loc_14003F125
0x14003f11c  movzx   ebx, bx
0x14003f11f  or      ebx, 80070000h
0x14003f125  mov     eax, 80004005h
0x14003f12a  test    ebx, ebx
0x14003f12c  cmovns  ebx, eax
0x14003f12f  lea     rax, aGenerateintegr; "GenerateIntegratorReportId failed"
0x14003f136  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x14003f13b  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx
0x14003f13f  mov     edx, 2BAh
0x14003f144  jmp     loc_14003F1DA
0x14003f149  mov     ebx, r14d
0x14003f14c  jmp     loc_14003F227
0x14003f151  mov     rcx, [rbp+5Fh]; this
0x14003f155  lea     rax, aSprintfFailed; "Sprintf failed"
0x14003f15c  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; int
0x14003f161  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx; wil::details *
0x14003f165  lea     r9, aCdumpprocessor_2; "CDumpProcessor::CreateMiniDumpFile"
0x14003f16c  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003f173  mov     edx, 28Ch; void *
0x14003f178  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003f17d  jmp     loc_14003F054
0x14003f182  call    cs:__imp_GetLastError
0x14003f189  nop     dword ptr [rax+rax+00h]
0x14003f18e  mov     ebx, eax
0x14003f190  test    eax, eax
0x14003f192  jle     short loc_14003F19D
0x14003f194  movzx   ebx, ax
0x14003f197  or      ebx, 80070000h
0x14003f19d  mov     eax, 80004005h
0x14003f1a2  test    ebx, ebx
0x14003f1a4  cmovns  ebx, eax
0x14003f1a7  lea     rax, aFiletimetoloca; "FileTimeToLocalTime failed"
0x14003f1ae  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x14003f1b3  mov     dword ptr [rsp+0E0h+dwCreationDisposition], ebx
0x14003f1b7  mov     edx, 270h
0x14003f1bc  jmp     short loc_14003F1DA
0x14003f1be  mov     eax, 80004005h
0x14003f1c3  mov     ebx, eax
0x14003f1c5  lea     rdx, aMinidumpdirNot; "Minidumpdir not set"
0x14003f1cc  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rdx; int
  ... truncated ...
```
