# GenericCallPackageHelper::CanCachedSSOCookieBeUsed(AadContextFunctions *,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,NonceLifetime const &,CachedNonce const &)

- ea: `0x180043180`
- end: `0x180043b2a`
- name: `?CanCachedSSOCookieBeUsed@GenericCallPackageHelper@@CA_NPEAVAadContextFunctions@@AEBVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBUNonceLifetime@@AEBUCachedNonce@@@Z`
- size: `2474`
- prototype: `bool __fastcall(AadContextFunctions *this, _QWORD *, _QWORD *, NonceLifetime *, CachedNonce *)`
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043ef4`
- `0x180044780`
- `0x180044ed8`

## callees

- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x1800090d0`
- `0x1800093e8`
- `0x18000a294`
- `0x18000a300`
- `0x18000c884`
- `0x180033180`
- `0x180041830`
- `0x180043180`
- `0x180049370`
- `0x180071e14`
- `0x180077b34`
- `0x180078a58`
- `0x18007a0fc`
- `0x18007a2a4`
- `0x18007a4a4`
- `0x18007adcc`

## string_xrefs

- `0x1800431b9`: `GenericCallPackageHelper::CanCachedSSOCookieBeUsed`
- `0x180043436`: `Cached SSO cookie has nonce`
- `0x180043575`: `Cached SSO cookie nonce is the same as nonce in URL`
- `0x1800434eb`: `Cached nonce is present`
- `0x18004364e`: `No valid cached nonce is present`
- `0x1800435e0`: `Cached SSO cookie has valid nonce`
- `0x180043891`: `Preferring cached SSO cookie with nonce over timestamp`
- `0x1800437f6`: `Cached SSO cookie timestamp is the same`
- `0x180043a5b`: `Cached SSO cookie timestamp is the same`
- `0x1800438d8`: `Cached SSO cookie nonce is the same`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall GenericCallPackageHelper::CanCachedSSOCookieBeUsed(
        AadContextFunctions *this,
        _QWORD *a2,
        _QWORD *a3,
        NonceLifetime *a4,
        CachedNonce *a5)
{
  bool IsValid; // r15
  int v9; // ebx
  int v10; // ebx
  __int64 v11; // rbx
  const wchar_t *v12; // r14
  const wchar_t *v13; // rax
  const wchar_t *v14; // rcx
  CachedNonce *v15; // r13
  bool IsEmpty; // al
  const wchar_t *v17; // rcx
  __int64 v18; // rdx
  bool v19; // zf
  int v20; // ecx
  int v21; // ebx
  int UnixEpochTime; // ebx
  ATL::CStringData *v23; // rcx
  __int64 v24; // rbx
  int v25; // edi
  int v26; // edi
  __int64 v28; // [rsp+28h] [rbp-E0h]
  int v29; // [rsp+38h] [rbp-D0h]
  int v30; // [rsp+38h] [rbp-D0h]
  __int64 v31; // [rsp+38h] [rbp-D0h]
  __int64 v32; // [rsp+38h] [rbp-D0h]
  __int64 v33; // [rsp+38h] [rbp-D0h]
  __int64 v34; // [rsp+38h] [rbp-D0h]
  __int64 v35; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+70h] [rbp-98h] BYREF
  __int64 v39; // [rsp+78h] [rbp-90h] BYREF
  __int64 v40; // [rsp+80h] [rbp-88h] BYREF
  struct CJsonObject *v41; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v42[8]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v43; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v44[56]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v45[56]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v46[56]; // [rsp+110h] [rbp+8h] BYREF
  unsigned int v47; // [rsp+178h] [rbp+70h] BYREF
  NonceLifetime *v48; // [rsp+190h] [rbp+88h]

  v48 = a4;
  v47 = 0;
  IsValid = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    v46,
    "genericcallpackagehelper.cpp",
    "GenericCallPackageHelper::CanCachedSSOCookieBeUsed",
    &v47);
  if ( this )
  {
    if ( !*(_DWORD *)(*a2 - 16LL) )
      goto LABEL_76;
    v41 = 0;
    CJsonValue::CJsonValue((CJsonValue *)v45);
    CJsonValue::CJsonValue((CJsonValue *)v44);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v36);
    v9 = StringUtility::StringFormat(&v37, L"{%s}", *a2);
    if ( v9 < 0 )
    {
      v29 = 2680;
LABEL_6:
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v9, "genericcallpackagehelper.cpp", v29, "HRESULT", &base);
      v47 = v9 & 0xAFFFFFFF | 0x40000000;
