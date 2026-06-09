# OAuthResponse::FillTokenInfo(AadContextFunctions *,ushort const *,_AadNetworkConfig *,_APPLUGIN_USER_INFO * *,_AadApPluginTokenInfo *)

- ea: `0x1800561a0`
- end: `0x180056f6a`
- name: `?FillTokenInfo@OAuthResponse@@UEAAJPEAVAadContextFunctions@@PEBGPEAU_AadNetworkConfig@@PEAPEAU_APPLUGIN_USER_INFO@@PEAU_AadApPluginTokenInfo@@@Z`
- size: `3530`
- prototype: `__int64 __usercall@<rax>(OAuthResponse *__hidden this@<rcx>, struct AadContextFunctions *@<rdx>, const unsigned __int16 *@<r8>, struct _AadNetworkConfig *@<r9>, struct _APPLUGIN_USER_INFO **, struct _AadApPluginTokenInfo *)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004a24`
- `0x1800063f4`
- `0x180006530`
- `0x1800069c0`
- `0x180006ac4`
- `0x180007a90`
- `0x180007df8`
- `0x1800090d0`
- `0x18000a300`
- `0x18000c6c4`
- `0x18001cf08`
- `0x18002fde8`
- `0x180036b3c`
- `0x1800377bc`
- `0x180052510`
- `0x180055864`
- `0x1800561a0`
- `0x18005950c`
- `0x180071e14`
- `0x180074a74`
- `0x180076228`
- `0x180076f14`
- `0x180077ab4`
- `0x180077fd8`
- `0x1800787ec`
- `0x180078b18`
- `0x1800a352c`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005638a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005638a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800563e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005656d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800563e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005656d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056ea1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056ed0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056ea1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056ed0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800563d9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180056563`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800563d9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180056563`

## string_xrefs

- `0x180056213`: `OAuthResponse::FillTokenInfo`
- `0x180056646`: `https://go.microsoft.com/fwlink/?LinkId=335789`
- `0x180056468`: `SecurityGroupsHelper::UpdateSecurityGroups error`
- `0x180056df3`: `RegistryHelper::SetPrtRefreshTimeout error`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OAuthResponse::FillTokenInfo(
        OAuthResponse *this,
        struct AadContextFunctions *a2,
        unsigned __int16 *a3,
        struct _AadNetworkConfig *a4,
        struct _APPLUGIN_USER_INFO **a5,
        struct _AadApPluginTokenInfo *a6)
{
  struct _AadApPluginTokenInfo *v9; // r13
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rdx
  const WCHAR *v16; // rcx
  signed int LastError; // eax
  int updated; // eax
  unsigned int v19; // ebx
  __int64 v20; // rcx
  unsigned int v21; // eax
  size_t v22; // rbx
  PSID *v23; // rax
  PSID *v24; // rdi
  int v25; // ebx
  __int64 v26; // rcx
  signed int v27; // eax
  char v28; // bl
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  int v32; // ecx
  unsigned __int8 v33; // al
  _DWORD *v34; // rax
  _DWORD *v35; // rbx
  __int64 v36; // rcx
  unsigned int v37; // eax
  __int64 (__fastcall *v38)(__int64, PSID, _QWORD, PSID *, __int64, _QWORD, _QWORD, _QWORD, _QWORD, __int128 *, __int128 *, unsigned __int64, bool, struct _APPLUGIN_USER_INFO **); // r10
  unsigned __int64 v39; // rax
  const void *const *v40; // rbx
  int v41; // eax
  _WORD *v42; // rax
  __int64 v43; // rdx
  int v44; // r8d
  const unsigned __int16 *v45; // rdx
  int v46; // r8d
  int v47; // r8d
  int v48; // r8d
  const unsigned __int16 *v49; // rdx
  int v50; // r8d
  int v51; // r8d
  __int64 v52; // rcx
  bool v53; // al
  const wchar_t *v54; // rbx
  const wchar_t *v55; // rcx
  unsigned int v56; // r9d
  struct _AadNetworkConfig *v57; // rax
  int v58; // eax
  PSID *v59; // rdx
  unsigned int v60; // ebx
  unsigned int i; // edi
  PSID v62; // rcx
  unsigned int v63; // ebx
  struct _AadApPluginKeyInfo *v65; // [rsp+28h] [rbp-E0h]
  struct _AadApPluginKeyInfo *v66; // [rsp+28h] [rbp-E0h]
  __int64 v67; // [rsp+38h] [rbp-D0h]
  __int64 v68; // [rsp+38h] [rbp-D0h]
  const char *v69; // [rsp+40h] [rbp-C8h]
  int v70; // [rsp+88h] [rbp-80h] BYREF
  char v71; // [rsp+8Ch] [rbp-7Ch]
  __int64 v72; // [rsp+90h] [rbp-78h] BYREF
  int v73; // [rsp+98h] [rbp-70h]
  unsigned int v74; // [rsp+9Ch] [rbp-6Ch]
  PSID *v75; // [rsp+A0h] [rbp-68h]
  PSID Sid; // [rsp+A8h] [rbp-60h] BYREF
  void *Source[2]; // [rsp+B0h] [rbp-58h] BYREF
  _DWORD *v78; // [rsp+C0h] [rbp-48h]
  __int128 v79; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v80; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v81; // [rsp+E8h] [rbp-20h]
  __int128 v82; // [rsp+F0h] [rbp-18h] BYREF
  struct _GUID v83; // [rsp+108h] [rbp+0h] BYREF
  const char *v84[12]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v85; // [rsp+190h] [rbp+88h] BYREF
  unsigned __int16 *v86; // [rsp+198h] [rbp+90h]
  struct _AadNetworkConfig *v87; // [rsp+1A0h] [rbp+98h]

