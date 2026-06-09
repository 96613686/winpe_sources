# KdcChangePassword

- ea: `0x1800412e0`
- end: `0x18004234a`
- name: `KdcChangePassword`
- size: `4202`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x18000ab40`
- `0x18000bcf8`
- `0x18000e9a4`
- `0x1800101c4`
- `0x1800101ec`
- `0x18001022c`
- `0x18001c944`
- `0x18001ff94`
- `0x18002005c`
- `0x180020380`
- `0x1800407e0`
- `0x180040ebc`
- `0x1800412e0`
- `0x180045b50`
- `0x18004b498`
- `0x18005a090`
- `0x18005c2a4`
- `0x18006349c`
- `0x180064ca0`
- `0x18007c054`
- `0x18007c5ec`
- `0x18007c61c`
- `0x18007d714`
- `0x18007dc20`
- `0x18007e35c`
- `0x18007f5c4`
- `0x18007fa48`
- `0x18007fd60`
- `0x180081bec`
- `0x180081f08`
- `0x180082a74`

## import_xrefs

- `Kerberos!KerbCreateTokenFromTicketForKdc` at `0x180041eee`
- `Kerberos!KerbCreateTokenFromTicketForKdc` at `0x180041eee`
- `ntdll!EtwLogTraceEvent` at `0x180041520`
- `ntdll!EtwLogTraceEvent` at `0x180042245`
- `ntdll!EtwLogTraceEvent` at `0x180041520`
- `ntdll!EtwLogTraceEvent` at `0x180042245`
- `ntdll!NtClose` at `0x1800422e6`
- `ntdll!NtClose` at `0x1800422e6`
- `SAMSRV!SamISetPasswordForeignUser2` at `0x180042052`
- `SAMSRV!SamISetPasswordForeignUser2` at `0x180042052`
- `SAMSRV!SamIChangePasswordForeignUser` at `0x180042027`
- `SAMSRV!SamIChangePasswordForeignUser` at `0x180042027`

## pseudocode

```c
__int64 __fastcall KdcChangePassword(
        __int64 a1,
        struct sockaddr_storage *a2,
        struct sockaddr *a3,
        int *a4,
        struct _KERB_MESSAGE_BUFFER *a5)
{
  KerberosCryptoPolicy *v7; // rbx
  KerberosCryptoPolicy *v8; // rdi
  __int64 v9; // rdx
  unsigned int v10; // esi
  unsigned int v11; // ecx
  unsigned int v12; // r8d
  unsigned __int8 *v13; // r13
  unsigned __int16 v14; // r15
  bool v15; // zf
  int v16; // eax
  unsigned int v17; // r12d
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // r9
  __int64 v23; // r9
  CSecurityData *v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  CSecurityData *v27; // rcx
  __int64 v28; // rdx
  struct _KERB_INTERNAL_NAME *v29; // r15
  char v30; // r15
  int *v31; // rcx
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  int v39; // eax
  unsigned __int16 *v40; // rdx
  struct _STRING *v41; // rcx
  unsigned int v43; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 v44[4]; // [rsp+84h] [rbp-7Ch] BYREF
  __int16 v45; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 v46[4]; // [rsp+8Ch] [rbp-74h] BYREF
  struct KERB_ENCRYPTED_TICKET *v47; // [rsp+90h] [rbp-70h] BYREF
  int v48; // [rsp+98h] [rbp-68h] BYREF
  struct _STRING v49; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-40h] BYREF
  void **v53; // [rsp+C8h] [rbp-38h] BYREF
  struct KERB_AUTHENTICATOR *v54; // [rsp+D0h] [rbp-30h] BYREF
  struct _KERB_INTERNAL_NAME *v55; // [rsp+D8h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING v57; // [rsp+E8h] [rbp-18h] BYREF
  struct _UNICODE_STRING v58; // [rsp+F8h] [rbp-8h] BYREF
  void *v59; // [rsp+108h] [rbp+8h] BYREF
  struct _KERB_MESSAGE_BUFFER *v60; // [rsp+110h] [rbp+10h]
  KerberosCryptoPolicy *v61; // [rsp+118h] [rbp+18h] BYREF
  KerberosCryptoPolicy *v62; // [rsp+120h] [rbp+20h] BYREF
  struct sockaddr *v63; // [rsp+128h] [rbp+28h]
  __int64 v64; // [rsp+130h] [rbp+30h] BYREF
  int v65; // [rsp+138h] [rbp+38h]
  int v66; // [rsp+13Ch] [rbp+3Ch]
  int v67; // [rsp+140h] [rbp+40h]
  int v68; // [rsp+144h] [rbp+44h]
  __int64 v69; // [rsp+148h] [rbp+48h]
  __int128 v70; // [rsp+150h] [rbp+50h] BYREF
  __int128 v71; // [rsp+160h] [rbp+60h] BYREF
  __int128 v72; // [rsp+170h] [rbp+70h] BYREF
  struct _UNICODE_STRING v73; // [rsp+180h] [rbp+80h] BYREF
  __int64 v74; // [rsp+190h] [rbp+90h] BYREF
  __int64 v75; // [rsp+198h] [rbp+98h]
  _BYTE v76[44]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v77; // [rsp+1CCh] [rbp+CCh]
  int v78; // [rsp+1E1h] [rbp+E1h]
  __int16 v79; // [rsp+1E5h] [rbp+E5h]
  char v80; // [rsp+1E7h] [rbp+E7h]
  __int16 v81; // [rsp+1F9h] [rbp+F9h]
  char v82; // [rsp+1FBh] [rbp+FBh]
  int v83; // [rsp+204h] [rbp+104h]
  __int64 v84; // [rsp+228h] [rbp+128h] BYREF
  __int128 v85; // [rsp+230h] [rbp+130h]
  _OWORD v86[2]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v87; // [rsp+260h] [rbp+160h]
  _OWORD v88[2]; // [rsp+268h] [rbp+168h] BYREF
  __int64 v89; // [rsp+288h] [rbp+188h]
  _QWORD v90[2]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v91[44]; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v92; // [rsp+2CCh] [rbp+1CCh]
  int v93; // [rsp+2E1h] [rbp+1E1h]
  __int16 v94; // [rsp+2E5h] [rbp+1E5h]
  char v95; // [rsp+2E7h] [rbp+1E7h]
  __int16 v96; // [rsp+2F9h] [rbp+1F9h]
  char v97; // [rsp+2FBh] [rbp+1FBh]
  int v98; // [rsp+300h] [rbp+200h]
  int v99; // [rsp+304h] [rbp+204h]
  __int64 v100; // [rsp+328h] [rbp+228h] BYREF
  __int128 v101; // [rsp+330h] [rbp+230h]
  __int64 v102; // [rsp+340h] [rbp+240h] BYREF
  int v103; // [rsp+348h] [rbp+248h]
  _DOMAIN_PASSWORD_INFORMATION v104; // [rsp+350h] [rbp+250h] BYREF
  _WORD v105[2]; // [rsp+370h] [rbp+270h] BYREF
  char v106; // [rsp+374h] [rbp+274h]
  __int128 v107; // [rsp+388h] [rbp+288h]
  int v108; // [rsp+39Ch] [rbp+29Ch]
  unsigned int *v109; // [rsp+3A0h] [rbp+2A0h]
  int v110; // [rsp+3A8h] [rbp+2A8h]
  __int64 *v111; // [rsp+3B0h] [rbp+2B0h]
  int v112; // [rsp+3B8h] [rbp+2B8h]
  char *v113; // [rsp+3C0h] [rbp+2C0h]
  int v114; // [rsp+3C8h] [rbp+2C8h]
  unsigned __int16 *v115; // [rsp+3D0h] [rbp+2D0h]
  int v116; // [rsp+3D8h] [rbp+2D8h]
  __int64 v117; // [rsp+3E0h] [rbp+2E0h]
  int v118; // [rsp+3E8h] [rbp+2E8h]
  struct _STRING *v119; // [rsp+3F0h] [rbp+2F0h]
  int v120; // [rsp+3F8h] [rbp+2F8h]
  PCHAR Buffer; // [rsp+400h] [rbp+300h]
  int Length; // [rsp+408h] [rbp+308h]
  int v123; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v124[4]; // [rsp+414h] [rbp+314h] BYREF
  struct sockaddr v125; // [rsp+418h] [rbp+318h]
  __int128 v126; // [rsp+428h] [rbp+328h]
  __int128 v127; // [rsp+438h] [rbp+338h]
  __int128 v128; // [rsp+448h] [rbp+348h]
  __int128 v129; // [rsp+458h] [rbp+358h]
  __int128 v130; // [rsp+468h] [rbp+368h]
  __int128 v131; // [rsp+478h] [rbp+378h]
  __int128 v132; // [rsp+488h] [rbp+388h]

  v60 = a5;
  v63 = a3;
  v103 = 0;
  v89 = 0;
  v87 = 0;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  v99 = 0;
  v43 = 0;
  v102 = 0;
  v54 = 0;
  v47 = 0;
  memset(v88, 0, sizeof(v88));
  v90[0] = 0;
  v90[1] = 0;
  memset(v86, 0, sizeof(v86));
  memset_0(v91, 0, 0x88u);
  v100 = 0;
  v77 = 0;
  v101 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v74 = 0;
  v75 = 0;
  memset_0(v76, 0, 0x88u);
  v84 = 0;
  v85 = 0;
  v53 = 0;
  v51 = 0;
  v44[0] = 0;
  v58 = 0;
  v52 = 0;
  v49 = 0;
  v55 = 0;
  v57 = 0;
  v46[0] = 0;
  v73 = 0;
  Handle = 0;
  v70 = 0;
  v59 = 0;
  v71 = 0;
  v72 = 0;
  memset_0(&v123, 0, 0x88u);
  memset(&v104, 0, sizeof(v104));
  memset_0(v105, 0, 0xA0u);
  KerberosCryptoPolicy::Create((__int64 **)&v62);
  KerberosCryptoPolicy::Create((__int64 **)&v61);
  v7 = v62;
  v8 = v61;
  if ( !v62 || !v61 )
  {
    v10 = 0;
    goto LABEL_146;
  }
  if ( KdcEventTraceFlag )
  {
    v106 = 1;
    v107 = KdcChangePassGuid;
    v108 = 0x20000;
    v105[0] = 48;
    EtwLogTraceEvent(KdcTraceLoggerHandle, v105);
  }
  v10 = EnterApiCall(0);
  if ( (v10 & 0x80000000) == 0 )
  {
    if ( KdcGlobalCDC )
    {
      LOBYTE(v9) = 1;
      v11 = KdcForwardMessage(2, v9, 0, a4, v60);
      v43 = v11;
LABEL_148:
      if ( KdcEventTraceFlag )
      {
        v110 = 4;
        v109 = &v43;
        v111 = &v102;
        v113 = (char *)&v102 + 4;
        v49.Buffer = (PCHAR)&v45;
        v112 = 4;
        v114 = 4;
        v45 = 0;
        *(_QWORD *)&v49.Length = 131074;
        if ( !v57.Buffer || (v40 = (unsigned __int16 *)&v57, !v57.Length) )
          v40 = (unsigned __int16 *)&v49;
        if ( !v75 || (v41 = (struct _STRING *)&v74, !(_WORD)v74) )
          v41 = &v49;
        v117 = *((_QWORD *)v40 + 1);
        v118 = *v40;
        Buffer = v41->Buffer;
        Length = v41->Length;
        v115 = v40;
        v119 = v41;
        v105[0] = 160;
        v116 = 2;
        v120 = 2;
        v107 = KdcChangePassGuid;
        v106 = 2;
        v108 = 1179648;
        EtwLogTraceEvent(KdcTraceLoggerHandle, v105);
        v11 = v43;
      }
      if ( v11 == -2147483645 )
        KdcReportInvalidMessage(0x80000003, (const unsigned __int16 *)v9);
      KerbFreeData(51, v47);
      FreeTicketInfo((struct _KDC_TICKET_INFO *)v90);
      FreeTicketInfo((struct _KDC_TICKET_INFO *)&v74);
      KerbFreeData(57, v53);
      KerbFreeData(4, v51);
      KerbFreeData(29, v52);
      KerbFreeString(&v58);
      KerbFreeData(52, v54);
      KerbFreeSid(&v55);
      KerbFreeString(&v57);
      KerbFreeString(&v73);
      if ( Handle )
        NtClose(Handle);
      LeaveApiCall();
      v10 = v43;
      goto LABEL_161;
    }
    v12 = *a4;
    if ( (unsigned int)*a4 < 7 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, v12);
      if ( (KDCInfoLevel & 0x10000000) == 0 )
        goto LABEL_35;
      HIDWORD(v102) = 67568427;
LABEL_34:
      v103 = 2;
      LODWORD(v102) = -1073741061;
LABEL_35:
      v11 = -2147483645;
      v43 = -2147483645;
      goto LABEL_148;
    }
    v13 = (unsigned __int8 *)*((_QWORD *)a4 + 1);
    v9 = 256;
    v14 = v13[3] + (v13[2] << 8);
    LOWORD(v50) = v14;
    v15 = v14 == 0xFF80;
    if ( v14 != 0xFF80 )
    {
      if ( v14 != 1 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, v14);
        }
        if ( (KDCInfoLevel & 0x10000000) == 0 )
          goto LABEL_35;
        HIDWORD(v102) = 67568452;
        goto LABEL_34;
      }
      v15 = 0;
    }
    v16 = *v13;
    LOBYTE(v45) = v15;
    v17 = (v16 << 8) + v13[1];
    if ( v17 != v12 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, v17, v12);
      if ( (KDCInfoLevel & 0x10000000) == 0 )
        goto LABEL_35;
      HIDWORD(v102) = 67568461;
      goto LABEL_34;
    }
    v9 = v13[4] << 8;
    LOWORD(v9) = v13[5] + (v13[4] << 8);
    v48 = (unsigned __int16)v9;
    if ( (unsigned int)(unsigned __int16)v9 + 6 > v17 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          WPP_72c574dd392638b0f9c59822794ca294_Traceguids,
          (unsigned __int16)v9);
      if ( (KDCInfoLevel & 0x10000000) == 0 )
        goto LABEL_35;
      HIDWORD(v102) = 67568475;
      goto LABEL_34;
    }
    v43 = KdcVerifyKdcRequest(
            v13 + 6,
            (unsigned __int16)v9,
            (struct sockaddr *)a2,
            0xEu,
            0xBu,
            0,
            &v54,
            &v47,
            (struct _KERB_ENCRYPTION_KEY *)v88,
            0,
            (struct _KERB_ENCRYPTION_KEY *)v86,
            (struct _KDC_TICKET_INFO *)v90,
            v44,
            0,
            0,
            (struct KERB_EXT_ERROR *)&v102);
    KerberosCryptoPolicy::SetKey(v7, (struct _KERB_ENCRYPTION_KEY *)v86, 1);
    KerberosCryptoPolicy::SetKey(v8, (struct _KERB_ENCRYPTION_KEY *)v88, 1);
    v11 = v43;
    if ( v43 )
    {
      if ( v43 == -2147483645 )
        goto LABEL_148;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_147:
        KerbFreeString(&v70);
        KerbFreeString(&v71);
        KerbFreeString(&v72);
        MIDL_user_free(v59);
        v11 = KdcBuildKpasswdResponse(v47, v54, v8, v63, &v104, v10, v43, (struct KERB_EXT_ERROR *)&v102, v60);
        v43 = v11;
        goto LABEL_148;
      }
      v18 = v43;
      v19 = 26;
      v20 = *((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_41:
      WPP_SF_d(v20, v19, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, v18);
      goto LABEL_147;
    }
    if ( !v44[0] )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_72c574dd392638b0f9c59822794ca294_Traceguids);
      if ( (KDCInfoLevel & 0x10000000) == 0 )
        goto LABEL_146;
      v102 = 0x407038DC00002FBLL;
      goto LABEL_48;
    }
    if ( (v98 & 0x400) == 0 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, v90);
      if ( (KDCInfoLevel & 0x10000000) != 0 )
      {
        v102 = 0x407039BC00002FBLL;
        v103 = 2;
      }
      v43 = 35;
      goto LABEL_147;
    }
    v21 = KerbUnpackData(&v13[(unsigned __int16)v48 + 6], v17 - v48 - 6, 57, &v53);
    v43 = v21;
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, v21);
      if ( (KDCInfoLevel & 0x10000000) != 0 )
      {
        v102 = 0x40703AEC00002FBLL;
        v103 = 2;
      }
      goto LABEL_147;
    }
    v22 = *(unsigned int *)v53;
    if ( (_DWORD)v22 != 5 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, v22);
      v43 = 39;
      goto LABEL_147;
    }
    v23 = *((unsigned int *)v53 + 1);
    if ( (_DWORD)v23 != 21 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, v23);
      v43 = 40;
      goto LABEL_147;
    }
    v48 = 0;
    v43 = KerberosCryptoPolicy::DecryptNoCopy(
            (__int64)v8,
            (__int64)(v53 + 1),
            13,
            (_DWORD *)v53 + 6,
            v53 + 4,
            (__int64)&v48,
            0);
    v18 = v43;
    if ( v43 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_147;
      v19 = 32;
      goto LABEL_76;
    }
    v43 = KerbUnpackData(v53[4], *((unsigned int *)v53 + 6), 4, &v51);
    v18 = v43;
    if ( v43 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_147;
      v19 = 33;
      goto LABEL_76;
    }
    if ( a2 )
    {
      if ( !KdcDontCheckAddresses )
      {
        v66 = 0;
        v68 = 0;
        v64 = 0;
        v65 = *(_DWORD *)(v51 + 48);
        v69 = *(_QWORD *)(v51 + 64);
        v67 = *(_DWORD *)(v51 + 56);
        if ( !(unsigned __int8)KerbVerifyClientAddress(a2, &v64, v25, v43) )
        {
          v43 = 38;
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_72c574dd392638b0f9c59822794ca294_Traceguids);
          }
          goto LABEL_147;
        }
      }
    }
    if ( (_WORD)v50 == 0xFF80 )
    {
      v43 = KerbUnpackData(*(_QWORD *)(v51 + 16), *(unsigned int *)(v51 + 8), 29, &v52);
      v18 = v43;
      if ( v43 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_147;
        }
        v19 = 35;
LABEL_76:
        v20 = *((_QWORD *)v24 + 2);
        goto LABEL_41;
      }
      v26 = *(unsigned int *)(v52 + 8);
      if ( (unsigned int)v26 > 0x3FFF )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_97;
        }
        v28 = 36;
