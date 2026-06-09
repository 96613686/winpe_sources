# CFlightingHttpRequest::InitializeServiceHeaders(ushort * *)

- ea: `0x18009c980`
- end: `0x18009ceca`
- name: `?InitializeServiceHeaders@CFlightingHttpRequest@@UEAAJPEAPEAG@Z`
- size: `1354`
- prototype: `__int64 __fastcall(CFlightingHttpRequest *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x180013da0`
- `0x1800177bc`
- `0x18001c6f4`
- `0x18001ec78`
- `0x18002035c`
- `0x180023fa8`
- `0x1800240f0`
- `0x180085a24`
- `0x180086644`
- `0x180086944`
- `0x180098040`
- `0x1800996b4`
- `0x18009c4ec`
- `0x18009c57c`
- `0x18009c6f0`
- `0x18009c980`
- `0x18009ced0`
- `0x18009cfd8`
- `0x18009d068`
- `0x1800b2e58`
- `0x1800b53f8`
- `0x1800b8614`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cb5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cb5a`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x18009cb4c`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x18009cb4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ccb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ccb6`

## string_xrefs

- `0x18009ca96`: `##DELETE##`
- `0x18009cb81`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\flightinghttprequest.cpp`
- `0x18009cd4e`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\flightinghttprequest.cpp`
- `0x18009cdda`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\flightinghttprequest.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFlightingHttpRequest::InitializeServiceHeaders(CFlightingHttpRequest *this, unsigned __int16 **a2)
{
  char v4; // si
  CUserIdentityProvider *v5; // rbx
  __int64 UserTicket; // rbx
  unsigned __int64 v7; // rdx
  unsigned __int8 v8; // cl
  int v9; // r15d
  __int64 v10; // rcx
  FlightSettingsAPITelemetryClass *v11; // rax
  unsigned __int64 v12; // rdx
  unsigned __int8 v13; // cl
  int v14; // r15d
  __int64 v15; // rcx
  FlightSettingsAPITelemetryClass *v16; // rax
  signed int LastError; // eax
  unsigned int v18; // ebx
  Flighting::Helpers *v19; // rcx
  __int64 FlightingMsaV2DeviceScope; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  const unsigned __int16 *v24; // rbx
  __int64 FlightingMsaV2DeviceAppId; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  const unsigned __int16 *v29; // rax
  int MSADeviceJsonWebToken; // ebx
  CUserIdentityProvider *v31; // rbx
  unsigned __int64 v32; // rdx
  unsigned __int8 v33; // cl
  int v34; // r14d
  __int64 v35; // rcx
  FlightSettingsAPITelemetryClass *v36; // rax
  unsigned __int16 *v37; // rbx
  int v38; // eax
  unsigned int v39; // edi
  int v40; // eax
  __int64 v41; // rdx
  unsigned __int16 *v42; // rax
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v47; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h]
  __int64 v49; // [rsp+80h] [rbp-80h]
  LPVOID pv; // [rsp+88h] [rbp-78h] BYREF
  __int64 v51; // [rsp+90h] [rbp-70h]
  __int64 v52; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v53; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-58h]
  __int64 v55; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v56; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v57; // [rsp+C0h] [rbp-40h]
  __int64 v58; // [rsp+C8h] [rbp-38h]
  _BYTE v59[40]; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR LocaleName[88]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  *a2 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v4 = 0;
  pv = 0;
  v51 = 0;
  v52 = 0;
  v45 = 0;
  if ( *((_BYTE *)this + 64) )
  {
    v5 = (CUserIdentityProvider *)*((_QWORD *)this + 9);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    v51 = -1;
    v52 = -1;
    UserTicket = (unsigned int)CUserIdentityProvider::GetUserTicket(
                                 v5,
                                 (unsigned __int16 **)&pv,
                                 (enum FlightingAccountType *)&v45);
    v46 = -2147483646;
    v9 = FSRegUtils::SetFlightingRegDWORD(&v46, 1, L"MsaUserTicketHr", UserTicket);
    if ( v9 < 0 && FlightSettingsAPITelemetryClass::IsEnabled(v8, v7) )
    {
      v11 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                 v10,
                                                 _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
      FlightSettingsAPITelemetryClass::WritingUserTicketHrFailed_(v11, v9);
    }
    if ( (int)UserTicket < 0 )
    {
      v4 = 1;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        &pv,
        &::LocaleName,
        -1);
    }
    else if ( v45 == 1 )
    {
      v4 = 1;
    }
  }
  else
  {
    LODWORD(UserTicket) = 0;
    v46 = -2147483646;
    v14 = FSRegUtils::SetFlightingRegString((HKEY *)&v46, 1u, L"MsaUserTicketHr", L"##DELETE##");
    if ( v14 < 0 && FlightSettingsAPITelemetryClass::IsEnabled(v13, v12) )
    {
      v16 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                 v15,
                                                 _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
      FlightSettingsAPITelemetryClass::DeletingUserTicketHrFailed_(v16, v14);
    }
  }
  v47 = 0;
  v48 = 0;
  v49 = 0;
  if ( (unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmptyIgnoringWhitespace(&pv)
    || v45 == 2 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59227329>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59227329>::GetImpl'::`2'::impl)
      && Flighting::Helpers::GetFlightingMsaV2DeviceEnabled(v19) )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v47);
      v48 = -1;
      v49 = -1;
      FlightingMsaV2DeviceScope = Flighting::Helpers::GetFlightingMsaV2DeviceScope(v59);
      v24 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                        FlightingMsaV2DeviceScope,
                                        v21,
                                        v22,
                                        v23);
      FlightingMsaV2DeviceAppId = Flighting::Helpers::GetFlightingMsaV2DeviceAppId(&v56);
      v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                        FlightingMsaV2DeviceAppId,
                                        v26,
                                        v27,
                                        v28);
      MSADeviceJsonWebToken = Flighting::CDeviceIdentityProvider::GetMSADeviceJsonWebToken(v29, v24, &v47);
      std::wstring::_Tidy_deallocate(&v56);
      std::wstring::_Tidy_deallocate(v59);
    }
    else
    {
      v31 = (CUserIdentityProvider *)*((_QWORD *)this + 9);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v47);
      v48 = -1;
      v49 = -1;
      MSADeviceJsonWebToken = CUserIdentityProvider::GetMSADeviceTicket(
                                v31,
                                *((const unsigned __int16 **)this + 2),
                                &v47);
    }
    v46 = -2147483646;
    v34 = FSRegUtils::SetFlightingRegDWORD(&v46, 1, L"MsaDeviceTicketHr", (unsigned int)MSADeviceJsonWebToken);
    if ( v34 < 0 && FlightSettingsAPITelemetryClass::IsEnabled(v33, v32) )
    {
      v36 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                 v35,
                                                 _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
      FlightSettingsAPITelemetryClass::WritingMsaDeviceTicketHrFailed_(v36, v34);
    }
    if ( MSADeviceJsonWebToken < 0 )
      goto LABEL_15;
    if ( (unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmptyIgnoringWhitespace(&pv) )
    {
      v4 = 1;
      v37 = v47;
      v47 = 0;
      v49 = 0;
      v48 = 0;
      if ( pv )
        CoTaskMemFree(pv);
      pv = v37;
      v52 = -1;
      v51 = -1;
    }
  }
  else if ( (int)UserTicket < 0 )
  {
LABEL_15:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
      &pv,
      L"deviceTicketDummyValue",
      -1);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
      &v47,
      L"deviceTicketDummyValue",
      -1);
  }
  if ( GetUserDefaultLocaleName(LocaleName, 85) )
  {
    v56 = 0;
    v57 = 0;
    v58 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v56);
    v57 = -1;
    v58 = -1;
    v46 = -2147483646;
    if ( FSRegUtils::GetFlightingRegString((HKEY *)&v46, 1u, L"CallerAlias", &v56) < 0 )
    {
      v38 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              &v56,
              &::LocaleName,
              -1);
      v39 = v38;
      if ( v38 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9E,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\flightinghttprequest.cpp",
          (const char *)(unsigned int)v38,
          v44);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v56);
        v18 = v39;
        goto LABEL_45;
      }
    }
    if ( v4 )
    {
      v40 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              &v53,
              L"%s%s \r\n%s%s\r\n%s%s\r\n%s%s \r\n",
              L"Authorization: Bearer ",
              pv);
      v18 = v40;
      if ( v40 < 0 )
      {
        v41 = 175;
LABEL_40:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v41,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\flightinghttprequest.cpp",
          (const char *)(unsigned int)v40,
          (int)L"X-AuthType: ");
