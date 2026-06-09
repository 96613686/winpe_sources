# RefreshTokenRequest::BuildPrtAssertion(bool,CSecureString &)

- ea: `0x180061288`
- end: `0x180062244`
- name: `?BuildPrtAssertion@RefreshTokenRequest@@AEAAJ_NAEAVCSecureString@@@Z`
- size: `4028`
- prototype: `__int64 __fastcall(RefreshTokenRequest *__hidden this, bool, struct CSecureString *)`
- caller_count: `2`
- callee_count: `34`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180062250`
- `0x180062880`

## callees

- `0x180006380`
- `0x1800065e8`
- `0x1800067f4`
- `0x180006e0c`
- `0x180007d7c`
- `0x1800090d0`
- `0x18000a300`
- `0x18000aa74`
- `0x180020974`
- `0x180028760`
- `0x18003345c`
- `0x180043050`
- `0x180049554`
- `0x180059a38`
- `0x180061288`
- `0x180062664`
- `0x180071e14`
- `0x1800765b0`
- `0x18007699c`
- `0x180076c3c`
- `0x180076f14`
- `0x180077b34`
- `0x180078a58`
- `0x180078b18`
- `0x1800794f0`
- `0x1800795d0`
- `0x180079d2c`
- `0x18007efac`
- `0x18007f130`
- `0x1800a2d64`
- `0x1800a2d94`
- `0x1800a2e9c`
- `0x1800a3520`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180062172`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180062187`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800621d3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800621e7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180062172`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180062187`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800621d3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800621e7`
- `popkeycli!NgcSignWithSymmetricPopKey` at `0x180061f89`
- `popkeycli!NgcSignWithSymmetricPopKey` at `0x180061f89`

## string_xrefs

- `0x18006149a`: `refresh_token`
- `0x1800617db`: `refresh_token`
- `0x180061438`: `aad:brokerplugin`
- `0x180061a32`: `previous_refresh_token`
- `0x180061877`: `cert_token_use`
- `0x1800618c5`: `http://schemas.microsoft.com/windows/pki/2009/01/enrollment#PKCS10`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall RefreshTokenRequest::BuildPrtAssertion(RefreshTokenRequest *this, char a2, struct CSecureString *a3)
{
  int UnixEpochTime; // edi
  char v7; // bl
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // rcx
  struct _AP_BLOB *v12; // rcx
  struct AadContextFunctions *v13; // rax
  RefreshTokenRequest *v14; // rcx
  struct _AP_BLOB *SeedLabel; // r14
  struct AadContextFunctions *v16; // rax
  int v17; // eax
  __int64 v18; // rcx
  char *v19; // rcx
  int i; // esi
  char *v21; // rcx
  int j; // esi
  __int64 v24; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+20h] [rbp-E0h]
  __int64 v26; // [rsp+20h] [rbp-E0h]
  __int64 v27; // [rsp+30h] [rbp-D0h]
  int v28; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+30h] [rbp-D0h]
  __int64 v30; // [rsp+30h] [rbp-D0h]
  void *Block[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+60h] [rbp-A0h]
  __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h]
  void *v35[2]; // [rsp+78h] [rbp-88h] BYREF
  int v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v38[8]; // [rsp+98h] [rbp-68h] BYREF
  int v39; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-58h]
  __int64 v41; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v42[8]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v43[8]; // [rsp+C0h] [rbp-40h] BYREF
  int v44; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v45; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v46; // [rsp+D8h] [rbp-28h] BYREF
  int v47; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v48; // [rsp+E8h] [rbp-18h]
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v50; // [rsp+158h] [rbp+58h]
  __int64 v51; // [rsp+190h] [rbp+90h] BYREF
  __int64 v52; // [rsp+1A8h] [rbp+A8h] BYREF

  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v43);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v42);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v38);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v41);
  *(_OWORD *)v35 = 0;
  v36 = 0;
  *(_OWORD *)Block = 0;
  v32 = 0;
  v45 = 0;
  v44 = 0;
  v48 = 0;
  v47 = 0;
  v40 = 0;
  v39 = 0;
  ATL::CSimpleStringT<unsigned short,0>::Empty(a3);
  if ( !*((_QWORD *)this + 9) )
  {
    UnixEpochTime = -2147024809;
    LODWORD(v27) = 109;
LABEL_62:
    LODWORD(v24) = UnixEpochTime;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v24, "refreshtokenrequest.cpp", v27, "HRESULT", &base);
    goto LABEL_63;
  }
  UnixEpochTime = StringUtility::DecodeBytes(*(LPCCH *)(*((_QWORD *)this + 25) + 8LL), **((_DWORD **)this + 25));
  if ( UnixEpochTime < 0 )
  {
    LODWORD(v27) = 113;
    goto LABEL_62;
  }
  Url::Url((Url *)&UrlComponents);
  (*(void (__fastcall **)(RefreshTokenRequest *, __int64 *))(*(_QWORD *)this + 24LL))(this, &v51);
  v7 = Url::TryCreate(&UrlComponents);
  ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  if ( !v7 )
  {
    UnixEpochTime = -2147187643;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -2147187643, "refreshtokenrequest.cpp", 121, "HRESULT", &base);