  v87 = a4;
  v86 = a3;
  v70 = 0;
  v80 = 0;
  v81 = 0;
  v79 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v72);
  Sid = 0;
  v74 = 0;
  v75 = 0;
  v71 = 0;
  v82 = 0;
  v78 = 0;
  *(_OWORD *)Source = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v84,
    (int)"oauthresponse.cpp",
    (int)"OAuthResponse::FillTokenInfo",
    (int)&v70);
  v9 = a6;
  if ( !a2 || !a5 || !a6 || !a4 )
  {
    LODWORD(v11) = -2147024809;
    v69 = "HRESULT";
    LODWORD(v67) = 637;
    goto LABEL_124;
  }
  *a5 = 0;
  memset_0(v9, 0, 0x268u);
  v10 = *((_QWORD *)this + 39);
  if ( *(_DWORD *)(v10 - 16) )
  {
    CSecureString::operator=((__int64)&v72, v10);
    goto LABEL_18;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 41) - 16LL) )
  {
    LODWORD(v11) = StringUtility::StringAppendFormat(&v72, L"%s ");
    v70 = v11;
    if ( (int)v11 < 0 )
    {
      v69 = "HRESULT";
      LODWORD(v67) = 652;
LABEL_125:
      LODWORD(v65) = v11;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v65, "oauthresponse.cpp", v67, v69, &base);
      goto LABEL_126;
    }
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 42) - 16LL) )
  {
    LODWORD(v11) = StringUtility::StringAppendFormat(&v72, L"%s ");
    v70 = v11;
    if ( (int)v11 < 0 )
    {
      v69 = "HRESULT";
      LODWORD(v67) = 656;
      goto LABEL_125;
    }
  }
  if ( !*(_DWORD *)(v72 - 16) )
  {
    v12 = *((_QWORD *)this + 43);
    v13 = *(unsigned int *)(v12 - 16);
    if ( (_DWORD)v13 )
      ATL::CSimpleStringT<unsigned short,0>::Append(&v72, v12, v13);
  }
  if ( !*(_DWORD *)(v72 - 16) )
    ATL::CSimpleStringT<unsigned short,0>::Append(
      &v72,
      *((_QWORD *)this + 40),
      *(unsigned int *)(*((_QWORD *)this + 40) - 16LL));
LABEL_18:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GuestUserRDPToAVD>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GuestUserRDPToAVD>::GetImpl'::`2'::impl) )
  {
    v14 = *((_QWORD *)this + 64);
    if ( *(_DWORD *)(v14 - 16) )
    {
      v15 = *((_QWORD *)this + 65);
      if ( *(_DWORD *)(v15 - 16) )
      {
        if ( (unsigned int)_o__wcsicmp(v14, v15) )
          *((_DWORD *)v9 + 152) = 1;
      }
    }
  }
  v16 = (const WCHAR *)*((_QWORD *)this + 44);
  if ( !*((_DWORD *)v16 - 4) )
  {
    LODWORD(v11) = -2147187646;
    v69 = "HRESULT";
    LODWORD(v67) = 681;
LABEL_124:
    v70 = v11;
    goto LABEL_125;
  }
  if ( !ConvertStringSidToSidW(v16, &Sid) )
  {
    LastError = GetLastError();
    LODWORD(v11) = LastError;
    if ( LastError > 0 )
      LODWORD(v11) = (unsigned __int16)LastError | 0x80070000;
    v70 = v11;
    if ( (int)v11 < 0 )
    {
      v69 = "HRESULT";
      LODWORD(v67) = 685;
      goto LABEL_125;
    }
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 51) - 16LL) )
  {
    if ( *((_QWORD *)this + 26) )
    {
      updated = SecurityGroupsHelper::UpdateSecurityGroups(a2);
      v19 = updated;
      if ( updated < 0 )
      {
        WPPTraceLogA(
          3,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          3,
          updated,
          "oauthresponse.cpp",
          693,
          "SecurityGroupsHelper::UpdateSecurityGroups error",
          &base);
        if ( (Microsoft_Windows_AADEnableBits & 0x80u) != 0 )
          McTemplateU0d_EventWriteTransfer(v20, Aad_CloudAPPlugin_UpdateSecurityGroupsError, v19);
      }
    }
  }
  v21 = *((_DWORD *)this + 94);
  v74 = v21;
  if ( v21 )
  {
    v22 = 8LL * v21;
    v23 = (PSID *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, size_t))(*(_QWORD *)a2 + 8LL))(
                    a2,
                    64,
                    v22);
    v24 = v23;
    v75 = v23;
    if ( !v23 )
    {
      v69 = "HRESULT";
      LODWORD(v67) = 707;
LABEL_38:
      LODWORD(v11) = -2147024882;
LABEL_39:
      v70 = v11;
      goto LABEL_125;
    }
    memset_0(v23, 0, v22);
    v71 = 1;
    v25 = 0;
    v26 = *((_QWORD *)this + 45);
    v85 = v26;
    if ( v26 )
    {
      while ( 1 )
      {
        if ( !v26 )
          ATL::AtlThrowImpl(-2147467259);
        if ( !ConvertStringSidToSidW(*(LPCWSTR *)(v26 + 16), &v24[v25]) )
        {
          v27 = GetLastError();
          v11 = (unsigned int)v27;
          if ( v27 > 0 )
            v11 = (unsigned __int16)v27 | 0x80070000;
          v70 = v11;
          if ( (int)v11 < 0 )
            break;
        }
        ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(v11, &v85);
        v26 = v85;
        if ( !v85 )
          goto LABEL_49;
        ++v25;
      }
      v69 = "HRESULT";
      LODWORD(v67) = 721;
      goto LABEL_125;
    }
  }