LABEL_75:
      CSecureString::~CSecureString((CSecureString *)&v36);
      CSecureString::~CSecureString((CSecureString *)&v37);
      CJsonValue::~CJsonValue((CJsonValue *)v44);
      CJsonValue::~CJsonValue((CJsonValue *)v45);
      goto LABEL_76;
    }
    v9 = WebResponseHelper::ParseJsonObject(&v37, v45, &v41);
    if ( v9 < 0 )
    {
      v29 = 2681;
      goto LABEL_6;
    }
    WebResponseHelper::GetJsonDataAsString(v41, L"assertion", &v36);
    if ( !*(_DWORD *)(v36 - 16) )
      goto LABEL_75;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v42);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v38);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v39);
    LODWORD(v35) = 0;
    v10 = WebResponseHelper::ParseJwt(this);
    if ( v10 < 0 )
    {
      v30 = 2691;
LABEL_12:
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v10, "genericcallpackagehelper.cpp", v30, "HRESULT", &base);
      v47 = v10 & 0xAFFFFFFF | 0x40000000;
LABEL_74:
      CSecureString::~CSecureString((CSecureString *)&v39);
      CSecureString::~CSecureString((CSecureString *)&v38);
      CSecureString::~CSecureString((CSecureString *)v42);
      goto LABEL_75;
    }
    if ( !*(_DWORD *)(v38 - 16) )
      goto LABEL_74;
    v10 = WebResponseHelper::ParseJsonObject(&v38, v44, &v41);
    if ( v10 < 0 )
    {
      v30 = 2695;
      goto LABEL_12;
    }
    WebResponseHelper::GetJsonDataAsString(v41, L"request_nonce", &v39);
    v11 = v39;
    v12 = L"Yes";
    v13 = L"Yes";
    if ( !*(_DWORD *)(v39 - 16) )
      v13 = L"No";
    WPPTraceLogA(
      4,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      4,
      0,
      "genericcallpackagehelper.cpp",
      2698,
      "Cached SSO cookie has nonce",
      v13);
    v14 = L"Yes";
    if ( !*(_DWORD *)(*a3 - 16LL) )
      v14 = L"No";
    LODWORD(v31) = 2699;
    WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "genericcallpackagehelper.cpp", v31, "URL has nonce", v14);
    v15 = a5;
    IsEmpty = CachedNonce::IsEmpty(a5);
    v17 = L"Yes";
    if ( IsEmpty )
      v17 = L"No";
    LODWORD(v32) = 2700;
    WPPTraceLogA(
      4,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      4,
      0,
      "genericcallpackagehelper.cpp",
      v32,
      "Cached nonce is present",
      v17);
    v19 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::__private_IsEnabled(
                             `wil::Feature<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::GetImpl'::`2'::impl,
                             v18) == 0;
    v20 = *(_DWORD *)(*a3 - 16LL);
    if ( v19 )
    {
      if ( *(_DWORD *)(v11 - 16) )
      {
        if ( !v20
          || (IsValid = 0,
              !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                               a3,
                               v11)) )
        {
          IsValid = 1;
        }
        if ( *(_DWORD *)(*a3 - 16LL) )
        {
          if ( !IsValid )
            v12 = L"No";
          LODWORD(v33) = 2802;
          WPPTraceLogA(
            4,
            0,
            "%x 0x%08x %s:%u : %s:%ws",
            4,
            0,
            "genericcallpackagehelper.cpp",
            v33,
            "Cached SSO cookie nonce is the same",
            v12);
          if ( !IsValid )
            goto LABEL_74;
LABEL_60:
          _InterlockedIncrement(&dword_1800E5E80);
          goto LABEL_74;
        }
        LODWORD(v33) = 2796;
        WPPTraceLogA(
          4,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          4,
          0,
          "genericcallpackagehelper.cpp",
          v33,
          "Preferring cached SSO cookie with nonce over timestamp",
          &base);
LABEL_35:
        _InterlockedIncrement(&dword_1800E5E88);
        goto LABEL_74;
      }
      if ( v20
        || !WebResponseHelper::IsJsonDataPresent(v41, L"iat", (enum CJsonValue::JsonValueType *)&v35)
        || (_DWORD)v35 != 3 )
      {
        goto LABEL_74;
      }
      v43 = 0;
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
      WebResponseHelper::GetJsonDataAsString(v41, L"iat", &v40);
      UnixEpochTime = GetUnixEpochTime(&v43);
      if ( UnixEpochTime < 0 )
      {
        LODWORD(v33) = 2818;
        goto LABEL_43;
      }
      UnixEpochTime = StringUtility::StringFormat(&v35, L"%lld", v43);
      if ( UnixEpochTime < 0 )
      {
        LODWORD(v33) = 2819;
        goto LABEL_43;
      }
      v24 = v40;
      v26 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
              &v35,
              v40);
      IsValid = v26 == 0;
      if ( v26 )
        v12 = L"No";
      LODWORD(v33) = 2821;
      WPPTraceLogA(
        4,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        4,
        0,
        "genericcallpackagehelper.cpp",
        v33,
        "Cached SSO cookie timestamp is the same",
        v12);
      if ( !v26 )
        _InterlockedIncrement(&dword_1800E5E84);
    }
    else
    {
      if ( *(_DWORD *)(v11 - 16) )
      {
        if ( v20 )
        {
          v21 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                  a3,
                  v11);
          IsValid = v21 == 0;
          if ( v21 )
            v12 = L"No";
          LODWORD(v33) = 2731;
          WPPTraceLogA(
            4,
            0,
            "%x 0x%08x %s:%u : %s:%ws",
            4,
            0,
            "genericcallpackagehelper.cpp",
            v33,
            "Cached SSO cookie nonce is the same as nonce in URL",
            v12);
          if ( v21 )
            goto LABEL_74;
          goto LABEL_60;
        }
        IsValid = NonceLifetime::IsValid(v48);
        if ( !IsValid )
          v12 = L"No";
        LODWORD(v33) = 2741;
        WPPTraceLogA(
          4,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          4,
          0,
          "genericcallpackagehelper.cpp",
          v33,
          "Cached SSO cookie has valid nonce",
          v12);
        if ( IsValid )
        {
          _InterlockedIncrement(&dword_1800E5E90);
          _InterlockedIncrement(&dword_1800E5E8C);
          goto LABEL_74;
        }
        if ( !CachedNonce::IsEmpty(v15) && NonceLifetime::IsValid((CachedNonce *)((char *)v15 + 8)) )
          goto LABEL_74;
        IsValid = 1;
        LODWORD(v34) = 2747;
        WPPTraceLogA(
          4,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          4,
          0,
          "genericcallpackagehelper.cpp",
          v34,
          "No valid cached nonce is present",
          &base);
        goto LABEL_35;
      }
      if ( v20
        || !CachedNonce::IsEmpty(v15)
        || !WebResponseHelper::IsJsonDataPresent(v41, L"iat", (enum CJsonValue::JsonValueType *)&v35)
        || (_DWORD)v35 != 3 )
      {
        goto LABEL_74;
      }
      v43 = 0;
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
      WebResponseHelper::GetJsonDataAsString(v41, L"iat", &v40);
      UnixEpochTime = GetUnixEpochTime(&v43);
      if ( UnixEpochTime < 0 )
      {
        LODWORD(v33) = 2773;
LABEL_43:
        LODWORD(v28) = UnixEpochTime;
        WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v28, "genericcallpackagehelper.cpp", v33, "HRESULT", &base);
        v47 = UnixEpochTime & 0xAFFFFFFF | 0x40000000;
        ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
        v23 = (ATL::CStringData *)(v40 - 24);