LABEL_7:
    v8 = v50;
LABEL_8:
    ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
    goto LABEL_63;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v52,
    (__int64)L"aad:brokerplugin");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v51,
    (__int64)L"iss");
  KeyValueList::Add((__int64)Block, (__int64)&v51, (__int64)&v52);
  ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v52,
    (__int64)L"refresh_token");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v51,
    (__int64)L"grant_type");
  KeyValueList::Add((__int64)Block, (__int64)&v51, (__int64)&v52);
  ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
  v9 = Url::Host(&UrlComponents, &v52);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v51,
    (__int64)L"aud");
  KeyValueList::Add((__int64)Block, (__int64)&v51, v9);
  ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
  if ( *(_DWORD *)(*((_QWORD *)this + 17) - 16LL) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v51,
      (__int64)L"resource");
    KeyValueList::Add((__int64)Block, (__int64)&v51, (__int64)this + 136);
    ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 19) - 16LL) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v51,
      (__int64)L"request_nonce");
    KeyValueList::Add((__int64)Block, (__int64)&v51, (__int64)this + 152);
    v11 = v51;
  }
  else
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
    v46 = 0;
    UnixEpochTime = GetUnixEpochTime(&v46);
    if ( UnixEpochTime < 0 )
    {
      v28 = 138;
LABEL_14:
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, UnixEpochTime, "refreshtokenrequest.cpp", v28, "HRESULT", &base);
      ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
      goto LABEL_7;
    }
    v10 = v46 + 600;
    UnixEpochTime = StringUtility::StringFormat(&v52, L"%lld");
    if ( UnixEpochTime < 0 )
    {
      v28 = 140;
      goto LABEL_14;
    }
    UnixEpochTime = StringUtility::StringFormat(&v51, L"%lld", v10);
    if ( UnixEpochTime < 0 )
    {
      v28 = 141;
      goto LABEL_14;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v33,
      (__int64)L"iat");
    KeyValueList::Add((__int64)Block, (__int64)&v33, (__int64)&v52);
    ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v33,
      (__int64)L"exp");
    KeyValueList::Add((__int64)Block, (__int64)&v33, (__int64)&v51);
    ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
    v11 = v52;
  }
  ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v51,
    (__int64)L"scope");
  KeyValueList::Add((__int64)Block, (__int64)&v51, (__int64)this + 160);
  ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v51,
    (__int64)L"refresh_token");
  KeyValueList::Add((__int64)Block, (__int64)&v51, (__int64)v43);
  ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v51,
    (__int64)L"client_id");
  KeyValueList::Add((__int64)Block, (__int64)&v51, (__int64)this + 144);
  ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  if ( *(_DWORD *)(*((_QWORD *)this + 26) - 16LL) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v52,
      (__int64)L"user_cert");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v51,
      (__int64)L"cert_token_use");
    KeyValueList::Add((__int64)Block, (__int64)&v51, (__int64)&v52);
    ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v52,
      (__int64)L"http://schemas.microsoft.com/windows/pki/2009/01/enrollment#PKCS10");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v51,
      (__int64)L"csr_type");
    KeyValueList::Add((__int64)Block, (__int64)&v51, (__int64)&v52);
    ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v52,
      *((_QWORD *)this + 26));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v51,
      (__int64)L"csr");
    KeyValueList::Add((__int64)Block, (__int64)&v51, (__int64)&v52);
    ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
  }
  if ( a2 )
  {
    if ( IsApBlobDefined(*((struct _AP_BLOB **)this + 21)) )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
      UnixEpochTime = StringUtility::DecodeBytes(*(LPCCH *)(*((_QWORD *)this + 21) + 8LL), **((_DWORD **)this + 21));
      if ( UnixEpochTime < 0 )
      {
        WPPTraceLogA(
          2,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          2,
          UnixEpochTime,
          "refreshtokenrequest.cpp",
          167,
          "HRESULT",
          &base);
LABEL_27:
        CSecureString::~CSecureString((CSecureString *)&v51);
        goto LABEL_7;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v52,
        (__int64)L"previous_refresh_token");
      KeyValueList::Add((__int64)Block, (__int64)&v52, (__int64)&v51);
      ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
      CSecureString::~CSecureString((CSecureString *)&v51);
    }
    v12 = (struct _AP_BLOB *)*((_QWORD *)this + 10);
    if ( v12 && IsApBlobDefined(v12) )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
      UnixEpochTime = StringUtility::Base64Encode(*((_QWORD *)this + 10), &v51);
      if ( UnixEpochTime < 0 )
      {
        WPPTraceLogA(
          2,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          2,
          UnixEpochTime,
          "refreshtokenrequest.cpp",
          177,
          "HRESULT",
          &base);
        goto LABEL_27;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v52,
        (__int64)L"vsm_binding_key");
      KeyValueList::Add((__int64)Block, (__int64)&v52, (__int64)&v51);
      ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
      CSecureString::~CSecureString((CSecureString *)&v51);
    }
  }
  OAuthTokenRequest::AddSecurityGroups(this, (struct KeyValueList *)Block);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v52,
    (__int64)L"10.0.29599.1000");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v51,
    (__int64)L"win_ver");
  KeyValueList::Add((__int64)Block, (__int64)&v51, (__int64)&v52);
  ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
  WebResponseHelper::FormatJson(Block, v38);
  ATL::CStringData::Release((ATL::CStringData *)(v50 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v52,
    (__int64)L"HS256");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v51,
    (__int64)L"alg");
  KeyValueList::Add((__int64)v35, (__int64)&v51, (__int64)&v52);
  ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
  if ( !wcscmp_0(*(const wchar_t **)(*((_QWORD *)this + 9) + 8LL), L"ngc") )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
    if ( (*((_BYTE *)this + 56) & 0x40) != 0 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v52,
        (__int64)L"kdf_ver");
      KeyValueList::Add(v35, &v52, 2);
      ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
      v13 = PluginContextHelper::Context();
      UnixEpochTime = GenerateKdfVector(
                        v13,
                        (struct CSecureString *)v38,
                        (struct _AP_BLOB *)&v39,
                        (struct _AP_BLOB *)&v47);
      if ( UnixEpochTime < 0 )
      {
        v29 = 200;
LABEL_38:
        WPPTraceLogA(
          2,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          2,
          UnixEpochTime,
          "refreshtokenrequest.cpp",
          v29,
          "HRESULT",
          &base);
        v8 = v51;
        goto LABEL_8;
      }
      UnixEpochTime = StringUtility::Base64Encode(&v47, &v51);
      if ( UnixEpochTime < 0 )
      {
        v29 = 201;
        goto LABEL_38;
      }
    }
    else
    {
      UnixEpochTime = LocalApBlob::Allocate((LocalApBlob *)&v39, 0x18u);
      if ( UnixEpochTime < 0 )
      {
        v29 = 205;
        goto LABEL_38;
      }
      UnixEpochTime = CryptoHelper::GenRandom((struct _AP_BLOB *)&v39);
      if ( UnixEpochTime < 0 )
      {
        v29 = 206;
        goto LABEL_38;
      }
      UnixEpochTime = StringUtility::Base64Encode(&v39, &v51);
      if ( UnixEpochTime < 0 )
      {
        v29 = 207;
        goto LABEL_38;
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v52,
      (__int64)L"ctx");
    KeyValueList::Add((__int64)v35, (__int64)&v52, (__int64)&v51);
    ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  }
  WebResponseHelper::FormatJson(v35, v42);
  UnixEpochTime = RefreshTokenRequest::ConstructSigningInput(
                    v14,
                    (const struct CSecureString *)v42,
                    (const struct CSecureString *)v38,
                    (struct CSecureString *)&v37);
  if ( UnixEpochTime < 0 )
  {
    LODWORD(v27) = 216;
    goto LABEL_62;
  }
  if ( wcscmp_0(*(const wchar_t **)(*((_QWORD *)this + 9) + 8LL), L"ngc") )
  {
    UnixEpochTime = -2147187642;
    LODWORD(v27) = 251;
    goto LABEL_62;
  }
  v34 = 0;
  LODWORD(v33) = 0;
  SeedLabel = CryptoHelper::GetSeedLabel();
  v16 = PluginContextHelper::Context();
  UnixEpochTime = StringUtility::EncodeString(v16, &v37, &v33, 65001, 1);
  if ( UnixEpochTime < 0 )
  {
    LODWORD(v25) = UnixEpochTime;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v25, "refreshtokenrequest.cpp", 225, "HRESULT", &base);
    PluginLocalFreeApBlob((struct _AP_BLOB *)&v33);
    goto LABEL_63;
  }
  v17 = NgcSignWithSymmetricPopKey(
          *(_QWORD *)(*((_QWORD *)this + 9) + 32LL),
          *(unsigned int *)(*((_QWORD *)this + 9) + 24LL),
          *((_QWORD *)SeedLabel + 1),
          *(unsigned int *)SeedLabel,
          v40,
          v39,
          v34,
          v33,
          &v45,
          &v44);
  UnixEpochTime = v17;
  if ( v17 >= 0 )
  {
    PluginLocalFreeApBlob((struct _AP_BLOB *)&v33);
    UnixEpochTime = StringUtility::Base64UrlEncode(&v44, &v41);
    if ( UnixEpochTime >= 0 )
    {
      UnixEpochTime = StringUtility::StringFormat(a3, L"%s.%s", v37, v41);
      if ( UnixEpochTime >= 0 )
        goto LABEL_63;
      LODWORD(v27) = 256;
    }
    else
    {
      LODWORD(v27) = 254;
    }
    goto LABEL_62;
  }
  *((_DWORD *)this + 11) = v17;
  WPPTraceLogA(
    2,
    0,
    "%x 0x%08x %s:%u : %s:%u",
    2,
    0,
    "refreshtokenrequest.cpp",
    244,
    "NgcSignWithSymmetricPopKey failed",
    v17);
  if ( (Microsoft_Windows_AADEnableBits & 4) != 0 )
    McTemplateU0zd_EventWriteTransfer(
      v18,
      Aad_CloudAPPlugin_NGC_Error,
      L"NgcSignWithSymmetricPopKey",
      (unsigned int)UnixEpochTime);
  LODWORD(v30) = 246;
  LODWORD(v26) = UnixEpochTime;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v26, "refreshtokenrequest.cpp", v30, "HRESULT", &base);
  PluginLocalFreeApBlob((struct _AP_BLOB *)&v33);
