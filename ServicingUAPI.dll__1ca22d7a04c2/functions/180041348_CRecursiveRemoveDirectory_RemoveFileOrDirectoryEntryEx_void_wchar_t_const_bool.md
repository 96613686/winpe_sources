# CRecursiveRemoveDirectory::RemoveFileOrDirectoryEntryEx(void *,wchar_t const *,bool)

- ea: `0x180041348`
- end: `0x180041841`
- name: `?RemoveFileOrDirectoryEntryEx@CRecursiveRemoveDirectory@@AEAAJPEAXPEB_W_N@Z`
- size: `1273`
- prototype: `__int64 __fastcall(CRecursiveRemoveDirectory *__hidden this, void *, const wchar_t *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x18003fec8`

## callees

- `0x1800031d0`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001a810`
- `0x18001b964`
- `0x18003fc14`
- `0x180041348`
- `0x180041cb4`
- `0x1801bd010`

## import_xrefs

- `ntdll!NtClose` at `0x180041418`
- `ntdll!NtClose` at `0x180041529`
- `ntdll!NtClose` at `0x18004157d`
- `ntdll!NtClose` at `0x1800415c7`
- `ntdll!NtClose` at `0x1800416e8`
- `ntdll!NtClose` at `0x18004179a`
- `ntdll!NtClose` at `0x1800417cc`
- `ntdll!NtClose` at `0x180041800`
- `ntdll!NtClose` at `0x180041418`
- `ntdll!NtClose` at `0x180041529`
- `ntdll!NtClose` at `0x18004157d`
- `ntdll!NtClose` at `0x1800415c7`
- `ntdll!NtClose` at `0x1800416e8`
- `ntdll!NtClose` at `0x18004179a`
- `ntdll!NtClose` at `0x1800417cc`
- `ntdll!NtClose` at `0x180041800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041758`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800415fb`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800415fb`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180041633`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180041748`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180041633`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180041748`

## string_xrefs

- `0x1800413b3`: `No path specified`
- `0x180041682`: `Failed clearing read-only attribute on: {}`
- `0x180041722`: `Unable to mark: {} as delete on close`
- `0x1800414c3`: `Failed to open {} for deletion`
- `0x180041778`: `Unable to restore read-only attribute on: {} after setting delete on close`

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
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
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
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
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
0x180041348  mov     rax, rsp
0x18004134b  push    rbp
0x18004134c  push    rsi
0x18004134d  push    rdi
0x18004134e  lea     rbp, [rax-5Fh]
0x180041352  sub     rsp, 90h
0x180041359  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x180041361  mov     [rax+20h], rbx
0x180041365  mov     rax, cs:__security_cookie
0x18004136c  xor     rax, rsp
0x18004136f  mov     [rbp+57h+var_20], rax
0x180041373  mov     rax, rdx
0x180041376  mov     rdi, rcx
0x180041379  mov     [rbp+57h+var_60], r8
0x18004137d  mov     [rbp+57h+Handle], 0
0x180041385  xorps   xmm0, xmm0
0x180041388  xor     ecx, ecx
0x18004138a  movups  [rbp+57h+FileInformation], xmm0
0x18004138e  movups  [rbp+57h+var_38], xmm0
0x180041392  mov     [rbp+57h+var_28], rcx
0x180041396  test    r8, r8
0x180041399  jnz     loc_18004143E
0x18004139f  mov     ebx, 80070057h
0x1800413a4  mov     [rbp+57h+var_50], ebx
0x1800413a7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800413ae  test    rcx, rcx
0x1800413b1  jz      short loc_1800413F1
0x1800413b3  lea     r9, aNoPathSpecifie; "No path specified"
0x1800413ba  lea     edi, [r8+3]
0x1800413be  mov     r8d, edi
0x1800413c1  xor     edx, edx
0x1800413c3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800413c8  lea     rax, [rbp+57h+var_50]
0x1800413cc  mov     qword ptr [rbp+57h+var_70], rax
0x1800413d0  lea     rax, [rbp+57h+var_70]
0x1800413d4  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x1800413d9  lea     r9, asc_1801CAFB4; ": {}"
0x1800413e0  mov     r8d, edi
0x1800413e3  mov     dl, 1
0x1800413e5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800413ec  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800413f1  mov     rcx, [rbp+5Fh]; this
0x1800413f5  mov     r9d, ebx; char *
0x1800413f8  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1800413ff  mov     edx, 40Ah; void *
0x180041404  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041409  nop
0x18004140a  mov     rcx, [rbp+57h+Handle]; Handle
0x18004140e  lea     rax, [rcx-1]
0x180041412  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180041416  ja      short loc_180041437
0x180041418  call    cs:__imp_NtClose
0x18004141f  nop     dword ptr [rax+rax+00h]
0x180041424  test    eax, eax
0x180041426  jns     short loc_18004142F
0x180041428  mov     ecx, 7
0x18004142d  int     29h; Win8: RtlFailFast(ecx)
0x18004142f  mov     [rbp+57h+Handle], 0
0x180041437  mov     eax, ebx
0x180041439  jmp     loc_180041821
0x18004143e  lea     rcx, [rbp+57h+Handle]
0x180041442  mov     [rsp+28h], rcx
0x180041447  mov     byte ptr [rsp+0A0h+var_80], 0
0x18004144c  mov     rdx, r8
0x18004144f  mov     rcx, rax
0x180041452  call    OpenFileRelativeToParent
0x180041457  mov     ebx, eax
0x180041459  lea     ecx, [rax+7FF8FFFEh]
0x18004145f  cmp     ecx, 1
0x180041462  jbe     loc_1800417F2
0x180041468  cmp     eax, 8007007Bh
0x18004146d  jz      loc_1800417F2
0x180041473  cmp     eax, 80070781h
0x180041478  jz      loc_1800417F2
0x18004147e  lea     ecx, [rax+2FFFFFCDh]
0x180041484  cmp     ecx, 1
0x180041487  jbe     loc_1800417F2
0x18004148d  cmp     eax, 0D000003Ah
0x180041492  jz      loc_1800417F2
0x180041498  cmp     eax, 0D0000280h
0x18004149d  jz      loc_1800417F2
0x1800414a3  test    eax, eax
0x1800414a5  jns     loc_18004154D
0x1800414ab  mov     [rbp+57h+var_50], eax
0x1800414ae  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800414b5  test    rcx, rcx
0x1800414b8  jz      short loc_180041502
0x1800414ba  lea     rax, [rbp+57h+var_60]
0x1800414be  mov     qword ptr [rsp+0A0h+var_80], rax
0x1800414c3  lea     r9, aFailedToOpenFo; "Failed to open {} for deletion"
0x1800414ca  mov     edi, 3
0x1800414cf  mov     r8d, edi
0x1800414d2  xor     edx, edx
0x1800414d4  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800414d9  lea     rax, [rbp+57h+var_50]
0x1800414dd  mov     qword ptr [rbp+57h+var_70], rax
0x1800414e1  lea     rax, [rbp+57h+var_70]
0x1800414e5  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x1800414ea  lea     r9, asc_1801CAFB4; ": {}"
0x1800414f1  mov     r8d, edi
0x1800414f4  mov     dl, 1
0x1800414f6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800414fd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180041502  mov     rcx, [rbp+5Fh]; this
0x180041506  mov     r9d, ebx; char *
0x180041509  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180041510  mov     edx, 41Fh; void *
0x180041515  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004151a  nop
0x18004151b  mov     rcx, [rbp+57h+Handle]; Handle
0x18004151f  lea     rax, [rcx-1]
0x180041523  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180041527  ja      short loc_180041548
0x180041529  call    cs:__imp_NtClose
0x180041530  nop     dword ptr [rax+rax+00h]
0x180041535  test    eax, eax
0x180041537  jns     short loc_180041540
0x180041539  mov     ecx, 7
0x18004153e  int     29h; Win8: RtlFailFast(ecx)
0x180041540  mov     [rbp+57h+Handle], 0
0x180041548  jmp     loc_180041437
0x18004154d  mov     rax, [rdi+8]
0x180041551  test    rax, rax
0x180041554  jz      short loc_1800415A1
0x180041556  mov     r8, [rbp+57h+Handle]
0x18004155a  mov     rdx, [rbp+57h+var_60]
0x18004155e  mov     rcx, [rdi]
0x180041561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041566  mov     ebx, eax
0x180041568  test    eax, eax
0x18004156a  jns     short loc_1800415A1
0x18004156c  mov     rdx, [rbp+57h+Handle]
0x180041570  lea     rcx, [rdx-1]
0x180041574  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180041578  ja      short loc_18004159C
0x18004157a  mov     rcx, rdx; Handle
0x18004157d  call    cs:__imp_NtClose
0x180041584  nop     dword ptr [rax+rax+00h]
0x180041589  test    eax, eax
0x18004158b  jns     short loc_180041594
0x18004158d  mov     ecx, 7
0x180041592  int     29h; Win8: RtlFailFast(ecx)
0x180041594  mov     [rbp+57h+Handle], 0
0x18004159c  jmp     loc_180041437
0x1800415a1  mov     rdx, [rbp+57h+Handle]; void *
0x1800415a5  mov     rcx, rdi; this
0x1800415a8  call    ?UnlinkOrDelete@CRecursiveRemoveDirectory@@AEAAJPEAX@Z; CRecursiveRemoveDirectory::UnlinkOrDelete(void *)
0x1800415ad  mov     ebx, eax
0x1800415af  cmp     eax, 80070005h
0x1800415b4  jz      short loc_1800415EB
0x1800415b6  mov     rdx, [rbp+57h+Handle]
0x1800415ba  lea     rcx, [rdx-1]
0x1800415be  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800415c2  ja      short loc_1800415E6
0x1800415c4  mov     rcx, rdx; Handle
0x1800415c7  call    cs:__imp_NtClose
0x1800415ce  nop     dword ptr [rax+rax+00h]
0x1800415d3  test    eax, eax
0x1800415d5  jns     short loc_1800415DE
0x1800415d7  mov     ecx, 7
0x1800415dc  int     29h; Win8: RtlFailFast(ecx)
0x1800415de  mov     [rbp+57h+Handle], 0
0x1800415e6  jmp     loc_180041437
0x1800415eb  mov     r9d, 28h ; '('; dwBufferSize
0x1800415f1  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x1800415f5  xor     edx, edx; FileInformationClass
0x1800415f7  mov     rcx, [rbp+57h+Handle]; hFile
0x1800415fb  call    cs:__imp_GetFileInformationByHandleEx
0x180041602  nop     dword ptr [rax+rax+00h]
0x180041607  test    eax, eax
0x180041609  jz      loc_1800417BE
0x18004160f  mov     esi, dword ptr [rbp+57h+var_28]
0x180041612  test    sil, 1
0x180041616  jz      loc_1800417BE
0x18004161c  mov     dword ptr [rbp+57h+var_28], 80h
0x180041623  mov     r9d, 28h ; '('; dwBufferSize
0x180041629  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x18004162d  xor     edx, edx; FileInformationClass
0x18004162f  mov     rcx, [rbp+57h+Handle]; hFile
0x180041633  call    cs:__imp_SetFileInformationByHandle
0x18004163a  nop     dword ptr [rax+rax+00h]
0x18004163f  test    eax, eax
0x180041641  jnz     loc_18004170C
0x180041647  call    cs:__imp_GetLastError
0x18004164e  nop     dword ptr [rax+rax+00h]
0x180041653  mov     ebx, eax
0x180041655  test    eax, eax
0x180041657  jle     short loc_180041662
0x180041659  movzx   ebx, ax
0x18004165c  or      ebx, 80070000h
0x180041662  test    ebx, ebx
0x180041664  jns     loc_18004170C
0x18004166a  mov     [rbp+57h+var_50], ebx
0x18004166d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180041674  test    rcx, rcx
0x180041677  jz      short loc_1800416C1
0x180041679  lea     rax, [rbp+57h+var_60]
0x18004167d  mov     qword ptr [rsp+0A0h+var_80], rax
0x180041682  lea     r9, aFailedClearing; "Failed clearing read-only attribute on:"...
0x180041689  mov     edi, 3
0x18004168e  mov     r8d, edi
0x180041691  xor     edx, edx
0x180041693  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180041698  lea     rax, [rbp+57h+var_50]
0x18004169c  mov     qword ptr [rbp+57h+var_70], rax
0x1800416a0  lea     rax, [rbp+57h+var_70]
0x1800416a4  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x1800416a9  lea     r9, asc_1801CAFB4; ": {}"
0x1800416b0  mov     r8d, edi
0x1800416b3  mov     dl, 1
0x1800416b5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800416bc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800416c1  mov     rcx, [rbp+5Fh]; this
0x1800416c5  mov     r9d, ebx; char *
0x1800416c8  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1800416cf  mov     edx, 44Dh; void *
0x1800416d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800416d9  nop
0x1800416da  mov     rcx, [rbp+57h+Handle]; Handle
0x1800416de  lea     rax, [rcx-1]
0x1800416e2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800416e6  ja      short loc_180041707
0x1800416e8  call    cs:__imp_NtClose
0x1800416ef  nop     dword ptr [rax+rax+00h]
0x1800416f4  test    eax, eax
0x1800416f6  jns     short loc_1800416FF
0x1800416f8  mov     ecx, 7
0x1800416fd  int     29h; Win8: RtlFailFast(ecx)
0x1800416ff  mov     [rbp+57h+Handle], 0
0x180041707  jmp     loc_180041437
0x18004170c  mov     rdx, [rbp+57h+Handle]; void *
0x180041710  mov     rcx, rdi; this
0x180041713  call    ?UnlinkOrDelete@CRecursiveRemoveDirectory@@AEAAJPEAX@Z; CRecursiveRemoveDirectory::UnlinkOrDelete(void *)
0x180041718  mov     ebx, eax
0x18004171a  test    eax, eax
0x18004171c  jns     short loc_180041735
0x18004171e  lea     r9, [rbp+57h+var_60]
0x180041722  lea     r8, aUnableToMarkAs; "Unable to mark: {} as delete on close"
0x180041729  mov     edx, eax
0x18004172b  mov     ecx, 1
0x180041730  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x180041735  mov     dword ptr [rbp+57h+var_28], esi
0x180041738  mov     r9d, 28h ; '('; dwBufferSize
0x18004173e  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180041742  xor     edx, edx; FileInformationClass
0x180041744  mov     rcx, [rbp+57h+Handle]; hFile
0x180041748  call    cs:__imp_SetFileInformationByHandle
0x18004174f  nop     dword ptr [rax+rax+00h]
0x180041754  test    eax, eax
0x180041756  jnz     short loc_18004178C
0x180041758  call    cs:__imp_GetLastError
0x18004175f  nop     dword ptr [rax+rax+00h]
0x180041764  test    eax, eax
0x180041766  jle     short loc_180041772
0x180041768  movzx   eax, ax
0x18004176b  or      eax, 80070000h
0x180041770  test    eax, eax
0x180041772  jns     short loc_18004178C
0x180041774  lea     r9, [rbp+57h+var_60]
0x180041778  lea     r8, aUnableToRestor; "Unable to restore read-only attribute o"...
0x18004177f  mov     edx, eax
0x180041781  mov     ecx, 1
0x180041786  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x18004178b  nop
0x18004178c  mov     rcx, [rbp+57h+Handle]; Handle
0x180041790  lea     rax, [rcx-1]
0x180041794  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180041798  ja      short loc_1800417B9
0x18004179a  call    cs:__imp_NtClose
0x1800417a1  nop     dword ptr [rax+rax+00h]
0x1800417a6  test    eax, eax
0x1800417a8  jns     short loc_1800417B1
0x1800417aa  mov     ecx, 7
0x1800417af  int     29h; Win8: RtlFailFast(ecx)
0x1800417b1  mov     [rbp+57h+Handle], 0
0x1800417b9  jmp     loc_180041437
0x1800417be  mov     rcx, [rbp+57h+Handle]; Handle
0x1800417c2  lea     rax, [rcx-1]
0x1800417c6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800417ca  ja      short loc_1800417EB
0x1800417cc  call    cs:__imp_NtClose
0x1800417d3  nop     dword ptr [rax+rax+00h]
0x1800417d8  test    eax, eax
0x1800417da  jns     short loc_1800417E3
0x1800417dc  mov     ecx, 7
0x1800417e1  int     29h; Win8: RtlFailFast(ecx)
0x1800417e3  mov     [rbp+57h+Handle], 0
0x1800417eb  mov     eax, 80070005h
0x1800417f0  jmp     short loc_180041821
0x1800417f2  mov     rcx, [rbp+57h+Handle]; Handle
0x1800417f6  lea     rax, [rcx-1]
0x1800417fa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800417fe  ja      short loc_18004181F
0x180041800  call    cs:__imp_NtClose
0x180041807  nop     dword ptr [rax+rax+00h]
0x18004180c  test    eax, eax
0x18004180e  jns     short loc_180041817
0x180041810  mov     ecx, 7
0x180041815  int     29h; Win8: RtlFailFast(ecx)
0x180041817  mov     [rbp+57h+Handle], 0
  ... truncated ...
```
