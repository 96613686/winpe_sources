# SideTransportStream::InitializeRdpNanoTransport(void)

- ea: `0x1801536d0`
- end: `0x180153b69`
- name: `?InitializeRdpNanoTransport@SideTransportStream@@IEAAJXZ`
- size: `1177`
- prototype: `__int64 __fastcall(SideTransportStream *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180151840`

## callees

- `0x180001574`
- `0x18000202c`
- `0x18003b118`
- `0x18007e9e0`
- `0x18007f42c`
- `0x18009f060`
- `0x1800a3270`
- `0x1800a3474`
- `0x1800d4788`
- `0x180150ef0`
- `0x1801536d0`
- `0x18019c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18015380a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18015380a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180153987`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180153987`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801537eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801537eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18015372a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18015372a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180153738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180153941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180153995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180153a5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180153738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180153941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180153995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180153a5a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180153b1f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180153b1f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180153926`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180153926`

## string_xrefs

- `0x180153846`: `StringCchCat of file path failed`
- `0x1801538a3`: `StringCchCopy of file path failed`
- `0x1801538fd`: `Loading dll`
- `0x180153787`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x18015386d`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x1801538ca`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180153a45`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180153aa5`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180153810`: `rdpnanoTransport.dll`
- `0x180153980`: `CreateRdpNanoServerSideTransport`
- `0x180153965`: `Failed to load RdpNanoTransport dll`
- `0x180153a1e`: `CreateRdpNanoServerSideTransport failed`
- `0x1801539b9`: `Failed to get CreateRdpNanoServerSideTransport address`

## pseudocode

