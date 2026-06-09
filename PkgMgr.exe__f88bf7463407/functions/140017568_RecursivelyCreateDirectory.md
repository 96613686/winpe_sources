# RecursivelyCreateDirectory

- ea: `0x140017568`
- end: `0x140017aea`
- name: `RecursivelyCreateDirectory`
- size: `1410`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140013288`
- `0x140017568`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006984`
- `0x140006c50`
- `0x14000726c`
- `0x14000eae0`
- `0x140010164`
- `0x140011884`
- `0x1400165f8`
- `0x140016870`
- `0x140016b44`
- `0x140016b84`
- `0x140017568`
- `0x14002750c`
- `0x140027858`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140017821`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140017821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400177fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017a77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400177fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017a77`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400177ef`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140017a6d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400177ef`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140017a6d`

## string_xrefs

- `0x1400175d0`: `No path specified`
- `0x14001775a`: `Failed calling GetSystemSecurity`
- `0x140017850`: `Cannot find parent for path: {}.`
- `0x140017958`: `Failed to copy parent of path: {}`
- `0x1400179f9`: `Failed to create path: {}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RecursivelyCreateDirectory(__int64 a1, struct _SECURITY_ATTRIBUTES *a2)
{
  unsigned int v3; // edi
  int v4; // edx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  bool *v9; // rdx
  int CanSetSystemOwner; // eax
  struct _SECURITY_DESCRIPTOR **v11; // rdx
  unsigned int v12; // r8d
  unsigned int v13; // edi
  int v14; // edx
  int SystemSecurity; // eax
  unsigned int v16; // r8d
  unsigned int v17; // edi
  int v18; // edx
  const wchar_t *v19; // rbx
  wchar_t *v20; // rax
  int v21; // edx
  unsigned __int64 v22; // rsi
  wchar_t *v23; // rdi
  unsigned __int64 v24; // rax
  int v25; // eax
  unsigned int v26; // esi
  int v27; // edx
  int Directory; // eax
  int v29; // edx
  signed int LastError; // eax
  int v31; // [rsp+28h] [rbp-59h]
  _BYTE v32[8]; // [rsp+38h] [rbp-49h] BYREF
  wchar_t *v33; // [rsp+40h] [rbp-41h] BYREF
  LPCWSTR lpPathName; // [rsp+48h] [rbp-39h] BYREF
  int v35[2]; // [rsp+50h] [rbp-31h] BYREF
  int v36[2]; // [rsp+58h] [rbp-29h] BYREF
  __int128 v37; // [rsp+60h] [rbp-21h]
  __int64 v38; // [rsp+70h] [rbp-11h]
  __int64 v39; // [rsp+78h] [rbp-9h]
  __int64 v40; // [rsp+80h] [rbp-1h] BYREF
  int v41; // [rsp+88h] [rbp+7h] BYREF
  __int128 v42; // [rsp+90h] [rbp+Fh] BYREF
  __int64 v43; // [rsp+A0h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  v39 = -2;
  v40 = a1;
  v42 = 0;
  v43 = 0;
  lpPathName = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    v41 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No path specified");
      v33 = (wchar_t *)&v41;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v4,
        3,
        (unsigned int)": {}",
        (__int64)&v33);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80070057LL,
      v31);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpPathName);
    return v3;
  }
  v6 = SczAllocFromSz(&lpPathName, a1);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x168,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v6,
      v31);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpPathName);
    return v7;
  }
  v8 = PathPrefix(&lpPathName);
  v7 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x169,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v8,
      v31);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpPathName);
    return v7;
  }
  if ( !a2 )
  {
    v32[0] = 0;
    CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
                          (Windows::WCP::Implementation::Rtl *)v32,
                          v9);
    v13 = CanSetSystemOwner;
    if ( CanSetSystemOwner < 0 )
    {
      v41 = CanSetSystemOwner;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed calling CanSetSystemOwner");
        v33 = (wchar_t *)&v41;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v14,
          3,
          (unsigned int)": {}",
          (__int64)&v33);
      }
      v7 = wil::details::in1diag3::Return_NtStatus(retaddr, (void *)0x16F, v12, (const char *)v13, v31);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpPathName);
      return v7;
    }
    if ( v32[0] )
    {
      v33 = 0;
      SystemSecurity = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                         (Windows::WCP::Implementation::Rtl *)&v33,
                         v11);
      v17 = SystemSecurity;
      if ( SystemSecurity < 0 )
      {
        v41 = SystemSecurity;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed calling GetSystemSecurity");
          v33 = (wchar_t *)&v41;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v18,
            3,
            (unsigned int)": {}",
            (__int64)&v33);
        }
        v7 = wil::details::in1diag3::Return_NtStatus(retaddr, (void *)0x175, v16, (const char *)v17, v31);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpPathName);
        return v7;
      }
      *(_QWORD *)&v37 = 24;
      *((_QWORD *)&v37 + 1) = v33;
      v38 = 0;
      v42 = v37;
      v43 = 0;
      a2 = (struct _SECURITY_ATTRIBUTES *)&v42;
    }
  }
  v19 = lpPathName;
  if ( !CreateDirectoryW(lpPathName, a2) && GetLastError() != 183 )
  {
    v20 = wcsrchr(v19, 0x5Cu);
    if ( !v20 )
    {
      v3 = -2147024893;
      v41 = -2147024893;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Cannot find parent for path: {}.",
          (__int64)&v40);
        v33 = (wchar_t *)&v41;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v21,
          3,
          (unsigned int)": {}",
          (__int64)&v33);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x188,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
        (const char *)0x80070003LL,
        v31);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpPathName);
      return v3;
    }
    v22 = v20 - v19;
    v33 = 0;
    Windows::AutoNewArrayPtr<wchar_t>::AllocateArray(&v33, v22 + 1);
    v23 = v33;
    if ( !v33 )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18F,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
        (const char *)0x8007000ELL,
        v31);
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v33);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpPathName);
      return v7;
    }
    v24 = -1;
    do
      ++v24;
    while ( v19[v24] );
    if ( v22 <= v24 )
    {
      v25 = StringCchCopyNW(v33, v22 + 1, v19, v22);
      v26 = v25;
      if ( v25 < 0 )
      {
        v41 = v25;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v35 = v19;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to copy parent of path: {}",
            (__int64)v35);
          *(_QWORD *)v36 = &v41;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v27,
            3,
            (unsigned int)": {}",
            (__int64)v36);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x196,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
          (const char *)v26,
          v31);
        Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v33);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpPathName);
        return v26;
      }
    }
    Directory = RecursivelyCreateDirectory(v23, a2);
    v26 = Directory;
    if ( Directory < 0 )
    {
      v41 = Directory;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v36 = v23;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to create path: {}",
          (__int64)v36);
        *(_QWORD *)v35 = &v41;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v29,
          3,
          (unsigned int)": {}",
          (__int64)v35);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x198,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
        (const char *)v26,
        v31);
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v33);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpPathName);
      return v26;
    }
    if ( !CreateDirectoryW(v19, a2) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError != 183 )
      {
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v33);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpPathName);
        return v7;
      }
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v33);
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpPathName);
  return 0;
}

