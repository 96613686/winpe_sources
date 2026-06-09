# DIGEST_AUTH_PROVIDER::DoAuthenticate(IHttpContext *,IHttpUser * *,AUTH_OUTPUT_FLAGS *)

- ea: `0x180001e00`
- end: `0x180002d7c`
- name: `?DoAuthenticate@DIGEST_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@PEAPEAVIHttpUser@@PEAW4AUTH_OUTPUT_FLAGS@@@Z`
- size: `3964`
- prototype: `__int64 __fastcall(DIGEST_AUTH_PROVIDER *this, struct IHttpContext *, struct IHttpUser **, enum AUTH_OUTPUT_FLAGS *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001024`
- `0x180001064`
- `0x180001e00`
- `0x180004170`
- `0x18000445c`
- `0x180005864`
- `0x180005a64`
- `0x180005f10`
- `0x1800060b4`
- `0x1800063d8`
- `0x1800065c6`
- `0x180006600`
- `0x180007010`

## import_xrefs

- `msvcrt!wcschr` at `0x180002487`
- `msvcrt!wcschr` at `0x180002487`
- `SspiCli!SeciFreeCallContext` at `0x1800022c1`
- `SspiCli!SeciFreeCallContext` at `0x1800022c1`
- `SspiCli!CompleteAuthToken` at `0x18000295f`
- `SspiCli!CompleteAuthToken` at `0x18000295f`
- `SspiCli!VerifySignature` at `0x18000259c`
- `SspiCli!VerifySignature` at `0x18000259c`
- `SspiCli!AcceptSecurityContext` at `0x18000276d`
- `SspiCli!AcceptSecurityContext` at `0x1800028df`
- `SspiCli!AcceptSecurityContext` at `0x18000276d`
- `SspiCli!AcceptSecurityContext` at `0x1800028df`
- `SspiCli!DeleteSecurityContext` at `0x18000225b`
- `SspiCli!DeleteSecurityContext` at `0x18000225b`
- `SspiCli!FreeCredentialsHandle` at `0x180002295`
- `SspiCli!FreeCredentialsHandle` at `0x180002800`
- `SspiCli!FreeCredentialsHandle` at `0x180002bbf`
- `SspiCli!FreeCredentialsHandle` at `0x180002295`
- `SspiCli!FreeCredentialsHandle` at `0x180002800`
- `SspiCli!FreeCredentialsHandle` at `0x180002bbf`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x180002706`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x180002706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d36`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800022ac`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800022e5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800022ff`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002817`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800029d0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002bd6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002c12`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800022ac`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800022e5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800022ff`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002817`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800029d0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002bd6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002c12`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002309`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002309`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800022a2`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000280d`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180002bcc`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800022a2`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000280d`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180002bcc`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180001ead`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002c97`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002cb1`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180001ead`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002c97`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002cb1`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001ef9`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002982`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001ef9`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002982`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001e88`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001ee2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001f21`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001f4c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001e88`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001ee2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001f21`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001f4c`
- `iisutil!PuDbgPrint` at `0x18000209e`
- `iisutil!PuDbgPrint` at `0x180002421`
- `iisutil!PuDbgPrint` at `0x180002681`
- `iisutil!PuDbgPrint` at `0x180002876`
- `iisutil!PuDbgPrint` at `0x180002b7f`
- `iisutil!PuDbgPrint` at `0x18000209e`
- `iisutil!PuDbgPrint` at `0x180002421`
- `iisutil!PuDbgPrint` at `0x180002681`
- `iisutil!PuDbgPrint` at `0x180002876`
- `iisutil!PuDbgPrint` at `0x180002b7f`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002357`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002a27`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002357`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002a27`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800023dd`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800029c0`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800023dd`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800029c0`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800024e3`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800024e3`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000263d`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000263d`
- `iisutil!WriteRefTraceLogEx` at `0x180002251`
- `iisutil!WriteRefTraceLogEx` at `0x1800027b6`
- `iisutil!WriteRefTraceLogEx` at `0x180002923`
- `iisutil!WriteRefTraceLogEx` at `0x180002c56`
- `iisutil!WriteRefTraceLogEx` at `0x180002251`
- `iisutil!WriteRefTraceLogEx` at `0x1800027b6`
- `iisutil!WriteRefTraceLogEx` at `0x180002923`
- `iisutil!WriteRefTraceLogEx` at `0x180002c56`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800024a7`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800024a7`
- `iisutil!UlCleanAndCopyUrl` at `0x180002a52`
- `iisutil!UlCleanAndCopyUrl` at `0x180002a52`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180002a66`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180002a66`
- `iisutil!?Equals@STRU@@QEBA_NPEBG@Z` at `0x180002a75`
- `iisutil!?Equals@STRU@@QEBA_NPEBG@Z` at `0x180002a75`
- `iisutil!?Equals@STRU@@QEBA_NAEBV1@@Z` at `0x180002a97`
- `iisutil!?Equals@STRU@@QEBA_NAEBV1@@Z` at `0x180002a97`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180002abe`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180002abe`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800022cb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800022d8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800022f2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002316`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800022cb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800022d8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800022f2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002316`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002c8d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002ca4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002c8d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002ca4`

## string_xrefs

