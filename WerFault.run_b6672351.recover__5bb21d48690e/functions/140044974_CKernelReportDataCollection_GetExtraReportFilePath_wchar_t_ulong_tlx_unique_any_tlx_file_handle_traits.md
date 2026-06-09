# CKernelReportDataCollection::GetExtraReportFilePath(wchar_t *,ulong,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x140044974`
- end: `0x140044cc9`
- name: `?GetExtraReportFilePath@CKernelReportDataCollection@@AEAAJPEA_WKPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `853`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140045078`

## callees

- `0x140002490`
- `0x14000b50c`
- `0x14000b580`
- `0x140015580`
- `0x1400167a4`
- `0x1400372dc`
- `0x140044974`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044a0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044a0b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140044b5f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140044b5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044b44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044bf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044c58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044c89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044b44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044bf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044c58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044c89`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140044ac9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140044ac9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140044b23`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140044b23`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140044c05`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140044c05`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400449fb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400449fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140044c6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140044c6f`

## string_xrefs

- `0x140044c18`: `StringCchCopy failed`
- `0x140044a30`: `ConvertStringSecurityDescriptorToSecurityDescriptor`
- `0x140044a48`: `CKernelReportDataCollection::GetExtraReportFilePath`
- `0x140044b99`: `CKernelReportDataCollection::GetExtraReportFilePath`
- `0x140044c28`: `CKernelReportDataCollection::GetExtraReportFilePath`
- `0x140044a7a`: `UtilGetTempDirPath failed`
- `0x140044adc`: `WER-%u-%u.sysdata.xml`
- `0x140044b89`: `StringCchPrintf failed while trying to create the file path`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CKernelReportDataCollection::GetExtraReportFilePath(__int64 a1, wchar_t *a2, __int64 a3, void **a4)
{
  wchar_t *v5; // rsi
  void *v6; // r14
  HANDLE v7; // rdi
  PSECURITY_DESCRIPTOR *v8; // rax
  unsigned int v9; // edx
  signed int LastError; // eax
  signed int TempDirPath; // ebx
  const char *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  wchar_t *v15; // r12
  unsigned int v16; // esi
  unsigned __int64 v17; // r13
  DWORD TickCount; // eax
  void *v19; // rcx
  HANDLE v20; // rax
  void *v21; // rcx
  wil::details *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  wil::details *dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  const char *hTemplateFile; // [rsp+30h] [rbp-D0h]
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v27; // [rsp+50h] [rbp-B0h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v5 = a2;
  v27 = a2;
  v6 = 0;
  v7 = 0;
  hMem = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !a2 || !a4 )
    return 2147942487LL;
  v8 = (PSECURITY_DESCRIPTOR *)___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&hMem);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)", 1u, v8, 0) )
  {
    FileName[0] = 0;
    TempDirPath = UtilGetTempDirPath(FileName, v9);
    if ( TempDirPath >= 0 )
    {
      v14 = -1;
      do
        ++v14;
      while ( FileName[v14] );
      v15 = &FileName[(unsigned int)v14];
      SecurityAttributes.nLength = 24;
      SecurityAttributes.bInheritHandle = 0;
      SecurityAttributes.lpSecurityDescriptor = hMem;
      v16 = 0;
      v17 = (unsigned int)(259 - v14);
      while ( 1 )
      {
        TickCount = GetTickCount();
        LODWORD(dwCreationDisposition) = v16;
        TempDirPath = StringCchPrintfW(v15, v17, L"WER-%u-%u.sysdata.xml", TickCount, dwCreationDisposition);
        if ( TempDirPath < 0 )
          break;
        v7 = CreateFileW(FileName, 0x40000000u, 0, &SecurityAttributes, 1u, 0, 0);
        if ( (unsigned __int64)v6 + 1 > 1 )
          CloseHandle(v6);
        if ( (unsigned __int64)v7 + 1 > 1 || (Sleep(0x64u), ++v16, v16 >= 0x14) )
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
      v5 = v27;
      goto LABEL_24;
    }
    v12 = "UtilGetTempDirPath failed";
    v13 = 2547;
  }
  else
  {
    LastError = GetLastError();
    TempDirPath = LastError;
    if ( LastError > 0 )
      TempDirPath = (unsigned __int16)LastError | 0x80070000;
    if ( TempDirPath >= 0 )
      TempDirPath = -2147467259;
    v12 = "ConvertStringSecurityDescriptorToSecurityDescriptor";
    v13 = 2537;
  }
  LODWORD(dwCreationDisposition) = TempDirPath;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)v13,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
    "CKernelReportDataCollection::GetExtraReportFilePath",
    dwCreationDisposition,
    (int)v12,
    hTemplateFile);
