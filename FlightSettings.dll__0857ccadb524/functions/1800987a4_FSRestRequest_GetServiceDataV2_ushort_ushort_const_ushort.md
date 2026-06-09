# FSRestRequest::GetServiceDataV2(ushort * *,ushort const *,ushort * *)

- ea: `0x1800987a4`
- end: `0x180098d11`
- name: `?GetServiceDataV2@FSRestRequest@@AEAAJPEAPEAGPEBG0@Z`
- size: `1389`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, unsigned __int16 **, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180097f64`
- `0x180098148`

## callees

- `0x18000b19c`
- `0x18000cc8c`
- `0x18000f9b8`
- `0x1800175b4`
- `0x18001a1d8`
- `0x18001c6f4`
- `0x180085a24`
- `0x180086644`
- `0x1800880cc`
- `0x18008a9c0`
- `0x18008aabc`
- `0x1800972a8`
- `0x1800979ec`
- `0x180097a94`
- `0x1800987a4`
- `0x180099850`
- `0x18009b158`
- `0x1800ae6e0`
- `0x1800aecd4`
- `0x1800bb8f8`
- `0x1800bc3b4`
- `0x1800be044`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800987f6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180098813`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180098993`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800989e9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180098be5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800987f6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180098813`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180098993`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800989e9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180098be5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098b1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098bce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098c8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098ce4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098b1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098bce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098c8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098ce4`

## string_xrefs

- `0x180098800`: `MockServiceDrivenActions`
- `0x180098870`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsrestrequest.cpp`
- `0x1800988b3`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsrestrequest.cpp`
- `0x180098937`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsrestrequest.cpp`
- `0x180098967`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsrestrequest.cpp`
- `0x180098999`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsrestrequest.cpp`

## pseudocode

```c
__int64 __fastcall FSRestRequest::GetServiceDataV2(
        const unsigned __int16 **this,
        unsigned __int16 **a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned __int16 **v4; // rsi
  unsigned __int16 **v6; // rdi
  const wchar_t *v8; // rbx
  int FlightingRegString; // eax
  unsigned int v10; // ebx
  unsigned __int16 *v11; // rax
  __int64 (__fastcall *v12)(const unsigned __int16 **, unsigned __int16 **); // rbx
  int v13; // eax
  int v14; // eax
  FSPropertyBag *v15; // rbx
  int PropertyBag; // eax
  const unsigned __int16 *v17; // rbx
  int v18; // edi
  const unsigned __int16 *v19; // rsi
  FSPropertyBag *v20; // rcx
  int ErrorPostData; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdx
  int ClientTransactionId; // eax
  int v26; // eax
  unsigned __int64 v27; // r9
  int v29; // [rsp+28h] [rbp-89h]
  int v30; // [rsp+28h] [rbp-89h]
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-79h] BYREF
  FSPropertyBag *v32; // [rsp+40h] [rbp-71h] BYREF
  unsigned __int16 *v33; // [rsp+48h] [rbp-69h] BYREF
  __int64 v34; // [rsp+50h] [rbp-61h]
  __int64 v35; // [rsp+58h] [rbp-59h]
  unsigned __int16 *v36; // [rsp+60h] [rbp-51h] BYREF
  __int64 v37; // [rsp+68h] [rbp-49h]
  __int64 v38; // [rsp+70h] [rbp-41h]
  unsigned __int16 *v39; // [rsp+78h] [rbp-39h] BYREF
  __int64 v40; // [rsp+80h] [rbp-31h]
  __int64 v41; // [rsp+88h] [rbp-29h]
  _BYTE v42[56]; // [rsp+98h] [rbp-19h] BYREF
  __int64 v43; // [rsp+D0h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+5Fh]
  __int64 v45; // [rsp+120h] [rbp+6Fh] BYREF
  unsigned __int16 **v46; // [rsp+130h] [rbp+7Fh]

  v46 = a4;
  v45 = (__int64)a2;
  v4 = a4;
  v6 = a2;
  *a2 = 0;
  if ( FSCommonUtils::IsTestFlagSet(0x20u) )
  {
    if ( !(unsigned int)_o__wcsicmp(a3, L"GetFlightSettings") )
    {
      v8 = L"MockServiceDrivenActions";
LABEL_6:
      v39 = 0;
      v40 = 0;
      v41 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v39);
      v40 = -1;
      v41 = -1;
      v45 = -2147483646;
      FlightingRegString = FSRegUtils::GetFlightingRegString(&v45, 0, v8, &v39);
      v10 = FlightingRegString;
      if ( FlightingRegString >= 0 )
      {
        v11 = v39;
        v39 = 0;
        v41 = 0;
        v40 = 0;
        *v6 = v11;
        v10 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC8,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
          (const char *)(unsigned int)FlightingRegString,
          v29);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v39);
      return v10;
    }
    if ( !(unsigned int)_o__wcsicmp(a3, L"OnActionError") )
    {
      v8 = L"MockOnActionError";
      goto LABEL_6;
    }
    v10 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
      (const char *)0x8000FFFFLL,
      v29);
    return v10;
  }
  SRWLock = 0;
  tip2::tip_test<tip2::details::merged_data<Flighting::_tip_FlightingMSAv2GetServiceDataTipTest,Flighting::_tip_FlightingMSAv2GetServiceDataTipTest>>::start_and_watch_errors(
    &SRWLock,
    v42);
  wil::com_ptr_t<tip2::details::merged_data<Flighting::_tip_FlightingMSAv2GetServiceDataTipTest,Flighting::_tip_FlightingMSAv2GetServiceDataTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<Flighting::_tip_FlightingMSAv2GetServiceDataTipTest,Flighting::_tip_FlightingMSAv2GetServiceDataTipTest>,wil::err_returncode_policy>(&SRWLock);
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, this + 10);
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v12 = (__int64 (__fastcall *)(const unsigned __int16 **, unsigned __int16 **))*((_QWORD *)*this + 4);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
  v37 = -1;
  v38 = -1;
  v13 = v12(this, &v36);
  v10 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
      (const char *)(unsigned int)v13,
      v29);
    goto LABEL_55;
  }
  v32 = 0;
  v14 = Microsoft::WRL::Details::MakeAndInitialize<FSPropertyBag,FSPropertyBag,>(&v32);
  v10 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
      (const char *)(unsigned int)v14,
      v29);