- `0x180002085`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\digest_auth\digest_auth.cxx`
- `0x180002415`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\digest_auth\digest_auth.cxx`
- `0x180002668`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\digest_auth\digest_auth.cxx`
- `0x18000285d`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\digest_auth\digest_auth.cxx`
- `0x180002b78`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\digest_auth\digest_auth.cxx`
- `0x180002506`: `Error copying the URL.  hr = %x\n`
- `0x18000266f`: `Error reading the realm.  hr = %x\n`
- `0x180002449`: `REQUEST_URI`

## pseudocode

```c
__int64 __fastcall DIGEST_AUTH_PROVIDER::DoAuthenticate(
        DIGEST_AUTH_PROVIDER *this,
        struct IHttpContext *a2,
        struct IHttpUser **a3,
        enum AUTH_OUTPUT_FLAGS *a4)
{
  char *v5; // rdi
  signed int v6; // ebx
  DIGEST_AUTH_PROVIDER *v7; // r12
  __int64 (__fastcall ***v8)(_QWORD, void *); // rax
  __int64 v9; // r13
  __int64 (__fastcall ***v10)(_QWORD, void *); // rax
  __int64 v11; // rsi
  __int64 v12; // r14
  _WORD *v13; // r12
  const char *v14; // rcx
  struct MULTISZ *v15; // r8
  int ReferencedCredential; // eax
  int (__fastcall ***v17)(_QWORD, GUID **); // rax
  int (__fastcall **v18)(_QWORD, GUID **); // rcx
  __int64 v19; // rax
  __int64 *v20; // rcx
  __int64 v21; // rax
  void (__fastcall *v22)(__int64 *, _QWORD *); // rax
  __int64 v23; // rcx
  __int64 v25; // rax
  const char *v26; // rax
  int v27; // eax
  __int64 v28; // rax
  wchar_t *v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // r14
  int v34; // r13d
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 (__fastcall ***v37)(_QWORD, void *); // rax
  __int64 v38; // rax
  int v39; // eax
  __int64 v40; // rdx
  DIGEST_AUTH_PROVIDER *v41; // r13
  __int64 v42; // rcx
  const char *v43; // rcx
  struct MULTISZ *v44; // r8
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rax
  const char *v49; // rax
  DIGEST_AUTH_PROVIDER *v50; // rcx
  char **v51; // r8
  unsigned int v52; // r9d
  char *v53; // r12
  __int64 v54; // rbx
  _QWORD *v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rax
  volatile signed __int32 *v58; // rbx
  __int64 v59; // rcx
  _DWORD *v60; // r14
  int v61; // r8d
  DWORD LastError; // eax
  DIGEST_AUTH_PROVIDER *v63; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int pfContextAttr; // [rsp+60h] [rbp-A0h] BYREF
  int v66; // [rsp+64h] [rbp-9Ch] BYREF
  wchar_t *Str; // [rsp+68h] [rbp-98h] BYREF
  int v68; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v69; // [rsp+74h] [rbp-8Ch] BYREF
  _SecBufferDesc pMessage; // [rsp+78h] [rbp-88h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+88h] [rbp-78h] BYREF
  __int64 v72; // [rsp+90h] [rbp-70h]
  struct _SecBufferDesc pOutput; // [rsp+98h] [rbp-68h] BYREF
  GUID *v74; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v75; // [rsp+B0h] [rbp-50h]
  __int64 v76; // [rsp+C0h] [rbp-40h]
  struct IHttpUser **v77; // [rsp+C8h] [rbp-38h]
  _DWORD v78[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v79; // [rsp+D8h] [rbp-28h]
  _SecHandle phContext; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v81[4]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD *v82; // [rsp+110h] [rbp+10h]
  int v83; // [rsp+118h] [rbp+18h]
  __int16 v84; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v85; // [rsp+120h] [rbp+20h] BYREF
  int v86; // [rsp+128h] [rbp+28h]
  __int64 v87; // [rsp+130h] [rbp+30h]
  int v88; // [rsp+138h] [rbp+38h]
  __int64 v89; // [rsp+140h] [rbp+40h]
  const wchar_t *v90; // [rsp+148h] [rbp+48h]
  int v91; // [rsp+150h] [rbp+50h]
  DIGEST_AUTH_PROVIDER **v92; // [rsp+158h] [rbp+58h]
  int v93; // [rsp+160h] [rbp+60h]
  __int64 v94; // [rsp+168h] [rbp+68h]
  _BYTE v95[32]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 *v96; // [rsp+190h] [rbp+90h]
  _BYTE v97[32]; // [rsp+1A8h] [rbp+A8h] BYREF
  _QWORD *v98; // [rsp+1C8h] [rbp+C8h]
  unsigned int v99; // [rsp+1D8h] [rbp+D8h]
  _BYTE v100[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v101; // [rsp+200h] [rbp+100h]
  int v102; // [rsp+210h] [rbp+110h]
  _BYTE v103[48]; // [rsp+218h] [rbp+118h] BYREF
  int v104; // [rsp+248h] [rbp+148h]
  _BYTE v105[32]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v106; // [rsp+270h] [rbp+170h]
  int v107; // [rsp+280h] [rbp+180h]
  _BYTE v108[56]; // [rsp+288h] [rbp+188h] BYREF
  _DWORD v109[2]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v110; // [rsp+2C8h] [rbp+1C8h]
  int v111; // [rsp+2D0h] [rbp+1D0h]
  int v112; // [rsp+2D4h] [rbp+1D4h]
  __int64 v113; // [rsp+2D8h] [rbp+1D8h]
  int v114; // [rsp+2E0h] [rbp+1E0h]
  int v115; // [rsp+2E4h] [rbp+1E4h]
  __int64 v116; // [rsp+2E8h] [rbp+1E8h]
  int v117; // [rsp+2F0h] [rbp+1F0h]
  int v118; // [rsp+2F4h] [rbp+1F4h]
  __int64 v119; // [rsp+2F8h] [rbp+1F8h]
  int v120; // [rsp+300h] [rbp+200h]
  int v121; // [rsp+304h] [rbp+204h]
  _QWORD *v122; // [rsp+308h] [rbp+208h]
  _QWORD v123[5]; // [rsp+310h] [rbp+210h] BYREF
  int v124; // [rsp+338h] [rbp+238h]
  int v125; // [rsp+33Ch] [rbp+23Ch]
  __int128 v126; // [rsp+340h] [rbp+240h]
  int v127; // [rsp+350h] [rbp+250h]
  int v128; // [rsp+354h] [rbp+254h]
  __int64 v129; // [rsp+358h] [rbp+258h]
  const wchar_t **v130; // [rsp+360h] [rbp+260h]
  unsigned __int16 v131[32]; // [rsp+390h] [rbp+290h] BYREF
  char v132[64]; // [rsp+3D0h] [rbp+2D0h] BYREF
  unsigned __int16 v133[64]; // [rsp+410h] [rbp+310h] BYREF
  unsigned __int16 v134[256]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v135[264]; // [rsp+690h] [rbp+590h] BYREF

  v77 = a3;
  v63 = this;
  Block = 0;
  ptsExpiry.QuadPart = 0;
  pfContextAttr = 0;
  v5 = 0;
  pOutput = 0;
  pMessage = 0;
  memset_0(v134, 0, sizeof(v134));
  STRU::STRU((STRU *)v108, v134, 0x100u);
  v81[0] = 0;
  v82 = v81;
  v83 = 32;
  v84 = 256;
  STRA::STRA((STRA *)v105);
  Str = 0;
  v68 = 0;
  memset_0(v133, 0, sizeof(v133));
  STRU::STRU((STRU *)v103, v133, 0x40u);
  STRA::STRA((STRA *)v100, v132, 0x40u);
  memset_0(v131, 0, sizeof(v131));
  STRU::STRU((STRU *)v97, v131, 0x20u);
  memset_0(v135, 0, 0x20Au);
  STRU::STRU((STRU *)v95, v135, 0x105u);
  v69 = 0;
  v66 = 0;
  phContext.dwUpper = -1;
  phContext.dwLower = -1;
  if ( !a2 )
  {
    v6 = -2147024809;
LABEL_3:
    v7 = v63;
    goto LABEL_17;
  }
  v8 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 56LL))(a2);
  v72 = (**v8)(v8, s_pModuleContext);
  v9 = v72;
  if ( !v72 )
  {
    v6 = -2147024883;
    goto LABEL_3;
  }
  v76 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 16LL))(a2);
  v10 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
  v11 = (**v10)(v10, s_pModuleContext);
  if ( v11 )
  {
    if ( (unsigned int)IsProxyRequest(a2) )
      SSPI_SECURITY_CONTEXT::Reset((SSPI_SECURITY_CONTEXT *)v11);
    if ( *(_QWORD *)(v11 + 32) != -1
      && *(_QWORD *)(v11 + 40) != -1
      && (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 232LL))(a2) )
    {
      v7 = v63;
LABEL_123:
      v60 = operator new(0x120u);
      if ( v60 )
      {
        *(_QWORD *)v60 = &SSPI_USER_CONTEXT::`vftable';
        STRU::STRU((STRU *)(v60 + 8));
        STRA::STRA((STRA *)(v60 + 22));
        STRU::STRU((STRU *)(v60 + 36));
        STRA::STRA((STRA *)(v60 + 56));
        v60[2] = 1;
        *((_QWORD *)v60 + 2) = 0;
        *((_QWORD *)v60 + 3) = 0;
        v60[54] = 0;
        *((_QWORD *)v60 + 35) = 0;
        v6 = SSPI_USER_CONTEXT::Create(
               (SSPI_USER_CONTEXT *)v60,
               (struct SSPI_SECURITY_CONTEXT *)v11,
               *(char **)(v9 + 40));
        if ( v6 >= 0 )
        {
          *v77 = (struct IHttpUser *)v60;
          TraceAuthSucceeded(a2, (struct IHttpUser *)v60, v61);
          v6 = 0;
LABEL_23:
          if ( phContext.dwLower != -1 && phContext.dwUpper != -1 )
          {
            v23 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 80LL);
            if ( v23 )
              WriteRefTraceLogEx(v23, 0, phContext.dwLower, phContext.dwUpper, 0, 0);
            DeleteSecurityContext(&phContext);
          }
          if ( v5 && _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 1, 0xFFFFFFFF) == 1 )
          {
            *(_DWORD *)v5 = 1396917094;
            if ( *((_QWORD *)v5 + 25) != -1 && *((_QWORD *)v5 + 26) != -1 )
              FreeCredentialsHandle((PCredHandle)(v5 + 200));
            MULTISZ::~MULTISZ((MULTISZ *)(v5 + 144));
            STRA::~STRA((STRA *)(v5 + 8));
            operator delete(v5);
          }
          if ( v66 )
            SeciFreeCallContext();
          goto LABEL_36;
        }
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v60 + 56LL))(v60);
      }
      else
      {
        v6 = -2147024888;
      }
LABEL_17:
      v17 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      v74 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v18 = *v17;
      v75 = 0;
      if ( (*v18)(v17, &v74) >= 0 && DWORD2(v75) && DWORD1(v75) >= 3 && ((_DWORD)v75 == 2 || (v75 & 2) != 0) )
      {
        v19 = *(_QWORD *)a2;
        LODWORD(v63) = v6;
        v20 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v19 + 272))(a2);
        v123[1] = 2;
        v123[3] = 18;
        v123[2] = &`IISAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
        v129 = 2;
        v123[4] = L"AUTH_WDIGEST_LOGON_FAILED";
        v123[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v85 = L"ContextId";
        v90 = L"ErrorCode";
        v92 = &v63;
        v130 = &v85;
        v21 = *v20;
        v124 = 1;
        v125 = 3;
        v126 = 0;
        v22 = *(void (__fastcall **)(__int64 *, _QWORD *))(v21 + 16);
        v127 = 0;
        v128 = 1;
        v86 = 72;
        v87 = 0;
        v88 = 16;
        v89 = 0;
        v91 = 19;
        v93 = 4;
        v94 = 0;
        v22(v20, v123);
      }
      goto LABEL_23;
    }
  }
  v12 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v13 = *(_WORD **)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12) + 104);
  ReferencedCredential = SSPI_CREDENTIAL::GetReferencedCredential(v14, (struct SSPI_CREDENTIAL **)&Block, v15);
  v6 = ReferencedCredential;
  if ( ReferencedCredential < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\digest_auth\\digest_auth.cxx",
        1048,
        "DIGEST_AUTH_PROVIDER::DoAuthenticate",
        "Error get credential handle. hr = 0x%x \n",
        ReferencedCredential);
