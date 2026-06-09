# CRecursiveRemoveDirectory::RemoveFileOrDirectoryEntryEx(void *,wchar_t const *,bool)

- ea: `0x180103c30`
- end: `0x180103f8c`
- name: `?RemoveFileOrDirectoryEntryEx@CRecursiveRemoveDirectory@@AEAAJPEAXPEB_W_N@Z`
- size: `860`
- prototype: `__int64 __fastcall(CRecursiveRemoveDirectory *__hidden this, void *, const wchar_t *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180102dcc`

## callees

- `0x18002e280`
- `0x18002ec34`
- `0x180056c7c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800b980c`
- `0x1800eb920`
- `0x180102b18`
- `0x180103c30`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103e4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103f1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103e4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103f1a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180103e3a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180103f0a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180103e3a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180103f0a`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180103e02`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180103e02`

## string_xrefs

- `0x180103c94`: `No path specified`
- `0x180103d62`: `Failed to open {} for deletion`
- `0x180103e8d`: `Failed clearing read-only attribute on: {}`
- `0x180103ee6`: `Unable to mark: {} as delete on close`
- `0x180103f3c`: `Unable to restore read-only attribute on: {} after setting delete on close`

## pseudocode

```c
__int64 __fastcall CRecursiveRemoveDirectory::RemoveFileOrDirectoryEntryEx(
        CRecursiveRemoveDirectory *this,
        void *a2,
        const wchar_t *a3)
{
  int v3; // ebx
  signed int v5; // ebx
  __int64 v6; // rdx
  __int64 InitPointer; // rax
  int v8; // r8d
  int v9; // r9d
  int v10; // eax
  __int64 (__fastcall *v11)(_QWORD, const wchar_t *, HANDLE); // rax
  int v12; // esi
  signed int LastError; // eax
  int v14; // eax
  signed int v15; // eax
  bool v16; // sf
  int v18; // [rsp+20h] [rbp-60h]
  int v19[2]; // [rsp+30h] [rbp-50h] BYREF
  const wchar_t *v20; // [rsp+38h] [rbp-48h] BYREF
  int v21; // [rsp+40h] [rbp-40h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-38h] BYREF
  _OWORD FileInformation[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v24; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v20 = a3;
  hFile = 0;
  v24 = 0;
  v3 = (int)a2;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( !a3 )
  {
    v5 = -2147024809;
    v21 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path specified");
      *(_QWORD *)v19 = &v21;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v19);
    }
    v6 = 1034;
    goto LABEL_15;
  }
  InitPointer = Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&hFile);
  v10 = OpenFileRelativeToParent(v3, (_DWORD)v20, v8, v9, 0, InitPointer);
  v5 = v10;
  if ( (unsigned int)(v10 + 2147024894) > 1
    && v10 != -2147024773
    && v10 != -2147022975
    && (unsigned int)(v10 + 805306317) > 1
    && v10 != -805306310
    && v10 != -805305728 )
  {
    if ( v10 >= 0 )
    {
      v11 = (__int64 (__fastcall *)(_QWORD, const wchar_t *, HANDLE))*((_QWORD *)this + 1);
      if ( v11 )
      {
        v5 = v11(*(_QWORD *)this, v20, hFile);
        if ( v5 < 0 )
          goto LABEL_36;
      }
      v5 = CRecursiveRemoveDirectory::UnlinkOrDelete(this, hFile);
      if ( v5 != -2147024891 )
        goto LABEL_36;
      if ( !GetFileInformationByHandleEx(hFile, FileBasicInfo, FileInformation, 0x28u) || (v12 = v24, (v24 & 1) == 0) )
      {
        v5 = -2147024891;
        goto LABEL_36;
      }
      LODWORD(v24) = 128;
      if ( SetFileInformationByHandle(hFile, FileBasicInfo, FileInformation, 0x28u) )
        goto LABEL_28;
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
      {
LABEL_28:
        v14 = CRecursiveRemoveDirectory::UnlinkOrDelete(this, hFile);
        v5 = v14;
        if ( v14 < 0 )
          LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
            1,
            (unsigned int)v14,
            "Unable to mark: {} as delete on close",
            &v20);
        LODWORD(v24) = v12;
        if ( !SetFileInformationByHandle(hFile, FileBasicInfo, FileInformation, 0x28u) )
        {
          v15 = GetLastError();
          v16 = v15 < 0;
          if ( v15 > 0 )
          {
            v15 = (unsigned __int16)v15 | 0x80070000;
            v16 = v15 < 0;
          }
          if ( v16 )
            LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
              1,
              (unsigned int)v15,
              "Unable to restore read-only attribute on: {} after setting delete on close",
              &v20);
        }
        goto LABEL_36;
      }
      v21 = v5;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed clearing read-only attribute on: {}",
          (__int64)&v20);
        *(_QWORD *)v19 = &v21;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v19);
      }
      v6 = 1101;
    }
    else
    {
      v21 = v10;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to open {} for deletion",
          (__int64)&v20);
        *(_QWORD *)v19 = &v21;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v19);
      }
      v6 = 1055;
    }
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v5,
      v18);
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
0x180103c30  mov     [rsp-18h+arg_18], rbx
0x180103c35  push    rbp
0x180103c36  push    rsi
0x180103c37  push    rdi
0x180103c38  mov     rbp, rsp
0x180103c3b  sub     rsp, 80h
0x180103c42  mov     rax, cs:__security_cookie
0x180103c49  xor     rax, rsp
0x180103c4c  mov     [rbp+var_8], rax
0x180103c50  xor     eax, eax
0x180103c52  mov     [rbp+var_48], r8
0x180103c56  mov     [rbp+hFile], 0
0x180103c5e  xorps   xmm0, xmm0
0x180103c61  mov     [rbp+var_10], rax
0x180103c65  mov     rbx, rdx
0x180103c68  mov     rdi, rcx
0x180103c6b  movups  [rbp+FileInformation], xmm0
0x180103c6f  movups  [rbp+var_20], xmm0
0x180103c73  test    r8, r8
0x180103c76  jnz     short loc_180103CD3
0x180103c78  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180103c7f  mov     ebx, 80070057h
0x180103c84  mov     [rbp+var_40], ebx
0x180103c87  test    rcx, rcx
0x180103c8a  jz      short loc_180103CC9
0x180103c8c  lea     edi, [rax+3]
0x180103c8f  xor     edx, edx
0x180103c91  mov     r8d, edi
0x180103c94  lea     r9, aNoPathSpecifie; "No path specified"
0x180103c9b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180103ca0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180103ca7  lea     rax, [rbp+var_40]
0x180103cab  mov     qword ptr [rbp+var_50], rax
0x180103caf  lea     r9, asc_1802EE7AC; ": {}"
0x180103cb6  lea     rax, [rbp+var_50]
0x180103cba  mov     r8d, edi
0x180103cbd  mov     dl, 1
0x180103cbf  mov     qword ptr [rsp+80h+var_60], rax
0x180103cc4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180103cc9  mov     edx, 40Ah
0x180103cce  jmp     loc_180103D9E
0x180103cd3  lea     rcx, [rbp+hFile]
0x180103cd7  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x180103cdc  mov     rdx, [rbp+var_48]
0x180103ce0  mov     rcx, rbx
0x180103ce3  mov     [rsp+80h+var_58], rax
0x180103ce8  mov     byte ptr [rsp+80h+var_60], 0
0x180103ced  call    OpenFileRelativeToParent
0x180103cf2  mov     ebx, eax
0x180103cf4  lea     ecx, [rax+7FF8FFFEh]
0x180103cfa  cmp     ecx, 1
0x180103cfd  jbe     loc_180103F61
0x180103d03  cmp     eax, 8007007Bh
0x180103d08  jz      loc_180103F61
0x180103d0e  cmp     eax, 80070781h
0x180103d13  jz      loc_180103F61
0x180103d19  lea     ecx, [rax+2FFFFFCDh]
0x180103d1f  cmp     ecx, 1
0x180103d22  jbe     loc_180103F61
0x180103d28  cmp     eax, 0D000003Ah
0x180103d2d  jz      loc_180103F61
0x180103d33  cmp     eax, 0D0000280h
0x180103d38  jz      loc_180103F61
0x180103d3e  test    eax, eax
0x180103d40  jns     short loc_180103DB6
0x180103d42  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180103d49  mov     [rbp+var_40], eax
0x180103d4c  test    rcx, rcx
0x180103d4f  jz      short loc_180103D99
0x180103d51  lea     rax, [rbp+var_48]
0x180103d55  mov     edi, 3
0x180103d5a  mov     r8d, edi
0x180103d5d  mov     qword ptr [rsp+80h+var_60], rax
0x180103d62  lea     r9, aFailedToOpenFo_0; "Failed to open {} for deletion"
0x180103d69  xor     edx, edx
0x180103d6b  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180103d70  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180103d77  lea     rax, [rbp+var_40]
0x180103d7b  mov     qword ptr [rbp+var_50], rax
0x180103d7f  lea     r9, asc_1802EE7AC; ": {}"
0x180103d86  lea     rax, [rbp+var_50]
0x180103d8a  mov     r8d, edi
0x180103d8d  mov     dl, 1
0x180103d8f  mov     qword ptr [rsp+80h+var_60], rax; int
0x180103d94  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180103d99  mov     edx, 41Fh; void *
0x180103d9e  mov     rcx, [rbp+18h]; this
0x180103da2  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180103da9  mov     r9d, ebx; char *
0x180103dac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180103db1  jmp     loc_180103F54
0x180103db6  mov     rax, [rdi+8]
0x180103dba  test    rax, rax
0x180103dbd  jz      short loc_180103DD9
0x180103dbf  mov     r8, [rbp+hFile]
0x180103dc3  mov     rdx, [rbp+var_48]
0x180103dc7  mov     rcx, [rdi]
0x180103dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103dcf  mov     ebx, eax
0x180103dd1  test    eax, eax
0x180103dd3  js      loc_180103F54
0x180103dd9  mov     rdx, [rbp+hFile]; void *
0x180103ddd  mov     rcx, rdi; this
0x180103de0  call    ?UnlinkOrDelete@CRecursiveRemoveDirectory@@AEAAJPEAX@Z; CRecursiveRemoveDirectory::UnlinkOrDelete(void *)
0x180103de5  mov     ebx, eax
0x180103de7  cmp     eax, 80070005h
0x180103dec  jnz     loc_180103F54
0x180103df2  mov     rcx, [rbp+hFile]; hFile
0x180103df6  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180103dfa  mov     r9d, 28h ; '('; dwBufferSize
0x180103e00  xor     edx, edx; FileInformationClass
0x180103e02  call    cs:__imp_GetFileInformationByHandleEx
0x180103e09  nop     dword ptr [rax+rax+00h]
0x180103e0e  test    eax, eax
0x180103e10  jz      loc_180103F4F
0x180103e16  mov     esi, dword ptr [rbp+var_10]
0x180103e19  test    sil, 1
0x180103e1d  jz      loc_180103F4F
0x180103e23  mov     rcx, [rbp+hFile]; hFile
0x180103e27  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180103e2b  mov     r9d, 28h ; '('; dwBufferSize
0x180103e31  mov     dword ptr [rbp+var_10], 80h
0x180103e38  xor     edx, edx; FileInformationClass
0x180103e3a  call    cs:__imp_SetFileInformationByHandle
0x180103e41  nop     dword ptr [rax+rax+00h]
0x180103e46  test    eax, eax
0x180103e48  jnz     loc_180103ECE
0x180103e4e  call    cs:__imp_GetLastError
0x180103e55  nop     dword ptr [rax+rax+00h]
0x180103e5a  mov     ebx, eax
0x180103e5c  test    eax, eax
0x180103e5e  jle     short loc_180103E69
0x180103e60  movzx   ebx, ax
0x180103e63  or      ebx, 80070000h
0x180103e69  test    ebx, ebx
0x180103e6b  jns     short loc_180103ECE
0x180103e6d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180103e74  mov     [rbp+var_40], ebx
0x180103e77  test    rcx, rcx
0x180103e7a  jz      short loc_180103EC4
0x180103e7c  lea     rax, [rbp+var_48]
0x180103e80  mov     edi, 3
0x180103e85  mov     r8d, edi
0x180103e88  mov     qword ptr [rsp+80h+var_60], rax
0x180103e8d  lea     r9, aFailedClearing_1; "Failed clearing read-only attribute on:"...
0x180103e94  xor     edx, edx
0x180103e96  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180103e9b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180103ea2  lea     rax, [rbp+var_40]
0x180103ea6  mov     qword ptr [rbp+var_50], rax
0x180103eaa  lea     r9, asc_1802EE7AC; ": {}"
0x180103eb1  lea     rax, [rbp+var_50]
0x180103eb5  mov     r8d, edi
0x180103eb8  mov     dl, 1
0x180103eba  mov     qword ptr [rsp+80h+var_60], rax
0x180103ebf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180103ec4  mov     edx, 44Dh
0x180103ec9  jmp     loc_180103D9E
0x180103ece  mov     rdx, [rbp+hFile]; void *
0x180103ed2  mov     rcx, rdi; this
0x180103ed5  call    ?UnlinkOrDelete@CRecursiveRemoveDirectory@@AEAAJPEAX@Z; CRecursiveRemoveDirectory::UnlinkOrDelete(void *)
0x180103eda  mov     ebx, eax
0x180103edc  test    eax, eax
0x180103ede  jns     short loc_180103EF7
0x180103ee0  lea     r9, [rbp+var_48]
0x180103ee4  mov     edx, eax
0x180103ee6  lea     r8, aUnableToMarkAs; "Unable to mark: {} as delete on close"
0x180103eed  mov     ecx, 1
0x180103ef2  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x180103ef7  mov     rcx, [rbp+hFile]; hFile
0x180103efb  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180103eff  mov     r9d, 28h ; '('; dwBufferSize
0x180103f05  mov     dword ptr [rbp+var_10], esi
0x180103f08  xor     edx, edx; FileInformationClass
0x180103f0a  call    cs:__imp_SetFileInformationByHandle
0x180103f11  nop     dword ptr [rax+rax+00h]
0x180103f16  test    eax, eax
0x180103f18  jnz     short loc_180103F54
0x180103f1a  call    cs:__imp_GetLastError
0x180103f21  nop     dword ptr [rax+rax+00h]
0x180103f26  test    eax, eax
0x180103f28  jle     short loc_180103F34
0x180103f2a  movzx   eax, ax
0x180103f2d  or      eax, 80070000h
0x180103f32  test    eax, eax
0x180103f34  jns     short loc_180103F54
0x180103f36  lea     r9, [rbp+var_48]
0x180103f3a  mov     edx, eax
0x180103f3c  lea     r8, aUnableToRestor_0; "Unable to restore read-only attribute o"...
0x180103f43  mov     ecx, 1
0x180103f48  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x180103f4d  jmp     short loc_180103F54
0x180103f4f  mov     ebx, 80070005h
0x180103f54  lea     rcx, [rbp+hFile]
0x180103f58  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180103f5d  mov     eax, ebx
0x180103f5f  jmp     short loc_180103F6C
0x180103f61  lea     rcx, [rbp+hFile]
0x180103f65  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180103f6a  xor     eax, eax
0x180103f6c  mov     rcx, [rbp+var_8]
0x180103f70  xor     rcx, rsp; StackCookie
0x180103f73  call    __security_check_cookie
0x180103f78  mov     rbx, [rsp+80h+arg_18]
0x180103f80  add     rsp, 80h
0x180103f87  pop     rdi
0x180103f88  pop     rsi
0x180103f89  pop     rbp
0x180103f8a  retn
```