```c
__int64 __fastcall SideTransportStream::InitializeRdpNanoTransport(RTL_SRWLOCK *this)
{
  signed int LastError; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  signed int v6; // edi
  DWORD ModuleFileNameW; // eax
  wchar_t *v8; // rax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  char *v12; // rdx
  const char *v13; // rax
  HMODULE LibraryW; // rax
  HMODULE Ptr; // rcx
  signed int v16; // eax
  const char *v17; // rax
  FARPROC ProcAddress; // rbx
  signed int v19; // eax
  __int64 v20; // rcx
  signed int v21; // eax
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh] BYREF
  const char *v25; // [rsp+58h] [rbp-A8h] BYREF
  const char *v26; // [rsp+60h] [rbp-A0h] BYREF
  const char *v27; // [rsp+68h] [rbp-98h] BYREF
  const char *v28; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h] BYREF
  HMODULE phModule; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF

  phModule = 0;
  memset_0(Filename, 0, 0x20Au);
  v29 = 0;
  if ( !GetModuleHandleExW(6u, &word_1801B83A0, &phModule) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v23 = 861;
      v27 = "Failed to get module handle to itself.";
      v24 = v6;
      v28 = "InitializeRdpNanoTransport";
      v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
      v25 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)qword_18029B408,
        v4,
        v5,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v26,
        (__int64)&v23,
        (__int64)&v28,
        (__int64)&v27);
    }
    goto LABEL_38;
  }
  ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x105u);
  if ( !ModuleFileNameW || ModuleFileNameW == 261 )
  {
    v21 = GetLastError();
    v6 = v21;
    if ( v21 > 0 )
      v6 = (unsigned __int16)v21 | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v17 = "Failed to get the module file name";
      v24 = 865;
      v12 = byte_18029B893;
      goto LABEL_36;
    }
  }
  else
  {
    v8 = wcsrchr(Filename, 0x5Cu);
    if ( v8 )
    {
      v8[1] = 0;
      v6 = StringCchCatW(Filename, 0x105u, L"rdpnanoTransport.dll");
      if ( v6 < 0 )
      {
        v9 = (int)CallbackContext;
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_38;
        v24 = 873;
        v25 = "StringCchCat of file path failed";
        v12 = byte_18029B7FD;
        v26 = "InitializeRdpNanoTransport";
        v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
        v13 = "Error HResult failed";
        goto LABEL_37;
      }
    }
    else
    {
      v6 = StringCchCopyW(Filename, 0x105u, L"rdpnanoTransport.dll");
      if ( v6 < 0 )
      {
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_38;
        v24 = 878;
        v25 = "StringCchCopy of file path failed";
        v12 = byte_18029C91B;
        v26 = "InitializeRdpNanoTransport";
        v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
        v13 = "Error HResult failed";
        goto LABEL_37;
      }
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      v25 = (const char *)Filename;
      v26 = "Loading dll";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v9,
        (unsigned int)&dword_18029B5E4,
        v10,
        v11,
        (__int64)&v26,
        (__int64)&v25);
    }
    LibraryW = LoadLibraryW(Filename);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      &this[15],
      LibraryW);
    Ptr = (HMODULE)this[15].Ptr;
    if ( Ptr )
    {
      ProcAddress = GetProcAddress(Ptr, "CreateRdpNanoServerSideTransport");
      if ( ProcAddress )
      {
        v20 = v29;
        v29 = 0;
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        v6 = ((__int64 (__fastcall *)(__int64, __int64 *))ProcAddress)(7, &v29);
        if ( v6 < 0 && (unsigned int)CallbackContext > 2 )
        {
          v24 = 892;
          v25 = "CreateRdpNanoServerSideTransport failed";
          v12 = (char *)word_18029CB6A;
          v26 = "InitializeRdpNanoTransport";
          v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
          v13 = "Error HResult failed";
LABEL_37:
          v27 = v13;
          v23 = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v9,
            (_DWORD)v12,
            v10,
            v11,
            (__int64)&v27,
            (__int64)&v23,
            (__int64)&v28,
            (__int64)&v24,
            (__int64)&v26,
            (__int64)&v25);
        }
      }
      else
      {
        v19 = GetLastError();
        v6 = v19;
        if ( v19 > 0 )
          v6 = (unsigned __int16)v19 | 0x80070000;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v17 = "Failed to get CreateRdpNanoServerSideTransport address";
          v24 = 889;
          v12 = (char *)qword_18029B848;
          goto LABEL_36;
        }
      }
    }
    else
    {
      v16 = GetLastError();
      v6 = v16;
      if ( v16 > 0 )
        v6 = (unsigned __int16)v16 | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v17 = "Failed to load RdpNanoTransport dll";
        v24 = 885;
        v12 = byte_18029CAB1;
LABEL_36:
        v25 = v17;
        v26 = "InitializeRdpNanoTransport";
        v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
        v13 = "Error condition failed";
        goto LABEL_37;
      }
    }
  }
LABEL_38:
  if ( !v29 )
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      &this[15],
      0);
  AcquireSRWLockExclusive(this + 16);
  v25 = (const char *)&this[16];
  wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy>::operator=(&this[14], &v29);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v25);
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v29);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801536d0  push    rbp
0x1801536d2  push    rbx
0x1801536d3  push    rsi
0x1801536d4  push    rdi
0x1801536d5  lea     rbp, [rsp-1B8h]
0x1801536dd  sub     rsp, 2B8h
0x1801536e4  mov     rax, cs:__security_cookie
0x1801536eb  xor     rax, rsp
0x1801536ee  mov     [rbp+1D0h+var_30], rax
0x1801536f5  mov     rsi, rcx
0x1801536f8  mov     [rbp+1D0h+phModule], 0
0x180153700  lea     rcx, [rbp+1D0h+Filename]; void *
0x180153704  xor     edx, edx; Val
0x180153706  mov     r8d, 20Ah; Size
0x18015370c  call    memset_0
0x180153711  lea     r8, [rbp+1D0h+phModule]; phModule
0x180153715  mov     [rsp+2D0h+var_258], 0
0x18015371e  lea     rdx, word_1801B83A0; lpModuleName
0x180153725  mov     ecx, 6; dwFlags
0x18015372a  call    cs:__imp_GetModuleHandleExW
0x180153730  test    eax, eax
0x180153732  jnz     loc_1801537DB
0x180153738  call    cs:__imp_GetLastError
0x18015373e  mov     edi, eax
0x180153740  test    eax, eax
0x180153742  jle     short loc_18015374D
0x180153744  movzx   edi, ax
0x180153747  or      edi, 80070000h
0x18015374d  mov     eax, cs:CallbackContext
0x180153753  cmp     eax, 2
0x180153756  jbe     loc_180153B02
0x18015375c  lea     rax, aFailedToGetMod; "Failed to get module handle to itself."
0x180153763  mov     [rsp+2D0h+var_280], 35Dh
0x18015376b  mov     [rsp+2D0h+var_268], rax
0x180153770  lea     rdx, qword_18029B408
0x180153777  lea     rax, aInitializerdpn_0; "InitializeRdpNanoTransport"
0x18015377e  mov     [rsp+2D0h+var_27C], edi
0x180153782  mov     [rsp+2D0h+var_260], rax
0x180153787  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18015378e  mov     [rsp+2D0h+var_270], rax
0x180153793  lea     rax, aErrorCondition; "Error condition failed"
0x18015379a  mov     [rsp+2D0h+var_278], rax
0x18015379f  lea     rax, [rsp+2D0h+var_268]
0x1801537a4  mov     [rsp+2D0h+var_288], rax
0x1801537a9  lea     rax, [rsp+2D0h+var_260]
0x1801537ae  mov     [rsp+2D0h+var_290], rax
0x1801537b3  lea     rax, [rsp+2D0h+var_280]
0x1801537b8  mov     [rsp+2D0h+var_298], rax
0x1801537bd  lea     rax, [rsp+2D0h+var_270]
0x1801537c2  mov     [rsp+2D0h+var_2A0], rax
0x1801537c7  lea     rax, [rsp+2D0h+var_27C]
0x1801537cc  mov     [rsp+2D0h+var_2A8], rax
0x1801537d1  lea     rax, [rsp+2D0h+var_278]
0x1801537d6  jmp     loc_180153AF8
0x1801537db  mov     rcx, [rbp+1D0h+phModule]; hModule
0x1801537df  lea     rdx, [rbp+1D0h+Filename]; lpFilename
0x1801537e3  mov     ebx, 105h
0x1801537e8  mov     r8d, ebx; nSize
0x1801537eb  call    cs:__imp_GetModuleFileNameW
0x1801537f1  test    eax, eax
0x1801537f3  jz      loc_180153A5A
0x1801537f9  cmp     eax, ebx
0x1801537fb  jz      loc_180153A5A
0x180153801  mov     edx, 5Ch ; '\'; Ch
0x180153806  lea     rcx, [rbp+1D0h+Filename]; Str
0x18015380a  call    cs:__imp_wcsrchr
0x180153810  lea     r8, aRdpnanotranspo; "rdpnanoTransport.dll"
0x180153817  mov     edx, ebx; unsigned __int64
0x180153819  test    rax, rax
0x18015381c  jz      short loc_180153885
0x18015381e  xor     ecx, ecx
0x180153820  mov     [rax+2], cx
0x180153824  lea     rcx, [rbp+1D0h+Filename]; unsigned __int16 *
0x180153828  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18015382d  mov     edi, eax
0x18015382f  test    eax, eax
0x180153831  jns     loc_1801538E2
0x180153837  mov     ecx, cs:CallbackContext
0x18015383d  cmp     ecx, 2
0x180153840  jbe     loc_180153B02
0x180153846  lea     rax, aStringcchcatOf; "StringCchCat of file path failed"
0x18015384d  mov     [rsp+2D0h+var_27C], 369h
0x180153855  mov     [rsp+2D0h+var_278], rax
0x18015385a  lea     rdx, byte_18029B7FD
0x180153861  lea     rax, aInitializerdpn_0; "InitializeRdpNanoTransport"
0x180153868  mov     [rsp+2D0h+var_270], rax
0x18015386d  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180153874  mov     [rsp+2D0h+var_260], rax
0x180153879  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180153880  jmp     loc_180153AB8
0x180153885  lea     rcx, [rbp+1D0h+Filename]; unsigned __int16 *
0x180153889  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18015388e  mov     edi, eax
0x180153890  test    eax, eax
0x180153892  jns     short loc_1801538E2
0x180153894  mov     eax, cs:CallbackContext
0x18015389a  cmp     eax, 2
0x18015389d  jbe     loc_180153B02
0x1801538a3  lea     rax, aStringcchcopyO_2; "StringCchCopy of file path failed"
0x1801538aa  mov     [rsp+2D0h+var_27C], 36Eh
0x1801538b2  mov     [rsp+2D0h+var_278], rax
0x1801538b7  lea     rdx, byte_18029C91B
0x1801538be  lea     rax, aInitializerdpn_0; "InitializeRdpNanoTransport"
0x1801538c5  mov     [rsp+2D0h+var_270], rax
0x1801538ca  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801538d1  mov     [rsp+2D0h+var_260], rax
0x1801538d6  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1801538dd  jmp     loc_180153AB8
0x1801538e2  mov     eax, cs:CallbackContext
0x1801538e8  cmp     eax, 4
0x1801538eb  jbe     short loc_180153922
0x1801538ed  lea     rax, [rbp+1D0h+Filename]
0x1801538f1  mov     [rsp+2D0h+var_278], rax
0x1801538f6  lea     rdx, dword_18029B5E4
0x1801538fd  lea     rax, aLoadingDll; "Loading dll"
0x180153904  mov     [rsp+2D0h+var_270], rax
0x180153909  lea     rax, [rsp+2D0h+var_278]
0x18015390e  mov     [rsp+2D0h+var_2A8], rax
0x180153913  lea     rax, [rsp+2D0h+var_270]
0x180153918  mov     [rsp+2D0h+var_2B0], rax
0x18015391d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180153922  lea     rcx, [rbp+1D0h+Filename]; lpLibFileName
0x180153926  call    cs:__imp_LoadLibraryW
0x18015392c  mov     rdx, rax
0x18015392f  lea     rcx, [rsi+78h]
0x180153933  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180153938  mov     rcx, [rsi+78h]; hModule
0x18015393c  test    rcx, rcx
0x18015393f  jnz     short loc_180153980
0x180153941  call    cs:__imp_GetLastError
0x180153947  mov     edi, eax
0x180153949  test    eax, eax
0x18015394b  jle     short loc_180153956
0x18015394d  movzx   edi, ax
0x180153950  or      edi, 80070000h
0x180153956  mov     eax, cs:CallbackContext
0x18015395c  cmp     eax, 2
0x18015395f  jbe     loc_180153B02
0x180153965  lea     rax, aFailedToLoadRd; "Failed to load RdpNanoTransport dll"
0x18015396c  mov     [rsp+2D0h+var_27C], 375h
0x180153974  lea     rdx, byte_18029CAB1
0x18015397b  jmp     loc_180153A94
0x180153980  lea     rdx, aCreaterdpnanos; "CreateRdpNanoServerSideTransport"
0x180153987  call    cs:__imp_GetProcAddress
0x18015398d  mov     rbx, rax
0x180153990  test    rax, rax
0x180153993  jnz     short loc_1801539D4
0x180153995  call    cs:__imp_GetLastError
0x18015399b  mov     edi, eax
0x18015399d  test    eax, eax
0x18015399f  jle     short loc_1801539AA
0x1801539a1  movzx   edi, ax
0x1801539a4  or      edi, 80070000h
0x1801539aa  mov     eax, cs:CallbackContext
0x1801539b0  cmp     eax, 2
0x1801539b3  jbe     loc_180153B02
0x1801539b9  lea     rax, aFailedToGetCre; "Failed to get CreateRdpNanoServerSideTr"...
0x1801539c0  mov     [rsp+2D0h+var_27C], 379h
0x1801539c8  lea     rdx, qword_18029B848
0x1801539cf  jmp     loc_180153A94
0x1801539d4  mov     rcx, [rsp+2D0h+var_258]
0x1801539d9  mov     [rsp+2D0h+var_258], 0
0x1801539e2  test    rcx, rcx
0x1801539e5  jz      short loc_1801539F3
0x1801539e7  mov     rax, [rcx]
0x1801539ea  mov     rax, [rax+10h]
0x1801539ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801539f3  lea     rdx, [rsp+2D0h+var_258]
0x1801539f8  mov     ecx, 7
0x1801539fd  mov     rax, rbx
0x180153a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180153a05  mov     edi, eax
0x180153a07  test    eax, eax
0x180153a09  jns     loc_180153B02
0x180153a0f  mov     eax, cs:CallbackContext
0x180153a15  cmp     eax, 2
0x180153a18  jbe     loc_180153B02
0x180153a1e  lea     rax, aCreaterdpnanos_0; "CreateRdpNanoServerSideTransport failed"
0x180153a25  mov     [rsp+2D0h+var_27C], 37Ch
0x180153a2d  mov     [rsp+2D0h+var_278], rax
0x180153a32  lea     rdx, word_18029CB6A
0x180153a39  lea     rax, aInitializerdpn_0; "InitializeRdpNanoTransport"
0x180153a40  mov     [rsp+2D0h+var_270], rax
0x180153a45  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180153a4c  mov     [rsp+2D0h+var_260], rax
0x180153a51  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180153a58  jmp     short loc_180153AB8
0x180153a5a  call    cs:__imp_GetLastError
0x180153a60  mov     edi, eax
0x180153a62  test    eax, eax
0x180153a64  jle     short loc_180153A6F
0x180153a66  movzx   edi, ax
0x180153a69  or      edi, 80070000h
0x180153a6f  mov     eax, cs:CallbackContext
0x180153a75  cmp     eax, 2
0x180153a78  jbe     loc_180153B02
0x180153a7e  lea     rax, aFailedToGetThe_1; "Failed to get the module file name"
0x180153a85  mov     [rsp+2D0h+var_27C], 361h
0x180153a8d  lea     rdx, byte_18029B893
0x180153a94  mov     [rsp+2D0h+var_278], rax
0x180153a99  lea     rax, aInitializerdpn_0; "InitializeRdpNanoTransport"
0x180153aa0  mov     [rsp+2D0h+var_270], rax
0x180153aa5  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180153aac  mov     [rsp+2D0h+var_260], rax
0x180153ab1  lea     rax, aErrorCondition; "Error condition failed"
0x180153ab8  mov     [rsp+2D0h+var_268], rax
0x180153abd  lea     rax, [rsp+2D0h+var_278]
0x180153ac2  mov     [rsp+2D0h+var_288], rax
0x180153ac7  lea     rax, [rsp+2D0h+var_270]
0x180153acc  mov     [rsp+2D0h+var_290], rax
0x180153ad1  lea     rax, [rsp+2D0h+var_27C]
0x180153ad6  mov     [rsp+2D0h+var_298], rax
0x180153adb  lea     rax, [rsp+2D0h+var_260]
0x180153ae0  mov     [rsp+2D0h+var_2A0], rax
0x180153ae5  lea     rax, [rsp+2D0h+var_280]
0x180153aea  mov     [rsp+2D0h+var_2A8], rax
0x180153aef  lea     rax, [rsp+2D0h+var_268]
0x180153af4  mov     [rsp+2D0h+var_280], edi
0x180153af8  mov     [rsp+2D0h+var_2B0], rax
0x180153afd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180153b02  cmp     [rsp+2D0h+var_258], 0
0x180153b08  jnz     short loc_180153B15
0x180153b0a  lea     rcx, [rsi+78h]
0x180153b0e  xor     edx, edx
0x180153b10  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180153b15  lea     rbx, [rsi+80h]
0x180153b1c  mov     rcx, rbx; SRWLock
0x180153b1f  call    cs:__imp_AcquireSRWLockExclusive
0x180153b25  lea     rcx, [rsi+70h]
0x180153b29  mov     [rsp+2D0h+var_278], rbx
0x180153b2e  lea     rdx, [rsp+2D0h+var_258]
0x180153b33  call    ??4?$com_ptr_t@UIRdpNanoServerTransport@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy> const &)
0x180153b38  lea     rcx, [rsp+2D0h+var_278]
0x180153b3d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180153b42  lea     rcx, [rsp+2D0h+var_258]
0x180153b47  call    ??1?$com_ptr_t@UIRDPCollection@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(void)
0x180153b4c  mov     eax, edi
0x180153b4e  mov     rcx, [rbp+1D0h+var_30]
0x180153b55  xor     rcx, rsp; StackCookie
0x180153b58  call    __security_check_cookie
0x180153b5d  add     rsp, 2B8h
0x180153b64  pop     rdi
0x180153b65  pop     rsi
0x180153b66  pop     rbx
0x180153b67  pop     rbp
0x180153b68  retn
```
