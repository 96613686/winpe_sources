# JoinStatusStorage::SetDefaultDiscoveryMetadata(struct_join_status *,ushort const *)

- ea: `0x180045e60`
- end: `0x180046c17`
- name: `?SetDefaultDiscoveryMetadata@JoinStatusStorage@@CAJPEAUstruct_join_status@@PEBG@Z`
- size: `3511`
- prototype: `static int(struct struct_join_status *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180016560`

## callees

- `0x18001a100`
- `0x18001b478`
- `0x18001ea7c`
- `0x180021184`
- `0x1800211dc`
- `0x1800215e4`
- `0x180026410`
- `0x180036c14`
- `0x180036f9c`
- `0x180037474`
- `0x180045e60`
- `0x18004aa08`
- `0x18004ccd8`
- `0x18004d79c`
- `0x18005366c`
- `0x18005db30`
- `0x18005dd44`
- `0x1800abf88`
- `0x1800abfc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004639d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004639d`

## string_xrefs

- `0x1800469cf`: `WebAuthnServiceVersion`
- `0x180046880`: `DrsServiceVersion`
- `0x1800468e7`: `AccessTokenUrl`
- `0x1800469e9`: `DeviceManagementServiceVersion`
- `0x18004694d`: `NgcServiceVersion`
- `0x1800468ff`: `CdjServiceVersion`
- `0x1800460ba`: `https://login.microsoftonline.com/%s/oauth2/token`
- `0x18004607c`: `https://login.microsoftonline.com/%s/oauth2/authorize`
- `0x180046110`: `https://enterpriseregistration.windows.net/EnrollmentServer/DeviceEnrollmentWebService.svc`
- `0x1800466c1`: `https://login.microsoftonline.com`

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
0x180045e60  mov     [rsp-8+arg_8], rbx
0x180045e65  push    rbp
0x180045e66  push    rsi
0x180045e67  push    rdi
0x180045e68  push    r12
0x180045e6a  push    r13
0x180045e6c  push    r14
0x180045e6e  push    r15
0x180045e70  lea     rbp, [rsp-40h]
0x180045e75  sub     rsp, 140h
0x180045e7c  mov     r13, rdx
0x180045e7f  mov     rdi, rcx
0x180045e82  xor     edx, edx; Val
0x180045e84  lea     rcx, [rsp+170h+var_130]; void *
0x180045e89  mov     r8d, 100h; Size
0x180045e8f  call    memset_0
0x180045e94  xor     ebx, ebx
0x180045e96  mov     r12d, ebx
0x180045e99  mov     [rbp+70h+Block], rbx
0x180045ea0  mov     r15d, ebx
0x180045ea3  mov     [rbp+70h+arg_0], rbx
0x180045eaa  mov     [rbp+70h+Str], rbx
0x180045eb1  mov     [rsp+170h+var_140], rbx
0x180045eb6  cmp     [rdi+48h], rbx
0x180045eba  jz      loc_180045F8B
0x180045ec0  cmp     [rdi+50h], rbx
0x180045ec4  jz      loc_180045F8B
0x180045eca  cmp     [rdi+58h], rbx
0x180045ece  jz      loc_180045F8B
0x180045ed4  cmp     [rdi+60h], rbx
0x180045ed8  jz      loc_180045F8B
0x180045ede  cmp     [rdi+68h], rbx
0x180045ee2  jz      loc_180045F8B
0x180045ee8  cmp     [rdi+70h], rbx
0x180045eec  jz      loc_180045F8B
0x180045ef2  cmp     [rdi+78h], rbx
0x180045ef6  jz      loc_180045F8B
0x180045efc  cmp     [rdi+80h], rbx
0x180045f03  jz      loc_180045F8B
0x180045f09  cmp     [rdi+88h], rbx
0x180045f10  jz      short loc_180045F8B
0x180045f12  cmp     [rdi+90h], rbx
0x180045f19  jz      short loc_180045F8B
0x180045f1b  cmp     [rdi+98h], rbx
0x180045f22  jz      short loc_180045F8B
0x180045f24  cmp     [rdi+0A0h], rbx
0x180045f2b  jz      short loc_180045F8B
0x180045f2d  cmp     [rdi+0A8h], rbx
0x180045f34  jz      short loc_180045F8B
0x180045f36  cmp     [rdi+0B0h], rbx
0x180045f3d  jz      short loc_180045F8B
0x180045f3f  cmp     [rdi+0B8h], rbx
0x180045f46  jz      short loc_180045F8B
0x180045f48  cmp     [rdi+0C0h], rbx
0x180045f4f  jz      short loc_180045F8B
0x180045f51  cmp     [rdi+0C8h], rbx
0x180045f58  jz      short loc_180045F8B
0x180045f5a  cmp     [rdi+118h], rbx
0x180045f61  jz      short loc_180045F8B
0x180045f63  cmp     [rdi+120h], rbx
0x180045f6a  jz      short loc_180045F8B
0x180045f6c  cmp     [rdi+128h], rbx
0x180045f73  jz      short loc_180045F8B
0x180045f75  cmp     [rdi+130h], rbx
0x180045f7c  jz      short loc_180045F8B
0x180045f7e  cmp     [rdi+138h], rbx
0x180045f85  jnz     loc_180046ADB
0x180045f8b  mov     r14, [rdi+10h]
0x180045f8f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180045f93  test    r14, r14
0x180045f96  jz      short loc_180045FB3
0x180045f98  cmp     [r14], bx
0x180045f9c  jz      short loc_180045FB3
0x180045f9e  mov     r15, rsi
0x180045fa1  inc     r15
0x180045fa4  cmp     [r14+r15*2], bx
0x180045fa9  jnz     short loc_180045FA1
0x180045fab  inc     r15
0x180045fae  jmp     loc_180046039
0x180045fb3  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x180045fba  lea     rcx, aSTenantidIsEmp; "%s: TenantId is empty."
0x180045fc1  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180045fc6  mov     rcx, [rdi+18h]; unsigned __int16 *
0x180045fca  test    rcx, rcx
0x180045fcd  jz      short loc_18004601D
0x180045fcf  cmp     [rcx], bx
0x180045fd2  jz      short loc_18004601D
0x180045fd4  lea     r8, [rsp+170h+var_140]; unsigned __int64 *
0x180045fd9  lea     rdx, [rbp+70h+Block]; unsigned __int16 **
0x180045fe0  call    ?GetDomainFromEmail@@YAJPEBGPEAPEAGPEA_K@Z; GetDomainFromEmail(ushort const *,ushort * *,unsigned __int64 *)
0x180045fe5  mov     ebx, eax
0x180045fe7  test    eax, eax
0x180045fe9  jns     short loc_18004600D
0x180045feb  lea     r8, aGetdomainfrome; "GetDomainFromEmail"
0x180045ff2  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x180045ff9  mov     r9d, eax
0x180045ffc  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180046003  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180046008  jmp     loc_180046ADB
0x18004600d  mov     r14, [rbp+70h+Block]
0x180046014  xor     ebx, ebx
0x180046016  mov     r15, [rsp+170h+var_140]
0x18004601b  jmp     short loc_180046030
0x18004601d  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x180046024  lea     rcx, aSJoinuseremail; "%s: JoinUserEmail is empty."
0x18004602b  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180046030  test    r14, r14
0x180046033  jz      loc_1800460D7
0x180046039  cmp     [r14], bx
0x18004603d  jz      loc_1800460D7
0x180046043  lea     rbx, [r15+36h]
0x180046047  lea     rcx, [rbx+rbx]; size
0x18004604b  call    MIDL_user_allocate
0x180046050  mov     [rsp+170h+var_118], rax
0x180046055  test    rax, rax
0x180046058  jnz     short loc_180046077
0x18004605a  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x180046061  mov     ebx, 8007000Eh
0x180046066  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18004606d  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180046072  jmp     loc_180046ADB
0x180046077  mov     rcx, [rsp+170h+var_118]; unsigned __int16 *
0x18004607c  lea     r8, aHttpsLoginMicr; "https://login.microsoftonline.com/%s/oa"...
0x180046083  mov     r9, r14
0x180046086  mov     rdx, rbx; unsigned __int64
0x180046089  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004608e  mov     ebx, eax
0x180046090  test    eax, eax
0x180046092  jns     short loc_1800460A0
0x180046094  lea     r8, aStringcchprint; "StringCchPrintfW"
0x18004609b  jmp     loc_180045FF2
0x1800460a0  add     r15, 32h ; '2'
0x1800460a4  lea     rcx, [r15+r15]; size
0x1800460a8  call    MIDL_user_allocate
0x1800460ad  mov     [rsp+170h+var_110], rax
0x1800460b2  test    rax, rax
0x1800460b5  jz      short loc_18004605A
0x1800460b7  mov     r9, r14
0x1800460ba  lea     r8, aHttpsLoginMicr_0; "https://login.microsoftonline.com/%s/oa"...
0x1800460c1  mov     rdx, r15; unsigned __int64
0x1800460c4  mov     rcx, rax; unsigned __int16 *
0x1800460c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800460cc  xor     r15d, r15d
0x1800460cf  mov     ebx, eax
0x1800460d1  test    eax, eax
0x1800460d3  jns     short loc_1800460DA
0x1800460d5  jmp     short loc_180046094
0x1800460d7  xor     r15d, r15d
0x1800460da  lea     r14, a10; "1.0"
0x1800460e1  mov     rcx, r14; unsigned __int16 *
0x1800460e4  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x1800460eb  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x1800460f0  mov     ebx, eax
0x1800460f2  test    eax, eax
0x1800460f4  jns     short loc_180046102
0x1800460f6  lea     r8, aStringdup; "StringDup"
0x1800460fd  jmp     loc_180045FF2
0x180046102  mov     rax, [rbp+70h+arg_0]
0x180046109  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x180046110  lea     rcx, aHttpsEnterpris; "https://enterpriseregistration.windows."...
0x180046117  mov     [rsp+170h+var_130], rax
0x18004611c  mov     [rbp+70h+arg_0], r15
0x180046123  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x180046128  mov     ebx, eax
0x18004612a  test    eax, eax
0x18004612c  js      short loc_1800460F6
0x18004612e  mov     rax, [rbp+70h+arg_0]
0x180046135  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18004613c  lea     rcx, aUrnMsDrsEnterp; "urn:ms-drs:enterpriseregistration.windo"...
0x180046143  mov     [rsp+170h+var_128], rax
0x180046148  mov     [rbp+70h+arg_0], r15
0x18004614f  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x180046154  mov     ebx, eax
0x180046156  test    eax, eax
0x180046158  js      short loc_1800460F6
0x18004615a  mov     rax, [rbp+70h+arg_0]
0x180046161  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x180046168  mov     rcx, r14; unsigned __int16 *
0x18004616b  mov     [rsp+170h+var_120], rax
0x180046170  mov     [rbp+70h+arg_0], r15
0x180046177  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18004617c  mov     ebx, eax
0x18004617e  test    eax, eax
0x180046180  js      loc_1800460F6
0x180046186  mov     rax, [rbp+70h+arg_0]
0x18004618d  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x180046194  lea     rcx, aHttpsEnterpris_2; "https://enterpriseregistration.windows."...
0x18004619b  mov     [rsp+170h+var_108], rax
0x1800461a0  mov     [rbp+70h+arg_0], r15
0x1800461a7  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x1800461ac  mov     ebx, eax
0x1800461ae  test    eax, eax
0x1800461b0  js      loc_1800460F6
0x1800461b6  mov     rax, [rbp+70h+arg_0]
0x1800461bd  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x1800461c4  lea     rcx, aUrnMsDrsEnterp; "urn:ms-drs:enterpriseregistration.windo"...
0x1800461cb  mov     [rsp+170h+var_100], rax
0x1800461d0  mov     [rbp+70h+arg_0], r15
0x1800461d7  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x1800461dc  mov     ebx, eax
0x1800461de  test    eax, eax
0x1800461e0  js      loc_1800460F6
0x1800461e6  mov     rax, [rbp+70h+arg_0]
0x1800461ed  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x1800461f4  mov     rcx, r14; unsigned __int16 *
0x1800461f7  mov     [rsp+170h+var_F8], rax
0x1800461fc  mov     [rbp+70h+arg_0], r15
0x180046203  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x180046208  mov     ebx, eax
0x18004620a  test    eax, eax
0x18004620c  js      loc_1800460F6
0x180046212  mov     rax, [rbp+70h+arg_0]
0x180046219  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x180046220  lea     rcx, aHttpsEnterpris_0; "https://enterpriseregistration.windows."...
0x180046227  mov     [rbp+70h+var_F0], rax
0x18004622b  mov     [rbp+70h+arg_0], r15
0x180046232  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x180046237  mov     ebx, eax
0x180046239  test    eax, eax
0x18004623b  js      loc_1800460F6
0x180046241  mov     rax, [rbp+70h+arg_0]
0x180046248  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18004624f  lea     rcx, aUrnMsDrsEnterp; "urn:ms-drs:enterpriseregistration.windo"...
0x180046256  mov     [rbp+70h+var_E8], rax
0x18004625a  mov     [rbp+70h+arg_0], r15
0x180046261  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x180046266  mov     ebx, eax
0x180046268  test    eax, eax
0x18004626a  js      loc_1800460F6
0x180046270  mov     rax, [rbp+70h+arg_0]
0x180046277  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18004627e  mov     rcx, r14; unsigned __int16 *
0x180046281  mov     [rbp+70h+var_E0], rax
0x180046285  mov     [rbp+70h+arg_0], r15
0x18004628c  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x180046291  mov     ebx, eax
0x180046293  test    eax, eax
0x180046295  js      loc_1800460F6
0x18004629b  mov     rax, [rbp+70h+arg_0]
0x1800462a2  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x1800462a9  mov     rcx, r14; unsigned __int16 *
0x1800462ac  mov     [rbp+70h+var_D8], rax
0x1800462b0  mov     [rbp+70h+arg_0], r15
0x1800462b7  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x1800462bc  mov     ebx, eax
0x1800462be  test    eax, eax
0x1800462c0  js      loc_1800460F6
0x1800462c6  mov     rax, [rbp+70h+arg_0]
0x1800462cd  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x1800462d4  lea     rcx, a40; "4.0"
0x1800462db  mov     [rbp+70h+var_C0], rax
0x1800462df  mov     [rbp+70h+arg_0], r15
0x1800462e6  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x1800462eb  mov     ebx, eax
0x1800462ed  test    eax, eax
0x1800462ef  js      loc_1800460F6
0x1800462f5  mov     rax, [rbp+70h+arg_0]
0x1800462fc  xor     ecx, ecx; void *
0x1800462fe  mov     [rbp+70h+var_60], rax
0x180046302  mov     rax, [rdi+90h]
0x180046309  mov     [rsp+170h+var_140], rax
0x18004630e  mov     rax, [rdi+78h]
0x180046312  mov     [rsp+170h+var_138], rax
0x180046317  mov     [rbp+70h+arg_0], r15
0x18004631e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180046323  lea     r8, [rbp+70h+Str]; unsigned __int16 **
0x18004632a  lea     rcx, [rsp+170h+var_140]; unsigned __int16 **
0x18004632f  call    ?GetBaseUrl@@YAJPEAPEBG_KPEAPEAG@Z; GetBaseUrl(ushort const * *,unsigned __int64,ushort * *)
0x180046334  mov     ebx, eax
0x180046336  test    eax, eax
0x180046338  jns     short loc_180046363
0x18004633a  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x180046341  lea     r8, aGetbaseurl; "GetBaseUrl"
0x180046348  mov     r9d, eax
0x18004634b  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180046352  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180046357  mov     r12, [rbp+70h+Str]
0x18004635e  jmp     loc_180046ADB
0x180046363  mov     r12, [rbp+70h+Str]
0x18004636a  mov     r14, r12
0x18004636d  test    r12, r12
0x180046370  jz      short loc_180046379
0x180046372  cmp     [r12], r15w
0x180046377  jnz     short loc_180046393
0x180046379  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x180046380  lea     rcx, aSCannotParseNg; "%s: Cannot parse NGC endpoint to get se"...
0x180046387  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18004638c  lea     r14, aHttpsEnterpris_1; "https://enterpriseregistration.windows."...
0x180046393  lea     rdx, SubStr; "://"
0x18004639a  mov     rcx, r14; Str
0x18004639d  call    cs:__imp_wcsstr
0x1800463a3  test    rax, rax
0x1800463a6  lea     rbx, [rax+6]
0x1800463aa  cmovz   rbx, r14
0x1800463ae  test    rbx, rbx
0x1800463b1  jz      short loc_180046406
0x1800463b3  cmp     [rbx], r15w
0x1800463b7  jz      short loc_180046406
0x1800463b9  mov     rax, rsi
0x1800463bc  inc     rax
  ... truncated ...
```
