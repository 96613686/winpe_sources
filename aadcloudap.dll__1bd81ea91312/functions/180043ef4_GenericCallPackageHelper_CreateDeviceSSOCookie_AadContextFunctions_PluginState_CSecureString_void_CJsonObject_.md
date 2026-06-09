# GenericCallPackageHelper::CreateDeviceSSOCookie(AadContextFunctions *,PluginState &,CSecureString &,void *,CJsonObject *,CSecureString &)

- ea: `0x180043ef4`
- end: `0x180044778`
- name: `?CreateDeviceSSOCookie@GenericCallPackageHelper@@CAJPEAVAadContextFunctions@@AEAVPluginState@@AEAVCSecureString@@PEAXPEAVCJsonObject@@2@Z`
- size: `2180`
- prototype: `__int64 __fastcall(struct AadContextFunctions *this, struct PluginState *, struct CSecureString *, void *, struct CJsonObject *, struct CSecureString *)`
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800477bc`

## callees

- `0x180006380`
- `0x1800063f4`
- `0x1800065e8`
- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x1800090d0`
- `0x18000a300`
- `0x18000aa74`
- `0x18001f458`
- `0x18001ff00`
- `0x180020974`
- `0x180021eb8`
- `0x180024314`
- `0x18002a6f4`
- `0x180033180`
- `0x180040cec`
- `0x180040ff8`
- `0x180041830`
- `0x180041868`
- `0x180042df0`
- `0x180043180`
- `0x180043ef4`
- `0x180049370`
- `0x180071e14`
- `0x180077680`
- `0x180077ab4`
- `0x1800788a4`
- `0x1800794f0`
- `0x180079d2c`
- `0x18007a0fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800446f9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180044712`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800446f9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180044712`

## string_xrefs

- `0x18004428a`: `aad:brokerplugin`
- `0x1800444ef`: `ua_redirect_uri`
- `0x18004406b`: `uaClientId`
- `0x180043f8a`: `GenericCallPackageHelper::CreateDeviceSSOCookie`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GenericCallPackageHelper::CreateDeviceSSOCookie(
        struct AadContextFunctions *this,
        struct PluginState *a2,
        struct CSecureString *a3,
        void *a4,
        struct CJsonObject *a5,
        struct CSecureString *a6)
{
  int TokenSid; // edx
  int DeviceSSOCookie; // eax
  __int64 v12; // rdx
  int Nonce; // ebx
  bool IsValid; // al
  volatile signed __int32 *v15; // rcx
  int appended; // ebx
  unsigned int v17; // esi
  char *v18; // rcx
  int i; // edi
  struct CSecureString *v21; // [rsp+20h] [rbp-E0h]
  struct CSecureString *v22; // [rsp+20h] [rbp-E0h]
  struct NonceLifetime *v23; // [rsp+30h] [rbp-D0h]
  struct NonceLifetime *v24; // [rsp+30h] [rbp-D0h]
  unsigned int v25; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  void *Block[2]; // [rsp+68h] [rbp-98h] BYREF
  int v29; // [rsp+78h] [rbp-88h]
  __int64 v30; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v32; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v33[8]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v34[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v35[8]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v37; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v39; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v40[96]; // [rsp+E0h] [rbp-20h] BYREF

  v25 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v36);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v35);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v30);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v34);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v33);
  *(_OWORD *)Block = 0;
  v29 = 0;
  v37 = 0;
  CachedNonce::CachedNonce((CachedNonce *)&v38);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    v40,
    "genericcallpackagehelper.cpp",
    "GenericCallPackageHelper::CreateDeviceSSOCookie",
    &v25);
  ATL::CSimpleStringT<unsigned short,0>::Empty(a6);
  if ( !PluginState::IsAadJoined(a2) )
  {
    WPPTraceLogA(
      2,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      2,
      -2147187623,
      "genericcallpackagehelper.cpp",
      960,
      "HRESULT",
      &base);
    v25 = -1073445799;
    goto LABEL_36;
  }
  TokenSid = CheckPackageSidForDeviceSSOCookie(this, a4);
  v25 = TokenSid;
  if ( TokenSid < 0 )
  {
    LODWORD(v23) = 963;
LABEL_35:
    LODWORD(v21) = TokenSid;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v21, "genericcallpackagehelper.cpp", v23, "NTSTATUS", &base);
    goto LABEL_36;
  }
  CSecureString::operator=(v33, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 8LL) + 24LL));
  StringUtility::ParseNavigationUrl(a3, &v31);
  WebResponseHelper::GetJsonDataAsString(a5, L"uaClientId", &v30);
  TokenSid = GetTokenSid(this, a4, (struct CSecureString *)&v32);
  v25 = TokenSid;
  if ( TokenSid < 0 )
  {
    LODWORD(v23) = 969;
    goto LABEL_35;
  }
  DeviceSSOCookie = SsoCache::GetDeviceSSOCookie(
                      this,
                      v32,
                      *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)a2 + 8LL) + 8LL),
                      (const struct CSecureString *)&v30,
                      *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)a2 + 8LL) + 72LL),
                      a6,
                      (struct NonceLifetime *)&v37);
  TokenSid = DeviceSSOCookie;
  v25 = DeviceSSOCookie;
  if ( DeviceSSOCookie < 0 )
  {
    LODWORD(v23) = 980;
    goto LABEL_35;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::GetImpl'::`2'::impl,
                          (unsigned int)DeviceSSOCookie) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v27,
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 8LL) + 8LL));
    Nonce = SsoCache::GetNonce(this);
    v25 = Nonce;
    ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
    if ( Nonce < 0 )
    {
      LODWORD(v23) = 984;
      LODWORD(v21) = Nonce;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v21, "genericcallpackagehelper.cpp", v23, "NTSTATUS", &base);
      goto LABEL_36;
    }
  }
  if ( *(_DWORD *)(*(_QWORD *)a6 - 16LL) )
  {
    if ( (unsigned __int8)GenericCallPackageHelper::CanCachedSSOCookieBeUsed(this, (CachedNonce *)&v38) )
    {
      _InterlockedIncrement(&dword_1800E5E78);
      goto LABEL_36;
    }
    ATL::CSimpleStringT<unsigned short,0>::Empty(a6);
  }
  _InterlockedIncrement(&dword_1800E5E7C);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::GetImpl'::`2'::impl,
                          v12) )
  {
    if ( *(_DWORD *)(v31 - 16) || CachedNonce::IsEmpty((CachedNonce *)&v38) )
    {
      v37 = 0;
      _InterlockedIncrement(&dword_1800E5E94);
    }
    else
    {
      v37 = v39;
      CSecureString::operator=(&v31, v38);
      IsValid = NonceLifetime::IsValid((NonceLifetime *)&v39);
      v15 = &dword_1800E5E8C;
      if ( !IsValid )
        v15 = &dword_1800E5E94;
      _InterlockedIncrement(v15);
    }
  }
  TokenSid = GenericCallPackageHelper::AddNonceOrTimestamp(Block, &v31);
  v25 = TokenSid;
  if ( TokenSid < 0 )
  {
    LODWORD(v23) = 1030;
    goto LABEL_35;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v26,
    L"aad:brokerplugin");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v27,
    L"iss");
  KeyValueList::Add(Block, &v27, &v26);
  ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v26,
    L"tenant_id");
  KeyValueList::Add(Block, &v26, v33);
  ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v27,
    L"device_auth");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v26,
    L"grant_type");
  KeyValueList::Add(Block, &v26, &v27);
  ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v27,
    L"10.0.29599.1000");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v26,
    L"win_ver");
  KeyValueList::Add(Block, &v26, &v27);
  ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v27,
    L"2.0.1");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v26,
    L"windows_api_version");
  KeyValueList::Add(Block, &v26, &v27);
  ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v27,
    L"windows");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v26,
    L"x_client_platform");
  KeyValueList::Add(Block, &v26, &v27);
  ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  if ( *(_DWORD *)(v30 - 16) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v26,
      L"ua_client_id");
    KeyValueList::Add(Block, &v26, &v30);
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
    TokenSid = GetRedirectUri(this, a4);
    v25 = TokenSid;
    if ( TokenSid < 0 )
    {
      LODWORD(v23) = 1043;
      goto LABEL_35;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v26,
      L"ua_redirect_uri");
    KeyValueList::Add(Block, &v26, v34);
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
  }
  WebResponseHelper::FormatJson(Block, v35);
  TokenSid = BuildDeviceAuthAssertion(
               this,
               *(struct _AadApPluginHandle **)a2,
               (const struct CSecureString *)v35,
               1,
               (struct CSecureString *)&v36);
  v25 = TokenSid;
  if ( TokenSid < 0 )
  {
    LODWORD(v23) = 1050;
    goto LABEL_35;
  }
  appended = StringUtility::StringAppendFormat(
               a6,
               L"\"%s\" : %d, \"%s\" : \"%s\", \"%s\" : \"%s\"",
               L"call",
               8,
               L"assertion",
               v36,
               L"authority",
               *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 8LL) + 8LL));
  if ( appended < 0 )
  {
    LODWORD(v24) = 1055;
    LODWORD(v22) = appended;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v22, "genericcallpackagehelper.cpp", v24, "HRESULT", &base);
    v25 = appended & 0xAFFFFFFF | 0x40000000;
    goto LABEL_36;
  }
  TokenSid = SsoCache::SetDeviceSSOCookie(
               this,
               v32,
               *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)a2 + 8LL) + 8LL),
               (const struct CSecureString *)&v30,
               *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)a2 + 8LL) + 72LL),
               a6,
               (const struct NonceLifetime *)&v37);
  v25 = TokenSid;
  if ( TokenSid < 0 )
  {
    LODWORD(v23) = 1065;
    goto LABEL_35;
  }