LABEL_15:
    v5 = (char *)Block;
    goto LABEL_16;
  }
  v5 = (char *)Block;
  if ( !BUFFER::Resize((BUFFER *)v81, *((_DWORD *)Block + 54)) )
  {
    v6 = -2147024888;
    goto LABEL_16;
  }
  memset_0(v109, 0, 0x50u);
  pMessage.ulVersion = 0;
  pMessage.pBuffers = (PSecBuffer)v109;
  v25 = -1;
  pMessage.cBuffers = 5;
  v109[1] = 2;
  do
    ++v25;
  while ( *(_BYTE *)(*(_QWORD *)(v9 + 64) + v25) );
  v109[0] = v25;
  v110 = *(_QWORD *)(v9 + 64);
  v26 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 64LL))(v12);
  v27 = STRA::Copy((STRA *)v105, v26);
  v6 = v27;
  if ( v27 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\digest_auth\\digest_auth.cxx",
        1096,
        "DIGEST_AUTH_PROVIDER::DoAuthenticate",
        "Error getting the method.  hr = %x\n",
        v27);
    goto LABEL_16;
  }
  v111 = v107;
  v113 = v106;
  v28 = *(_QWORD *)a2;
  v112 = 3;
  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *, const char *, wchar_t **, int *))(v28 + 128))(
         a2,
         "REQUEST_URI",
         &Str,
         &v68);
  if ( v6 < 0 || (v29 = wcschr(Str, 0x3Fu)) != 0 && (v6 = STRU::Copy((STRU *)v103, Str, v29 - Str), v6 < 0) )
  {
LABEL_16:
    v7 = v63;
    goto LABEL_17;
  }
  v30 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
  v32 = STRA::CopyW((STRA *)v100, *(const unsigned __int16 **)(v31 + 88));
  v6 = v32;
  if ( v32 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\digest_auth\\digest_auth.cxx",
        1132,
        "DIGEST_AUTH_PROVIDER::DoAuthenticate",
        "Error copying the URL.  hr = %x\n",
        v32);
    goto LABEL_16;
  }
  v114 = v102;
  v116 = v101;
  v115 = 3;
  v118 = 3;
  v117 = 0;
  v119 = 0;
  if ( v11 )
  {
    LODWORD(v33) = 0;
    if ( *(_QWORD *)(v11 + 32) != -1 )
    {
      if ( *(_QWORD *)(v11 + 40) != -1 )
      {
        v120 = v83;
        v122 = v82;
        v121 = 2;
        LODWORD(v33) = VerifySignature((PCtxtHandle)(v11 + 32), &pMessage, 0, 0);
        if ( (int)v33 < 0 )
          SSPI_SECURITY_CONTEXT::Reset((SSPI_SECURITY_CONTEXT *)v11);
      }
      if ( *(_QWORD *)(v11 + 32) != -1 && *(_QWORD *)(v11 + 40) != -1 )
      {
        v34 = 0;
        if ( (int)v33 >= 0 )
          goto LABEL_89;
      }
    }
  }
  pOutput.ulVersion = 0;
  pOutput.pBuffers = (PSecBuffer)v78;
  v78[0] = v83;
  v79 = v82;
  v35 = *(_QWORD *)a2;
  pOutput.cBuffers = 1;
  v78[1] = 2;
  v36 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v35 + 160))(a2);
  v37 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 24LL))(v36);
  v38 = (**v37)(v37, s_pModuleContext);
  v39 = STRU::Copy((STRU *)v97, (const struct STRU *)(v38 + 16));
  v6 = v39;
  if ( v39 >= 0 )
  {
    if ( v99 )
    {
      if ( v99 > 0x400 )
      {
        v6 = -2147467259;
        goto LABEL_36;
      }
      v120 = 2 * v99;
      v122 = v98;
    }
    else
    {
      v120 = 0;
      v122 = 0;
    }
    v121 = 3;
    if ( v13 )
    {
      if ( *v13 == 2 )
      {
        v40 = 16;
      }
      else
      {
        if ( *v13 != 23 )
          goto LABEL_72;
        v40 = 28;
      }
      v6 = SeciAllocateAndSetIPAddress(v13, v40, &v66);
      if ( v6 < 0 )
        goto LABEL_3;
    }
LABEL_72:
    (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 24LL))(s_pGlobalInfo);
    v33 = AcceptSecurityContext(
            (PCredHandle)(v5 + 200),
            0,
            &pMessage,
            0x804u,
            0x10u,
            &phContext,
            &pOutput,
            &pfContextAttr,
            &ptsExpiry);
    (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 32LL))(s_pGlobalInfo);
    v41 = v63;
    v42 = *(_QWORD *)(*((_QWORD *)v63 + 2) + 80LL);
    if ( v42 )
      WriteRefTraceLogEx(v42, 1, phContext.dwLower, phContext.dwUpper, v33, 0);
    if ( (_DWORD)v33 == -2146893022 )
    {
      SSPI_CREDENTIAL::RemoveCredentialFromCache((struct SSPI_CREDENTIAL *)v5);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 1, 0xFFFFFFFF) == 1 && v5 )
      {
        *(_DWORD *)v5 = 1396917094;
        if ( *((_QWORD *)v5 + 25) != -1 && *((_QWORD *)v5 + 26) != -1 )
          FreeCredentialsHandle((PCredHandle)(v5 + 200));
        MULTISZ::~MULTISZ((MULTISZ *)(v5 + 144));
        STRA::~STRA((STRA *)(v5 + 8));
        operator delete(v5);
      }
      Block = 0;
      v45 = SSPI_CREDENTIAL::GetReferencedCredential(v43, (struct SSPI_CREDENTIAL **)&Block, v44);
      v6 = v45;
      if ( v45 < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\digest_auth\\digest_auth.cxx",
            1313,
            "DIGEST_AUTH_PROVIDER::DoAuthenticate",
            "Error get credential handle. hr = 0x%x \n",
            v45);
          v5 = (char *)Block;
          v7 = v41;
          goto LABEL_17;
        }
        goto LABEL_15;
      }
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 24LL))(s_pGlobalInfo);
      v5 = (char *)Block;
      v33 = AcceptSecurityContext(
              (PCredHandle)((char *)Block + 200),
              0,
              &pMessage,
              0x804u,
              0x10u,
              &phContext,
              &pOutput,
              &pfContextAttr,
              &ptsExpiry);
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 32LL))(s_pGlobalInfo);
      v46 = *(_QWORD *)(*((_QWORD *)v41 + 2) + 80LL);
      if ( v46 )
        WriteRefTraceLogEx(v46, 1, phContext.dwLower, phContext.dwUpper, v33, 0);
    }
    v34 = 1;
    if ( (_DWORD)v33 == 590611 )
    {
      v120 = v83;
      v122 = v82;
      v121 = 2;
      LODWORD(v33) = CompleteAuthToken(&phContext, &pMessage);
    }
    if ( (int)v33 < 0 )
    {
      v7 = v63;
      goto LABEL_129;
    }