LABEL_96:
        WPP_SF_d(*((_QWORD *)v27 + 2), v28, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, v26);
LABEL_97:
        v43 = 61;
        goto LABEL_147;
      }
      v49.Length = *(_WORD *)(v52 + 8);
      v49.MaximumLength = v49.Length;
      v49.Buffer = *(PCHAR *)(v52 + 16);
      v43 = KerbStringToUnicodeString(&v58, &v49);
      if ( v43 )
        goto LABEL_147;
      if ( (*(_BYTE *)v52 & 0xC0) != 0xC0 )
      {
        LOBYTE(v45) = 0;
LABEL_104:
        if ( (KerbConvertFlagsToUlong((struct KERB_ENCRYPTED_TICKET *)((char *)v47 + 8)) & 0x400000) == 0 )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_72c574dd392638b0f9c59822794ca294_Traceguids);
          }
          goto LABEL_146;
        }
        if ( !v58.Buffer )
        {
          v26 = *(unsigned int *)(v51 + 8);
          if ( (unsigned int)v26 > 0x3FFF )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_97;
            }
            v28 = 38;
            goto LABEL_96;
          }
          v49.Length = *(_WORD *)(v51 + 8);
          v49.MaximumLength = v49.Length;
          v49.Buffer = *(PCHAR *)(v51 + 16);
          v43 = KerbStringToUnicodeString(&v58, &v49);
          if ( v43 )
            goto LABEL_147;
        }
        v43 = KerbConvertPrincipalNameToKdcName(&v55, (struct KERB_ENCRYPTED_TICKET *)((char *)v47 + 56));
        if ( v43 )
          goto LABEL_147;
        v43 = KerbConvertRealmToUnicodeString(&v57, (char *)v47 + 48);
        if ( v43 )
          goto LABEL_147;
