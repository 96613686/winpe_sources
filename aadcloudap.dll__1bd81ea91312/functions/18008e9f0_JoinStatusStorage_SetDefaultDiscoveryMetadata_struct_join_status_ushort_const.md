# JoinStatusStorage::SetDefaultDiscoveryMetadata(struct_join_status *,ushort const *)

- ea: `0x18008e9f0`
- end: `0x18008f7d8`
- name: `?SetDefaultDiscoveryMetadata@JoinStatusStorage@@CAJPEAUstruct_join_status@@PEBG@Z`
- size: `3560`
- prototype: `static int(struct struct_join_status *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008d760`

## callees

- `0x180004a24`
- `0x180019868`
- `0x180086454`
- `0x180087188`
- `0x1800871b4`
- `0x180087468`
- `0x18008970c`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aad8`
- `0x18008c734`
- `0x18008c848`
- `0x18008c8a0`
- `0x18008cc14`
- `0x18008e9f0`
- `0x18008f7e0`
- `0x18008f81c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008f6a2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008f6a2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18008ef51`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18008ef51`

## string_xrefs

- `0x18008f281`: `https://login.microsoftonline.com`
- `0x18008f440`: `DrsServiceVersion`
- `0x18008f4a7`: `AccessTokenUrl`
- `0x18008f4bf`: `CdjServiceVersion`
- `0x18008f50d`: `NgcServiceVersion`
- `0x18008f58f`: `WebAuthnServiceVersion`
- `0x18008f5a9`: `DeviceManagementServiceVersion`
- `0x18008ec4a`: `https://login.microsoftonline.com/%s/oauth2/token`
- `0x18008ec0c`: `https://login.microsoftonline.com/%s/oauth2/authorize`
- `0x18008ecab`: `https://enterpriseregistration.windows.net/EnrollmentServer/DeviceEnrollmentWebService.svc`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::SetDefaultDiscoveryMetadata(
        struct struct_join_status *a1,
        const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  wchar_t *v5; // r12
  unsigned __int16 *v6; // r15
  _WORD *v7; // r14
  __int64 v8; // rsi
  __int64 v9; // r15
  const unsigned __int16 *v10; // rcx
  int DomainFromEmail; // eax
  const wchar_t *v12; // r8
  unsigned __int64 v13; // r15
  unsigned __int16 *v14; // rax
  unsigned __int64 v15; // rdx
  int BaseUrl; // eax
  wchar_t *v17; // r14
  wchar_t *v18; // rax
  wchar_t *v19; // rbx
  __int64 v20; // rax
  unsigned __int64 v21; // r15
  unsigned __int16 *v22; // rax
  _WORD *v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  unsigned __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rax
  unsigned __int64 v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // rax
  unsigned __int64 v32; // rbx
  const unsigned __int16 *v33; // rcx
  unsigned __int16 *v34; // rcx
  const unsigned __int16 *v35; // rcx
  wchar_t *v36; // r14
  _WORD *v37; // rcx
  __int64 v38; // rax
  unsigned __int64 v39; // rbx
  _WORD *v40; // rax
  unsigned __int16 *v41; // rcx
  int v42; // edx
  unsigned __int16 *v43; // rcx
  unsigned __int16 *v45[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v46; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v47; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v48; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v49; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v50; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v51; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v52; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v53; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v54; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v55; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v56; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v57; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v58; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v59; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v60; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v61; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v62; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v63; // [rsp+100h] [rbp+0h]
  void *v64; // [rsp+108h] [rbp+8h]
  void *v65; // [rsp+110h] [rbp+10h]
  unsigned __int16 *v66; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int16 *v67; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v68; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 *v69; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 *v70; // [rsp+138h] [rbp+38h] BYREF
  unsigned __int16 *v71; // [rsp+180h] [rbp+80h] BYREF
  wchar_t *Str; // [rsp+190h] [rbp+90h] BYREF
  void *Block; // [rsp+198h] [rbp+98h] BYREF

  memset_0(&v46, 0, 0x100u);
  v4 = 0;
  v5 = 0;
  Block = 0;
  v6 = 0;
  v71 = 0;
  Str = 0;
  v45[0] = 0;
  if ( *((_QWORD *)a1 + 9)
    && *((_QWORD *)a1 + 10)
    && *((_QWORD *)a1 + 11)
    && *((_QWORD *)a1 + 12)
    && *((_QWORD *)a1 + 13)
    && *((_QWORD *)a1 + 14)
    && *((_QWORD *)a1 + 15)
    && *((_QWORD *)a1 + 16)
    && *((_QWORD *)a1 + 17)
    && *((_QWORD *)a1 + 18)
    && *((_QWORD *)a1 + 19)
    && *((_QWORD *)a1 + 20)
    && *((_QWORD *)a1 + 21)
    && *((_QWORD *)a1 + 22)
    && *((_QWORD *)a1 + 23)
    && *((_QWORD *)a1 + 24)
    && *((_QWORD *)a1 + 25)
    && *((_QWORD *)a1 + 35)
    && *((_QWORD *)a1 + 36)
    && *((_QWORD *)a1 + 37)
    && *((_QWORD *)a1 + 38)
    && *((_QWORD *)a1 + 39) )
  {
    goto LABEL_142;
  }
  v7 = (_WORD *)*((_QWORD *)a1 + 2);
  v8 = -1;
  if ( v7 && *v7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v7[v9] );
    v6 = (unsigned __int16 *)(v9 + 1);
    goto LABEL_36;
  }
  Logger::TraceWarning(L"%s: TenantId is empty.", L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  v10 = (const unsigned __int16 *)*((_QWORD *)a1 + 3);
  if ( v10 && *v10 )
  {
    DomainFromEmail = GetDomainFromEmail(v10, (unsigned __int16 **)&Block, (unsigned __int64 *)v45);
    v4 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
    {
      v12 = L"GetDomainFromEmail";
LABEL_32:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"JoinStatusStorage::SetDefaultDiscoveryMetadata",
        v12,
        (unsigned int)DomainFromEmail);
      goto LABEL_142;
    }
    v7 = Block;
    v6 = v45[0];
  }
  else
  {
    Logger::TraceWarning(L"%s: JoinUserEmail is empty.", L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  if ( v7 )
  {
LABEL_36:
    if ( *v7 )
    {
      v49 = (unsigned __int16 *)SafeAlloc(2LL * (_QWORD)(v6 + 27));
      if ( !v49 )
      {
LABEL_38:
        v4 = -2147024882;
        Logger::TraceCritical(
          L"%s: Out of memory. Allocation failed.",
          L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
        goto LABEL_142;
      }
      DomainFromEmail = StringCchPrintfW(
                          v49,
                          (unsigned __int64)(v6 + 27),
                          L"https://login.microsoftonline.com/%s/oauth2/authorize",
                          v7);
      v4 = DomainFromEmail;
      if ( DomainFromEmail < 0 )
        goto LABEL_40;
      v13 = (unsigned __int64)(v6 + 25);
      v14 = (unsigned __int16 *)SafeAlloc(2 * v13);
      v50 = v14;
      if ( !v14 )
        goto LABEL_38;
      DomainFromEmail = StringCchPrintfW(v14, v13, L"https://login.microsoftonline.com/%s/oauth2/token", v7);
      v4 = DomainFromEmail;
      if ( DomainFromEmail < 0 )
        goto LABEL_40;
    }
  }
  DomainFromEmail = StringDup(L"1.0", &v71, 0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v46 = v71;
  v71 = 0;
  DomainFromEmail = StringDup(
                      L"https://enterpriseregistration.windows.net/EnrollmentServer/DeviceEnrollmentWebService.svc",
                      &v71,
                      0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v47 = v71;
  v71 = 0;
  DomainFromEmail = StringDup(L"urn:ms-drs:enterpriseregistration.windows.net", &v71, 0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v48 = v71;
  v71 = 0;
  DomainFromEmail = StringDup(L"1.0", &v71, 0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v51 = v71;
  v71 = 0;
  DomainFromEmail = StringDup(L"https://enterpriseregistration.windows.net/EnrollmentServer/device/", &v71, 0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v52 = v71;
  v71 = 0;
  DomainFromEmail = StringDup(L"urn:ms-drs:enterpriseregistration.windows.net", &v71, 0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v53 = v71;
  v71 = 0;
  DomainFromEmail = StringDup(L"1.0", &v71, 0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v54 = v71;
  v71 = 0;
  DomainFromEmail = StringDup(L"https://enterpriseregistration.windows.net/EnrollmentServer/key/", &v71, 0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v55 = v71;
  v71 = 0;
  DomainFromEmail = StringDup(L"urn:ms-drs:enterpriseregistration.windows.net", &v71, 0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v56 = v71;
  v71 = 0;
  DomainFromEmail = StringDup(L"1.0", &v71, 0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v57 = v71;
  v71 = 0;
  DomainFromEmail = StringDup(L"1.0", &v71, 0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v60 = v71;
  v71 = 0;
  DomainFromEmail = StringDup(L"4.0", &v71, 0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v65 = v71;
  v45[0] = *((unsigned __int16 **)a1 + 18);
  v45[1] = *((unsigned __int16 **)a1 + 15);
  v71 = 0;
  SafeFree(0);
  BaseUrl = GetBaseUrl((const unsigned __int16 **)v45, v15, &Str);
  v4 = BaseUrl;
  if ( BaseUrl < 0 )
  {
LABEL_57:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata",
      L"GetBaseUrl",
      (unsigned int)BaseUrl);
    v5 = Str;
    goto LABEL_142;
  }
  v5 = Str;
  v17 = Str;
  if ( !Str || !*Str )
  {
    Logger::TraceWarning(
      L"%s: Cannot parse NGC endpoint to get server string. Use default value.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
    v17 = L"https://enterpriseregistration.windows.net";
  }
  v18 = wcsstr(v17, L"://");
  v19 = v18 + 3;
  if ( !v18 )
    v19 = v17;
  if ( v19 && *v19 )
  {
    v20 = -1;
    do
      ++v20;
    while ( v19[v20] );
    v21 = v20 + 7;
    v22 = (unsigned __int16 *)SafeAlloc(2 * (v20 + 7));
    v71 = v22;
    if ( !v22 )
      goto LABEL_38;
    DomainFromEmail = StringCchPrintfW(v22, v21, L"adrs/%s", v19);
    v4 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
    {
LABEL_40:
      v12 = L"StringCchPrintfW";
      goto LABEL_32;
    }
    goto LABEL_71;
  }
  DomainFromEmail = StringDup(L"adrs/enterpriseregistration.windows.net", &v71, 0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
  {
LABEL_44:
    v12 = L"StringDup";
    goto LABEL_32;
  }
LABEL_71:
  v23 = (_WORD *)*((_QWORD *)a1 + 2);
  v66 = v71;
  v71 = 0;
  if ( v23 && *v23 )
  {
    v24 = -1;
    do
      ++v24;
    while ( v17[v24] );
    v25 = -1;
    do
      ++v25;
    while ( v23[v25] );
    v26 = v25 + v24 + 13;
    v71 = (unsigned __int16 *)SafeAlloc(2 * v26);
    if ( !v71 )
      goto LABEL_38;
    DomainFromEmail = StringCchPrintfW(v71, v26, L"%s/webauthn/%s/", v17, *((_QWORD *)a1 + 2));
    v4 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_40;
    v27 = -1;
    v58 = v71;
    do
      ++v27;
    while ( v17[v27] );
    v28 = -1;
    do
      ++v28;
    while ( *(_WORD *)(*((_QWORD *)a1 + 2) + 2 * v28) );
    v29 = v28 + v27 + 11;
    v71 = (unsigned __int16 *)SafeAlloc(2 * v29);
    if ( !v71 )
      goto LABEL_38;
    DomainFromEmail = StringCchPrintfW(v71, v29, L"%s/manage/%s/", v17, *((_QWORD *)a1 + 2));
    v4 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_40;
    v30 = -1;
    v61 = v71;
    do
      ++v30;
    while ( v17[v30] );
    v31 = -1;
    do
      ++v31;
    while ( *(_WORD *)(*((_QWORD *)a1 + 2) + 2 * v31) );
    v32 = v31 + v30 + 37;
    v71 = (unsigned __int16 *)SafeAlloc(2 * v32);
    if ( !v71 )
      goto LABEL_38;
    DomainFromEmail = StringCchPrintfW(v71, v32, L"%s/EnrollmentServer/device/resource/%s/", v17, *((_QWORD *)a1 + 2));
    v4 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_40;
    v63 = v71;
    v71 = 0;
  }
  else
  {
    Logger::TraceWarning(
      L"%s: Tenant ID is empty. Default WebAuthN and device management endpoint will not be set.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  v33 = (const unsigned __int16 *)*((_QWORD *)a1 + 19);
  if ( !v33 || !*v33 )
    v33 = L"urn:ms-drs:enterpriseregistration.windows.net";
  DomainFromEmail = StringDup(v33, &v71, 0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_96;
  v34 = v71;
  v59 = v71;
  v71 = 0;
  DomainFromEmail = StringDup(v34, &v71, 0);
  v4 = DomainFromEmail;
  if ( DomainFromEmail < 0
    || (v62 = v71, v71 = 0, DomainFromEmail = StringDup(v59, &v71, 0), v4 = DomainFromEmail, DomainFromEmail < 0) )
  {
LABEL_96:
    v12 = L"StringDup";
    goto LABEL_32;
  }
  v64 = v71;
  v71 = 0;
  SafeFree(v5);
  v35 = (const unsigned __int16 *)*((_QWORD *)a1 + 12);
  Str = 0;
  BaseUrl = GetBaseUrl(v35, &Str);
  v4 = BaseUrl;
  if ( BaseUrl < 0 )
    goto LABEL_57;
  v5 = Str;
  v36 = Str;
  if ( !Str || !*Str )
  {
    Logger::TraceWarning(
      L"%s: Cannot parse AuthCodeUrl to get server string. Use default value.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
    v36 = L"https://login.microsoftonline.com";
  }
  v37 = (_WORD *)*((_QWORD *)a1 + 2);
  if ( v37 && *v37 )
  {
    v38 = -1;
    do
      ++v38;
    while ( v36[v38] );
    do
      ++v8;
    while ( v37[v8] );
    v39 = v8 + v38 + 12;
    v71 = (unsigned __int16 *)SafeAlloc(2 * v39);
    if ( !v71 )
      goto LABEL_38;
    DomainFromEmail = StringCchPrintfW(v71, v39, L"%s/%s/kerberos", v36, *((_QWORD *)a1 + 2));
    v4 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_40;
    v67 = v71;
    v71 = 0;
  }
  else
  {
    Logger::TraceWarning(
      L"%s: Tenant ID is empty. Default kerb endpoint will not be set.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  v40 = (_WORD *)*((_QWORD *)a1 + 15);
  v41 = v52;
  if ( !v40 || (v42 = 0, !*v40) )
    v42 = 1;
  if ( !v42 )
    v41 = (unsigned __int16 *)*((_QWORD *)a1 + 15);
  if ( v41 && *v41 )
  {
    DomainFromEmail = GetCertAuthUrl(v41, &v71);
    v4 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
    {
LABEL_121:
      v12 = L"GetCertAuthUrl";
      goto LABEL_32;
    }
    v68 = v71;
    v71 = 0;
  }
  else
  {
    Logger::TraceWarning(
      L"%s: Device join endpoint is empty. Default device join endpoint for TSL will not be set.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  v43 = (unsigned __int16 *)*((_QWORD *)a1 + 24);
  if ( v43 && *v43 || (v43 = v61) != 0 && *v61 )
  {
    DomainFromEmail = GetCertAuthUrl(v43, &v71);
    v4 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_121;
    v69 = v71;
    v71 = 0;
  }
  else
  {
    Logger::TraceWarning(
      L"%s: Device management endpoint is empty. Default device management endpoint for TSL will not be set.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  if ( v63 && *v63 )
  {
    DomainFromEmail = GetCertAuthUrl(v63, &v71);
    v4 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_121;
    v70 = v71;
    v71 = 0;
  }
  else
  {
    Logger::TraceWarning(
      L"%s: Resource account join endpoint is empty. Default resource account join endpoint for TSL will not be set.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  FillJoinStatus((unsigned __int16 **)a1 + 9, (const unsigned __int16 **)&v46, a2, L"DrsServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 10, (const unsigned __int16 **)&v47, a2, L"DrsEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 11, (const unsigned __int16 **)&v48, a2, L"DrsResourceId");
  FillJoinStatus((unsigned __int16 **)a1 + 12, (const unsigned __int16 **)&v49, a2, L"AuthCodeUrl");
  FillJoinStatus((unsigned __int16 **)a1 + 13, (const unsigned __int16 **)&v50, a2, L"AccessTokenUrl");
  FillJoinStatus((unsigned __int16 **)a1 + 14, (const unsigned __int16 **)&v51, a2, L"CdjServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 15, (const unsigned __int16 **)&v52, a2, L"CdjEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 16, (const unsigned __int16 **)&v53, a2, L"CdjResourceId");
  FillJoinStatus((unsigned __int16 **)a1 + 17, (const unsigned __int16 **)&v54, a2, L"NgcServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 18, (const unsigned __int16 **)&v55, a2, L"NgcEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 19, (const unsigned __int16 **)&v56, a2, L"NgcResourceId");
  FillJoinStatus((unsigned __int16 **)a1 + 21, (const unsigned __int16 **)&v58, a2, L"WebAuthnEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 22, (const unsigned __int16 **)&v59, a2, L"WebAuthnResourceId");
  FillJoinStatus((unsigned __int16 **)a1 + 20, (const unsigned __int16 **)&v57, a2, L"WebAuthnServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 23, (const unsigned __int16 **)&v60, a2, L"DeviceManagementServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 24, (const unsigned __int16 **)&v61, a2, L"DeviceManagementEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 25, (const unsigned __int16 **)&v62, a2, L"DeviceManagementResourceId");
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADCloudKerbHaadj>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AADCloudKerbHaadj>::GetImpl'::`2'::impl) )
  {
    FillJoinStatus((unsigned __int16 **)a1 + 35, (const unsigned __int16 **)&v66, a2, L"KerbSpn");
    FillJoinStatus((unsigned __int16 **)a1 + 36, (const unsigned __int16 **)&v67, a2, L"KerbEndpoint");
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::GetImpl'::`2'::impl) )
  {
    FillJoinStatus((unsigned __int16 **)a1 + 37, (const unsigned __int16 **)&v68, a2, L"CdjEndpointTLS");
    FillJoinStatus((unsigned __int16 **)a1 + 38, (const unsigned __int16 **)&v69, a2, L"DeviceManagementEndpointTLS");
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RAforMTRW>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RAforMTRW>::GetImpl'::`2'::impl) )
    FillJoinStatus((unsigned __int16 **)a1 + 39, (const unsigned __int16 **)&v70, a2, L"DeviceJoinResourceEndpointTLS");
LABEL_142:
  free(Block);
  SafeFree(v71);
  SafeFree(v5);
  SafeFree(v46);
  SafeFree(v47);
  SafeFree(v48);
  SafeFree(v49);
  SafeFree(v50);
  SafeFree(v51);
  SafeFree(v52);
  SafeFree(v53);
  SafeFree(v54);
  SafeFree(v55);
  SafeFree(v56);
  SafeFree(v57);
  SafeFree(v58);
  SafeFree(v59);
  SafeFree(v60);
  SafeFree(v61);
  SafeFree(v62);
  SafeFree(v65);
  SafeFree(v63);
  SafeFree(v64);
  SafeFree(v66);
  SafeFree(v67);
  SafeFree(v68);
  SafeFree(v69);
  SafeFree(v70);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"JoinStatusStorage::SetDefaultDiscoveryMetadata", v4);
  return v4;
}

```

## disassembly

```asm
0x18008e9f0  mov     [rsp-8+arg_8], rbx
0x18008e9f5  push    rbp
0x18008e9f6  push    rsi
0x18008e9f7  push    rdi
0x18008e9f8  push    r12
0x18008e9fa  push    r13
0x18008e9fc  push    r14
0x18008e9fe  push    r15
0x18008ea00  lea     rbp, [rsp-40h]
0x18008ea05  sub     rsp, 140h
0x18008ea0c  mov     r13, rdx
0x18008ea0f  mov     rdi, rcx
0x18008ea12  xor     edx, edx; Val
0x18008ea14  lea     rcx, [rsp+170h+var_130]; void *
0x18008ea19  mov     r8d, 100h; Size
0x18008ea1f  call    memset_0
0x18008ea24  xor     ebx, ebx
0x18008ea26  mov     r12d, ebx
0x18008ea29  mov     [rbp+70h+Block], rbx
0x18008ea30  mov     r15d, ebx
0x18008ea33  mov     [rbp+70h+arg_0], rbx
0x18008ea3a  mov     [rbp+70h+Str], rbx
0x18008ea41  mov     [rsp+170h+var_140], rbx
0x18008ea46  cmp     [rdi+48h], rbx
0x18008ea4a  jz      loc_18008EB1B
0x18008ea50  cmp     [rdi+50h], rbx
0x18008ea54  jz      loc_18008EB1B
0x18008ea5a  cmp     [rdi+58h], rbx
0x18008ea5e  jz      loc_18008EB1B
0x18008ea64  cmp     [rdi+60h], rbx
0x18008ea68  jz      loc_18008EB1B
0x18008ea6e  cmp     [rdi+68h], rbx
0x18008ea72  jz      loc_18008EB1B
0x18008ea78  cmp     [rdi+70h], rbx
0x18008ea7c  jz      loc_18008EB1B
0x18008ea82  cmp     [rdi+78h], rbx
0x18008ea86  jz      loc_18008EB1B
0x18008ea8c  cmp     [rdi+80h], rbx
0x18008ea93  jz      loc_18008EB1B
0x18008ea99  cmp     [rdi+88h], rbx
0x18008eaa0  jz      short loc_18008EB1B
0x18008eaa2  cmp     [rdi+90h], rbx
0x18008eaa9  jz      short loc_18008EB1B
0x18008eaab  cmp     [rdi+98h], rbx
0x18008eab2  jz      short loc_18008EB1B
0x18008eab4  cmp     [rdi+0A0h], rbx
0x18008eabb  jz      short loc_18008EB1B
0x18008eabd  cmp     [rdi+0A8h], rbx
0x18008eac4  jz      short loc_18008EB1B
0x18008eac6  cmp     [rdi+0B0h], rbx
0x18008eacd  jz      short loc_18008EB1B
0x18008eacf  cmp     [rdi+0B8h], rbx
0x18008ead6  jz      short loc_18008EB1B
0x18008ead8  cmp     [rdi+0C0h], rbx
0x18008eadf  jz      short loc_18008EB1B
0x18008eae1  cmp     [rdi+0C8h], rbx
0x18008eae8  jz      short loc_18008EB1B
0x18008eaea  cmp     [rdi+118h], rbx
0x18008eaf1  jz      short loc_18008EB1B
0x18008eaf3  cmp     [rdi+120h], rbx
0x18008eafa  jz      short loc_18008EB1B
0x18008eafc  cmp     [rdi+128h], rbx
0x18008eb03  jz      short loc_18008EB1B
0x18008eb05  cmp     [rdi+130h], rbx
0x18008eb0c  jz      short loc_18008EB1B
0x18008eb0e  cmp     [rdi+138h], rbx
0x18008eb15  jnz     loc_18008F69B
0x18008eb1b  mov     r14, [rdi+10h]
0x18008eb1f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008eb23  test    r14, r14
0x18008eb26  jz      short loc_18008EB43
0x18008eb28  cmp     [r14], bx
0x18008eb2c  jz      short loc_18008EB43
0x18008eb2e  mov     r15, rsi
0x18008eb31  inc     r15
0x18008eb34  cmp     [r14+r15*2], bx
0x18008eb39  jnz     short loc_18008EB31
0x18008eb3b  inc     r15
0x18008eb3e  jmp     loc_18008EBC9
0x18008eb43  lea     rdx, aJoinstatusstor_7; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x18008eb4a  lea     rcx, aSTenantidIsEmp; "%s: TenantId is empty."
0x18008eb51  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18008eb56  mov     rcx, [rdi+18h]; unsigned __int16 *
0x18008eb5a  test    rcx, rcx
0x18008eb5d  jz      short loc_18008EBAD
0x18008eb5f  cmp     [rcx], bx
0x18008eb62  jz      short loc_18008EBAD
0x18008eb64  lea     r8, [rsp+170h+var_140]; unsigned __int64 *
0x18008eb69  lea     rdx, [rbp+70h+Block]; unsigned __int16 **
0x18008eb70  call    ?GetDomainFromEmail@@YAJPEBGPEAPEAGPEA_K@Z; GetDomainFromEmail(ushort const *,ushort * *,unsigned __int64 *)
0x18008eb75  mov     ebx, eax
0x18008eb77  test    eax, eax
0x18008eb79  jns     short loc_18008EB9D
0x18008eb7b  lea     r8, aGetdomainfrome; "GetDomainFromEmail"
0x18008eb82  lea     rdx, aJoinstatusstor_7; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x18008eb89  mov     r9d, eax
0x18008eb8c  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18008eb93  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008eb98  jmp     loc_18008F69B
0x18008eb9d  mov     r14, [rbp+70h+Block]
0x18008eba4  xor     ebx, ebx
0x18008eba6  mov     r15, [rsp+170h+var_140]
0x18008ebab  jmp     short loc_18008EBC0
0x18008ebad  lea     rdx, aJoinstatusstor_7; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x18008ebb4  lea     rcx, aSJoinuseremail; "%s: JoinUserEmail is empty."
0x18008ebbb  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18008ebc0  test    r14, r14
0x18008ebc3  jz      loc_18008EC67
0x18008ebc9  cmp     [r14], bx
0x18008ebcd  jz      loc_18008EC67
0x18008ebd3  lea     rbx, [r15+36h]
0x18008ebd7  lea     rcx, [rbx+rbx]; unsigned __int64
0x18008ebdb  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18008ebe0  mov     [rsp+170h+var_118], rax
0x18008ebe5  test    rax, rax
0x18008ebe8  jnz     short loc_18008EC07
0x18008ebea  lea     rdx, aJoinstatusstor_7; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x18008ebf1  mov     ebx, 8007000Eh
0x18008ebf6  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18008ebfd  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18008ec02  jmp     loc_18008F69B
0x18008ec07  mov     rcx, [rsp+170h+var_118]; unsigned __int16 *
0x18008ec0c  lea     r8, aHttpsLoginMicr; "https://login.microsoftonline.com/%s/oa"...
0x18008ec13  mov     r9, r14
0x18008ec16  mov     rdx, rbx; unsigned __int64
0x18008ec19  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008ec1e  mov     ebx, eax
0x18008ec20  test    eax, eax
0x18008ec22  jns     short loc_18008EC30
0x18008ec24  lea     r8, aStringcchprint; "StringCchPrintfW"
0x18008ec2b  jmp     loc_18008EB82
0x18008ec30  add     r15, 32h ; '2'
0x18008ec34  lea     rcx, [r15+r15]; unsigned __int64
0x18008ec38  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18008ec3d  mov     [rsp+170h+var_110], rax
0x18008ec42  test    rax, rax
0x18008ec45  jz      short loc_18008EBEA
0x18008ec47  mov     r9, r14
0x18008ec4a  lea     r8, aHttpsLoginMicr_0; "https://login.microsoftonline.com/%s/oa"...
0x18008ec51  mov     rdx, r15; unsigned __int64
0x18008ec54  mov     rcx, rax; unsigned __int16 *
0x18008ec57  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008ec5c  xor     r15d, r15d
0x18008ec5f  mov     ebx, eax
0x18008ec61  test    eax, eax
0x18008ec63  jns     short loc_18008EC6A
0x18008ec65  jmp     short loc_18008EC24
0x18008ec67  xor     r15d, r15d
0x18008ec6a  lea     r14, a10; "1.0"
0x18008ec71  xor     r8d, r8d; int
0x18008ec74  mov     rcx, r14; unsigned __int16 *
0x18008ec77  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18008ec7e  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18008ec83  mov     ebx, eax
0x18008ec85  test    eax, eax
0x18008ec87  jns     short loc_18008EC95
0x18008ec89  lea     r8, aStringdup; "StringDup"
0x18008ec90  jmp     loc_18008EB82
0x18008ec95  mov     rax, [rbp+70h+arg_0]
0x18008ec9c  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18008eca3  xor     r8d, r8d; int
0x18008eca6  mov     [rsp+170h+var_130], rax
0x18008ecab  lea     rcx, aHttpsEnterpris; "https://enterpriseregistration.windows."...
0x18008ecb2  mov     [rbp+70h+arg_0], r15
0x18008ecb9  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18008ecbe  mov     ebx, eax
0x18008ecc0  test    eax, eax
0x18008ecc2  js      short loc_18008EC89
0x18008ecc4  mov     rax, [rbp+70h+arg_0]
0x18008eccb  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18008ecd2  xor     r8d, r8d; int
0x18008ecd5  mov     [rsp+170h+var_128], rax
0x18008ecda  lea     rcx, aUrnMsDrsEnterp; "urn:ms-drs:enterpriseregistration.windo"...
0x18008ece1  mov     [rbp+70h+arg_0], r15
0x18008ece8  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18008eced  mov     ebx, eax
0x18008ecef  test    eax, eax
0x18008ecf1  js      short loc_18008EC89
0x18008ecf3  mov     rax, [rbp+70h+arg_0]
0x18008ecfa  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18008ed01  xor     r8d, r8d; int
0x18008ed04  mov     [rsp+170h+var_120], rax
0x18008ed09  mov     rcx, r14; unsigned __int16 *
0x18008ed0c  mov     [rbp+70h+arg_0], r15
0x18008ed13  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18008ed18  mov     ebx, eax
0x18008ed1a  test    eax, eax
0x18008ed1c  js      loc_18008EC89
0x18008ed22  mov     rax, [rbp+70h+arg_0]
0x18008ed29  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18008ed30  xor     r8d, r8d; int
0x18008ed33  mov     [rsp+170h+var_108], rax
0x18008ed38  lea     rcx, aHttpsEnterpris_2; "https://enterpriseregistration.windows."...
0x18008ed3f  mov     [rbp+70h+arg_0], r15
0x18008ed46  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18008ed4b  mov     ebx, eax
0x18008ed4d  test    eax, eax
0x18008ed4f  js      loc_18008EC89
0x18008ed55  mov     rax, [rbp+70h+arg_0]
0x18008ed5c  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18008ed63  xor     r8d, r8d; int
0x18008ed66  mov     [rsp+170h+var_100], rax
0x18008ed6b  lea     rcx, aUrnMsDrsEnterp; "urn:ms-drs:enterpriseregistration.windo"...
0x18008ed72  mov     [rbp+70h+arg_0], r15
0x18008ed79  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18008ed7e  mov     ebx, eax
0x18008ed80  test    eax, eax
0x18008ed82  js      loc_18008EC89
0x18008ed88  mov     rax, [rbp+70h+arg_0]
0x18008ed8f  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18008ed96  xor     r8d, r8d; int
0x18008ed99  mov     [rsp+170h+var_F8], rax
0x18008ed9e  mov     rcx, r14; unsigned __int16 *
0x18008eda1  mov     [rbp+70h+arg_0], r15
0x18008eda8  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18008edad  mov     ebx, eax
0x18008edaf  test    eax, eax
0x18008edb1  js      loc_18008EC89
0x18008edb7  mov     rax, [rbp+70h+arg_0]
0x18008edbe  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18008edc5  xor     r8d, r8d; int
0x18008edc8  mov     [rbp+70h+var_F0], rax
0x18008edcc  lea     rcx, aHttpsEnterpris_0; "https://enterpriseregistration.windows."...
0x18008edd3  mov     [rbp+70h+arg_0], r15
0x18008edda  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18008eddf  mov     ebx, eax
0x18008ede1  test    eax, eax
0x18008ede3  js      loc_18008EC89
0x18008ede9  mov     rax, [rbp+70h+arg_0]
0x18008edf0  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18008edf7  xor     r8d, r8d; int
0x18008edfa  mov     [rbp+70h+var_E8], rax
0x18008edfe  lea     rcx, aUrnMsDrsEnterp; "urn:ms-drs:enterpriseregistration.windo"...
0x18008ee05  mov     [rbp+70h+arg_0], r15
0x18008ee0c  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18008ee11  mov     ebx, eax
0x18008ee13  test    eax, eax
0x18008ee15  js      loc_18008EC89
0x18008ee1b  mov     rax, [rbp+70h+arg_0]
0x18008ee22  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18008ee29  xor     r8d, r8d; int
0x18008ee2c  mov     [rbp+70h+var_E0], rax
0x18008ee30  mov     rcx, r14; unsigned __int16 *
0x18008ee33  mov     [rbp+70h+arg_0], r15
0x18008ee3a  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18008ee3f  mov     ebx, eax
0x18008ee41  test    eax, eax
0x18008ee43  js      loc_18008EC89
0x18008ee49  mov     rax, [rbp+70h+arg_0]
0x18008ee50  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18008ee57  xor     r8d, r8d; int
0x18008ee5a  mov     [rbp+70h+var_D8], rax
0x18008ee5e  mov     rcx, r14; unsigned __int16 *
0x18008ee61  mov     [rbp+70h+arg_0], r15
0x18008ee68  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18008ee6d  mov     ebx, eax
0x18008ee6f  test    eax, eax
0x18008ee71  js      loc_18008EC89
0x18008ee77  mov     rax, [rbp+70h+arg_0]
0x18008ee7e  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18008ee85  xor     r8d, r8d; int
0x18008ee88  mov     [rbp+70h+var_C0], rax
0x18008ee8c  lea     rcx, a40; "4.0"
0x18008ee93  mov     [rbp+70h+arg_0], r15
0x18008ee9a  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18008ee9f  mov     ebx, eax
0x18008eea1  test    eax, eax
0x18008eea3  js      loc_18008EC89
0x18008eea9  mov     rax, [rbp+70h+arg_0]
0x18008eeb0  xor     ecx, ecx; void *
0x18008eeb2  mov     [rbp+70h+var_60], rax
0x18008eeb6  mov     rax, [rdi+90h]
0x18008eebd  mov     [rsp+170h+var_140], rax
0x18008eec2  mov     rax, [rdi+78h]
0x18008eec6  mov     [rsp+170h+var_138], rax
0x18008eecb  mov     [rbp+70h+arg_0], r15
0x18008eed2  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008eed7  lea     r8, [rbp+70h+Str]; unsigned __int16 **
0x18008eede  lea     rcx, [rsp+170h+var_140]; unsigned __int16 **
0x18008eee3  call    ?GetBaseUrl@@YAJPEAPEBG_KPEAPEAG@Z; GetBaseUrl(ushort const * *,unsigned __int64,ushort * *)
0x18008eee8  mov     ebx, eax
0x18008eeea  test    eax, eax
0x18008eeec  jns     short loc_18008EF17
0x18008eeee  lea     rdx, aJoinstatusstor_7; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x18008eef5  lea     r8, aGetbaseurl; "GetBaseUrl"
0x18008eefc  mov     r9d, eax
0x18008eeff  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18008ef06  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008ef0b  mov     r12, [rbp+70h+Str]
0x18008ef12  jmp     loc_18008F69B
0x18008ef17  mov     r12, [rbp+70h+Str]
0x18008ef1e  mov     r14, r12
0x18008ef21  test    r12, r12
0x18008ef24  jz      short loc_18008EF2D
0x18008ef26  cmp     [r12], r15w
0x18008ef2b  jnz     short loc_18008EF47
0x18008ef2d  lea     rdx, aJoinstatusstor_7; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x18008ef34  lea     rcx, aSCannotParseNg; "%s: Cannot parse NGC endpoint to get se"...
0x18008ef3b  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18008ef40  lea     r14, aHttpsEnterpris_1; "https://enterpriseregistration.windows."...
  ... truncated ...
```
