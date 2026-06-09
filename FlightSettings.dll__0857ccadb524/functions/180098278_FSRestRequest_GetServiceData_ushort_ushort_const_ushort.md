# FSRestRequest::GetServiceData(ushort * *,ushort const *,ushort * *)

- ea: `0x180098278`
- end: `0x18009879d`
- name: `?GetServiceData@FSRestRequest@@AEAAJPEAPEAGPEBG0@Z`
- size: `1317`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, unsigned __int16 **, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180097f64`
- `0x180098148`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x18000f9b8`
- `0x180013da0`
- `0x1800177bc`
- `0x180019214`
- `0x18001c6f4`
- `0x180085a24`
- `0x180086644`
- `0x1800880cc`
- `0x18008a9c0`
- `0x18008aabc`
- `0x180097198`
- `0x1800972a8`
- `0x180097b10`
- `0x180097cd4`
- `0x180098278`
- `0x18009912c`
- `0x180099208`
- `0x1800ae6e0`
- `0x1800aecd4`
- `0x1800b1664`
- `0x1800bb8f8`
- `0x1800bc3b4`
- `0x1800be044`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009830e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009832b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800984be`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009851f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800986af`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009830e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009832b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800984be`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009851f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800986af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098618`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098698`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009875e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098618`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098698`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009875e`

## string_xrefs

