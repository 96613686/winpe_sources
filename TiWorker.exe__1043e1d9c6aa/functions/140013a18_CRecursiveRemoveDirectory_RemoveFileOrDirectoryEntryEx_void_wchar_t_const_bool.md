# CRecursiveRemoveDirectory::RemoveFileOrDirectoryEntryEx(void *,wchar_t const *,bool)

- ea: `0x140013a18`
- end: `0x140013d41`
- name: `?RemoveFileOrDirectoryEntryEx@CRecursiveRemoveDirectory@@AEAAJPEAXPEB_W_N@Z`
- size: `809`
- prototype: `__int64 __fastcall(CRecursiveRemoveDirectory *this, void *, const wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x140012c58`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x14000e66c`
- `0x14000ebb4`
- `0x1400123a4`
- `0x1400129b8`
- `0x140013a18`
- `0x1400141ac`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013cdb`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140013c18`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140013cd1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140013c18`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140013cd1`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x140013be6`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x140013be6`

## string_xrefs

- `0x140013a7c`: `No path specified`
- `0x140013b48`: `Failed to open {} for deletion`
- `0x140013c5b`: `Failed clearing read-only attribute on: {}`
- `0x140013cb2`: `Unable to mark: {} as delete on close`
- `0x140013cf7`: `Unable to restore read-only attribute on: {} after setting delete on close`

## pseudocode

```c
__int64 __fastcall CRecursiveRemoveDirectory::RemoveFileOrDirectoryEntryEx(
        CRecursiveRemoveDirectory *this,
        void *a2,
        const wchar_t *a3)
{
  int v3; // ebx
  signed int v5; // ebx
  int v6; // edx
  __int64 v7; // rdx
  __int64 InitPointer; // rax
  int v9; // r8d
  int v10; // r9d
  int v11; // eax
  int v12; // edx
  __int64 (__fastcall *v13)(_QWORD, const wchar_t *, HANDLE); // rax
  int v14; // esi
  signed int LastError; // eax
  int v16; // edx
  int v17; // eax
  __int64 v18; // rcx
  signed int v19; // eax
  __int64 v20; // rcx
  bool v21; // sf
  int v23; // [rsp+20h] [rbp-60h]
  int v24[2]; // [rsp+30h] [rbp-50h] BYREF
  const wchar_t *v25; // [rsp+38h] [rbp-48h] BYREF
  int v26; // [rsp+40h] [rbp-40h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-38h] BYREF
  _OWORD FileInformation[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v29; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v25 = a3;
  hFile = 0;
  v29 = 0;
  v3 = (int)a2;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( !a3 )
  {
    v5 = -2147024809;
    v26 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No path specified");
      *(_QWORD *)v24 = &v26;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v6,
        3,
        (unsigned int)": {}",
        (__int64)v24);
    }
    v7 = 1034;
    goto LABEL_15;
  }
  InitPointer = Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&hFile);
  v11 = OpenFileRelativeToParent(v3, (_DWORD)v25, v9, v10, 0, InitPointer);
  v5 = v11;
  if ( (unsigned int)(v11 + 2147024894) > 1
    && v11 != -2147024773
    && v11 != -2147022975
    && (unsigned int)(v11 + 805306317) > 1
    && v11 != -805306310
    && v11 != -805305728 )
  {
    if ( v11 >= 0 )
    {
      v13 = (__int64 (__fastcall *)(_QWORD, const wchar_t *, HANDLE))*((_QWORD *)this + 1);
      if ( v13 )
      {
        v5 = v13(*(_QWORD *)this, v25, hFile);
        if ( v5 < 0 )
          goto LABEL_36;
      }
      v5 = CRecursiveRemoveDirectory::UnlinkOrDelete(this, hFile);
      if ( v5 != -2147024891 )
        goto LABEL_36;
      if ( !GetFileInformationByHandleEx(hFile, FileBasicInfo, FileInformation, 0x28u) || (v14 = v29, (v29 & 1) == 0) )
      {
        v5 = -2147024891;
        goto LABEL_36;
      }
      LODWORD(v29) = 128;
      if ( SetFileInformationByHandle(hFile, FileBasicInfo, FileInformation, 0x28u) )
        goto LABEL_28;
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
      {
LABEL_28:
        v17 = CRecursiveRemoveDirectory::UnlinkOrDelete(this, hFile);
        v5 = v17;
        if ( v17 < 0 )
          LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
            v18,
            (unsigned int)v17,
            "Unable to mark: {} as delete on close",
            &v25);
        LODWORD(v29) = v14;
        if ( !SetFileInformationByHandle(hFile, FileBasicInfo, FileInformation, 0x28u) )
        {
          v19 = GetLastError();
          v21 = v19 < 0;
          if ( v19 > 0 )
          {
            v19 = (unsigned __int16)v19 | 0x80070000;
            v21 = v19 < 0;
          }
          if ( v21 )
            LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
              v20,
              (unsigned int)v19,
              "Unable to restore read-only attribute on: {} after setting delete on close",
              &v25);
        }
        goto LABEL_36;
      }
      v26 = v5;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed clearing read-only attribute on: {}",
          (__int64)&v25);
        *(_QWORD *)v24 = &v26;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v16,
          3,
          (unsigned int)": {}",
          (__int64)v24);
      }
      v7 = 1101;
    }
    else
    {
      v26 = v11;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to open {} for deletion",
          (__int64)&v25);
        *(_QWORD *)v24 = &v26;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v12,
          3,
          (unsigned int)": {}",
          (__int64)v24);
      }
      v7 = 1055;
    }
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v5,
      v23);
