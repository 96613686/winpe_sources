# GenericCallPackageHelper::CreateSSOCookieInternal(AadContextFunctions *,PluginState &,CSecureString &,CSecureString &,void *,CSecureString &,bool,_AadApPluginKeyInfo *,CSecureString &)

- ea: `0x180045694`
- end: `0x180046111`
- name: `?CreateSSOCookieInternal@GenericCallPackageHelper@@CAJPEAVAadContextFunctions@@AEAVPluginState@@AEAVCSecureString@@2PEAX2_NPEAU_AadApPluginKeyInfo@@2@Z`
- size: `2685`
- prototype: `__int64 __usercall@<rax>(struct AadContextFunctions *@<rcx>, struct PluginState *@<rdx>, struct CSecureString *@<r8>, struct CSecureString *@<r9>, void *, struct CSecureString *, bool, struct _AadApPluginKeyInfo *, struct CSecureString *)`
- caller_count: `2`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044780`
- `0x180044ed8`

## callees

- `0x180006380`
- `0x1800065e8`
- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x180006e0c`
- `0x180007d7c`
- `0x1800090d0`
- `0x18000a300`
- `0x18000aa74`
- `0x180020974`
- `0x180024910`
- `0x180025728`
- `0x18002852c`
- `0x180028760`
- `0x18002a6f4`
- `0x18003345c`
- `0x180042df0`
- `0x180043050`
- `0x180045694`
- `0x180049554`
- `0x180071e14`
- `0x1800765b0`
- `0x18007699c`
- `0x180076f14`
- `0x180077b34`
- `0x1800794f0`
- `0x1800795d0`
- `0x180079d2c`
- `0x18007efac`
- `0x18007f130`
- `0x1800a3520`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004604b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180046060`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800460a9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800460bc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004604b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180046060`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800460a9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800460bc`
- `popkeycli!NgcSignWithSymmetricPopKey` at `0x180045ddc`
- `popkeycli!NgcSignWithSymmetricPopKey` at `0x180045ddc`

## string_xrefs

- `0x1800457aa`: `refresh_token`
- `0x1800459bc`: `ua_redirect_uri`
- `0x180045726`: `GenericCallPackageHelper::CreateSSOCookieInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall GenericCallPackageHelper::CreateSSOCookieInternal(
        struct AadContextFunctions *a1,
        struct _AadNetworkConfig ***a2,
        struct CSecureString *a3,
        struct CSecureString *a4,
        void *a5,
        struct CSecureString *a6,
        bool a7,
        const wchar_t **a8,
        struct CSecureString *a9)
{
  int RedirectUri; // eax
  struct AadContextFunctions *v14; // rax
  int KdfVector; // eax
  int v16; // esi
  struct _AP_BLOB *SeedLabel; // r14
  int v18; // eax
  int v19; // esi
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // rcx
  unsigned int v23; // esi
  char *v24; // rcx
  int i; // edi
  char *v26; // rcx
  int j; // edi
  __int64 v29; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+20h] [rbp-E0h]
  __int64 v31; // [rsp+20h] [rbp-E0h]
  __int64 v32; // [rsp+30h] [rbp-D0h]
  int v33; // [rsp+30h] [rbp-D0h]
  int v34; // [rsp+30h] [rbp-D0h]
  __int64 v35; // [rsp+30h] [rbp-D0h]
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v37; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h]
  void *Block[2]; // [rsp+70h] [rbp-90h] BYREF
  int v41; // [rsp+80h] [rbp-80h]
  void *v42[2]; // [rsp+88h] [rbp-78h] BYREF
  int v43; // [rsp+98h] [rbp-68h]
  __int64 v44; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v45[8]; // [rsp+A8h] [rbp-58h] BYREF
  int v46; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v47; // [rsp+B8h] [rbp-48h]
  _BYTE v48[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v50[8]; // [rsp+D0h] [rbp-30h] BYREF
  int v51; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v52; // [rsp+E0h] [rbp-20h] BYREF
  int v53; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v54; // [rsp+F0h] [rbp-10h]
  const char *v55[15]; // [rsp+F8h] [rbp-8h] BYREF

  v37 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v50);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v45);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v44);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v49);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v48);
  *(_OWORD *)v42 = 0;
  v43 = 0;
  *(_OWORD *)Block = 0;
  v41 = 0;
  v52 = 0;
  v51 = 0;
  v54 = 0;
  v53 = 0;
  v47 = 0;
  v46 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v55,
    (int)"genericcallpackagehelper.cpp",
    (int)"GenericCallPackageHelper::CreateSSOCookieInternal",
    (int)&v37);
  ATL::CSimpleStringT<unsigned short,0>::Empty(a9);
  RedirectUri = CheckPackageSidForSSOCookie(a1, a5);
  v37 = RedirectUri;
  if ( RedirectUri < 0 )
  {
    v33 = 2432;
LABEL_3:
    WPPTraceLogA(
      2,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      2,
      RedirectUri,
      "genericcallpackagehelper.cpp",
      v33,
      "NTSTATUS",
      &base);
    goto LABEL_39;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v36,
    (__int64)L"refresh_token");
  KeyValueList::Add((__int64)Block, (__int64)&v36, (__int64)a6);
  ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v38,
    (__int64)L"true");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v36,
    (__int64)L"is_primary");
  KeyValueList::Add((__int64)Block, (__int64)&v36, (__int64)&v38);
  ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v36,
    (__int64)L"10.0.29599.1000");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v38,
    (__int64)L"win_ver");
  KeyValueList::Add((__int64)Block, (__int64)&v38, (__int64)&v36);
  ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v36,
    (__int64)L"2.0.1");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v38,
    (__int64)L"windows_api_version");
  KeyValueList::Add((__int64)Block, (__int64)&v38, (__int64)&v36);
  ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v36,
    (__int64)L"windows");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v38,
    (__int64)L"x_client_platform");
  KeyValueList::Add((__int64)Block, (__int64)&v38, (__int64)&v36);
  ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
  if ( *(_DWORD *)(*(_QWORD *)a4 - 16LL) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v38,
      (__int64)L"ua_client_id");
    KeyValueList::Add((__int64)Block, (__int64)&v38, (__int64)a4);
    ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
    RedirectUri = GetRedirectUri(a1, a5, *(_QWORD *)a4, (__int64)v48);
    v37 = RedirectUri;
    if ( RedirectUri < 0 )
    {
      v33 = 2445;
      goto LABEL_3;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v38,
      (__int64)L"ua_redirect_uri");
    KeyValueList::Add((__int64)Block, (__int64)&v38, (__int64)v48);
    ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
  }
  RedirectUri = GenericCallPackageHelper::AddNonceOrTimestamp(Block, a3);
  v37 = RedirectUri;
  if ( RedirectUri < 0 )
  {
    v33 = 2451;
    goto LABEL_3;
  }
  WebResponseHelper::FormatJson(Block, v45);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v36,
    (__int64)L"HS256");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v38,
    (__int64)L"alg");
  KeyValueList::Add((__int64)v42, (__int64)&v38, (__int64)&v36);
  ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
  if ( !wcscmp_0(a8[1], L"ngc") )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v36);
    if ( a7 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v38,
        (__int64)L"kdf_ver");
      KeyValueList::Add(v42, &v38, 2);
      ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
      v14 = PluginContextHelper::Context();
      KdfVector = GenerateKdfVector(v14, (struct CSecureString *)v45, (struct _AP_BLOB *)&v46, (struct _AP_BLOB *)&v53);
      if ( KdfVector < 0 )
      {
        v34 = 2466;
LABEL_14:
        WPPTraceLogA(
          2,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          2,
          KdfVector,
          "genericcallpackagehelper.cpp",
          v34,
          "HRESULT",
          &base);
        CSecureString::~CSecureString((CSecureString *)&v36);
        goto LABEL_39;
      }
      KdfVector = StringUtility::Base64Encode(&v53, &v36);
      if ( KdfVector < 0 )
      {
        v34 = 2467;
        goto LABEL_14;
      }
    }
    else
    {
      KdfVector = LocalApBlob::Allocate((LocalApBlob *)&v46, 0x18u);
      if ( KdfVector < 0 )
      {
        v34 = 2471;
        goto LABEL_14;
      }
      KdfVector = CryptoHelper::GenRandom((struct _AP_BLOB *)&v46);
      if ( KdfVector < 0 )
      {
        v34 = 2472;
        goto LABEL_14;
      }
      KdfVector = StringUtility::Base64Encode(&v46, &v36);
      if ( KdfVector < 0 )
      {
        v34 = 2473;
        goto LABEL_14;
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v38,
      (__int64)L"ctx");
    KeyValueList::Add((__int64)v42, (__int64)&v38, (__int64)&v36);
    ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
    CSecureString::~CSecureString((CSecureString *)&v36);
  }
  WebResponseHelper::FormatJson(v42, v50);
  v16 = ConstructSigningInput(v50, v45, &v44);
  if ( v16 < 0 )
  {
    LODWORD(v32) = 2482;
LABEL_26:
    LODWORD(v29) = v16;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v29, "genericcallpackagehelper.cpp", v32, "HRESULT", &base);
    v37 = v16 & 0xAFFFFFFF | 0x40000000;
    goto LABEL_39;
  }
  if ( !wcscmp_0(a8[1], L"ngc") )
  {
    v39 = 0;
    LODWORD(v38) = 0;
    SeedLabel = CryptoHelper::GetSeedLabel();
    v18 = StringUtility::EncodeString(a1, &v44, &v38, 65001, 1);
    v19 = v18;
    if ( v18 >= 0 )
    {
      v20 = NgcSignWithSymmetricPopKey(
              a8[4],
              *((unsigned int *)a8 + 6),
              *((_QWORD *)SeedLabel + 1),
              *(unsigned int *)SeedLabel,
              v47,
              v46,
              v39,
              v38,
              &v52,
              &v51);
      v21 = v20;
      if ( v20 >= 0 )
      {
        PluginLocalFreeApBlob((struct _AP_BLOB *)&v38);
        v16 = StringUtility::Base64UrlEncode(&v51, &v49);
        if ( v16 < 0 )
        {
          LODWORD(v32) = 2519;
          goto LABEL_26;
        }
        v16 = StringUtility::StringFormat(a9, L"%s.%s", v44, v49);
        if ( v16 < 0 )
        {
          LODWORD(v32) = 2521;
          goto LABEL_26;
        }
      }
      else
      {
        WPPTraceLogA(
          2,
          0,
          "%x 0x%08x %s:%u : %s:%u",
          2,
          0,
          "genericcallpackagehelper.cpp",
          2507,
          "NgcSignWithSymmetricPopKey(SSO) failed",
          v20);
        if ( (Microsoft_Windows_AADEnableBits & 4) != 0 )
          McTemplateU0zd_EventWriteTransfer(v22, Aad_CloudAPPlugin_NGC_Error, L"NgcSignWithSymmetricPopKey(SSO)", v21);
        EnableAadRecoveryOnNgcErrorIfNecessary(
          **a2,
          v21,
          *((const unsigned __int16 **)(*a2)[1] + 3),
          L"Signing SSO artifact");
        LODWORD(v35) = 2510;
        LODWORD(v31) = v21;
        WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v31, "genericcallpackagehelper.cpp", v35, "HRESULT", &base);
        v37 = v21 & 0xAFFFFFFF | 0x40000000;
        PluginLocalFreeApBlob((struct _AP_BLOB *)&v38);
      }
    }
    else
    {
      LODWORD(v30) = v18;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v30, "genericcallpackagehelper.cpp", 2490, "HRESULT", &base);
      v37 = v19 & 0xAFFFFFFF | 0x40000000;
      PluginLocalFreeApBlob((struct _AP_BLOB *)&v38);
    }
  }
  else
  {
    WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws");
    WPPTraceLogA(
      2,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      2,
      2147779654LL,
      "genericcallpackagehelper.cpp",
      2516,
      "HRESULT",
      &base);
    v37 = -1073445818;
  }
