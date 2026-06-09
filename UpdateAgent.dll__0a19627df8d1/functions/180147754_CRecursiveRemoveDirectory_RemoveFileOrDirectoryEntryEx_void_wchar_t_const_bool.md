# CRecursiveRemoveDirectory::RemoveFileOrDirectoryEntryEx(void *,wchar_t const *,bool)

- ea: `0x180147754`
- end: `0x180147c4d`
- name: `?RemoveFileOrDirectoryEntryEx@CRecursiveRemoveDirectory@@AEAAJPEAXPEB_W_N@Z`
- size: `1273`
- prototype: `__int64 __fastcall(CRecursiveRemoveDirectory *this, void *, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x1801462a8`

## callees

- `0x1800059d0`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x18008b38c`
- `0x1800bdd54`
- `0x180145ff4`
- `0x180147754`
- `0x180148104`
- `0x1802b1010`

## import_xrefs

- `ntdll!NtClose` at `0x180147824`
- `ntdll!NtClose` at `0x180147935`
- `ntdll!NtClose` at `0x180147989`
- `ntdll!NtClose` at `0x1801479d3`
- `ntdll!NtClose` at `0x180147af4`
- `ntdll!NtClose` at `0x180147ba6`
- `ntdll!NtClose` at `0x180147bd8`
- `ntdll!NtClose` at `0x180147c0c`
- `ntdll!NtClose` at `0x180147824`
- `ntdll!NtClose` at `0x180147935`
- `ntdll!NtClose` at `0x180147989`
- `ntdll!NtClose` at `0x1801479d3`
- `ntdll!NtClose` at `0x180147af4`
- `ntdll!NtClose` at `0x180147ba6`
- `ntdll!NtClose` at `0x180147bd8`
- `ntdll!NtClose` at `0x180147c0c`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180147a3f`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180147b54`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180147a3f`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180147b54`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180147a07`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180147a07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147b64`

## string_xrefs

- `0x1801477bf`: `No path specified`
- `0x180147a8e`: `Failed clearing read-only attribute on: {}`
- `0x180147b2e`: `Unable to mark: {} as delete on close`
- `0x1801478cf`: `Failed to open {} for deletion`
- `0x180147b84`: `Unable to restore read-only attribute on: {} after setting delete on close`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecursiveRemoveDirectory::RemoveFileOrDirectoryEntryEx(
        CRecursiveRemoveDirectory *this,
        void *a2,
        const wchar_t *a3,
        int a4)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v8; // eax
  __int64 v9; // rdx
  __int64 (__fastcall *v10)(_QWORD, const wchar_t *, HANDLE); // rax
  int v11; // esi
  signed int LastError; // eax
  __int64 v13; // rdx
  int v14; // eax
  signed int v15; // eax
  bool v16; // sf
  int *v17; // [rsp+28h] [rbp-29h]
  int *v18; // [rsp+28h] [rbp-29h]
  int v19[2]; // [rsp+38h] [rbp-19h] BYREF
  __int64 v20; // [rsp+40h] [rbp-11h]
  const wchar_t *v21; // [rsp+48h] [rbp-9h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-1h] BYREF
  int v23; // [rsp+58h] [rbp+7h] BYREF
  _OWORD FileInformation[2]; // [rsp+60h] [rbp+Fh] BYREF
  __int64 v25; // [rsp+80h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]

  v20 = -2;
  v21 = a3;
  Handle = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v25 = 0;
  if ( !a3 )
  {
    v5 = -2147024809;
    v23 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No path specified");
      *(_QWORD *)v19 = &v23;
      v17 = v19;
      LOBYTE(v6) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v6,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40A,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80070057LL,
      (int)v17);
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(Handle) < 0 )
        __fastfail(7u);
      Handle = 0;
    }
    return v5;
  }
  v8 = OpenFileRelativeToParent((_DWORD)a2, (_DWORD)a3, (_DWORD)a3, a4, 0, (__int64)&Handle);
  v5 = v8;
  if ( (unsigned int)(v8 + 2147024894) <= 1
    || v8 == -2147024773
    || v8 == -2147022975
    || (unsigned int)(v8 + 805306317) <= 1
    || v8 == -805306310
    || v8 == -805305728 )
  {
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(Handle) < 0 )
        __fastfail(7u);
      Handle = 0;
    }
    return 0;
  }
  else
  {
    if ( v8 < 0 )
    {
      v23 = v8;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to open {} for deletion",
          &v21);
        *(_QWORD *)v19 = &v23;
        v18 = v19;
        LOBYTE(v9) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v9,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41F,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
        (const char *)v5,
        (int)v18);
      if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        if ( NtClose(Handle) < 0 )
          __fastfail(7u);
        Handle = 0;
      }
      return v5;
    }
    v10 = (__int64 (__fastcall *)(_QWORD, const wchar_t *, HANDLE))*((_QWORD *)this + 1);
    if ( v10 )
    {
      v5 = v10(*(_QWORD *)this, v21, Handle);
      if ( (v5 & 0x80000000) != 0 )
      {
        if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          if ( NtClose(Handle) < 0 )
            __fastfail(7u);
          Handle = 0;
        }
        return v5;
      }
    }
    v5 = CRecursiveRemoveDirectory::UnlinkOrDelete(this, Handle);
    if ( v5 != -2147024891 )
    {
      if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        if ( NtClose(Handle) < 0 )
          __fastfail(7u);
        Handle = 0;
      }
      return v5;
    }
    if ( GetFileInformationByHandleEx(Handle, FileBasicInfo, FileInformation, 0x28u) )
    {
      v11 = v25;
      if ( (v25 & 1) != 0 )
      {
        LODWORD(v25) = 128;
        if ( SetFileInformationByHandle(Handle, FileBasicInfo, FileInformation, 0x28u) )
          goto LABEL_49;
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( (v5 & 0x80000000) == 0 )
        {
LABEL_49:
          v14 = CRecursiveRemoveDirectory::UnlinkOrDelete(this, Handle);
          v5 = v14;
          if ( v14 < 0 )
            LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
              1,
              (unsigned int)v14,
              "Unable to mark: {} as delete on close",
              &v21);
          LODWORD(v25) = v11;
          if ( !SetFileInformationByHandle(Handle, FileBasicInfo, FileInformation, 0x28u) )
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
                &v21);
          }
          if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            if ( NtClose(Handle) < 0 )
              __fastfail(7u);
            Handle = 0;
          }
        }
        else
        {
          v23 = v5;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed clearing read-only attribute on: {}",
              &v21);
            *(_QWORD *)v19 = &v23;
            v18 = v19;
            LOBYTE(v13) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v13,
              3,
              ": {}");
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x44D,
            (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
            (const char *)v5,
            (int)v18);
          if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            if ( NtClose(Handle) < 0 )
              __fastfail(7u);
            Handle = 0;
          }
        }
        return v5;
      }
    }
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(Handle) < 0 )
        __fastfail(7u);
      Handle = 0;
    }
    return 2147942405LL;
  }
}

```