```

## disassembly

```asm
0x140017568  mov     rax, rsp
0x14001756b  push    rbp
0x14001756c  push    rdi
0x14001756d  push    r12
0x14001756f  push    r14
0x140017571  push    r15
0x140017573  lea     rbp, [rax-5Fh]
0x140017577  sub     rsp, 0B0h
0x14001757e  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x140017586  mov     [rax+18h], rbx
0x14001758a  mov     [rax+20h], rsi
0x14001758e  mov     rax, cs:__security_cookie
0x140017595  xor     rax, rsp
0x140017598  mov     [rbp+57h+var_30], rax
0x14001759c  mov     r14, rdx
0x14001759f  mov     [rbp+57h+var_58], rcx
0x1400175a3  xorps   xmm0, xmm0
0x1400175a6  xor     eax, eax
0x1400175a8  movups  [rbp+57h+var_48], xmm0
0x1400175ac  mov     [rbp+57h+var_38], rax
0x1400175b0  xor     r12d, r12d
0x1400175b3  mov     [rbp+57h+lpPathName], r12
0x1400175b7  test    rcx, rcx
0x1400175ba  jnz     short loc_140017635
0x1400175bc  mov     edi, 80070057h
0x1400175c1  mov     [rbp+57h+var_50], edi
0x1400175c4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400175cb  test    rcx, rcx
0x1400175ce  jz      short loc_14001760B
0x1400175d0  lea     r9, aNoPathSpecifie; "No path specified"
0x1400175d7  lea     ebx, [rax+3]
0x1400175da  mov     r8d, ebx
0x1400175dd  xor     edx, edx
0x1400175df  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400175e4  lea     rax, [rbp+57h+var_50]
0x1400175e8  mov     [rbp+57h+var_98], rax
0x1400175ec  lea     rax, [rbp+57h+var_98]
0x1400175f0  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1400175f5  lea     r9, asc_14002D4FC; ": {}"
0x1400175fc  mov     r8d, ebx
0x1400175ff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017606  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001760b  mov     rcx, [rbp+5Fh]; this
0x14001760f  mov     r9d, edi; char *
0x140017612  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140017619  mov     edx, 163h; void *
0x14001761e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017623  nop
0x140017624  lea     rcx, [rbp+57h+lpPathName]
0x140017628  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14001762d  nop
0x14001762e  mov     eax, edi
0x140017630  jmp     loc_140017AC2
0x140017635  mov     rdx, rcx
0x140017638  lea     rcx, [rbp+57h+lpPathName]
0x14001763c  call    SczAllocFromSz
0x140017641  mov     ebx, eax
0x140017643  test    eax, eax
0x140017645  jns     short loc_140017671
0x140017647  mov     rcx, [rbp+5Fh]; this
0x14001764b  mov     r9d, eax; char *
0x14001764e  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140017655  mov     edx, 168h; void *
0x14001765a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001765f  nop
0x140017660  lea     rcx, [rbp+57h+lpPathName]
0x140017664  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140017669  nop
0x14001766a  mov     eax, ebx
0x14001766c  jmp     loc_140017AC2
0x140017671  lea     rcx, [rbp+57h+lpPathName]
0x140017675  call    PathPrefix
0x14001767a  mov     ebx, eax
0x14001767c  test    eax, eax
0x14001767e  jns     short loc_1400176A5
0x140017680  mov     rcx, [rbp+5Fh]; this
0x140017684  mov     r9d, eax; char *
0x140017687  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001768e  mov     edx, 169h; void *
0x140017693  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017698  nop
0x140017699  lea     rcx, [rbp+57h+lpPathName]
0x14001769d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400176a2  nop
0x1400176a3  jmp     short loc_14001766A
0x1400176a5  test    r14, r14
0x1400176a8  jnz     loc_1400177E5
0x1400176ae  mov     [rbp+57h+var_A0], r12b
0x1400176b2  lea     rcx, [rbp+57h+var_A0]; this
0x1400176b6  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x1400176bb  mov     edi, eax
0x1400176bd  test    eax, eax
0x1400176bf  jns     short loc_14001772E
0x1400176c1  mov     [rbp+57h+var_50], eax
0x1400176c4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400176cb  test    rcx, rcx
0x1400176ce  jz      short loc_14001770C
0x1400176d0  lea     r9, aFailedCallingC; "Failed calling CanSetSystemOwner"
0x1400176d7  lea     ebx, [r14+3]
0x1400176db  mov     r8d, ebx
0x1400176de  xor     edx, edx
0x1400176e0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400176e5  lea     rax, [rbp+57h+var_50]
0x1400176e9  mov     [rbp+57h+var_98], rax
0x1400176ed  lea     rax, [rbp+57h+var_98]
0x1400176f1  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1400176f6  lea     r9, asc_14002D4FC; ": {}"
0x1400176fd  mov     r8d, ebx
0x140017700  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017707  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x14001770c  mov     rcx, [rbp+5Fh]; this
0x140017710  mov     r9d, edi; char *
0x140017713  mov     edx, 16Fh; void *
0x140017718  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14001771d  mov     ebx, eax
0x14001771f  lea     rcx, [rbp+57h+lpPathName]
0x140017723  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140017728  nop
0x140017729  jmp     loc_14001766A
0x14001772e  cmp     [rbp+57h+var_A0], r12b
0x140017732  jz      loc_1400177E5
0x140017738  mov     [rbp+57h+var_98], r12
0x14001773c  lea     rcx, [rbp+57h+var_98]; this
0x140017740  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x140017745  mov     edi, eax
0x140017747  test    eax, eax
0x140017749  jns     short loc_1400177B9
0x14001774b  mov     [rbp+57h+var_50], eax
0x14001774e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017755  test    rcx, rcx
0x140017758  jz      short loc_140017797
0x14001775a  lea     r9, aFailedCallingG; "Failed calling GetSystemSecurity"
0x140017761  mov     ebx, 3
0x140017766  mov     r8d, ebx
0x140017769  xor     edx, edx
0x14001776b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017770  lea     rax, [rbp+57h+var_50]
0x140017774  mov     [rbp+57h+var_98], rax
0x140017778  lea     rax, [rbp+57h+var_98]
0x14001777c  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x140017781  lea     r9, asc_14002D4FC; ": {}"
0x140017788  mov     r8d, ebx
0x14001778b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017792  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x140017797  mov     rcx, [rbp+5Fh]; this
0x14001779b  mov     r9d, edi; char *
0x14001779e  mov     edx, 175h; void *
0x1400177a3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400177a8  mov     ebx, eax
0x1400177aa  lea     rcx, [rbp+57h+lpPathName]
0x1400177ae  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400177b3  nop
0x1400177b4  jmp     loc_14001766A
0x1400177b9  mov     qword ptr [rbp+57h+var_78], 18h
0x1400177c1  mov     rax, [rbp+57h+var_98]
0x1400177c5  mov     qword ptr [rbp+57h+var_78+8], rax
0x1400177c9  xor     eax, eax
0x1400177cb  mov     [rbp+57h+var_68], rax
0x1400177cf  movups  xmm0, [rbp+57h+var_78]
0x1400177d3  movups  [rbp+57h+var_48], xmm0
0x1400177d7  movsd   xmm1, [rbp+57h+var_68]
0x1400177dc  movsd   [rbp+57h+var_38], xmm1
0x1400177e1  lea     r14, [rbp+57h+var_48]
0x1400177e5  mov     rdx, r14; lpSecurityAttributes
0x1400177e8  mov     rbx, [rbp+57h+lpPathName]
0x1400177ec  mov     rcx, rbx; lpPathName
0x1400177ef  call    cs:__imp_CreateDirectoryW
0x1400177f5  test    eax, eax
0x1400177f7  jnz     loc_140017AB6
0x1400177fd  call    cs:__imp_GetLastError
0x140017803  cmp     eax, 0B7h
0x140017808  jnz     short loc_140017819
0x14001780a  lea     rcx, [rbp+57h+lpPathName]
0x14001780e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140017813  nop
0x140017814  jmp     loc_140017AC0
0x140017819  mov     edx, 5Ch ; '\'; Ch
0x14001781e  mov     rcx, rbx; Str
0x140017821  call    cs:__imp_wcsrchr
0x140017827  mov     rsi, rax
0x14001782a  test    rax, rax
0x14001782d  jnz     loc_1400178B3
0x140017833  mov     edi, 80070003h
0x140017838  mov     [rbp+57h+var_50], edi
0x14001783b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017842  test    rcx, rcx
0x140017845  jz      short loc_14001788B
0x140017847  lea     rax, [rbp+57h+var_58]
0x14001784b  mov     qword ptr [rsp+0D0h+var_B0], rax
0x140017850  lea     r9, aCannotFindPare; "Cannot find parent for path: {}."
0x140017857  lea     ebx, [rsi+3]
0x14001785a  mov     r8d, ebx
0x14001785d  xor     edx, edx
0x14001785f  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140017864  lea     rax, [rbp+57h+var_50]
0x140017868  mov     [rbp+57h+var_98], rax
0x14001786c  lea     rax, [rbp+57h+var_98]
0x140017870  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x140017875  lea     r9, asc_14002D4FC; ": {}"
0x14001787c  mov     r8d, ebx
0x14001787f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017886  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001788b  mov     rcx, [rbp+5Fh]; this
0x14001788f  mov     r9d, edi; char *
0x140017892  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140017899  mov     edx, 188h; void *
0x14001789e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400178a3  nop
0x1400178a4  lea     rcx, [rbp+57h+lpPathName]
0x1400178a8  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400178ad  nop
0x1400178ae  jmp     loc_14001762E
0x1400178b3  sub     rsi, rbx
0x1400178b6  sar     rsi, 1
0x1400178b9  mov     [rbp+57h+var_98], r12
0x1400178bd  lea     rdx, [rsi+1]
0x1400178c1  lea     rcx, [rbp+57h+var_98]
0x1400178c5  call    ?AllocateArray@?$AutoNewArrayPtr@_W@Windows@@QEAAPEA_W_K@Z; Windows::AutoNewArrayPtr<wchar_t>::AllocateArray(unsigned __int64)
0x1400178ca  mov     rdi, [rbp+57h+var_98]
0x1400178ce  test    rdi, rdi
0x1400178d1  jnz     short loc_140017909
0x1400178d3  mov     rcx, [rbp+5Fh]; this
0x1400178d7  mov     ebx, 8007000Eh
0x1400178dc  mov     r9d, ebx; char *
0x1400178df  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1400178e6  mov     edx, 18Fh; void *
0x1400178eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400178f0  lea     rcx, [rbp+57h+var_98]
0x1400178f4  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x1400178f9  nop
0x1400178fa  lea     rcx, [rbp+57h+lpPathName]
0x1400178fe  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140017903  nop
0x140017904  jmp     loc_14001766A
0x140017909  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001790d  inc     rax
0x140017910  cmp     [rbx+rax*2], r12w
0x140017915  jnz     short loc_14001790D
0x140017917  cmp     rsi, rax
0x14001791a  ja      loc_1400179C8
0x140017920  mov     r9, rsi; unsigned __int64
0x140017923  mov     r8, rbx; wchar_t *
0x140017926  lea     rdx, [rsi+1]; unsigned __int64
0x14001792a  mov     rcx, rdi; wchar_t *
0x14001792d  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x140017932  mov     esi, eax
0x140017934  test    eax, eax
0x140017936  jns     loc_1400179C8
0x14001793c  mov     [rbp+57h+var_50], eax
0x14001793f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017946  test    rcx, rcx
0x140017949  jz      short loc_140017995
0x14001794b  mov     qword ptr [rbp+57h+var_88], rbx
0x14001794f  lea     rax, [rbp+57h+var_88]
0x140017953  mov     qword ptr [rsp+0D0h+var_B0], rax
0x140017958  lea     r9, aFailedToCopyPa; "Failed to copy parent of path: {}"
0x14001795f  mov     ebx, 3
0x140017964  mov     r8d, ebx
0x140017967  xor     edx, edx
0x140017969  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001796e  lea     rax, [rbp+57h+var_50]
0x140017972  mov     qword ptr [rbp+57h+var_80], rax
0x140017976  lea     rax, [rbp+57h+var_80]
0x14001797a  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x14001797f  lea     r9, asc_14002D4FC; ": {}"
0x140017986  mov     r8d, ebx
0x140017989  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017990  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017995  mov     rcx, [rbp+5Fh]; this
0x140017999  mov     r9d, esi; char *
0x14001799c  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1400179a3  mov     edx, 196h; void *
0x1400179a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400179ad  lea     rcx, [rbp+57h+var_98]
0x1400179b1  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x1400179b6  nop
0x1400179b7  lea     rcx, [rbp+57h+lpPathName]
0x1400179bb  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400179c0  nop
0x1400179c1  mov     eax, esi
0x1400179c3  jmp     loc_140017AC2
0x1400179c8  mov     rdx, r14
0x1400179cb  mov     rcx, rdi
0x1400179ce  call    RecursivelyCreateDirectory
0x1400179d3  mov     esi, eax
0x1400179d5  test    eax, eax
0x1400179d7  jns     loc_140017A67
0x1400179dd  mov     [rbp+57h+var_50], eax
0x1400179e0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400179e7  test    rcx, rcx
0x1400179ea  jz      short loc_140017A36
0x1400179ec  mov     qword ptr [rbp+57h+var_80], rdi
0x1400179f0  lea     rax, [rbp+57h+var_80]
0x1400179f4  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1400179f9  lea     r9, aFailedToCreate; "Failed to create path: {}"
0x140017a00  mov     ebx, 3
0x140017a05  mov     r8d, ebx
0x140017a08  xor     edx, edx
0x140017a0a  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140017a0f  lea     rax, [rbp+57h+var_50]
  ... truncated ...
```