LABEL_54:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
LABEL_55:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
LABEL_57:
    tip2::test_watcher<tip2::details::merged_data<Flighting::_tip_FlightingMSAv2GetServiceDataTipTest,Flighting::_tip_FlightingMSAv2GetServiceDataTipTest>>::~test_watcher<tip2::details::merged_data<Flighting::_tip_FlightingMSAv2GetServiceDataTipTest,Flighting::_tip_FlightingMSAv2GetServiceDataTipTest>>(v42);
    return v10;
  }
  v33 = 0;
  v34 = 0;
  v35 = 0;
  if ( (unsigned int)_o__wcsicmp(a3, L"GetFlightSettings") )
  {
    if ( (unsigned int)_o__wcsicmp(a3, L"OnActionError") )
    {
      v10 = -2147418113;
      v24 = 227;
LABEL_52:
      v27 = v10;
      goto LABEL_53;
    }
    v17 = this[15];
    v18 = *((_DWORD *)this + 22);
    v19 = this[12];
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
    v34 = -1;
    v35 = -1;
    ErrorPostData = FSPropertyBag::GetErrorPostData(v20, &v33, v19, v18, v17);
    if ( ErrorPostData < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xDF,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
        (const char *)(unsigned int)ErrorPostData,
        v30);
    v4 = v46;
    v6 = (unsigned __int16 **)v45;
  }
  else
  {
    v15 = v32;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
    v34 = -1;
    v35 = -1;
    PropertyBag = FSPropertyBag::GetPropertyBag(v15, &v33);
    if ( PropertyBag < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xDA,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
        (const char *)(unsigned int)PropertyBag,
        v29);
  }
  v10 = CGeneralHttpRequest::OpenPostRequest((CGeneralHttpRequest *)this, a3, v33, v36, 1);
  if ( v10 == -2147012721 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
      (const char *)0x80072F8FLL,
      v29);
    v10 = CGeneralHttpRequest::OpenPostRequest((CGeneralHttpRequest *)this, a3, v33, v36, 0);
  }
  if ( v10 == -2146698745 )
  {
    v45 = -2147483646;
    v22 = FSRegUtils::SetFlightingRegDWORD(&v45, 1, L"LastHR", 2148268551LL);
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF6,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
        (const char *)(unsigned int)v22,
        v29);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
      (const char *)0x800BFA07LL,
      v29);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v10 = -2146698745;
    goto LABEL_57;
  }
  if ( (v10 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
      (const char *)v10,
      v29);
    v45 = -2147483646;
    v23 = FSRegUtils::SetFlightingRegDWORD(&v45, 1, L"LastHR", v10);
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x101,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
        (const char *)(unsigned int)v23,
        v29);
    if ( FlightSettingsAPICommon::IsInternetHResult(v10)
      || !FlightSettingsAPICommon::IsInternetConnected()
      || v10 == -2146698741 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      v10 = -2146698741;
      goto LABEL_57;
    }
    v24 = 264;
    goto LABEL_52;
  }
  if ( !(unsigned int)_o__wcsicmp(a3, L"GetFlightSettings") )
  {
    ClientTransactionId = FSPropertyBag::GetClientTransactionId(v32, v4);
    v10 = ClientTransactionId;
    if ( ClientTransactionId < 0 )
    {
      v24 = 271;
LABEL_47:
      v27 = (unsigned int)ClientTransactionId;
LABEL_53:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
        (const char *)v27,
        v29);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
      goto LABEL_54;
    }
  }
  v45 = -2147483646;
  v26 = FSRegUtils::SetFlightingRegDWORD(&v45, 1, L"TimeoutCount", 0);
  if ( v26 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x113,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrestrequest.cpp",
      (const char *)(unsigned int)v26,
      v29);
  ClientTransactionId = CGeneralHttpRequest::GetDataAsUnicodeString((CGeneralHttpRequest *)this, v6);
  v10 = ClientTransactionId;
  if ( ClientTransactionId < 0 )
  {
    v24 = 277;
    goto LABEL_47;
  }
  tip2::details::shared_data<0,0,0>::complete_without_lock(v43 + 8);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  tip2::test_watcher<tip2::details::merged_data<Flighting::_tip_FlightingMSAv2GetServiceDataTipTest,Flighting::_tip_FlightingMSAv2GetServiceDataTipTest>>::~test_watcher<tip2::details::merged_data<Flighting::_tip_FlightingMSAv2GetServiceDataTipTest,Flighting::_tip_FlightingMSAv2GetServiceDataTipTest>>(v42);
  return 0;
}