LABEL_116:
        v29 = v55;
        v43 = KdcNormalize(
                v55,
                0,
                &v57,
                0,
                1u,
                0,
                0,
                v46,
                &v73,
                (struct _KDC_TICKET_INFO *)&v74,
                (struct KERB_EXT_ERROR *)&v102,
                0,
                0,
                0,
                0,
                0);
        if ( v43 )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF__KERB_NAME_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              39,
              WPP_72c574dd392638b0f9c59822794ca294_Traceguids,
              v29);
          }
          goto LABEL_147;
        }
        v30 = v45;
        if ( !(_BYTE)v45 )
        {
          v43 = KdcValidatePacUserSid(v47, (const struct _KDC_TICKET_INFO *)&v74);
          if ( v43 )
          {
            v10 = -1073741790;
            goto LABEL_147;
          }
        }
        v50 = 997;
        v10 = KerbCreateTokenFromTicketForKdc(
                &v50,
                0,
                v47,
                v54,
                0,
                v7,
                &DomainName2,
                v8,
                &v50,
                &v59,
                &Handle,
                &v70,
                &v71,
                &v72,
                0,
                0);
        if ( (v10 & 0x80000000) == 0 )
        {
          if ( !a2 || a2->ss_family == 2 || (v31 = 0, a2->ss_family == 23) )
          {
            memset_0(v124, 0, 0x84u);
            v123 = 1;
            if ( !a2 )
              a2 = &GlobalLocalhostAddress;
            v31 = &v123;
            v32 = *(_OWORD *)a2->__ss_pad2;
            v125 = *(struct sockaddr *)&a2->ss_family;
            v33 = *(_OWORD *)&a2->__ss_pad2[16];
            v126 = v32;
            v34 = *(_OWORD *)&a2->__ss_pad2[32];
            v127 = v33;
            v35 = *(_OWORD *)&a2->__ss_pad2[48];
            v128 = v34;
            v36 = *(_OWORD *)&a2->__ss_pad2[64];
            v129 = v35;
            v37 = *(_OWORD *)&a2->__ss_pad2[80];
            v130 = v36;
            v38 = *(_OWORD *)&a2->__ss_pad2[96];
            v131 = v37;
            v132 = v38;
          }
          if ( v30 )
            v39 = SamISetPasswordForeignUser2(v31, 512, &v74, &v58, 0, Handle, &v104);
          else
            v39 = SamIChangePasswordForeignUser(v31, &v74, &v58, Handle, 64, &v104);
          v10 = v39;
          if ( v39 < 0 )
          {
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_Zd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                41,
                (unsigned int)WPP_72c574dd392638b0f9c59822794ca294_Traceguids,
                (unsigned int)&v74,
                v39);
            }
            if ( (KDCInfoLevel & 0x10000000) != 0 )
            {
              v102 = v10 | 0x407052000000000LL;
              v103 = 2;
            }
            v43 = 12;
          }
          goto LABEL_147;
        }
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, v10);
        }
        if ( (KDCInfoLevel & 0x10000000) == 0 )
        {
LABEL_146:
          v43 = 60;
          goto LABEL_147;
        }
        v102 = v10 | 0x40704E800000000LL;