LABEL_39:
  LocalApBlob::ReleaseExternal((LocalApBlob *)&v51);
  v23 = v37;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v55);
  PluginLocalFreeApBlob((struct _AP_BLOB *)&v46);
  PluginLocalFreeApBlob((struct _AP_BLOB *)&v53);
  PluginLocalFreeApBlob((struct _AP_BLOB *)&v51);
  v24 = (char *)Block[0];
  if ( Block[0] )
  {
    for ( i = 0; i < v41; v24 = (char *)Block[0] )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::`scalar deleting destructor'(&v24[8 * i]);
      KeyListValue::~KeyListValue((KeyListValue *)((char *)Block[1] + 72 * i++));
    }
    free(v24);
    Block[0] = 0;
  }
  if ( Block[1] )
  {
    free(Block[1]);
    Block[1] = 0;
  }
  v41 = 0;
  v26 = (char *)v42[0];
  if ( v42[0] )
  {
    for ( j = 0; j < v43; v26 = (char *)v42[0] )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::`scalar deleting destructor'(&v26[8 * j]);
      KeyListValue::~KeyListValue((KeyListValue *)((char *)v42[1] + 72 * j++));
    }
    free(v26);
    v42[0] = 0;
  }
  if ( v42[1] )
  {
    free(v42[1]);
    v42[1] = 0;
  }
  v43 = 0;
  CSecureString::~CSecureString((CSecureString *)v48);
  CSecureString::~CSecureString((CSecureString *)&v49);
  CSecureString::~CSecureString((CSecureString *)&v44);
  CSecureString::~CSecureString((CSecureString *)v45);
  CSecureString::~CSecureString((CSecureString *)v50);
  return v23;
}