LABEL_44:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v56);
        goto LABEL_45;
      }
    }
    else
    {
      v40 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              &v53,
              L"%s%s \r\n%s%s\r\n%s%s\r\n%s%s\r\n%s%s \r\n",
              L"Authorization: Bearer ",
              pv);
      v18 = v40;
      if ( v40 < 0 )
      {
        v41 = 193;
        goto LABEL_40;
      }
    }
    v42 = v53;
    v53 = 0;
    v55 = 0;
    v54 = 0;
    *a2 = v42;
    goto LABEL_44;
  }
  LastError = GetLastError();
  v18 = LastError;
  if ( LastError > 0 )
    v18 = (unsigned __int16)LastError | 0x80070000;
  if ( (v18 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\flightinghttprequest.cpp",
      (const char *)v18,
      v44);
LABEL_45:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v47);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v53);
  return v18;
}

```

## disassembly

```asm
0x18009c980  mov     [rsp-8+arg_10], rbx
0x18009c985  push    rbp
0x18009c986  push    rsi
0x18009c987  push    rdi
0x18009c988  push    r12
0x18009c98a  push    r13
0x18009c98c  push    r14
0x18009c98e  push    r15
0x18009c990  lea     rbp, [rsp-0C0h]
0x18009c998  sub     rsp, 1C0h
0x18009c99f  mov     rax, cs:__security_cookie
0x18009c9a6  xor     rax, rsp
0x18009c9a9  mov     [rbp+0F0h+var_40], rax
0x18009c9b0  mov     r13, rdx
0x18009c9b3  mov     r14, rcx
0x18009c9b6  xor     eax, eax
0x18009c9b8  mov     [rdx], rax
0x18009c9bb  mov     [rbp+0F0h+var_150], rax
0x18009c9bf  mov     [rbp+0F0h+var_148], rax
0x18009c9c3  mov     [rbp+0F0h+var_140], rax
0x18009c9c7  mov     sil, al
0x18009c9ca  mov     [rbp+0F0h+pv], rax
0x18009c9ce  mov     [rbp+0F0h+var_160], rax
0x18009c9d2  mov     [rbp+0F0h+var_158], rax
0x18009c9d6  mov     [rsp+1F0h+var_190], eax
0x18009c9da  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009c9de  cmp     [rcx+40h], al
0x18009c9e1  jz      loc_18009CA88
0x18009c9e7  mov     rbx, [rcx+48h]
0x18009c9eb  lea     rcx, [rbp+0F0h+pv]
0x18009c9ef  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009c9f4  mov     [rbp+0F0h+var_160], rdi
0x18009c9f8  mov     [rbp+0F0h+var_158], rdi
0x18009c9fc  lea     r8, [rsp+1F0h+var_190]; enum FlightingAccountType *
0x18009ca01  lea     rdx, [rbp+0F0h+pv]; unsigned __int16 **
0x18009ca05  mov     rcx, rbx; this
0x18009ca08  call    ?GetUserTicket@CUserIdentityProvider@@QEAAJPEAPEAGPEAW4FlightingAccountType@@@Z; CUserIdentityProvider::GetUserTicket(ushort * *,FlightingAccountType *)
0x18009ca0d  mov     ebx, eax
0x18009ca0f  mov     r12, 0FFFFFFFF80000002h
0x18009ca16  mov     [rsp+1F0h+var_188], r12
0x18009ca1b  mov     r9d, eax
0x18009ca1e  lea     r8, aMsauserticketh; "MsaUserTicketHr"
0x18009ca25  mov     edi, 1
0x18009ca2a  mov     edx, edi
0x18009ca2c  lea     rcx, [rsp+1F0h+var_188]
0x18009ca31  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x18009ca36  mov     r15d, eax
0x18009ca39  test    eax, eax
0x18009ca3b  jns     short loc_18009CA5D
0x18009ca3d  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18009ca42  test    al, al
0x18009ca44  jz      short loc_18009CA5D
0x18009ca46  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x18009ca4d  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x18009ca52  mov     edx, r15d; int
0x18009ca55  mov     rcx, rax; this
0x18009ca58  call    ?WritingUserTicketHrFailed_@FlightSettingsAPITelemetryClass@@QEAAXJ@Z; FlightSettingsAPITelemetryClass::WritingUserTicketHrFailed_(long)
0x18009ca5d  xor     r15d, r15d
0x18009ca60  test    ebx, ebx
0x18009ca62  js      short loc_18009CA6F
0x18009ca64  cmp     [rsp+1F0h+var_190], edi
0x18009ca68  jnz     short loc_18009CADF
0x18009ca6a  mov     sil, dil
0x18009ca6d  jmp     short loc_18009CADF
0x18009ca6f  mov     sil, dil
0x18009ca72  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009ca76  lea     rdx, LocaleName
0x18009ca7d  lea     rcx, [rbp+0F0h+pv]
0x18009ca81  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18009ca86  jmp     short loc_18009CADF
0x18009ca88  mov     ebx, eax
0x18009ca8a  mov     r12, 0FFFFFFFF80000002h
0x18009ca91  mov     [rsp+1F0h+var_188], r12
0x18009ca96  lea     r9, aDelete_0; "##DELETE##"
0x18009ca9d  lea     r8, aMsauserticketh; "MsaUserTicketHr"
0x18009caa4  mov     edi, 1
0x18009caa9  mov     edx, edi
0x18009caab  lea     rcx, [rsp+1F0h+var_188]
0x18009cab0  call    ?SetFlightingRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBG2@Z; FSRegUtils::SetFlightingRegString(HKEY__ * const &,FlightingRegistryKey,ushort const *,ushort const *)
0x18009cab5  mov     r15d, eax
0x18009cab8  test    eax, eax
0x18009caba  jns     short loc_18009CADC
0x18009cabc  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18009cac1  test    al, al
0x18009cac3  jz      short loc_18009CADC
0x18009cac5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x18009cacc  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x18009cad1  mov     edx, r15d; int
0x18009cad4  mov     rcx, rax; this
0x18009cad7  call    ?DeletingUserTicketHrFailed_@FlightSettingsAPITelemetryClass@@QEAAXJ@Z; FlightSettingsAPITelemetryClass::DeletingUserTicketHrFailed_(long)
0x18009cadc  xor     r15d, r15d
0x18009cadf  mov     [rsp+1F0h+var_180], r15
0x18009cae4  mov     [rsp+1F0h+var_178], r15
0x18009cae9  mov     [rbp+0F0h+var_170], r15
0x18009caed  lea     rcx, [rbp+0F0h+pv]
0x18009caf1  call    ?IsEmptyIgnoringWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::IsEmptyIgnoringWhitespace(void)
0x18009caf6  test    al, al
0x18009caf8  jnz     loc_18009CB97
0x18009cafe  cmp     [rsp+1F0h+var_190], 2
0x18009cb03  jz      loc_18009CB97
0x18009cb09  test    ebx, ebx
0x18009cb0b  jns     loc_18009CCCE
0x18009cb11  lea     rbx, aNoAuth; "NO-AUTH"
0x18009cb18  or      r14, 0FFFFFFFFFFFFFFFFh
0x18009cb1c  mov     r8, r14
0x18009cb1f  lea     rdx, aDeviceticketdu; "deviceTicketDummyValue"
0x18009cb26  lea     rcx, [rbp+0F0h+pv]
0x18009cb2a  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18009cb2f  mov     r8, r14
0x18009cb32  lea     rdx, aDeviceticketdu; "deviceTicketDummyValue"
0x18009cb39  lea     rcx, [rsp+1F0h+var_180]
0x18009cb3e  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18009cb43  mov     edx, 55h ; 'U'; cchLocaleName
0x18009cb48  lea     rcx, [rbp+0F0h+LocaleName]; lpLocaleName
0x18009cb4c  call    cs:__imp_GetUserDefaultLocaleName
0x18009cb52  test    eax, eax
0x18009cb54  jnz     loc_18009CCEE
0x18009cb5a  call    cs:__imp_GetLastError
0x18009cb60  mov     ebx, eax
0x18009cb62  test    eax, eax
0x18009cb64  jle     short loc_18009CB6F
0x18009cb66  movzx   ebx, ax
0x18009cb69  or      ebx, 80070000h
0x18009cb6f  test    ebx, ebx
0x18009cb71  jns     loc_18009CE80
0x18009cb77  mov     rcx, [rbp+0F8h]; this
0x18009cb7e  mov     r9d, ebx; char *
0x18009cb81  lea     r8, aOnecoreBaseFli_90; "onecore\\base\\flighting\\flightsetting"...
0x18009cb88  mov     edx, 97h; void *
0x18009cb8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009cb92  jmp     loc_18009CE80
0x18009cb97  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59227329@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59227329@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59227329> `wil::Feature<__WilFeatureTraits_Feature_59227329>::GetImpl(void)'::`2'::impl
0x18009cb9e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59227329@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59227329>::__private_IsEnabled(void)
0x18009cba3  test    al, al
0x18009cba5  jz      short loc_18009CC12
0x18009cba7  call    ?GetFlightingMsaV2DeviceEnabled@Helpers@Flighting@@YA_NXZ; Flighting::Helpers::GetFlightingMsaV2DeviceEnabled(void)
0x18009cbac  test    al, al
0x18009cbae  jz      short loc_18009CC12
0x18009cbb0  lea     rcx, [rsp+1F0h+var_180]
0x18009cbb5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009cbba  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009cbbe  mov     [rsp+1F0h+var_178], rax
0x18009cbc3  mov     [rbp+0F0h+var_170], rax
0x18009cbc7  lea     rcx, [rbp+0F0h+var_118]
0x18009cbcb  call    ?GetFlightingMsaV2DeviceScope@Helpers@Flighting@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Flighting::Helpers::GetFlightingMsaV2DeviceScope(void)
0x18009cbd0  mov     rcx, rax
0x18009cbd3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009cbd8  mov     rbx, rax
0x18009cbdb  lea     rcx, [rbp+0F0h+var_138]
0x18009cbdf  call    ?GetFlightingMsaV2DeviceAppId@Helpers@Flighting@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Flighting::Helpers::GetFlightingMsaV2DeviceAppId(void)
0x18009cbe4  mov     rcx, rax
0x18009cbe7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009cbec  lea     r8, [rsp+1F0h+var_180]; unsigned __int16 **
0x18009cbf1  mov     rdx, rbx; unsigned __int16 *
0x18009cbf4  mov     rcx, rax; unsigned __int16 *
0x18009cbf7  call    ?GetMSADeviceJsonWebToken@CDeviceIdentityProvider@Flighting@@SAJPEBG0PEAPEAG@Z; Flighting::CDeviceIdentityProvider::GetMSADeviceJsonWebToken(ushort const *,ushort const *,ushort * *)
0x18009cbfc  mov     ebx, eax
0x18009cbfe  lea     rcx, [rbp+0F0h+var_138]
0x18009cc02  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009cc07  lea     rcx, [rbp+0F0h+var_118]
0x18009cc0b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009cc10  jmp     short loc_18009CC40
0x18009cc12  mov     rbx, [r14+48h]
0x18009cc16  lea     rcx, [rsp+1F0h+var_180]
0x18009cc1b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009cc20  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009cc24  mov     [rsp+1F0h+var_178], rax
0x18009cc29  mov     [rbp+0F0h+var_170], rax
0x18009cc2d  lea     r8, [rsp+1F0h+var_180]; unsigned __int16 **
0x18009cc32  mov     rdx, [r14+10h]; unsigned __int16 *
0x18009cc36  mov     rcx, rbx; this
0x18009cc39  call    ?GetMSADeviceTicket@CUserIdentityProvider@@QEAAJPEBGPEAPEAG@Z; CUserIdentityProvider::GetMSADeviceTicket(ushort const *,ushort * *)
0x18009cc3e  mov     ebx, eax
0x18009cc40  mov     [rsp+1F0h+var_188], r12
0x18009cc45  mov     r9d, ebx
0x18009cc48  lea     r8, aMsadeviceticke; "MsaDeviceTicketHr"
0x18009cc4f  mov     edx, edi
0x18009cc51  lea     rcx, [rsp+1F0h+var_188]
0x18009cc56  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x18009cc5b  mov     r14d, eax
0x18009cc5e  test    eax, eax
0x18009cc60  jns     short loc_18009CC82
0x18009cc62  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18009cc67  test    al, al
0x18009cc69  jz      short loc_18009CC82
0x18009cc6b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x18009cc72  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x18009cc77  mov     edx, r14d; int
0x18009cc7a  mov     rcx, rax; this
0x18009cc7d  call    ?WritingMsaDeviceTicketHrFailed_@FlightSettingsAPITelemetryClass@@QEAAXJ@Z; FlightSettingsAPITelemetryClass::WritingMsaDeviceTicketHrFailed_(long)
0x18009cc82  test    ebx, ebx
0x18009cc84  js      loc_18009CB11
0x18009cc8a  lea     rcx, [rbp+0F0h+pv]
0x18009cc8e  call    ?IsEmptyIgnoringWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::IsEmptyIgnoringWhitespace(void)
0x18009cc93  test    al, al
0x18009cc95  jz      short loc_18009CCCE
0x18009cc97  mov     sil, dil
0x18009cc9a  mov     rbx, [rsp+1F0h+var_180]
0x18009cc9f  mov     [rsp+1F0h+var_180], r15
0x18009cca4  mov     [rbp+0F0h+var_170], r15
0x18009cca8  mov     [rsp+1F0h+var_178], r15
0x18009ccad  mov     rcx, [rbp+0F0h+pv]; pv
0x18009ccb1  test    rcx, rcx
0x18009ccb4  jz      short loc_18009CCBC
0x18009ccb6  call    cs:__imp_CoTaskMemFree
0x18009ccbc  mov     [rbp+0F0h+pv], rbx
0x18009ccc0  or      r14, 0FFFFFFFFFFFFFFFFh
0x18009ccc4  mov     [rbp+0F0h+var_158], r14
0x18009ccc8  mov     [rbp+0F0h+var_160], r14
0x18009cccc  jmp     short loc_18009CCD2
0x18009ccce  or      r14, 0FFFFFFFFFFFFFFFFh
0x18009ccd2  lea     rbx, aAad; "AAD"
0x18009ccd9  lea     rax, aMsa; "MSA"
0x18009cce0  cmp     [rsp+1F0h+var_190], 2
0x18009cce5  cmovnz  rbx, rax
0x18009cce9  jmp     loc_18009CB43
0x18009ccee  mov     [rbp+0F0h+var_138], r15
0x18009ccf2  mov     [rbp+0F0h+var_130], r15
0x18009ccf6  mov     [rbp+0F0h+var_128], r15
0x18009ccfa  lea     rcx, [rbp+0F0h+var_138]
0x18009ccfe  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009cd03  mov     [rbp+0F0h+var_130], r14
0x18009cd07  mov     [rbp+0F0h+var_128], r14
0x18009cd0b  mov     [rsp+1F0h+var_188], r12
0x18009cd10  lea     r9, [rbp+0F0h+var_138]
0x18009cd14  lea     r8, aCalleralias_0; "CallerAlias"
0x18009cd1b  mov     edx, edi
0x18009cd1d  lea     rcx, [rsp+1F0h+var_188]
0x18009cd22  call    ?GetFlightingRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAPEAG@Z; FSRegUtils::GetFlightingRegString(HKEY__ * const &,FlightingRegistryKey,ushort const *,ushort * *)
0x18009cd27  test    eax, eax
0x18009cd29  jns     short loc_18009CD70
0x18009cd2b  mov     r8, r14
0x18009cd2e  lea     rdx, LocaleName
0x18009cd35  lea     rcx, [rbp+0F0h+var_138]
0x18009cd39  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18009cd3e  mov     edi, eax
0x18009cd40  test    eax, eax
0x18009cd42  jns     short loc_18009CD70
0x18009cd44  mov     rcx, [rbp+0F8h]; this
0x18009cd4b  mov     r9d, eax; char *
0x18009cd4e  lea     r8, aOnecoreBaseFli_90; "onecore\\base\\flighting\\flightsetting"...
0x18009cd55  mov     edx, 9Eh; void *
0x18009cd5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009cd5f  nop
0x18009cd60  lea     rcx, [rbp+0F0h+var_138]
0x18009cd64  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009cd69  mov     ebx, edi
0x18009cd6b  jmp     loc_18009CE80
0x18009cd70  mov     rax, [rbp+0F0h+var_138]
0x18009cd74  mov     r9, [rbp+0F0h+pv]
0x18009cd78  lea     r8, aAuthorizationB; "Authorization: Bearer "
0x18009cd7f  test    sil, sil
0x18009cd82  jz      short loc_18009CDF5
0x18009cd84  mov     [rsp+1F0h+var_1A8], rax
0x18009cd89  lea     rax, aCalleralias; "CallerAlias: "
0x18009cd90  mov     [rsp+1F0h+var_1B0], rax
0x18009cd95  lea     rax, [rbp+0F0h+LocaleName]
0x18009cd99  mov     [rsp+1F0h+var_1B8], rax
0x18009cd9e  lea     rax, aAcceptLanguage; "Accept-Language: "
0x18009cda5  mov     [rsp+1F0h+var_1C0], rax
0x18009cdaa  mov     [rsp+1F0h+var_1C8], rbx
0x18009cdaf  lea     rax, aXAuthtype; "X-AuthType: "
0x18009cdb6  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x18009cdbb  lea     rdx, aSSSSSSSS; "%s%s \r\n%s%s\r\n%s%s\r\n%s%s \r\n"
0x18009cdc2  lea     rcx, [rbp+0F0h+var_150]
0x18009cdc6  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18009cdcb  mov     ebx, eax
0x18009cdcd  test    eax, eax
0x18009cdcf  jns     loc_18009CE62
0x18009cdd5  mov     edx, 0AFh; void *
0x18009cdda  lea     r8, aOnecoreBaseFli_90; "onecore\\base\\flighting\\flightsetting"...
0x18009cde1  mov     r9d, eax; char *
0x18009cde4  mov     rcx, [rbp+0F8h]; this
0x18009cdeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009cdf0  jmp     loc_18009CE76
0x18009cdf5  mov     rcx, [rsp+1F0h+var_180]
0x18009cdfa  mov     [rsp+1F0h+var_198], rax
0x18009cdff  lea     rax, aCalleralias; "CallerAlias: "
0x18009ce06  mov     [rsp+1F0h+var_1A0], rax
0x18009ce0b  lea     rax, [rbp+0F0h+LocaleName]
0x18009ce0f  mov     [rsp+1F0h+var_1A8], rax
0x18009ce14  lea     rax, aAcceptLanguage; "Accept-Language: "
0x18009ce1b  mov     [rsp+1F0h+var_1B0], rax
0x18009ce20  mov     [rsp+1F0h+var_1B8], rcx
0x18009ce25  lea     rax, aXDeviceauthBea; "X-DeviceAuth: Bearer "
0x18009ce2c  mov     [rsp+1F0h+var_1C0], rax
0x18009ce31  mov     [rsp+1F0h+var_1C8], rbx
0x18009ce36  lea     rax, aXAuthtype; "X-AuthType: "
0x18009ce3d  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x18009ce42  lea     rdx, aSSSSSSSSSS; "%s%s \r\n%s%s\r\n%s%s\r\n%s%s\r\n%s%s "...
0x18009ce49  lea     rcx, [rbp+0F0h+var_150]
0x18009ce4d  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18009ce52  mov     ebx, eax
0x18009ce54  test    eax, eax
0x18009ce56  jns     short loc_18009CE62
0x18009ce58  mov     edx, 0C1h
0x18009ce5d  jmp     loc_18009CDDA
0x18009ce62  mov     rax, [rbp+0F0h+var_150]
0x18009ce66  mov     [rbp+0F0h+var_150], r15
0x18009ce6a  mov     [rbp+0F0h+var_140], r15
  ... truncated ...
```