LABEL_63:
  LocalApBlob::ReleaseExternal((LocalApBlob *)&v44);
  PluginLocalFreeApBlob((struct _AP_BLOB *)&v39);
  PluginLocalFreeApBlob((struct _AP_BLOB *)&v47);
  PluginLocalFreeApBlob((struct _AP_BLOB *)&v44);
  v19 = (char *)Block[0];
  if ( Block[0] )
  {
    for ( i = 0; i < v32; v19 = (char *)Block[0] )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::`scalar deleting destructor'(&v19[8 * i]);
      KeyListValue::~KeyListValue((KeyListValue *)((char *)Block[1] + 72 * i++));
    }
    free(v19);
    Block[0] = 0;
  }
  if ( Block[1] )
  {
    free(Block[1]);
    Block[1] = 0;
  }
  v32 = 0;
  v21 = (char *)v35[0];
  if ( v35[0] )
  {
    for ( j = 0; j < v36; v21 = (char *)v35[0] )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::`scalar deleting destructor'(&v21[8 * j]);
      KeyListValue::~KeyListValue((KeyListValue *)((char *)v35[1] + 72 * j++));
    }
    free(v21);
    v35[0] = 0;
  }
  if ( v35[1] )
  {
    free(v35[1]);
    v35[1] = 0;
  }
  v36 = 0;
  CSecureString::~CSecureString((CSecureString *)&v41);
  CSecureString::~CSecureString((CSecureString *)&v37);
  CSecureString::~CSecureString((CSecureString *)v38);
  CSecureString::~CSecureString((CSecureString *)v42);
  CSecureString::~CSecureString((CSecureString *)v43);
  return (unsigned int)UnixEpochTime;
}

