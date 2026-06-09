# TsSideTransport::InitializeRdpNanoTransport(void)

- ea: `0x18046b93c`
- end: `0x18046bdd0`
- name: `?InitializeRdpNanoTransport@TsSideTransport@@IEAAJXZ`
- size: `1172`
- prototype: `__int64 __fastcall(TsSideTransport *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18046b610`

## callees

- `0x1800031a8`
- `0x1800054f4`
- `0x18001cdc0`
- `0x1800204e8`
- `0x1800cf498`
- `0x1800cfa74`
- `0x1800d1db0`
- `0x180238aac`
- `0x18040fe30`
- `0x18046b93c`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18046ba81`
- `msvcrt!wcsrchr` at `0x18046ba81`
- `KERNEL32!LoadLibraryW` at `0x18046bba1`
- `KERNEL32!LoadLibraryW` at `0x18046bba1`
- `KERNEL32!GetModuleHandleExW` at `0x18046b99f`
- `KERNEL32!GetModuleHandleExW` at `0x18046b99f`
- `KERNEL32!GetLastError` at `0x18046b9ad`
- `KERNEL32!GetLastError` at `0x18046bbaf`
- `KERNEL32!GetLastError` at `0x18046bc03`
- `KERNEL32!GetLastError` at `0x18046bcb3`
- `KERNEL32!GetLastError` at `0x18046b9ad`
- `KERNEL32!GetLastError` at `0x18046bbaf`
- `KERNEL32!GetLastError` at `0x18046bc03`
- `KERNEL32!GetLastError` at `0x18046bcb3`
- `KERNEL32!GetProcAddress` at `0x18046bbf5`
- `KERNEL32!GetProcAddress` at `0x18046bbf5`
- `KERNEL32!FreeLibrary` at `0x18046bd6b`
- `KERNEL32!FreeLibrary` at `0x18046bd6b`
- `KERNEL32!GetModuleFileNameW` at `0x18046ba61`
- `KERNEL32!GetModuleFileNameW` at `0x18046ba61`

## string_xrefs

- `0x18046bac1`: `StringCchCat of file path failed`
- `0x18046bb78`: `Loading dll`
- `0x18046ba87`: `rdpnanoTransport.dll`
- `0x18046bbd3`: `Failed to load RdpNanoTransport dll`
- `0x18046bb1e`: `StringCchCopy of file path failed`
- `0x18046b9fc`: `clientcore\termsrv\client\plugins\sidetransport\tssidetransport.cpp`
- `0x18046bae8`: `clientcore\termsrv\client\plugins\sidetransport\tssidetransport.cpp`
- `0x18046bb45`: `clientcore\termsrv\client\plugins\sidetransport\tssidetransport.cpp`
- `0x18046bc9e`: `clientcore\termsrv\client\plugins\sidetransport\tssidetransport.cpp`
- `0x18046bcfe`: `clientcore\termsrv\client\plugins\sidetransport\tssidetransport.cpp`
- `0x18046bc77`: `CreateRdpNanoClientSideTransport failed`
- `0x18046bbeb`: `CreateRdpNanoClientSideTransport`
- `0x18046bc27`: `Failed to get CreateRdpNanoClientSideTransport address`

## pseudocode

```c
__int64 __fastcall TsSideTransport::InitializeRdpNanoTransport(TsSideTransport *this)
{
  HMODULE v2; // rdi
  signed int LastError; // eax
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  signed int v7; // ebx
  DWORD ModuleFileNameW; // eax
  wchar_t *v9; // rax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int *v13; // rdx
  const char *v14; // rax
  HMODULE LibraryW; // rax
  signed int v16; // eax
  const char *v17; // rax
  FARPROC ProcAddress; // rbx
  signed int v19; // eax
  signed int v20; // eax
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+54h] [rbp-ACh] BYREF
  const char *v24; // [rsp+58h] [rbp-A8h] BYREF
  const char *v25; // [rsp+60h] [rbp-A0h] BYREF
  const char *v26; // [rsp+68h] [rbp-98h] BYREF
  const char *v27; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  HMODULE phModule; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF

  phModule = 0;
  memset_0(Filename, 0, 0x20Au);
  v2 = 0;
  v28 = 0;
  if ( !GetModuleHandleExW(6u, (LPCWSTR)TsSideTransport::STATIC_DummyMethod, &phModule) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      v22 = 237;
      v26 = "Failed to get module handle to itself.";
      v23 = v7;
      v27 = "InitializeRdpNanoTransport";
      v25 = "clientcore\\termsrv\\client\\plugins\\sidetransport\\tssidetransport.cpp";
      v24 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v4,
        (unsigned int)&word_180882F56,
        v5,
        v6,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v25,
        (__int64)&v22,
        (__int64)&v27,
        (__int64)&v26);
    }
    goto LABEL_36;
  }
  ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x105u);
  if ( !ModuleFileNameW || ModuleFileNameW == 261 )
  {
    v20 = GetLastError();
    v7 = v20;
    if ( v20 > 0 )
      v7 = (unsigned __int16)v20 | 0x80070000;
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      v17 = "Failed to get the module file name";
      v23 = 241;
      v13 = (int *)byte_18088300B;
      goto LABEL_34;
    }
  }
  else
  {
    v9 = wcsrchr(Filename, 0x5Cu);
    if ( v9 )
    {
      v9[1] = 0;
      v7 = StringCchCatW(Filename, 0x105u, L"rdpnanoTransport.dll");
      if ( v7 < 0 )
      {
        v10 = dword_1808B5850;
        if ( (unsigned int)dword_1808B5850 <= 2 )
          goto LABEL_36;
        v23 = 249;
        v24 = "StringCchCat of file path failed";
        v13 = (int *)qword_180882FC0;
        v25 = "InitializeRdpNanoTransport";
        v27 = "clientcore\\termsrv\\client\\plugins\\sidetransport\\tssidetransport.cpp";
        v14 = "Error HResult failed";
        goto LABEL_35;
      }
    }
    else
    {
      v7 = StringCchCopyW(Filename, 0x105u, L"rdpnanoTransport.dll");
      if ( v7 < 0 )
      {
        if ( (unsigned int)dword_1808B5850 <= 2 )
          goto LABEL_36;
        v23 = 254;
        v24 = "StringCchCopy of file path failed";
        v13 = (int *)&word_18088307E;
        v25 = "InitializeRdpNanoTransport";
        v27 = "clientcore\\termsrv\\client\\plugins\\sidetransport\\tssidetransport.cpp";
        v14 = "Error HResult failed";
        goto LABEL_35;
      }
    }
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v24 = (const char *)Filename;
      v25 = "Loading dll";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v10,
        (unsigned int)&word_180883056,
        v11,
        v12,
        (__int64)&v25,
        (__int64)&v24);
    }
    LibraryW = LoadLibraryW(Filename);
    v2 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "CreateRdpNanoClientSideTransport");
      if ( ProcAddress )
      {
        wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::reset(&v28);
        v7 = ((__int64 (__fastcall *)(__int64, __int64 *))ProcAddress)(7, &v28);
        if ( v7 >= 0 || (unsigned int)dword_1808B5850 <= 2 )
          goto LABEL_36;
        v23 = 268;
        v24 = "CreateRdpNanoClientSideTransport failed";
        v13 = &dword_180882E14;
        v25 = "InitializeRdpNanoTransport";
        v27 = "clientcore\\termsrv\\client\\plugins\\sidetransport\\tssidetransport.cpp";
        v14 = "Error HResult failed";
LABEL_35:
        v26 = v14;
        v22 = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v10,
          (_DWORD)v13,
          v11,
          v12,
          (__int64)&v26,
          (__int64)&v22,
          (__int64)&v27,
          (__int64)&v23,
          (__int64)&v25,
          (__int64)&v24);
        goto LABEL_36;
      }
      v19 = GetLastError();
      v7 = v19;
      if ( v19 > 0 )
        v7 = (unsigned __int16)v19 | 0x80070000;
      if ( (unsigned int)dword_1808B5850 > 2 )
      {
        v17 = "Failed to get CreateRdpNanoClientSideTransport address";
        v23 = 265;
        v13 = (int *)byte_1808830C9;
        goto LABEL_34;
      }
    }
    else
    {
      v16 = GetLastError();
      v7 = v16;
      if ( v16 > 0 )
        v7 = (unsigned __int16)v16 | 0x80070000;
      if ( (unsigned int)dword_1808B5850 > 2 )
      {
        v17 = "Failed to load RdpNanoTransport dll";
        v23 = 261;
        v13 = &dword_180883114;
LABEL_34:
        v24 = v17;
        v25 = "InitializeRdpNanoTransport";
        v27 = "clientcore\\termsrv\\client\\plugins\\sidetransport\\tssidetransport.cpp";
        v14 = "Error condition failed";
        goto LABEL_35;
      }
    }
  }
