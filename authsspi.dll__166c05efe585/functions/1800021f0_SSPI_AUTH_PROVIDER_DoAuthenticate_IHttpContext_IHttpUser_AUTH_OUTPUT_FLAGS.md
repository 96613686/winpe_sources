# SSPI_AUTH_PROVIDER::DoAuthenticate(IHttpContext *,IHttpUser * *,AUTH_OUTPUT_FLAGS *)

- ea: `0x1800021f0`
- end: `0x18000364d`
- name: `?DoAuthenticate@SSPI_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@PEAPEAVIHttpUser@@PEAW4AUTH_OUTPUT_FLAGS@@@Z`
- size: `5213`
- prototype: `__int64 __fastcall(SSPI_AUTH_PROVIDER *this, struct IHttpContext *, struct IHttpUser **, enum AUTH_OUTPUT_FLAGS *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001024`
- `0x180001064`
- `0x180002084`
- `0x1800021f0`
- `0x18000417c`
- `0x180004868`
- `0x180005adc`
- `0x180005dc4`
- `0x180005eac`
- `0x1800066cc`
- `0x18000680c`
- `0x180007b38`
- `0x180007d34`
- `0x180008480`
- `0x180008910`
- `0x180008b52`
- `0x180008ba0`
- `0x180009010`

## import_xrefs

- `SspiCli!SeciFreeCallContext` at `0x180003600`
- `SspiCli!SeciFreeCallContext` at `0x180003600`
- `SspiCli!FreeContextBuffer` at `0x1800032e5`
- `SspiCli!FreeContextBuffer` at `0x1800032e5`
- `SspiCli!QueryContextAttributesW` at `0x1800032be`
- `SspiCli!QueryContextAttributesW` at `0x1800032be`
- `SspiCli!CompleteAuthToken` at `0x180002fc4`
- `SspiCli!CompleteAuthToken` at `0x180002fc4`
- `SspiCli!FreeCredentialsHandle` at `0x180002837`
- `SspiCli!FreeCredentialsHandle` at `0x180002c99`
- `SspiCli!FreeCredentialsHandle` at `0x180002837`
- `SspiCli!FreeCredentialsHandle` at `0x180002c99`
- `SspiCli!DeleteSecurityContext` at `0x180002b9b`
- `SspiCli!DeleteSecurityContext` at `0x180002b9b`
- `SspiCli!AcceptSecurityContext` at `0x180002b67`
- `SspiCli!AcceptSecurityContext` at `0x180002d29`
- `SspiCli!AcceptSecurityContext` at `0x180002b67`
- `SspiCli!AcceptSecurityContext` at `0x180002d29`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x180002aec`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x180002aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003125`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000331a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000331a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800022fb`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002308`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003093`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003324`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003612`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000361f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800022fb`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002308`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003093`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003324`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003612`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000361f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002666`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002699`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800026aa`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000284e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002cb0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002666`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002699`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800026aa`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000284e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002cb0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800023a9`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800024b9`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003299`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003376`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000338d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800023a9`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800024b9`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003299`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003376`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000338d`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002390`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000239b`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800024c3`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000263a`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003380`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000339a`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002390`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000239b`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800024c3`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000263a`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003380`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000339a`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180002844`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180002ca6`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180002844`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180002ca6`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002a2f`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002a2f`
- `iisutil!uuencode` at `0x1800030e1`
- `iisutil!uuencode` at `0x1800030e1`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003193`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003193`
- `iisutil!?Equals@STRA@@QEBA_NPEBD@Z` at `0x180002517`
- `iisutil!?Equals@STRA@@QEBA_NPEBD@Z` at `0x1800033f4`
- `iisutil!?Equals@STRA@@QEBA_NPEBD@Z` at `0x180002517`
- `iisutil!?Equals@STRA@@QEBA_NPEBD@Z` at `0x1800033f4`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180002656`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180002656`
- `iisutil!?EqualsNoCase@STRA@@QEBA_NPEBD@Z` at `0x180002678`
- `iisutil!?EqualsNoCase@STRA@@QEBA_NPEBD@Z` at `0x180002678`
- `iisutil!PuDbgPrint` at `0x1800027dc`
- `iisutil!PuDbgPrint` at `0x1800028cd`
- `iisutil!PuDbgPrint` at `0x180002995`
- `iisutil!PuDbgPrint` at `0x180002c43`
- `iisutil!PuDbgPrint` at `0x180003089`
- `iisutil!PuDbgPrint` at `0x18000311f`
- `iisutil!PuDbgPrint` at `0x1800027dc`
- `iisutil!PuDbgPrint` at `0x1800028cd`
- `iisutil!PuDbgPrint` at `0x180002995`
- `iisutil!PuDbgPrint` at `0x180002c43`
- `iisutil!PuDbgPrint` at `0x180003089`
- `iisutil!PuDbgPrint` at `0x18000311f`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800028df`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800028df`
- `iisutil!uudecode` at `0x1800029de`
- `iisutil!uudecode` at `0x1800029de`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180003150`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180003150`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800032d8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800032d8`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003049`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800030b9`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003049`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800030b9`

## string_xrefs