LABEL_24:
  if ( (unsigned __int64)v7 + 1 > 1 )
  {
    TempDirPath = StringCchCopyW(v5, 0x104u, FileName);
    if ( TempDirPath >= 0 )
    {
      v20 = v7;
      v7 = 0;
      v21 = *a4;
      *a4 = v20;
      if ( (unsigned __int64)v21 + 1 > 1 )
        CloseHandle(v21);
    }
    else
    {
      v19 = v7;
      v7 = 0;
      if ( (unsigned __int64)v19 + 1 > 1 )
        CloseHandle(v19);
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
  if ( hMem )
    LocalFree(hMem);
  if ( (unsigned __int64)v7 + 1 > 1 )
    CloseHandle(v7);
  return (unsigned int)TempDirPath;
}

```

## disassembly

```asm
0x140044974  mov     [rsp-8+arg_0], rbx
0x140044979  push    rbp
0x14004497a  push    rsi
0x14004497b  push    rdi
0x14004497c  push    r12
0x14004497e  push    r13
0x140044980  push    r14
0x140044982  push    r15
0x140044984  lea     rbp, [rsp-190h]
0x14004498c  sub     rsp, 290h
0x140044993  mov     rax, cs:__security_cookie
0x14004499a  xor     rax, rsp
0x14004499d  mov     [rbp+1C0h+var_40], rax
0x1400449a4  mov     r15, r9
0x1400449a7  mov     rsi, rdx
0x1400449aa  mov     [rsp+2C0h+var_270], rdx
0x1400449af  xor     r14d, r14d
0x1400449b2  mov     edi, r14d
0x1400449b5  mov     [rsp+2C0h+var_280], r14
0x1400449ba  mov     [rsp+2C0h+hMem], r14
0x1400449bf  xorps   xmm0, xmm0
0x1400449c2  xor     eax, eax
0x1400449c4  movups  xmmword ptr [rsp+2C0h+SecurityAttributes.nLength], xmm0
0x1400449c9  mov     qword ptr [rsp+2C0h+SecurityAttributes.bInheritHandle], rax
0x1400449ce  test    rdx, rdx
0x1400449d1  jz      loc_140044C99
0x1400449d7  test    r9, r9
0x1400449da  jz      loc_140044C99
0x1400449e0  lea     rcx, [rsp+2C0h+hMem]
0x1400449e5  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x1400449ea  mov     r8, rax; SecurityDescriptor
0x1400449ed  xor     r9d, r9d; SecurityDescriptorSize
0x1400449f0  lea     edx, [r14+1]; StringSDRevision
0x1400449f4  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x1400449fb  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140044a02  nop     dword ptr [rax+rax+00h]
0x140044a07  test    eax, eax
0x140044a09  jnz     short loc_140044A64
0x140044a0b  call    cs:__imp_GetLastError
0x140044a12  nop     dword ptr [rax+rax+00h]
0x140044a17  mov     ebx, eax
0x140044a19  test    eax, eax
0x140044a1b  jle     short loc_140044A26
0x140044a1d  movzx   ebx, ax
0x140044a20  or      ebx, 80070000h
0x140044a26  mov     eax, 80004005h
0x140044a2b  test    ebx, ebx
0x140044a2d  cmovns  ebx, eax
0x140044a30  lea     rax, aConvertstrings_0; "ConvertStringSecurityDescriptorToSecuri"...
0x140044a37  mov     edx, 9E9h; void *
0x140044a3c  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax; int
0x140044a41  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140044a48  lea     r9, aCkernelreportd_2; "CKernelReportDataCollection::GetExtraRe"...
0x140044a4f  mov     dword ptr [rsp+2C0h+dwCreationDisposition], ebx; wil::details *
0x140044a53  mov     rcx, [rbp+1C8h]; this
0x140044a5a  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140044a5f  jmp     loc_140044BB9
0x140044a64  mov     [rsp+2C0h+FileName], r14w
0x140044a6a  lea     rcx, [rsp+2C0h+FileName]; lpFileName
0x140044a6f  call    ?UtilGetTempDirPath@@YAJPEA_WK@Z; UtilGetTempDirPath(wchar_t *,ulong)
0x140044a74  mov     ebx, eax
0x140044a76  test    eax, eax
0x140044a78  jns     short loc_140044A88
0x140044a7a  lea     rax, aUtilgettempdir; "UtilGetTempDirPath failed"
0x140044a81  mov     edx, 9F3h
0x140044a86  jmp     short loc_140044A3C
0x140044a88  lea     rax, [rsp+2C0h+FileName]
0x140044a8d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140044a91  inc     rcx
0x140044a94  cmp     [rax+rcx*2], r14w
0x140044a99  jnz     short loc_140044A91
0x140044a9b  mov     eax, ecx
0x140044a9d  lea     r12, [rsp+2C0h+FileName]
0x140044aa2  lea     r12, [r12+rax*2]
0x140044aa6  mov     [rsp+2C0h+SecurityAttributes.nLength], 18h
0x140044aae  mov     [rsp+2C0h+SecurityAttributes.bInheritHandle], r14d
0x140044ab3  mov     rax, [rsp+2C0h+hMem]
0x140044ab8  mov     [rsp+2C0h+SecurityAttributes.lpSecurityDescriptor], rax
0x140044abd  mov     esi, r14d
0x140044ac0  mov     r13d, 103h
0x140044ac6  sub     r13d, ecx
0x140044ac9  call    cs:__imp_GetTickCount
0x140044ad0  nop     dword ptr [rax+rax+00h]
0x140044ad5  mov     r9d, eax
0x140044ad8  mov     dword ptr [rsp+2C0h+dwCreationDisposition], esi
0x140044adc  lea     r8, aWerUUSysdataXm; "WER-%u-%u.sysdata.xml"
0x140044ae3  mov     rdx, r13; unsigned __int64
0x140044ae6  mov     rcx, r12; wchar_t *
0x140044ae9  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140044aee  mov     ebx, eax
0x140044af0  test    eax, eax
0x140044af2  js      loc_140044B82
0x140044af8  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x140044b01  mov     [rsp+2C0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140044b09  mov     dword ptr [rsp+2C0h+dwCreationDisposition], 1; dwCreationDisposition
0x140044b11  lea     r9, [rsp+2C0h+SecurityAttributes]; lpSecurityAttributes
0x140044b16  xor     r8d, r8d; dwShareMode
0x140044b19  mov     edx, 40000000h; dwDesiredAccess
0x140044b1e  lea     rcx, [rsp+2C0h+FileName]; lpFileName
0x140044b23  call    cs:__imp_CreateFileW
0x140044b2a  nop     dword ptr [rax+rax+00h]
0x140044b2f  mov     rdi, rax
0x140044b32  mov     [rsp+2C0h+var_280], rax
0x140044b37  lea     rax, [r14+1]
0x140044b3b  cmp     rax, 1
0x140044b3f  jbe     short loc_140044B50
0x140044b41  mov     rcx, r14; hObject
0x140044b44  call    cs:__imp_CloseHandle
0x140044b4b  nop     dword ptr [rax+rax+00h]
0x140044b50  lea     rax, [rdi+1]
0x140044b54  cmp     rax, 1
0x140044b58  ja      short loc_140044B7A
0x140044b5a  mov     ecx, 64h ; 'd'; dwMilliseconds
0x140044b5f  call    cs:__imp_Sleep
0x140044b66  nop     dword ptr [rax+rax+00h]
0x140044b6b  inc     esi
0x140044b6d  cmp     esi, 14h
0x140044b70  jnb     short loc_140044B7A
0x140044b72  mov     r14, rdi
0x140044b75  jmp     loc_140044AC9
0x140044b7a  xor     r14d, r14d
0x140044b7d  mov     ebx, r14d
0x140044b80  jmp     short loc_140044BB4
0x140044b82  mov     rcx, [rbp+1C8h]; this
0x140044b89  lea     rax, aStringcchprint_0; "StringCchPrintf failed while trying to "...
0x140044b90  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax; int
0x140044b95  mov     dword ptr [rsp+2C0h+dwCreationDisposition], ebx; wil::details *
0x140044b99  lea     r9, aCkernelreportd_2; "CKernelReportDataCollection::GetExtraRe"...
0x140044ba0  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140044ba7  mov     edx, 0A11h; void *
0x140044bac  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140044bb1  xor     r14d, r14d
0x140044bb4  mov     rsi, [rsp+2C0h+var_270]
0x140044bb9  lea     rax, [rdi+1]
0x140044bbd  cmp     rax, 1
0x140044bc1  jbe     loc_140044C65
0x140044bc7  lea     r8, [rsp+2C0h+FileName]; wchar_t *
0x140044bcc  mov     edx, 104h; unsigned __int64
0x140044bd1  mov     rcx, rsi; wchar_t *
0x140044bd4  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140044bd9  mov     ebx, eax
0x140044bdb  mov     [rsp+2C0h+var_280], r14
0x140044be0  test    eax, eax
0x140044be2  jns     short loc_140044C42
0x140044be4  mov     rcx, rdi; hObject
0x140044be7  mov     rdi, r14
0x140044bea  lea     rax, [rcx+1]
0x140044bee  cmp     rax, 1
0x140044bf2  jbe     short loc_140044C00
0x140044bf4  call    cs:__imp_CloseHandle
0x140044bfb  nop     dword ptr [rax+rax+00h]
0x140044c00  lea     rcx, [rsp+2C0h+FileName]; lpFileName
0x140044c05  call    cs:__imp_DeleteFileW
0x140044c0c  nop     dword ptr [rax+rax+00h]
0x140044c11  mov     rcx, [rbp+1C8h]; this
0x140044c18  lea     rax, aStringcchcopyF_1; "StringCchCopy failed"
0x140044c1f  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax; int
0x140044c24  mov     dword ptr [rsp+2C0h+dwCreationDisposition], ebx; wil::details *
0x140044c28  lea     r9, aCkernelreportd_2; "CKernelReportDataCollection::GetExtraRe"...
0x140044c2f  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140044c36  mov     edx, 0A36h; void *
0x140044c3b  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140044c40  jmp     short loc_140044C65
0x140044c42  mov     rax, rdi
0x140044c45  mov     rdi, r14
0x140044c48  mov     rcx, [r15]; hObject
0x140044c4b  mov     [r15], rax
0x140044c4e  lea     rax, [rcx+1]
0x140044c52  cmp     rax, 1
0x140044c56  jbe     short loc_140044C65
0x140044c58  call    cs:__imp_CloseHandle
0x140044c5f  nop     dword ptr [rax+rax+00h]
0x140044c64  nop
0x140044c65  mov     rcx, [rsp+2C0h+hMem]; hMem
0x140044c6a  test    rcx, rcx
0x140044c6d  jz      short loc_140044C7C
0x140044c6f  call    cs:__imp_LocalFree
0x140044c76  nop     dword ptr [rax+rax+00h]
0x140044c7b  nop
0x140044c7c  lea     rax, [rdi+1]
0x140044c80  cmp     rax, 1
0x140044c84  jbe     short loc_140044C95
0x140044c86  mov     rcx, rdi; hObject
0x140044c89  call    cs:__imp_CloseHandle
0x140044c90  nop     dword ptr [rax+rax+00h]
0x140044c95  mov     eax, ebx
0x140044c97  jmp     short loc_140044C9E
0x140044c99  mov     eax, 80070057h
0x140044c9e  mov     rcx, [rbp+1C0h+var_40]
0x140044ca5  xor     rcx, rsp; StackCookie
0x140044ca8  call    __security_check_cookie
0x140044cad  mov     rbx, [rsp+2C0h+arg_0]
0x140044cb5  add     rsp, 290h
0x140044cbc  pop     r15
0x140044cbe  pop     r14
0x140044cc0  pop     r13
0x140044cc2  pop     r12
0x140044cc4  pop     rdi
0x140044cc5  pop     rsi
0x140044cc6  pop     rbp
0x140044cc7  retn
```