```

## disassembly

```asm
0x180045694  push    rbp
0x180045696  push    rbx
0x180045697  push    rsi
0x180045698  push    rdi
0x180045699  push    r12
0x18004569b  push    r13
0x18004569d  push    r14
0x18004569f  push    r15
0x1800456a1  lea     rbp, [rsp-38h]
0x1800456a6  sub     rsp, 138h
0x1800456ad  mov     rbx, r9
0x1800456b0  mov     rdi, r8
0x1800456b3  mov     r12, rdx
0x1800456b6  mov     r15, rcx
0x1800456b9  xor     r13d, r13d
0x1800456bc  mov     [rsp+170h+var_118], r13d
0x1800456c1  lea     rcx, [rbp+70h+var_A0]; void *
0x1800456c5  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800456ca  nop
0x1800456cb  lea     rcx, [rbp+70h+var_C8]; void *
0x1800456cf  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800456d4  nop
0x1800456d5  lea     rcx, [rbp+70h+var_D0]; void *
0x1800456d9  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800456de  nop
0x1800456df  lea     rcx, [rbp+70h+var_A8]; void *
0x1800456e3  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800456e8  nop
0x1800456e9  lea     rcx, [rbp+70h+var_B0]; void *
0x1800456ed  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800456f2  nop
0x1800456f3  xorps   xmm0, xmm0
0x1800456f6  movdqu  xmmword ptr [rbp+70h+var_E8], xmm0
0x1800456fb  mov     [rbp+70h+var_D8], r13d
0x1800456ff  movdqu  xmmword ptr [rsp+170h+Block], xmm0
0x180045705  mov     [rbp+70h+var_F0], r13d
0x180045709  mov     [rbp+70h+var_90], r13
0x18004570d  mov     [rbp+70h+var_98], r13d
0x180045711  mov     [rbp+70h+var_80], r13
0x180045715  mov     [rbp+70h+var_88], r13d
0x180045719  mov     [rbp+70h+var_B8], r13
0x18004571d  mov     [rbp+70h+var_C0], r13d
0x180045721  lea     r9, [rsp+170h+var_118]
0x180045726  lea     r8, aGenericcallpac_23; "GenericCallPackageHelper::CreateSSOCook"...
0x18004572d  lea     r14, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x180045734  mov     rdx, r14
0x180045737  lea     rcx, [rbp+70h+var_78]
0x18004573b  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180045740  nop
0x180045741  mov     rcx, [rbp+70h+arg_40]
0x180045748  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18004574d  mov     rdx, [rbp+70h+arg_20]; void *
0x180045754  mov     rcx, r15; struct AadContextFunctions *
0x180045757  call    ?CheckPackageSidForSSOCookie@@YAJPEAVAadContextFunctions@@PEAX@Z; CheckPackageSidForSSOCookie(AadContextFunctions *,void *)
0x18004575c  mov     [rsp+170h+var_118], eax
0x180045760  test    eax, eax
0x180045762  jns     short loc_1800457AA
0x180045764  lea     rdi, base
0x18004576b  mov     [rsp+170h+var_130], rdi
0x180045770  lea     rcx, aNtstatus; "NTSTATUS"
0x180045777  mov     [rsp+170h+var_138], rcx
0x18004577c  mov     dword ptr [rsp+170h+var_140], 980h
0x180045784  mov     [rsp+170h+var_148], r14
0x180045789  mov     dword ptr [rsp+170h+var_150], eax
0x18004578d  mov     ebx, 2
0x180045792  mov     r9d, ebx
0x180045795  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004579c  xor     edx, edx
0x18004579e  mov     ecx, ebx
0x1800457a0  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800457a5  jmp     loc_180045FD9
0x1800457aa  lea     rdx, aRefreshToken; "refresh_token"
0x1800457b1  lea     rcx, [rsp+170h+var_120]
0x1800457b6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800457bb  nop
0x1800457bc  mov     r8, [rbp+70h+arg_28]
0x1800457c3  lea     rdx, [rsp+170h+var_120]
0x1800457c8  lea     rcx, [rsp+170h+Block]
0x1800457cd  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800457d2  nop
0x1800457d3  mov     rcx, [rsp+170h+var_120]
0x1800457d8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800457dc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800457e1  lea     rdx, aTrue; "true"
0x1800457e8  lea     rcx, [rsp+170h+var_110]
0x1800457ed  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800457f2  nop
0x1800457f3  lea     rdx, aIsPrimary; "is_primary"
0x1800457fa  lea     rcx, [rsp+170h+var_120]
0x1800457ff  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180045804  nop
0x180045805  lea     r8, [rsp+170h+var_110]
0x18004580a  lea     rdx, [rsp+170h+var_120]
0x18004580f  lea     rcx, [rsp+170h+Block]
0x180045814  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180045819  nop
0x18004581a  mov     rcx, [rsp+170h+var_120]
0x18004581f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180045823  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180045828  nop
0x180045829  mov     rcx, [rsp+170h+var_110]
0x18004582e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180045832  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180045837  lea     rdx, a100295991000; "10.0.29599.1000"
0x18004583e  lea     rcx, [rsp+170h+var_120]
0x180045843  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180045848  nop
0x180045849  lea     rdx, aWinVer; "win_ver"
0x180045850  lea     rcx, [rsp+170h+var_110]
0x180045855  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18004585a  nop
0x18004585b  lea     r8, [rsp+170h+var_120]
0x180045860  lea     rdx, [rsp+170h+var_110]
0x180045865  lea     rcx, [rsp+170h+Block]
0x18004586a  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004586f  nop
0x180045870  mov     rcx, [rsp+170h+var_110]
0x180045875  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180045879  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004587e  nop
0x18004587f  mov     rcx, [rsp+170h+var_120]
0x180045884  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180045888  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004588d  lea     rdx, a201; "2.0.1"
0x180045894  lea     rcx, [rsp+170h+var_120]
0x180045899  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18004589e  nop
0x18004589f  lea     rdx, aWindowsApiVers; "windows_api_version"
0x1800458a6  lea     rcx, [rsp+170h+var_110]
0x1800458ab  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800458b0  nop
0x1800458b1  lea     r8, [rsp+170h+var_120]
0x1800458b6  lea     rdx, [rsp+170h+var_110]
0x1800458bb  lea     rcx, [rsp+170h+Block]
0x1800458c0  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800458c5  nop
0x1800458c6  mov     rcx, [rsp+170h+var_110]
0x1800458cb  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800458cf  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800458d4  nop
0x1800458d5  mov     rcx, [rsp+170h+var_120]
0x1800458da  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800458de  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800458e3  lea     rdx, aWindows; "windows"
0x1800458ea  lea     rcx, [rsp+170h+var_120]
0x1800458ef  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800458f4  nop
0x1800458f5  lea     rdx, aXClientPlatfor; "x_client_platform"
0x1800458fc  lea     rcx, [rsp+170h+var_110]
0x180045901  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180045906  nop
0x180045907  lea     r8, [rsp+170h+var_120]
0x18004590c  lea     rdx, [rsp+170h+var_110]
0x180045911  lea     rcx, [rsp+170h+Block]
0x180045916  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004591b  nop
0x18004591c  mov     rcx, [rsp+170h+var_110]
0x180045921  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180045925  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004592a  nop
0x18004592b  mov     rcx, [rsp+170h+var_120]
0x180045930  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180045934  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180045939  mov     rax, [rbx]
0x18004593c  cmp     [rax-10h], r13d
0x180045940  jz      loc_1800459F0
0x180045946  lea     rdx, aUaClientId; "ua_client_id"
0x18004594d  lea     rcx, [rsp+170h+var_110]
0x180045952  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180045957  nop
0x180045958  mov     r8, rbx
0x18004595b  lea     rdx, [rsp+170h+var_110]
0x180045960  lea     rcx, [rsp+170h+Block]
0x180045965  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004596a  nop
0x18004596b  mov     rcx, [rsp+170h+var_110]
0x180045970  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180045974  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180045979  lea     r9, [rbp+70h+var_B0]
0x18004597d  mov     r8, [rbx]
0x180045980  mov     rdx, [rbp+70h+arg_20]; void *
0x180045987  mov     rcx, r15; struct AadContextFunctions *
0x18004598a  call    ?GetRedirectUri@@YAJPEAVAadContextFunctions@@PEAXPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetRedirectUri(AadContextFunctions *,void *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18004598f  mov     [rsp+170h+var_118], eax
0x180045993  test    eax, eax
0x180045995  jns     short loc_1800459BC
0x180045997  lea     rdi, base
0x18004599e  mov     [rsp+170h+var_130], rdi
0x1800459a3  lea     rcx, aNtstatus; "NTSTATUS"
0x1800459aa  mov     [rsp+170h+var_138], rcx
0x1800459af  mov     dword ptr [rsp+170h+var_140], 98Dh
0x1800459b7  jmp     loc_180045784
0x1800459bc  lea     rdx, aUaRedirectUri; "ua_redirect_uri"
0x1800459c3  lea     rcx, [rsp+170h+var_110]
0x1800459c8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800459cd  nop
0x1800459ce  lea     r8, [rbp+70h+var_B0]
0x1800459d2  lea     rdx, [rsp+170h+var_110]
0x1800459d7  lea     rcx, [rsp+170h+Block]
0x1800459dc  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800459e1  nop
0x1800459e2  mov     rcx, [rsp+170h+var_110]
0x1800459e7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800459eb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800459f0  mov     rdx, rdi
0x1800459f3  lea     rcx, [rsp+170h+Block]
0x1800459f8  call    ?AddNonceOrTimestamp@GenericCallPackageHelper@@CAJAEAVKeyValueList@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GenericCallPackageHelper::AddNonceOrTimestamp(KeyValueList &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800459fd  mov     [rsp+170h+var_118], eax
0x180045a01  test    eax, eax
0x180045a03  jns     short loc_180045A2A
0x180045a05  lea     rdi, base
0x180045a0c  mov     [rsp+170h+var_130], rdi
0x180045a11  lea     rcx, aNtstatus; "NTSTATUS"
0x180045a18  mov     [rsp+170h+var_138], rcx
0x180045a1d  mov     dword ptr [rsp+170h+var_140], 993h
0x180045a25  jmp     loc_180045784
0x180045a2a  lea     rdx, [rbp+70h+var_C8]
0x180045a2e  lea     rcx, [rsp+170h+Block]
0x180045a33  call    ?FormatJson@WebResponseHelper@@SAXAEBVKeyValueList@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::FormatJson(KeyValueList const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180045a38  lea     rdx, aHs256; "HS256"
0x180045a3f  lea     rcx, [rsp+170h+var_120]
0x180045a44  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180045a49  nop
0x180045a4a  lea     rdx, aAlg; "alg"
0x180045a51  lea     rcx, [rsp+170h+var_110]
0x180045a56  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180045a5b  nop
0x180045a5c  lea     r8, [rsp+170h+var_120]
0x180045a61  lea     rdx, [rsp+170h+var_110]
0x180045a66  lea     rcx, [rbp+70h+var_E8]
0x180045a6a  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180045a6f  nop
0x180045a70  mov     rcx, [rsp+170h+var_110]
0x180045a75  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180045a79  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180045a7e  nop
0x180045a7f  mov     rcx, [rsp+170h+var_120]
0x180045a84  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180045a88  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180045a8d  mov     rdi, [rbp+70h+arg_38]
0x180045a94  lea     rdx, aNgc; "ngc"
0x180045a9b  mov     rcx, [rdi+8]; String1
0x180045a9f  call    wcscmp_0
0x180045aa4  mov     ebx, 2
0x180045aa9  test    eax, eax
0x180045aab  jnz     loc_180045C7B
0x180045ab1  lea     rcx, [rsp+170h+var_120]; void *
0x180045ab6  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180045abb  nop
0x180045abc  cmp     [rbp+70h+arg_30], r13b
0x180045ac3  jz      loc_180045B9C
0x180045ac9  lea     rdx, aKdfVer; "kdf_ver"
0x180045ad0  lea     rcx, [rsp+170h+var_110]
0x180045ad5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180045ada  nop
0x180045adb  mov     r8d, ebx
0x180045ade  lea     rdx, [rsp+170h+var_110]
0x180045ae3  lea     rcx, [rbp+70h+var_E8]
0x180045ae7  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,int)
0x180045aec  nop
0x180045aed  mov     rcx, [rsp+170h+var_110]
0x180045af2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180045af6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180045afb  call    ?Context@PluginContextHelper@@SAPEAVAadContextFunctions@@XZ; PluginContextHelper::Context(void)
0x180045b00  mov     rcx, rax; this
0x180045b03  lea     r9, [rbp+70h+var_88]; struct _AP_BLOB *
0x180045b07  lea     r8, [rbp+70h+var_C0]; struct _AP_BLOB *
0x180045b0b  lea     rdx, [rbp+70h+var_C8]; struct CSecureString *
0x180045b0f  call    ?GenerateKdfVector@@YAJPEAVAadContextFunctions@@AEAVCSecureString@@PEAU_AP_BLOB@@2@Z; GenerateKdfVector(AadContextFunctions *,CSecureString &,_AP_BLOB *,_AP_BLOB *)
0x180045b14  test    eax, eax
0x180045b16  jns     short loc_180045B64
0x180045b18  lea     rdi, base
0x180045b1f  mov     [rsp+170h+var_130], rdi
0x180045b24  lea     rcx, aHresult; "HRESULT"
0x180045b2b  mov     [rsp+170h+var_138], rcx
0x180045b30  mov     dword ptr [rsp+170h+var_140], 9A2h
0x180045b38  mov     [rsp+170h+var_148], r14
0x180045b3d  mov     dword ptr [rsp+170h+var_150], eax
0x180045b41  mov     r9d, ebx
0x180045b44  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180045b4b  xor     edx, edx
0x180045b4d  mov     ecx, ebx
0x180045b4f  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180045b54  nop
0x180045b55  lea     rcx, [rsp+170h+var_120]; this
0x180045b5a  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x180045b5f  jmp     loc_180045FD9
0x180045b64  lea     rdx, [rsp+170h+var_120]
0x180045b69  lea     rcx, [rbp+70h+var_88]
0x180045b6d  call    ?Base64Encode@StringUtility@@SAJQEAU_AP_BLOB@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; StringUtility::Base64Encode(_AP_BLOB * const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180045b72  test    eax, eax
0x180045b74  jns     loc_180045C3C
0x180045b7a  lea     rdi, base
0x180045b81  mov     [rsp+170h+var_130], rdi
0x180045b86  lea     rcx, aHresult; "HRESULT"
0x180045b8d  mov     [rsp+170h+var_138], rcx
0x180045b92  mov     dword ptr [rsp+170h+var_140], 9A3h
0x180045b9a  jmp     short loc_180045B38
0x180045b9c  mov     edx, 18h; unsigned int
0x180045ba1  lea     rcx, [rbp+70h+var_C0]; this
  ... truncated ...
```