LABEL_49:
  v28 = 0;
  v29 = v80;
  if ( *(_DWORD *)(*((_QWORD *)this + 52) - 16LL) )
    v29 = *((_QWORD *)this + 52);
  *(_QWORD *)&v80 = v29;
  v30 = *((_QWORD *)&v80 + 1);
  if ( *(_DWORD *)(*((_QWORD *)this + 53) - 16LL) )
    v30 = *((_QWORD *)this + 53);
  *((_QWORD *)&v80 + 1) = v30;
  v31 = v81;
  if ( *(_DWORD *)(*((_QWORD *)this + 54) - 16LL) )
    v31 = *((_QWORD *)this + 54);
  v81 = v31;
  v32 = *((_DWORD *)this + 121);
  if ( v32 )
    *((_QWORD *)&v79 + 1) = 10000000 * (v32 + *((_DWORD *)this + 4) + 0x2B6109100LL);
  if ( *(_DWORD *)(*((_QWORD *)this + 61) - 16LL) )
  {
    *(_QWORD *)&v79 = *((_QWORD *)this + 61);
    v33 = 0;
  }
  else
  {
    *(_QWORD *)&v79 = L"https://go.microsoft.com/fwlink/?LinkId=335789";
    v33 = 1;
  }
  *((_DWORD *)v9 + 116) = v33;
  *(_DWORD *)v9 = 3;
  if ( *(_DWORD *)(*((_QWORD *)this + 62) - 16LL) )
  {
    LODWORD(v11) = StringUtility::Base64Decode(a2, (char *)this + 496, Source);
    v70 = v11;
    if ( (int)v11 < 0 )
    {
      v69 = "HRESULT";
      LODWORD(v67) = 766;
      goto LABEL_125;
    }
    v34 = (_DWORD *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
                      a2,
                      64,
                      (unsigned int)(LODWORD(Source[0]) + 20));
    v35 = v34;
    v78 = v34;
    if ( !v34 )
    {
      v69 = "HRESULT";
      LODWORD(v67) = 773;
      goto LABEL_38;
    }
    *v34 = LODWORD(Source[0]) + 20;
    v36 = 10000000 * (*((int *)this + 6) + 0x2B6109100LL);
    v34[1] = 10000000 * (*((_DWORD *)this + 6) - 1240428288);
    v34[2] = HIDWORD(v36);
    v34[3] = 20;
    v37 = (unsigned int)Source[0];
    v35[4] = Source[0];
    if ( memcpy_s_0(v35 + 5, v37, Source[1], v37) )
    {
      LODWORD(v11) = -1073741595;
      v69 = "NTSTATUS";
      LODWORD(v67) = 786;
      goto LABEL_39;
    }
    LODWORD(v82) = 6;
    *((_QWORD *)&v82 + 1) = v35;
    v28 = 1;
  }
  LODWORD(v85) = *(_DWORD *)(*((_QWORD *)this + 63) - 16LL);
  if ( (*(__int64 (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a2 + 48LL))(a2) )
  {
    v38 = *(__int64 (__fastcall **)(__int64, PSID, _QWORD, PSID *, __int64, _QWORD, _QWORD, _QWORD, _QWORD, __int128 *, __int128 *, unsigned __int64, bool, struct _APPLUGIN_USER_INFO **))((*(__int64 (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a2 + 48LL))(a2) + 48);
    v39 = (unsigned __int64)&v82 & -(__int64)(v28 != 0);
    v40 = (const void *const *)a5;
    v41 = v38(
            2,
            Sid,
            v74,
            v75,
            v72,
            *((_QWORD *)this + 35),
            *((_QWORD *)this + 41),
            *((_QWORD *)this + 42),
            *((_QWORD *)this + 38),
            &v80,
            &v79,
            v39,
            (_DWORD)v85 != 0,
            a5);
    LODWORD(v11) = v41 | 0x10000000;
    v70 = v41 | 0x10000000;
    if ( v41 < 0 )
    {
      v69 = "HRESULT";
      LODWORD(v67) = 817;
      goto LABEL_125;
    }
    if ( !*v40 )
    {
      LODWORD(v11) = -2147187647;
      v70 = -2147187647;
      v69 = "HRESULT";
      LODWORD(v67) = 822;
      goto LABEL_125;
    }
    memcpy_s_0((char *)v9 + 8, 0x88u, *v40, 0x88u);
  }
  v42 = (_WORD *)*((_QWORD *)this + 32);
  if ( !v42 || !*v42 )
  {
    LODWORD(v11) = -2147187624;
    v70 = -2147187624;
    v69 = "HRESULT";
    LODWORD(v67) = 832;
    goto LABEL_125;
  }
  LOBYTE(v65) = 0;
  LODWORD(v11) = StringUtility::EncodeString(a2, (char *)this + 256, (char *)v9 + 144, 65001, (_DWORD)v65);
  v70 = v11;
  if ( (int)v11 < 0 )
  {
    v69 = "HRESULT";
    LODWORD(v67) = 841;
    goto LABEL_125;
  }
  *((_QWORD *)v9 + 20) = *((_QWORD *)this + 2);
  *((_QWORD *)v9 + 21) = *((_QWORD *)this + 3);
  v43 = *((_QWORD *)this + 17);
  if ( !v43 || (*((_DWORD *)this + 45) & 0x100) != 0 )
  {
    v45 = L"oct";
    if ( !*((_BYTE *)this + 568) )
      v45 = L"ngc";
    LODWORD(v11) = CreateKeyInfo(
                     a2,
                     v45,
                     (const unsigned __int16 *)((unsigned __int64)L"A128KW" & -(__int64)(*((_BYTE *)this + 568) != 0)),
                     (OAuthResponse *)((char *)this + 528),
                     (struct _AadApPluginTokenInfo *)((char *)v9 + 176));
    v70 = v11;
    if ( (int)v11 < 0 )
    {
      v69 = "HRESULT";
      LODWORD(v67) = 864;
      goto LABEL_125;
    }
  }
  else
  {
    LODWORD(v11) = CreateKeyInfo(
                     a2,
                     *(const unsigned __int16 **)(v43 + 8),
                     *(const unsigned __int16 **)(v43 + 16),
                     (struct _AP_BLOB *)(v43 + 24),
                     (struct _AadApPluginTokenInfo *)((char *)v9 + 176));
    v70 = v11;
    if ( (int)v11 < 0 )
    {
      v69 = "HRESULT";
      LODWORD(v67) = 854;
      goto LABEL_125;
    }
  }
  *((_QWORD *)v9 + 56) = *((_QWORD *)this + 72);
  DuplicateString(a2, *((const unsigned __int16 **)this + 37), v44, (unsigned __int16 **)v9 + 27);
  DuplicateString(a2, *((const unsigned __int16 **)this + 40), v46, (unsigned __int16 **)v9 + 28);
  DuplicateString(a2, *((const unsigned __int16 **)this + 36), v47, (unsigned __int16 **)v9 + 29);
  v49 = (const unsigned __int16 *)*((_QWORD *)this + 63);
  if ( *((_DWORD *)v49 - 4) )
    DuplicateString(a2, v49, v48, (unsigned __int16 **)v9 + 59);
  DuplicateString(a2, v86, v48, (unsigned __int16 **)v9 + 30);
  DuplicateString(a2, *((const unsigned __int16 **)this + 92), v50, (unsigned __int16 **)v9 + 74);
  DuplicateString(a2, *((const unsigned __int16 **)this + 91), v51, (unsigned __int16 **)v9 + 75);
  v52 = *((_QWORD *)this + 18);
  if ( !v52 || (v53 = IsApBlobDefined((struct _AP_BLOB *)(v52 + 24)), LOBYTE(v85) = 1, !v53) )
    LOBYTE(v85) = 0;
  v73 = wcsncmp_0(*((const wchar_t **)this + 19), qword_1800E5A78, *((unsigned int *)qword_1800E5A78 - 4));
  v54 = L"Yes";
  v55 = L"Yes";
  if ( !(_BYTE)v85 )
    v55 = L"No";
  LODWORD(v67) = 896;
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "oauthresponse.cpp", v67, "VSM binding key defined", v55);
  if ( v73 )
    v54 = L"No";
  LODWORD(v68) = 897;
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "oauthresponse.cpp", v68, "Jose content type", v54);
  if ( *(_DWORD *)(*((_QWORD *)this + 75) - 16LL) && *(_DWORD *)(*((_QWORD *)this + 77) - 16LL) )
  {
    LODWORD(v11) = StringUtility::Base64Decode(a2, (char *)this + 616, (char *)v9 + 512);
    v70 = v11;
    if ( (int)v11 < 0 )
    {
      v69 = "HRESULT";
      LODWORD(v67) = 902;
      goto LABEL_125;
    }
    if ( (_BYTE)v85 || !v73 )
    {
      LODWORD(v11) = StringUtility::Base64Decode(a2, (char *)this + 600, (char *)v9 + 528);
      v70 = v11;
      if ( (int)v11 < 0 )
      {
        v69 = "HRESULT";
        LODWORD(v67) = 908;
        goto LABEL_125;
      }
    }
    else
    {
      LODWORD(v11) = OAuthResponse::DecryptResponse(this, (char *)v9 + 176, (char *)this + 600, (char *)v9 + 528);
      v70 = v11;
      if ( (int)v11 < 0 )
      {
        v69 = "HRESULT";
        LODWORD(v67) = 912;
        goto LABEL_125;
      }
    }
    *((_DWORD *)v9 + 136) = *((_DWORD *)this + 152);
    *((_DWORD *)v9 + 137) = *((_DWORD *)this + 164);
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 83) - 16LL) && *(_DWORD *)(*((_QWORD *)this + 85) - 16LL) )
  {
    LODWORD(v11) = StringUtility::Base64Decode(a2, (char *)this + 680, (char *)v9 + 552);
    v70 = v11;
    if ( (int)v11 < 0 )
    {
      v69 = "HRESULT";
      LODWORD(v67) = 922;
      goto LABEL_125;
    }
    if ( (_BYTE)v85 || !v73 )
    {
      LODWORD(v11) = StringUtility::Base64Decode(a2, (char *)this + 664, (char *)v9 + 568);
      v70 = v11;
      if ( (int)v11 < 0 )
      {
        v69 = "HRESULT";
        LODWORD(v67) = 928;
        goto LABEL_125;
      }
    }
    else
    {
      LODWORD(v11) = OAuthResponse::DecryptResponse(this, (char *)v9 + 176, (char *)this + 664, (char *)v9 + 568);
      v70 = v11;
      if ( (int)v11 < 0 )
      {
        v69 = "HRESULT";
        LODWORD(v67) = 932;
        goto LABEL_125;
      }
    }
    *((_DWORD *)v9 + 146) = *((_DWORD *)this + 168);
    *((_DWORD *)v9 + 147) = *((_DWORD *)this + 180);
  }
  if ( (*(__int64 (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a2 + 48LL))(a2) )
    OAuthResponse::SaveDeviceTokenProperties(this);
  v56 = *((_DWORD *)this + 120);
  v57 = v87;
  if ( *((_DWORD *)v87 + 8) != v56 )
  {
    *((_DWORD *)v87 + 8) = v56;
    v83 = *(struct _GUID *)((char *)v57 + 36);
    v58 = RegistryHelper::SetDWORDValue(a2, &v83, L"PrtRefreshTimeout", v56, (bool)v65);
    if ( v58 < 0 )
    {
      LODWORD(v67) = 956;
      LODWORD(v66) = v58;
      WPPTraceLogA(
        3,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        3,
        v66,
        "oauthresponse.cpp",
        v67,
        "RegistryHelper::SetPrtRefreshTimeout error",
        &base);
    }
  }
LABEL_126:
  if ( Sid )
    LocalFree(Sid);
  if ( a2 )
  {
    v59 = v75;
    if ( v75 )
    {
      if ( v71 )
      {
        v60 = 0;
        for ( i = v74; v60 < i; ++v60 )
        {
          v62 = v59[v60];
          if ( v62 )
          {
            LocalFree(v62);
            v59 = v75;
          }
        }
      }
      (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a2 + 16LL))(a2);
    }
    if ( v78 )
      (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a2 + 16LL))(a2);
    AadContextFunctions::LocalFreeApBlob(a2, (struct _AP_BLOB *)Source);
  }
  v63 = v70;
  if ( v70 < 0 )
  {
    ReleaseUserInfoData(a2, a5, v9);
    v63 = v70;
  }
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v84);
  CSecureString::~CSecureString((CSecureString *)&v72);
  return v63;
}