LABEL_48:
        v103 = 2;
        goto LABEL_146;
      }
      v43 = KerbConvertPrincipalNameToKdcName(&v55, (struct KERB_PRINCIPAL_NAME *)(v52 + 24));
      if ( v43 )
        goto LABEL_147;
      v43 = KerbConvertRealmToUnicodeString(&v57, v52 + 40);
      if ( v43 )
        goto LABEL_147;
    }
    if ( v14 == 0xFF80 )
      goto LABEL_116;
    goto LABEL_104;
  }
LABEL_161:
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v61);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v62);
  std::vector<unsigned int>::_Tidy((__int64)&v84);
  std::vector<unsigned int>::_Tidy((__int64)&v100);
  return v10;
}

```

## disassembly

```asm
0x1800412e0  mov     [rsp-8+arg_0], rbx
0x1800412e5  push    rbp
0x1800412e6  push    rsi
0x1800412e7  push    rdi
0x1800412e8  push    r12
0x1800412ea  push    r13
0x1800412ec  push    r14
0x1800412ee  push    r15
0x1800412f0  lea     rbp, [rsp-3B0h]
0x1800412f8  sub     rsp, 4B0h
0x1800412ff  mov     rax, cs:__security_cookie
0x180041306  xor     rax, rsp
0x180041309  mov     [rbp+3E0h+var_40], rax
0x180041310  mov     rax, [rbp+3E0h+arg_20]
0x180041317  lea     rcx, [rbp+3E0h+var_240]; void *
0x18004131e  xor     r12d, r12d
0x180041321  mov     [rbp+3E0h+var_3D0], rax
0x180041325  xor     eax, eax
0x180041327  mov     [rbp+3E0h+var_3B8], r8
0x18004132b  xorps   xmm0, xmm0
0x18004132e  mov     [rbp+3E0h+var_198], eax
0x180041334  xorps   xmm1, xmm1
0x180041337  mov     [rbp+3E0h+var_258], rax
0x18004133e  mov     r14, rdx
0x180041341  mov     [rbp+3E0h+var_280], rax
0x180041348  mov     ebx, 88h
0x18004134d  mov     [rbp+3E0h+var_214], eax
0x180041353  mov     r8d, ebx; Size
0x180041356  mov     [rbp+3E0h+var_1FF], eax
0x18004135c  xor     edx, edx; Val
0x18004135e  mov     [rbp+3E0h+var_1FB], ax
0x180041365  mov     [rbp+3E0h+var_1F9], al
0x18004136b  mov     r13, r9
0x18004136e  mov     [rbp+3E0h+var_1E7], ax
0x180041375  mov     [rbp+3E0h+var_1E5], al
0x18004137b  mov     [rbp+3E0h+var_1DC], eax
0x180041381  mov     [rbp+3E0h+var_460], r12d
0x180041385  mov     [rbp+3E0h+var_1A0], r12
0x18004138c  mov     [rbp+3E0h+var_410], r12
0x180041390  mov     [rbp+3E0h+var_450], r12
0x180041394  movups  [rbp+3E0h+var_278], xmm0
0x18004139b  mov     [rbp+3E0h+var_250], r12
0x1800413a2  movups  [rbp+3E0h+var_268], xmm0
0x1800413a9  mov     [rbp+3E0h+var_248], r12
0x1800413b0  movups  [rbp+3E0h+var_2A0], xmm1
0x1800413b7  movups  [rbp+3E0h+var_290], xmm1
0x1800413be  call    memset_0
0x1800413c3  xor     eax, eax
0x1800413c5  mov     [rbp+3E0h+var_1B8], r12
0x1800413cc  xorps   xmm0, xmm0
0x1800413cf  mov     [rbp+3E0h+var_314], eax
0x1800413d5  mov     r8d, ebx; Size
0x1800413d8  movdqa  [rbp+3E0h+var_1B0], xmm0
0x1800413e0  xor     edx, edx; Val
0x1800413e2  mov     [rbp+3E0h+var_2FF], eax
0x1800413e8  lea     rcx, [rbp+3E0h+var_340]; void *
0x1800413ef  mov     [rbp+3E0h+var_2FB], ax
0x1800413f6  mov     [rbp+3E0h+var_2F9], al
0x1800413fc  mov     [rbp+3E0h+var_2E7], ax
0x180041403  mov     [rbp+3E0h+var_2E5], al
0x180041409  mov     [rbp+3E0h+var_2DC], eax
0x18004140f  mov     [rbp+3E0h+var_350], r12
0x180041416  mov     [rbp+3E0h+var_348], r12
0x18004141d  call    memset_0
0x180041422  xorps   xmm0, xmm0
0x180041425  mov     [rbp+3E0h+var_2B8], r12
0x18004142c  xorps   xmm1, xmm1
0x18004142f  movdqa  [rbp+3E0h+var_2B0], xmm0
0x180041437  mov     r8d, ebx; Size
0x18004143a  mov     [rbp+3E0h+var_418], r12
0x18004143e  xor     edx, edx; Val
0x180041440  mov     [rbp+3E0h+var_428], r12
0x180041444  lea     rcx, [rbp+3E0h+var_D0]; void *
0x18004144b  mov     [rbp+3E0h+var_45C], r12b
0x18004144f  movups  xmmword ptr [rbp+3E0h+var_3E8.Length], xmm1
0x180041453  mov     [rbp+3E0h+var_420], r12
0x180041457  movups  xmmword ptr [rbp+3E0h+var_440.Length], xmm0
0x18004145b  mov     [rbp+3E0h+var_408], r12
0x18004145f  movups  xmmword ptr [rbp+3E0h+var_3F8.Length], xmm0
0x180041463  mov     [rbp+3E0h+var_454], r12b
0x180041467  movups  xmmword ptr [rbp+3E0h+var_360.Length], xmm1
0x18004146e  mov     [rbp+3E0h+Handle], r12
0x180041472  movups  [rbp+3E0h+var_390], xmm0
0x180041476  mov     [rbp+3E0h+var_3D8], r12
0x18004147a  movups  [rbp+3E0h+var_380], xmm1
0x18004147e  movups  [rbp+3E0h+var_370], xmm0
0x180041482  call    memset_0
0x180041487  xor     eax, eax
0x180041489  lea     r8d, [rbx+18h]; Size
0x18004148d  xorps   xmm0, xmm0
0x180041490  mov     qword ptr [rbp+3E0h+var_190.MinPasswordAge], rax
0x180041497  movups  xmmword ptr [rbp+3E0h+var_190.MinPasswordLength], xmm0
0x18004149e  xor     edx, edx; Val
0x1800414a0  lea     rcx, [rbp+3E0h+var_170]; void *
0x1800414a7  call    memset_0
0x1800414ac  lea     rcx, [rbp+3E0h+var_3C0]
0x1800414b0  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x1800414b5  lea     rcx, [rbp+3E0h+var_3C8]
0x1800414b9  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x1800414be  mov     rbx, [rbp+3E0h+var_3C0]
0x1800414c2  mov     rdi, [rbp+3E0h+var_3C8]
0x1800414c6  test    rbx, rbx
0x1800414c9  jz      loc_1800420C2
0x1800414cf  test    rdi, rdi
0x1800414d2  jz      loc_1800420C2
0x1800414d8  cmp     cs:KdcEventTraceFlag, r12d
0x1800414df  lea     r15d, [r12+1]
0x1800414e4  jz      short loc_180041526
0x1800414e6  movups  xmm0, cs:KdcChangePassGuid
0x1800414ed  mov     rcx, cs:KdcTraceLoggerHandle
0x1800414f4  lea     eax, [r12+30h]
0x1800414f9  lea     rdx, [rbp+3E0h+var_170]
0x180041500  mov     [rbp+3E0h+var_16C], r15b
0x180041507  movdqu  [rbp+3E0h+var_158], xmm0
0x18004150f  mov     [rbp+3E0h+var_144], 20000h
0x180041519  mov     [rbp+3E0h+var_170], ax
0x180041520  call    cs:__imp_EtwLogTraceEvent
0x180041526  xor     ecx, ecx
0x180041528  call    ?EnterApiCall@@YAJW4NeededKdcState@@@Z; EnterApiCall(NeededKdcState)
0x18004152d  mov     esi, eax
0x18004152f  test    eax, eax
0x180041531  js      loc_1800422F4
0x180041537  cmp     cs:?KdcGlobalCDC@@3HA, r12d; int KdcGlobalCDC
0x18004153e  jz      short loc_180041567
0x180041540  mov     rcx, [rbp+3E0h+var_3D0]
0x180041544  xor     r8d, r8d
0x180041547  mov     [rsp+4E0h+var_4C0], rcx
0x18004154c  mov     r9, r13
0x18004154f  mov     dl, r15b
0x180041552  lea     edi, [r8+2]
0x180041556  mov     ecx, edi
0x180041558  call    ?KdcForwardMessage@@YAJW4_KERB_KDC_TYPE@@EKPEAU_KERB_MESSAGE_BUFFER@@1@Z; KdcForwardMessage(_KERB_KDC_TYPE,uchar,ulong,_KERB_MESSAGE_BUFFER *,_KERB_MESSAGE_BUFFER *)
0x18004155d  mov     ecx, eax
0x18004155f  mov     [rbp+3E0h+var_460], eax
0x180041562  jmp     loc_18004213A
0x180041567  mov     r8d, [r13+0]
0x18004156b  cmp     r8d, 7
0x18004156f  jnb     short loc_1800415C6
0x180041571  mov     rcx, cs:WPP_GLOBAL_Control
0x180041578  lea     rax, WPP_GLOBAL_Control
0x18004157f  cmp     rcx, rax
0x180041582  jz      short loc_1800415A2
0x180041584  test    [rcx+1Ch], r15b
0x180041588  jz      short loc_1800415A2
0x18004158a  mov     rcx, [rcx+10h]
0x18004158e  mov     r9d, r8d
0x180041591  lea     r8, WPP_72c574dd392638b0f9c59822794ca294_Traceguids
0x180041598  mov     edx, 16h
0x18004159d  call    WPP_SF_d
0x1800415a2  test    cs:?KDCInfoLevel@@3KA, 10000000h; ulong KDCInfoLevel
0x1800415ac  mov     edi, 2
0x1800415b1  jz      loc_180041748
0x1800415b7  mov     dword ptr [rbp+3E0h+var_1A0+4], 407032Bh
0x1800415c1  jmp     loc_180041738
0x1800415c6  mov     r13, [r13+8]
0x1800415ca  mov     edx, 100h
0x1800415cf  mov     r9d, 1
0x1800415d5  movzx   eax, byte ptr [r13+3]
0x1800415da  movzx   r15d, byte ptr [r13+2]
0x1800415df  imul    r15d, edx
0x1800415e3  add     r15w, ax
0x1800415e7  mov     eax, 0FF80h
0x1800415ec  mov     word ptr [rbp+3E0h+var_430], r15w
0x1800415f1  cmp     r15w, ax
0x1800415f5  jz      short loc_180041657
0x1800415f7  cmp     r15w, r9w
0x1800415fb  jz      short loc_180041653
0x1800415fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180041604  lea     rax, WPP_GLOBAL_Control
0x18004160b  cmp     rcx, rax
0x18004160e  jz      short loc_18004162F
0x180041610  test    [rcx+1Ch], r9b
0x180041614  jz      short loc_18004162F
0x180041616  mov     rcx, [rcx+10h]
0x18004161a  lea     r8, WPP_72c574dd392638b0f9c59822794ca294_Traceguids
0x180041621  movzx   r9d, r15w
0x180041625  mov     edx, 17h
0x18004162a  call    WPP_SF_d
0x18004162f  test    cs:?KDCInfoLevel@@3KA, 10000000h; ulong KDCInfoLevel
0x180041639  mov     edi, 2
0x18004163e  jz      loc_180041748
0x180041644  mov     dword ptr [rbp+3E0h+var_1A0+4], 4070344h
0x18004164e  jmp     loc_180041738
0x180041653  cmp     r15w, ax
0x180041657  movzx   eax, byte ptr [r13+0]
0x18004165c  setz    byte ptr [rbp+3E0h+var_458]
0x180041660  movzx   r12d, byte ptr [r13+1]
0x180041665  shl     eax, 8
0x180041668  add     r12d, eax
0x18004166b  cmp     r12d, r8d
0x18004166e  jz      short loc_1800416C7
0x180041670  mov     rcx, cs:WPP_GLOBAL_Control
0x180041677  lea     rax, WPP_GLOBAL_Control
0x18004167e  cmp     rcx, rax
0x180041681  jz      short loc_1800416A6
0x180041683  test    [rcx+1Ch], r9b
0x180041687  jz      short loc_1800416A6
0x180041689  mov     rcx, [rcx+10h]
0x18004168d  mov     edx, 18h
0x180041692  mov     dword ptr [rsp+4E0h+var_4C0], r8d
0x180041697  mov     r9d, r12d
0x18004169a  lea     r8, WPP_72c574dd392638b0f9c59822794ca294_Traceguids
0x1800416a1  call    WPP_SF_Dd
0x1800416a6  test    cs:?KDCInfoLevel@@3KA, 10000000h; ulong KDCInfoLevel
0x1800416b0  mov     edi, 2
0x1800416b5  jz      loc_180041748
0x1800416bb  mov     dword ptr [rbp+3E0h+var_1A0+4], 407034Dh
0x1800416c5  jmp     short loc_180041738
0x1800416c7  movzx   eax, byte ptr [r13+4]
0x1800416cc  mov     ecx, edx
0x1800416ce  mov     edx, eax
0x1800416d0  movzx   eax, byte ptr [r13+5]
0x1800416d5  imul    edx, ecx
0x1800416d8  add     dx, ax
0x1800416db  movzx   r10d, dx
0x1800416df  mov     [rbp+3E0h+var_448], r10d
0x1800416e3  lea     eax, [r10+6]
0x1800416e7  cmp     eax, r12d
0x1800416ea  jbe     short loc_180041755
0x1800416ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800416f3  lea     rax, WPP_GLOBAL_Control
0x1800416fa  cmp     rcx, rax
0x1800416fd  jz      short loc_18004171D
0x1800416ff  test    [rcx+1Ch], r9b
0x180041703  jz      short loc_18004171D
0x180041705  mov     rcx, [rcx+10h]
0x180041709  lea     r8, WPP_72c574dd392638b0f9c59822794ca294_Traceguids
0x180041710  mov     edx, 19h
0x180041715  mov     r9d, r10d
0x180041718  call    WPP_SF_d
0x18004171d  test    cs:?KDCInfoLevel@@3KA, 10000000h; ulong KDCInfoLevel
0x180041727  mov     edi, 2
0x18004172c  jz      short loc_180041748
0x18004172e  mov     dword ptr [rbp+3E0h+var_1A0+4], 407035Bh
0x180041738  mov     [rbp+3E0h+var_198], edi
0x18004173e  mov     dword ptr [rbp+3E0h+var_1A0], 0C00002FBh
0x180041748  mov     ecx, 80000003h
0x18004174d  mov     [rbp+3E0h+var_460], ecx
0x180041750  jmp     loc_18004213A
0x180041755  xor     edx, edx
0x180041757  lea     rax, [rbp+3E0h+var_1A0]
0x18004175e  mov     [rsp+4E0h+var_468], rax; struct KERB_EXT_ERROR *
0x180041763  lea     rcx, [r13+6]; unsigned __int8 *
0x180041767  mov     [rsp+4E0h+var_470], rdx; unsigned __int8 *
0x18004176c  lea     rax, [rbp+3E0h+var_45C]
0x180041770  mov     [rsp+4E0h+var_478], rdx; unsigned __int8 *
0x180041775  mov     r8, r14; struct sockaddr *
0x180041778  mov     [rsp+4E0h+var_480], rax; unsigned __int8 *
0x18004177d  lea     r9d, [rdx+0Eh]; unsigned int
0x180041781  lea     rax, [rbp+3E0h+var_250]
0x180041788  mov     [rsp+4E0h+var_488], rax; struct _KDC_TICKET_INFO *
0x18004178d  lea     rax, [rbp+3E0h+var_2A0]
0x180041794  mov     [rsp+4E0h+var_490], rax; struct _KERB_ENCRYPTION_KEY *
0x180041799  lea     rax, [rbp+3E0h+var_278]
0x1800417a0  mov     [rsp+4E0h+var_498], rdx; struct _KERB_ENCRYPTION_KEY *
0x1800417a5  mov     [rsp+4E0h+var_4A0], rax; struct _KERB_ENCRYPTION_KEY *
0x1800417aa  lea     rax, [rbp+3E0h+var_450]
0x1800417ae  mov     [rsp+4E0h+var_4A8], rax; struct KERB_ENCRYPTED_TICKET **
0x1800417b3  lea     rax, [rbp+3E0h+var_410]
0x1800417b7  mov     [rsp+4E0h+var_4B0], rax; struct KERB_AUTHENTICATOR **
0x1800417bc  mov     [rsp+4E0h+var_4B8], rdx; struct KERB_AP_REQUEST **
0x1800417c1  mov     edx, r10d; unsigned int
0x1800417c4  mov     dword ptr [rsp+4E0h+var_4C0], 0Bh; unsigned int
0x1800417cc  call    ?KdcVerifyKdcRequest@@YAJPEAEKPEAUsockaddr@@KKPEAPEAUKERB_AP_REQUEST@@PEAPEAUKERB_AUTHENTICATOR@@PEAPEAUKERB_ENCRYPTED_TICKET@@PEAU_KERB_ENCRYPTION_KEY@@55PEAU_KDC_TICKET_INFO@@000PEAUKERB_EXT_ERROR@@@Z; KdcVerifyKdcRequest(uchar *,ulong,sockaddr *,ulong,ulong,KERB_AP_REQUEST * *,KERB_AUTHENTICATOR * *,KERB_ENCRYPTED_TICKET * *,_KERB_ENCRYPTION_KEY *,_KERB_ENCRYPTION_KEY *,_KERB_ENCRYPTION_KEY *,_KDC_TICKET_INFO *,uchar *,uchar *,uchar *,KERB_EXT_ERROR *)
0x1800417d1  mov     r8b, 1; bool
0x1800417d4  mov     [rbp+3E0h+var_460], eax
0x1800417d7  lea     rdx, [rbp+3E0h+var_2A0]; struct _KERB_ENCRYPTION_KEY *
0x1800417de  mov     rcx, rbx; this
0x1800417e1  call    ?SetKey@KerberosCryptoPolicy@@QEAAXPEAU_KERB_ENCRYPTION_KEY@@_N@Z; KerberosCryptoPolicy::SetKey(_KERB_ENCRYPTION_KEY *,bool)
0x1800417e6  mov     r8b, 1; bool
0x1800417e9  lea     rdx, [rbp+3E0h+var_278]; struct _KERB_ENCRYPTION_KEY *
0x1800417f0  mov     rcx, rdi; this
0x1800417f3  call    ?SetKey@KerberosCryptoPolicy@@QEAAXPEAU_KERB_ENCRYPTION_KEY@@_N@Z; KerberosCryptoPolicy::SetKey(_KERB_ENCRYPTION_KEY *,bool)
0x1800417f8  mov     ecx, [rbp+3E0h+var_460]
0x1800417fb  test    ecx, ecx
0x1800417fd  jz      short loc_18004184C
0x1800417ff  cmp     ecx, 80000003h
0x180041805  jz      loc_180042135
0x18004180b  mov     r10, cs:WPP_GLOBAL_Control
0x180041812  lea     rax, WPP_GLOBAL_Control
0x180041819  cmp     r10, rax
0x18004181c  jz      loc_1800420CC
0x180041822  mov     ebx, 2
0x180041827  test    [r10+1Ch], bl
0x18004182b  jz      loc_1800420CC
0x180041831  mov     r9d, ecx
0x180041834  lea     edx, [rbx+18h]
0x180041837  mov     rcx, [r10+10h]
0x18004183b  lea     r8, WPP_72c574dd392638b0f9c59822794ca294_Traceguids
0x180041842  call    WPP_SF_d
0x180041847  jmp     loc_1800420CC
0x18004184c  cmp     [rbp+3E0h+var_45C], 0
0x180041850  jnz     short loc_1800418B4
0x180041852  mov     rcx, cs:WPP_GLOBAL_Control
0x180041859  lea     rax, WPP_GLOBAL_Control
0x180041860  cmp     rcx, rax
0x180041863  jz      short loc_180041880
0x180041865  test    byte ptr [rcx+1Ch], 1
0x180041869  jz      short loc_180041880
0x18004186b  mov     rcx, [rcx+10h]
  ... truncated ...
```