LABEL_36:
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
    return (unsigned int)v5;
  }
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
  return 0;
}

```

## disassembly

```asm
0x140013a18  mov     [rsp-18h+arg_18], rbx
0x140013a1d  push    rbp
0x140013a1e  push    rsi
0x140013a1f  push    rdi
0x140013a20  mov     rbp, rsp
0x140013a23  sub     rsp, 80h
0x140013a2a  mov     rax, cs:__security_cookie
0x140013a31  xor     rax, rsp
0x140013a34  mov     [rbp+var_8], rax
0x140013a38  xor     eax, eax
0x140013a3a  mov     [rbp+var_48], r8
0x140013a3e  mov     [rbp+hFile], 0
0x140013a46  xorps   xmm0, xmm0
0x140013a49  mov     [rbp+var_10], rax
0x140013a4d  mov     rbx, rdx
0x140013a50  mov     rdi, rcx
0x140013a53  movups  [rbp+FileInformation], xmm0
0x140013a57  movups  [rbp+var_20], xmm0
0x140013a5b  test    r8, r8
0x140013a5e  jnz     short loc_140013AB9
0x140013a60  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013a67  mov     ebx, 80070057h
0x140013a6c  mov     [rbp+var_40], ebx
0x140013a6f  test    rcx, rcx
0x140013a72  jz      short loc_140013AAF
0x140013a74  lea     edi, [rax+3]
0x140013a77  xor     edx, edx
0x140013a79  mov     r8d, edi
0x140013a7c  lea     r9, aNoPathSpecifie; "No path specified"
0x140013a83  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140013a88  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013a8f  lea     rax, [rbp+var_40]
0x140013a93  mov     qword ptr [rbp+var_50], rax
0x140013a97  lea     r9, asc_140030534; ": {}"
0x140013a9e  lea     rax, [rbp+var_50]
0x140013aa2  mov     r8d, edi
0x140013aa5  mov     qword ptr [rsp+80h+var_60], rax
0x140013aaa  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140013aaf  mov     edx, 40Ah
0x140013ab4  jmp     loc_140013B82
0x140013ab9  lea     rcx, [rbp+hFile]
0x140013abd  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x140013ac2  mov     rdx, [rbp+var_48]
0x140013ac6  mov     rcx, rbx
0x140013ac9  mov     [rsp+80h+var_58], rax
0x140013ace  mov     byte ptr [rsp+80h+var_60], 0
0x140013ad3  call    OpenFileRelativeToParent
0x140013ad8  mov     ebx, eax
0x140013ada  lea     ecx, [rax+7FF8FFFEh]
0x140013ae0  cmp     ecx, 1
0x140013ae3  jbe     loc_140013D17
0x140013ae9  cmp     eax, 8007007Bh
0x140013aee  jz      loc_140013D17
0x140013af4  cmp     eax, 80070781h
0x140013af9  jz      loc_140013D17
0x140013aff  lea     ecx, [rax+2FFFFFCDh]
0x140013b05  cmp     ecx, 1
0x140013b08  jbe     loc_140013D17
0x140013b0e  cmp     eax, 0D000003Ah
0x140013b13  jz      loc_140013D17
0x140013b19  cmp     eax, 0D0000280h
0x140013b1e  jz      loc_140013D17
0x140013b24  test    eax, eax
0x140013b26  jns     short loc_140013B9A
0x140013b28  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013b2f  mov     [rbp+var_40], eax
0x140013b32  test    rcx, rcx
0x140013b35  jz      short loc_140013B7D
0x140013b37  lea     rax, [rbp+var_48]
0x140013b3b  mov     edi, 3
0x140013b40  mov     r8d, edi
0x140013b43  mov     qword ptr [rsp+80h+var_60], rax
0x140013b48  lea     r9, aFailedToOpenFo; "Failed to open {} for deletion"
0x140013b4f  xor     edx, edx
0x140013b51  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140013b56  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013b5d  lea     rax, [rbp+var_40]
0x140013b61  mov     qword ptr [rbp+var_50], rax
0x140013b65  lea     r9, asc_140030534; ": {}"
0x140013b6c  lea     rax, [rbp+var_50]
0x140013b70  mov     r8d, edi
0x140013b73  mov     qword ptr [rsp+80h+var_60], rax; int
0x140013b78  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140013b7d  mov     edx, 41Fh; void *
0x140013b82  mov     rcx, [rbp+18h]; this
0x140013b86  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140013b8d  mov     r9d, ebx; char *
0x140013b90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013b95  jmp     loc_140013D0A
0x140013b9a  mov     rax, [rdi+8]
0x140013b9e  test    rax, rax
0x140013ba1  jz      short loc_140013BBD
0x140013ba3  mov     r8, [rbp+hFile]
0x140013ba7  mov     rdx, [rbp+var_48]
0x140013bab  mov     rcx, [rdi]
0x140013bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013bb3  mov     ebx, eax
0x140013bb5  test    eax, eax
0x140013bb7  js      loc_140013D0A
0x140013bbd  mov     rdx, [rbp+hFile]; void *
0x140013bc1  mov     rcx, rdi; this
0x140013bc4  call    ?UnlinkOrDelete@CRecursiveRemoveDirectory@@AEAAJPEAX@Z; CRecursiveRemoveDirectory::UnlinkOrDelete(void *)
0x140013bc9  mov     ebx, eax
0x140013bcb  cmp     eax, 80070005h
0x140013bd0  jnz     loc_140013D0A
0x140013bd6  mov     rcx, [rbp+hFile]; hFile
0x140013bda  lea     r8, [rbp+FileInformation]; lpFileInformation
0x140013bde  mov     r9d, 28h ; '('; dwBufferSize
0x140013be4  xor     edx, edx; FileInformationClass
0x140013be6  call    cs:__imp_GetFileInformationByHandleEx
0x140013bec  test    eax, eax
0x140013bee  jz      loc_140013D05
0x140013bf4  mov     esi, dword ptr [rbp+var_10]
0x140013bf7  test    sil, 1
0x140013bfb  jz      loc_140013D05
0x140013c01  mov     rcx, [rbp+hFile]; hFile
0x140013c05  lea     r8, [rbp+FileInformation]; lpFileInformation
0x140013c09  mov     r9d, 28h ; '('; dwBufferSize
0x140013c0f  mov     dword ptr [rbp+var_10], 80h
0x140013c16  xor     edx, edx; FileInformationClass
0x140013c18  call    cs:__imp_SetFileInformationByHandle
0x140013c1e  test    eax, eax
0x140013c20  jnz     short loc_140013C9A
0x140013c22  call    cs:__imp_GetLastError
0x140013c28  mov     ebx, eax
0x140013c2a  test    eax, eax
0x140013c2c  jle     short loc_140013C37
0x140013c2e  movzx   ebx, ax
0x140013c31  or      ebx, 80070000h
0x140013c37  test    ebx, ebx
0x140013c39  jns     short loc_140013C9A
0x140013c3b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013c42  mov     [rbp+var_40], ebx
0x140013c45  test    rcx, rcx
0x140013c48  jz      short loc_140013C90
0x140013c4a  lea     rax, [rbp+var_48]
0x140013c4e  mov     edi, 3
0x140013c53  mov     r8d, edi
0x140013c56  mov     qword ptr [rsp+80h+var_60], rax
0x140013c5b  lea     r9, aFailedClearing; "Failed clearing read-only attribute on:"...
0x140013c62  xor     edx, edx
0x140013c64  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140013c69  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013c70  lea     rax, [rbp+var_40]
0x140013c74  mov     qword ptr [rbp+var_50], rax
0x140013c78  lea     r9, asc_140030534; ": {}"
0x140013c7f  lea     rax, [rbp+var_50]
0x140013c83  mov     r8d, edi
0x140013c86  mov     qword ptr [rsp+80h+var_60], rax
0x140013c8b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140013c90  mov     edx, 44Dh
0x140013c95  jmp     loc_140013B82
0x140013c9a  mov     rdx, [rbp+hFile]; void *
0x140013c9e  mov     rcx, rdi; this
0x140013ca1  call    ?UnlinkOrDelete@CRecursiveRemoveDirectory@@AEAAJPEAX@Z; CRecursiveRemoveDirectory::UnlinkOrDelete(void *)
0x140013ca6  mov     ebx, eax
0x140013ca8  test    eax, eax
0x140013caa  jns     short loc_140013CBE
0x140013cac  lea     r9, [rbp+var_48]
0x140013cb0  mov     edx, eax
0x140013cb2  lea     r8, aUnableToMarkAs; "Unable to mark: {} as delete on close"
0x140013cb9  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x140013cbe  mov     rcx, [rbp+hFile]; hFile
0x140013cc2  lea     r8, [rbp+FileInformation]; lpFileInformation
0x140013cc6  mov     r9d, 28h ; '('; dwBufferSize
0x140013ccc  mov     dword ptr [rbp+var_10], esi
0x140013ccf  xor     edx, edx; FileInformationClass
0x140013cd1  call    cs:__imp_SetFileInformationByHandle
0x140013cd7  test    eax, eax
0x140013cd9  jnz     short loc_140013D0A
0x140013cdb  call    cs:__imp_GetLastError
0x140013ce1  test    eax, eax
0x140013ce3  jle     short loc_140013CEF
0x140013ce5  movzx   eax, ax
0x140013ce8  or      eax, 80070000h
0x140013ced  test    eax, eax
0x140013cef  jns     short loc_140013D0A
0x140013cf1  lea     r9, [rbp+var_48]
0x140013cf5  mov     edx, eax
0x140013cf7  lea     r8, aUnableToRestor; "Unable to restore read-only attribute o"...
0x140013cfe  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x140013d03  jmp     short loc_140013D0A
0x140013d05  mov     ebx, 80070005h
0x140013d0a  lea     rcx, [rbp+hFile]
0x140013d0e  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x140013d13  mov     eax, ebx
0x140013d15  jmp     short loc_140013D22
0x140013d17  lea     rcx, [rbp+hFile]
0x140013d1b  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x140013d20  xor     eax, eax
0x140013d22  mov     rcx, [rbp+var_8]
0x140013d26  xor     rcx, rsp; StackCookie
0x140013d29  call    __security_check_cookie
0x140013d2e  mov     rbx, [rsp+80h+arg_18]
0x140013d36  add     rsp, 80h
0x140013d3d  pop     rdi
0x140013d3e  pop     rsi
0x140013d3f  pop     rbp
0x140013d40  retn
```
