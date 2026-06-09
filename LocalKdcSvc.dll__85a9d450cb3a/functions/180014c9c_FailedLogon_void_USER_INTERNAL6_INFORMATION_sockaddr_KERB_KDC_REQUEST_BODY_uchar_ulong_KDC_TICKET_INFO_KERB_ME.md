# FailedLogon(void *,_USER_INTERNAL6_INFORMATION *,sockaddr *,KERB_KDC_REQUEST_BODY *,uchar *,ulong,_KDC_TICKET_INFO *,_KERB_MESSAGE_BUFFER *,_KERB_MESSAGE_BUFFER *,_UNICODE_STRING *,long,long,uchar,ulong,_PDC_RSO *)

- ea: `0x180014c9c`
- end: `0x180015ac4`
- name: `?FailedLogon@@YAXPEAXPEAU_USER_INTERNAL6_INFORMATION@@PEAUsockaddr@@PEAUKERB_KDC_REQUEST_BODY@@PEAEKPEAU_KDC_TICKET_INFO@@PEAU_KERB_MESSAGE_BUFFER@@6PEAU_UNICODE_STRING@@JJEKPEAU_PDC_RSO@@@Z`
- size: `3624`
- prototype: `void __fastcall(void *, struct _USER_INTERNAL6_INFORMATION *, struct sockaddr_storage *, struct KERB_KDC_REQUEST_BODY *, unsigned __int8 *, unsigned int, struct _KDC_TICKET_INFO *, void **, struct _KERB_MESSAGE_BUFFER *, struct _UNICODE_STRING *, unsigned int, int, char, unsigned int, struct _PDC_RSO *)`
- caller_count: `2`
- callee_count: `23`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016148`
- `0x1800280ac`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x1800101c4`
- `0x1800101ec`
- `0x18001022c`
- `0x180013f64`
- `0x1800141b8`
- `0x180014314`
- `0x180014c9c`
- `0x18001c944`
- `0x18001cb70`
- `0x18001db14`
- `0x18001ff94`
- `0x18002013c`
- `0x180037b28`
- `0x180037b90`
- `0x18005a090`
- `0x18007d4b0`
- `0x18007dc20`
- `0x18007f5c4`
- `0x18007fa48`
- `0x1800833e0`
- `0x180083990`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014e6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014e6a`
- `logoncli!DsGetDcNameW` at `0x180015229`
- `logoncli!DsGetDcNameW` at `0x180015278`
- `logoncli!DsGetDcNameW` at `0x180015229`
- `logoncli!DsGetDcNameW` at `0x180015278`
- `ntdll!RtlInitUnicodeString` at `0x1800152ca`
- `ntdll!RtlInitUnicodeString` at `0x1800152ca`
- `SAMSRV!SamIRandomizeStoredPassword` at `0x180014d85`
- `SAMSRV!SamIRandomizeStoredPassword` at `0x180014d85`
- `SAMSRV!SamIQueryServerRole` at `0x180014e3f`
- `SAMSRV!SamIQueryServerRole` at `0x180014e3f`
- `SAMSRV!SamIResetBadPwdCountOnPdc` at `0x18001586e`
- `SAMSRV!SamIResetBadPwdCountOnPdc` at `0x18001586e`
- `SAMSRV!SamIReplicateAccountData` at `0x180015310`
- `SAMSRV!SamIReplicateAccountData` at `0x180015310`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x180015516`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x1800157de`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x180015a2b`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x180015516`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x1800157de`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x180015a2b`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x180015440`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x180015702`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x180015955`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x180015440`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x180015702`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x180015955`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall FailedLogon(
        void *a1,
        struct _USER_INTERNAL6_INFORMATION *a2,
        struct sockaddr_storage *a3,
        struct KERB_KDC_REQUEST_BODY *a4,
        unsigned __int8 *a5,
        unsigned int a6,
        struct _KDC_TICKET_INFO *a7,
        void **a8,
        struct _KERB_MESSAGE_BUFFER *a9,
        struct _UNICODE_STRING *a10,
        unsigned int a11,
        int a12,
        char a13,
        unsigned int a14,
        struct _PDC_RSO *a15)
{
  void *v17; // r12
  int v18; // eax
  unsigned int v19; // r15d
  CSecurityData *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rdx
  int v23; // ebx
  __int64 v24; // rdx
  void *v25; // r9
  unsigned __int8 v26; // bl
  CSecurityData *v27; // rcx
  struct KERB_PRINCIPAL_NAME *v28; // rsi
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rdx
  int v32; // ebx
  CSecurityData *v33; // rcx
  struct _KDC_TICKET_INFO *v34; // r14
  DWORD DcNameW; // eax
  int v36; // r8d
  int v37; // eax
  unsigned __int8 v38; // si
  int v39; // ebx
  int v40; // eax
  struct sockaddr_storage *v41; // rax
  struct sockaddr v42; // xmm1
  struct sockaddr v43; // xmm0
  struct sockaddr v44; // xmm1
  struct sockaddr v45; // xmm0
  struct sockaddr v46; // xmm1
  struct sockaddr v47; // xmm0
  struct sockaddr v48; // xmm1
  int v49; // eax
  __int64 v50; // rdx
  CSecurityData *v51; // rcx
  int v52; // eax
  struct sockaddr v53; // xmm1
  struct sockaddr v54; // xmm0
  struct sockaddr v55; // xmm1
  struct sockaddr v56; // xmm0
  struct sockaddr v57; // xmm1
  struct sockaddr v58; // xmm0
  struct sockaddr v59; // xmm1
  int v60; // eax
  CSecurityData *v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // r9
  int v64; // eax
  int v65; // ebx
  int v66; // eax
  struct sockaddr v67; // xmm1
  struct sockaddr v68; // xmm0
  struct sockaddr v69; // xmm1
  struct sockaddr v70; // xmm0
  struct sockaddr v71; // xmm1
  struct sockaddr v72; // xmm0
  struct sockaddr v73; // xmm1
  int v74; // eax
  unsigned int Flags; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v76[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v77; // [rsp+58h] [rbp-A8h]
  struct _UNICODE_STRING *v78; // [rsp+60h] [rbp-A0h]
  int v79; // [rsp+68h] [rbp-98h] BYREF
  void *v80; // [rsp+70h] [rbp-90h]
  struct KERB_ERROR *v81; // [rsp+78h] [rbp-88h] BYREF
  void **v82; // [rsp+80h] [rbp-80h] BYREF
  struct KERB_KDC_REPLY *v83; // [rsp+88h] [rbp-78h] BYREF
  struct KERB_EXT_ERROR *v84; // [rsp+90h] [rbp-70h] BYREF
  struct KERB_KDC_REQUEST_BODY *v85; // [rsp+98h] [rbp-68h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp-60h] BYREF
  struct _USER_INTERNAL6_INFORMATION *v87; // [rsp+A8h] [rbp-58h]
  __int128 v88; // [rsp+B0h] [rbp-50h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v90; // [rsp+D0h] [rbp-30h] BYREF
  __m256i v91; // [rsp+E0h] [rbp-20h]
  __int128 v92; // [rsp+100h] [rbp+0h]
  __int128 v93; // [rsp+110h] [rbp+10h]
  struct sockaddr v94; // [rsp+120h] [rbp+20h]
  struct sockaddr v95; // [rsp+130h] [rbp+30h]
  struct sockaddr v96; // [rsp+140h] [rbp+40h]
  struct sockaddr v97; // [rsp+150h] [rbp+50h]
  struct sockaddr v98; // [rsp+160h] [rbp+60h]
  struct sockaddr v99; // [rsp+170h] [rbp+70h]
  struct sockaddr v100; // [rsp+180h] [rbp+80h]
  __int128 v101; // [rsp+190h] [rbp+90h] BYREF
  __m256i v102; // [rsp+1A0h] [rbp+A0h]
  __int128 v103; // [rsp+1C0h] [rbp+C0h]
  __int128 v104; // [rsp+1D0h] [rbp+D0h]
  struct sockaddr v105; // [rsp+1E0h] [rbp+E0h]
  struct sockaddr v106; // [rsp+1F0h] [rbp+F0h]
  struct sockaddr v107; // [rsp+200h] [rbp+100h]
  struct sockaddr v108; // [rsp+210h] [rbp+110h]
  struct sockaddr v109; // [rsp+220h] [rbp+120h]
  struct sockaddr v110; // [rsp+230h] [rbp+130h]
  struct sockaddr v111; // [rsp+240h] [rbp+140h]

  v78 = a10;
  v87 = a2;
  v77 = a1;
  v80 = a5;
  v85 = a4;
  v82 = a8;
  memset_0(&v101, 0, 0xC0u);
  SystemTimeAsFileTime = 0;
  DestinationString = 0;
  v81 = 0;
  v83 = 0;
  v84 = 0;
  v76[0] = 0;
  v79 = 0;
  if ( !*(_BYTE *)a15 && (*((_DWORD *)a2 + 70) & 0x1000) != 0 && (a12 == -1073741711 || a12 == -1073741276) )
  {
    v17 = v77;
    v18 = SamIRandomizeStoredPassword(v77);
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
          (unsigned int)v18);
      v19 = a11;
      goto LABEL_141;
    }
    *(_BYTE *)a15 = 1;
    *((_BYTE *)a15 + 1) = *((_DWORD *)a7 + 25) != 0;
    *((_BYTE *)a15 + 2) = a13;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v21 = a11;
      v22 = 22;
LABEL_13:
      WPP_SF_Dd(*((_QWORD *)v20 + 2), v22, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v21, a12);
      return;
    }
    return;
  }
  if ( (int)SamIQueryServerRole(GlobalAccountDomainHandle, &v79) >= 0 && (v23 = 0, v79 == 3)
    || (GetSystemTimeAsFileTime(&SystemTimeAsFileTime), !*(_BYTE *)a15)
    && (v23 = 0,
        (unsigned int)CAuthenticatorList::Check(
                        ReplayDetect,
                        a8[1],
                        *(_DWORD *)a8,
                        v25,
                        Flags,
                        (union _LARGE_INTEGER *)&SystemTimeAsFileTime,
                        1u,
                        0,
                        1u)) )
  {
    v19 = a11;
    goto LABEL_17;
  }
  v19 = a11;
  if ( a11 == 24 )
    goto LABEL_25;
  if ( a11 != -2147483642 )
  {
    if ( a12 != -1073741711 && a12 != -1073741276 )
    {
      v23 = 0;
      if ( a12 != -1073741260 )
        goto LABEL_17;
    }
LABEL_25:
    if ( (int)AsNegCacheCheck(v80, v24, v78->Buffer, v78->Length, v76) < 0 || v76[0] == 1 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, a11, a12);
      goto LABEL_140;
    }
    v26 = 0;
    goto LABEL_28;
  }
  v26 = 1;
LABEL_28:
  v76[0] = v26;
  v27 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, 67306222);
    v27 = WPP_GLOBAL_Control;
  }
  if ( KdcGlobalCDC && v26 )
  {
    LODWORD(v82) = 0;
    v28 = (struct KERB_KDC_REQUEST_BODY *)((char *)v85 + 24);
    v88 = 0;
    if ( (unsigned int)KerbConvertPrincipalNameToString(&v88, &v82, (char *)v85 + 24) )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      {
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, &v88);
      }
      KerbFreeString(&v88);
    }
    v29 = KdcForwardMessage(2, 0, 0, a8, a9);
    goto LABEL_59;
  }
  if ( *(_BYTE *)a15 )
    goto LABEL_133;
  if ( KdcGlobalAvoidPdcOnWan )
    goto LABEL_50;
  if ( a14 )
    goto LABEL_79;
  if ( !KdcGlobalDomainFastLevel && !KdcGlobalDomainClaimsLevel )
  {
LABEL_50:
    if ( v27 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 4) != 0 )
    {
      v30 = 27;
LABEL_53:
      WPP_SF_(*((_QWORD *)v27 + 2), v30, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
      v27 = WPP_GLOBAL_Control;
      goto LABEL_54;
    }
    goto LABEL_54;
  }
  if ( (unsigned int)KdcIsWin8FunctionalLevel() )
  {
    v27 = WPP_GLOBAL_Control;
    goto LABEL_50;
  }
LABEL_79:
  if ( !DsGetDcNameW(0, GlobalDomainName.Buffer, 0, 0, a14 | 0x40200280, (PDOMAIN_CONTROLLER_INFOW *)a15 + 1) )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v30 = 28;
      goto LABEL_53;
    }
LABEL_54:
    if ( !*(_BYTE *)a15 )
    {
      if ( v27 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)v27 + 2), 33, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
      v29 = KdcForwardMessage(1, 0, 0, v82, a9);
      v28 = (struct KERB_KDC_REQUEST_BODY *)((char *)v85 + 24);
LABEL_59:
      v23 = 0;
      if ( !v29 )
      {
        if ( !(unsigned int)KerbUnpackData(*((_QWORD *)a9 + 1), *(unsigned int *)a9, 6, &v81) )
        {
          v32 = -1073741595;
          if ( (*(_BYTE *)v81 & 4) != 0
            && !(unsigned int)KerbUnpackErrorData(v81, &v84)
            && v84
            && (*((_BYTE *)v84 + 8) & 1) != 0
            && *(int *)v84 < 0 )
          {
            v32 = *(_DWORD *)v84;
            v33 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            {
LABEL_70:
              v34 = a7;
              v19 = *((_DWORD *)v81 + 13);
              if ( !v76[0] )
              {
                if ( !*((_DWORD *)a7 + 25) )
                  goto LABEL_77;
                if ( v33 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 4) != 0 )
                  WPP_SF_(*((_QWORD *)v33 + 2), 35, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
                if ( v32 == -1073741260 || a13 )
LABEL_77:
                  AsNegCacheUpdate(v80, v31, v78->Buffer, v78->Length, v32);
              }
              v17 = v77;
              v23 = 1;
              goto LABEL_143;
            }
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              34,
              WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
              67306401,
              *(_DWORD *)v84);
          }
          v33 = WPP_GLOBAL_Control;
          goto LABEL_70;
        }
        if ( (unsigned int)KerbUnpackData(*((_QWORD *)a9 + 1), *(unsigned int *)a9, 73, &v83)
          || !KdcGlobalCDC && !KdcVerifyKdcAsRep(v83, v28) )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, 67306516);
          }
          v17 = v77;
          v19 = 0;
          v23 = 1;
          goto LABEL_142;
        }
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, 67306463);
        }
        v19 = 0;
        memset_0(&v101, 0, 0xC0u);
        v38 = v76[0];
        v39 = ((v76[0] ^ 1) + 1) << 19;
        if ( (unsigned int)KdcIsLHFunctionalLevel()
          && ((unsigned int)LsaIIsLastInteractiveLogonInfoEnabled() || KdcGlobalEmitLILI) )
        {
          v34 = a7;
          if ( (*((_DWORD *)a7 + 11) & 0x1C0) == 0 )
          {
            v40 = 84148224;
LABEL_110:
            LODWORD(v101) = v39 | v40;
            if ( !a3 || a3->ss_family == 2 || a3->ss_family == 23 )
            {
              DWORD2(v103) = 1;
              v41 = a3;
              if ( !a3 )
                v41 = &GlobalLocalhostAddress;
              v42 = *(struct sockaddr *)v41->__ss_pad2;
              v104 = *(_OWORD *)&v41->ss_family;
              v43 = *(struct sockaddr *)&v41->__ss_pad2[16];
              v105 = v42;
              v44 = *(struct sockaddr *)&v41->__ss_pad2[32];
              v106 = v43;
              v45 = *(struct sockaddr *)&v41->__ss_pad2[48];
              v107 = v44;
              v46 = *(struct sockaddr *)&v41->__ss_pad2[64];
              v108 = v45;
              v47 = *(struct sockaddr *)&v41->__ss_pad2[80];
              v109 = v46;
              v48 = *(struct sockaddr *)&v41->__ss_pad2[96];
              v110 = v47;
              v111 = v48;
            }
            v17 = v77;
            v49 = SamIUpdateLogonStatistics(v77, &v101);
            if ( v49 < 0 )
            {
              v51 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control )
              {
LABEL_124:
                if ( !v38 )
                {
                  AsNegCacheDelete(v80, v50, v78->Buffer, v78->Length);
                  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      39,
                      WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
                      67306509);
                  }
                }
                v23 = 1;
LABEL_143:
                KerbFreeData(6, v81);
                KerbFreeData(73, v83);
                MIDL_user_free(v84);
                if ( v19 == 24 )
                {
                  if ( *(_BYTE *)a15 && !a13 )
                    KdcIncreaseBadPwdCountOnPdc(v85);
                  memset_0(&v101, 0, 0xC0u);
                  if ( !(unsigned int)KdcIsLHFunctionalLevel()
                    || !(unsigned int)LsaIIsLastInteractiveLogonInfoEnabled() && !KdcGlobalEmitLILI
                    || (v52 = 335806464, (*((_DWORD *)v34 + 11) & 0x1C0) != 0) )
                  {
                    v52 = 335544320;
                  }
                  LODWORD(v101) = v52;
                  if ( !a13 )
                    LODWORD(v101) = v52 | 0x8000000;
                  *(struct _UNICODE_STRING *)&v102.m256i_u64[1] = *v78;
                  if ( !a3 || a3->ss_family == 2 || a3->ss_family == 23 )
                  {
                    DWORD2(v103) = 1;
                    if ( !a3 )
                      a3 = &GlobalLocalhostAddress;
                    v53 = *(struct sockaddr *)a3->__ss_pad2;
                    v104 = *(_OWORD *)&a3->ss_family;
                    v54 = *(struct sockaddr *)&a3->__ss_pad2[16];
                    v105 = v53;
                    v55 = *(struct sockaddr *)&a3->__ss_pad2[32];
                    v106 = v54;
                    v56 = *(struct sockaddr *)&a3->__ss_pad2[48];
                    v107 = v55;
                    v57 = *(struct sockaddr *)&a3->__ss_pad2[64];
                    v108 = v56;
                    v58 = *(struct sockaddr *)&a3->__ss_pad2[80];
                    v109 = v57;
                    v59 = *(struct sockaddr *)&a3->__ss_pad2[96];
                    v110 = v58;
                    v111 = v59;
                  }
                  v60 = SamIUpdateLogonStatistics(v17, &v101);
                  if ( v60 >= 0 )
                    goto LABEL_164;
                  v61 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_165;
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      41,
                      WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
                      (unsigned int)v60);
LABEL_164:
                    v61 = WPP_GLOBAL_Control;
LABEL_165:
                    if ( v61 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v61 + 28) & 4) == 0 )
                      goto LABEL_195;
                    v62 = 42;
                    v63 = 67306581;
                    goto LABEL_194;
                  }
LABEL_195:
                  *(_BYTE *)a15 = 0;
                  return;
                }
                if ( v19 != 23 )
                  goto LABEL_195;
                if ( *(_BYTE *)a15 )
                {
                  if ( *((_WORD *)v87 + 152) )
                  {
                    v64 = SamIResetBadPwdCountOnPdc(v17);
                    if ( v64 < 0
                      && WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        43,
                        WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
                        (unsigned int)v64);
                    }
                  }
                }
                memset_0(&v90, 0, 0xC0u);
                v101 = v90;
                v65 = v23 << 20;
                v102 = v91;
                v103 = v92;
                v104 = v93;
                v105 = v94;
                v106 = v95;
                v107 = v96;
                v108 = v97;
                v109 = v98;
                v110 = v99;
                v111 = v100;
                if ( !(unsigned int)KdcIsLHFunctionalLevel()
                  || !(unsigned int)LsaIIsLastInteractiveLogonInfoEnabled() && !KdcGlobalEmitLILI
                  || (v66 = 67371012, (*((_DWORD *)a7 + 11) & 0x1C0) != 0) )
                {
                  v66 = 67108868;
                }
                LODWORD(v101) = v66 | v65;
                *(struct _UNICODE_STRING *)&v102.m256i_u64[1] = *v78;
                if ( !a3 || a3->ss_family == 2 || a3->ss_family == 23 )
                {
                  DWORD2(v103) = 1;
                  if ( !a3 )
                    a3 = &GlobalLocalhostAddress;
                  v67 = *(struct sockaddr *)a3->__ss_pad2;
                  v104 = *(_OWORD *)&a3->ss_family;
                  v68 = *(struct sockaddr *)&a3->__ss_pad2[16];
                  v105 = v67;
                  v69 = *(struct sockaddr *)&a3->__ss_pad2[32];
                  v106 = v68;
                  v70 = *(struct sockaddr *)&a3->__ss_pad2[48];
                  v107 = v69;
                  v71 = *(struct sockaddr *)&a3->__ss_pad2[64];
                  v108 = v70;
                  v72 = *(struct sockaddr *)&a3->__ss_pad2[80];
                  v109 = v71;
                  v73 = *(struct sockaddr *)&a3->__ss_pad2[96];
                  v110 = v72;
                  v111 = v73;
                }
                v74 = SamIUpdateLogonStatistics(v17, &v101);
                if ( v74 < 0 )
                {
                  v61 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control )
                    goto LABEL_195;
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  {
LABEL_191:
                    if ( v61 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v61 + 28) & 4) == 0 )
                      goto LABEL_195;
                    v62 = 45;
                    v63 = 67306627;
LABEL_194:
                    WPP_SF_Dd(*((_QWORD *)v61 + 2), v62, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v63, v101);
                    goto LABEL_195;
                  }
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    44,
                    WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
                    (unsigned int)v74);
                }
                v61 = WPP_GLOBAL_Control;
                goto LABEL_191;
              }
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
LABEL_121:
                if ( v51 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v51 + 28) & 4) != 0 )
                  WPP_SF_Dd(*((_QWORD *)v51 + 2), 38, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, 67306494, v101);
                goto LABEL_124;
              }
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                37,
                WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
                (unsigned int)v49);
            }
            v51 = WPP_GLOBAL_Control;
            goto LABEL_121;
          }
        }
        else
        {
          v34 = a7;
        }
        v40 = 83886080;
        goto LABEL_110;
      }
LABEL_17:
      v17 = v77;
LABEL_142:
      v34 = a7;
      goto LABEL_143;
    }
LABEL_133:
    if ( !*((_BYTE *)a15 + 1) || a12 == -1073741260 || *((_BYTE *)a15 + 2) )
      AsNegCacheUpdate(v80, v24, v78->Buffer, v78->Length, a12);
LABEL_140:
    v17 = v77;
LABEL_141:
    v23 = 0;
    goto LABEL_142;
  }
  DcNameW = DsGetDcNameW(0, GlobalDomainName.Buffer, 0, 0, 0x40000280u, (PDOMAIN_CONTROLLER_INFOW *)a15 + 1);
  if ( DcNameW )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_ZDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        v36,
        (unsigned int)&GlobalDomainName,
        DcNameW);
    goto LABEL_140;
  }
  RtlInitUnicodeString(&DestinationString, (PCWSTR)(**((_QWORD **)a15 + 1) + 4LL));
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
  v17 = v77;
  v37 = SamIReplicateAccountData(v77, &DestinationString, 2);
  if ( v37 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
        (unsigned int)v37,
        60);
    goto LABEL_141;
  }
  *(_BYTE *)a15 = 1;
  *((_BYTE *)a15 + 1) = *((_DWORD *)a7 + 25) != 0;
  *((_BYTE *)a15 + 2) = a13;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v22 = 32;
    v21 = a11;
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x180014c9c  mov     [rsp-8+arg_8], rbx
0x180014ca1  push    rbp
0x180014ca2  push    rsi
0x180014ca3  push    rdi
0x180014ca4  push    r12
0x180014ca6  push    r13
0x180014ca8  push    r14
0x180014caa  push    r15
0x180014cac  lea     rbp, [rsp-160h]
0x180014cb4  sub     rsp, 260h
0x180014cbb  mov     rax, cs:__security_cookie
0x180014cc2  xor     rax, rsp
0x180014cc5  mov     [rbp+190h+var_40], rax
0x180014ccc  mov     rax, [rbp+190h+arg_48]
0x180014cd3  mov     rdi, r8
0x180014cd6  mov     r14, [rbp+190h+arg_38]
0x180014cdd  mov     rbx, rdx
0x180014ce0  mov     r13, [rbp+190h+arg_70]
0x180014ce7  mov     r8d, 0C0h; Size
0x180014ced  mov     r12, [rbp+190h+arg_40]
0x180014cf4  mov     [rsp+290h+var_230], rax
0x180014cf9  mov     rax, [rbp+190h+arg_20]
0x180014d00  mov     [rbp+190h+var_1E8], rdx
0x180014d04  xor     edx, edx; Val
0x180014d06  mov     [rsp+290h+var_238], rcx
0x180014d0b  lea     rcx, [rbp+190h+var_100]; void *
0x180014d12  mov     [rsp+290h+var_220], rax
0x180014d17  mov     [rbp+190h+var_1F8], r9
0x180014d1b  mov     [rbp+190h+var_210], r14
0x180014d1f  call    memset_0
0x180014d24  mov     esi, [rbp+190h+arg_58]
0x180014d2a  xor     r15d, r15d
0x180014d2d  xorps   xmm0, xmm0
0x180014d30  mov     qword ptr [rbp+190h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180014d34  movups  xmmword ptr [rbp+190h+DestinationString.Length], xmm0
0x180014d38  mov     [rsp+290h+var_218], r15
0x180014d3d  mov     [rbp+190h+var_208], r15
0x180014d41  mov     [rbp+190h+var_200], r15
0x180014d45  mov     [rsp+290h+var_240], r15b
0x180014d4a  mov     [rsp+290h+var_228], r15d
0x180014d4f  cmp     [r13+0], r15b
0x180014d53  jnz     loc_180014E33
0x180014d59  test    dword ptr [rbx+118h], 1000h
0x180014d63  jz      loc_180014E33
0x180014d69  cmp     esi, 0C0000071h
0x180014d6f  jz      short loc_180014D7D
0x180014d71  cmp     esi, 0C0000224h
0x180014d77  jnz     loc_180014E33
0x180014d7d  mov     r12, [rsp+290h+var_238]
0x180014d82  mov     rcx, r12
0x180014d85  call    cs:__imp_SamIRandomizeStoredPassword
0x180014d8b  test    eax, eax
0x180014d8d  jns     short loc_180014DCC
0x180014d8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d96  lea     rdx, WPP_GLOBAL_Control
0x180014d9d  cmp     rcx, rdx
0x180014da0  jz      short loc_180014DC0
0x180014da2  test    byte ptr [rcx+1Ch], 1
0x180014da6  jz      short loc_180014DC0
0x180014da8  mov     rcx, [rcx+10h]
0x180014dac  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x180014db3  mov     edx, 15h
0x180014db8  mov     r9d, eax
0x180014dbb  call    WPP_SF_d
0x180014dc0  mov     r15d, [rbp+190h+arg_50]
0x180014dc7  jmp     loc_180015691
0x180014dcc  mov     r14, [rbp+190h+arg_30]
0x180014dd3  mov     byte ptr [r13+0], 1
0x180014dd8  cmp     [r14+64h], r15d
0x180014ddc  setnz   al
0x180014ddf  mov     [r13+1], al
0x180014de3  mov     al, [rbp+190h+arg_60]
0x180014de9  mov     [r13+2], al
0x180014ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180014df4  lea     rax, WPP_GLOBAL_Control
0x180014dfb  cmp     rcx, rax
0x180014dfe  jz      loc_180015A9A
0x180014e04  test    byte ptr [rcx+1Ch], 80h
0x180014e08  jz      loc_180015A9A
0x180014e0e  mov     r9d, [rbp+190h+arg_50]
0x180014e15  mov     edx, 16h
0x180014e1a  mov     rcx, [rcx+10h]
0x180014e1e  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x180014e25  mov     [rsp+290h+Flags], esi
0x180014e29  call    WPP_SF_Dd
0x180014e2e  jmp     loc_180015A9A
0x180014e33  mov     rcx, cs:?GlobalAccountDomainHandle@@3PEAXEA; void * GlobalAccountDomainHandle
0x180014e3a  lea     rdx, [rsp+290h+var_228]
0x180014e3f  call    cs:__imp_SamIQueryServerRole
0x180014e45  test    eax, eax
0x180014e47  js      short loc_180014E66
0x180014e49  cmp     [rsp+290h+var_228], 3
0x180014e4e  mov     ebx, r15d
0x180014e51  jnz     short loc_180014E66
0x180014e53  mov     r15d, [rbp+190h+arg_50]
0x180014e5a  mov     r12, [rsp+290h+var_238]
0x180014e5f  xor     esi, esi
0x180014e61  jmp     loc_180015695
0x180014e66  lea     rcx, [rbp+190h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014e6a  call    cs:__imp_GetSystemTimeAsFileTime
0x180014e70  cmp     [r13+0], r15b
0x180014e74  jnz     short loc_180014EA8
0x180014e76  mov     r8d, [r14]; unsigned int
0x180014e79  lea     rax, [rbp+190h+SystemTimeAsFileTime]
0x180014e7d  mov     rdx, [r14+8]; void *
0x180014e81  mov     ebx, r15d
0x180014e84  mov     rcx, cs:?ReplayDetect@@3PEAVCAuthenticatorList@@EA; Table
0x180014e8b  mov     [rsp+290h+var_250], 1; unsigned __int8
0x180014e90  mov     [rsp+290h+var_258], r15b; unsigned __int8
0x180014e95  mov     [rsp+290h+var_260], 1; unsigned __int8
0x180014e9a  mov     [rsp+290h+DomainControllerInfo], rax; union _LARGE_INTEGER *
0x180014e9f  call    ?Check@CAuthenticatorList@@QEAAJPEAXK0KPEAT_LARGE_INTEGER@@EEE@Z; CAuthenticatorList::Check(void *,ulong,void *,ulong,_LARGE_INTEGER *,uchar,uchar,uchar)
0x180014ea4  test    eax, eax
0x180014ea6  jnz     short loc_180014E53
0x180014ea8  mov     r15d, [rbp+190h+arg_50]
0x180014eaf  cmp     r15d, 18h
0x180014eb3  jz      short loc_180014EE0
0x180014eb5  cmp     r15d, 80000006h
0x180014ebc  jz      loc_180014FD4
0x180014ec2  cmp     esi, 0C0000071h
0x180014ec8  jz      short loc_180014EE0
0x180014eca  cmp     esi, 0C0000224h
0x180014ed0  jz      short loc_180014EE0
0x180014ed2  xor     ebx, ebx
0x180014ed4  cmp     esi, 0C0000234h
0x180014eda  jnz     loc_180014E5A
0x180014ee0  mov     rax, [rsp+290h+var_230]
0x180014ee5  lea     rcx, [rsp+290h+var_240]
0x180014eea  mov     qword ptr [rsp+290h+Flags], rcx; unsigned __int8 *
0x180014eef  mov     rcx, [rsp+290h+var_220]; void *
0x180014ef4  movzx   r9d, word ptr [rax]; unsigned int
0x180014ef8  mov     r8, [rax+8]; void *
0x180014efc  call    ?AsNegCacheCheck@@YAJPEAXK0KPEAE@Z; AsNegCacheCheck(void *,ulong,void *,ulong,uchar *)
0x180014f01  test    eax, eax
0x180014f03  js      loc_180015657
0x180014f09  cmp     [rsp+290h+var_240], 1
0x180014f0e  jz      loc_180015657
0x180014f14  xor     bl, bl
0x180014f16  mov     [rsp+290h+var_240], bl
0x180014f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f21  lea     rax, WPP_GLOBAL_Control
0x180014f28  cmp     rcx, rax
0x180014f2b  jz      short loc_180014F55
0x180014f2d  test    byte ptr [rcx+1Ch], 4
0x180014f31  jz      short loc_180014F55
0x180014f33  mov     rcx, [rcx+10h]
0x180014f37  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x180014f3e  mov     edx, 18h
0x180014f43  mov     r9d, 40302EEh
0x180014f49  call    WPP_SF_d
0x180014f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f55  cmp     cs:?KdcGlobalCDC@@3HA, 0; int KdcGlobalCDC
0x180014f5c  jz      loc_18001502D
0x180014f62  test    bl, bl
0x180014f64  jz      loc_18001502D
0x180014f6a  mov     rsi, [rbp+190h+var_1F8]
0x180014f6e  lea     rdx, [rbp+190h+var_210]
0x180014f72  xorps   xmm0, xmm0
0x180014f75  mov     dword ptr [rbp+190h+var_210], 0
0x180014f7c  add     rsi, 18h
0x180014f80  lea     rcx, [rbp+190h+var_1E0]
0x180014f84  mov     r8, rsi
0x180014f87  movups  [rbp+190h+var_1E0], xmm0
0x180014f8b  call    KerbConvertPrincipalNameToString
0x180014f90  test    eax, eax
0x180014f92  jnz     short loc_180014FDB
0x180014f94  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f9b  lea     rax, WPP_GLOBAL_Control
0x180014fa2  cmp     rcx, rax
0x180014fa5  jz      short loc_180014FC9
0x180014fa7  test    dword ptr [rcx+1Ch], 40000h
0x180014fae  jz      short loc_180014FC9
0x180014fb0  mov     rcx, [rcx+10h]
0x180014fb4  lea     r9, [rbp+190h+var_1E0]
0x180014fb8  mov     edx, 19h
0x180014fbd  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x180014fc4  call    WPP_SF_Z
0x180014fc9  lea     rcx, [rbp+190h+var_1E0]
0x180014fcd  call    KerbFreeString
0x180014fd2  jmp     short loc_18001500C
0x180014fd4  mov     bl, 1
0x180014fd6  jmp     loc_180014F16
0x180014fdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fe2  lea     rax, WPP_GLOBAL_Control
0x180014fe9  cmp     rcx, rax
0x180014fec  jz      short loc_18001500C
0x180014fee  test    dword ptr [rcx+1Ch], 40000h
0x180014ff5  jz      short loc_18001500C
0x180014ff7  mov     rcx, [rcx+10h]
0x180014ffb  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x180015002  mov     edx, 1Ah
0x180015007  call    WPP_SF_
0x18001500c  xor     edx, edx
0x18001500e  mov     qword ptr [rsp+290h+Flags], r12
0x180015013  mov     r9, r14
0x180015016  xor     r8d, r8d
0x180015019  lea     ecx, [rdx+2]
0x18001501c  call    ?KdcForwardMessage@@YAJW4_KERB_KDC_TYPE@@EKPEAU_KERB_MESSAGE_BUFFER@@1@Z; KdcForwardMessage(_KERB_KDC_TYPE,uchar,ulong,_KERB_MESSAGE_BUFFER *,_KERB_MESSAGE_BUFFER *)
0x180015021  lea     r14, WPP_GLOBAL_Control
0x180015028  jmp     loc_1800150EE
0x18001502d  cmp     byte ptr [r13+0], 0
0x180015032  jnz     loc_180015624
0x180015038  cmp     cs:?KdcGlobalAvoidPdcOnWan@@3HA, 0; int KdcGlobalAvoidPdcOnWan
0x18001503f  jnz     short loc_180015077
0x180015041  mov     r14d, [rbp+190h+arg_68]
0x180015048  test    r14d, r14d
0x18001504b  jnz     loc_180015205
0x180015051  cmp     cs:?KdcGlobalDomainFastLevel@@3KA, 1; ulong KdcGlobalDomainFastLevel
0x180015058  jnb     short loc_180015063
0x18001505a  cmp     cs:?KdcGlobalDomainClaimsLevel@@3KA, 1; ulong KdcGlobalDomainClaimsLevel
0x180015061  jb      short loc_180015077
0x180015063  call    ?KdcIsWin8FunctionalLevel@@YAHXZ; KdcIsWin8FunctionalLevel(void)
0x180015068  test    eax, eax
0x18001506a  jz      loc_180015205
0x180015070  mov     rcx, cs:WPP_GLOBAL_Control
0x180015077  lea     r14, WPP_GLOBAL_Control
0x18001507e  cmp     rcx, r14
0x180015081  jz      short loc_1800150A5
0x180015083  test    byte ptr [rcx+1Ch], 4
0x180015087  jz      short loc_1800150A5
0x180015089  mov     edx, 1Bh
0x18001508e  mov     rcx, [rcx+10h]
0x180015092  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x180015099  call    WPP_SF_
0x18001509e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150a5  cmp     byte ptr [r13+0], 0
0x1800150aa  jnz     loc_180015624
0x1800150b0  cmp     rcx, r14
0x1800150b3  jz      short loc_1800150D0
0x1800150b5  test    byte ptr [rcx+1Ch], 4
0x1800150b9  jz      short loc_1800150D0
0x1800150bb  mov     rcx, [rcx+10h]
0x1800150bf  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x1800150c6  mov     edx, 21h ; '!'
0x1800150cb  call    WPP_SF_
0x1800150d0  mov     r9, [rbp+190h+var_210]
0x1800150d4  xor     edx, edx
0x1800150d6  xor     r8d, r8d
0x1800150d9  mov     qword ptr [rsp+290h+Flags], r12
0x1800150de  lea     ecx, [rdx+1]
0x1800150e1  call    ?KdcForwardMessage@@YAJW4_KERB_KDC_TYPE@@EKPEAU_KERB_MESSAGE_BUFFER@@1@Z; KdcForwardMessage(_KERB_KDC_TYPE,uchar,ulong,_KERB_MESSAGE_BUFFER *,_KERB_MESSAGE_BUFFER *)
0x1800150e6  mov     rsi, [rbp+190h+var_1F8]
0x1800150ea  add     rsi, 18h
0x1800150ee  xor     ebx, ebx
0x1800150f0  test    eax, eax
0x1800150f2  jnz     loc_180014E5A
0x1800150f8  mov     edx, [r12]
0x1800150fc  lea     r9, [rsp+290h+var_218]
0x180015101  mov     rcx, [r12+8]
0x180015106  lea     r8d, [rbx+6]
0x18001510a  call    KerbUnpackData
0x18001510f  test    eax, eax
0x180015111  jnz     loc_1800153A2
0x180015117  mov     rcx, [rsp+290h+var_218]; struct KERB_ERROR *
0x18001511c  mov     ebx, 0C00000E5h
0x180015121  test    byte ptr [rcx], 4
0x180015124  jz      short loc_18001517F
0x180015126  lea     rdx, [rbp+190h+var_200]; struct KERB_EXT_ERROR **
0x18001512a  call    ?KerbUnpackErrorData@@YAJPEAUKERB_ERROR@@PEAPEAUKERB_EXT_ERROR@@@Z; KerbUnpackErrorData(KERB_ERROR *,KERB_EXT_ERROR * *)
0x18001512f  test    eax, eax
0x180015131  jnz     short loc_18001517F
0x180015133  mov     rax, [rbp+190h+var_200]
0x180015137  test    rax, rax
0x18001513a  jz      short loc_18001517F
0x18001513c  test    byte ptr [rax+8], 1
0x180015140  jz      short loc_18001517F
0x180015142  mov     r8d, [rax]
0x180015145  test    r8d, r8d
0x180015148  jns     short loc_18001517F
0x18001514a  mov     ebx, r8d
0x18001514d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015154  cmp     rcx, r14
0x180015157  jz      short loc_180015186
0x180015159  test    byte ptr [rcx+1Ch], 4
0x18001515d  jz      short loc_180015186
0x18001515f  mov     rcx, [rcx+10h]
0x180015163  mov     edx, 22h ; '"'
0x180015168  mov     [rsp+290h+Flags], r8d
0x18001516d  mov     r9d, 40303A1h
0x180015173  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x18001517a  call    WPP_SF_Dd
0x18001517f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015186  mov     rax, [rsp+290h+var_218]
0x18001518b  xor     esi, esi
0x18001518d  mov     r14, [rbp+190h+arg_30]
0x180015194  mov     r15d, [rax+34h]
0x180015198  cmp     [rsp+290h+var_240], sil
0x18001519d  jnz     short loc_1800151F6
0x18001519f  cmp     [r14+64h], esi
0x1800151a3  jz      short loc_1800151DB
0x1800151a5  lea     rax, WPP_GLOBAL_Control
0x1800151ac  cmp     rcx, rax
0x1800151af  jz      short loc_1800151CA
0x1800151b1  test    byte ptr [rcx+1Ch], 4
0x1800151b5  jz      short loc_1800151CA
0x1800151b7  mov     rcx, [rcx+10h]
0x1800151bb  lea     edx, [rsi+23h]
0x1800151be  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x1800151c5  call    WPP_SF_
0x1800151ca  cmp     ebx, 0C0000234h
  ... truncated ...
```