```

## disassembly

```asm
0x180061288  mov     [rsp-8+arg_8], rbx
0x18006128d  mov     [rsp-8+arg_10], rsi
0x180061292  push    rbp
0x180061293  push    rdi
0x180061294  push    r12
0x180061296  push    r14
0x180061298  push    r15
0x18006129a  lea     rbp, [rsp-60h]
0x18006129f  sub     rsp, 160h
0x1800612a6  mov     r15, r8
0x1800612a9  mov     r14b, dl
0x1800612ac  mov     rsi, rcx
0x1800612af  lea     rcx, [rbp+80h+var_C0]; void *
0x1800612b3  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800612b8  nop
0x1800612b9  lea     rcx, [rbp+80h+var_C8]; void *
0x1800612bd  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800612c2  nop
0x1800612c3  lea     rcx, [rbp+80h+var_E8]; void *
0x1800612c7  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800612cc  nop
0x1800612cd  lea     rcx, [rbp+80h+var_F0]; void *
0x1800612d1  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800612d6  nop
0x1800612d7  lea     rcx, [rbp+80h+var_D0]; void *
0x1800612db  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800612e0  nop
0x1800612e1  xorps   xmm0, xmm0
0x1800612e4  movdqu  xmmword ptr [rsp+180h+var_108], xmm0
0x1800612ea  xor     r12d, r12d
0x1800612ed  mov     [rbp+80h+var_F8], r12d
0x1800612f1  movdqu  xmmword ptr [rsp+180h+Block], xmm0
0x1800612f7  mov     [rsp+180h+var_120], r12d
0x1800612fc  mov     [rbp+80h+var_B0], r12
0x180061300  mov     [rbp+80h+var_B8], r12d
0x180061304  mov     [rbp+80h+var_98], r12
0x180061308  mov     [rbp+80h+var_A0], r12d
0x18006130c  mov     [rbp+80h+var_D8], r12
0x180061310  mov     [rbp+80h+var_E0], r12d
0x180061314  mov     rcx, r15
0x180061317  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18006131c  cmp     [rsi+48h], r12
0x180061320  jnz     short loc_180061351
0x180061322  mov     edi, 80070057h
0x180061327  lea     rax, base
0x18006132e  mov     [rsp+180h+var_140], rax
0x180061333  lea     rax, aHresult; "HRESULT"
0x18006133a  mov     [rsp+180h+var_148], rax
0x18006133f  mov     dword ptr [rsp+180h+var_150], 6Dh ; 'm'
0x180061347  mov     ebx, 2
0x18006134c  jmp     loc_1800620E8
0x180061351  mov     rcx, [rsi+0C8h]
0x180061358  mov     r9d, 0FDE9h
0x18006135e  lea     r8, [rbp+80h+var_C0]
0x180061362  mov     edx, [rcx]; cbMultiByte
0x180061364  mov     rcx, [rcx+8]; lpMultiByteStr
0x180061368  call    ?DecodeBytes@StringUtility@@SAJPEBDHAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@I@Z; StringUtility::DecodeBytes(char const *,int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,uint)
0x18006136d  mov     edi, eax
0x18006136f  test    eax, eax
0x180061371  jns     short loc_180061395
0x180061373  lea     rax, base
0x18006137a  mov     [rsp+180h+var_140], rax
0x18006137f  lea     rax, aHresult; "HRESULT"
0x180061386  mov     [rsp+180h+var_148], rax
0x18006138b  mov     dword ptr [rsp+180h+var_150], 71h ; 'q'
0x180061393  jmp     short loc_180061347
0x180061395  lea     rcx, [rbp+80h+UrlComponents]; this
0x180061399  call    ??0Url@@QEAA@XZ; Url::Url(void)
0x18006139e  nop
0x18006139f  mov     rax, [rsi]
0x1800613a2  lea     rdx, [rbp+80h+arg_0]
0x1800613a9  mov     rcx, rsi
0x1800613ac  mov     rax, [rax+18h]
0x1800613b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800613b5  nop
0x1800613b6  mov     rdx, rax
0x1800613b9  lea     rcx, [rbp+80h+UrlComponents]; lpUrlComponents
0x1800613bd  call    ?TryCreate@Url@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Url::TryCreate(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800613c2  mov     bl, al
0x1800613c4  mov     rcx, [rbp+80h+arg_0]
0x1800613cb  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800613cf  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800613d4  test    bl, bl
0x1800613d6  jnz     short loc_180061438
0x1800613d8  mov     edi, 80048445h
0x1800613dd  lea     rax, base
0x1800613e4  mov     [rsp+180h+var_140], rax
0x1800613e9  lea     rax, aHresult; "HRESULT"
0x1800613f0  mov     [rsp+180h+var_148], rax
0x1800613f5  mov     dword ptr [rsp+180h+var_150], 79h ; 'y'
0x1800613fd  lea     rsi, aOnecoreuapDsEx_43+21h; "refreshtokenrequest.cpp"
0x180061404  mov     [rsp+180h+var_158], rsi
0x180061409  mov     dword ptr [rsp+180h+var_160], edi
0x18006140d  mov     ebx, 2
0x180061412  mov     r9d, ebx
0x180061415  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18006141c  xor     edx, edx
0x18006141e  mov     ecx, ebx
0x180061420  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180061425  nop
0x180061426  mov     rcx, [rbp+80h+var_28]
0x18006142a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18006142e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180061433  jmp     loc_18006210B
0x180061438  lea     rdx, aAadBrokerplugi; "aad:brokerplugin"
0x18006143f  lea     rcx, [rbp+80h+arg_18]
0x180061446  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18006144b  nop
0x18006144c  lea     rdx, aIss; "iss"
0x180061453  lea     rcx, [rbp+80h+arg_0]
0x18006145a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18006145f  nop
0x180061460  lea     r8, [rbp+80h+arg_18]
0x180061467  lea     rdx, [rbp+80h+arg_0]
0x18006146e  lea     rcx, [rsp+180h+Block]
0x180061473  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180061478  nop
0x180061479  mov     rcx, [rbp+80h+arg_0]
0x180061480  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180061484  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180061489  nop
0x18006148a  mov     rcx, [rbp+80h+arg_18]
0x180061491  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180061495  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18006149a  lea     rdx, aRefreshToken; "refresh_token"
0x1800614a1  lea     rcx, [rbp+80h+arg_18]
0x1800614a8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800614ad  nop
0x1800614ae  lea     rdx, aGrantType; "grant_type"
0x1800614b5  lea     rcx, [rbp+80h+arg_0]
0x1800614bc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800614c1  nop
0x1800614c2  lea     r8, [rbp+80h+arg_18]
0x1800614c9  lea     rdx, [rbp+80h+arg_0]
0x1800614d0  lea     rcx, [rsp+180h+Block]
0x1800614d5  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800614da  nop
0x1800614db  mov     rcx, [rbp+80h+arg_0]
0x1800614e2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800614e6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800614eb  nop
0x1800614ec  mov     rcx, [rbp+80h+arg_18]
0x1800614f3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800614f7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800614fc  lea     rdx, [rbp+80h+arg_18]
0x180061503  lea     rcx, [rbp+80h+UrlComponents]
0x180061507  call    ?Host@Url@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; Url::Host(void)
0x18006150c  mov     rbx, rax
0x18006150f  lea     rdx, aAud; "aud"
0x180061516  lea     rcx, [rbp+80h+arg_0]
0x18006151d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180061522  nop
0x180061523  mov     r8, rbx
0x180061526  lea     rdx, [rbp+80h+arg_0]
0x18006152d  lea     rcx, [rsp+180h+Block]
0x180061532  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180061537  nop
0x180061538  mov     rcx, [rbp+80h+arg_0]
0x18006153f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180061543  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180061548  nop
0x180061549  mov     rcx, [rbp+80h+arg_18]
0x180061550  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180061554  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180061559  lea     rbx, [rsi+88h]
0x180061560  mov     rax, [rbx]
0x180061563  cmp     [rax-10h], r12d
0x180061567  jz      short loc_1800615A2
0x180061569  lea     rdx, aResource_0; "resource"
0x180061570  lea     rcx, [rbp+80h+arg_0]
0x180061577  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18006157c  nop
0x18006157d  mov     r8, rbx
0x180061580  lea     rdx, [rbp+80h+arg_0]
0x180061587  lea     rcx, [rsp+180h+Block]
0x18006158c  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180061591  nop
0x180061592  mov     rcx, [rbp+80h+arg_0]
0x180061599  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18006159d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800615a2  lea     rbx, [rsi+98h]
0x1800615a9  mov     rax, [rbx]
0x1800615ac  cmp     [rax-10h], r12d
0x1800615b0  jnz     loc_180061765
0x1800615b6  lea     rcx, [rbp+80h+arg_18]; void *
0x1800615bd  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800615c2  nop
0x1800615c3  lea     rcx, [rbp+80h+arg_0]; void *
0x1800615ca  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800615cf  nop
0x1800615d0  mov     [rbp+80h+var_A8], r12
0x1800615d4  lea     rcx, [rbp+80h+var_A8]; __int64 *
0x1800615d8  call    ?GetUnixEpochTime@@YAJAEA_J@Z; GetUnixEpochTime(__int64 &)
0x1800615dd  mov     edi, eax
0x1800615df  test    eax, eax
0x1800615e1  jns     short loc_180061652
0x1800615e3  lea     rax, base
0x1800615ea  mov     [rsp+180h+var_140], rax
0x1800615ef  lea     rax, aHresult; "HRESULT"
0x1800615f6  mov     [rsp+180h+var_148], rax
0x1800615fb  mov     dword ptr [rsp+180h+var_150], 8Ah
0x180061603  lea     rsi, aOnecoreuapDsEx_43+21h; "refreshtokenrequest.cpp"
0x18006160a  mov     [rsp+180h+var_158], rsi
0x18006160f  mov     dword ptr [rsp+180h+var_160], edi
0x180061613  mov     ebx, 2
0x180061618  mov     r9d, ebx
0x18006161b  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180061622  xor     edx, edx
0x180061624  mov     ecx, ebx
0x180061626  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18006162b  nop
0x18006162c  mov     rcx, [rbp+80h+arg_0]
0x180061633  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180061637  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18006163c  nop
0x18006163d  mov     rcx, [rbp+80h+arg_18]
0x180061644  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180061648  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18006164d  jmp     loc_180061426
0x180061652  mov     r8, [rbp+80h+var_A8]
0x180061656  lea     rbx, [r8+258h]
0x18006165d  lea     rdx, aLld; "%lld"
0x180061664  lea     rcx, [rbp+80h+arg_18]
0x18006166b  call    ?StringFormat@StringUtility@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGZZ; StringUtility::StringFormat(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,...)
0x180061670  mov     edi, eax
0x180061672  test    eax, eax
0x180061674  jns     short loc_18006169B
0x180061676  lea     rax, base
0x18006167d  mov     [rsp+180h+var_140], rax
0x180061682  lea     rax, aHresult; "HRESULT"
0x180061689  mov     [rsp+180h+var_148], rax
0x18006168e  mov     dword ptr [rsp+180h+var_150], 8Ch
0x180061696  jmp     loc_180061603
0x18006169b  mov     r8, rbx
0x18006169e  lea     rdx, aLld; "%lld"
0x1800616a5  lea     rcx, [rbp+80h+arg_0]
0x1800616ac  call    ?StringFormat@StringUtility@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGZZ; StringUtility::StringFormat(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,...)
0x1800616b1  mov     edi, eax
0x1800616b3  test    eax, eax
0x1800616b5  jns     short loc_1800616DC
0x1800616b7  lea     rax, base
0x1800616be  mov     [rsp+180h+var_140], rax
0x1800616c3  lea     rax, aHresult; "HRESULT"
0x1800616ca  mov     [rsp+180h+var_148], rax
0x1800616cf  mov     dword ptr [rsp+180h+var_150], 8Dh
0x1800616d7  jmp     loc_180061603
0x1800616dc  lea     rdx, aIat; "iat"
0x1800616e3  lea     rcx, [rsp+180h+var_118]
0x1800616e8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800616ed  nop
0x1800616ee  lea     r8, [rbp+80h+arg_18]
0x1800616f5  lea     rdx, [rsp+180h+var_118]
0x1800616fa  lea     rcx, [rsp+180h+Block]
0x1800616ff  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180061704  nop
0x180061705  mov     rcx, [rsp+180h+var_118]
0x18006170a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18006170e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180061713  lea     rdx, aExp; "exp"
0x18006171a  lea     rcx, [rsp+180h+var_118]
0x18006171f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180061724  nop
0x180061725  lea     r8, [rbp+80h+arg_0]
0x18006172c  lea     rdx, [rsp+180h+var_118]
0x180061731  lea     rcx, [rsp+180h+Block]
0x180061736  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18006173b  nop
0x18006173c  mov     rcx, [rsp+180h+var_118]
0x180061741  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180061745  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18006174a  nop
0x18006174b  mov     rcx, [rbp+80h+arg_0]
0x180061752  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180061756  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18006175b  nop
0x18006175c  mov     rcx, [rbp+80h+arg_18]
0x180061763  jmp     short loc_180061795
0x180061765  lea     rdx, aRequestNonce; "request_nonce"
0x18006176c  lea     rcx, [rbp+80h+arg_0]
0x180061773  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180061778  nop
0x180061779  mov     r8, rbx
0x18006177c  lea     rdx, [rbp+80h+arg_0]
0x180061783  lea     rcx, [rsp+180h+Block]
0x180061788  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18006178d  nop
0x18006178e  mov     rcx, [rbp+80h+arg_0]
0x180061795  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180061799  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18006179e  lea     rdx, aScope_0; "scope"
0x1800617a5  lea     rcx, [rbp+80h+arg_0]
0x1800617ac  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800617b1  nop
0x1800617b2  lea     r8, [rsi+0A0h]
0x1800617b9  lea     rdx, [rbp+80h+arg_0]
0x1800617c0  lea     rcx, [rsp+180h+Block]
0x1800617c5  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800617ca  nop
0x1800617cb  mov     rcx, [rbp+80h+arg_0]
0x1800617d2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
  ... truncated ...
```