LABEL_36:
  v17 = v25;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v40);
  CSecureString::~CSecureString((CSecureString *)&v32);
  ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
  v18 = (char *)Block[0];
  if ( Block[0] )
  {
    for ( i = 0; i < v29; v18 = (char *)Block[0] )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::`scalar deleting destructor'(&v18[8 * i]);
      KeyListValue::~KeyListValue((KeyListValue *)((char *)Block[1] + 72 * i++));
    }
    free(v18);
    Block[0] = 0;
  }
  if ( Block[1] )
  {
    free(Block[1]);
    Block[1] = 0;
  }
  v29 = 0;
  CSecureString::~CSecureString((CSecureString *)v33);
  CSecureString::~CSecureString((CSecureString *)v34);
  CSecureString::~CSecureString((CSecureString *)&v30);
  CSecureString::~CSecureString((CSecureString *)&v31);
  CSecureString::~CSecureString((CSecureString *)v35);
  CSecureString::~CSecureString((CSecureString *)&v36);
  return v17;
}

```

## disassembly

```asm
0x180043ef4  push    rbp
0x180043ef6  push    rbx
0x180043ef7  push    rsi
0x180043ef8  push    rdi
0x180043ef9  push    r13
0x180043efb  push    r14
0x180043efd  push    r15
0x180043eff  lea     rbp, [rsp-10h]
0x180043f04  sub     rsp, 110h
0x180043f0b  mov     r15, r9
0x180043f0e  mov     rbx, r8
0x180043f11  mov     r14, rdx
0x180043f14  mov     rdi, rcx
0x180043f17  mov     [rsp+140h+var_F0], 0
0x180043f1f  lea     rcx, [rbp+40h+var_90]; void *
0x180043f23  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180043f28  nop
0x180043f29  lea     rcx, [rbp+40h+var_98]; void *
0x180043f2d  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180043f32  nop
0x180043f33  lea     rcx, [rbp+40h+var_B8]; void *
0x180043f37  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180043f3c  nop
0x180043f3d  lea     rcx, [rbp+40h+var_C0]; void *
0x180043f41  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180043f46  nop
0x180043f47  lea     rcx, [rbp+40h+var_A0]; void *
0x180043f4b  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180043f50  nop
0x180043f51  lea     rcx, [rbp+40h+var_A8]; void *
0x180043f55  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180043f5a  nop
0x180043f5b  xorps   xmm0, xmm0
0x180043f5e  movdqu  xmmword ptr [rsp+140h+Block], xmm0
0x180043f64  mov     [rsp+140h+var_C8], 0
0x180043f6c  movdqu  [rbp+40h+var_88], xmm0
0x180043f71  lea     rcx, [rbp+40h+var_78]; this
0x180043f75  call    ??0CachedNonce@@QEAA@XZ; CachedNonce::CachedNonce(void)
0x180043f7a  nop
0x180043f7b  lea     rcx, [rbp+40h+var_B0]; void *
0x180043f7f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180043f84  nop
0x180043f85  lea     r9, [rsp+140h+var_F0]
0x180043f8a  lea     r8, aGenericcallpac_3; "GenericCallPackageHelper::CreateDeviceS"...
0x180043f91  lea     r13, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x180043f98  mov     rdx, r13
0x180043f9b  lea     rcx, [rbp+40h+var_60]
0x180043f9f  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180043fa4  nop
0x180043fa5  mov     rsi, [rbp+40h+arg_28]
0x180043fa9  mov     rcx, rsi
0x180043fac  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180043fb1  mov     rcx, r14; this
0x180043fb4  call    ?IsAadJoined@PluginState@@QEAA_NXZ; PluginState::IsAadJoined(void)
0x180043fb9  test    al, al
0x180043fbb  jnz     short loc_18004400D
0x180043fbd  lea     rax, base
0x180043fc4  mov     [rsp+140h+var_100], rax
0x180043fc9  lea     rax, aHresult; "HRESULT"
0x180043fd0  mov     [rsp+140h+var_108], rax
0x180043fd5  mov     dword ptr [rsp+140h+var_110], 3C0h
0x180043fdd  mov     [rsp+140h+var_118], r13
0x180043fe2  mov     dword ptr [rsp+140h+var_120], 80048459h
0x180043fea  mov     ecx, 2
0x180043fef  mov     r9d, ecx
0x180043ff2  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180043ff9  xor     edx, edx
0x180043ffb  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180044000  mov     [rsp+140h+var_F0], 0C0048459h
0x180044008  jmp     loc_180044696
0x18004400d  mov     rdx, r15; void *
0x180044010  mov     rcx, rdi; struct AadContextFunctions *
0x180044013  call    ?CheckPackageSidForDeviceSSOCookie@@YAJPEAVAadContextFunctions@@PEAX@Z; CheckPackageSidForDeviceSSOCookie(AadContextFunctions *,void *)
0x180044018  mov     edx, eax
0x18004401a  mov     [rsp+140h+var_F0], eax
0x18004401e  test    eax, eax
0x180044020  jns     short loc_180044047
0x180044022  lea     rax, base
0x180044029  mov     [rsp+140h+var_100], rax
0x18004402e  lea     rcx, aNtstatus; "NTSTATUS"
0x180044035  mov     [rsp+140h+var_108], rcx
0x18004403a  mov     dword ptr [rsp+140h+var_110], 3C3h
0x180044042  jmp     loc_180044677
0x180044047  mov     rax, [r14]
0x18004404a  mov     rdx, [rax+8]
0x18004404e  mov     rdx, [rdx+18h]
0x180044052  lea     rcx, [rbp+40h+var_A8]
0x180044056  call    ??4CSecureString@@QEAAAEAV0@PEBG@Z; CSecureString::operator=(ushort const *)
0x18004405b  lea     rdx, [rbp+40h+var_B8]
0x18004405f  mov     rcx, rbx
0x180044062  call    ?ParseNavigationUrl@StringUtility@@SAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z; StringUtility::ParseNavigationUrl(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180044067  lea     r8, [rbp+40h+var_C0]
0x18004406b  lea     rdx, aUaclientid; "uaClientId"
0x180044072  mov     rcx, [rbp+40h+arg_20]
0x180044076  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18004407b  lea     r8, [rbp+40h+var_B0]; struct CSecureString *
0x18004407f  mov     rdx, r15; void *
0x180044082  mov     rcx, rdi; struct AadContextFunctions *
0x180044085  call    ?GetTokenSid@@YAJPEAVAadContextFunctions@@PEAXAEAVCSecureString@@@Z; GetTokenSid(AadContextFunctions *,void *,CSecureString &)
0x18004408a  mov     edx, eax
0x18004408c  mov     [rsp+140h+var_F0], eax
0x180044090  test    eax, eax
0x180044092  jns     short loc_1800440B9
0x180044094  lea     rax, base
0x18004409b  mov     [rsp+140h+var_100], rax
0x1800440a0  lea     rcx, aNtstatus; "NTSTATUS"
0x1800440a7  mov     [rsp+140h+var_108], rcx
0x1800440ac  mov     dword ptr [rsp+140h+var_110], 3C9h
0x1800440b4  jmp     loc_180044677
0x1800440b9  mov     rax, [r14]
0x1800440bc  mov     r8, [rax+8]
0x1800440c0  lea     rax, [rbp+40h+var_88]
0x1800440c4  mov     [rsp+140h+var_110], rax; struct NonceLifetime *
0x1800440c9  mov     [rsp+140h+var_118], rsi; struct CSecureString *
0x1800440ce  mov     rax, [r8+48h]
0x1800440d2  mov     [rsp+140h+var_120], rax; unsigned __int16 *
0x1800440d7  lea     r9, [rbp+40h+var_C0]; struct CSecureString *
0x1800440db  mov     r8, [r8+8]; unsigned __int16 *
0x1800440df  mov     rdx, [rbp+40h+var_B0]; unsigned __int16 *
0x1800440e3  mov     rcx, rdi; this
0x1800440e6  call    ?GetDeviceSSOCookie@SsoCache@@SAJPEAVAadContextFunctions@@PEBG1AEBVCSecureString@@1AEAV3@AEAUNonceLifetime@@@Z; SsoCache::GetDeviceSSOCookie(AadContextFunctions *,ushort const *,ushort const *,CSecureString const &,ushort const *,CSecureString &,NonceLifetime &)
0x1800440eb  mov     edx, eax
0x1800440ed  mov     [rsp+140h+var_F0], eax
0x1800440f1  test    eax, eax
0x1800440f3  jns     short loc_18004411A
0x1800440f5  lea     rax, base
0x1800440fc  mov     [rsp+140h+var_100], rax
0x180044101  lea     rcx, aNtstatus; "NTSTATUS"
0x180044108  mov     [rsp+140h+var_108], rcx
0x18004410d  mov     dword ptr [rsp+140h+var_110], 3D4h
0x180044115  jmp     loc_180044677
0x18004411a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BrowserSSONonceCaching@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BrowserSSONonceCaching@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserSSONonceCaching> `wil::Feature<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::GetImpl(void)'::`2'::impl
0x180044121  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BrowserSSONonceCaching@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::__private_IsEnabled(void)
0x180044126  test    al, al
0x180044128  jz      short loc_18004419B
0x18004412a  mov     rax, [r14]
0x18004412d  mov     rdx, [rax+8]
0x180044131  mov     rdx, [rdx+8]
0x180044135  lea     rcx, [rsp+140h+var_E0]
0x18004413a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18004413f  nop
0x180044140  lea     r9, [rbp+40h+var_78]
0x180044144  lea     r8, [rsp+140h+var_E0]
0x180044149  lea     rdx, [rbp+40h+var_B0]
0x18004414d  mov     rcx, rdi; struct AadContextFunctions *
0x180044150  call    ?GetNonce@SsoCache@@SAJPEAVAadContextFunctions@@AEBVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAUCachedNonce@@@Z; SsoCache::GetNonce(AadContextFunctions *,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CachedNonce &)
0x180044155  mov     ebx, eax
0x180044157  mov     [rsp+140h+var_F0], eax
0x18004415b  mov     rcx, [rsp+140h+var_E0]
0x180044160  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180044164  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180044169  test    ebx, ebx
0x18004416b  jns     short loc_18004419B
0x18004416d  lea     rax, base
0x180044174  mov     [rsp+140h+var_100], rax
0x180044179  lea     rcx, aNtstatus; "NTSTATUS"
0x180044180  mov     [rsp+140h+var_108], rcx
0x180044185  mov     dword ptr [rsp+140h+var_110], 3D8h
0x18004418d  mov     [rsp+140h+var_118], r13
0x180044192  mov     dword ptr [rsp+140h+var_120], ebx
0x180044196  jmp     loc_180044680
0x18004419b  mov     rax, [rsi]
0x18004419e  cmp     dword ptr [rax-10h], 0
0x1800441a2  jz      short loc_1800441D8
0x1800441a4  lea     rax, [rbp+40h+var_78]
0x1800441a8  mov     [rsp+140h+var_120], rax; CachedNonce *
0x1800441ad  lea     r9, [rbp+40h+var_88]
0x1800441b1  lea     r8, [rbp+40h+var_B8]
0x1800441b5  mov     rdx, rsi
0x1800441b8  mov     rcx, rdi; this
0x1800441bb  call    ?CanCachedSSOCookieBeUsed@GenericCallPackageHelper@@CA_NPEAVAadContextFunctions@@AEBVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBUNonceLifetime@@AEBUCachedNonce@@@Z; GenericCallPackageHelper::CanCachedSSOCookieBeUsed(AadContextFunctions *,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,NonceLifetime const &,CachedNonce const &)
0x1800441c0  test    al, al
0x1800441c2  jz      short loc_1800441D0
0x1800441c4  lock inc cs:dword_1800E5E78
0x1800441cb  jmp     loc_180044696
0x1800441d0  mov     rcx, rsi
0x1800441d3  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800441d8  lock inc cs:dword_1800E5E7C
0x1800441df  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BrowserSSONonceCaching@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BrowserSSONonceCaching@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserSSONonceCaching> `wil::Feature<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::GetImpl(void)'::`2'::impl
0x1800441e6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BrowserSSONonceCaching@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::__private_IsEnabled(void)
0x1800441eb  test    al, al
0x1800441ed  jz      short loc_18004424D
0x1800441ef  mov     rax, [rbp+40h+var_B8]
0x1800441f3  cmp     dword ptr [rax-10h], 0
0x1800441f7  jnz     short loc_18004423E
0x1800441f9  lea     rcx, [rbp+40h+var_78]; this
0x1800441fd  call    ?IsEmpty@CachedNonce@@QEBA_NXZ; CachedNonce::IsEmpty(void)
0x180044202  test    al, al
0x180044204  jnz     short loc_18004423E
0x180044206  movups  xmm0, [rbp+40h+var_70]
0x18004420a  movdqu  [rbp+40h+var_88], xmm0
0x18004420f  mov     rdx, [rbp+40h+var_78]
0x180044213  lea     rcx, [rbp+40h+var_B8]
0x180044217  call    ??4CSecureString@@QEAAAEAV0@PEBG@Z; CSecureString::operator=(ushort const *)
0x18004421c  lea     rcx, [rbp+40h+var_70]; this
0x180044220  call    ?IsValid@NonceLifetime@@QEBA_NXZ; NonceLifetime::IsValid(void)
0x180044225  lea     rdx, dword_1800E5E94
0x18004422c  lea     rcx, dword_1800E5E8C
0x180044233  test    al, al
0x180044235  cmovz   rcx, rdx
0x180044239  lock inc dword ptr [rcx]
0x18004423c  jmp     short loc_18004424D
0x18004423e  xorps   xmm0, xmm0
0x180044241  movdqu  [rbp+40h+var_88], xmm0
0x180044246  lock inc cs:dword_1800E5E94
0x18004424d  lea     rdx, [rbp+40h+var_B8]
0x180044251  lea     rcx, [rsp+140h+Block]
0x180044256  call    ?AddNonceOrTimestamp@GenericCallPackageHelper@@CAJAEAVKeyValueList@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GenericCallPackageHelper::AddNonceOrTimestamp(KeyValueList &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004425b  mov     edx, eax
0x18004425d  mov     [rsp+140h+var_F0], eax
0x180044261  test    eax, eax
0x180044263  jns     short loc_18004428A
0x180044265  lea     rax, base
0x18004426c  mov     [rsp+140h+var_100], rax
0x180044271  lea     rcx, aNtstatus; "NTSTATUS"
0x180044278  mov     [rsp+140h+var_108], rcx
0x18004427d  mov     dword ptr [rsp+140h+var_110], 406h
0x180044285  jmp     loc_180044677
0x18004428a  lea     rdx, aAadBrokerplugi; "aad:brokerplugin"
0x180044291  lea     rcx, [rsp+140h+var_E8]
0x180044296  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18004429b  nop
0x18004429c  lea     rdx, aIss; "iss"
0x1800442a3  lea     rcx, [rsp+140h+var_E0]
0x1800442a8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800442ad  nop
0x1800442ae  lea     r8, [rsp+140h+var_E8]
0x1800442b3  lea     rdx, [rsp+140h+var_E0]
0x1800442b8  lea     rcx, [rsp+140h+Block]
0x1800442bd  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800442c2  nop
0x1800442c3  mov     rcx, [rsp+140h+var_E0]
0x1800442c8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800442cc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800442d1  nop
0x1800442d2  mov     rcx, [rsp+140h+var_E8]
0x1800442d7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800442db  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800442e0  lea     rdx, aTenantId; "tenant_id"
0x1800442e7  lea     rcx, [rsp+140h+var_E8]
0x1800442ec  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800442f1  nop
0x1800442f2  lea     r8, [rbp+40h+var_A8]
0x1800442f6  lea     rdx, [rsp+140h+var_E8]
0x1800442fb  lea     rcx, [rsp+140h+Block]
0x180044300  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180044305  nop
0x180044306  mov     rcx, [rsp+140h+var_E8]
0x18004430b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004430f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180044314  lea     rdx, aDeviceAuth; "device_auth"
0x18004431b  lea     rcx, [rsp+140h+var_E0]
0x180044320  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180044325  nop
0x180044326  lea     rdx, aGrantType; "grant_type"
0x18004432d  lea     rcx, [rsp+140h+var_E8]
0x180044332  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180044337  nop
0x180044338  lea     r8, [rsp+140h+var_E0]
0x18004433d  lea     rdx, [rsp+140h+var_E8]
0x180044342  lea     rcx, [rsp+140h+Block]
0x180044347  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004434c  nop
0x18004434d  mov     rcx, [rsp+140h+var_E8]
0x180044352  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180044356  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004435b  nop
0x18004435c  mov     rcx, [rsp+140h+var_E0]
0x180044361  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180044365  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004436a  lea     rdx, a100295991000; "10.0.29599.1000"
0x180044371  lea     rcx, [rsp+140h+var_E0]
0x180044376  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18004437b  nop
0x18004437c  lea     rdx, aWinVer; "win_ver"
0x180044383  lea     rcx, [rsp+140h+var_E8]
0x180044388  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18004438d  nop
0x18004438e  lea     r8, [rsp+140h+var_E0]
0x180044393  lea     rdx, [rsp+140h+var_E8]
0x180044398  lea     rcx, [rsp+140h+Block]
0x18004439d  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800443a2  nop
0x1800443a3  mov     rcx, [rsp+140h+var_E8]
0x1800443a8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800443ac  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800443b1  nop
0x1800443b2  mov     rcx, [rsp+140h+var_E0]
0x1800443b7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800443bb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800443c0  lea     rdx, a201; "2.0.1"
0x1800443c7  lea     rcx, [rsp+140h+var_E0]
0x1800443cc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800443d1  nop
0x1800443d2  lea     rdx, aWindowsApiVers; "windows_api_version"
0x1800443d9  lea     rcx, [rsp+140h+var_E8]
0x1800443de  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800443e3  nop
0x1800443e4  lea     r8, [rsp+140h+var_E0]
0x1800443e9  lea     rdx, [rsp+140h+var_E8]
  ... truncated ...
```