```

## disassembly

```asm
0x1800561a0  mov     rax, rsp
0x1800561a3  mov     [rax+8], rbx
0x1800561a7  mov     [rax+20h], r9
0x1800561ab  mov     [rax+18h], r8
0x1800561af  push    rbp
0x1800561b0  push    rsi
0x1800561b1  push    rdi
0x1800561b2  push    r12
0x1800561b4  push    r13
0x1800561b6  push    r14
0x1800561b8  push    r15
0x1800561ba  lea     rbp, [rax-78h]
0x1800561be  sub     rsp, 140h
0x1800561c5  mov     rbx, r9
0x1800561c8  mov     r14, rdx
0x1800561cb  mov     rsi, rcx
0x1800561ce  xor     edi, edi
0x1800561d0  mov     [rbp+70h+var_F0], edi
0x1800561d3  xorps   xmm0, xmm0
0x1800561d6  xor     eax, eax
0x1800561d8  movups  [rbp+70h+var_A0], xmm0
0x1800561dc  mov     [rbp+70h+var_90], rax
0x1800561e0  movups  [rbp+70h+var_B0], xmm0
0x1800561e4  lea     rcx, [rbp+70h+var_E8]; void *
0x1800561e8  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800561ed  nop
0x1800561ee  mov     [rbp+70h+Sid], rdi
0x1800561f2  mov     [rbp+70h+var_DC], edi
0x1800561f5  mov     [rbp+70h+var_D8], rdi
0x1800561f9  mov     [rbp+70h+var_EC], dil
0x1800561fd  xorps   xmm0, xmm0
0x180056200  movups  [rbp+70h+var_88], xmm0
0x180056204  mov     [rbp+70h+var_B8], rdi
0x180056208  xorps   xmm1, xmm1
0x18005620b  movups  xmmword ptr [rbp+70h+Source], xmm1
0x18005620f  lea     r9, [rbp+70h+var_F0]
0x180056213  lea     r8, aOauthresponseF; "OAuthResponse::FillTokenInfo"
0x18005621a  lea     r15, aOnecoreuapDsEx_66+21h; "oauthresponse.cpp"
0x180056221  mov     rdx, r15
0x180056224  lea     rcx, [rbp+70h+var_60]
0x180056228  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18005622d  nop
0x18005622e  mov     r13, [rbp+70h+arg_28]
0x180056235  test    r14, r14
0x180056238  jz      loc_180056E4C
0x18005623e  mov     rax, [rbp+70h+arg_20]
0x180056245  test    rax, rax
0x180056248  jz      loc_180056E4C
0x18005624e  test    r13, r13
0x180056251  jz      loc_180056E4C
0x180056257  test    rbx, rbx
0x18005625a  jz      loc_180056E4C
0x180056260  mov     [rax], rdi
0x180056263  xor     edx, edx; Val
0x180056265  mov     r8d, 268h; Size
0x18005626b  mov     rcx, r13; void *
0x18005626e  call    memset_0
0x180056273  mov     rdx, [rsi+138h]
0x18005627a  cmp     [rdx-10h], edi
0x18005627d  jz      short loc_18005628D
0x18005627f  lea     rcx, [rbp+70h+var_E8]
0x180056283  call    ??4CSecureString@@QEAAAEAV0@PEBG@Z; CSecureString::operator=(ushort const *)
0x180056288  jmp     loc_180056362
0x18005628d  mov     r8, [rsi+148h]
0x180056294  cmp     [r8-10h], edi
0x180056298  jz      short loc_1800562D8
0x18005629a  lea     rdx, aS_2; "%s "
0x1800562a1  lea     rcx, [rbp+70h+var_E8]
0x1800562a5  call    ?StringAppendFormat@StringUtility@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGZZ; StringUtility::StringAppendFormat(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,...)
0x1800562aa  mov     ecx, eax
0x1800562ac  mov     [rbp+70h+var_F0], eax
0x1800562af  test    eax, eax
0x1800562b1  jns     short loc_1800562D8
0x1800562b3  lea     r12, base
0x1800562ba  mov     [rsp+170h+var_130], r12
0x1800562bf  lea     rax, aHresult; "HRESULT"
0x1800562c6  mov     [rsp+170h+var_138], rax
0x1800562cb  mov     dword ptr [rsp+170h+var_140], 28Ch
0x1800562d3  jmp     loc_180056E74
0x1800562d8  mov     r8, [rsi+150h]
0x1800562df  cmp     [r8-10h], edi
0x1800562e3  jz      short loc_180056323
0x1800562e5  lea     rdx, aS_2; "%s "
0x1800562ec  lea     rcx, [rbp+70h+var_E8]
0x1800562f0  call    ?StringAppendFormat@StringUtility@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGZZ; StringUtility::StringAppendFormat(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,...)
0x1800562f5  mov     ecx, eax
0x1800562f7  mov     [rbp+70h+var_F0], eax
0x1800562fa  test    eax, eax
0x1800562fc  jns     short loc_180056323
0x1800562fe  lea     r12, base
0x180056305  mov     [rsp+170h+var_130], r12
0x18005630a  lea     rax, aHresult; "HRESULT"
0x180056311  mov     [rsp+170h+var_138], rax
0x180056316  mov     dword ptr [rsp+170h+var_140], 290h
0x18005631e  jmp     loc_180056E74
0x180056323  mov     rax, [rbp+70h+var_E8]
0x180056327  cmp     [rax-10h], edi
0x18005632a  jnz     short loc_180056345
0x18005632c  mov     rdx, [rsi+158h]
0x180056333  mov     r8d, [rdx-10h]
0x180056337  test    r8d, r8d
0x18005633a  jz      short loc_180056345
0x18005633c  lea     rcx, [rbp+70h+var_E8]
0x180056340  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180056345  mov     rax, [rbp+70h+var_E8]
0x180056349  cmp     [rax-10h], edi
0x18005634c  jnz     short loc_180056362
0x18005634e  mov     rdx, [rsi+140h]
0x180056355  mov     r8d, [rdx-10h]
0x180056359  lea     rcx, [rbp+70h+var_E8]
0x18005635d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180056362  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GuestUserRDPToAVD@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GuestUserRDPToAVD@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GuestUserRDPToAVD> `wil::Feature<__WilFeatureTraits_Feature_GuestUserRDPToAVD>::GetImpl(void)'::`2'::impl
0x180056369  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GuestUserRDPToAVD@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GuestUserRDPToAVD>::__private_IsEnabled(void)
0x18005636e  test    al, al
0x180056370  jz      short loc_18005639F
0x180056372  mov     rcx, [rsi+200h]
0x180056379  cmp     [rcx-10h], edi
0x18005637c  jz      short loc_18005639F
0x18005637e  mov     rdx, [rsi+208h]
0x180056385  cmp     [rdx-10h], edi
0x180056388  jz      short loc_18005639F
0x18005638a  call    cs:__imp__o__wcsicmp
0x180056390  test    eax, eax
0x180056392  jz      short loc_18005639F
0x180056394  mov     dword ptr [r13+260h], 1
0x18005639f  mov     rcx, [rsi+160h]; StringSid
0x1800563a6  cmp     [rcx-10h], edi
0x1800563a9  jnz     short loc_1800563D5
0x1800563ab  mov     ecx, 80048442h
0x1800563b0  lea     r12, base
0x1800563b7  mov     [rsp+170h+var_130], r12
0x1800563bc  lea     rax, aHresult; "HRESULT"
0x1800563c3  mov     [rsp+170h+var_138], rax
0x1800563c8  mov     dword ptr [rsp+170h+var_140], 2A9h
0x1800563d0  jmp     loc_180056E71
0x1800563d5  lea     rdx, [rbp+70h+Sid]; Sid
0x1800563d9  call    cs:__imp_ConvertStringSidToSidW
0x1800563df  test    eax, eax
0x1800563e1  jnz     short loc_180056424
0x1800563e3  call    cs:__imp_GetLastError
0x1800563e9  mov     ecx, eax
0x1800563eb  test    eax, eax
0x1800563ed  jle     short loc_1800563F8
0x1800563ef  movzx   ecx, ax
0x1800563f2  or      ecx, 80070000h
0x1800563f8  mov     [rbp+70h+var_F0], ecx
0x1800563fb  test    ecx, ecx
0x1800563fd  jns     short loc_180056424
0x1800563ff  lea     r12, base
0x180056406  mov     [rsp+170h+var_130], r12
0x18005640b  lea     rax, aHresult; "HRESULT"
0x180056412  mov     [rsp+170h+var_138], rax
0x180056417  mov     dword ptr [rsp+170h+var_140], 2ADh
0x18005641f  jmp     loc_180056E74
0x180056424  lea     r8, [rsi+198h]
0x18005642b  mov     rax, [r8]
0x18005642e  lea     r12, base
0x180056435  lea     r15, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18005643c  cmp     [rax-10h], edi
0x18005643f  jz      short loc_1800564B8
0x180056441  lea     rdx, [rsi+0C0h]
0x180056448  cmp     [rdx+10h], rdi
0x18005644c  jbe     short loc_1800564B8
0x18005644e  lea     r9, [rsi+168h]
0x180056455  mov     rcx, r14; this
0x180056458  call    ?UpdateSecurityGroups@SecurityGroupsHelper@@SAJPEAVAadContextFunctions@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@4@1@Z; SecurityGroupsHelper::UpdateSecurityGroups(AadContextFunctions *,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x18005645d  mov     ebx, eax
0x18005645f  test    eax, eax
0x180056461  jns     short loc_1800564B8
0x180056463  mov     [rsp+170h+var_130], r12
0x180056468  lea     rax, aSecuritygroups_4; "SecurityGroupsHelper::UpdateSecurityGro"...
0x18005646f  mov     [rsp+170h+var_138], rax
0x180056474  mov     dword ptr [rsp+170h+var_140], 2B5h
0x18005647c  lea     rcx, aOnecoreuapDsEx_66+21h; "oauthresponse.cpp"
0x180056483  mov     [rsp+170h+var_148], rcx
0x180056488  mov     dword ptr [rsp+170h+var_150], ebx
0x18005648c  mov     eax, 3
0x180056491  mov     r9d, eax
0x180056494  mov     r8, r15
0x180056497  xor     edx, edx
0x180056499  mov     ecx, eax
0x18005649b  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800564a0  cmp     byte ptr cs:Microsoft_Windows_AADEnableBits, dil
0x1800564a7  jge     short loc_1800564B8
0x1800564a9  mov     r8d, ebx
0x1800564ac  lea     rdx, Aad_CloudAPPlugin_UpdateSecurityGroupsError
0x1800564b3  call    McTemplateU0d_EventWriteTransfer
0x1800564b8  mov     eax, [rsi+178h]
0x1800564be  mov     [rbp+70h+var_DC], eax
0x1800564c1  test    eax, eax
0x1800564c3  jz      loc_1800565C5
0x1800564c9  mov     ebx, eax
0x1800564cb  shl     rbx, 3
0x1800564cf  mov     rax, [r14]
0x1800564d2  mov     r8, rbx
0x1800564d5  mov     edx, 40h ; '@'
0x1800564da  mov     rcx, r14
0x1800564dd  mov     rax, [rax+8]
0x1800564e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800564e6  mov     rdi, rax
0x1800564e9  mov     [rbp+70h+var_D8], rax
0x1800564ed  test    rax, rax
0x1800564f0  jnz     short loc_180056527
0x1800564f2  mov     [rsp+170h+var_130], r12
0x1800564f7  lea     rax, aHresult; "HRESULT"
0x1800564fe  mov     [rsp+170h+var_138], rax
0x180056503  mov     dword ptr [rsp+170h+var_140], 2C3h
0x18005650b  mov     ecx, 8007000Eh
0x180056510  mov     [rbp+70h+var_F0], ecx
0x180056513  lea     rax, aOnecoreuapDsEx_66+21h; "oauthresponse.cpp"
0x18005651a  mov     [rsp+170h+var_148], rax
0x18005651f  mov     r8, r15
0x180056522  jmp     loc_180056E80
0x180056527  mov     r8, rbx; Size
0x18005652a  xor     edx, edx; Val
0x18005652c  mov     rcx, rdi; void *
0x18005652f  call    memset_0
0x180056534  mov     [rbp+70h+var_EC], 1
0x180056538  xor     eax, eax
0x18005653a  mov     ebx, eax
0x18005653c  mov     rcx, [rsi+168h]
0x180056543  mov     [rbp+70h+arg_8], rcx
0x18005654a  test    rcx, rcx
0x18005654d  jz      short loc_1800565C3
0x18005654f  test    rcx, rcx
0x180056552  jz      loc_180056F5F
0x180056558  movsxd  rax, ebx
0x18005655b  lea     rdx, [rdi+rax*8]; Sid
0x18005655f  mov     rcx, [rcx+10h]; StringSid
0x180056563  call    cs:__imp_ConvertStringSidToSidW
0x180056569  test    eax, eax
0x18005656b  jnz     short loc_180056589
0x18005656d  call    cs:__imp_GetLastError
0x180056573  mov     ecx, eax
0x180056575  test    eax, eax
0x180056577  jle     short loc_180056582
0x180056579  movzx   ecx, cx
0x18005657c  or      ecx, 80070000h
0x180056582  mov     [rbp+70h+var_F0], ecx
0x180056585  test    ecx, ecx
0x180056587  js      short loc_1800565A5
0x180056589  lea     rdx, [rbp+70h+arg_8]
0x180056590  call    ?GetNext@?$CAtlList@UJsonKeyStringValueItem@@V?$CElementTraits@UJsonKeyStringValueItem@@@ATL@@@ATL@@QEAAAEAUJsonKeyStringValueItem@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(__POSITION * &)
0x180056595  mov     rcx, [rbp+70h+arg_8]
0x18005659c  test    rcx, rcx
0x18005659f  jz      short loc_1800565C3
0x1800565a1  inc     ebx
0x1800565a3  jmp     short loc_18005654F
0x1800565a5  mov     [rsp+170h+var_130], r12
0x1800565aa  lea     rax, aHresult; "HRESULT"
0x1800565b1  mov     [rsp+170h+var_138], rax
0x1800565b6  mov     dword ptr [rsp+170h+var_140], 2D1h
0x1800565be  jmp     loc_180056513
0x1800565c3  xor     edi, edi
0x1800565c5  mov     bl, dil
0x1800565c8  mov     rcx, [rsi+1A0h]
0x1800565cf  mov     rax, qword ptr [rbp+70h+var_A0]
0x1800565d3  cmp     [rcx-10h], edi
0x1800565d6  cmovnz  rax, rcx
0x1800565da  mov     qword ptr [rbp+70h+var_A0], rax
0x1800565de  mov     rcx, [rsi+1A8h]
0x1800565e5  mov     rax, qword ptr [rbp+70h+var_A0+8]
0x1800565e9  cmp     [rcx-10h], edi
0x1800565ec  cmovnz  rax, rcx
0x1800565f0  mov     qword ptr [rbp+70h+var_A0+8], rax
0x1800565f4  mov     rcx, [rsi+1B0h]
0x1800565fb  mov     rax, [rbp+70h+var_90]
0x1800565ff  cmp     [rcx-10h], edi
0x180056602  cmovnz  rax, rcx
0x180056606  mov     [rbp+70h+var_90], rax
0x18005660a  mov     ecx, [rsi+1E4h]
0x180056610  mov     rdx, 2B6109100h
0x18005661a  test    ecx, ecx
0x18005661c  jz      short loc_18005663A
0x18005661e  mov     eax, [rsi+10h]
0x180056621  add     eax, ecx
0x180056623  movsxd  rcx, eax
0x180056626  add     rcx, rdx
0x180056629  imul    rax, rcx, 989680h
0x180056630  mov     dword ptr [rbp+70h+var_B0+8], eax
0x180056633  sar     rax, 20h
0x180056637  mov     dword ptr [rbp+70h+var_B0+0Ch], eax
0x18005663a  mov     rax, [rsi+1E8h]
0x180056641  cmp     [rax-10h], edi
0x180056644  jnz     short loc_180056655
0x180056646  lea     rax, aHttpsGoMicroso; "https://go.microsoft.com/fwlink/?LinkId"...
0x18005664d  mov     qword ptr [rbp+70h+var_B0], rax
0x180056651  mov     al, 1
0x180056653  jmp     short loc_18005665C
0x180056655  mov     qword ptr [rbp+70h+var_B0], rax
0x180056659  mov     al, dil
0x18005665c  movzx   eax, al
0x18005665f  mov     [r13+1D0h], eax
0x180056666  mov     dword ptr [r13+0], 3
0x18005666e  lea     rdx, [rsi+1F0h]
0x180056675  mov     rax, [rdx]
0x180056678  cmp     [rax-10h], edi
0x18005667b  jz      loc_180056777
0x180056681  lea     r8, [rbp+70h+Source]
0x180056685  mov     rcx, r14
  ... truncated ...
```