- `0x1800027c3`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\sspi_auth\sspi_auth.cxx`
- `0x1800028b4`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\sspi_auth\sspi_auth.cxx`
- `0x18000298e`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\sspi_auth\sspi_auth.cxx`
- `0x180002c37`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\sspi_auth\sspi_auth.cxx`
- `0x18000307d`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\sspi_auth\sspi_auth.cxx`
- `0x180003118`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\sspi_auth\sspi_auth.cxx`
- `0x180002d8f`: `AcceptSecurityContext failed, error %x\n`
- `0x180002fe7`: `Error on CompleteAuthToken, hr = 0x%x\n`
- `0x180003068`: `Error copying auth type, hr = 0x%x.\n`
- `0x180003177`: `Error copying auth header, hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SSPI_AUTH_PROVIDER::DoAuthenticate(
        SSPI_AUTH_PROVIDER *this,
        struct IHttpContext *a2,
        struct IHttpUser **a3,
        enum AUTH_OUTPUT_FLAGS *a4)
{
  SSPI_AUTH_PROVIDER *v6; // rcx
  signed int SecStatus; // ebx
  __int64 v9; // rax
  __int64 (__fastcall ***v10)(_QWORD, void *); // rax
  __int64 v11; // r12
  __int64 v12; // rax
  __int64 (__fastcall *v13)(struct IHttpContext *); // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  unsigned int v17; // ecx
  struct _HTTP_REQUEST_AUTH_INFO *v18; // rbx
  __int64 v19; // rsi
  int v20; // ebx
  SSPI_AUTH_PROVIDER *v21; // rcx
  int IsPersistentAuthHeaderTrue; // eax
  const char *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 (__fastcall ***v27)(_QWORD, void *); // rax
  __int64 v28; // rax
  struct IHttpUser *v29; // rsi
  const unsigned __int16 *v30; // rax
  const char **v31; // rbx
  __int64 (__fastcall ***v32)(_QWORD, void *); // rax
  __int64 v33; // r14
  __int64 v34; // rax
  __int64 (__fastcall ***v35)(_QWORD, void *); // rax
  __int64 v36; // rax
  struct SSPI_CREDENTIAL **v37; // rax
  bool v38; // zf
  struct SSPI_CREDENTIAL *v39; // r13
  __int64 *v40; // rcx
  const char *v41; // rax
  signed __int64 v42; // rcx
  int v43; // edx
  int v44; // r8d
  int ReferencedCredential; // eax
  struct _SecHandle *v46; // rcx
  volatile signed __int32 *dwLower; // rbx
  int v48; // eax
  _QWORD *v49; // rax
  struct _SecHandle *v50; // rcx
  __int64 v51; // rax
  char *v52; // rbx
  signed int LastError; // eax
  __int64 v54; // rax
  __int64 v55; // rdx
  struct _SecHandle *v56; // rdx
  _QWORD *v57; // rbx
  SECURITY_STATUS v58; // esi
  unsigned int v59; // r9d
  int v60; // eax
  volatile signed __int32 *v61; // rbx
  struct IHttpServer *v62; // rcx
  int v63; // ecx
  DWORD v64; // eax
  int (__fastcall ***v65)(_QWORD, _BYTE *); // rax
  int (__fastcall **v66)(_QWORD, _BYTE *); // rcx
  __int64 *v67; // rcx
  __int64 v68; // rax
  void (__fastcall *v69)(__int64 *, GUID **); // rax
  int (__fastcall ***v70)(_QWORD, _BYTE *); // rax
  int v71; // r8d
  struct _SecHandle v72; // xmm0
  struct _SecHandle *v73; // rax
  SECURITY_STATUS v74; // eax
  int v75; // eax
  STRA *v76; // rcx
  signed int v77; // eax
  int v78; // eax
  const char *v79; // rdx
  int v80; // eax
  unsigned int v81; // esi
  __int64 v82; // rax
  _DWORD *v83; // rax
  int (__fastcall ***v84)(_QWORD, _BYTE *); // rax
  int v85; // ebx
  unsigned __int16 *v86; // rbx
  struct IHttpTraceContext *v87; // rax
  const struct _GUID *v88; // rdx
  _DWORD *v89; // rsi
  __int64 v90; // rax
  int v91; // ebx
  SSPI_AUTH_PROVIDER *v92; // rcx
  __int64 v93; // rcx
  const char *v94; // rcx
  struct IHttpUser **v95; // rax
  int (__fastcall ***v96)(_QWORD, _BYTE *); // rax
  int (__fastcall **v97)(_QWORD, _BYTE *); // rcx
  __int64 v98; // rax
  __int64 *v99; // rcx
  __int64 v100; // rax
  void (__fastcall *v101)(__int64 *, _QWORD *); // rax
  PCtxtHandle phNewContext; // [rsp+28h] [rbp-D8h]
  unsigned int fContextReq; // [rsp+50h] [rbp-B0h] BYREF
  struct _SecHandle *v104; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int pfContextAttr; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v106; // [rsp+64h] [rbp-9Ch] BYREF
  int v107; // [rsp+68h] [rbp-98h] BYREF
  struct SSPI_CREDENTIAL *v108; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pBuffer[24]; // [rsp+78h] [rbp-88h] BYREF
  int v110; // [rsp+90h] [rbp-70h]
  __int64 v111; // [rsp+98h] [rbp-68h]
  __int128 v112; // [rsp+A0h] [rbp-60h] BYREF
  int v113; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v114; // [rsp+B8h] [rbp-48h]
  SSPI_APP_CONTEXT *v115; // [rsp+C0h] [rbp-40h] BYREF
  struct _SecBufferDesc pInput; // [rsp+C8h] [rbp-38h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+D8h] [rbp-28h] BYREF
  struct _SecBufferDesc pToken; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v119[24]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v120; // [rsp+110h] [rbp+10h]
  SSPI_AUTH_PROVIDER *v121; // [rsp+118h] [rbp+18h]
  struct IHttpUser **v122; // [rsp+120h] [rbp+20h]
  _DWORD v123[2]; // [rsp+128h] [rbp+28h] BYREF
  char *v124; // [rsp+130h] [rbp+30h]
  struct _SecBuffer v125; // [rsp+138h] [rbp+38h] BYREF
  struct _SecHandle phContext; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v127[4]; // [rsp+160h] [rbp+60h] BYREF
  const wchar_t *v128; // [rsp+180h] [rbp+80h]
  int v129; // [rsp+188h] [rbp+88h]
  int v130; // [rsp+18Ch] [rbp+8Ch]
  __int128 v131; // [rsp+190h] [rbp+90h]
  int v132; // [rsp+1A0h] [rbp+A0h]
  int v133; // [rsp+1A4h] [rbp+A4h]
  __int64 v134; // [rsp+1A8h] [rbp+A8h]
  GUID **v135; // [rsp+1B0h] [rbp+B0h]
  GUID *v136; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v137; // [rsp+1C8h] [rbp+C8h]
  GUID *v138; // [rsp+1D0h] [rbp+D0h]
  __int64 v139; // [rsp+1D8h] [rbp+D8h]
  unsigned __int16 *v140; // [rsp+1E0h] [rbp+E0h]
  __int64 v141; // [rsp+1E8h] [rbp+E8h]
  __int128 v142; // [rsp+1F0h] [rbp+F0h]
  int v143; // [rsp+200h] [rbp+100h]
  int v144; // [rsp+204h] [rbp+104h]
  __int64 v145; // [rsp+208h] [rbp+108h]
  _BYTE *v146; // [rsp+210h] [rbp+110h]
  _QWORD v147[4]; // [rsp+220h] [rbp+120h] BYREF
  _QWORD *v148; // [rsp+240h] [rbp+140h]
  int v149; // [rsp+248h] [rbp+148h]
  __int16 v150; // [rsp+24Ch] [rbp+14Ch]
  _BYTE v151[32]; // [rsp+250h] [rbp+150h] BYREF
  char *v152; // [rsp+270h] [rbp+170h]
  int v153; // [rsp+278h] [rbp+178h]
  __int16 v154; // [rsp+27Ch] [rbp+17Ch]
  char v155; // [rsp+280h] [rbp+180h] BYREF
  char v156[255]; // [rsp+281h] [rbp+181h] BYREF
  char v157; // [rsp+380h] [rbp+280h] BYREF
  char v158[255]; // [rsp+381h] [rbp+281h] BYREF

  v122 = a3;
  v121 = this;
  ptsExpiry.QuadPart = 0;
  pfContextAttr = 0;
  v108 = 0;
  *(_QWORD *)pBuffer = a4;
  pToken = 0;
  v112 = 0;
  pInput = 0;
  memset_0(v156, 0, sizeof(v156));
  v155 = 0;
  v152 = &v155;
  v148 = v147;
  v153 = 256;
  v154 = 256;
  v106 = 0;
  v147[0] = 0;
  v149 = 32;
  v150 = 256;
  v107 = 0;
  v113 = 0;
  phContext = 0;
  if ( !a2 || !a3 )
  {
    BUFFER::~BUFFER((BUFFER *)v147);
    BUFFER::~BUFFER((BUFFER *)v151);
    return 2147942487LL;
  }
  v115 = 0;
  SecStatus = SSPI_AUTH_PROVIDER::SetupParsedAppContext(v6, a2, &v115);
  if ( SecStatus < 0 )
    goto LABEL_4;
  v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 240LL))(a2);
  v10 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 56LL))(v9);
  v11 = (**v10)(v10, s_ModuleId);
  if ( !v11 )
  {
    v11 = (*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a2 + 144LL))(a2, 208);
    if ( !v11 )
      goto LABEL_25;
    *(_QWORD *)v11 = &AUTH_REQUEST_CONTEXT::`vftable';
    STRA::STRA((STRA *)(v11 + 8));
    STRA::STRA((STRA *)(v11 + 72));
    STRU::STRU((STRU *)(v11 + 136));
    *(_QWORD *)(v11 + 64) = 0;
    *(_DWORD *)(v11 + 128) = 0;
    *(_QWORD *)(v11 + 192) = 0;
    v12 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 56LL))(a2);
    SecStatus = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v12 + 8LL))(v12, v11, s_ModuleId);
    if ( SecStatus < 0 )
    {
      (**(void (__fastcall ***)(__int64))v11)(v11);
      goto LABEL_4;
    }
  }
  v13 = *(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL);
  if ( *((_DWORD *)v115 + 2) )
  {
    v14 = v13(a2);
    v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    if ( !*(_WORD *)(v15 + 848) )
    {
LABEL_16:
      SecStatus = -2146893042;
      goto LABEL_4;
    }
    v16 = *(_QWORD *)(v15 + 856);
    v17 = 0;
    while ( 1 )
    {
      if ( !*(_DWORD *)(v16 + 16LL * v17) )
      {
        v18 = *(struct _HTTP_REQUEST_AUTH_INFO **)(v16 + 16LL * v17 + 8);
        if ( v18->AuthStatus == HttpAuthStatusSuccess )
        {
          v19 = (*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a2 + 144LL))(a2, 176);
          if ( v19 )
          {
            *(_QWORD *)v19 = &KERNEL_USER_CONTEXT::`vftable';
            STRU::STRU((STRU *)(v19 + 40));
            STRA::STRA((STRA *)(v19 + 120));
            *(_DWORD *)(v19 + 8) = 1;
            *(_QWORD *)(v19 + 104) = -1;
            *(_QWORD *)(v19 + 96) = -1;
            *(_QWORD *)(v19 + 16) = 0;
            *(_QWORD *)(v19 + 24) = 0;
            *(_QWORD *)(v19 + 32) = 0;
            *(_QWORD *)(v19 + 112) = 0;
            SecStatus = KERNEL_USER_CONTEXT::Initialize((KERNEL_USER_CONTEXT *)v19, v18);
            if ( SecStatus >= 0 )
            {
              v20 = STRA::Equals((STRA *)(v19 + 120), "NTLM");
              IsPersistentAuthHeaderTrue = SSPI_AUTH_PROVIDER::IsPersistentAuthHeaderTrue(v21, a2, v20);
              *(_DWORD *)(v11 + 196) = 1;
              v23 = "true";
              if ( !IsPersistentAuthHeaderTrue )
                v23 = "false";
              *(_QWORD *)(v11 + 200) = v23;
              TraceAuthSucceeded(a2, (struct IHttpUser *)v19, v20);
              *a3 = (struct IHttpUser *)v19;
              SecStatus = 0;
            }
            else
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 56LL))(v19);
            }
            goto LABEL_4;
          }
LABEL_25:
          SecStatus = -2147024888;
          goto LABEL_4;
        }
        if ( v18->AuthStatus == HttpAuthStatusFailure )
        {
          SecStatus = v18->SecStatus;
          goto LABEL_4;
        }
      }
      if ( ++v17 >= *(unsigned __int16 *)(v15 + 848) )
        goto LABEL_16;
    }
  }
  v24 = v13(a2);
  v25 = *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24) + 104);
  v26 = *(_QWORD *)a2;
  *(_QWORD *)v119 = v25;
  v104 = (struct _SecHandle *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v26 + 16))(a2);
  if ( !v104 )
    goto LABEL_25;
  v27 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 56LL))(a2);
  v114 = (**v27)(v27, s_ModuleId);
  if ( !v114 )
  {
    SecStatus = -2147024883;
    goto LABEL_4;
  }
  if ( (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 232LL))(a2) )
  {
    v28 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 232LL))(a2);
    v29 = (struct IHttpUser *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 48LL))(v28);
    if ( !v29 )
    {
LABEL_34:
      SecStatus = 0;
      goto LABEL_4;
    }
    STRA::STRA((STRA *)v127);
    v30 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)v29 + 16LL))(v29);
    SecStatus = STRA::CopyW((STRA *)v127, v30);
    if ( SecStatus < 0 )
    {
      STRA::~STRA((STRA *)v127);
      goto LABEL_4;
    }
    v31 = (const char **)(v114 + 40);
    if ( STRA::EqualsNoCase((STRA *)v127, *(const char **)(v114 + 40)) )
    {
      (*(void (__fastcall **)(struct IHttpUser *))(*(_QWORD *)v29 + 48LL))(v29);
      *a3 = v29;
      STRA::~STRA((STRA *)v127);
      goto LABEL_34;
    }
    STRA::~STRA((STRA *)v127);
  }
  else
  {
    v31 = (const char **)(v114 + 40);
  }
  v32 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct _SecHandle *))(v104->dwLower + 16))(v104);
  v33 = (**v32)(v32, s_ModuleId);
  v34 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
  v35 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 24LL))(v34);
  v36 = (**v35)(v35, s_ModuleId);
  v120 = v36;
  if ( v33 )
  {
    v37 = (struct SSPI_CREDENTIAL **)(v33 + 16);
    v38 = *(_DWORD *)(v33 + 28) == 0;
    v104 = (struct _SecHandle *)(v33 + 16);
    if ( v38 )
    {
      v39 = *v37;
      v40 = &qword_18000B0B8;
      if ( *v37 )
        v40 = (__int64 *)*((_QWORD *)v39 + 5);
      v41 = *v31;
      v42 = (char *)v40 - *v31;
      do
      {
        v43 = (unsigned __int8)v41[v42];
        v44 = *(unsigned __int8 *)v41 - v43;
        if ( v44 )
          break;
        ++v41;
      }
      while ( v43 );
      if ( !v44 )
      {
LABEL_59:
        v108 = v39;
        LODWORD(v104) = *(_DWORD *)(v33 + 24) == 0;
        goto LABEL_69;
      }
    }
    else
    {
      v104 = (struct _SecHandle *)(v33 + 16);
    }
    SSPI_SECURITY_CONTEXT::Reset((SSPI_SECURITY_CONTEXT *)v33);
    ReferencedCredential = SSPI_CREDENTIAL::GetReferencedCredential(*v31, &v108, (struct MULTISZ *)(v120 + 72));
    SecStatus = ReferencedCredential;
    if ( ReferencedCredential < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\sspi_auth\\sspi_auth.cxx",
          1182,
          "SSPI_AUTH_PROVIDER::DoAuthenticate",
          "Error get credential handle. hr = 0x%x \n",
          ReferencedCredential);
LABEL_50:
      SSPI_SECURITY_CONTEXT::Reset((SSPI_SECURITY_CONTEXT *)v33);
      goto LABEL_188;
    }
    v46 = v104;
    v39 = v108;
    dwLower = (volatile signed __int32 *)v104->dwLower;
    if ( v104->dwLower && _InterlockedExchangeAdd(dwLower + 1, 0xFFFFFFFF) == 1 )
    {
      *dwLower = 1396917094;
      if ( *((_QWORD *)dwLower + 25) != -1 && *((_QWORD *)dwLower + 26) != -1 )
        FreeCredentialsHandle((PCredHandle)(dwLower + 50));
      MULTISZ::~MULTISZ((MULTISZ *)(dwLower + 36));
      STRA::~STRA((STRA *)(dwLower + 2));
      operator delete((void *)dwLower);
      v46 = v104;
    }
    v46->dwLower = (ULONG_PTR)v39;
    goto LABEL_59;
  }
  v48 = SSPI_CREDENTIAL::GetReferencedCredential(*v31, &v108, (struct MULTISZ *)(v36 + 72));
  SecStatus = v48;
  if ( v48 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\sspi_auth\\sspi_auth.cxx",
        1215,
        "SSPI_AUTH_PROVIDER::DoAuthenticate",
        "Error get credential handle. hr = 0x%x \n",
        v48);
    goto LABEL_188;
  }
  v49 = ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext);
  v33 = (__int64)v49;
  if ( v49 )
  {
    v50 = v104;
    v39 = v108;
    v49[3] = 0;
    v49[7] = 0;
    *v49 = &SSPI_SECURITY_CONTEXT::`vftable';
    v49[2] = v39;
    v49[5] = -1;
    v49[4] = -1;
    *((_DWORD *)v49 + 2) = 1;
    v51 = (*(__int64 (__fastcall **)(struct _SecHandle *))(v50->dwLower + 16))(v50);
    SecStatus = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v51 + 8LL))(v51, v33, s_ModuleId);
    if ( SecStatus < 0 )
    {
      (**(void (__fastcall ***)(__int64))v33)(v33);
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\sspi_auth\\sspi_auth.cxx",
          1239,
          "SSPI_AUTH_PROVIDER::DoAuthenticate",
          "Failed to set Connection Auth Context. hr = 0x%x \n",
          SecStatus);
      goto LABEL_188;
    }
    LODWORD(v104) = 1;
    *((_DWORD *)v121 + 4) = 0;
LABEL_69:
    v52 = *(char **)(v114 + 64);
    if ( *((_DWORD *)v39 + 55) )
    {
      if ( !uudecode(*(char **)(v114 + 64), (struct BUFFER *)v151, &v106, 0) )
        goto LABEL_71;
      v52 = v152;
    }
    else
    {
      v54 = -1;
      do
        ++v54;
      while ( v52[v54] );
      v106 = v54 + 1;
    }
    if ( !BUFFER::Resize((BUFFER *)v147, *((_DWORD *)v39 + 54)) )
    {
LABEL_71:
      LastError = GetLastError();
      SecStatus = LastError;
      if ( LastError > 0 )
        SecStatus = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_99;
    }
    pToken.pBuffers = (PSecBuffer)&v112;
    pToken.ulVersion = 0;
    pToken.cBuffers = 1;
    LODWORD(v112) = *((_DWORD *)v39 + 54);
    *((_QWORD *)&v112 + 1) = v148;
    pInput.pBuffers = (PSecBuffer)v123;
    v123[0] = v106;
    DWORD1(v112) = 2;
    pInput.ulVersion = 0;
    pInput.cBuffers = 1;
    v123[1] = 2;
    v124 = v52;
    fContextReq = 32769;
    SecStatus = SSPI_APP_CONTEXT::AdjustFlagsForCbt(v115, a2, &fContextReq, &v125, &v113);
    if ( SecStatus < 0 )
      goto LABEL_99;
    if ( v113 )
      ++pInput.cBuffers;
    if ( *(_QWORD *)v119 )
    {
      if ( **(_WORD **)v119 == 2 )
      {
        v55 = 16;
      }
      else
      {
        if ( **(_WORD **)v119 != 23 )
          goto LABEL_87;
        v55 = 28;
      }
      SecStatus = SeciAllocateAndSetIPAddress(*(_QWORD *)v119, v55, &v107);
      if ( SecStatus < 0 )
        goto LABEL_99;
    }
LABEL_87:
    (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 24LL))(s_pGlobalInfo);
    if ( (_DWORD)v104 )
      v56 = 0;
    else
      v56 = (struct _SecHandle *)(v33 + 32);
    v57 = (_QWORD *)(v33 + 32);
    v104 = (struct _SecHandle *)(v33 + 32);
    v58 = AcceptSecurityContext(
            (PCredHandle)((char *)v39 + 200),
            v56,
            &pInput,
            fContextReq,
            0x10u,
            &phContext,
            &pToken,
            &pfContextAttr,
            &ptsExpiry);
    (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 32LL))(s_pGlobalInfo);
    if ( v58 == -2146893048 )
    {
      if ( *v57 != -1 && *(_QWORD *)(v33 + 40) != -1 )
      {
        DeleteSecurityContext((PCtxtHandle)(v33 + 32));
        *(_QWORD *)(v33 + 40) = -1;
        *v57 = -1;
      }
      LODWORD(v112) = *((_DWORD *)v39 + 54);
      *((_QWORD *)&v112 + 1) = v148;
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 24LL))(s_pGlobalInfo);
      v59 = 0x8000;
    }
    else
    {
      if ( v58 != -2146893022 )
        goto LABEL_109;
      SSPI_CREDENTIAL::RemoveCredentialFromCache(v39);
      v60 = SSPI_CREDENTIAL::GetReferencedCredential(*(const char **)(v114 + 40), &v108, (struct MULTISZ *)(v120 + 72));
      SecStatus = v60;
      if ( v60 < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LODWORD(phNewContext) = v60;
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\sspi_auth\\sspi_auth.cxx",
            1425,
            "SSPI_AUTH_PROVIDER::DoAuthenticate",
            "Error get credential handle. hr = 0x%x \n",
            phNewContext);
        }