- `0x180098318`: `MockServiceDrivenActions`
- `0x180098390`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsrestrequest.cpp`
- `0x1800983e6`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsrestrequest.cpp`
- `0x18009845b`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsrestrequest.cpp`
- `0x18009848f`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsrestrequest.cpp`
- `0x18009871f`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsrestrequest.cpp`

## pseudocode

```c
__int64 __fastcall FSRestRequest::GetServiceData(
        const unsigned __int16 **this,
        unsigned __int16 **a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned __int16 **v4; // rdi
  unsigned int v8; // edx
  const wchar_t *v9; // rbx
  int FlightingRegString; // eax
  unsigned int v11; // ebx
  unsigned int v12; // edx
  unsigned __int16 *v13; // rax
  __int64 (__fastcall *v14)(const unsigned __int16 **, unsigned __int16 **); // rbx
  int v15; // eax
  int v16; // eax
  FSPropertyBag *v17; // rbx
  unsigned __int64 v18; // rdx
  unsigned __int8 v19; // cl
  int PropertyBag; // ebx
  __int64 v21; // rcx
  FlightSettingsAPITelemetryClass *v22; // rax
  const unsigned __int16 *v23; // rbx
  int v24; // edi
  const unsigned __int16 *v25; // rsi
  FSPropertyBag *v26; // rcx
  int v27; // eax
  int ClientTransactionId; // eax
  __int64 v29; // r9
  __int64 v30; // rdx
  int DataAsUnicodeString; // eax
  int v33; // [rsp+20h] [rbp-E0h]
  FSPropertyBag *v34; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h]
  __int64 v39; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v40; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h]
  __int64 v42; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v43; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h]
  __int64 v45; // [rsp+88h] [rbp-78h]
  _QWORD *v46; // [rsp+90h] [rbp-70h]
  char v47; // [rsp+98h] [rbp-68h]
  _QWORD v48[42]; // [rsp+A0h] [rbp-60h] BYREF
  char v49; // [rsp+1F0h] [rbp+F0h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v4 = a4;
  v36 = (__int64)a4;
  wil::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,33554432,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v48);
  v48[0] = &FlightSettingsAPITelemetryClass::FSRestRequestActionsList::`vftable';
  v49 = 0;
  FlightSettingsAPITelemetryClass::FSRestRequestActionsList::StartActivity(
    (FlightSettingsAPITelemetryClass::FSRestRequestActionsList *)v48,
    v8);
  *a2 = 0;
  v46 = v48;
  v47 = 1;
  if ( !FSCommonUtils::IsTestFlagSet(0x20u) )
  {
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, this + 10);
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v14 = (__int64 (__fastcall *)(const unsigned __int16 **, unsigned __int16 **))*((_QWORD *)*this + 4);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
    v41 = -1;
    v42 = -1;
    v15 = v14(this, &v40);
    v11 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
        (const char *)(unsigned int)v15,
        v33);
      goto LABEL_42;
    }
    v34 = 0;
    v16 = Microsoft::WRL::Details::MakeAndInitialize<FSPropertyBag,FSPropertyBag,>(&v34);
    v11 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
        (const char *)(unsigned int)v16,
        v33);
LABEL_41:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
LABEL_42:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      goto LABEL_44;
    }
    v37 = 0;
    v38 = 0;
    v39 = 0;
    if ( (unsigned int)_o__wcsicmp(a3, L"GetFlightSettings") )
    {
      if ( (unsigned int)_o__wcsicmp(a3, L"OnActionError") )
      {
        v11 = -2147418113;
        v29 = 2147549183LL;
        v30 = 125;
        goto LABEL_39;
      }
      v23 = this[15];
      v24 = *((_DWORD *)this + 22);
      v25 = this[12];
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
      v38 = -1;
      v39 = -1;
      FSPropertyBag::GetErrorPostData(v26, &v37, v25, v24, v23);
      v4 = (unsigned __int16 **)v36;
    }
    else
    {
      v17 = v34;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
      v38 = -1;
      v39 = -1;
      PropertyBag = FSPropertyBag::GetPropertyBag(v17, &v37);
      if ( PropertyBag < 0 && FlightSettingsAPITelemetryClass::IsEnabled(v19, v18) )
      {
        v22 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                   v21,
                                                   _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
        FlightSettingsAPITelemetryClass::FSPropertyBagFailed_(v22, PropertyBag);
      }
    }
    v27 = CGeneralHttpRequest::OpenPostRequest((CGeneralHttpRequest *)this, a3, v37, v40, 1);
    LODWORD(v36) = v27;
    if ( v27 == -2147012721 )
    {
      FlightSettingsAPITelemetryClass::HttpDecompressionFailed<long &>(&v36);
      v27 = CGeneralHttpRequest::OpenPostRequest((CGeneralHttpRequest *)this, a3, v37, v40, 0);
    }
    v11 = v27;
    if ( v27 == -2146698745 )
    {
      CUserIdentityProvider::ClearWAMTicketCache();
      v36 = -2147483646;
      FSRegUtils::SetFlightingRegDWORD(&v36, 1, L"LastHR", 2148268551LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      v11 = -2146698745;
      goto LABEL_44;
    }
    if ( v27 < 0 )
    {
      v36 = -2147483646;
      FSRegUtils::SetFlightingRegDWORD(&v36, 1, L"LastHR", (unsigned int)v27);
      if ( FlightSettingsAPICommon::IsInternetHResult(v11)
        || !FlightSettingsAPICommon::IsInternetConnected()
        || v11 == -2146698741 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
        if ( SRWLock )
          ReleaseSRWLockExclusive(SRWLock);
        v11 = -2146698741;
        goto LABEL_44;
      }
      goto LABEL_40;
    }
    if ( (unsigned int)_o__wcsicmp(a3, L"GetFlightSettings")
      || (ClientTransactionId = FSPropertyBag::GetClientTransactionId(v34, v4),
          v11 = ClientTransactionId,
          ClientTransactionId >= 0) )
    {
      v36 = -2147483646;
      FSRegUtils::SetFlightingRegDWORD(&v36, 1, L"TimeoutCount", 0);
      DataAsUnicodeString = CGeneralHttpRequest::GetDataAsUnicodeString((CGeneralHttpRequest *)this, a2);
      v11 = DataAsUnicodeString;
      if ( DataAsUnicodeString >= 0 )
      {
LABEL_40:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
        goto LABEL_41;
      }
      v29 = (unsigned int)DataAsUnicodeString;
      v30 = 173;
    }
    else
    {
      v29 = (unsigned int)ClientTransactionId;
      v30 = 167;
    }
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
      (const char *)v29,
      v33);
    goto LABEL_40;
  }
  if ( (unsigned int)_o__wcsicmp(a3, L"GetFlightSettings") )
  {
    if ( (unsigned int)_o__wcsicmp(a3, L"OnActionError") )
    {
      v11 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
        (const char *)0x8000FFFFLL,
        v33);
      goto LABEL_44;
    }
    v9 = L"MockOnActionError";
  }
  else
  {
    v9 = L"MockServiceDrivenActions";
  }
  v43 = 0;
  v44 = 0;
  v45 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v43);
  v44 = -1;
  v45 = -1;
  SRWLock = (PSRWLOCK)-2147483646LL;
  FlightingRegString = FSRegUtils::GetFlightingRegString(&SRWLock, 0, v9, &v43);
  v11 = FlightingRegString;
  if ( FlightingRegString >= 0 )
  {
    v13 = v43;
    v43 = 0;
    v45 = 0;
    v44 = 0;
    *a2 = v13;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v43);
    v11 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
      (const char *)(unsigned int)FlightingRegString,
      v33);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v43);
  }
LABEL_44:
  FlightSettingsAPITelemetryClass::FSRestRequestActionsList::Stop(
    (FlightSettingsAPITelemetryClass::FSRestRequestActionsList *)v48,
    v12);
  FlightSettingsAPITelemetryClass::FSRestRequestActionsList::~FSRestRequestActionsList((FlightSettingsAPITelemetryClass::FSRestRequestActionsList *)v48);
  return v11;
}

```

