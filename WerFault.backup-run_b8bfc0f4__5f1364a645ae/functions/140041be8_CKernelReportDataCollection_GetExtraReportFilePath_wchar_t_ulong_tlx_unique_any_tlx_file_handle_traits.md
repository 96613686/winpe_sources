# CKernelReportDataCollection::GetExtraReportFilePath(wchar_t *,ulong,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x140041be8`
- end: `0x140041eed`
- name: `?GetExtraReportFilePath@CKernelReportDataCollection@@AEAAJPEA_WKPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `773`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140042250`

## callees

- `0x140002470`
- `0x14000b4cc`
- `0x14000b540`
- `0x140014a94`
- `0x140034d9c`
- `0x140041be8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041c70`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140041da8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140041da8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041d93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041e37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041e8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041eb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041d93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041e37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041e8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041eb4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140041d28`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140041d28`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140041d78`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140041d78`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140041e42`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140041e42`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140041c66`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140041c66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140041ea0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140041ea0`

## string_xrefs

- `0x140041e4f`: `StringCchCopy failed`
- `0x140041c8f`: `ConvertStringSecurityDescriptorToSecurityDescriptor`
- `0x140041ca7`: `CKernelReportDataCollection::GetExtraReportFilePath`
- `0x140041ddc`: `CKernelReportDataCollection::GetExtraReportFilePath`
- `0x140041e5f`: `CKernelReportDataCollection::GetExtraReportFilePath`
- `0x140041cd9`: `UtilGetTempDirPath failed`
- `0x140041d35`: `WER-%u-%u.sysdata.xml`
- `0x140041dcc`: `StringCchPrintf failed while trying to create the file path`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CKernelReportDataCollection::GetExtraReportFilePath(__int64 a1, wchar_t *a2, __int64 a3, void **a4)
{
  wchar_t *v5; // rsi
  void *v6; // r14
  HANDLE v7; // rdi
  unsigned int v8; // edx
  signed int LastError; // eax
  signed int TempDirPath; // ebx
  const char *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  wchar_t *v14; // r12
  unsigned int v15; // esi
  unsigned __int64 v16; // r13
  DWORD TickCount; // eax
  void *v18; // rcx
  HANDLE v19; // rax
  void *v20; // rcx
  wil::details *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  wil::details *dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  const char *hTemplateFile; // [rsp+30h] [rbp-D0h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v26; // [rsp+50h] [rbp-B0h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v5 = a2;
  v26 = a2;
  v6 = 0;
  v7 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !a2 || !a4 )
    return 2147942487LL;
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    FileName[0] = 0;
    TempDirPath = UtilGetTempDirPath(FileName, v8);
    if ( TempDirPath >= 0 )
    {
      v13 = -1;
      do
        ++v13;
      while ( FileName[v13] );
      v14 = &FileName[(unsigned int)v13];
      SecurityAttributes.nLength = 24;
      SecurityAttributes.bInheritHandle = 0;
      SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
      v15 = 0;
      v16 = (unsigned int)(259 - v13);
      while ( 1 )
      {
        TickCount = GetTickCount();
        LODWORD(dwCreationDisposition) = v15;
        TempDirPath = StringCchPrintfW(v14, v16, L"WER-%u-%u.sysdata.xml", TickCount, dwCreationDisposition);
        if ( TempDirPath < 0 )
          break;
        v7 = CreateFileW(FileName, 0x40000000u, 0, &SecurityAttributes, 1u, 0, 0);
        if ( (unsigned __int64)v6 + 1 > 1 )
          CloseHandle(v6);
        if ( (unsigned __int64)v7 + 1 > 1 || (Sleep(0x64u), ++v15, v15 >= 0x14) )
        {
          TempDirPath = 0;
          goto LABEL_23;
        }
        v6 = v7;
      }
      LODWORD(dwCreationDispositiona) = TempDirPath;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0xA11,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
        "CKernelReportDataCollection::GetExtraReportFilePath",
        dwCreationDispositiona,
        (int)"StringCchPrintf failed while trying to create the file path",
        hTemplateFile);