## disassembly

```asm
0x180147754  mov     rax, rsp
0x180147757  push    rbp
0x180147758  push    rsi
0x180147759  push    rdi
0x18014775a  lea     rbp, [rax-5Fh]
0x18014775e  sub     rsp, 90h
0x180147765  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x18014776d  mov     [rax+20h], rbx
0x180147771  mov     rax, cs:__security_cookie
0x180147778  xor     rax, rsp
0x18014777b  mov     [rbp+57h+var_20], rax
0x18014777f  mov     rax, rdx
0x180147782  mov     rdi, rcx
0x180147785  mov     [rbp+57h+var_60], r8
0x180147789  mov     [rbp+57h+Handle], 0
0x180147791  xorps   xmm0, xmm0
0x180147794  xor     ecx, ecx
0x180147796  movups  [rbp+57h+FileInformation], xmm0
0x18014779a  movups  [rbp+57h+var_38], xmm0
0x18014779e  mov     [rbp+57h+var_28], rcx
0x1801477a2  test    r8, r8
0x1801477a5  jnz     loc_18014784A
0x1801477ab  mov     ebx, 80070057h
0x1801477b0  mov     [rbp+57h+var_50], ebx
0x1801477b3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801477ba  test    rcx, rcx
0x1801477bd  jz      short loc_1801477FD
0x1801477bf  lea     r9, aNoPathSpecifie; "No path specified"
0x1801477c6  lea     edi, [r8+3]
0x1801477ca  mov     r8d, edi
0x1801477cd  xor     edx, edx
0x1801477cf  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801477d4  lea     rax, [rbp+57h+var_50]
0x1801477d8  mov     qword ptr [rbp+57h+var_70], rax
0x1801477dc  lea     rax, [rbp+57h+var_70]
0x1801477e0  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x1801477e5  lea     r9, asc_1802C6678; ": {}"
0x1801477ec  mov     r8d, edi
0x1801477ef  mov     dl, 1
0x1801477f1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801477f8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801477fd  mov     rcx, [rbp+5Fh]; this
0x180147801  mov     r9d, ebx; char *
0x180147804  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18014780b  mov     edx, 40Ah; void *
0x180147810  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180147815  nop
0x180147816  mov     rcx, [rbp+57h+Handle]; Handle
0x18014781a  lea     rax, [rcx-1]
0x18014781e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180147822  ja      short loc_180147843
0x180147824  call    cs:__imp_NtClose
0x18014782b  nop     dword ptr [rax+rax+00h]
0x180147830  test    eax, eax
0x180147832  jns     short loc_18014783B
0x180147834  mov     ecx, 7
0x180147839  int     29h; Win8: RtlFailFast(ecx)
0x18014783b  mov     [rbp+57h+Handle], 0
0x180147843  mov     eax, ebx
0x180147845  jmp     loc_180147C2D
0x18014784a  lea     rcx, [rbp+57h+Handle]
0x18014784e  mov     [rsp+28h], rcx
0x180147853  mov     byte ptr [rsp+0A0h+var_80], 0
0x180147858  mov     rdx, r8
0x18014785b  mov     rcx, rax
0x18014785e  call    OpenFileRelativeToParent
0x180147863  mov     ebx, eax
0x180147865  lea     ecx, [rax+7FF8FFFEh]
0x18014786b  cmp     ecx, 1
0x18014786e  jbe     loc_180147BFE
0x180147874  cmp     eax, 8007007Bh
0x180147879  jz      loc_180147BFE
0x18014787f  cmp     eax, 80070781h
0x180147884  jz      loc_180147BFE
0x18014788a  lea     ecx, [rax+2FFFFFCDh]
0x180147890  cmp     ecx, 1
0x180147893  jbe     loc_180147BFE
0x180147899  cmp     eax, 0D000003Ah
0x18014789e  jz      loc_180147BFE
0x1801478a4  cmp     eax, 0D0000280h
0x1801478a9  jz      loc_180147BFE
0x1801478af  test    eax, eax
0x1801478b1  jns     loc_180147959
0x1801478b7  mov     [rbp+57h+var_50], eax
0x1801478ba  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801478c1  test    rcx, rcx
0x1801478c4  jz      short loc_18014790E
0x1801478c6  lea     rax, [rbp+57h+var_60]
0x1801478ca  mov     qword ptr [rsp+0A0h+var_80], rax
0x1801478cf  lea     r9, aFailedToOpenFo; "Failed to open {} for deletion"
0x1801478d6  mov     edi, 3
0x1801478db  mov     r8d, edi
0x1801478de  xor     edx, edx
0x1801478e0  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x1801478e5  lea     rax, [rbp+57h+var_50]
0x1801478e9  mov     qword ptr [rbp+57h+var_70], rax
0x1801478ed  lea     rax, [rbp+57h+var_70]
0x1801478f1  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x1801478f6  lea     r9, asc_1802C6678; ": {}"
0x1801478fd  mov     r8d, edi
0x180147900  mov     dl, 1
0x180147902  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180147909  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18014790e  mov     rcx, [rbp+5Fh]; this
0x180147912  mov     r9d, ebx; char *
0x180147915  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18014791c  mov     edx, 41Fh; void *
0x180147921  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180147926  nop
0x180147927  mov     rcx, [rbp+57h+Handle]; Handle
0x18014792b  lea     rax, [rcx-1]
0x18014792f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180147933  ja      short loc_180147954
0x180147935  call    cs:__imp_NtClose
0x18014793c  nop     dword ptr [rax+rax+00h]
0x180147941  test    eax, eax
0x180147943  jns     short loc_18014794C
0x180147945  mov     ecx, 7
0x18014794a  int     29h; Win8: RtlFailFast(ecx)
0x18014794c  mov     [rbp+57h+Handle], 0
0x180147954  jmp     loc_180147843
0x180147959  mov     rax, [rdi+8]
0x18014795d  test    rax, rax
0x180147960  jz      short loc_1801479AD
0x180147962  mov     r8, [rbp+57h+Handle]
0x180147966  mov     rdx, [rbp+57h+var_60]
0x18014796a  mov     rcx, [rdi]
0x18014796d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180147972  mov     ebx, eax
0x180147974  test    eax, eax
0x180147976  jns     short loc_1801479AD
0x180147978  mov     rdx, [rbp+57h+Handle]
0x18014797c  lea     rcx, [rdx-1]
0x180147980  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180147984  ja      short loc_1801479A8
0x180147986  mov     rcx, rdx; Handle
0x180147989  call    cs:__imp_NtClose
0x180147990  nop     dword ptr [rax+rax+00h]
0x180147995  test    eax, eax
0x180147997  jns     short loc_1801479A0
0x180147999  mov     ecx, 7
0x18014799e  int     29h; Win8: RtlFailFast(ecx)
0x1801479a0  mov     [rbp+57h+Handle], 0
0x1801479a8  jmp     loc_180147843
0x1801479ad  mov     rdx, [rbp+57h+Handle]; void *
0x1801479b1  mov     rcx, rdi; this
0x1801479b4  call    ?UnlinkOrDelete@CRecursiveRemoveDirectory@@AEAAJPEAX@Z; CRecursiveRemoveDirectory::UnlinkOrDelete(void *)
0x1801479b9  mov     ebx, eax
0x1801479bb  cmp     eax, 80070005h
0x1801479c0  jz      short loc_1801479F7
0x1801479c2  mov     rdx, [rbp+57h+Handle]
0x1801479c6  lea     rcx, [rdx-1]
0x1801479ca  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801479ce  ja      short loc_1801479F2
0x1801479d0  mov     rcx, rdx; Handle
0x1801479d3  call    cs:__imp_NtClose
0x1801479da  nop     dword ptr [rax+rax+00h]
0x1801479df  test    eax, eax
0x1801479e1  jns     short loc_1801479EA
0x1801479e3  mov     ecx, 7
0x1801479e8  int     29h; Win8: RtlFailFast(ecx)
0x1801479ea  mov     [rbp+57h+Handle], 0
0x1801479f2  jmp     loc_180147843
0x1801479f7  mov     r9d, 28h ; '('; dwBufferSize
0x1801479fd  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180147a01  xor     edx, edx; FileInformationClass
0x180147a03  mov     rcx, [rbp+57h+Handle]; hFile
0x180147a07  call    cs:__imp_GetFileInformationByHandleEx
0x180147a0e  nop     dword ptr [rax+rax+00h]
0x180147a13  test    eax, eax
0x180147a15  jz      loc_180147BCA
0x180147a1b  mov     esi, dword ptr [rbp+57h+var_28]
0x180147a1e  test    sil, 1
0x180147a22  jz      loc_180147BCA
0x180147a28  mov     dword ptr [rbp+57h+var_28], 80h
0x180147a2f  mov     r9d, 28h ; '('; dwBufferSize
0x180147a35  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180147a39  xor     edx, edx; FileInformationClass
0x180147a3b  mov     rcx, [rbp+57h+Handle]; hFile
0x180147a3f  call    cs:__imp_SetFileInformationByHandle
0x180147a46  nop     dword ptr [rax+rax+00h]
0x180147a4b  test    eax, eax
0x180147a4d  jnz     loc_180147B18
0x180147a53  call    cs:__imp_GetLastError
0x180147a5a  nop     dword ptr [rax+rax+00h]
0x180147a5f  mov     ebx, eax
0x180147a61  test    eax, eax
0x180147a63  jle     short loc_180147A6E
0x180147a65  movzx   ebx, ax
0x180147a68  or      ebx, 80070000h
0x180147a6e  test    ebx, ebx
0x180147a70  jns     loc_180147B18
0x180147a76  mov     [rbp+57h+var_50], ebx
0x180147a79  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180147a80  test    rcx, rcx
0x180147a83  jz      short loc_180147ACD
0x180147a85  lea     rax, [rbp+57h+var_60]
0x180147a89  mov     qword ptr [rsp+0A0h+var_80], rax
0x180147a8e  lea     r9, aFailedClearing; "Failed clearing read-only attribute on:"...
0x180147a95  mov     edi, 3
0x180147a9a  mov     r8d, edi
0x180147a9d  xor     edx, edx
0x180147a9f  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x180147aa4  lea     rax, [rbp+57h+var_50]
0x180147aa8  mov     qword ptr [rbp+57h+var_70], rax
0x180147aac  lea     rax, [rbp+57h+var_70]
0x180147ab0  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x180147ab5  lea     r9, asc_1802C6678; ": {}"
0x180147abc  mov     r8d, edi
0x180147abf  mov     dl, 1
0x180147ac1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180147ac8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180147acd  mov     rcx, [rbp+5Fh]; this
0x180147ad1  mov     r9d, ebx; char *
0x180147ad4  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180147adb  mov     edx, 44Dh; void *
0x180147ae0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180147ae5  nop
0x180147ae6  mov     rcx, [rbp+57h+Handle]; Handle
0x180147aea  lea     rax, [rcx-1]
0x180147aee  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180147af2  ja      short loc_180147B13
0x180147af4  call    cs:__imp_NtClose
0x180147afb  nop     dword ptr [rax+rax+00h]
0x180147b00  test    eax, eax
0x180147b02  jns     short loc_180147B0B
0x180147b04  mov     ecx, 7
0x180147b09  int     29h; Win8: RtlFailFast(ecx)
0x180147b0b  mov     [rbp+57h+Handle], 0
0x180147b13  jmp     loc_180147843
0x180147b18  mov     rdx, [rbp+57h+Handle]; void *
0x180147b1c  mov     rcx, rdi; this
0x180147b1f  call    ?UnlinkOrDelete@CRecursiveRemoveDirectory@@AEAAJPEAX@Z; CRecursiveRemoveDirectory::UnlinkOrDelete(void *)
0x180147b24  mov     ebx, eax
0x180147b26  test    eax, eax
0x180147b28  jns     short loc_180147B41
0x180147b2a  lea     r9, [rbp+57h+var_60]
0x180147b2e  lea     r8, aUnableToMarkAs; "Unable to mark: {} as delete on close"
0x180147b35  mov     edx, eax
0x180147b37  mov     ecx, 1
0x180147b3c  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x180147b41  mov     dword ptr [rbp+57h+var_28], esi
0x180147b44  mov     r9d, 28h ; '('; dwBufferSize
0x180147b4a  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180147b4e  xor     edx, edx; FileInformationClass
0x180147b50  mov     rcx, [rbp+57h+Handle]; hFile
0x180147b54  call    cs:__imp_SetFileInformationByHandle
0x180147b5b  nop     dword ptr [rax+rax+00h]
0x180147b60  test    eax, eax
0x180147b62  jnz     short loc_180147B98
0x180147b64  call    cs:__imp_GetLastError
0x180147b6b  nop     dword ptr [rax+rax+00h]
0x180147b70  test    eax, eax
0x180147b72  jle     short loc_180147B7E
0x180147b74  movzx   eax, ax
0x180147b77  or      eax, 80070000h
0x180147b7c  test    eax, eax
0x180147b7e  jns     short loc_180147B98
0x180147b80  lea     r9, [rbp+57h+var_60]
0x180147b84  lea     r8, aUnableToRestor; "Unable to restore read-only attribute o"...
0x180147b8b  mov     edx, eax
0x180147b8d  mov     ecx, 1
0x180147b92  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x180147b97  nop
0x180147b98  mov     rcx, [rbp+57h+Handle]; Handle
0x180147b9c  lea     rax, [rcx-1]
0x180147ba0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180147ba4  ja      short loc_180147BC5
0x180147ba6  call    cs:__imp_NtClose
0x180147bad  nop     dword ptr [rax+rax+00h]
0x180147bb2  test    eax, eax
0x180147bb4  jns     short loc_180147BBD
0x180147bb6  mov     ecx, 7
0x180147bbb  int     29h; Win8: RtlFailFast(ecx)
0x180147bbd  mov     [rbp+57h+Handle], 0
0x180147bc5  jmp     loc_180147843
0x180147bca  mov     rcx, [rbp+57h+Handle]; Handle
0x180147bce  lea     rax, [rcx-1]
0x180147bd2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180147bd6  ja      short loc_180147BF7
0x180147bd8  call    cs:__imp_NtClose
0x180147bdf  nop     dword ptr [rax+rax+00h]
0x180147be4  test    eax, eax
0x180147be6  jns     short loc_180147BEF
0x180147be8  mov     ecx, 7
0x180147bed  int     29h; Win8: RtlFailFast(ecx)
0x180147bef  mov     [rbp+57h+Handle], 0
0x180147bf7  mov     eax, 80070005h
0x180147bfc  jmp     short loc_180147C2D
0x180147bfe  mov     rcx, [rbp+57h+Handle]; Handle
0x180147c02  lea     rax, [rcx-1]
0x180147c06  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180147c0a  ja      short loc_180147C2B
0x180147c0c  call    cs:__imp_NtClose
0x180147c13  nop     dword ptr [rax+rax+00h]
0x180147c18  test    eax, eax
0x180147c1a  jns     short loc_180147C23
0x180147c1c  mov     ecx, 7
0x180147c21  int     29h; Win8: RtlFailFast(ecx)
0x180147c23  mov     [rbp+57h+Handle], 0
  ... truncated ...
```
