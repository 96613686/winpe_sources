# JoinStatusStorage::SetDefaultDiscoveryMetadata(struct_join_status *,ushort const *)

- ea: `0x18007eee0`
- end: `0x18007fc97`
- name: `?SetDefaultDiscoveryMetadata@JoinStatusStorage@@CAJPEAUstruct_join_status@@PEBG@Z`
- size: `3511`
- prototype: `static int(struct struct_join_status *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18007e710`

## callees

- `0x180007db4`
- `0x1800084c8`
- `0x18000ddc8`
- `0x18006b2c0`
- `0x1800793bc`
- `0x180079de0`
- `0x18007a058`
- `0x18007bea4`
- `0x18007d17c`
- `0x18007d1b8`
- `0x18007d22c`
- `0x18007d268`
- `0x18007d7e8`
- `0x18007d82c`
- `0x18007d884`
- `0x18007dbf4`
- `0x18007eee0`
- `0x18007fca0`
- `0x18007fcdc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18007f41d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18007f41d`

## string_xrefs

- `0x18007f900`: `DrsServiceVersion`
- `0x18007f967`: `AccessTokenUrl`
- `0x18007f9cd`: `NgcServiceVersion`
- `0x18007f97f`: `CdjServiceVersion`
- `0x18007fa4f`: `WebAuthnServiceVersion`
- `0x18007fa69`: `DeviceManagementServiceVersion`
- `0x18007f0fc`: `https://login.microsoftonline.com/%s/oauth2/authorize`
- `0x18007f190`: `https://enterpriseregistration.windows.net/EnrollmentServer/DeviceEnrollmentWebService.svc`
- `0x18007f13a`: `https://login.microsoftonline.com/%s/oauth2/token`
- `0x18007f741`: `https://login.microsoftonline.com`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::SetDefaultDiscoveryMetadata(
        struct struct_join_status *a1,
        const unsigned __int16 *a2)
{
  int v4; // r8d
  unsigned int v5; // ebx
  wchar_t *v6; // r12
  unsigned __int16 *v7; // r15
  _WORD *v8; // r14
  __int64 v9; // rsi
  __int64 v10; // r15
  const unsigned __int16 *v11; // rcx
  int DomainFromEmail; // eax
  const wchar_t *v13; // r8
  unsigned __int64 v14; // r15
  unsigned __int16 *v15; // rax
  int v16; // r8d
  int v17; // r8d
  int v18; // r8d
  int v19; // r8d
  int v20; // r8d
  int v21; // r8d
  int v22; // r8d
  int v23; // r8d
  int v24; // r8d
  int v25; // r8d
  int v26; // r8d
  unsigned __int64 v27; // rdx
  int BaseUrl; // eax
  wchar_t *v29; // r14
  wchar_t *v30; // rax
  int v31; // r8d
  wchar_t *v32; // rbx
  __int64 v33; // rax
  unsigned __int64 v34; // r15
  unsigned __int16 *v35; // rax
  _WORD *v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // rax
  unsigned __int64 v39; // rbx
  __int64 v40; // rcx
  __int64 v41; // rax
  unsigned __int64 v42; // rbx
  __int64 v43; // rcx
  __int64 v44; // rax
  unsigned __int64 v45; // rbx
  int v46; // r8d
  const unsigned __int16 *v47; // rcx
  int v48; // r8d
  unsigned __int16 *v49; // rcx
  int v50; // r8d
  const unsigned __int16 *v51; // rcx
  wchar_t *v52; // r14
  _WORD *v53; // rcx
  __int64 v54; // rax
  unsigned __int64 v55; // rbx
  _WORD *v56; // rax
  unsigned __int16 *v57; // rcx
  int v58; // edx
  unsigned __int16 *v59; // rcx
  unsigned __int16 *v61[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v62; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v63; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v64; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v65; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v66; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v67; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v68; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v69; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v70; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v71; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v72; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v73; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v74; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v75; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v76; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v77; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v78; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v79; // [rsp+100h] [rbp+0h]
  void *v80; // [rsp+108h] [rbp+8h]
  void *v81; // [rsp+110h] [rbp+10h]
  unsigned __int16 *v82; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int16 *v83; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v84; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 *v85; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 *v86; // [rsp+138h] [rbp+38h] BYREF
  unsigned __int16 *v87; // [rsp+180h] [rbp+80h] BYREF
  wchar_t *Str; // [rsp+190h] [rbp+90h] BYREF
  void *Block; // [rsp+198h] [rbp+98h] BYREF

  memset_0(&v62, 0, 0x100u);
  v5 = 0;
  v6 = 0;
  Block = 0;
  v7 = 0;
  v87 = 0;
  Str = 0;
  v61[0] = 0;
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
  v8 = (_WORD *)*((_QWORD *)a1 + 2);
  v9 = -1;
  if ( v8 && *v8 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v8[v10] );
    v7 = (unsigned __int16 *)(v10 + 1);
    goto LABEL_36;
  }
  Logger::TraceWarning(L"%s: TenantId is empty.", L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  v11 = (const unsigned __int16 *)*((_QWORD *)a1 + 3);
  if ( v11 && *v11 )
  {
    DomainFromEmail = GetDomainFromEmail(v11, (unsigned __int16 **)&Block, (unsigned __int64 *)v61);
    v5 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
    {
      v13 = L"GetDomainFromEmail";
LABEL_32:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"JoinStatusStorage::SetDefaultDiscoveryMetadata",
        v13,
        (unsigned int)DomainFromEmail);
      goto LABEL_142;
    }
    v8 = Block;
    v7 = v61[0];
  }
  else
  {
    Logger::TraceWarning(L"%s: JoinUserEmail is empty.", L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  if ( v8 )
  {
LABEL_36:
    if ( *v8 )
    {
      v65 = (unsigned __int16 *)MIDL_user_allocate(2LL * (_QWORD)(v7 + 27));
      if ( !v65 )
      {
LABEL_38:
        v5 = -2147024882;
        Logger::TraceCritical(
          L"%s: Out of memory. Allocation failed.",
          L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
        goto LABEL_142;
      }
      DomainFromEmail = StringCchPrintfW(
                          v65,
                          (unsigned __int64)(v7 + 27),
                          L"https://login.microsoftonline.com/%s/oauth2/authorize",
                          v8);
      v5 = DomainFromEmail;
      if ( DomainFromEmail < 0 )
        goto LABEL_40;
      v14 = (unsigned __int64)(v7 + 25);
      v15 = (unsigned __int16 *)MIDL_user_allocate(2 * v14);
      v66 = v15;
      if ( !v15 )
        goto LABEL_38;
      DomainFromEmail = StringCchPrintfW(v15, v14, L"https://login.microsoftonline.com/%s/oauth2/token", v8);
      v5 = DomainFromEmail;
      if ( DomainFromEmail < 0 )
        goto LABEL_40;
    }
  }
  DomainFromEmail = StringDup(L"1.0", &v87, v4);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v62 = v87;
  v87 = 0;
  DomainFromEmail = StringDup(
                      L"https://enterpriseregistration.windows.net/EnrollmentServer/DeviceEnrollmentWebService.svc",
                      &v87,
                      v16);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v63 = v87;
  v87 = 0;
  DomainFromEmail = StringDup(L"urn:ms-drs:enterpriseregistration.windows.net", &v87, v17);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v64 = v87;
  v87 = 0;
  DomainFromEmail = StringDup(L"1.0", &v87, v18);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v67 = v87;
  v87 = 0;
  DomainFromEmail = StringDup(L"https://enterpriseregistration.windows.net/EnrollmentServer/device/", &v87, v19);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v68 = v87;
  v87 = 0;
  DomainFromEmail = StringDup(L"urn:ms-drs:enterpriseregistration.windows.net", &v87, v20);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v69 = v87;
  v87 = 0;
  DomainFromEmail = StringDup(L"1.0", &v87, v21);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v70 = v87;
  v87 = 0;
  DomainFromEmail = StringDup(L"https://enterpriseregistration.windows.net/EnrollmentServer/key/", &v87, v22);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v71 = v87;
  v87 = 0;
  DomainFromEmail = StringDup(L"urn:ms-drs:enterpriseregistration.windows.net", &v87, v23);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v72 = v87;
  v87 = 0;
  DomainFromEmail = StringDup(L"1.0", &v87, v24);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v73 = v87;
  v87 = 0;
  DomainFromEmail = StringDup(L"1.0", &v87, v25);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v76 = v87;
  v87 = 0;
  DomainFromEmail = StringDup(L"4.0", &v87, v26);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_44;
  v81 = v87;
  v61[0] = *((unsigned __int16 **)a1 + 18);
  v61[1] = *((unsigned __int16 **)a1 + 15);
  v87 = 0;
  SafeFree(0);
  BaseUrl = GetBaseUrl((const unsigned __int16 **)v61, v27, &Str);
  v5 = BaseUrl;
  if ( BaseUrl < 0 )
  {
LABEL_57:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata",
      L"GetBaseUrl",
      (unsigned int)BaseUrl);
    v6 = Str;
    goto LABEL_142;
  }
  v6 = Str;
  v29 = Str;
  if ( !Str || !*Str )
  {
    Logger::TraceWarning(
      L"%s: Cannot parse NGC endpoint to get server string. Use default value.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
    v29 = L"https://enterpriseregistration.windows.net";
  }
  v30 = wcsstr(v29, L"://");
  v32 = v30 + 3;
  if ( !v30 )
    v32 = v29;
  if ( v32 && *v32 )
  {
    v33 = -1;
    do
      ++v33;
    while ( v32[v33] );
    v34 = v33 + 7;
    v35 = (unsigned __int16 *)MIDL_user_allocate(2 * (v33 + 7));
    v87 = v35;
    if ( !v35 )
      goto LABEL_38;
    DomainFromEmail = StringCchPrintfW(v35, v34, L"adrs/%s", v32);
    v5 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
    {
LABEL_40:
      v13 = L"StringCchPrintfW";
      goto LABEL_32;
    }
    goto LABEL_71;
  }
  DomainFromEmail = StringDup(L"adrs/enterpriseregistration.windows.net", &v87, v31);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
  {
LABEL_44:
    v13 = L"StringDup";
    goto LABEL_32;
  }
LABEL_71:
  v36 = (_WORD *)*((_QWORD *)a1 + 2);
  v82 = v87;
  v87 = 0;
  if ( v36 && *v36 )
  {
    v37 = -1;
    do
      ++v37;
    while ( v29[v37] );
    v38 = -1;
    do
      ++v38;
    while ( v36[v38] );
    v39 = v38 + v37 + 13;
    v87 = (unsigned __int16 *)MIDL_user_allocate(2 * v39);
    if ( !v87 )
      goto LABEL_38;
    DomainFromEmail = StringCchPrintfW(v87, v39, L"%s/webauthn/%s/", v29, *((_QWORD *)a1 + 2));
    v5 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_40;
    v40 = -1;
    v74 = v87;
    do
      ++v40;
    while ( v29[v40] );
    v41 = -1;
    do
      ++v41;
    while ( *(_WORD *)(*((_QWORD *)a1 + 2) + 2 * v41) );
    v42 = v41 + v40 + 11;
    v87 = (unsigned __int16 *)MIDL_user_allocate(2 * v42);
    if ( !v87 )
      goto LABEL_38;
    DomainFromEmail = StringCchPrintfW(v87, v42, L"%s/manage/%s/", v29, *((_QWORD *)a1 + 2));
    v5 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_40;
    v43 = -1;
    v77 = v87;
    do
      ++v43;
    while ( v29[v43] );
    v44 = -1;
    do
      ++v44;
    while ( *(_WORD *)(*((_QWORD *)a1 + 2) + 2 * v44) );
    v45 = v44 + v43 + 37;
    v87 = (unsigned __int16 *)MIDL_user_allocate(2 * v45);
    if ( !v87 )
      goto LABEL_38;
    DomainFromEmail = StringCchPrintfW(v87, v45, L"%s/EnrollmentServer/device/resource/%s/", v29, *((_QWORD *)a1 + 2));
    v5 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_40;
    v79 = v87;
    v87 = 0;
  }
  else
  {
    Logger::TraceWarning(
      L"%s: Tenant ID is empty. Default WebAuthN and device management endpoint will not be set.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  v47 = (const unsigned __int16 *)*((_QWORD *)a1 + 19);
  if ( !v47 || !*v47 )
    v47 = L"urn:ms-drs:enterpriseregistration.windows.net";
  DomainFromEmail = StringDup(v47, &v87, v46);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_96;
  v49 = v87;
  v75 = v87;
  v87 = 0;
  DomainFromEmail = StringDup(v49, &v87, v48);
  v5 = DomainFromEmail;
  if ( DomainFromEmail < 0
    || (v78 = v87, v87 = 0, DomainFromEmail = StringDup(v75, &v87, v50), v5 = DomainFromEmail, DomainFromEmail < 0) )
  {
LABEL_96:
    v13 = L"StringDup";
    goto LABEL_32;
  }
  v80 = v87;
  v87 = 0;
  SafeFree(v6);
  v51 = (const unsigned __int16 *)*((_QWORD *)a1 + 12);
  Str = 0;
  BaseUrl = GetBaseUrl(v51, &Str);
  v5 = BaseUrl;
  if ( BaseUrl < 0 )
    goto LABEL_57;
  v6 = Str;
  v52 = Str;
  if ( !Str || !*Str )
  {
    Logger::TraceWarning(
      L"%s: Cannot parse AuthCodeUrl to get server string. Use default value.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
    v52 = L"https://login.microsoftonline.com";
  }
  v53 = (_WORD *)*((_QWORD *)a1 + 2);
  if ( v53 && *v53 )
  {
    v54 = -1;
    do
      ++v54;
    while ( v52[v54] );
    do
      ++v9;
    while ( v53[v9] );
    v55 = v9 + v54 + 12;
    v87 = (unsigned __int16 *)MIDL_user_allocate(2 * v55);
    if ( !v87 )
      goto LABEL_38;
    DomainFromEmail = StringCchPrintfW(v87, v55, L"%s/%s/kerberos", v52, *((_QWORD *)a1 + 2));
    v5 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_40;
    v83 = v87;
    v87 = 0;
  }
  else
  {
    Logger::TraceWarning(
      L"%s: Tenant ID is empty. Default kerb endpoint will not be set.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  v56 = (_WORD *)*((_QWORD *)a1 + 15);
  v57 = v68;
  if ( !v56 || (v58 = 0, !*v56) )
    v58 = 1;
  if ( !v58 )
    v57 = (unsigned __int16 *)*((_QWORD *)a1 + 15);
  if ( v57 && *v57 )
  {
    DomainFromEmail = GetCertAuthUrl(v57, &v87);
    v5 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
    {
LABEL_121:
      v13 = L"GetCertAuthUrl";
      goto LABEL_32;
    }
    v84 = v87;
    v87 = 0;
  }
  else
  {
    Logger::TraceWarning(
      L"%s: Device join endpoint is empty. Default device join endpoint for TSL will not be set.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  v59 = (unsigned __int16 *)*((_QWORD *)a1 + 24);
  if ( v59 && *v59 || (v59 = v77) != 0 && *v77 )
  {
    DomainFromEmail = GetCertAuthUrl(v59, &v87);
    v5 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_121;
    v85 = v87;
    v87 = 0;
  }
  else
  {
    Logger::TraceWarning(
      L"%s: Device management endpoint is empty. Default device management endpoint for TSL will not be set.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  if ( v79 && *v79 )
  {
    DomainFromEmail = GetCertAuthUrl(v79, &v87);
    v5 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_121;
    v86 = v87;
    v87 = 0;
  }
  else
  {
    Logger::TraceWarning(
      L"%s: Resource account join endpoint is empty. Default resource account join endpoint for TSL will not be set.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  FillJoinStatus((unsigned __int16 **)a1 + 9, (const unsigned __int16 **)&v62, a2, L"DrsServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 10, (const unsigned __int16 **)&v63, a2, L"DrsEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 11, (const unsigned __int16 **)&v64, a2, L"DrsResourceId");
  FillJoinStatus((unsigned __int16 **)a1 + 12, (const unsigned __int16 **)&v65, a2, L"AuthCodeUrl");
  FillJoinStatus((unsigned __int16 **)a1 + 13, (const unsigned __int16 **)&v66, a2, L"AccessTokenUrl");
  FillJoinStatus((unsigned __int16 **)a1 + 14, (const unsigned __int16 **)&v67, a2, L"CdjServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 15, (const unsigned __int16 **)&v68, a2, L"CdjEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 16, (const unsigned __int16 **)&v69, a2, L"CdjResourceId");
  FillJoinStatus((unsigned __int16 **)a1 + 17, (const unsigned __int16 **)&v70, a2, L"NgcServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 18, (const unsigned __int16 **)&v71, a2, L"NgcEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 19, (const unsigned __int16 **)&v72, a2, L"NgcResourceId");
  FillJoinStatus((unsigned __int16 **)a1 + 21, (const unsigned __int16 **)&v74, a2, L"WebAuthnEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 22, (const unsigned __int16 **)&v75, a2, L"WebAuthnResourceId");
  FillJoinStatus((unsigned __int16 **)a1 + 20, (const unsigned __int16 **)&v73, a2, L"WebAuthnServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 23, (const unsigned __int16 **)&v76, a2, L"DeviceManagementServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 24, (const unsigned __int16 **)&v77, a2, L"DeviceManagementEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 25, (const unsigned __int16 **)&v78, a2, L"DeviceManagementResourceId");
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADCloudKerbHaadj>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AADCloudKerbHaadj>::GetImpl'::`2'::impl) )
  {
    FillJoinStatus((unsigned __int16 **)a1 + 35, (const unsigned __int16 **)&v82, a2, L"KerbSpn");
    FillJoinStatus((unsigned __int16 **)a1 + 36, (const unsigned __int16 **)&v83, a2, L"KerbEndpoint");
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::GetImpl'::`2'::impl) )
  {
    FillJoinStatus((unsigned __int16 **)a1 + 37, (const unsigned __int16 **)&v84, a2, L"CdjEndpointTLS");
    FillJoinStatus((unsigned __int16 **)a1 + 38, (const unsigned __int16 **)&v85, a2, L"DeviceManagementEndpointTLS");
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RAforMTRW>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RAforMTRW>::GetImpl'::`2'::impl) )
    FillJoinStatus((unsigned __int16 **)a1 + 39, (const unsigned __int16 **)&v86, a2, L"DeviceJoinResourceEndpointTLS");
LABEL_142:
  operator delete(Block);
  SafeFree(v87);
  SafeFree(v6);
  SafeFree(v62);
  SafeFree(v63);
  SafeFree(v64);
  SafeFree(v65);
  SafeFree(v66);
  SafeFree(v67);
  SafeFree(v68);
  SafeFree(v69);
  SafeFree(v70);
  SafeFree(v71);
  SafeFree(v72);
  SafeFree(v73);
  SafeFree(v74);
  SafeFree(v75);
  SafeFree(v76);
  SafeFree(v77);
  SafeFree(v78);
  SafeFree(v81);
  SafeFree(v79);
  SafeFree(v80);
  SafeFree(v82);
  SafeFree(v83);
  SafeFree(v84);
  SafeFree(v85);
  SafeFree(v86);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"JoinStatusStorage::SetDefaultDiscoveryMetadata", v5);
  return v5;
}

```

## disassembly

```asm
0x18007eee0  mov     [rsp-8+arg_8], rbx
0x18007eee5  push    rbp
0x18007eee6  push    rsi
0x18007eee7  push    rdi
0x18007eee8  push    r12
0x18007eeea  push    r13
0x18007eeec  push    r14
0x18007eeee  push    r15
0x18007eef0  lea     rbp, [rsp-40h]
0x18007eef5  sub     rsp, 140h
0x18007eefc  mov     r13, rdx
0x18007eeff  mov     rdi, rcx
0x18007ef02  xor     edx, edx; Val
0x18007ef04  lea     rcx, [rsp+170h+var_130]; void *
0x18007ef09  mov     r8d, 100h; Size
0x18007ef0f  call    memset_0
0x18007ef14  xor     ebx, ebx
0x18007ef16  mov     r12d, ebx
0x18007ef19  mov     [rbp+70h+Block], rbx
0x18007ef20  mov     r15d, ebx
0x18007ef23  mov     [rbp+70h+arg_0], rbx
0x18007ef2a  mov     [rbp+70h+Str], rbx
0x18007ef31  mov     [rsp+170h+var_140], rbx
0x18007ef36  cmp     [rdi+48h], rbx
0x18007ef3a  jz      loc_18007F00B
0x18007ef40  cmp     [rdi+50h], rbx
0x18007ef44  jz      loc_18007F00B
0x18007ef4a  cmp     [rdi+58h], rbx
0x18007ef4e  jz      loc_18007F00B
0x18007ef54  cmp     [rdi+60h], rbx
0x18007ef58  jz      loc_18007F00B
0x18007ef5e  cmp     [rdi+68h], rbx
0x18007ef62  jz      loc_18007F00B
0x18007ef68  cmp     [rdi+70h], rbx
0x18007ef6c  jz      loc_18007F00B
0x18007ef72  cmp     [rdi+78h], rbx
0x18007ef76  jz      loc_18007F00B
0x18007ef7c  cmp     [rdi+80h], rbx
0x18007ef83  jz      loc_18007F00B
0x18007ef89  cmp     [rdi+88h], rbx
0x18007ef90  jz      short loc_18007F00B
0x18007ef92  cmp     [rdi+90h], rbx
0x18007ef99  jz      short loc_18007F00B
0x18007ef9b  cmp     [rdi+98h], rbx
0x18007efa2  jz      short loc_18007F00B
0x18007efa4  cmp     [rdi+0A0h], rbx
0x18007efab  jz      short loc_18007F00B
0x18007efad  cmp     [rdi+0A8h], rbx
0x18007efb4  jz      short loc_18007F00B
0x18007efb6  cmp     [rdi+0B0h], rbx
0x18007efbd  jz      short loc_18007F00B
0x18007efbf  cmp     [rdi+0B8h], rbx
0x18007efc6  jz      short loc_18007F00B
0x18007efc8  cmp     [rdi+0C0h], rbx
0x18007efcf  jz      short loc_18007F00B
0x18007efd1  cmp     [rdi+0C8h], rbx
0x18007efd8  jz      short loc_18007F00B
0x18007efda  cmp     [rdi+118h], rbx
0x18007efe1  jz      short loc_18007F00B
0x18007efe3  cmp     [rdi+120h], rbx
0x18007efea  jz      short loc_18007F00B
0x18007efec  cmp     [rdi+128h], rbx
0x18007eff3  jz      short loc_18007F00B
0x18007eff5  cmp     [rdi+130h], rbx
0x18007effc  jz      short loc_18007F00B
0x18007effe  cmp     [rdi+138h], rbx
0x18007f005  jnz     loc_18007FB5B
0x18007f00b  mov     r14, [rdi+10h]
0x18007f00f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18007f013  test    r14, r14
0x18007f016  jz      short loc_18007F033
0x18007f018  cmp     [r14], bx
0x18007f01c  jz      short loc_18007F033
0x18007f01e  mov     r15, rsi
0x18007f021  inc     r15
0x18007f024  cmp     [r14+r15*2], bx
0x18007f029  jnz     short loc_18007F021
0x18007f02b  inc     r15
0x18007f02e  jmp     loc_18007F0B9
0x18007f033  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x18007f03a  lea     rcx, aSTenantidIsEmp; "%s: TenantId is empty."
0x18007f041  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18007f046  mov     rcx, [rdi+18h]; unsigned __int16 *
0x18007f04a  test    rcx, rcx
0x18007f04d  jz      short loc_18007F09D
0x18007f04f  cmp     [rcx], bx
0x18007f052  jz      short loc_18007F09D
0x18007f054  lea     r8, [rsp+170h+var_140]; unsigned __int64 *
0x18007f059  lea     rdx, [rbp+70h+Block]; unsigned __int16 **
0x18007f060  call    ?GetDomainFromEmail@@YAJPEBGPEAPEAGPEA_K@Z; GetDomainFromEmail(ushort const *,ushort * *,unsigned __int64 *)
0x18007f065  mov     ebx, eax
0x18007f067  test    eax, eax
0x18007f069  jns     short loc_18007F08D
0x18007f06b  lea     r8, aGetdomainfrome; "GetDomainFromEmail"
0x18007f072  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x18007f079  mov     r9d, eax
0x18007f07c  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18007f083  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007f088  jmp     loc_18007FB5B
0x18007f08d  mov     r14, [rbp+70h+Block]
0x18007f094  xor     ebx, ebx
0x18007f096  mov     r15, [rsp+170h+var_140]
0x18007f09b  jmp     short loc_18007F0B0
0x18007f09d  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x18007f0a4  lea     rcx, aSJoinuseremail; "%s: JoinUserEmail is empty."
0x18007f0ab  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18007f0b0  test    r14, r14
0x18007f0b3  jz      loc_18007F157
0x18007f0b9  cmp     [r14], bx
0x18007f0bd  jz      loc_18007F157
0x18007f0c3  lea     rbx, [r15+36h]
0x18007f0c7  lea     rcx, [rbx+rbx]; size
0x18007f0cb  call    MIDL_user_allocate
0x18007f0d0  mov     [rsp+170h+var_118], rax
0x18007f0d5  test    rax, rax
0x18007f0d8  jnz     short loc_18007F0F7
0x18007f0da  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x18007f0e1  mov     ebx, 8007000Eh
0x18007f0e6  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18007f0ed  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18007f0f2  jmp     loc_18007FB5B
0x18007f0f7  mov     rcx, [rsp+170h+var_118]; unsigned __int16 *
0x18007f0fc  lea     r8, aHttpsLoginMicr; "https://login.microsoftonline.com/%s/oa"...
0x18007f103  mov     r9, r14
0x18007f106  mov     rdx, rbx; unsigned __int64
0x18007f109  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007f10e  mov     ebx, eax
0x18007f110  test    eax, eax
0x18007f112  jns     short loc_18007F120
0x18007f114  lea     r8, aStringcchprint; "StringCchPrintfW"
0x18007f11b  jmp     loc_18007F072
0x18007f120  add     r15, 32h ; '2'
0x18007f124  lea     rcx, [r15+r15]; size
0x18007f128  call    MIDL_user_allocate
0x18007f12d  mov     [rsp+170h+var_110], rax
0x18007f132  test    rax, rax
0x18007f135  jz      short loc_18007F0DA
0x18007f137  mov     r9, r14
0x18007f13a  lea     r8, aHttpsLoginMicr_0; "https://login.microsoftonline.com/%s/oa"...
0x18007f141  mov     rdx, r15; unsigned __int64
0x18007f144  mov     rcx, rax; unsigned __int16 *
0x18007f147  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007f14c  xor     r15d, r15d
0x18007f14f  mov     ebx, eax
0x18007f151  test    eax, eax
0x18007f153  jns     short loc_18007F15A
0x18007f155  jmp     short loc_18007F114
0x18007f157  xor     r15d, r15d
0x18007f15a  lea     r14, a10; "1.0"
0x18007f161  mov     rcx, r14; unsigned __int16 *
0x18007f164  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18007f16b  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18007f170  mov     ebx, eax
0x18007f172  test    eax, eax
0x18007f174  jns     short loc_18007F182
0x18007f176  lea     r8, aStringdup; "StringDup"
0x18007f17d  jmp     loc_18007F072
0x18007f182  mov     rax, [rbp+70h+arg_0]
0x18007f189  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18007f190  lea     rcx, aHttpsEnterpris; "https://enterpriseregistration.windows."...
0x18007f197  mov     [rsp+170h+var_130], rax
0x18007f19c  mov     [rbp+70h+arg_0], r15
0x18007f1a3  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18007f1a8  mov     ebx, eax
0x18007f1aa  test    eax, eax
0x18007f1ac  js      short loc_18007F176
0x18007f1ae  mov     rax, [rbp+70h+arg_0]
0x18007f1b5  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18007f1bc  lea     rcx, aUrnMsDrsEnterp; "urn:ms-drs:enterpriseregistration.windo"...
0x18007f1c3  mov     [rsp+170h+var_128], rax
0x18007f1c8  mov     [rbp+70h+arg_0], r15
0x18007f1cf  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18007f1d4  mov     ebx, eax
0x18007f1d6  test    eax, eax
0x18007f1d8  js      short loc_18007F176
0x18007f1da  mov     rax, [rbp+70h+arg_0]
0x18007f1e1  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18007f1e8  mov     rcx, r14; unsigned __int16 *
0x18007f1eb  mov     [rsp+170h+var_120], rax
0x18007f1f0  mov     [rbp+70h+arg_0], r15
0x18007f1f7  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18007f1fc  mov     ebx, eax
0x18007f1fe  test    eax, eax
0x18007f200  js      loc_18007F176
0x18007f206  mov     rax, [rbp+70h+arg_0]
0x18007f20d  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18007f214  lea     rcx, aHttpsEnterpris_2; "https://enterpriseregistration.windows."...
0x18007f21b  mov     [rsp+170h+var_108], rax
0x18007f220  mov     [rbp+70h+arg_0], r15
0x18007f227  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18007f22c  mov     ebx, eax
0x18007f22e  test    eax, eax
0x18007f230  js      loc_18007F176
0x18007f236  mov     rax, [rbp+70h+arg_0]
0x18007f23d  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18007f244  lea     rcx, aUrnMsDrsEnterp; "urn:ms-drs:enterpriseregistration.windo"...
0x18007f24b  mov     [rsp+170h+var_100], rax
0x18007f250  mov     [rbp+70h+arg_0], r15
0x18007f257  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18007f25c  mov     ebx, eax
0x18007f25e  test    eax, eax
0x18007f260  js      loc_18007F176
0x18007f266  mov     rax, [rbp+70h+arg_0]
0x18007f26d  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18007f274  mov     rcx, r14; unsigned __int16 *
0x18007f277  mov     [rsp+170h+var_F8], rax
0x18007f27c  mov     [rbp+70h+arg_0], r15
0x18007f283  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18007f288  mov     ebx, eax
0x18007f28a  test    eax, eax
0x18007f28c  js      loc_18007F176
0x18007f292  mov     rax, [rbp+70h+arg_0]
0x18007f299  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18007f2a0  lea     rcx, aHttpsEnterpris_0; "https://enterpriseregistration.windows."...
0x18007f2a7  mov     [rbp+70h+var_F0], rax
0x18007f2ab  mov     [rbp+70h+arg_0], r15
0x18007f2b2  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18007f2b7  mov     ebx, eax
0x18007f2b9  test    eax, eax
0x18007f2bb  js      loc_18007F176
0x18007f2c1  mov     rax, [rbp+70h+arg_0]
0x18007f2c8  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18007f2cf  lea     rcx, aUrnMsDrsEnterp; "urn:ms-drs:enterpriseregistration.windo"...
0x18007f2d6  mov     [rbp+70h+var_E8], rax
0x18007f2da  mov     [rbp+70h+arg_0], r15
0x18007f2e1  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18007f2e6  mov     ebx, eax
0x18007f2e8  test    eax, eax
0x18007f2ea  js      loc_18007F176
0x18007f2f0  mov     rax, [rbp+70h+arg_0]
0x18007f2f7  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18007f2fe  mov     rcx, r14; unsigned __int16 *
0x18007f301  mov     [rbp+70h+var_E0], rax
0x18007f305  mov     [rbp+70h+arg_0], r15
0x18007f30c  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18007f311  mov     ebx, eax
0x18007f313  test    eax, eax
0x18007f315  js      loc_18007F176
0x18007f31b  mov     rax, [rbp+70h+arg_0]
0x18007f322  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18007f329  mov     rcx, r14; unsigned __int16 *
0x18007f32c  mov     [rbp+70h+var_D8], rax
0x18007f330  mov     [rbp+70h+arg_0], r15
0x18007f337  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18007f33c  mov     ebx, eax
0x18007f33e  test    eax, eax
0x18007f340  js      loc_18007F176
0x18007f346  mov     rax, [rbp+70h+arg_0]
0x18007f34d  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18007f354  lea     rcx, a40; "4.0"
0x18007f35b  mov     [rbp+70h+var_C0], rax
0x18007f35f  mov     [rbp+70h+arg_0], r15
0x18007f366  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18007f36b  mov     ebx, eax
0x18007f36d  test    eax, eax
0x18007f36f  js      loc_18007F176
0x18007f375  mov     rax, [rbp+70h+arg_0]
0x18007f37c  xor     ecx, ecx; void *
0x18007f37e  mov     [rbp+70h+var_60], rax
0x18007f382  mov     rax, [rdi+90h]
0x18007f389  mov     [rsp+170h+var_140], rax
0x18007f38e  mov     rax, [rdi+78h]
0x18007f392  mov     [rsp+170h+var_138], rax
0x18007f397  mov     [rbp+70h+arg_0], r15
0x18007f39e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007f3a3  lea     r8, [rbp+70h+Str]; unsigned __int16 **
0x18007f3aa  lea     rcx, [rsp+170h+var_140]; unsigned __int16 **
0x18007f3af  call    ?GetBaseUrl@@YAJPEAPEBG_KPEAPEAG@Z; GetBaseUrl(ushort const * *,unsigned __int64,ushort * *)
0x18007f3b4  mov     ebx, eax
0x18007f3b6  test    eax, eax
0x18007f3b8  jns     short loc_18007F3E3
0x18007f3ba  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x18007f3c1  lea     r8, aGetbaseurl; "GetBaseUrl"
0x18007f3c8  mov     r9d, eax
0x18007f3cb  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18007f3d2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007f3d7  mov     r12, [rbp+70h+Str]
0x18007f3de  jmp     loc_18007FB5B
0x18007f3e3  mov     r12, [rbp+70h+Str]
0x18007f3ea  mov     r14, r12
0x18007f3ed  test    r12, r12
0x18007f3f0  jz      short loc_18007F3F9
0x18007f3f2  cmp     [r12], r15w
0x18007f3f7  jnz     short loc_18007F413
0x18007f3f9  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x18007f400  lea     rcx, aSCannotParseNg; "%s: Cannot parse NGC endpoint to get se"...
0x18007f407  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18007f40c  lea     r14, aHttpsEnterpris_1; "https://enterpriseregistration.windows."...
0x18007f413  lea     rdx, asc_18009FB30; "://"
0x18007f41a  mov     rcx, r14; Str
0x18007f41d  call    cs:__imp_wcsstr
0x18007f423  test    rax, rax
0x18007f426  lea     rbx, [rax+6]
0x18007f42a  cmovz   rbx, r14
0x18007f42e  test    rbx, rbx
0x18007f431  jz      short loc_18007F486
0x18007f433  cmp     [rbx], r15w
0x18007f437  jz      short loc_18007F486
0x18007f439  mov     rax, rsi
0x18007f43c  inc     rax
  ... truncated ...
```