LABEL_23:
      v5 = v26;
      goto LABEL_24;
    }
    v11 = "UtilGetTempDirPath failed";
    v12 = 2547;
  }
  else
  {
    LastError = GetLastError();
    TempDirPath = LastError;
    if ( LastError > 0 )
      TempDirPath = (unsigned __int16)LastError | 0x80070000;
    if ( TempDirPath >= 0 )
      TempDirPath = -2147467259;
    v11 = "ConvertStringSecurityDescriptorToSecurityDescriptor";
    v12 = 2537;
  }
  LODWORD(dwCreationDisposition) = TempDirPath;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
    "CKernelReportDataCollection::GetExtraReportFilePath",
    dwCreationDisposition,
    (int)v11,
    hTemplateFile);
LABEL_24:
  if ( (unsigned __int64)v7 + 1 > 1 )
  {
    TempDirPath = StringCchCopyW(v5, 0x104u, FileName);
    if ( TempDirPath >= 0 )
    {
      v19 = v7;
      v7 = 0;
      v20 = *a4;
      *a4 = v19;
      if ( (unsigned __int64)v20 + 1 > 1 )
        CloseHandle(v20);
    }
    else
    {
      v18 = v7;
      v7 = 0;
      if ( (unsigned __int64)v18 + 1 > 1 )
        CloseHandle(v18);
      DeleteFileW(FileName);
      LODWORD(dwCreationDisposition) = TempDirPath;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0xA36,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
        "CKernelReportDataCollection::GetExtraReportFilePath",
        dwCreationDisposition,
        (int)"StringCchCopy failed",
        hTemplateFile);
    }
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( (unsigned __int64)v7 + 1 > 1 )
    CloseHandle(v7);
  return (unsigned int)TempDirPath;
}