LABEL_99:
        if ( !v33 )
          goto LABEL_188;
        goto LABEL_50;
      }
      v61 = *(volatile signed __int32 **)(v33 + 16);
      v39 = v108;
      if ( v61 && _InterlockedExchangeAdd(v61 + 1, 0xFFFFFFFF) == 1 )
      {
        *v61 = 1396917094;
        if ( *((_QWORD *)v61 + 25) != -1 && *((_QWORD *)v61 + 26) != -1 )
          FreeCredentialsHandle((PCredHandle)(v61 + 50));
        MULTISZ::~MULTISZ((MULTISZ *)(v61 + 36));
        STRA::~STRA((STRA *)(v61 + 2));
        operator delete((void *)v61);
      }
      v62 = s_pGlobalInfo;
      *(_QWORD *)(v33 + 16) = v39;
      LODWORD(v112) = *((_DWORD *)v39 + 54);
      *((_QWORD *)&v112 + 1) = v148;
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)v62 + 24LL))(v62);
      v59 = fContextReq;
    }
    v58 = AcceptSecurityContext(
            (PCredHandle)((char *)v39 + 200),
            0,
            &pInput,
            v59,
            0x10u,
            &phContext,
            &pToken,
            &pfContextAttr,
            &ptsExpiry);
    (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 32LL))(s_pGlobalInfo);