LABEL_36:
  if ( !v28 && v2 )
  {
    FreeLibrary(v2);
    v2 = 0;
  }
  v24 = (char *)this + 104;
  CTSCriticalSection::Lock((TsSideTransport *)((char *)this + 104));
  wil::com_ptr_t<ISharedHandle,wil::err_returncode_policy>::operator=((char *)this + 88, &v28);
  *((_QWORD *)this + 12) = v2;
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v24);
  wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v28);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18046b93c  mov     [rsp-8+arg_8], rbx
0x18046b941  mov     [rsp-8+arg_10], rsi
0x18046b946  push    rbp
0x18046b947  push    rdi
0x18046b948  push    r15
0x18046b94a  lea     rbp, [rsp-1B0h]
0x18046b952  sub     rsp, 2B0h
0x18046b959  mov     rax, cs:__security_cookie
0x18046b960  xor     rax, rsp
0x18046b963  mov     [rbp+1C0h+var_20], rax
0x18046b96a  mov     rsi, rcx
0x18046b96d  mov     [rbp+1C0h+phModule], 0
0x18046b975  lea     rcx, [rbp+1C0h+Filename]; void *
0x18046b979  xor     edx, edx; Val
0x18046b97b  mov     r8d, 20Ah; Size
0x18046b981  call    memset_0
0x18046b986  xor     edi, edi
0x18046b988  mov     [rsp+2C0h+var_248], 0
0x18046b991  lea     r8, [rbp+1C0h+phModule]; phModule
0x18046b995  lea     rdx, ?STATIC_DummyMethod@TsSideTransport@@KAKPEAX@Z; lpModuleName
0x18046b99c  lea     ecx, [rdi+6]; dwFlags
0x18046b99f  call    cs:__imp_GetModuleHandleExW
0x18046b9a5  test    eax, eax
0x18046b9a7  jnz     loc_18046BA50
0x18046b9ad  call    cs:__imp_GetLastError
0x18046b9b3  mov     ebx, eax
0x18046b9b5  test    eax, eax
0x18046b9b7  jle     short loc_18046B9C2
0x18046b9b9  movzx   ebx, ax
0x18046b9bc  or      ebx, 80070000h
0x18046b9c2  mov     eax, cs:dword_1808B5850
0x18046b9c8  cmp     eax, 2
0x18046b9cb  jbe     loc_18046BD5B
0x18046b9d1  lea     rax, aFailedToGetMod_0; "Failed to get module handle to itself."
0x18046b9d8  mov     [rsp+2C0h+var_270], 0EDh
0x18046b9e0  mov     [rsp+2C0h+var_258], rax
0x18046b9e5  lea     rdx, word_180882F56
0x18046b9ec  lea     rax, aInitializerdpn_0; "InitializeRdpNanoTransport"
0x18046b9f3  mov     [rsp+2C0h+var_26C], ebx
0x18046b9f7  mov     [rsp+2C0h+var_250], rax
0x18046b9fc  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\client\\plugins\\s"...
0x18046ba03  mov     [rsp+2C0h+var_260], rax
0x18046ba08  lea     rax, aErrorCondition; "Error condition failed"
0x18046ba0f  mov     [rsp+2C0h+var_268], rax
0x18046ba14  lea     rax, [rsp+2C0h+var_258]
0x18046ba19  mov     [rsp+2C0h+var_278], rax
0x18046ba1e  lea     rax, [rsp+2C0h+var_250]
0x18046ba23  mov     [rsp+2C0h+var_280], rax
0x18046ba28  lea     rax, [rsp+2C0h+var_270]
0x18046ba2d  mov     [rsp+2C0h+var_288], rax
0x18046ba32  lea     rax, [rsp+2C0h+var_260]
0x18046ba37  mov     [rsp+2C0h+var_290], rax
0x18046ba3c  lea     rax, [rsp+2C0h+var_26C]
0x18046ba41  mov     [rsp+2C0h+var_298], rax
0x18046ba46  lea     rax, [rsp+2C0h+var_268]
0x18046ba4b  jmp     loc_18046BD51
0x18046ba50  mov     rcx, [rbp+1C0h+phModule]; hModule
0x18046ba54  lea     rdx, [rbp+1C0h+Filename]; lpFilename
0x18046ba58  mov     r15d, 105h
0x18046ba5e  mov     r8d, r15d; nSize
0x18046ba61  call    cs:__imp_GetModuleFileNameW
0x18046ba67  test    eax, eax
0x18046ba69  jz      loc_18046BCB3
0x18046ba6f  cmp     eax, r15d
0x18046ba72  jz      loc_18046BCB3
0x18046ba78  mov     edx, 5Ch ; '\'; Ch
0x18046ba7d  lea     rcx, [rbp+1C0h+Filename]; Str
0x18046ba81  call    cs:__imp_wcsrchr
0x18046ba87  lea     r8, aRdpnanotranspo; "rdpnanoTransport.dll"
0x18046ba8e  mov     edx, r15d; unsigned __int64
0x18046ba91  mov     rcx, rax
0x18046ba94  test    rax, rax
0x18046ba97  jz      short loc_18046BB00
0x18046ba99  xor     eax, eax
0x18046ba9b  mov     [rcx+2], ax
0x18046ba9f  lea     rcx, [rbp+1C0h+Filename]; unsigned __int16 *
0x18046baa3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18046baa8  mov     ebx, eax
0x18046baaa  test    eax, eax
0x18046baac  jns     loc_18046BB5D
0x18046bab2  mov     ecx, cs:dword_1808B5850
0x18046bab8  cmp     ecx, 2
0x18046babb  jbe     loc_18046BD5B
0x18046bac1  lea     rax, aStringcchcatOf; "StringCchCat of file path failed"
0x18046bac8  mov     [rsp+2C0h+var_26C], 0F9h
0x18046bad0  mov     [rsp+2C0h+var_268], rax
0x18046bad5  lea     rdx, qword_180882FC0
0x18046badc  lea     rax, aInitializerdpn_0; "InitializeRdpNanoTransport"
0x18046bae3  mov     [rsp+2C0h+var_260], rax
0x18046bae8  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\client\\plugins\\s"...
0x18046baef  mov     [rsp+2C0h+var_250], rax
0x18046baf4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18046bafb  jmp     loc_18046BD11
0x18046bb00  lea     rcx, [rbp+1C0h+Filename]; unsigned __int16 *
0x18046bb04  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18046bb09  mov     ebx, eax
0x18046bb0b  test    eax, eax
0x18046bb0d  jns     short loc_18046BB5D
0x18046bb0f  mov     eax, cs:dword_1808B5850
0x18046bb15  cmp     eax, 2
0x18046bb18  jbe     loc_18046BD5B
0x18046bb1e  lea     rax, aStringcchcopyO_0; "StringCchCopy of file path failed"
0x18046bb25  mov     [rsp+2C0h+var_26C], 0FEh
0x18046bb2d  mov     [rsp+2C0h+var_268], rax
0x18046bb32  lea     rdx, word_18088307E
0x18046bb39  lea     rax, aInitializerdpn_0; "InitializeRdpNanoTransport"
0x18046bb40  mov     [rsp+2C0h+var_260], rax
0x18046bb45  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\client\\plugins\\s"...
0x18046bb4c  mov     [rsp+2C0h+var_250], rax
0x18046bb51  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18046bb58  jmp     loc_18046BD11
0x18046bb5d  mov     eax, cs:dword_1808B5850
0x18046bb63  cmp     eax, 4
0x18046bb66  jbe     short loc_18046BB9D
0x18046bb68  lea     rax, [rbp+1C0h+Filename]
0x18046bb6c  mov     [rsp+2C0h+var_268], rax
0x18046bb71  lea     rdx, word_180883056
0x18046bb78  lea     rax, aLoadingDll; "Loading dll"
0x18046bb7f  mov     [rsp+2C0h+var_260], rax
0x18046bb84  lea     rax, [rsp+2C0h+var_268]
0x18046bb89  mov     [rsp+2C0h+var_298], rax
0x18046bb8e  lea     rax, [rsp+2C0h+var_260]
0x18046bb93  mov     [rsp+2C0h+var_2A0], rax
0x18046bb98  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18046bb9d  lea     rcx, [rbp+1C0h+Filename]; lpLibFileName
0x18046bba1  call    cs:__imp_LoadLibraryW
0x18046bba7  mov     rdi, rax
0x18046bbaa  test    rax, rax
0x18046bbad  jnz     short loc_18046BBEB
0x18046bbaf  call    cs:__imp_GetLastError
0x18046bbb5  mov     ebx, eax
0x18046bbb7  test    eax, eax
0x18046bbb9  jle     short loc_18046BBC4
0x18046bbbb  movzx   ebx, ax
0x18046bbbe  or      ebx, 80070000h
0x18046bbc4  mov     eax, cs:dword_1808B5850
0x18046bbca  cmp     eax, 2
0x18046bbcd  jbe     loc_18046BD5B
0x18046bbd3  lea     rax, aFailedToLoadRd; "Failed to load RdpNanoTransport dll"
0x18046bbda  mov     [rsp+2C0h+var_26C], r15d
0x18046bbdf  lea     rdx, dword_180883114
0x18046bbe6  jmp     loc_18046BCED
0x18046bbeb  lea     rdx, aCreaterdpnanoc; "CreateRdpNanoClientSideTransport"
0x18046bbf2  mov     rcx, rax; hModule
0x18046bbf5  call    cs:__imp_GetProcAddress
0x18046bbfb  mov     rbx, rax
0x18046bbfe  test    rax, rax
0x18046bc01  jnz     short loc_18046BC42
0x18046bc03  call    cs:__imp_GetLastError
0x18046bc09  mov     ebx, eax
0x18046bc0b  test    eax, eax
0x18046bc0d  jle     short loc_18046BC18
0x18046bc0f  movzx   ebx, ax
0x18046bc12  or      ebx, 80070000h
0x18046bc18  mov     eax, cs:dword_1808B5850
0x18046bc1e  cmp     eax, 2
0x18046bc21  jbe     loc_18046BD5B
0x18046bc27  lea     rax, aFailedToGetCre; "Failed to get CreateRdpNanoClientSideTr"...
0x18046bc2e  mov     [rsp+2C0h+var_26C], 109h
0x18046bc36  lea     rdx, byte_1808830C9
0x18046bc3d  jmp     loc_18046BCED
0x18046bc42  lea     rcx, [rsp+2C0h+var_248]
0x18046bc47  call    ?reset@?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::reset(void)
0x18046bc4c  lea     rdx, [rsp+2C0h+var_248]
0x18046bc51  mov     ecx, 7
0x18046bc56  mov     rax, rbx
0x18046bc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18046bc5e  mov     ebx, eax
0x18046bc60  test    eax, eax
0x18046bc62  jns     loc_18046BD5B
0x18046bc68  mov     eax, cs:dword_1808B5850
0x18046bc6e  cmp     eax, 2
0x18046bc71  jbe     loc_18046BD5B
0x18046bc77  lea     rax, aCreaterdpnanoc_0; "CreateRdpNanoClientSideTransport failed"
0x18046bc7e  mov     [rsp+2C0h+var_26C], 10Ch
0x18046bc86  mov     [rsp+2C0h+var_268], rax
0x18046bc8b  lea     rdx, dword_180882E14
0x18046bc92  lea     rax, aInitializerdpn_0; "InitializeRdpNanoTransport"
0x18046bc99  mov     [rsp+2C0h+var_260], rax
0x18046bc9e  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\client\\plugins\\s"...
0x18046bca5  mov     [rsp+2C0h+var_250], rax
0x18046bcaa  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18046bcb1  jmp     short loc_18046BD11
0x18046bcb3  call    cs:__imp_GetLastError
0x18046bcb9  mov     ebx, eax
0x18046bcbb  test    eax, eax
0x18046bcbd  jle     short loc_18046BCC8
0x18046bcbf  movzx   ebx, ax
0x18046bcc2  or      ebx, 80070000h
0x18046bcc8  mov     eax, cs:dword_1808B5850
0x18046bcce  cmp     eax, 2
0x18046bcd1  jbe     loc_18046BD5B
0x18046bcd7  lea     rax, aFailedToGetThe_0; "Failed to get the module file name"
0x18046bcde  mov     [rsp+2C0h+var_26C], 0F1h
0x18046bce6  lea     rdx, byte_18088300B
0x18046bced  mov     [rsp+2C0h+var_268], rax
0x18046bcf2  lea     rax, aInitializerdpn_0; "InitializeRdpNanoTransport"
0x18046bcf9  mov     [rsp+2C0h+var_260], rax
0x18046bcfe  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\client\\plugins\\s"...
0x18046bd05  mov     [rsp+2C0h+var_250], rax
0x18046bd0a  lea     rax, aErrorCondition; "Error condition failed"
0x18046bd11  mov     [rsp+2C0h+var_258], rax
0x18046bd16  lea     rax, [rsp+2C0h+var_268]
0x18046bd1b  mov     [rsp+2C0h+var_278], rax
0x18046bd20  lea     rax, [rsp+2C0h+var_260]
0x18046bd25  mov     [rsp+2C0h+var_280], rax
0x18046bd2a  lea     rax, [rsp+2C0h+var_26C]
0x18046bd2f  mov     [rsp+2C0h+var_288], rax
0x18046bd34  lea     rax, [rsp+2C0h+var_250]
0x18046bd39  mov     [rsp+2C0h+var_290], rax
0x18046bd3e  lea     rax, [rsp+2C0h+var_270]
0x18046bd43  mov     [rsp+2C0h+var_298], rax
0x18046bd48  lea     rax, [rsp+2C0h+var_258]
0x18046bd4d  mov     [rsp+2C0h+var_270], ebx
0x18046bd51  mov     [rsp+2C0h+var_2A0], rax
0x18046bd56  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18046bd5b  cmp     [rsp+2C0h+var_248], 0
0x18046bd61  jnz     short loc_18046BD73
0x18046bd63  test    rdi, rdi
0x18046bd66  jz      short loc_18046BD73
0x18046bd68  mov     rcx, rdi; hLibModule
0x18046bd6b  call    cs:__imp_FreeLibrary
0x18046bd71  xor     edi, edi
0x18046bd73  lea     rcx, [rsi+68h]; this
0x18046bd77  mov     [rsp+2C0h+var_268], rcx
0x18046bd7c  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18046bd81  lea     rcx, [rsi+58h]
0x18046bd85  lea     rdx, [rsp+2C0h+var_248]
0x18046bd8a  call    ??4?$com_ptr_t@UISharedHandle@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<ISharedHandle,wil::err_returncode_policy>::operator=(wil::com_ptr_t<ISharedHandle,wil::err_returncode_policy> const &)
0x18046bd8f  lea     rcx, [rsp+2C0h+var_268]; this
0x18046bd94  mov     [rsi+60h], rdi
0x18046bd98  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18046bd9d  lea     rcx, [rsp+2C0h+var_248]; void *
0x18046bda2  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x18046bda7  mov     eax, ebx
0x18046bda9  mov     rcx, [rbp+1C0h+var_20]
0x18046bdb0  xor     rcx, rsp; StackCookie
0x18046bdb3  call    __security_check_cookie
0x18046bdb8  lea     r11, [rsp+2C0h+var_10]
0x18046bdc0  mov     rbx, [r11+28h]
0x18046bdc4  mov     rsi, [r11+30h]
0x18046bdc8  mov     rsp, r11
0x18046bdcb  pop     r15
0x18046bdcd  pop     rdi
0x18046bdce  pop     rbp
0x18046bdcf  retn
```