```

## disassembly

```asm
0x140041be8  mov     [rsp-8+arg_0], rbx
0x140041bed  push    rbp
0x140041bee  push    rsi
0x140041bef  push    rdi
0x140041bf0  push    r12
0x140041bf2  push    r13
0x140041bf4  push    r14
0x140041bf6  push    r15
0x140041bf8  lea     rbp, [rsp-190h]
0x140041c00  sub     rsp, 290h
0x140041c07  mov     rax, cs:__security_cookie
0x140041c0e  xor     rax, rsp
0x140041c11  mov     [rbp+1C0h+var_40], rax
0x140041c18  mov     r15, r9
0x140041c1b  mov     rsi, rdx
0x140041c1e  mov     [rsp+2C0h+var_270], rdx
0x140041c23  xor     r14d, r14d
0x140041c26  mov     edi, r14d
0x140041c29  mov     [rsp+2C0h+var_280], r14
0x140041c2e  xorps   xmm0, xmm0
0x140041c31  xor     eax, eax
0x140041c33  movups  xmmword ptr [rsp+2C0h+SecurityAttributes.nLength], xmm0
0x140041c38  mov     qword ptr [rsp+2C0h+SecurityAttributes.bInheritHandle], rax
0x140041c3d  test    rdx, rdx
0x140041c40  jz      loc_140041EBE
0x140041c46  test    r9, r9
0x140041c49  jz      loc_140041EBE
0x140041c4f  mov     [rsp+2C0h+SecurityDescriptor], r14
0x140041c54  xor     r9d, r9d; SecurityDescriptorSize
0x140041c57  lea     r8, [rsp+2C0h+SecurityDescriptor]; SecurityDescriptor
0x140041c5c  lea     edx, [rax+1]; StringSDRevision
0x140041c5f  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x140041c66  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140041c6c  test    eax, eax
0x140041c6e  jnz     short loc_140041CC3
0x140041c70  call    cs:__imp_GetLastError
0x140041c76  mov     ebx, eax
0x140041c78  test    eax, eax
0x140041c7a  jle     short loc_140041C85
0x140041c7c  movzx   ebx, ax
0x140041c7f  or      ebx, 80070000h
0x140041c85  mov     eax, 80004005h
0x140041c8a  test    ebx, ebx
0x140041c8c  cmovns  ebx, eax
0x140041c8f  lea     rax, aConvertstrings_0; "ConvertStringSecurityDescriptorToSecuri"...
0x140041c96  mov     edx, 9E9h; void *
0x140041c9b  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax; int
0x140041ca0  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140041ca7  lea     r9, aCkernelreportd_2; "CKernelReportDataCollection::GetExtraRe"...
0x140041cae  mov     dword ptr [rsp+2C0h+dwCreationDisposition], ebx; wil::details *
0x140041cb2  mov     rcx, [rbp+1C8h]; this
0x140041cb9  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140041cbe  jmp     loc_140041DFC
0x140041cc3  mov     [rsp+2C0h+FileName], r14w
0x140041cc9  lea     rcx, [rsp+2C0h+FileName]; lpFileName
0x140041cce  call    ?UtilGetTempDirPath@@YAJPEA_WK@Z; UtilGetTempDirPath(wchar_t *,ulong)
0x140041cd3  mov     ebx, eax
0x140041cd5  test    eax, eax
0x140041cd7  jns     short loc_140041CE7
0x140041cd9  lea     rax, aUtilgettempdir; "UtilGetTempDirPath failed"
0x140041ce0  mov     edx, 9F3h
0x140041ce5  jmp     short loc_140041C9B
0x140041ce7  lea     rax, [rsp+2C0h+FileName]
0x140041cec  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140041cf0  inc     rcx
0x140041cf3  cmp     [rax+rcx*2], r14w
0x140041cf8  jnz     short loc_140041CF0
0x140041cfa  mov     eax, ecx
0x140041cfc  lea     r12, [rsp+2C0h+FileName]
0x140041d01  lea     r12, [r12+rax*2]
0x140041d05  mov     [rsp+2C0h+SecurityAttributes.nLength], 18h
0x140041d0d  mov     [rsp+2C0h+SecurityAttributes.bInheritHandle], r14d
0x140041d12  mov     rax, [rsp+2C0h+SecurityDescriptor]
0x140041d17  mov     [rsp+2C0h+SecurityAttributes.lpSecurityDescriptor], rax
0x140041d1c  mov     esi, r14d
0x140041d1f  mov     r13d, 103h
0x140041d25  sub     r13d, ecx
0x140041d28  call    cs:__imp_GetTickCount
0x140041d2e  mov     r9d, eax
0x140041d31  mov     dword ptr [rsp+2C0h+dwCreationDisposition], esi
0x140041d35  lea     r8, aWerUUSysdataXm; "WER-%u-%u.sysdata.xml"
0x140041d3c  mov     rdx, r13; unsigned __int64
0x140041d3f  mov     rcx, r12; wchar_t *
0x140041d42  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140041d47  mov     ebx, eax
0x140041d49  test    eax, eax
0x140041d4b  js      short loc_140041DC5
0x140041d4d  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x140041d56  mov     [rsp+2C0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140041d5e  mov     dword ptr [rsp+2C0h+dwCreationDisposition], 1; dwCreationDisposition
0x140041d66  lea     r9, [rsp+2C0h+SecurityAttributes]; lpSecurityAttributes
0x140041d6b  xor     r8d, r8d; dwShareMode
0x140041d6e  mov     edx, 40000000h; dwDesiredAccess
0x140041d73  lea     rcx, [rsp+2C0h+FileName]; lpFileName
0x140041d78  call    cs:__imp_CreateFileW
0x140041d7e  mov     rdi, rax
0x140041d81  mov     [rsp+2C0h+var_280], rax
0x140041d86  lea     rax, [r14+1]
0x140041d8a  cmp     rax, 1
0x140041d8e  jbe     short loc_140041D99
0x140041d90  mov     rcx, r14; hObject
0x140041d93  call    cs:__imp_CloseHandle
0x140041d99  lea     rax, [rdi+1]
0x140041d9d  cmp     rax, 1
0x140041da1  ja      short loc_140041DBD
0x140041da3  mov     ecx, 64h ; 'd'; dwMilliseconds
0x140041da8  call    cs:__imp_Sleep
0x140041dae  inc     esi
0x140041db0  cmp     esi, 14h
0x140041db3  jnb     short loc_140041DBD
0x140041db5  mov     r14, rdi
0x140041db8  jmp     loc_140041D28
0x140041dbd  xor     r14d, r14d
0x140041dc0  mov     ebx, r14d
0x140041dc3  jmp     short loc_140041DF7
0x140041dc5  mov     rcx, [rbp+1C8h]; this
0x140041dcc  lea     rax, aStringcchprint_0; "StringCchPrintf failed while trying to "...
0x140041dd3  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax; int
0x140041dd8  mov     dword ptr [rsp+2C0h+dwCreationDisposition], ebx; wil::details *
0x140041ddc  lea     r9, aCkernelreportd_2; "CKernelReportDataCollection::GetExtraRe"...
0x140041de3  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140041dea  mov     edx, 0A11h; void *
0x140041def  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140041df4  xor     r14d, r14d
0x140041df7  mov     rsi, [rsp+2C0h+var_270]
0x140041dfc  lea     rax, [rdi+1]
0x140041e00  cmp     rax, 1
0x140041e04  jbe     loc_140041E96
0x140041e0a  lea     r8, [rsp+2C0h+FileName]; wchar_t *
0x140041e0f  mov     edx, 104h; unsigned __int64
0x140041e14  mov     rcx, rsi; wchar_t *
0x140041e17  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140041e1c  mov     ebx, eax
0x140041e1e  mov     [rsp+2C0h+var_280], r14
0x140041e23  test    eax, eax
0x140041e25  jns     short loc_140041E79
0x140041e27  mov     rcx, rdi; hObject
0x140041e2a  mov     rdi, r14
0x140041e2d  lea     rax, [rcx+1]
0x140041e31  cmp     rax, 1
0x140041e35  jbe     short loc_140041E3D
0x140041e37  call    cs:__imp_CloseHandle
0x140041e3d  lea     rcx, [rsp+2C0h+FileName]; lpFileName
0x140041e42  call    cs:__imp_DeleteFileW
0x140041e48  mov     rcx, [rbp+1C8h]; this
0x140041e4f  lea     rax, aStringcchcopyF_1; "StringCchCopy failed"
0x140041e56  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax; int
0x140041e5b  mov     dword ptr [rsp+2C0h+dwCreationDisposition], ebx; wil::details *
0x140041e5f  lea     r9, aCkernelreportd_2; "CKernelReportDataCollection::GetExtraRe"...
0x140041e66  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140041e6d  mov     edx, 0A36h; void *
0x140041e72  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140041e77  jmp     short loc_140041E96
0x140041e79  mov     rax, rdi
0x140041e7c  mov     rdi, r14
0x140041e7f  mov     rcx, [r15]; hObject
0x140041e82  mov     [r15], rax
0x140041e85  lea     rax, [rcx+1]
0x140041e89  cmp     rax, 1
0x140041e8d  jbe     short loc_140041E96
0x140041e8f  call    cs:__imp_CloseHandle
0x140041e95  nop
0x140041e96  mov     rcx, [rsp+2C0h+SecurityDescriptor]; hMem
0x140041e9b  test    rcx, rcx
0x140041e9e  jz      short loc_140041EA7
0x140041ea0  call    cs:__imp_LocalFree
0x140041ea6  nop
0x140041ea7  lea     rax, [rdi+1]
0x140041eab  cmp     rax, 1
0x140041eaf  jbe     short loc_140041EBA
0x140041eb1  mov     rcx, rdi; hObject
0x140041eb4  call    cs:__imp_CloseHandle
0x140041eba  mov     eax, ebx
0x140041ebc  jmp     short loc_140041EC3
0x140041ebe  mov     eax, 80070057h
0x140041ec3  mov     rcx, [rbp+1C0h+var_40]
0x140041eca  xor     rcx, rsp; StackCookie
0x140041ecd  call    __security_check_cookie
0x140041ed2  mov     rbx, [rsp+2C0h+arg_0]
0x140041eda  add     rsp, 290h
0x140041ee1  pop     r15
0x140041ee3  pop     r14
0x140041ee5  pop     r13
0x140041ee7  pop     r12
0x140041ee9  pop     rdi
0x140041eea  pop     rsi
0x140041eeb  pop     rbp
0x140041eec  retn
```