LABEL_109:
    if ( v58 < 0 )
    {
      if ( (unsigned int)(v58 + 2146893055) <= 0xB
        && (v63 = 2177, _bittest(&v63, v58 + 2146893055))
        && ((v64 = GetLastError(), v64 == 1907) || v64 == 1330) )
      {
        SecStatus = (unsigned __int16)v64 | 0x80070000;
      }
      else
      {
        SecStatus = v58;
      }
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(phNewContext) = v58;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\sspi_auth\\sspi_auth.cxx",
          1491,
          "SSPI_AUTH_PROVIDER::DoAuthenticate",
          "AcceptSecurityContext failed, error %x\n",
          phNewContext);
      }
      goto LABEL_99;
    }
    if ( (pfContextAttr & 0x100000) != 0 )
    {
      v65 = (int (__fastcall ***)(_QWORD, _BYTE *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      *(_QWORD *)pBuffer = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v66 = *v65;
      *(_OWORD *)&pBuffer[8] = 0;
      if ( (*v66)(v65, pBuffer) >= 0
        && *(_DWORD *)&pBuffer[16]
        && *(_DWORD *)&pBuffer[12] >= 3u
        && (*(_DWORD *)&pBuffer[8] == 2 || (pBuffer[8] & 2) != 0) )
      {
        v67 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
        v137 = 2;
        v139 = 22;
        v138 = &`IISAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
        v145 = 1;
        v140 = L"AUTH_NTLM_NULL_SESSION";
        v136 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v146 = pBuffer;
        v68 = *v67;
        v141 = 0x300000001LL;
        v142 = 0;
        v69 = *(void (__fastcall **)(__int64 *, GUID **))(v68 + 16);
        v143 = 0;
        v144 = 1;
        *(_QWORD *)pBuffer = L"ContextId";
        *(_DWORD *)&pBuffer[8] = 72;
        *(_QWORD *)&pBuffer[16] = 0;
        v110 = 16;
        v111 = 0;
        v69(v67, &v136);
      }
      SecStatus = -2147024891;
      goto LABEL_99;
    }
    if ( v58 == 590610 )
    {
      v70 = (int (__fastcall ***)(_QWORD, _BYTE *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      *(_QWORD *)v119 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      *(_OWORD *)&v119[8] = 0;
      if ( (**v70)(v70, v119) >= 0
        && *(_DWORD *)&v119[16]
        && *(_DWORD *)&v119[12] >= 3u
        && (*(_DWORD *)&v119[8] == 2 || (v119[8] & 2) != 0) )
      {
        SSPI_AUTH_PROVIDER::DiagnoseSSPI(v121, a2, v71);
      }
    }
    v72 = phContext;
    v73 = v104;
    *(_DWORD *)(v33 + 24) = 1;
    *v73 = v72;
    *(_DWORD *)(v33 + 48) = pfContextAttr;
    if ( v58 == 590610 || (fContextReq = 0, v58 == 590612) )
      fContextReq = 1;
    if ( (unsigned int)(v58 - 590611) <= 1 )
    {
      v74 = CompleteAuthToken(&phContext, &pToken);
      SecStatus = v74;
      if ( v74 < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LODWORD(phNewContext) = v74;
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\sspi_auth\\sspi_auth.cxx",
            1547,
            "SSPI_AUTH_PROVIDER::DoAuthenticate",
            "Error on CompleteAuthToken, hr = 0x%x\n",
            phNewContext);
        }
        goto LABEL_99;
      }
    }
    if ( !(_DWORD)v112 )
    {
      v81 = fContextReq;
LABEL_174:
      if ( !v81 )
      {
        SecStatus = SSPI_APP_CONTEXT::CheckSpn(v115, v104);
        if ( SecStatus < 0 )
          goto LABEL_99;
        v89 = operator new(0x120u);
        if ( !v89 )
        {
          SecStatus = -2147024888;
          goto LABEL_99;
        }
        *(_QWORD *)v89 = &SSPI_USER_CONTEXT::`vftable';
        STRU::STRU((STRU *)(v89 + 8));
        STRA::STRA((STRA *)(v89 + 22));
        STRU::STRU((STRU *)(v89 + 36));
        STRA::STRA((STRA *)(v89 + 56));
        v90 = v114;
        v89[2] = 1;
        *((_QWORD *)v89 + 2) = 0;
        *((_QWORD *)v89 + 3) = 0;
        v89[54] = 0;
        *((_QWORD *)v89 + 35) = 0;
        SecStatus = SSPI_USER_CONTEXT::Create(
                      (SSPI_USER_CONTEXT *)v89,
                      (struct SSPI_SECURITY_CONTEXT *)v33,
                      *(char **)(v90 + 40));
        if ( SecStatus < 0 )
        {
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v89 + 56LL))(v89);
          goto LABEL_99;
        }
        v91 = STRA::Equals((STRA *)(v89 + 22), "NTLM");
        if ( SSPI_AUTH_PROVIDER::IsPersistentAuthHeaderTrue(v92, a2, v91) )
        {
          v93 = *(_QWORD *)(v33 + 56);
          if ( v93 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 56LL))(v93);
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v89 + 48LL))(v89);
          v94 = "true";
          *(_QWORD *)(v33 + 56) = v89;
        }
        else
        {
          v94 = "false";
        }
        v95 = v122;
        *(_DWORD *)(v11 + 196) = 1;
        *(_QWORD *)(v11 + 200) = v94;
        *v95 = (struct IHttpUser *)v89;
        TraceAuthSucceeded(a2, (struct IHttpUser *)v89, v91);
        *(_DWORD *)(v33 + 28) = 1;
      }
      SecStatus = 0;
      goto LABEL_194;
    }
    memset_0(v158, 0, sizeof(v158));
    v157 = 0;
    v128 = (const wchar_t *)&v157;
    v129 = 256;
    LOWORD(v130) = 256;
    v75 = STRA::Copy((STRA *)(v11 + 72), *(const char **)(v114 + 40));
    SecStatus = v75;
    if ( v75 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(phNewContext) = v75;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\sspi_auth\\sspi_auth.cxx",
          1567,
          "SSPI_AUTH_PROVIDER::DoAuthenticate",
          "Error copying auth type, hr = 0x%x.\n",
          phNewContext);
      }
      goto LABEL_144;
    }
    v76 = (STRA *)(v11 + 72);
    if ( *(_DWORD *)(v114 + 192) )
    {
      SecStatus = STRA::Copy(v76, "Nego2 ");
      if ( SecStatus < 0 )
        goto LABEL_144;
    }
    else
    {
      v78 = STRA::Append(v76, " ", 1u);
      SecStatus = v78;
      if ( v78 < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LODWORD(phNewContext) = v78;
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\sspi_auth\\sspi_auth.cxx",
            1588,
            "SSPI_AUTH_PROVIDER::DoAuthenticate",
            "Error copying auth header, hr = 0x%x.\n",
            phNewContext);
        }
        goto LABEL_144;
      }
    }
    if ( *((_DWORD *)v39 + 55) )
    {
      if ( !uuencode(*((unsigned __int8 **)&v112 + 1), v112, (struct BUFFER *)v127, 0) )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\sspi_auth\\sspi_auth.cxx",
            1604,
            "SSPI_AUTH_PROVIDER::DoAuthenticate",
            "Error uuencoding the output buffer.\n");
        v77 = GetLastError();
        SecStatus = v77;
        if ( v77 > 0 )
          SecStatus = (unsigned __int16)v77 | 0x80070000;
        goto LABEL_144;
      }
      v79 = (const char *)v128;
    }
    else
    {
      v79 = (const char *)*((_QWORD *)&v112 + 1);
    }
    v80 = STRA::Append((STRA *)(v11 + 72), v79);
    SecStatus = v80;
    if ( v80 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(phNewContext) = v80;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\sspi_auth\\sspi_auth.cxx",
          1622,
          "SSPI_AUTH_PROVIDER::DoAuthenticate",
          "Error appending resp header, hr = 0x%x.\n",
          phNewContext);
      }
      goto LABEL_144;
    }
    v81 = fContextReq;
    if ( !fContextReq )
      goto LABEL_172;
    v82 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
    SecStatus = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v82 + 40LL))(
                  v82,
                  "WWW-Authenticate",
                  *(_QWORD *)(v11 + 104),
                  *(unsigned __int16 *)(v11 + 120),
                  0);
    if ( SecStatus >= 0 )
    {
      v83 = *(_DWORD **)pBuffer;
      *(_DWORD *)(v11 + 128) = 1;
      *v83 = 4;
      v84 = (int (__fastcall ***)(_QWORD, _BYTE *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      *(_QWORD *)pBuffer = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      *(_OWORD *)&pBuffer[8] = 0;
      if ( (**v84)(v84, pBuffer) >= 0
        && *(_DWORD *)&pBuffer[16]
        && *(_DWORD *)&pBuffer[12] >= 4u
        && (*(_DWORD *)&pBuffer[8] == 2 || (pBuffer[8] & 2) != 0) )
      {
        STRU::STRU((STRU *)&v136);
        *(struct _SecHandle *)v119 = phContext;
        *(_OWORD *)pBuffer = 0;
        if ( QueryContextAttributesW((PCtxtHandle)v119, 0xCu, pBuffer) >= 0 )
        {
          v85 = STRU::Copy((STRU *)&v136, *(const unsigned __int16 **)(*(_QWORD *)pBuffer + 16LL));
          FreeContextBuffer(*(PVOID *)pBuffer);
          if ( v85 >= 0 )
          {
            v86 = v140;
            v87 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
            IISAuthenticationEvents::AUTH_SSPI_CONTINUE_NEEDED::RaiseEvent(v87, v88, v86);
          }
        }
        STRU::~STRU((STRU *)&v136);
      }
LABEL_172:
      BUFFER::~BUFFER((BUFFER *)v127);
      goto LABEL_174;
    }
LABEL_144:
    BUFFER::~BUFFER((BUFFER *)v127);
    goto LABEL_99;
  }
  SecStatus = -2147024888;
LABEL_188:
  v96 = (int (__fastcall ***)(_QWORD, _BYTE *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
  *(_QWORD *)pBuffer = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v97 = *v96;
  *(_OWORD *)&pBuffer[8] = 0;
  if ( (*v97)(v96, pBuffer) >= 0
    && *(_DWORD *)&pBuffer[16]
    && *(_DWORD *)&pBuffer[12] >= 3u
    && (*(_DWORD *)&pBuffer[8] == 2 || (pBuffer[8] & 2) != 0) )
  {
    v98 = *(_QWORD *)a2;
    LODWORD(v104) = SecStatus;
    v99 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v98 + 272))(a2);
    v127[1] = 2;
    v127[3] = 21;
    v128 = L"AUTH_SSPI_LOGON_FAILED";
    v134 = 2;
    v141 = (__int64)L"ErrorCode";
    v127[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    *((_QWORD *)&v142 + 1) = &v104;
    v135 = &v136;
    v100 = *v99;
    v127[2] = &`IISAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
    v129 = 1;
    v130 = 3;
    v101 = *(void (__fastcall **)(__int64 *, _QWORD *))(v100 + 16);
    v131 = 0;
    v132 = 0;
    v133 = 1;
    v136 = (GUID *)L"ContextId";
    LODWORD(v137) = 72;
    v138 = 0;
    LODWORD(v139) = 16;
    v140 = 0;
    LODWORD(v142) = 19;
    v143 = 4;
    v145 = 0;
    v101(v99, v127);
  }
LABEL_194:
  if ( v107 )
    SeciFreeCallContext();
LABEL_4:
  BUFFER::~BUFFER((BUFFER *)v147);
  BUFFER::~BUFFER((BUFFER *)v151);
  return (unsigned int)SecStatus;
}

```

## disassembly

```asm
0x1800021f0  push    rbp
0x1800021f2  push    rbx
0x1800021f3  push    rsi
0x1800021f4  push    rdi
0x1800021f5  push    r12
0x1800021f7  push    r13
0x1800021f9  push    r14
0x1800021fb  push    r15
0x1800021fd  lea     rbp, [rsp-398h]
0x180002205  sub     rsp, 498h
0x18000220c  mov     rax, cs:__security_cookie
0x180002213  xor     rax, rsp
0x180002216  mov     [rbp+3D0h+var_50], rax
0x18000221d  xor     r14d, r14d
0x180002220  mov     [rbp+3D0h+var_3B0], r8
0x180002224  xorps   xmm0, xmm0
0x180002227  mov     [rbp+3D0h+var_3B8], rcx
0x18000222b  mov     r13, r8
0x18000222e  mov     qword ptr [rbp+3D0h+var_3F8], r14
0x180002232  mov     rdi, rdx
0x180002235  mov     [rsp+4D0h+var_470], r14d
0x18000223a  xorps   xmm1, xmm1
0x18000223d  mov     [rsp+4D0h+var_460], r14
0x180002242  xor     edx, edx; Val
0x180002244  mov     qword ptr [rsp+4D0h+pBuffer], r9
0x180002249  mov     r8d, 0FFh; Size
0x18000224f  lea     rcx, [rbp+3D0h+var_24F]; void *
0x180002256  movups  xmmword ptr [rbp+3D0h+pToken.ulVersion], xmm0
0x18000225a  movups  [rbp+3D0h+var_430], xmm1
0x18000225e  movups  xmmword ptr [rbp+3D0h+pInput.ulVersion], xmm0
0x180002262  call    memset_0
0x180002267  mov     [rbp+3D0h+var_250], r14b
0x18000226e  lea     rax, [rbp+3D0h+var_250]
0x180002275  mov     [rbp+3D0h+var_260], rax
0x18000227c  lea     rax, [rbp+3D0h+var_2B0]
0x180002283  mov     [rbp+3D0h+var_290], rax
0x18000228a  xorps   xmm0, xmm0
0x18000228d  mov     [rbp+3D0h+var_258], 100h
0x180002297  mov     [rbp+3D0h+var_254], 100h
0x1800022a0  mov     [rsp+4D0h+var_46C], r14d
0x1800022a5  mov     [rbp+3D0h+var_2B0], r14
0x1800022ac  mov     [rbp+3D0h+var_288], 20h ; ' '
0x1800022b6  mov     [rbp+3D0h+var_284], 100h
0x1800022bf  mov     [rsp+4D0h+var_468], r14d
0x1800022c4  mov     [rbp+3D0h+var_420], r14d
0x1800022c8  movups  xmmword ptr [rbp+3D0h+phContext.dwLower], xmm0
0x1800022cc  test    rdi, rdi
0x1800022cf  jz      loc_18000360B
0x1800022d5  test    r13, r13
0x1800022d8  jz      loc_18000360B
0x1800022de  lea     r8, [rbp+3D0h+var_410]; struct SSPI_APP_CONTEXT **
0x1800022e2  mov     [rbp+3D0h+var_410], r14
0x1800022e6  mov     rdx, rdi; struct IHttpContext *
0x1800022e9  call    ?SetupParsedAppContext@SSPI_AUTH_PROVIDER@@QEAAJPEAVIHttpContext@@PEAPEAVSSPI_APP_CONTEXT@@@Z; SSPI_AUTH_PROVIDER::SetupParsedAppContext(IHttpContext *,SSPI_APP_CONTEXT * *)
0x1800022ee  mov     ebx, eax
0x1800022f0  test    eax, eax
0x1800022f2  jns     short loc_180002315
0x1800022f4  lea     rcx, [rbp+3D0h+var_2B0]
0x1800022fb  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002301  lea     rcx, [rbp+3D0h+var_280]
0x180002308  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000230e  mov     eax, ebx
0x180002310  jmp     loc_18000362A
0x180002315  mov     rax, [rdi]
0x180002318  mov     rcx, rdi
0x18000231b  mov     rax, [rax+0F0h]
0x180002322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002327  mov     rdx, rax
0x18000232a  mov     rcx, [rax]
0x18000232d  mov     rax, [rcx+38h]
0x180002331  mov     rcx, rdx
0x180002334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002339  mov     rdx, cs:?s_ModuleId@@3PEAXEA; void * s_ModuleId
0x180002340  mov     r8, rax
0x180002343  mov     rcx, [rax]
0x180002346  mov     rax, [rcx]
0x180002349  mov     rcx, r8
0x18000234c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002351  mov     r12, rax
0x180002354  test    rax, rax
0x180002357  jnz     loc_180002409
0x18000235d  mov     rax, [rdi]
0x180002360  mov     edx, 0D0h
0x180002365  mov     rcx, rdi
0x180002368  mov     rax, [rax+90h]
0x18000236f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002374  mov     r12, rax
0x180002377  test    rax, rax
0x18000237a  jz      loc_1800025A8
0x180002380  lea     rax, ??_7AUTH_REQUEST_CONTEXT@@6B@; const AUTH_REQUEST_CONTEXT::`vftable'
0x180002387  lea     rcx, [r12+8]
0x18000238c  mov     [r12], rax
0x180002390  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180002396  lea     rcx, [r12+48h]
0x18000239b  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800023a1  lea     rcx, [r12+88h]
0x1800023a9  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800023af  mov     [r12+40h], r14
0x1800023b4  mov     rcx, rdi
0x1800023b7  mov     [r12+80h], r14d
0x1800023bf  mov     [r12+0C0h], r14
0x1800023c7  mov     rax, [rdi]
0x1800023ca  mov     rax, [rax+38h]
0x1800023ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023d3  mov     r8, cs:?s_ModuleId@@3PEAXEA; void * s_ModuleId
0x1800023da  mov     r9, rax
0x1800023dd  mov     rdx, r12
0x1800023e0  mov     rcx, [rax]
0x1800023e3  mov     rax, [rcx+8]
0x1800023e7  mov     rcx, r9
0x1800023ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023ef  mov     ebx, eax
0x1800023f1  test    eax, eax
0x1800023f3  jns     short loc_180002409
0x1800023f5  mov     rcx, [r12]
0x1800023f9  mov     rax, [rcx]
0x1800023fc  mov     rcx, r12
0x1800023ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002404  jmp     loc_1800022F4
0x180002409  mov     rcx, [rbp+3D0h+var_410]
0x18000240d  mov     rax, [rdi]
0x180002410  cmp     [rcx+8], r14d
0x180002414  mov     rcx, rdi
0x180002417  mov     rax, [rax+18h]
0x18000241b  jz      loc_18000256D
0x180002421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002426  mov     rdx, rax
0x180002429  mov     rcx, [rax]
0x18000242c  mov     rax, [rcx+8]
0x180002430  mov     rcx, rdx
0x180002433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002438  movzx   r8d, word ptr [rax+350h]
0x180002440  test    r8d, r8d
0x180002443  jz      short loc_180002476
0x180002445  mov     rdx, [rax+358h]
0x18000244c  mov     ecx, r14d
0x18000244f  mov     r15d, 2
0x180002455  mov     eax, ecx
0x180002457  add     rax, rax
0x18000245a  cmp     [rdx+rax*8], r14d
0x18000245e  jnz     short loc_18000246F
0x180002460  mov     rbx, [rdx+rax*8+8]
0x180002465  cmp     [rbx], r14d
0x180002468  jz      short loc_180002488
0x18000246a  cmp     [rbx], r15d
0x18000246d  jz      short loc_180002480
0x18000246f  inc     ecx
0x180002471  cmp     ecx, r8d
0x180002474  jb      short loc_180002455
0x180002476  mov     ebx, 8009030Eh
0x18000247b  jmp     loc_1800022F4
0x180002480  mov     ebx, [rbx+4]
0x180002483  jmp     loc_1800022F4
0x180002488  mov     rax, [rdi]
0x18000248b  mov     edx, 0B0h
0x180002490  mov     rcx, rdi
0x180002493  mov     rax, [rax+90h]
0x18000249a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000249f  mov     rsi, rax
0x1800024a2  test    rax, rax
0x1800024a5  jz      loc_1800025A8
0x1800024ab  lea     rax, ??_7KERNEL_USER_CONTEXT@@6B@; const KERNEL_USER_CONTEXT::`vftable'
0x1800024b2  lea     rcx, [rsi+28h]
0x1800024b6  mov     [rsi], rax
0x1800024b9  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800024bf  lea     rcx, [rsi+78h]
0x1800024c3  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800024c9  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800024cd  mov     dword ptr [rsi+8], 1
0x1800024d4  mov     rdx, rbx; struct _HTTP_REQUEST_AUTH_INFO *
0x1800024d7  mov     [rsi+68h], r15
0x1800024db  mov     rcx, rsi; this
0x1800024de  mov     [rsi+60h], r15
0x1800024e2  mov     [rsi+10h], r14
0x1800024e6  mov     [rsi+18h], r14
0x1800024ea  mov     [rsi+20h], r14
0x1800024ee  mov     [rsi+70h], r14
0x1800024f2  call    ?Initialize@KERNEL_USER_CONTEXT@@QEAAJPEAU_HTTP_REQUEST_AUTH_INFO@@@Z; KERNEL_USER_CONTEXT::Initialize(_HTTP_REQUEST_AUTH_INFO *)
0x1800024f7  mov     ebx, eax
0x1800024f9  test    eax, eax
0x1800024fb  jns     short loc_18000250C
0x1800024fd  mov     rax, [rsi]
0x180002500  mov     rcx, rsi
0x180002503  mov     rax, [rax+38h]
0x180002507  jmp     loc_1800023FF
0x18000250c  lea     rcx, [rsi+78h]
0x180002510  lea     rdx, aNtlm; "NTLM"
0x180002517  call    cs:__imp_?Equals@STRA@@QEBA_NPEBD@Z; STRA::Equals(char const *)
0x18000251d  movzx   ebx, al
0x180002520  mov     rdx, rdi; struct IHttpContext *
0x180002523  mov     r8d, ebx; int
0x180002526  call    ?IsPersistentAuthHeaderTrue@SSPI_AUTH_PROVIDER@@AEAAHPEAVIHttpContext@@H@Z; SSPI_AUTH_PROVIDER::IsPersistentAuthHeaderTrue(IHttpContext *,int)
0x18000252b  test    eax, eax
0x18000252d  mov     dword ptr [r12+0C4h], 1
0x180002539  lea     rdx, aFalse; "false"
0x180002540  mov     r8d, ebx; int
0x180002543  lea     rcx, aTrue; "true"
0x18000254a  cmovz   rcx, rdx
0x18000254e  mov     rdx, rsi; struct IHttpUser *
0x180002551  mov     [r12+0C8h], rcx
0x180002559  mov     rcx, rdi; struct IHttpContext *
0x18000255c  call    ?TraceAuthSucceeded@@YAJPEAVIHttpContext@@PEAVIHttpUser@@H@Z; TraceAuthSucceeded(IHttpContext *,IHttpUser *,int)
0x180002561  mov     [r13+0], rsi
0x180002565  mov     ebx, r14d
0x180002568  jmp     loc_1800022F4
0x18000256d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002572  mov     rdx, rax
0x180002575  mov     rcx, [rax]
0x180002578  mov     rax, [rcx+8]
0x18000257c  mov     rcx, rdx
0x18000257f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002584  mov     rcx, [rax+68h]
0x180002588  mov     rax, [rdi]
0x18000258b  mov     [rbp+3D0h+var_3E0.dwLower], rcx
0x18000258f  mov     rcx, rdi
0x180002592  mov     rax, [rax+10h]
0x180002596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000259b  mov     [rsp+4D0h+var_478], rax
0x1800025a0  mov     r14, rax
0x1800025a3  test    rax, rax
0x1800025a6  jnz     short loc_1800025B2
0x1800025a8  mov     ebx, 80070008h
0x1800025ad  jmp     loc_1800022F4
0x1800025b2  mov     rax, [rdi]
0x1800025b5  mov     rcx, rdi
0x1800025b8  mov     rax, [rax+38h]
0x1800025bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025c1  mov     rdx, cs:?s_ModuleId@@3PEAXEA; void * s_ModuleId
0x1800025c8  mov     r8, rax
0x1800025cb  mov     rcx, [rax]
0x1800025ce  mov     rax, [rcx]
0x1800025d1  mov     rcx, r8
0x1800025d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025d9  mov     [rbp+3D0h+var_418], rax
0x1800025dd  mov     r15, rax
0x1800025e0  test    rax, rax
0x1800025e3  jnz     short loc_1800025EF
0x1800025e5  mov     ebx, 8007000Dh
0x1800025ea  jmp     loc_1800022F4
0x1800025ef  mov     rax, [rdi]
0x1800025f2  mov     rcx, rdi
0x1800025f5  mov     rax, [rax+0E8h]
0x1800025fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002601  test    rax, rax
0x180002604  jz      loc_1800026B2
0x18000260a  mov     rax, [rdi]
0x18000260d  mov     rcx, rdi
0x180002610  mov     rax, [rax+0E8h]
0x180002617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000261c  mov     rdx, rax
0x18000261f  mov     rcx, [rax]
0x180002622  mov     rax, [rcx+30h]
0x180002626  mov     rcx, rdx
0x180002629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000262e  mov     rsi, rax
0x180002631  test    rax, rax
0x180002634  jz      short loc_18000269F
0x180002636  lea     rcx, [rbp+3D0h+var_370]
0x18000263a  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180002640  mov     rax, [rsi]
0x180002643  mov     rcx, rsi
0x180002646  mov     rax, [rax+10h]
0x18000264a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000264f  mov     rdx, rax
0x180002652  lea     rcx, [rbp+3D0h+var_370]
0x180002656  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18000265c  lea     rcx, [rbp+3D0h+var_370]
0x180002660  mov     ebx, eax
0x180002662  test    eax, eax
0x180002664  jns     short loc_180002671
0x180002666  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000266c  jmp     loc_1800022F4
0x180002671  lea     rbx, [r15+28h]
0x180002675  mov     rdx, [rbx]
0x180002678  call    cs:__imp_?EqualsNoCase@STRA@@QEBA_NPEBD@Z; STRA::EqualsNoCase(char const *)
0x18000267e  test    al, al
0x180002680  jz      short loc_1800026A6
0x180002682  mov     rax, [rsi]
0x180002685  mov     rcx, rsi
0x180002688  mov     rax, [rax+30h]
0x18000268c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002691  lea     rcx, [rbp+3D0h+var_370]
0x180002695  mov     [r13+0], rsi
0x180002699  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000269f  xor     ebx, ebx
0x1800026a1  jmp     loc_1800022F4
0x1800026a6  lea     rcx, [rbp+3D0h+var_370]
0x1800026aa  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800026b0  jmp     short loc_1800026B6
0x1800026b2  lea     rbx, [r15+28h]
0x1800026b6  mov     rax, [r14]
0x1800026b9  mov     rcx, r14
0x1800026bc  mov     rax, [rax+10h]
0x1800026c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c5  mov     rdx, cs:?s_ModuleId@@3PEAXEA; void * s_ModuleId
0x1800026cc  mov     r8, rax
0x1800026cf  mov     rcx, [rax]
0x1800026d2  mov     rax, [rcx]
0x1800026d5  mov     rcx, r8
0x1800026d8  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