## disassembly

```asm
0x180098278  push    rbp
0x18009827a  push    rbx
0x18009827b  push    rsi
0x18009827c  push    rdi
0x18009827d  push    r12
0x18009827f  push    r13
0x180098281  push    r14
0x180098283  push    r15
0x180098285  lea     rbp, [rsp-118h]
0x18009828d  sub     rsp, 218h
0x180098294  mov     rax, cs:__security_cookie
0x18009829b  xor     rax, rsp
0x18009829e  mov     [rbp+150h+var_50], rax
0x1800982a5  mov     rdi, r9
0x1800982a8  mov     [rsp+250h+var_210], r9
0x1800982ad  mov     r15, r8
0x1800982b0  mov     r13, rdx
0x1800982b3  mov     r12, rcx
0x1800982b6  lea     rdx, aFsrestrequesta; "FSRestRequestActionsList"
0x1800982bd  lea     rcx, [rbp+150h+var_1B0]; struct wil::details::IFailureCallback *
0x1800982c1  call    ??0?$ActivityBase@VFlightSettingsAPITelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,33554432,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800982c6  lea     rax, ??_7FSRestRequestActionsList@FlightSettingsAPITelemetryClass@@6B@; const FlightSettingsAPITelemetryClass::FSRestRequestActionsList::`vftable'
0x1800982cd  mov     [rbp+150h+var_1B0], rax
0x1800982d1  xor     esi, esi
0x1800982d3  mov     [rbp+150h+var_60], sil
0x1800982da  lea     rcx, [rbp+150h+var_1B0]; this
0x1800982de  call    ?StartActivity@FSRestRequestActionsList@FlightSettingsAPITelemetryClass@@QEAAXK@Z; FlightSettingsAPITelemetryClass::FSRestRequestActionsList::StartActivity(ulong)
0x1800982e3  nop
0x1800982e4  mov     [r13+0], rsi
0x1800982e8  lea     rax, [rbp+150h+var_1B0]
0x1800982ec  mov     [rbp+150h+var_1C0], rax
0x1800982f0  mov     [rbp+150h+var_1B8], 1
0x1800982f4  lea     ecx, [rsi+20h]; unsigned int
0x1800982f7  call    ?IsTestFlagSet@FSCommonUtils@@SA_NK@Z; FSCommonUtils::IsTestFlagSet(ulong)
0x1800982fc  test    al, al
0x1800982fe  jz      loc_1800983FC
0x180098304  lea     rdx, aGetflightsetti; "GetFlightSettings"
0x18009830b  mov     rcx, r15
0x18009830e  call    cs:__imp__o__wcsicmp
0x180098314  test    eax, eax
0x180098316  jnz     short loc_180098321
0x180098318  lea     rbx, aMockservicedri; "MockServiceDrivenActions"
0x18009831f  jmp     short loc_180098340
0x180098321  lea     rdx, aOnactionerror; "OnActionError"
0x180098328  mov     rcx, r15
0x18009832b  call    cs:__imp__o__wcsicmp
0x180098331  test    eax, eax
0x180098333  jnz     loc_1800983D7
0x180098339  lea     rbx, aMockonactioner; "MockOnActionError"
0x180098340  mov     [rsp+250h+var_1D8], rsi
0x180098345  mov     [rbp+150h+var_1D0], rsi
0x180098349  mov     [rbp+150h+var_1C8], rsi
0x18009834d  lea     rcx, [rsp+250h+var_1D8]
0x180098352  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180098357  or      r14, 0FFFFFFFFFFFFFFFFh
0x18009835b  mov     [rbp+150h+var_1D0], r14
0x18009835f  mov     [rbp+150h+var_1C8], r14
0x180098363  mov     [rsp+250h+SRWLock], 0FFFFFFFF80000002h
0x18009836c  lea     r9, [rsp+250h+var_1D8]
0x180098371  mov     r8, rbx
0x180098374  xor     edx, edx
0x180098376  lea     rcx, [rsp+250h+SRWLock]
0x18009837b  call    ?GetFlightingRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAPEAG@Z; FSRegUtils::GetFlightingRegString(HKEY__ * const &,FlightingRegistryKey,ushort const *,ushort * *)
0x180098380  mov     ebx, eax
0x180098382  test    eax, eax
0x180098384  jns     short loc_1800983B0
0x180098386  mov     rcx, [rbp+158h]; this
0x18009838d  mov     r9d, eax; char *
0x180098390  lea     r8, aOnecoreBaseFli_14; "onecore\\base\\flighting\\flightsetting"...
0x180098397  lea     edx, [r14+62h]; void *
0x18009839b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800983a0  nop
0x1800983a1  lea     rcx, [rsp+250h+var_1D8]
0x1800983a6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800983ab  jmp     loc_180098765
0x1800983b0  mov     rax, [rsp+250h+var_1D8]
0x1800983b5  mov     [rsp+250h+var_1D8], rsi
0x1800983ba  mov     [rbp+150h+var_1C8], rsi
0x1800983be  mov     [rbp+150h+var_1D0], rsi
0x1800983c2  mov     [r13+0], rax
0x1800983c6  lea     rcx, [rsp+250h+var_1D8]
0x1800983cb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800983d0  mov     ebx, esi
0x1800983d2  jmp     loc_180098765
0x1800983d7  mov     rcx, [rbp+158h]; this
0x1800983de  mov     ebx, 8000FFFFh
0x1800983e3  mov     r9d, ebx; char *
0x1800983e6  lea     r8, aOnecoreBaseFli_14; "onecore\\base\\flighting\\flightsetting"...
0x1800983ed  mov     edx, 5Dh ; ']'; void *
0x1800983f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800983f7  jmp     loc_180098765
0x1800983fc  lea     rdx, [r12+50h]
0x180098401  lea     rcx, [rsp+250h+SRWLock]
0x180098406  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18009840b  nop
0x18009840c  mov     [rsp+250h+var_1F0], rsi
0x180098411  mov     [rsp+250h+var_1E8], rsi
0x180098416  mov     [rsp+250h+var_1E0], rsi
0x18009841b  mov     rax, [r12]
0x18009841f  mov     rbx, [rax+20h]
0x180098423  lea     rcx, [rsp+250h+var_1F0]
0x180098428  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009842d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180098431  mov     [rsp+250h+var_1E8], r14
0x180098436  mov     [rsp+250h+var_1E0], r14
0x18009843b  lea     rdx, [rsp+250h+var_1F0]
0x180098440  mov     rcx, r12
0x180098443  mov     rax, rbx
0x180098446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009844b  mov     ebx, eax
0x18009844d  test    eax, eax
0x18009844f  jns     short loc_180098470
0x180098451  mov     rcx, [rbp+158h]; this
0x180098458  mov     r9d, eax; char *
0x18009845b  lea     r8, aOnecoreBaseFli_14; "onecore\\base\\flighting\\flightsetting"...
0x180098462  lea     edx, [r14+6Bh]; void *
0x180098466  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009846b  jmp     loc_180098749
0x180098470  mov     [rsp+250h+var_220], rsi
0x180098475  lea     rcx, [rsp+250h+var_220]
0x18009847a  call    ??$MakeAndInitialize@VFSPropertyBag@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VFSPropertyBag@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSPropertyBag,FSPropertyBag,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<FSPropertyBag>>)
0x18009847f  mov     ebx, eax
0x180098481  test    eax, eax
0x180098483  jns     short loc_1800984A5
0x180098485  mov     rcx, [rbp+158h]; this
0x18009848c  mov     r9d, eax; char *
0x18009848f  lea     r8, aOnecoreBaseFli_14; "onecore\\base\\flighting\\flightsetting"...
0x180098496  mov     edx, 6Dh ; 'm'; void *
0x18009849b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800984a0  jmp     loc_18009873E
0x1800984a5  mov     [rsp+250h+var_208], rsi
0x1800984aa  mov     [rsp+250h+var_200], rsi
0x1800984af  mov     [rsp+250h+var_1F8], rsi
0x1800984b4  lea     rdx, aGetflightsetti; "GetFlightSettings"
0x1800984bb  mov     rcx, r15
0x1800984be  call    cs:__imp__o__wcsicmp
0x1800984c4  test    eax, eax
0x1800984c6  jnz     short loc_180098515
0x1800984c8  mov     rbx, [rsp+250h+var_220]
0x1800984cd  lea     rcx, [rsp+250h+var_208]
0x1800984d2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800984d7  mov     [rsp+250h+var_200], r14
0x1800984dc  mov     [rsp+250h+var_1F8], r14
0x1800984e1  lea     rdx, [rsp+250h+var_208]; unsigned __int16 **
0x1800984e6  mov     rcx, rbx; this
0x1800984e9  call    ?GetPropertyBag@FSPropertyBag@@QEAAJPEAPEAG@Z; FSPropertyBag::GetPropertyBag(ushort * *)
0x1800984ee  mov     ebx, eax
0x1800984f0  test    eax, eax
0x1800984f2  jns     short loc_18009856C
0x1800984f4  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800984f9  test    al, al
0x1800984fb  jz      short loc_18009856C
0x1800984fd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x180098504  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x180098509  mov     edx, ebx; int
0x18009850b  mov     rcx, rax; this
0x18009850e  call    ?FSPropertyBagFailed_@FlightSettingsAPITelemetryClass@@QEAAXJ@Z; FlightSettingsAPITelemetryClass::FSPropertyBagFailed_(long)
0x180098513  jmp     short loc_18009856C
0x180098515  lea     rdx, aOnactionerror; "OnActionError"
0x18009851c  mov     rcx, r15
0x18009851f  call    cs:__imp__o__wcsicmp
0x180098525  test    eax, eax
0x180098527  jnz     loc_180098712
0x18009852d  mov     rbx, [r12+78h]
0x180098532  mov     edi, [r12+58h]
0x180098537  mov     rsi, [r12+60h]
0x18009853c  lea     rcx, [rsp+250h+var_208]
0x180098541  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180098546  mov     [rsp+250h+var_200], r14
0x18009854b  mov     [rsp+250h+var_1F8], r14
0x180098550  mov     qword ptr [rsp+250h+var_230], rbx; unsigned __int16 *
0x180098555  mov     r9d, edi; int
0x180098558  mov     r8, rsi; unsigned __int16 *
0x18009855b  lea     rdx, [rsp+250h+var_208]; unsigned __int16 **
0x180098560  call    ?GetErrorPostData@FSPropertyBag@@QEAAJPEAPEAGPEBGJ1@Z; FSPropertyBag::GetErrorPostData(ushort * *,ushort const *,long,ushort const *)
0x180098565  mov     rdi, [rsp+250h+var_210]
0x18009856a  xor     esi, esi
0x18009856c  mov     byte ptr [rsp+250h+var_230], 1; bool
0x180098571  mov     r9, [rsp+250h+var_1F0]; unsigned __int16 *
0x180098576  mov     r8, [rsp+250h+var_208]; unsigned __int16 *
0x18009857b  mov     rdx, r15; unsigned __int16 *
0x18009857e  mov     rcx, r12; this
0x180098581  call    ?OpenPostRequest@CGeneralHttpRequest@@IEAAJPEBG00_N@Z; CGeneralHttpRequest::OpenPostRequest(ushort const *,ushort const *,ushort const *,bool)
0x180098586  mov     dword ptr [rsp+250h+var_210], eax
0x18009858a  cmp     eax, 80072F8Fh
0x18009858f  jnz     short loc_1800985B5
0x180098591  lea     rcx, [rsp+250h+var_210]
0x180098596  call    ??$HttpDecompressionFailed@AEAJ@FlightSettingsAPITelemetryClass@@SAXAEAJ@Z; FlightSettingsAPITelemetryClass::HttpDecompressionFailed<long &>(long &)
0x18009859b  mov     byte ptr [rsp+250h+var_230], sil; bool
0x1800985a0  mov     r9, [rsp+250h+var_1F0]; unsigned __int16 *
0x1800985a5  mov     r8, [rsp+250h+var_208]; unsigned __int16 *
0x1800985aa  mov     rdx, r15; unsigned __int16 *
0x1800985ad  mov     rcx, r12; this
0x1800985b0  call    ?OpenPostRequest@CGeneralHttpRequest@@IEAAJPEBG00_N@Z; CGeneralHttpRequest::OpenPostRequest(ushort const *,ushort const *,ushort const *,bool)
0x1800985b5  mov     ebx, eax
0x1800985b7  mov     r14d, 800BFA07h
0x1800985bd  cmp     eax, r14d
0x1800985c0  jnz     short loc_180098626
0x1800985c2  call    ?ClearWAMTicketCache@CUserIdentityProvider@@SAJXZ; CUserIdentityProvider::ClearWAMTicketCache(void)
0x1800985c7  mov     [rsp+250h+var_210], 0FFFFFFFF80000002h
0x1800985d0  mov     r9d, 800BFA07h
0x1800985d6  lea     r8, aLasthr; "LastHR"
0x1800985dd  mov     edx, 1
0x1800985e2  lea     rcx, [rsp+250h+var_210]
0x1800985e7  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x1800985ec  nop
0x1800985ed  lea     rcx, [rsp+250h+var_208]
0x1800985f2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800985f7  nop
0x1800985f8  lea     rcx, [rsp+250h+var_220]
0x1800985fd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180098602  nop
0x180098603  lea     rcx, [rsp+250h+var_1F0]
0x180098608  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009860d  nop
0x18009860e  mov     rcx, [rsp+250h+SRWLock]; SRWLock
0x180098613  test    rcx, rcx
0x180098616  jz      short loc_18009861E
0x180098618  call    cs:__imp_ReleaseSRWLockExclusive
0x18009861e  mov     ebx, r14d
0x180098621  jmp     loc_180098765
0x180098626  test    ebx, ebx
0x180098628  jns     short loc_1800986A5
0x18009862a  mov     [rsp+250h+var_210], 0FFFFFFFF80000002h
0x180098633  mov     r9d, eax
0x180098636  lea     r8, aLasthr; "LastHR"
0x18009863d  mov     edx, 1
0x180098642  lea     rcx, [rsp+250h+var_210]
0x180098647  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x18009864c  mov     ecx, ebx; int
0x18009864e  call    ?IsInternetHResult@FlightSettingsAPICommon@@SA_NJ@Z; FlightSettingsAPICommon::IsInternetHResult(long)
0x180098653  mov     edi, 800BFA0Bh
0x180098658  test    al, al
0x18009865a  jnz     short loc_18009866D
0x18009865c  call    ?IsInternetConnected@FlightSettingsAPICommon@@SA_NXZ; FlightSettingsAPICommon::IsInternetConnected(void)
0x180098661  test    al, al
0x180098663  jz      short loc_18009866D
0x180098665  cmp     ebx, edi
0x180098667  jnz     loc_180098733
0x18009866d  lea     rcx, [rsp+250h+var_208]
0x180098672  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180098677  nop
0x180098678  lea     rcx, [rsp+250h+var_220]
0x18009867d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180098682  nop
0x180098683  lea     rcx, [rsp+250h+var_1F0]
0x180098688  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009868d  nop
0x18009868e  mov     rcx, [rsp+250h+SRWLock]; SRWLock
0x180098693  test    rcx, rcx
0x180098696  jz      short loc_18009869E
0x180098698  call    cs:__imp_ReleaseSRWLockExclusive
0x18009869e  mov     ebx, edi
0x1800986a0  jmp     loc_180098765
0x1800986a5  lea     rdx, aGetflightsetti; "GetFlightSettings"
0x1800986ac  mov     rcx, r15
0x1800986af  call    cs:__imp__o__wcsicmp
0x1800986b5  test    eax, eax
0x1800986b7  jnz     short loc_1800986D6
0x1800986b9  mov     rdx, rdi; unsigned __int16 **
0x1800986bc  mov     rcx, [rsp+250h+var_220]; this
0x1800986c1  call    ?GetClientTransactionId@FSPropertyBag@@QEAAJPEAPEAG@Z; FSPropertyBag::GetClientTransactionId(ushort * *)
0x1800986c6  mov     ebx, eax
0x1800986c8  test    eax, eax
0x1800986ca  jns     short loc_1800986D6
0x1800986cc  mov     r9d, eax
0x1800986cf  mov     edx, 0A7h
0x1800986d4  jmp     short loc_18009871F
0x1800986d6  mov     [rsp+250h+var_210], 0FFFFFFFF80000002h
0x1800986df  xor     r9d, r9d
0x1800986e2  lea     r8, aTimeoutcount; "TimeoutCount"
0x1800986e9  lea     edx, [r9+1]
0x1800986ed  lea     rcx, [rsp+250h+var_210]
0x1800986f2  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x1800986f7  mov     rdx, r13; unsigned __int16 **
0x1800986fa  mov     rcx, r12; this
0x1800986fd  call    ?GetDataAsUnicodeString@CGeneralHttpRequest@@IEAAJPEAPEAG@Z; CGeneralHttpRequest::GetDataAsUnicodeString(ushort * *)
0x180098702  mov     ebx, eax
0x180098704  test    eax, eax
0x180098706  jns     short loc_180098733
0x180098708  mov     r9d, eax
0x18009870b  mov     edx, 0ADh
0x180098710  jmp     short loc_18009871F
0x180098712  mov     ebx, 8000FFFFh
0x180098717  mov     r9d, ebx; char *
0x18009871a  mov     edx, 7Dh ; '}'; void *
0x18009871f  lea     r8, aOnecoreBaseFli_14; "onecore\\base\\flighting\\flightsetting"...
0x180098726  mov     rcx, [rbp+158h]; this
0x18009872d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098732  nop
0x180098733  lea     rcx, [rsp+250h+var_208]
0x180098738  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009873d  nop
0x18009873e  lea     rcx, [rsp+250h+var_220]
0x180098743  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180098748  nop
0x180098749  lea     rcx, [rsp+250h+var_1F0]
0x18009874e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180098753  nop
0x180098754  mov     rcx, [rsp+250h+SRWLock]; SRWLock
  ... truncated ...
```
