# CLiveDumpProcessor::CreateLiveMiniDumpFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x14003e7a0`
- end: `0x14003eab3`
- name: `?CreateLiveMiniDumpFile@CLiveDumpProcessor@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `787`
- prototype: `__int64 __fastcall(__int64, __int64, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14003e3b0`

## callees

- `0x140002728`
- `0x14000c8a0`
- `0x1400126dc`
- `0x140013ff0`
- `0x140034d9c`
- `0x14003e7a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e83c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e8a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e83c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e8a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003e9cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ea1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003e9cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ea1e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14003e88f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14003e88f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003e969`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003e969`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003ea2e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003ea2e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14003e832`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14003e832`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003ea8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003ea8f`

## string_xrefs

- `0x14003e85b`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed`
- `0x14003e8ce`: `Unable to create the folder %ws`
- `0x14003e9a4`: `Copy failed`
- `0x14003e8de`: `CLiveDumpProcessor::CreateLiveMiniDumpFile`
- `0x14003e9f6`: `CLiveDumpProcessor::CreateLiveMiniDumpFile`
- `0x14003ea53`: `CLiveDumpProcessor::CreateLiveMiniDumpFile`
- `0x14003e9e1`: `Live minidump directory not set`

## pseudocode

```c
__int64 __fastcall CLiveDumpProcessor::CreateLiveMiniDumpFile(__int64 a1, __int64 a2, void **a3)
{
  char *v6; // rsi
  const wchar_t *v7; // rdi
  signed int v8; // eax
  signed int v9; // ebx
  signed int LastError; // eax
  __int64 v11; // rbx
  __int64 v12; // r8
  __int64 v13; // rdx
  void *v14; // rcx
  WCHAR *v15; // rcx
  wil::details *dwCreationDisposition; // [rsp+20h] [rbp-60h]
  wil::details *dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  const char *hTemplateFile; // [rsp+30h] [rbp-50h]
  const char *hTemplateFilea; // [rsp+30h] [rbp-50h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-28h] BYREF
  const WCHAR *v23; // [rsp+60h] [rbp-20h]
  _WORD v24[12]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+B8h] [rbp+38h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v27; // [rsp+D8h] [rbp+58h]

  v6 = 0;
  v27 = 0;
  SecurityDescriptor = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  lpFileName = v24;
  v23 = v24;
  v24[0] = 0;
  if ( !a2 || !a3 )
  {
    v9 = -2147024809;
    LODWORD(dwCreationDisposition) = -2147024809;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
      "CLiveDumpProcessor::CreateLiveMiniDumpFile",
      dwCreationDisposition,
      (int)"Invalid args",
      hTemplateFile);
    v15 = (WCHAR *)lpFileName;
    goto LABEL_39;
  }
  v7 = *(const wchar_t **)(a1 + 40);
  if ( v7 && *v7 )
  {
    SecurityDescriptor = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)",
           1u,
           &SecurityDescriptor,
           0) )
    {
      SecurityAttributes.nLength = 24;
      SecurityAttributes.bInheritHandle = 0;
      SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
      if ( CreateDirectoryW(v7, &SecurityAttributes) || GetLastError() == 183 )
      {
        UtilSetPathToSoftReserve(v7);
        v11 = -1;
        v12 = -1;
        do
          ++v12;
        while ( v7[v12] );
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(&lpFileName, v7, v12);
        v13 = *(_QWORD *)(a1 + 104);
        if ( v13 )
        {
          do
            ++v11;
          while ( *(_WORD *)(v13 + 2 * v11) );
        }
        else
        {
          v11 = 0;
        }
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(&lpFileName, v13, v11);
        v6 = (char *)CreateFileW(lpFileName, 0x40040000u, 0, &SecurityAttributes, 1u, 0x80u, 0);
        if ( v6 == (char *)-1LL || v6 + 1 == (char *)1 )
        {
          v9 = -2147467259;
        }
        else
        {
          if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                  a2,
                                  lpFileName,
                                  v23 - lpFileName) )
          {
            v27 = 0;
            v14 = *a3;
            *a3 = v6;
            if ( (unsigned __int64)v14 + 1 > 1 )
              CloseHandle(v14);
            v9 = 0;
            goto LABEL_36;
          }
          v9 = -2147024882;
          LODWORD(dwCreationDispositiona) = -2147024882;
          wil::details::in1diag4::Log_HrMsg(
            retaddr,
            (void *)0xD4,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
            "CLiveDumpProcessor::CreateLiveMiniDumpFile",
            dwCreationDispositiona,
            (int)"Copy failed",
            hTemplateFilea);
        }
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( v9 >= 0 )
          v9 = -2147467259;
        LODWORD(dwCreationDisposition) = v9;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0xAF,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
          "CLiveDumpProcessor::CreateLiveMiniDumpFile",
          dwCreationDisposition,
          (int)"Unable to create the folder %ws",
          (const char *)v7);
      }
    }
    else
    {
      v8 = GetLastError();
      v9 = v8;
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      if ( v9 >= 0 )
        v9 = -2147467259;
      LODWORD(dwCreationDisposition) = v9;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
        "CLiveDumpProcessor::CreateLiveMiniDumpFile",
        dwCreationDisposition,
        (int)"ConvertStringSecurityDescriptorToSecurityDescriptor failed",
        hTemplateFile);
    }
  }
  else
  {
    v9 = -2147467259;
    LODWORD(dwCreationDisposition) = -2147467259;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
      "CLiveDumpProcessor::CreateLiveMiniDumpFile",
      dwCreationDisposition,
      (int)"Live minidump directory not set",
      hTemplateFile);
  }
  v27 = 0;
  if ( (unsigned __int64)(v6 + 1) > 1 )
    CloseHandle(v6);
  v15 = (WCHAR *)lpFileName;
  if ( lpFileName != v23 )
  {
    DeleteFileW(lpFileName);
LABEL_36:
    v15 = (WCHAR *)lpFileName;
  }
LABEL_39:
  if ( v15 != v24 )
    operator delete(v15, (const struct std::nothrow_t *)&std::nothrow);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14003e7a0  mov     [rsp-38h+arg_0], rbx
0x14003e7a5  push    rbp
0x14003e7a6  push    rsi
0x14003e7a7  push    rdi
0x14003e7a8  push    r12
0x14003e7aa  push    r13
0x14003e7ac  push    r14
0x14003e7ae  push    r15
0x14003e7b0  mov     rbp, rsp
0x14003e7b3  sub     rsp, 80h
0x14003e7ba  mov     r14, r8
0x14003e7bd  mov     r12, rdx
0x14003e7c0  mov     r15, rcx
0x14003e7c3  xor     r13d, r13d
0x14003e7c6  mov     esi, r13d
0x14003e7c9  mov     [rbp+arg_18], r13
0x14003e7cd  mov     [rbp+SecurityDescriptor], r13
0x14003e7d1  xorps   xmm0, xmm0
0x14003e7d4  xor     eax, eax
0x14003e7d6  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x14003e7da  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x14003e7de  lea     rax, [rbp+var_18]
0x14003e7e2  mov     [rbp+lpFileName], rax
0x14003e7e6  lea     rax, [rbp+var_18]
0x14003e7ea  mov     [rbp+var_20], rax
0x14003e7ee  mov     [rbp+var_18], r13w
0x14003e7f3  test    rdx, rdx
0x14003e7f6  jz      loc_14003EA3A
0x14003e7fc  test    r8, r8
0x14003e7ff  jz      loc_14003EA3A
0x14003e805  mov     rdi, [rcx+28h]
0x14003e809  test    rdi, rdi
0x14003e80c  jz      loc_14003E9DA
0x14003e812  cmp     [rdi], r13w
0x14003e816  jz      loc_14003E9DA
0x14003e81c  mov     [rbp+SecurityDescriptor], r13
0x14003e820  xor     r9d, r9d; SecurityDescriptorSize
0x14003e823  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14003e827  lea     edx, [r13+1]; StringSDRevision
0x14003e82b  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x14003e832  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14003e838  test    eax, eax
0x14003e83a  jnz     short loc_14003E875
0x14003e83c  call    cs:__imp_GetLastError
0x14003e842  mov     ebx, eax
0x14003e844  test    eax, eax
0x14003e846  jle     short loc_14003E851
0x14003e848  movzx   ebx, ax
0x14003e84b  or      ebx, 80070000h
0x14003e851  mov     eax, 80004005h
0x14003e856  test    ebx, ebx
0x14003e858  cmovns  ebx, eax
0x14003e85b  lea     rax, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x14003e862  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax
0x14003e867  mov     dword ptr [rsp+80h+dwCreationDisposition], ebx
0x14003e86b  mov     edx, 9Fh
0x14003e870  jmp     loc_14003E9F6
0x14003e875  mov     [rbp+SecurityAttributes.nLength], 18h
0x14003e87c  mov     [rbp+SecurityAttributes.bInheritHandle], r13d
0x14003e880  mov     rax, [rbp+SecurityDescriptor]
0x14003e884  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x14003e888  lea     rdx, [rbp+SecurityAttributes]; lpSecurityAttributes
0x14003e88c  mov     rcx, rdi; lpPathName
0x14003e88f  call    cs:__imp_CreateDirectoryW
0x14003e895  test    eax, eax
0x14003e897  jnz     short loc_14003E8FB
0x14003e899  call    cs:__imp_GetLastError
0x14003e89f  cmp     eax, 0B7h
0x14003e8a4  jz      short loc_14003E8FB
0x14003e8a6  call    cs:__imp_GetLastError
0x14003e8ac  mov     ebx, eax
0x14003e8ae  test    eax, eax
0x14003e8b0  jle     short loc_14003E8BB
0x14003e8b2  movzx   ebx, ax
0x14003e8b5  or      ebx, 80070000h
0x14003e8bb  mov     eax, 80004005h
0x14003e8c0  test    ebx, ebx
0x14003e8c2  cmovns  ebx, eax
0x14003e8c5  mov     rcx, [rbp+38h]; this
0x14003e8c9  mov     [rsp+80h+hTemplateFile], rdi; char *
0x14003e8ce  lea     rax, aUnableToCreate; "Unable to create the folder %ws"
0x14003e8d5  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax; int
0x14003e8da  mov     dword ptr [rsp+80h+dwCreationDisposition], ebx; wil::details *
0x14003e8de  lea     r9, aClivedumpproce_6; "CLiveDumpProcessor::CreateLiveMiniDumpF"...
0x14003e8e5  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003e8ec  mov     edx, 0AFh; void *
0x14003e8f1  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003e8f6  jmp     loc_14003EA0D
0x14003e8fb  mov     rcx, rdi; wchar_t *
0x14003e8fe  call    ?UtilSetPathToSoftReserve@@YAJPEB_W@Z; UtilSetPathToSoftReserve(wchar_t const *)
0x14003e903  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14003e907  mov     r8, rbx
0x14003e90a  inc     r8
0x14003e90d  cmp     [rdi+r8*2], r13w
0x14003e912  jnz     short loc_14003E90A
0x14003e914  mov     rdx, rdi
0x14003e917  lea     rcx, [rbp+lpFileName]
0x14003e91b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003e920  mov     rdx, [r15+68h]
0x14003e924  test    rdx, rdx
0x14003e927  jz      short loc_14003E935
0x14003e929  inc     rbx
0x14003e92c  cmp     [rdx+rbx*2], r13w
0x14003e931  jnz     short loc_14003E929
0x14003e933  jmp     short loc_14003E938
0x14003e935  mov     rbx, r13
0x14003e938  mov     r8, rbx
0x14003e93b  lea     rcx, [rbp+lpFileName]
0x14003e93f  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14003e944  mov     [rsp+80h+hTemplateFile], r13; hTemplateFile
0x14003e949  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14003e951  mov     dword ptr [rsp+80h+dwCreationDisposition], 1; dwCreationDisposition
0x14003e959  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x14003e95d  xor     r8d, r8d; dwShareMode
0x14003e960  mov     edx, 40040000h; dwDesiredAccess
0x14003e965  mov     rcx, [rbp+lpFileName]; lpFileName
0x14003e969  call    cs:__imp_CreateFileW
0x14003e96f  mov     rsi, rax
0x14003e972  inc     rax
0x14003e975  cmp     rax, 1
0x14003e979  ja      short loc_14003E985
0x14003e97b  mov     ebx, 80004005h
0x14003e980  jmp     loc_14003EA0D
0x14003e985  mov     r8, [rbp+var_20]
0x14003e989  mov     rdx, [rbp+lpFileName]
0x14003e98d  sub     r8, rdx
0x14003e990  sar     r8, 1
0x14003e993  mov     rcx, r12
0x14003e996  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003e99b  test    al, al
0x14003e99d  jnz     short loc_14003E9BB
0x14003e99f  mov     ebx, 8007000Eh
0x14003e9a4  lea     rax, aCopyFailed; "Copy failed"
0x14003e9ab  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax
0x14003e9b0  mov     dword ptr [rsp+80h+dwCreationDisposition], ebx
0x14003e9b4  mov     edx, 0D4h
0x14003e9b9  jmp     short loc_14003E9F6
0x14003e9bb  mov     [rbp+arg_18], r13
0x14003e9bf  mov     rcx, [r14]; hObject
0x14003e9c2  mov     [r14], rsi
0x14003e9c5  lea     rax, [rcx+1]
0x14003e9c9  cmp     rax, 1
0x14003e9cd  jbe     short loc_14003E9D5
0x14003e9cf  call    cs:__imp_CloseHandle
0x14003e9d5  mov     ebx, r13d
0x14003e9d8  jmp     short loc_14003EA34
0x14003e9da  mov     eax, 80004005h
0x14003e9df  mov     ebx, eax
0x14003e9e1  lea     rdx, aLiveMinidumpDi; "Live minidump directory not set"
0x14003e9e8  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rdx; int
0x14003e9ed  mov     dword ptr [rsp+80h+dwCreationDisposition], eax; wil::details *
0x14003e9f1  mov     edx, 92h; void *
0x14003e9f6  lea     r9, aClivedumpproce_6; "CLiveDumpProcessor::CreateLiveMiniDumpF"...
0x14003e9fd  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003ea04  mov     rcx, [rbp+38h]; this
0x14003ea08  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ea0d  mov     [rbp+arg_18], r13
0x14003ea11  lea     rax, [rsi+1]
0x14003ea15  cmp     rax, 1
0x14003ea19  jbe     short loc_14003EA24
0x14003ea1b  mov     rcx, rsi; hObject
0x14003ea1e  call    cs:__imp_CloseHandle
0x14003ea24  mov     rcx, [rbp+lpFileName]; lpFileName
0x14003ea28  cmp     rcx, [rbp+var_20]
0x14003ea2c  jz      short loc_14003EA38
0x14003ea2e  call    cs:__imp_DeleteFileW
0x14003ea34  mov     rcx, [rbp+lpFileName]
0x14003ea38  jmp     short loc_14003EA70
0x14003ea3a  mov     rcx, [rbp+38h]; this
0x14003ea3e  lea     rax, aInvalidArgs; "Invalid args"
0x14003ea45  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax; int
0x14003ea4a  mov     ebx, 80070057h
0x14003ea4f  mov     dword ptr [rsp+80h+dwCreationDisposition], ebx; wil::details *
0x14003ea53  lea     r9, aClivedumpproce_6; "CLiveDumpProcessor::CreateLiveMiniDumpF"...
0x14003ea5a  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003ea61  mov     edx, 87h; void *
0x14003ea66  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ea6b  nop
0x14003ea6c  mov     rcx, [rbp+lpFileName]; void *
0x14003ea70  lea     rax, [rbp+var_18]
0x14003ea74  cmp     rcx, rax
0x14003ea77  jz      short loc_14003EA86
0x14003ea79  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003ea80  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003ea85  nop
0x14003ea86  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x14003ea8a  test    rcx, rcx
0x14003ea8d  jz      short loc_14003EA96
0x14003ea8f  call    cs:__imp_LocalFree
0x14003ea95  nop
0x14003ea96  mov     eax, ebx
0x14003ea98  mov     rbx, [rsp+80h+arg_0]
0x14003eaa0  add     rsp, 80h
0x14003eaa7  pop     r15
0x14003eaa9  pop     r14
0x14003eaab  pop     r13
0x14003eaad  pop     r12
0x14003eaaf  pop     rdi
0x14003eab0  pop     rsi
0x14003eab1  pop     rbp
0x14003eab2  retn
```