LABEL_89:
    STRA::STRA((STRA *)&v85, (char *)v123, 0x80u);
    v47 = *(_QWORD *)a2;
    Block = 0;
    v48 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v47 + 24))(a2);
    v49 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 16LL))(v48, 24);
    v6 = STRA::Copy((STRA *)&v85, v49);
    if ( v6 < 0 )
      goto LABEL_90;
    v6 = DIGEST_AUTH_PROVIDER::ParseForName(v50, (char *)(v89 + 6), v51, v52, (char **)&Block);
    if ( v6 < 0 )
      goto LABEL_90;
    v53 = (char *)Block;
    if ( !Block )
      goto LABEL_119;
    v54 = -1;
    do
      ++v54;
    while ( *((_BYTE *)Block + v54) );
    if ( !(_DWORD)v54 )
      goto LABEL_119;
    if ( !BUFFER::Resize((BUFFER *)v95, 2 * v54 + 2) )
    {
LABEL_97:
      v6 = -2147024888;
LABEL_90:
      STRA::~STRA((STRA *)&v85);
      goto LABEL_16;
    }
    v6 = UlCleanAndCopyUrl(v53, v54, &v69, v96, 0);
    if ( v6 < 0 )
      goto LABEL_90;
    STRU::SyncWithBuffer((STRU *)v95);
    if ( STRU::Equals((STRU *)v95, Str) || v104 && STRU::Equals((STRU *)v103, (const struct STRU *)v95) )
    {
      if ( v34 )
      {
        if ( v11 )
        {
          v58 = *(volatile signed __int32 **)(v11 + 16);
          if ( v58 && _InterlockedExchangeAdd(v58 + 1, 0xFFFFFFFF) == 1 )
          {
            *v58 = 1396917094;
            if ( *((_QWORD *)v58 + 25) != -1 && *((_QWORD *)v58 + 26) != -1 )
              FreeCredentialsHandle((PCredHandle)(v58 + 50));
            MULTISZ::~MULTISZ((MULTISZ *)(v58 + 36));
            STRA::~STRA((STRA *)(v58 + 2));
            operator delete((void *)v58);
          }
          *(_QWORD *)(v11 + 16) = v5;
          v5 = 0;
        }
        else
        {
          v55 = ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext);
          v11 = (__int64)v55;
          if ( !v55 )
            goto LABEL_97;
          v56 = v76;
          v55[2] = v5;
          v5 = 0;
          v55[5] = -1;
          v55[4] = -1;
          v55[3] = 0;
          v55[7] = 0;
          *((_DWORD *)v55 + 2) = 1;
          *v55 = &DIGEST_SSPI_SECURITY_CONTEXT::`vftable';
          v57 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
          v6 = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v57 + 8LL))(v57, v11, s_pModuleContext);
          if ( v6 < 0 )
          {
            (**(void (__fastcall ***)(__int64))v11)(v11);
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\digest_auth\\digest_auth.cxx",
                1525,
                "DIGEST_AUTH_PROVIDER::DoAuthenticate",
                "Failed to set Connection Auth Context. hr = 0x%x \n",
                v6);
            goto LABEL_90;
          }
        }
        *(_SecHandle *)(v11 + 32) = phContext;
        *(_DWORD *)(v11 + 24) = 1;
        phContext.dwUpper = -1;
        phContext.dwLower = -1;
        *(_DWORD *)(v11 + 48) = pfContextAttr;
      }
      v7 = v63;
    }
    else
    {
LABEL_119:
      v7 = v63;
      v59 = *(_QWORD *)(*((_QWORD *)v63 + 2) + 80LL);
      if ( v59 )
        WriteRefTraceLogEx(v59, 0, phContext.dwLower, phContext.dwUpper, 0, 0);
      LODWORD(v33) = -2146893041;
    }
    STRA::~STRA((STRA *)&v85);
    if ( (int)v33 >= 0 )
    {
      v9 = v72;
      goto LABEL_123;
    }
LABEL_129:
    LastError = GetLastError();
    if ( (_DWORD)v33 == -2146893040 )
      *(_DWORD *)(v72 + 208) = 1;
    if ( LastError == 1907 || LastError == 1330 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    else
      v6 = v33;
    goto LABEL_17;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\digest_auth\\digest_auth.cxx",
      1221,
      "DIGEST_AUTH_PROVIDER::DoAuthenticate",
      "Error reading the realm.  hr = %x\n",
      v39);
LABEL_36:
  STRU::~STRU((STRU *)v95);
  STRU::~STRU((STRU *)v97);
  STRA::~STRA((STRA *)v100);
  STRU::~STRU((STRU *)v103);
  STRA::~STRA((STRA *)v105);
  BUFFER::~BUFFER((BUFFER *)v81);
  STRU::~STRU((STRU *)v108);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180001e00  mov     [rsp-8+arg_18], rbx
0x180001e05  push    rbp
0x180001e06  push    rsi
0x180001e07  push    rdi
0x180001e08  push    r12
0x180001e0a  push    r13
0x180001e0c  push    r14
0x180001e0e  push    r15
0x180001e10  lea     rbp, [rsp-7B0h]
0x180001e18  sub     rsp, 8B0h
0x180001e1f  mov     rax, cs:__security_cookie
0x180001e26  xor     rax, rsp
0x180001e29  mov     [rbp+7E0h+var_40], rax
0x180001e30  xor     ebx, ebx
0x180001e32  mov     [rbp+7E0h+var_818], r8
0x180001e36  xorps   xmm0, xmm0
0x180001e39  mov     [rsp+8E0h+var_890], rcx
0x180001e3e  mov     r15, rdx
0x180001e41  mov     [rsp+8E0h+Block], rbx
0x180001e46  xorps   xmm1, xmm1
0x180001e49  mov     qword ptr [rbp+7E0h+var_858], rbx
0x180001e4d  xor     edx, edx; Val
0x180001e4f  mov     [rsp+8E0h+var_880], ebx
0x180001e53  mov     r8d, 200h; Size
0x180001e59  lea     rcx, [rbp+7E0h+var_450]; void *
0x180001e60  mov     edi, ebx
0x180001e62  movups  xmmword ptr [rbp+7E0h+var_848.ulVersion], xmm0
0x180001e66  movups  xmmword ptr [rsp+8E0h+pMessage.ulVersion], xmm1
0x180001e6b  movups  xmmword ptr [rbp+7E0h+phContext.dwLower], xmm0
0x180001e6f  call    memset_0
0x180001e74  mov     r8d, 100h
0x180001e7a  lea     rdx, [rbp+7E0h+var_450]
0x180001e81  lea     rcx, [rbp+7E0h+var_658]
0x180001e88  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001e8e  lea     rax, [rbp+7E0h+var_7F0]
0x180001e92  mov     [rbp+7E0h+var_7F0], rbx
0x180001e96  lea     esi, [rbx+20h]
0x180001e99  mov     [rbp+7E0h+var_7D0], rax
0x180001e9d  lea     rcx, [rbp+7E0h+var_690]
0x180001ea4  mov     [rbp+7E0h+var_7C8], esi
0x180001ea7  mov     [rbp+7E0h+var_7C4], 100h
0x180001ead  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180001eb3  xor     edx, edx; Val
0x180001eb5  mov     [rsp+8E0h+Str], rbx
0x180001eba  lea     r8d, [rsi+60h]; Size
0x180001ebe  mov     [rsp+8E0h+var_870], ebx
0x180001ec2  lea     rcx, [rbp+7E0h+var_4D0]; void *
0x180001ec9  call    memset_0
0x180001ece  lea     ebx, [rdi+40h]
0x180001ed1  mov     r8d, ebx
0x180001ed4  lea     rdx, [rbp+7E0h+var_4D0]
0x180001edb  lea     rcx, [rbp+7E0h+var_6C8]
0x180001ee2  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001ee8  mov     r8d, ebx
0x180001eeb  lea     rdx, [rbp+7E0h+var_510]
0x180001ef2  lea     rcx, [rbp+7E0h+var_700]
0x180001ef9  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180001eff  mov     r8d, ebx; Size
0x180001f02  lea     rcx, [rbp+7E0h+var_550]; void *
0x180001f09  xor     edx, edx; Val
0x180001f0b  call    memset_0
0x180001f10  mov     r8d, esi
0x180001f13  lea     rdx, [rbp+7E0h+var_550]
0x180001f1a  lea     rcx, [rbp+7E0h+var_738]
0x180001f21  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001f27  xor     edx, edx; Val
0x180001f29  lea     rcx, [rbp+7E0h+var_250]; void *
0x180001f30  mov     r8d, 20Ah; Size
0x180001f36  call    memset_0
0x180001f3b  mov     r8d, 105h
0x180001f41  lea     rdx, [rbp+7E0h+var_250]
0x180001f48  lea     rcx, [rbp+7E0h+var_770]
0x180001f4c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001f52  or      r13, 0FFFFFFFFFFFFFFFFh
0x180001f56  mov     [rsp+8E0h+var_86C], edi
0x180001f5a  mov     [rsp+8E0h+var_87C], edi
0x180001f5e  lea     r14d, [rdi+2]
0x180001f62  mov     [rbp+7E0h+phContext.dwUpper], r13
0x180001f66  mov     [rbp+7E0h+phContext.dwLower], r13
0x180001f6a  test    r15, r15
0x180001f6d  jnz     short loc_180001F7E
0x180001f6f  mov     ebx, 80070057h
0x180001f74  mov     r12, [rsp+8E0h+var_890]
0x180001f79  jmp     loc_1800020B4
0x180001f7e  mov     rax, [r15]
0x180001f81  mov     rcx, r15
0x180001f84  mov     rax, [rax+38h]
0x180001f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f8d  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180001f94  mov     rcx, rax
0x180001f97  mov     rax, [rax]
0x180001f9a  mov     rax, [rax]
0x180001f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fa2  mov     [rbp+7E0h+var_850], rax
0x180001fa6  mov     r13, rax
0x180001fa9  test    rax, rax
0x180001fac  jnz     short loc_180001FB5
0x180001fae  mov     ebx, 8007000Dh
0x180001fb3  jmp     short loc_180001F74
0x180001fb5  mov     rax, [r15]
0x180001fb8  mov     rcx, r15
0x180001fbb  mov     rax, [rax+10h]
0x180001fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fc4  mov     rcx, rax
0x180001fc7  mov     [rbp+7E0h+var_820], rax
0x180001fcb  mov     rax, [rax]
0x180001fce  mov     rax, [rax+10h]
0x180001fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fd7  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180001fde  mov     rcx, rax
0x180001fe1  mov     rax, [rax]
0x180001fe4  mov     rax, [rax]
0x180001fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fec  mov     rsi, rax
0x180001fef  test    rax, rax
0x180001ff2  jz      short loc_180002031
0x180001ff4  mov     rcx, r15; struct IHttpContext *
0x180001ff7  call    ?IsProxyRequest@@YAHPEAVIHttpContext@@@Z; IsProxyRequest(IHttpContext *)
0x180001ffc  test    eax, eax
0x180001ffe  jz      short loc_180002008
0x180002000  mov     rcx, rsi; this
0x180002003  call    ?Reset@SSPI_SECURITY_CONTEXT@@QEAAXXZ; SSPI_SECURITY_CONTEXT::Reset(void)
0x180002008  cmp     qword ptr [rsi+20h], 0FFFFFFFFFFFFFFFFh
0x18000200d  jz      short loc_180002031
0x18000200f  cmp     qword ptr [rsi+28h], 0FFFFFFFFFFFFFFFFh
0x180002014  jz      short loc_180002031
0x180002016  mov     rax, [r15]
0x180002019  mov     rcx, r15
0x18000201c  mov     rax, [rax+0E8h]
0x180002023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002028  test    rax, rax
0x18000202b  jnz     loc_180002C64
0x180002031  mov     rax, [r15]
0x180002034  mov     rcx, r15
0x180002037  mov     rax, [rax+18h]
0x18000203b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002040  mov     r14, rax
0x180002043  mov     rcx, r14
0x180002046  mov     rax, [rax]
0x180002049  mov     rax, [rax+8]
0x18000204d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002052  lea     rdx, [rsp+8E0h+Block]; struct SSPI_CREDENTIAL **
0x180002057  mov     r12, [rax+68h]
0x18000205b  call    ?GetReferencedCredential@SSPI_CREDENTIAL@@SAJPEBDPEAPEAV1@PEAVMULTISZ@@@Z; SSPI_CREDENTIAL::GetReferencedCredential(char const *,SSPI_CREDENTIAL * *,MULTISZ *)
0x180002060  mov     ebx, eax
0x180002062  test    eax, eax
0x180002064  jns     loc_180002348
0x18000206a  test    byte ptr cs:g_dwDebugFlags, 3
0x180002071  jz      short loc_1800020A4
0x180002073  mov     rcx, cs:g_pDebug
0x18000207a  lea     r9, aDigestAuthProv_0; "DIGEST_AUTH_PROVIDER::DoAuthenticate"
0x180002081  mov     dword ptr [rsp+8E0h+phNewContext], eax
0x180002085  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000208c  lea     rax, aErrorGetCreden; "Error get credential handle. hr = 0x%x "...
0x180002093  mov     r8d, 418h
0x180002099  mov     qword ptr [rsp+8E0h+TargetDataRep], rax
0x18000209e  call    cs:__imp_PuDbgPrint
0x1800020a4  mov     rdi, [rsp+8E0h+Block]
0x1800020a9  mov     r12, [rsp+8E0h+var_890]
0x1800020ae  mov     r14d, 2
0x1800020b4  mov     rax, [r15]
0x1800020b7  mov     rcx, r15
0x1800020ba  mov     rax, [rax+110h]
0x1800020c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020c6  mov     r8, rax
0x1800020c9  lea     rsi, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800020d0  xorps   xmm0, xmm0
0x1800020d3  mov     [rbp+7E0h+var_838], rsi
0x1800020d7  lea     rdx, [rbp+7E0h+var_838]
0x1800020db  mov     rcx, [rax]
0x1800020de  movdqu  [rbp+7E0h+var_830], xmm0
0x1800020e3  mov     rax, [rcx]
0x1800020e6  mov     rcx, r8
0x1800020e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ee  test    eax, eax
0x1800020f0  js      loc_18000221B
0x1800020f6  cmp     dword ptr [rbp+7E0h+var_830+8], 0
0x1800020fa  jz      loc_18000221B
0x180002100  cmp     dword ptr [rbp+7E0h+var_830+4], 3
0x180002104  jb      loc_18000221B
0x18000210a  cmp     dword ptr [rbp+7E0h+var_830], r14d
0x18000210e  jz      short loc_18000211A
0x180002110  test    byte ptr [rbp+7E0h+var_830], r14b
0x180002114  jz      loc_18000221B
0x18000211a  mov     rax, [r15]
0x18000211d  mov     rcx, r15
0x180002120  mov     dword ptr [rsp+8E0h+var_890], ebx
0x180002124  mov     rax, [rax+110h]
0x18000212b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002130  mov     rcx, rax
0x180002133  mov     [rbp+7E0h+var_5C8], 2
0x18000213e  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180002145  mov     [rbp+7E0h+var_5B8], 12h
0x180002150  mov     [rbp+7E0h+var_5C0], rax
0x180002157  lea     rdx, [rbp+7E0h+var_5D0]
0x18000215e  lea     rax, aAuthWdigestLog; "AUTH_WDIGEST_LOGON_FAILED"
0x180002165  mov     [rbp+7E0h+var_588], 2
0x180002170  mov     [rbp+7E0h+var_5B0], rax
0x180002177  xorps   xmm0, xmm0
0x18000217a  lea     rax, aContextid; "ContextId"
0x180002181  mov     [rbp+7E0h+var_5D0], rsi
0x180002188  mov     [rbp+7E0h+var_7C0], rax
0x18000218c  lea     rax, aErrorcode; "ErrorCode"
0x180002193  mov     [rbp+7E0h+var_798], rax
0x180002197  lea     rax, [rsp+8E0h+var_890]
0x18000219c  mov     [rbp+7E0h+var_788], rax
0x1800021a0  lea     rax, [rbp+7E0h+var_7C0]
0x1800021a4  mov     [rbp+7E0h+var_580], rax
0x1800021ab  mov     rax, [rcx]
0x1800021ae  mov     [rbp+7E0h+var_5A8], 1
0x1800021b8  mov     [rbp+7E0h+var_5A4], 3
0x1800021c2  movdqa  [rbp+7E0h+var_5A0], xmm0
0x1800021ca  mov     rax, [rax+10h]
0x1800021ce  mov     [rbp+7E0h+var_590], 0
0x1800021d8  mov     [rbp+7E0h+var_58C], 1
0x1800021e2  mov     [rbp+7E0h+var_7B8], 48h ; 'H'
0x1800021e9  mov     [rbp+7E0h+var_7B0], 0
0x1800021f1  mov     [rbp+7E0h+var_7A8], 10h
0x1800021f8  mov     [rbp+7E0h+var_7A0], 0
0x180002200  mov     [rbp+7E0h+var_790], 13h
0x180002207  mov     [rbp+7E0h+var_780], 4
0x18000220e  mov     [rbp+7E0h+var_778], 0
0x180002216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000221b  mov     r8, [rbp+7E0h+phContext.dwLower]
0x18000221f  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180002223  jz      short loc_180002261
0x180002225  mov     r9, [rbp+7E0h+phContext.dwUpper]
0x180002229  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18000222d  jz      short loc_180002261
0x18000222f  mov     rax, [r12+10h]
0x180002234  mov     rcx, [rax+50h]
0x180002238  test    rcx, rcx
0x18000223b  jz      short loc_180002257
0x18000223d  mov     [rsp+8E0h+phNewContext], 0
0x180002246  xor     edx, edx
0x180002248  mov     qword ptr [rsp+8E0h+TargetDataRep], 0
0x180002251  call    cs:__imp_WriteRefTraceLogEx
0x180002257  lea     rcx, [rbp+7E0h+phContext]; phContext
0x18000225b  call    cs:__imp_DeleteSecurityContext
0x180002261  test    rdi, rdi
0x180002264  jz      short loc_1800022BA
0x180002266  or      eax, 0FFFFFFFFh
0x180002269  lock xadd [rdi+4], eax
0x18000226e  cmp     eax, 1
0x180002271  jnz     short loc_1800022BA
0x180002273  test    rdi, rdi
0x180002276  jz      short loc_1800022BA
0x180002278  lea     rcx, [rdi+0C8h]; phCredential
0x18000227f  mov     dword ptr [rdi], 53434366h
0x180002285  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180002289  jz      short loc_18000229B
0x18000228b  cmp     qword ptr [rdi+0D0h], 0FFFFFFFFFFFFFFFFh
0x180002293  jz      short loc_18000229B
0x180002295  call    cs:__imp_FreeCredentialsHandle
0x18000229b  lea     rcx, [rdi+90h]
0x1800022a2  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x1800022a8  lea     rcx, [rdi+8]
0x1800022ac  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800022b2  mov     rcx, rdi; Block
0x1800022b5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800022ba  cmp     [rsp+8E0h+var_87C], 0
0x1800022bf  jz      short loc_1800022C7
0x1800022c1  call    cs:__imp_SeciFreeCallContext
0x1800022c7  lea     rcx, [rbp+7E0h+var_770]
0x1800022cb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800022d1  lea     rcx, [rbp+7E0h+var_738]
0x1800022d8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800022de  lea     rcx, [rbp+7E0h+var_700]
0x1800022e5  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800022eb  lea     rcx, [rbp+7E0h+var_6C8]
0x1800022f2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800022f8  lea     rcx, [rbp+7E0h+var_690]
0x1800022ff  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002305  lea     rcx, [rbp+7E0h+var_7F0]
0x180002309  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000230f  lea     rcx, [rbp+7E0h+var_658]
0x180002316  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000231c  mov     eax, ebx
0x18000231e  mov     rcx, [rbp+7E0h+var_40]
0x180002325  xor     rcx, rsp; StackCookie
0x180002328  call    __security_check_cookie
0x18000232d  mov     rbx, [rsp+8E0h+arg_18]
0x180002335  add     rsp, 8B0h
0x18000233c  pop     r15
0x18000233e  pop     r14
0x180002340  pop     r13
0x180002342  pop     r12
0x180002344  pop     rdi
0x180002345  pop     rsi
0x180002346  pop     rbp
0x180002347  retn
0x180002348  mov     rdi, [rsp+8E0h+Block]
0x18000234d  lea     rcx, [rbp+7E0h+var_7F0]
0x180002351  mov     edx, [rdi+0D8h]
0x180002357  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000235d  test    al, al
0x18000235f  jnz     short loc_18000236B
0x180002361  mov     ebx, 80070008h
0x180002366  jmp     loc_1800020A9
0x18000236b  xor     edx, edx; Val
  ... truncated ...
```