LABEL_73:
        ATL::CStringData::Release(v23);
        goto LABEL_74;
      }
      UnixEpochTime = StringUtility::StringFormat(&v35, L"%lld", v43);
      if ( UnixEpochTime < 0 )
      {
        LODWORD(v33) = 2774;
        goto LABEL_43;
      }
      v24 = v40;
      v25 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
              &v35,
              v40);
      IsValid = v25 == 0;
      if ( v25 )
        v12 = L"No";
      LODWORD(v33) = 2776;
      WPPTraceLogA(
        4,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        4,
        0,
        "genericcallpackagehelper.cpp",
        v33,
        "Cached SSO cookie timestamp is the same",
        v12);
      if ( !v25 )
        _InterlockedIncrement(&dword_1800E5E84);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
    v23 = (ATL::CStringData *)(v24 - 24);
    goto LABEL_73;
  }
  v47 = -1073741811;
  WPPTraceLogA(
    2,
    0,
    "%x 0x%08x %s:%u : %s:%ws",
    2,
    -1073741811,
    "genericcallpackagehelper.cpp",
    2670,
    "NTSTATUS",
    &base);
LABEL_76:
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v46);
  return IsValid;
}

```

## disassembly

```asm
0x180043180  mov     rax, rsp
0x180043183  mov     [rax+10h], rbx
0x180043187  mov     [rax+18h], rsi
0x18004318b  mov     [rax+20h], r9
0x18004318f  push    rbp
0x180043190  push    rdi
0x180043191  push    r13
0x180043193  push    r14
0x180043195  push    r15
0x180043197  lea     rbp, [rax-68h]
0x18004319b  sub     rsp, 140h
0x1800431a2  mov     rdi, r8
0x1800431a5  mov     rbx, rdx
0x1800431a8  mov     rsi, rcx
0x1800431ab  xor     r13d, r13d
0x1800431ae  mov     [rbp+60h+arg_0], r13d
0x1800431b2  mov     r15b, r13b
0x1800431b5  lea     r9, [rbp+60h+arg_0]
0x1800431b9  lea     r8, aGenericcallpac_7; "GenericCallPackageHelper::CanCachedSSOC"...
0x1800431c0  lea     r14, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x1800431c7  mov     rdx, r14
0x1800431ca  lea     rcx, [rbp+60h+var_58]
0x1800431ce  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x1800431d3  nop
0x1800431d4  test    rsi, rsi
0x1800431d7  jnz     short loc_180043223
0x1800431d9  mov     ecx, 0C000000Dh
0x1800431de  mov     [rbp+60h+arg_0], ecx
0x1800431e1  lea     rax, base
0x1800431e8  mov     [rsp+160h+var_120], rax
0x1800431ed  lea     rax, aNtstatus; "NTSTATUS"
0x1800431f4  mov     [rsp+160h+var_128], rax
0x1800431f9  mov     dword ptr [rsp+160h+var_130], 0A6Eh
0x180043201  mov     qword ptr [rsp+160h+var_138], r14
0x180043206  mov     dword ptr [rsp+160h+var_140], ecx
0x18004320a  lea     ecx, [rsi+2]
0x18004320d  mov     r9d, ecx
0x180043210  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180043217  xor     edx, edx
0x180043219  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004321e  jmp     loc_180043B02
0x180043223  mov     rax, [rbx]
0x180043226  cmp     [rax-10h], r13d
0x18004322a  jz      loc_180043B02
0x180043230  mov     [rbp+60h+var_E0], r13
0x180043234  lea     rcx, [rbp+60h+var_90]; this
0x180043238  call    ??0CJsonValue@@QEAA@XZ; CJsonValue::CJsonValue(void)
0x18004323d  nop
0x18004323e  lea     rcx, [rbp+60h+var_C8]; this
0x180043242  call    ??0CJsonValue@@QEAA@XZ; CJsonValue::CJsonValue(void)
0x180043247  nop
0x180043248  lea     rcx, [rsp+160h+var_100]; void *
0x18004324d  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180043252  nop
0x180043253  lea     rcx, [rsp+160h+var_108]; void *
0x180043258  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004325d  nop
0x18004325e  mov     r8, [rbx]
0x180043261  lea     rdx, aS_3; "{%s}"
0x180043268  lea     rcx, [rsp+160h+var_100]
0x18004326d  call    ?StringFormat@StringUtility@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGZZ; StringUtility::StringFormat(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,...)
0x180043272  mov     ebx, eax
0x180043274  test    eax, eax
0x180043276  jns     short loc_1800432C7
0x180043278  lea     rax, base
0x18004327f  mov     [rsp+160h+var_120], rax
0x180043284  lea     rax, aHresult; "HRESULT"
0x18004328b  mov     [rsp+160h+var_128], rax
0x180043290  mov     dword ptr [rsp+160h+var_130], 0A78h
0x180043298  mov     qword ptr [rsp+160h+var_138], r14
0x18004329d  mov     dword ptr [rsp+160h+var_140], ebx
0x1800432a1  mov     ecx, 2
0x1800432a6  mov     r9d, ecx
0x1800432a9  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800432b0  xor     edx, edx
0x1800432b2  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800432b7  btr     ebx, 1Ch
0x1800432bb  bts     ebx, 1Eh
0x1800432bf  mov     [rbp+60h+arg_0], ebx
0x1800432c2  jmp     loc_180043AD8
0x1800432c7  lea     r8, [rbp+60h+var_E0]
0x1800432cb  lea     rdx, [rbp+60h+var_90]
0x1800432cf  lea     rcx, [rsp+160h+var_100]
0x1800432d4  call    ?ParseJsonObject@WebResponseHelper@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCJsonValue@@PEAPEAVCJsonObject@@@Z; WebResponseHelper::ParseJsonObject(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CJsonValue *,CJsonObject * *)
0x1800432d9  mov     ebx, eax
0x1800432db  test    eax, eax
0x1800432dd  jns     short loc_180043301
0x1800432df  lea     rax, base
0x1800432e6  mov     [rsp+160h+var_120], rax
0x1800432eb  lea     rax, aHresult; "HRESULT"
0x1800432f2  mov     [rsp+160h+var_128], rax
0x1800432f7  mov     dword ptr [rsp+160h+var_130], 0A79h
0x1800432ff  jmp     short loc_180043298
0x180043301  lea     r8, [rsp+160h+var_108]
0x180043306  lea     rdx, aAssertion; "assertion"
0x18004330d  mov     rcx, [rbp+60h+var_E0]
0x180043311  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180043316  mov     rax, [rsp+160h+var_108]
0x18004331b  cmp     [rax-10h], r13d
0x18004331f  jz      loc_180043AD8
0x180043325  lea     rcx, [rbp+60h+var_D8]; void *
0x180043329  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004332e  nop
0x18004332f  lea     rcx, [rsp+160h+var_F8]; void *
0x180043334  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180043339  nop
0x18004333a  lea     rcx, [rsp+160h+var_F0]; void *
0x18004333f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180043344  nop
0x180043345  mov     dword ptr [rsp+160h+var_110], r13d
0x18004334a  lea     r9, [rsp+160h+var_F8]
0x18004334f  lea     r8, [rbp+60h+var_D8]
0x180043353  lea     rdx, [rsp+160h+var_108]
0x180043358  mov     rcx, rsi; this
0x18004335b  call    ?ParseJwt@WebResponseHelper@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@2@Z; WebResponseHelper::ParseJwt(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180043360  mov     ebx, eax
0x180043362  test    eax, eax
0x180043364  jns     short loc_1800433B5
0x180043366  lea     rax, base
0x18004336d  mov     [rsp+160h+var_120], rax
0x180043372  lea     rax, aHresult; "HRESULT"
0x180043379  mov     [rsp+160h+var_128], rax
0x18004337e  mov     dword ptr [rsp+160h+var_130], 0A83h
0x180043386  mov     qword ptr [rsp+160h+var_138], r14
0x18004338b  mov     dword ptr [rsp+160h+var_140], ebx
0x18004338f  mov     ecx, 2
0x180043394  mov     r9d, ecx
0x180043397  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004339e  xor     edx, edx
0x1800433a0  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800433a5  btr     ebx, 1Ch
0x1800433a9  bts     ebx, 1Eh
0x1800433ad  mov     [rbp+60h+arg_0], ebx
0x1800433b0  jmp     loc_180043AB8
0x1800433b5  mov     rax, [rsp+160h+var_F8]
0x1800433ba  cmp     [rax-10h], r13d
0x1800433be  jz      loc_180043AB8
0x1800433c4  lea     r8, [rbp+60h+var_E0]
0x1800433c8  lea     rdx, [rbp+60h+var_C8]
0x1800433cc  lea     rcx, [rsp+160h+var_F8]
0x1800433d1  call    ?ParseJsonObject@WebResponseHelper@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCJsonValue@@PEAPEAVCJsonObject@@@Z; WebResponseHelper::ParseJsonObject(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CJsonValue *,CJsonObject * *)
0x1800433d6  mov     ebx, eax
0x1800433d8  test    eax, eax
0x1800433da  jns     short loc_1800433FE
0x1800433dc  lea     rax, base
0x1800433e3  mov     [rsp+160h+var_120], rax
0x1800433e8  lea     rax, aHresult; "HRESULT"
0x1800433ef  mov     [rsp+160h+var_128], rax
0x1800433f4  mov     dword ptr [rsp+160h+var_130], 0A87h
0x1800433fc  jmp     short loc_180043386
0x1800433fe  lea     r8, [rsp+160h+var_F0]
0x180043403  lea     rdx, aRequestNonce; "request_nonce"
0x18004340a  mov     rcx, [rbp+60h+var_E0]
0x18004340e  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180043413  mov     rbx, [rsp+160h+var_F0]
0x180043418  lea     rcx, aNo; "No"
0x18004341f  lea     r14, aYes; "Yes"
0x180043426  mov     rax, r14
0x180043429  cmp     [rbx-10h], r13d
0x18004342d  cmovz   rax, rcx
0x180043431  mov     [rsp+160h+var_120], rax
0x180043436  lea     rax, aCachedSsoCooki; "Cached SSO cookie has nonce"
0x18004343d  mov     [rsp+160h+var_128], rax
0x180043442  mov     dword ptr [rsp+160h+var_130], 0A8Ah
0x18004344a  lea     rax, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x180043451  mov     qword ptr [rsp+160h+var_138], rax
0x180043456  mov     [rsp+160h+var_140], r13
0x18004345b  mov     eax, 4
0x180043460  mov     r9d, eax
0x180043463  lea     rsi, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004346a  mov     r8, rsi
0x18004346d  xor     edx, edx
0x18004346f  mov     ecx, eax
0x180043471  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180043476  mov     rax, [rdi]
0x180043479  mov     rcx, r14
0x18004347c  cmp     [rax-10h], r13d
0x180043480  lea     rax, aNo; "No"
0x180043487  cmovz   rcx, rax
0x18004348b  mov     [rsp+160h+var_120], rcx
0x180043490  lea     rax, aUrlHasNonce; "URL has nonce"
0x180043497  mov     [rsp+160h+var_128], rax
0x18004349c  mov     dword ptr [rsp+160h+var_130], 0A8Bh
0x1800434a4  lea     rax, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x1800434ab  mov     qword ptr [rsp+160h+var_138], rax
0x1800434b0  mov     [rsp+160h+var_140], r13
0x1800434b5  mov     ecx, 4
0x1800434ba  mov     r9d, ecx
0x1800434bd  mov     r8, rsi
0x1800434c0  xor     edx, edx
0x1800434c2  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800434c7  mov     r13, [rbp+60h+arg_20]
0x1800434ce  mov     rcx, r13; this
0x1800434d1  call    ?IsEmpty@CachedNonce@@QEBA_NXZ; CachedNonce::IsEmpty(void)
0x1800434d6  mov     rcx, r14
0x1800434d9  test    al, al
0x1800434db  lea     rax, aNo; "No"
0x1800434e2  cmovnz  rcx, rax
0x1800434e6  mov     [rsp+160h+var_120], rcx
0x1800434eb  lea     rax, aCachedNonceIsP; "Cached nonce is present"
0x1800434f2  mov     [rsp+160h+var_128], rax
0x1800434f7  mov     dword ptr [rsp+160h+var_130], 0A8Ch
0x1800434ff  lea     rax, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x180043506  mov     qword ptr [rsp+160h+var_138], rax
0x18004350b  mov     [rsp+160h+var_140], 0
0x180043514  mov     eax, 4
0x180043519  mov     r9d, eax
0x18004351c  mov     r8, rsi
0x18004351f  xor     edx, edx
0x180043521  mov     ecx, eax
0x180043523  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180043528  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BrowserSSONonceCaching@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BrowserSSONonceCaching@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserSSONonceCaching> `wil::Feature<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::GetImpl(void)'::`2'::impl
0x18004352f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BrowserSSONonceCaching@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::__private_IsEnabled(void)
0x180043534  test    al, al
0x180043536  mov     rax, [rdi]
0x180043539  mov     ecx, [rax-10h]
0x18004353c  jz      loc_180043852
0x180043542  cmp     dword ptr [rbx-10h], 0
0x180043546  jz      loc_18004369E
0x18004354c  test    ecx, ecx
0x18004354e  jz      short loc_1800435BF
0x180043550  mov     rdx, rbx
0x180043553  mov     rcx, rdi
0x180043556  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x18004355b  mov     ebx, eax
0x18004355d  test    eax, eax
0x18004355f  setz    r15b
0x180043563  test    eax, eax
0x180043565  lea     rax, aNo; "No"
0x18004356c  cmovnz  r14, rax
0x180043570  mov     [rsp+160h+var_120], r14
0x180043575  lea     rax, aCachedSsoCooki_0; "Cached SSO cookie nonce is the same as "...
0x18004357c  mov     [rsp+160h+var_128], rax
0x180043581  mov     dword ptr [rsp+160h+var_130], 0AABh
0x180043589  lea     rax, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x180043590  mov     qword ptr [rsp+160h+var_138], rax
0x180043595  mov     [rsp+160h+var_140], 0
0x18004359e  mov     eax, 4
0x1800435a3  mov     r9d, eax
0x1800435a6  mov     r8, rsi
0x1800435a9  xor     edx, edx
0x1800435ab  mov     ecx, eax
0x1800435ad  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800435b2  test    ebx, ebx
0x1800435b4  jnz     loc_180043AB8
0x1800435ba  jmp     loc_180043917
0x1800435bf  mov     rcx, [rbp+60h+arg_18]; this
0x1800435c6  call    ?IsValid@NonceLifetime@@QEBA_NXZ; NonceLifetime::IsValid(void)
0x1800435cb  mov     r15b, al
0x1800435ce  test    al, al
0x1800435d0  lea     rax, aNo; "No"
0x1800435d7  cmovz   r14, rax
0x1800435db  mov     [rsp+160h+var_120], r14
0x1800435e0  lea     rax, aCachedSsoCooki_1; "Cached SSO cookie has valid nonce"
0x1800435e7  mov     [rsp+160h+var_128], rax
0x1800435ec  mov     dword ptr [rsp+160h+var_130], 0AB5h
0x1800435f4  lea     rbx, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x1800435fb  mov     qword ptr [rsp+160h+var_138], rbx
0x180043600  mov     [rsp+160h+var_140], 0
0x180043609  mov     edi, 4
0x18004360e  mov     r9d, edi
0x180043611  mov     r8, rsi
0x180043614  xor     edx, edx
0x180043616  mov     ecx, edi
0x180043618  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004361d  test    r15b, r15b
0x180043620  jnz     short loc_18004368B
0x180043622  mov     rcx, r13; this
0x180043625  call    ?IsEmpty@CachedNonce@@QEBA_NXZ; CachedNonce::IsEmpty(void)
0x18004362a  test    al, al
0x18004362c  jnz     short loc_18004363F
0x18004362e  lea     rcx, [r13+8]; this
0x180043632  call    ?IsValid@NonceLifetime@@QEBA_NXZ; NonceLifetime::IsValid(void)
0x180043637  test    al, al
0x180043639  jnz     loc_180043AB8
0x18004363f  mov     r15b, 1
0x180043642  lea     rax, base
0x180043649  mov     [rsp+160h+var_120], rax
0x18004364e  lea     rax, aNoValidCachedN; "No valid cached nonce is present"
0x180043655  mov     [rsp+160h+var_128], rax
0x18004365a  mov     dword ptr [rsp+160h+var_130], 0ABBh
0x180043662  mov     qword ptr [rsp+160h+var_138], rbx
0x180043667  mov     [rsp+160h+var_140], 0
0x180043670  mov     r9d, edi
0x180043673  mov     r8, rsi
0x180043676  mov     ecx, edi
0x180043678  xor     edx, edx
0x18004367a  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004367f  lock inc cs:dword_1800E5E88
0x180043686  jmp     loc_180043AB8
0x18004368b  lock inc cs:dword_1800E5E90
0x180043692  lock inc cs:dword_1800E5E8C
0x180043699  jmp     loc_180043AB8
0x18004369e  test    ecx, ecx
0x1800436a0  jnz     loc_180043AB8
0x1800436a6  mov     rcx, r13; this
0x1800436a9  call    ?IsEmpty@CachedNonce@@QEBA_NXZ; CachedNonce::IsEmpty(void)
0x1800436ae  test    al, al
0x1800436b0  jz      loc_180043AB8
0x1800436b6  lea     r8, [rsp+160h+var_110]; enum CJsonValue::JsonValueType *
  ... truncated ...
```