```

## disassembly

```asm
0x1800987a4  mov     rax, rsp
0x1800987a7  mov     [rax+8], rbx
0x1800987ab  mov     [rax+20h], r9
0x1800987af  mov     [rax+10h], rdx
0x1800987b3  push    rbp
0x1800987b4  push    rsi
0x1800987b5  push    rdi
0x1800987b6  push    r12
0x1800987b8  push    r13
0x1800987ba  push    r14
0x1800987bc  push    r15
0x1800987be  lea     rbp, [rax-5Fh]
0x1800987c2  sub     rsp, 0D0h
0x1800987c9  mov     rsi, r9
0x1800987cc  mov     r15, r8
0x1800987cf  mov     rdi, rdx
0x1800987d2  mov     r13, rcx
0x1800987d5  xor     r14d, r14d
0x1800987d8  mov     [rdx], r14
0x1800987db  lea     ecx, [r14+20h]; unsigned int
0x1800987df  call    ?IsTestFlagSet@FSCommonUtils@@SA_NK@Z; FSCommonUtils::IsTestFlagSet(ulong)
0x1800987e4  test    al, al
0x1800987e6  jz      loc_1800988C9
0x1800987ec  lea     rdx, aGetflightsetti; "GetFlightSettings"
0x1800987f3  mov     rcx, r15
0x1800987f6  call    cs:__imp__o__wcsicmp
0x1800987fc  test    eax, eax
0x1800987fe  jnz     short loc_180098809
0x180098800  lea     rbx, aMockservicedri; "MockServiceDrivenActions"
0x180098807  jmp     short loc_180098828
0x180098809  lea     rdx, aOnactionerror; "OnActionError"
0x180098810  mov     rcx, r15
0x180098813  call    cs:__imp__o__wcsicmp
0x180098819  test    eax, eax
0x18009881b  jnz     loc_1800988A7
0x180098821  lea     rbx, aMockonactioner; "MockOnActionError"
0x180098828  mov     [rbp+57h+var_90], r14
0x18009882c  mov     [rbp+57h+var_88], r14
0x180098830  mov     [rbp+57h+var_80], r14
0x180098834  lea     rcx, [rbp+57h+var_90]
0x180098838  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009883d  or      r12, 0FFFFFFFFFFFFFFFFh
0x180098841  mov     [rbp+57h+var_88], r12
0x180098845  mov     [rbp+57h+var_80], r12
0x180098849  mov     [rbp+57h+arg_8], 0FFFFFFFF80000002h
0x180098851  lea     r9, [rbp+57h+var_90]
0x180098855  mov     r8, rbx
0x180098858  xor     edx, edx
0x18009885a  lea     rcx, [rbp+57h+arg_8]
0x18009885e  call    ?GetFlightingRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAPEAG@Z; FSRegUtils::GetFlightingRegString(HKEY__ * const &,FlightingRegistryKey,ushort const *,ushort * *)
0x180098863  mov     ebx, eax
0x180098865  test    eax, eax
0x180098867  jns     short loc_180098883
0x180098869  mov     rcx, [rbp+5Fh]; this
0x18009886d  mov     r9d, eax; char *
0x180098870  lea     r8, aOnecoreBaseFli_14; "onecore\\base\\flighting\\flightsetting"...
0x180098877  mov     edx, 0C8h; void *
0x18009887c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098881  jmp     short loc_180098899
0x180098883  mov     rax, [rbp+57h+var_90]
0x180098887  mov     [rbp+57h+var_90], r14
0x18009888b  mov     [rbp+57h+var_80], r14
0x18009888f  mov     [rbp+57h+var_88], r14
0x180098893  mov     [rdi], rax
0x180098896  mov     ebx, r14d
0x180098899  lea     rcx, [rbp+57h+var_90]
0x18009889d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800988a2  jmp     loc_180098CF4
0x1800988a7  mov     rcx, [rbp+5Fh]; this
0x1800988ab  mov     ebx, 8000FFFFh
0x1800988b0  mov     r9d, ebx; char *
0x1800988b3  lea     r8, aOnecoreBaseFli_14; "onecore\\base\\flighting\\flightsetting"...
0x1800988ba  mov     edx, 0C4h; void *
0x1800988bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800988c4  jmp     loc_180098CF4
0x1800988c9  mov     [rbp+57h+SRWLock], r14
0x1800988cd  lea     rdx, [rbp+57h+var_70]
0x1800988d1  lea     rcx, [rbp+57h+SRWLock]
0x1800988d5  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_FlightingMSAv2GetServiceDataTipTest@Flighting@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_FlightingMSAv2GetServiceDataTipTest@Flighting@@U12@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<Flighting::_tip_FlightingMSAv2GetServiceDataTipTest,Flighting::_tip_FlightingMSAv2GetServiceDataTipTest>>::start_and_watch_errors(void)
0x1800988da  lea     rcx, [rbp+57h+SRWLock]
0x1800988de  call    ??1?$com_ptr_t@V?$merged_data@U_tip_FlightingMSAv2GetServiceDataTipTest@Flighting@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<Flighting::_tip_FlightingMSAv2GetServiceDataTipTest,Flighting::_tip_FlightingMSAv2GetServiceDataTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<Flighting::_tip_FlightingMSAv2GetServiceDataTipTest,Flighting::_tip_FlightingMSAv2GetServiceDataTipTest>,wil::err_returncode_policy>(void)
0x1800988e3  nop
0x1800988e4  lea     rdx, [r13+50h]
0x1800988e8  lea     rcx, [rbp+57h+SRWLock]
0x1800988ec  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800988f1  nop
0x1800988f2  mov     [rbp+57h+var_A8], r14
0x1800988f6  mov     [rbp+57h+var_A0], r14
0x1800988fa  mov     [rbp+57h+var_98], r14
0x1800988fe  mov     rax, [r13+0]
0x180098902  mov     rbx, [rax+20h]
0x180098906  lea     rcx, [rbp+57h+var_A8]
0x18009890a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009890f  or      r12, 0FFFFFFFFFFFFFFFFh
0x180098913  mov     [rbp+57h+var_A0], r12
0x180098917  mov     [rbp+57h+var_98], r12
0x18009891b  lea     rdx, [rbp+57h+var_A8]
0x18009891f  mov     rcx, r13
0x180098922  mov     rax, rbx
0x180098925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009892a  mov     ebx, eax
0x18009892c  test    eax, eax
0x18009892e  jns     short loc_18009894D
0x180098930  mov     rcx, [rbp+5Fh]; this
0x180098934  mov     r9d, eax; char *
0x180098937  lea     r8, aOnecoreBaseFli_14; "onecore\\base\\flighting\\flightsetting"...
0x18009893e  mov     edx, 0D3h; void *
0x180098943  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098948  jmp     loc_180098CD1
0x18009894d  mov     [rbp+57h+var_C8], r14
0x180098951  lea     rcx, [rbp+57h+var_C8]
0x180098955  call    ??$MakeAndInitialize@VFSPropertyBag@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VFSPropertyBag@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSPropertyBag,FSPropertyBag,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<FSPropertyBag>>)
0x18009895a  mov     ebx, eax
0x18009895c  test    eax, eax
0x18009895e  jns     short loc_18009897D
0x180098960  mov     rcx, [rbp+5Fh]; this
0x180098964  mov     r9d, eax; char *
0x180098967  lea     r8, aOnecoreBaseFli_14; "onecore\\base\\flighting\\flightsetting"...
0x18009896e  mov     edx, 0D6h; void *
0x180098973  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098978  jmp     loc_180098CC7
0x18009897d  mov     [rbp+57h+var_C0], r14
0x180098981  mov     [rbp+57h+var_B8], r14
0x180098985  mov     [rbp+57h+var_B0], r14
0x180098989  lea     rdx, aGetflightsetti; "GetFlightSettings"
0x180098990  mov     rcx, r15
0x180098993  call    cs:__imp__o__wcsicmp
0x180098999  lea     r14, aOnecoreBaseFli_14; "onecore\\base\\flighting\\flightsetting"...
0x1800989a0  test    eax, eax
0x1800989a2  jnz     short loc_1800989DF
0x1800989a4  mov     rbx, [rbp+57h+var_C8]
0x1800989a8  lea     rcx, [rbp+57h+var_C0]
0x1800989ac  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800989b1  mov     [rbp+57h+var_B8], r12
0x1800989b5  mov     [rbp+57h+var_B0], r12
0x1800989b9  lea     rdx, [rbp+57h+var_C0]; unsigned __int16 **
0x1800989bd  mov     rcx, rbx; this
0x1800989c0  call    ?GetPropertyBag@FSPropertyBag@@QEAAJPEAPEAG@Z; FSPropertyBag::GetPropertyBag(ushort * *)
0x1800989c5  mov     rcx, [rbp+5Fh]; this
0x1800989c9  test    eax, eax
0x1800989cb  jns     short loc_180098A48
0x1800989cd  mov     r9d, eax; char *
0x1800989d0  mov     r8, r14; unsigned int
0x1800989d3  mov     edx, 0DAh; void *
0x1800989d8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800989dd  jmp     short loc_180098A48
0x1800989df  lea     rdx, aOnactionerror; "OnActionError"
0x1800989e6  mov     rcx, r15
0x1800989e9  call    cs:__imp__o__wcsicmp
0x1800989ef  test    eax, eax
0x1800989f1  jnz     loc_180098CA3
0x1800989f7  mov     rbx, [r13+78h]
0x1800989fb  mov     edi, [r13+58h]
0x1800989ff  mov     rsi, [r13+60h]
0x180098a03  lea     rcx, [rbp+57h+var_C0]
0x180098a07  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180098a0c  mov     [rbp+57h+var_B8], r12
0x180098a10  mov     [rbp+57h+var_B0], r12
0x180098a14  mov     [rsp+20h], rbx; int
0x180098a19  mov     r9d, edi; int
0x180098a1c  mov     r8, rsi; unsigned __int16 *
0x180098a1f  lea     rdx, [rbp+57h+var_C0]; unsigned __int16 **
0x180098a23  call    ?GetErrorPostData@FSPropertyBag@@QEAAJPEAPEAGPEBGJ1@Z; FSPropertyBag::GetErrorPostData(ushort * *,ushort const *,long,ushort const *)
0x180098a28  mov     rcx, [rbp+5Fh]; this
0x180098a2c  test    eax, eax
0x180098a2e  jns     short loc_180098A40
0x180098a30  mov     r9d, eax; char *
0x180098a33  mov     r8, r14; unsigned int
0x180098a36  mov     edx, 0DFh; void *
0x180098a3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180098a40  mov     rsi, [rbp+57h+arg_18]
0x180098a44  mov     rdi, [rbp+57h+arg_8]
0x180098a48  mov     byte ptr [rsp+20h], 1; int
0x180098a4d  mov     r9, [rbp+57h+var_A8]; unsigned __int16 *
0x180098a51  mov     r8, [rbp+57h+var_C0]; unsigned __int16 *
0x180098a55  mov     rdx, r15; unsigned __int16 *
0x180098a58  mov     rcx, r13; this
0x180098a5b  call    ?OpenPostRequest@CGeneralHttpRequest@@IEAAJPEBG00_N@Z; CGeneralHttpRequest::OpenPostRequest(ushort const *,ushort const *,ushort const *,bool)
0x180098a60  mov     ebx, eax
0x180098a62  mov     r9d, 80072F8Fh; char *
0x180098a68  cmp     eax, r9d
0x180098a6b  jnz     short loc_180098A98
0x180098a6d  mov     rcx, [rbp+5Fh]; this
0x180098a71  mov     r8, r14; unsigned int
0x180098a74  mov     edx, 0EAh; void *
0x180098a79  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180098a7e  mov     byte ptr [rsp+20h], 0; int
0x180098a83  mov     r9, [rbp+57h+var_A8]; unsigned __int16 *
0x180098a87  mov     r8, [rbp+57h+var_C0]; unsigned __int16 *
0x180098a8b  mov     rdx, r15; unsigned __int16 *
0x180098a8e  mov     rcx, r13; this
0x180098a91  call    ?OpenPostRequest@CGeneralHttpRequest@@IEAAJPEBG00_N@Z; CGeneralHttpRequest::OpenPostRequest(ushort const *,ushort const *,ushort const *,bool)
0x180098a96  mov     ebx, eax
0x180098a98  mov     r12d, 800BFA07h
0x180098a9e  cmp     ebx, r12d
0x180098aa1  jnz     loc_180098B2C
0x180098aa7  mov     [rbp+57h+arg_8], 0FFFFFFFF80000002h
0x180098aaf  mov     r9d, 800BFA07h
0x180098ab5  lea     r8, aLasthr; "LastHR"
0x180098abc  mov     edx, 1
0x180098ac1  lea     rcx, [rbp+57h+arg_8]
0x180098ac5  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x180098aca  mov     rcx, [rbp+5Fh]; this
0x180098ace  test    eax, eax
0x180098ad0  jns     short loc_180098AE2
0x180098ad2  mov     r9d, eax; char *
0x180098ad5  mov     r8, r14; unsigned int
0x180098ad8  mov     edx, 0F6h; void *
0x180098add  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180098ae2  mov     rcx, [rbp+5Fh]; this
0x180098ae6  mov     r9d, r12d; char *
0x180098ae9  mov     r8, r14; unsigned int
0x180098aec  mov     edx, 0F9h; void *
0x180098af1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098af6  nop
0x180098af7  lea     rcx, [rbp+57h+var_C0]
0x180098afb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180098b00  nop
0x180098b01  lea     rcx, [rbp+57h+var_C8]
0x180098b05  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180098b0a  nop
0x180098b0b  lea     rcx, [rbp+57h+var_A8]
0x180098b0f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180098b14  nop
0x180098b15  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180098b19  test    rcx, rcx
0x180098b1c  jz      short loc_180098B24
0x180098b1e  call    cs:__imp_ReleaseSRWLockExclusive
0x180098b24  mov     ebx, r12d
0x180098b27  jmp     loc_180098CEB
0x180098b2c  mov     rcx, [rbp+5Fh]; this
0x180098b30  test    ebx, ebx
0x180098b32  jns     loc_180098BDB
0x180098b38  mov     r9d, ebx; char *
0x180098b3b  mov     r8, r14; unsigned int
0x180098b3e  mov     edx, 0FBh; void *
0x180098b43  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180098b48  mov     [rbp+57h+arg_8], 0FFFFFFFF80000002h
0x180098b50  mov     r9d, ebx
0x180098b53  lea     r8, aLasthr; "LastHR"
0x180098b5a  mov     edx, 1
0x180098b5f  lea     rcx, [rbp+57h+arg_8]
0x180098b63  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x180098b68  mov     rcx, [rbp+5Fh]; this
0x180098b6c  test    eax, eax
0x180098b6e  jns     short loc_180098B80
0x180098b70  mov     r9d, eax; char *
0x180098b73  mov     r8, r14; unsigned int
0x180098b76  mov     edx, 101h; void *
0x180098b7b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180098b80  mov     ecx, ebx; int
0x180098b82  call    ?IsInternetHResult@FlightSettingsAPICommon@@SA_NJ@Z; FlightSettingsAPICommon::IsInternetHResult(long)
0x180098b87  mov     edi, 800BFA0Bh
0x180098b8c  test    al, al
0x180098b8e  jnz     short loc_180098BA7
0x180098b90  call    ?IsInternetConnected@FlightSettingsAPICommon@@SA_NXZ; FlightSettingsAPICommon::IsInternetConnected(void)
0x180098b95  test    al, al
0x180098b97  jz      short loc_180098BA7
0x180098b99  cmp     ebx, edi
0x180098b9b  jz      short loc_180098BA7
0x180098b9d  mov     edx, 108h
0x180098ba2  jmp     loc_180098CAD
0x180098ba7  lea     rcx, [rbp+57h+var_C0]
0x180098bab  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180098bb0  nop
0x180098bb1  lea     rcx, [rbp+57h+var_C8]
0x180098bb5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180098bba  nop
0x180098bbb  lea     rcx, [rbp+57h+var_A8]
0x180098bbf  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180098bc4  nop
0x180098bc5  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180098bc9  test    rcx, rcx
0x180098bcc  jz      short loc_180098BD4
0x180098bce  call    cs:__imp_ReleaseSRWLockExclusive
0x180098bd4  mov     ebx, edi
0x180098bd6  jmp     loc_180098CEB
0x180098bdb  lea     rdx, aGetflightsetti; "GetFlightSettings"
0x180098be2  mov     rcx, r15
0x180098be5  call    cs:__imp__o__wcsicmp
0x180098beb  test    eax, eax
0x180098bed  jnz     short loc_180098C08
0x180098bef  mov     rdx, rsi; unsigned __int16 **
0x180098bf2  mov     rcx, [rbp+57h+var_C8]; this
0x180098bf6  call    ?GetClientTransactionId@FSPropertyBag@@QEAAJPEAPEAG@Z; FSPropertyBag::GetClientTransactionId(ushort * *)
0x180098bfb  mov     ebx, eax
0x180098bfd  test    eax, eax
0x180098bff  jns     short loc_180098C08
0x180098c01  mov     edx, 10Fh
0x180098c06  jmp     short loc_180098C55
0x180098c08  mov     [rbp+57h+arg_8], 0FFFFFFFF80000002h
0x180098c10  xor     r9d, r9d
0x180098c13  lea     r8, aTimeoutcount; "TimeoutCount"
0x180098c1a  lea     edx, [r9+1]
0x180098c1e  lea     rcx, [rbp+57h+arg_8]
0x180098c22  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x180098c27  mov     rcx, [rbp+5Fh]; this
0x180098c2b  test    eax, eax
0x180098c2d  jns     short loc_180098C3F
0x180098c2f  mov     r9d, eax; char *
  ... truncated ...
```
