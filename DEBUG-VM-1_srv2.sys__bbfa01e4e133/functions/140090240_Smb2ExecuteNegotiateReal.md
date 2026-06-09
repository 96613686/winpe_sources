# Smb2ExecuteNegotiateReal

- ea: `0x140090240`
- end: `0x140091755`
- name: `Smb2ExecuteNegotiateReal`
- size: `5397`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400901a0`

## callees

- `0x140005070`
- `0x140007400`
- `0x140007900`
- `0x140008190`
- `0x14000a4e4`
- `0x1400154b0`
- `0x140018c60`
- `0x14001a554`
- `0x14001b354`
- `0x14001c768`
- `0x1400222ec`
- `0x1400224b8`
- `0x140022958`
- `0x1400229ac`
- `0x140024314`
- `0x14002484c`
- `0x140024cfc`
- `0x140024dd8`
- `0x140038490`
- `0x140038680`
- `0x140038980`
- `0x1400594f0`
- `0x140060b5c`
- `0x140060c60`
- `0x140060e78`
- `0x140060ee0`
- `0x14008bea8`
- `0x14008bf38`
- `0x14008bfc8`
- `0x14008eb44`
- `0x14008ef4c`
- `0x14008f110`
- `0x140090240`
- `0x140094ce8`
- `0x140095588`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400906dc`
- `ntoskrnl!ExAllocatePool2` at `0x1400906dc`
- `srvnet!SrvNetIsConnectionLoopback` at `0x14009036a`
- `srvnet!SrvNetIsConnectionLoopback` at `0x14009036a`
- `srvnet!SmbCryptoHashCreate` at `0x140090655`
- `srvnet!SmbCryptoHashCreate` at `0x140090655`
- `srvnet!SmbCryptoHashGetOutputLength` at `0x1400906bd`
- `srvnet!SmbCryptoHashGetOutputLength` at `0x1400906bd`
- `srvnet!SmbCryptoUpdatePreauthIntegrityHashValue` at `0x14009075e`
- `srvnet!SmbCryptoUpdatePreauthIntegrityHashValue` at `0x14009075e`
- `srvnet!SrvNetIsConnectionTransportLevelEncrypted` at `0x14009083e`
- `srvnet!SrvNetIsConnectionTransportLevelEncrypted` at `0x14009083e`
- `srvnet!SmbCryptoHashGetRecommendedSaltSize` at `0x140090e56`
- `srvnet!SmbCryptoHashGetRecommendedSaltSize` at `0x140090e56`
- `srvnet!SrvNetIsRdmaConnection` at `0x140091235`
- `srvnet!SrvNetIsRdmaConnection` at `0x140091235`
- `srvnet!SrvNetGetRdmaNicInfo` at `0x14009126c`
- `srvnet!SrvNetGetRdmaNicInfo` at `0x14009126c`
- `ksecdd!FreeContextBuffer` at `0x1400916f7`
- `ksecdd!FreeContextBuffer` at `0x1400916f7`

## pseudocode

```c
__int64 __fastcall Smb2ExecuteNegotiateReal(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  __int64 v4; // r13
  __int64 v6; // rdi
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // edx
  int v14; // r8d
  int v15; // r8d
  __int64 v16; // rdx
  _DWORD *v17; // rbx
  unsigned int *v18; // rbx
  __int64 v19; // r8
  int NegotiateSecurityInfo; // esi
  _QWORD *v21; // r14
  int v22; // eax
  __int64 v23; // rdx
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  unsigned int OutputLength; // eax
  __int64 Pool2; // rax
  PDEVICE_OBJECT v27; // rcx
  int updated; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  char v31; // si
  __int64 v32; // rbx
  int v33; // r8d
  int v34; // ebx
  __int64 v35; // rdx
  unsigned __int16 v36; // r14
  unsigned int v37; // edx
  int v38; // r8d
  int v39; // ecx
  int v40; // ebx
  ULONG v41; // r8d
  int v42; // edx
  int v43; // eax
  int v44; // edx
  unsigned int v45; // edx
  unsigned int v46; // r8d
  unsigned __int16 v47; // ax
  unsigned int v48; // edx
  int v49; // eax
  __int64 v50; // rdx
  PDEVICE_OBJECT v51; // rcx
  __int64 v52; // rdx
  unsigned int v53; // r13d
  unsigned int v54; // r14d
  int v55; // r13d
  int v56; // r10d
  unsigned int v57; // eax
  unsigned int v58; // edx
  NTSTATUS v59; // ecx
  unsigned int v60; // eax
  unsigned int v61; // ebx
  unsigned __int16 RecommendedSaltSize; // ax
  int v63; // ecx
  unsigned int v64; // edx
  unsigned int v65; // edx
  unsigned int v66; // ecx
  unsigned int v67; // r8d
  unsigned int v68; // eax
  unsigned int v69; // ecx
  unsigned int v70; // edx
  bool v71; // cf
  int v72; // eax
  __int64 v73; // r9
  unsigned int v74; // edx
  unsigned int v75; // ecx
  unsigned int v76; // r8d
  int v77; // eax
  ULONG v78; // r8d
  ULONG v79; // ecx
  unsigned int v80; // edx
  int v81; // eax
  unsigned int v82; // edx
  unsigned int v83; // ecx
  unsigned int v84; // r8d
  int v85; // eax
  ULONG v86; // r8d
  ULONG v87; // ecx
  unsigned int v88; // edx
  int v89; // eax
  unsigned int v90; // edx
  unsigned int v91; // ecx
  unsigned int v92; // r8d
  unsigned int v93; // eax
  unsigned int v94; // ecx
  unsigned int v95; // edx
  int v96; // eax
  unsigned int v97; // eax
  unsigned int v98; // ecx
  __int64 v99; // rsi
  char IsRdmaConnection; // bl
  __int64 v101; // r8
  int RdmaNicInfo; // eax
  int v103; // r8d
  __int64 v104; // rax
  __int64 v105; // rcx
  int v107; // [rsp+20h] [rbp-E0h]
  int v108; // [rsp+20h] [rbp-E0h]
  int v109; // [rsp+28h] [rbp-D8h]
  char v110; // [rsp+50h] [rbp-B0h]
  char v111; // [rsp+51h] [rbp-AFh]
  char v112; // [rsp+52h] [rbp-AEh]
  char v113; // [rsp+53h] [rbp-ADh]
  char v114; // [rsp+54h] [rbp-ACh]
  ULONG pulResult; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v116; // [rsp+5Ch] [rbp-A4h] BYREF
  char v117; // [rsp+60h] [rbp-A0h] BYREF
  char v118; // [rsp+61h] [rbp-9Fh] BYREF
  char v119; // [rsp+62h] [rbp-9Eh] BYREF
  bool v120; // [rsp+63h] [rbp-9Dh] BYREF
  char v121; // [rsp+64h] [rbp-9Ch] BYREF
  size_t Size; // [rsp+68h] [rbp-98h] BYREF
  int v123; // [rsp+70h] [rbp-90h] BYREF
  __int64 v124; // [rsp+78h] [rbp-88h] BYREF
  int v125; // [rsp+80h] [rbp-80h]
  int v126; // [rsp+84h] [rbp-7Ch]
  int *v127; // [rsp+88h] [rbp-78h] BYREF
  int v128; // [rsp+90h] [rbp-70h] BYREF
  __int64 v129; // [rsp+94h] [rbp-6Ch] BYREF
  void *Src; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v131; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v132; // [rsp+B0h] [rbp-50h] BYREF
  int v133; // [rsp+B8h] [rbp-48h]
  struct _EVENT_DATA_DESCRIPTOR v134; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v135; // [rsp+E0h] [rbp-20h]
  __int64 v136; // [rsp+E8h] [rbp-18h]
  int *v137; // [rsp+F0h] [rbp-10h]
  __int64 v138; // [rsp+F8h] [rbp-8h]
  char *v139; // [rsp+100h] [rbp+0h]
  __int64 v140; // [rsp+108h] [rbp+8h]
  char *v141; // [rsp+110h] [rbp+10h]
  __int64 v142; // [rsp+118h] [rbp+18h]
  char *v143; // [rsp+120h] [rbp+20h]
  __int64 v144; // [rsp+128h] [rbp+28h]
  bool *v145; // [rsp+130h] [rbp+30h]
  __int64 v146; // [rsp+138h] [rbp+38h]
  char *v147; // [rsp+140h] [rbp+40h]
  __int64 v148; // [rsp+148h] [rbp+48h]
  int *v149; // [rsp+150h] [rbp+50h]
  __int64 v150; // [rsp+158h] [rbp+58h]
  __int64 *v151; // [rsp+160h] [rbp+60h]
  __int64 v152; // [rsp+168h] [rbp+68h]
  char *v153; // [rsp+170h] [rbp+70h]
  __int64 v154; // [rsp+178h] [rbp+78h]
  __int64 *v155; // [rsp+180h] [rbp+80h]
  __int64 v156; // [rsp+188h] [rbp+88h]
  size_t *p_Size; // [rsp+190h] [rbp+90h]
  __int64 v158; // [rsp+198h] [rbp+98h]

  v3 = a1[12];
  v4 = a1[70];
  v124 = v4;
  v126 = 0;
  v6 = *(_QWORD *)(v3 + 496);
  Src = 0;
  Size = 0;
  v123 = 0;
  v125 = 0;
  v116 = 0;
  v7 = *(unsigned __int16 *)(v4 + 262);
  *(_WORD *)(v6 + 44) = v7;
  pulResult = 0;
  v110 = 0;
  v111 = 0;
  v113 = 0;
  v114 = 0;
  v112 = 0;
  v8 = v7 - 514;
  if ( !v8 || (v9 = v8 - 14) == 0 )
  {
    *(_DWORD *)(v6 + 32) = 0;
    goto LABEL_13;
  }
  v10 = v9 - 240;
  if ( !v10 )
  {
    *(_DWORD *)(v6 + 32) = 1;
LABEL_13:
    *(_BYTE *)(v6 + 48) = 0;
    *(_DWORD *)(v6 + 40) = 1;
    goto LABEL_14;
  }
  v11 = v10 - 2;
  if ( !v11 )
  {
    *(_DWORD *)(v6 + 32) = 2;
    *(_DWORD *)(v6 + 40) = 3;
    *(_BYTE *)(v6 + 48) = 1;
LABEL_14:
    *(_WORD *)(v6 + 46) = 0;
    goto LABEL_15;
  }
  v12 = v11 - 15;
  if ( !v12 )
  {
    *(_DWORD *)(v6 + 40) = 3;
    goto LABEL_8;
  }
  if ( v12 == 1 )
  {
    *(_DWORD *)(v6 + 40) = 7;
LABEL_8:
    *(_DWORD *)(v6 + 32) = 3;
    *(_BYTE *)(v6 + 48) = 3;
    *(_WORD *)(v6 + 46) = 7;
  }
LABEL_15:
  *(_WORD *)(v6 + 116) = 1;
  if ( (unsigned __int8)Srv2IsSigningRequiredForInstance(a1[8], a2, a3)
    || Smb2SigningRequiredForLoopback
    && (unsigned __int8)SrvNetIsConnectionLoopback(*(_QWORD *)(*(_QWORD *)(v6 + 56) + 480LL)) )
  {
    *(_WORD *)(v6 + 116) |= 2u;
    *(_BYTE *)(v6 + 49) |= 1u;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Dl(
      WPP_GLOBAL_Control->AttachedDevice,
      25,
      *(_BYTE *)(v6 + 49) & 1,
      *(unsigned __int8 *)a1[8],
      *(_BYTE *)(v6 + 49) & 1);
  }
  if ( *(_WORD *)(v6 + 44) < 0x300u && AuditClientDoesNotSupportEncryption && (byte_14004C33B & 8) != 0 )
    McTemplateK0hzr0tq_EtwWriteTransfer(
      a1[12],
      v13,
      v14,
      *(_WORD *)(a1[12] + 360LL) >> 1,
      *(_QWORD *)(a1[12] + 368LL),
      Smb2EncryptionEnabled,
      2);
  v15 = *(unsigned __int16 *)(v6 + 44);
  *(_DWORD *)(v6 + 140) = (unsigned __int16)v15 >= 0x300u;
  *(_DWORD *)(v6 + 108) |= 1u;
  v16 = *(unsigned int *)(v6 + 108);
  if ( (unsigned __int16)v15 >= 0x210u )
  {
    if ( Smb2LeasingEnabled )
    {
      v16 = (unsigned int)v16 | 2;
      *(_DWORD *)(v6 + 108) = v16;
    }
    if ( !*(_BYTE *)(*(_QWORD *)(a1[12] + 488LL) + 289LL) )
    {
      v16 = (unsigned int)v16 | 4;
      *(_BYTE *)(v6 + 49) |= 2u;
      *(_DWORD *)(v6 + 108) = v16;
    }
    if ( (unsigned __int16)v15 >= 0x300u )
    {
      v17 = (_DWORD *)(v4 + 248);
      if ( Smb2IsRkfInstalled && (*v17 & 0x10) != 0 )
      {
        *(_BYTE *)(v6 + 49) |= 4u;
        v16 = (unsigned int)v16 | 0x10;
        *(_DWORD *)(v6 + 108) = v16;
      }
      if ( Smb2MultiChannelEnabled && (*v17 & 8) != 0 )
      {
        v16 = (unsigned int)v16 | 8;
        *(_DWORD *)(v6 + 108) = v16;
      }
      if ( Smb2DirLeasingEnabled && (*v17 & 0x20) != 0 )
      {
        v16 = (unsigned int)v16 | 0x20;
        *(_DWORD *)(v6 + 108) = v16;
      }
      if ( Smb2EncryptionEnabled )
      {
        if ( (*v17 & 0x40) != 0 && (unsigned __int16)v15 < 0x311u )
        {
          Smb2SelectCommonCipherForConnection(a1, v16);
          if ( (*(_BYTE *)(v6 + 49) & 8) != 0 )
            *(_DWORD *)(v6 + 108) |= 0x40u;
        }
      }
      if ( (*v17 & 0x40) == 0
        && *(_WORD *)(v6 + 44) < 0x311u
        && AuditClientDoesNotSupportEncryption
        && (byte_14004C33B & 8) != 0 )
      {
        McTemplateK0hzr0tq_EtwWriteTransfer(
          a1[12],
          v16,
          v15,
          *(_WORD *)(a1[12] + 360LL) >> 1,
          *(_QWORD *)(a1[12] + 368LL),
          Smb2EncryptionEnabled,
          0);
      }
      if ( Smb2NotificationsEnabled && (*v17 & 0x80u) != 0 )
      {
        *(_BYTE *)(v6 + 49) |= 0x40u;
        *(_DWORD *)(v6 + 108) |= 0x80u;
      }
    }
  }
  if ( *(_WORD *)(v6 + 44) >= 0x311u )
  {
    v18 = (unsigned int *)(v6 + 132);
    if ( (int)Smb2SelectPreauthIntegrityHashAlgorithm(*(_QWORD *)(v4 + 208), *(unsigned __int16 *)(v4 + 252), v6 + 132) < 0 )
    {
      NegotiateSecurityInfo = -1067646976;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 26, &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids, a1);
      }
      goto LABEL_326;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 27, &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids, a1, *v18);
    }
    v21 = (_QWORD *)(v4 + 200);
    LOBYTE(v19) = 1;
    NegotiateSecurityInfo = SmbCryptoHashCreate(v4 + 200, *v18, v19);
    if ( NegotiateSecurityInfo < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_326;
      }
      v22 = *v18;
      v23 = 28;
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v109 = NegotiateSecurityInfo;
LABEL_70:
      WPP_SF_qDD(AttachedDevice, v23, &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids, a1, v22, v109);
      goto LABEL_326;
    }
    OutputLength = SmbCryptoHashGetOutputLength(*v21);
    *(_DWORD *)(v6 + 128) = OutputLength;
    Pool2 = ExAllocatePool2(256, OutputLength, 1664242508);
    *(_QWORD *)(v6 + 120) = Pool2;
    if ( !Pool2 )
    {
      NegotiateSecurityInfo = -1073741670;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_326;
      }
      v23 = 29;
      v109 = *(_DWORD *)(v6 + 128);
LABEL_76:
      v22 = *v18;
LABEL_77:
      AttachedDevice = v27->AttachedDevice;
      goto LABEL_70;
    }
    updated = SmbCryptoUpdatePreauthIntegrityHashValue(
                *v21,
                Pool2,
                *(unsigned int *)(v6 + 128),
                *(_QWORD *)(a1[38] + 24LL),
                *(_DWORD *)(a1[38] + 36LL));
    NegotiateSecurityInfo = updated;
    if ( updated < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_326;
      }
      v23 = 30;
      v109 = updated;
      goto LABEL_76;
    }
    v31 = 16;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_DDq(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        v30,
        **(unsigned int **)(v6 + 120),
        *(_DWORD *)(a1[38] + 36LL),
        v6);
    }
    if ( Smb2EncryptionEnabled )
    {
      if ( *(_WORD *)(v4 + 254) )
      {
        Smb2SelectCommonCipherForConnection(a1, v29);
        v110 = 1;
        if ( Smb2DisableSmbEncryptDataOnSecureConnection )
        {
          if ( *(_BYTE *)(v4 + 268) )
          {
            v126 = 1;
            v32 = *(_QWORD *)(v6 + 56);
            *(_BYTE *)(v32 + 511) = SrvNetIsConnectionTransportLevelEncrypted(*(_QWORD *)(v32 + 480));
            v114 = 1;
          }
        }
      }
    }
    if ( !*(_WORD *)(v4 + 254) && AuditClientDoesNotSupportEncryption && (byte_14004C33B & 8) != 0 )
      McTemplateK0hzr0tq_EtwWriteTransfer(
        a1[12],
        v29,
        v30,
        *(_WORD *)(a1[12] + 360LL) >> 1,
        *(_QWORD *)(a1[12] + 368LL),
        Smb2EncryptionEnabled,
        1);
    if ( *(_WORD *)(v4 + 258) )
    {
      v33 = Smb2SelectSigningAlgorithm(*(_QWORD *)(v4 + 224), *(unsigned __int16 *)(v4 + 258), &v123);
      if ( v33 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            33,
            &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids,
            a1,
            v33,
            -1067646973);
        }
      }
      else
      {
        v34 = v123;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 32, &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids, a1, v123);
        }
        *(_DWORD *)(v6 + 140) = v34;
      }
      v111 = 1;
    }
    v35 = *(unsigned __int16 *)(v4 + 256);
    if ( (_WORD)v35 )
    {
      Smb2SelectRdmaTransforms(*(_QWORD *)(v4 + 232), v35, &v127, &v116);
      v36 = v116;
      v125 = v116;
      if ( v116 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 34, &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids, a1, v116);
        }
        if ( (unsigned int)v36 - 1 > 1 )
          __int2c();
        v37 = 0;
        if ( v36 )
        {
          v38 = *(_DWORD *)(v6 + 156);
          do
          {
            v39 = *((unsigned __int16 *)&v127 + 2 * v37);
            if ( (v38 & v39) == 0 )
            {
              v38 |= 1 << (v39 - 1);
              *(_DWORD *)(v6 + 156) = v38;
            }
            ++v37;
          }
          while ( v37 < v36 );
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 35, &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids, a1);
      }
      v112 = 1;
    }
    if ( !Smb2CompressionDisabled && *(_WORD *)(v4 + 260) )
    {
      if ( (int)Smb2SelectCompressionAlgorithms(
                  *(_QWORD *)(v4 + 240),
                  *(unsigned __int16 *)(v4 + 260),
                  (char *)&Size + 4,
                  &pulResult) < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 37, &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids, a1);
        }
      }
      else
      {
        v40 = HIDWORD(Size);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            36,
            &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids,
            a1,
            HIDWORD(Size));
        }
        v41 = pulResult;
        *(_DWORD *)(v6 + 144) = v40;
        v42 = 1 << (v40 - 1);
        *(_DWORD *)(v6 + 148) = v41;
        v43 = *(_DWORD *)(v6 + 152);
        if ( (v43 & v42) == 0 )
        {
          v43 |= v42;
          *(_DWORD *)(v6 + 152) = v43;
        }
        v44 = 1 << (v41 - 1);
        if ( (v44 & v43) == 0 )
          *(_DWORD *)(v6 + 152) = v43 | v44;
        if ( !v40 && !v41 )
          v31 = 0;
        *(_BYTE *)(v6 + 49) = v31 | *(_BYTE *)(v6 + 49) & 0xEF;
      }
      v113 = 1;
      *(_BYTE *)(v6 + 49) ^= (*(_BYTE *)(v6 + 49) ^ (32 * *(_BYTE *)(v4 + 267))) & 0x20;
    }
  }
  v45 = *(_DWORD *)(v6 + 108);
  v46 = v45 & 0xFFFFFFEF;
  LOBYTE(v116) = *(_BYTE *)(v4 + 269);
  if ( !*(_BYTE *)a1[8] )
    v46 = v45;
  *(_DWORD *)(v6 + 108) = v46;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 38, &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids, a1, v46);
  }
  v47 = *(_WORD *)(v6 + 44);
  v48 = *(_DWORD *)(*(_QWORD *)(a1[12] + 488LL) + 292LL);
  *(_DWORD *)(v6 + 36) = v48;
  if ( v47 >= 0x210u )
  {
    if ( v47 >= 0x311u )
      goto LABEL_164;
  }
  else
  {
    v49 = 0x10000;
    if ( v48 < 0x10000 )
      v49 = v48;
    *(_DWORD *)(v6 + 36) = v49;
  }
  if ( !*(_BYTE *)(v4 + 266) )
  {
    *(_DWORD *)(v6 + 132) = 1;
    NegotiateSecurityInfo = Smb2ComputeValidateNegotiateInfoHash(
                              1u,
                              *(_DWORD *)(*(_QWORD *)(v4 + 192) + 8LL),
                              *(_QWORD *)(v4 + 192) + 12LL,
                              *(_WORD *)(*(_QWORD *)(v4 + 192) + 4LL),
                              *(_QWORD *)(v4 + 192) + 36LL,
                              *(_WORD *)(*(_QWORD *)(v4 + 192) + 2LL),
                              (_QWORD *)(v6 + 120),
                              (_DWORD *)(v6 + 128),
                              0x6332534Cu);
    if ( NegotiateSecurityInfo < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_326;
      }
      v22 = *(_DWORD *)(v6 + 132);
      v23 = 39;
      v109 = NegotiateSecurityInfo;
      goto LABEL_77;
    }
  }
LABEL_164:
  Srv2SetResponseBufferToReceiveBuffer(a1);
  LOBYTE(v107) = 1;
  LOBYTE(v50) = 7;
  SRV2_PERF_ENTER_EX(a1 + 73, v50, 1556, "Smb2ExecuteNegotiateReal", v107);
  LOBYTE(v108) = 1;
  NegotiateSecurityInfo = Smb2GetNegotiateSecurityInfo(&Src, &Size);
  SRV2_PERF_ENTER_EX(a1 + 73, 0, 1562, "Smb2ExecuteNegotiateReal", v108);
  if ( NegotiateSecurityInfo < 0 )
  {
    v51 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_326;
    }
    v52 = 40;
    goto LABEL_315;
  }
  v53 = Size;
  if ( (unsigned int)Size > 0xFFFF )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 41, &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids, a1, Size);
    }
LABEL_174:
    NegotiateSecurityInfo = -1073741595;
    goto LABEL_326;
  }
  HIDWORD(Size) = 0;
  v54 = Size + 128;
  if ( (unsigned int)(Size + 128) < 0x81 )
    v54 = 129;
  if ( *(_WORD *)(v6 + 44) >= 0x311u )
  {
    v55 = -1;
    v56 = -8;
    if ( (v54 & 7) != 0 )
    {
      if ( v54 + 7 < v54 )
      {
        v59 = -1073741675;
        goto LABEL_192;
      }
      v54 = (v54 + 7) & 0xFFFFFFF8;
    }
    v57 = v54 + 8;
    v58 = -1;
    if ( v54 + 8 >= v54 )
      v58 = v54 + 8;
    v59 = v57 < v54 ? 0xC0000095 : 0;
    if ( v57 < v54 )
    {
      v54 = v58;
    }
    else
    {
      v60 = v58 + 6;
      v54 = -1;
      if ( v58 + 6 >= v58 )
        v54 = v58 + 6;
      v59 = v60 < v58 ? 0xC0000095 : 0;
      if ( v60 >= v58 )
      {
        v61 = v54;
        RecommendedSaltSize = SmbCryptoHashGetRecommendedSaltSize(*(_QWORD *)(v124 + 200));
        v63 = -1;
        v64 = v54 + RecommendedSaltSize;
        v56 = -8;
        HIDWORD(Size) = RecommendedSaltSize;
        if ( v64 >= v54 )
          v63 = v54 + RecommendedSaltSize;
        v54 = v63;
        v59 = v64 < v61 ? 0xC0000095 : 0;
      }
    }
LABEL_192:
    if ( v110 && v59 >= 0 )
    {
      if ( (v54 & 7) != 0 )
      {
        if ( v54 + 7 < v54 )
        {
          v59 = -1073741675;
          goto LABEL_203;
        }
        v54 = (v54 + 7) & 0xFFFFFFF8;
      }
      v65 = v54 + 8;
      v66 = v54;
      v67 = v54;
      v68 = -1;
      if ( v54 + 8 >= v54 )
        v68 = v54 + 8;
      v54 = v68;
      v59 = v65 < v66 ? 0xC0000095 : 0;
      if ( v65 >= v67 )
      {
        v69 = v68 + 4;
        v70 = v68;
        v71 = v68 + 4 < v68;
        v72 = -1;
        if ( !v71 )
          v72 = v69;
        v54 = v72;
        v59 = v69 < v70 ? 0xC0000095 : 0;
      }
    }
LABEL_203:
    if ( v113 )
    {
      pulResult = 0;
      if ( v59 >= 0 )
      {
        if ( (v54 & 7) == 0 )
        {
LABEL_208:
          v73 = v124;
          v74 = v54 + 8;
          v75 = v54;
          v76 = v54;
          v77 = -1;
          if ( v54 + 8 >= v54 )
            v77 = v54 + 8;
          v54 = v77;
          v59 = v74 < v75 ? 0xC0000095 : 0;
          if ( v74 >= v76 )
          {
            v59 = RtlULongLongToULong(2LL * *(unsigned __int16 *)(v124 + 260), &pulResult);
            if ( v59 >= 0 )
            {
              v78 = -1;
              if ( pulResult < 0xFFFFFFF8 )
                v78 = pulResult + 8;
              v59 = pulResult >= 0xFFFFFFF8 ? 0xC0000095 : 0;
              if ( pulResult + 8 >= 8 )
              {
                v79 = v78 + v54;
                v80 = v54;
                v81 = -1;
                if ( v78 + v54 >= v54 )
                  v81 = v78 + v54;
                v54 = v81;
                v59 = v79 < v80 ? 0xC0000095 : 0;
              }
            }
          }
LABEL_221:
          if ( v112 )
          {
            pulResult = 0;
            if ( v59 >= 0 )
            {
              if ( (v54 & 7) != 0 )
              {
                if ( v54 + 7 < v54 )
                {
                  v59 = -1073741675;
                  goto LABEL_236;
                }
                v54 = v56 & (v54 + 7);
              }
              v82 = v54 + 8;
              v83 = v54;
              v84 = v54;
              v85 = -1;
              if ( v54 + 8 >= v54 )
                v85 = v54 + 8;
              v54 = v85;
              v59 = v82 < v83 ? 0xC0000095 : 0;
              if ( v82 >= v84 )
              {
                v59 = RtlULongLongToULong(2LL * *(unsigned __int16 *)(v73 + 256), &pulResult);
                if ( v59 >= 0 )
                {
                  v86 = -1;
                  if ( pulResult < 0xFFFFFFF8 )
                    v86 = pulResult + 8;
                  v59 = pulResult >= 0xFFFFFFF8 ? 0xC0000095 : 0;
                  if ( pulResult + 8 >= 8 )
                  {
                    v87 = v86 + v54;
                    v88 = v54;
                    v89 = -1;
                    if ( v86 + v54 >= v54 )
                      v89 = v86 + v54;
                    v54 = v89;
                    v59 = v87 < v88 ? 0xC0000095 : 0;
                  }
                }
              }
            }
          }
LABEL_236:
          if ( v111 && v59 >= 0 )
          {
            if ( (v54 & 7) == 0 )
            {
LABEL_241:
              v90 = v54 + 8;
              v91 = v54;
              v92 = v54;
              v93 = -1;
              if ( v54 + 8 >= v54 )
                v93 = v54 + 8;
              v54 = v93;
              v59 = v90 < v91 ? 0xC0000095 : 0;
              if ( v90 >= v92 )
              {
                v94 = v93 + 4;
                v95 = v93;
                v71 = v93 + 4 < v93;
                v96 = -1;
                if ( !v71 )
                  v96 = v94;
                v54 = v96;
                v59 = v94 < v95 ? 0xC0000095 : 0;
              }
              goto LABEL_247;
            }
            if ( v54 + 7 >= v54 )
            {
              v54 = v56 & (v54 + 7);
              goto LABEL_241;
            }
            v59 = -1073741675;
          }
LABEL_247:
          if ( v114 )
          {
            if ( v59 < 0 )
            {
LABEL_253:
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 42, &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids, a1);
              }
              goto LABEL_174;
            }
            v97 = v54 + 4;
            v98 = v54;
            if ( v54 + 4 >= v54 )
              v55 = v54 + 4;
            v54 = v55;
            v59 = v97 < v98 ? 0xC0000095 : 0;
          }
          if ( v59 < 0 )
            goto LABEL_253;
          v53 = Size;
          goto LABEL_260;
        }
        if ( v54 + 7 >= v54 )
        {
          v54 = (v54 + 7) & 0xFFFFFFF8;
          goto LABEL_208;
        }
        v59 = -1073741675;
      }
    }
    v73 = v124;
    goto LABEL_221;
  }
LABEL_260:
  if ( *(_DWORD *)(a1[39] + 32LL) < v54 )
  {
    NegotiateSecurityInfo = Srv2AllocateResponseBuffer(a1, v54, a1[38]);
    if ( NegotiateSecurityInfo < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 43, &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids, a1, v54);
      }
      goto LABEL_326;
    }
  }
  v99 = *(_QWORD *)(a1[39] + 24LL);
  if ( *(_BYTE *)(v124 + 266) )
  {
    memset(*(void **)(a1[39] + 24LL), 0, 0x40u);
    *(_DWORD *)v99 = 1112364030;
    *(_WORD *)(v99 + 4) = 64;
  }
  *(_DWORD *)(v99 + 16) |= 1u;
  memset((void *)(v99 + 64), 0, *(unsigned int *)(a1[39] + 32LL) - 64LL);
  *(_WORD *)(v99 + 64) = 65;
  *(_WORD *)(v99 + 66) = *(_WORD *)(v6 + 116);
  *(_WORD *)(v99 + 68) = *(_WORD *)(v6 + 44);
  *(_OWORD *)(v99 + 72) = Smb2Guid;
  *(_DWORD *)(v99 + 88) = *(_DWORD *)(v6 + 108);
  *(_DWORD *)(v99 + 92) = *(_DWORD *)(v6 + 36);
  *(_DWORD *)(v99 + 96) = *(_DWORD *)(v6 + 36);
  *(_DWORD *)(v99 + 100) = *(_DWORD *)(v6 + 36);
  *(_QWORD *)(v99 + 104) = MEMORY[0xFFFFF78000000014];
  *(_QWORD *)(v99 + 112) = 0;
  *(_QWORD *)(v99 + 120) = 0;
  *(_WORD *)(v99 + 70) = 0;
  IsRdmaConnection = SrvNetIsRdmaConnection(*(_QWORD *)(a1[12] + 480LL));
  pulResult = 12;
  v132 = 0;
  v133 = 0;
  if ( IsRdmaConnection )
  {
    RdmaNicInfo = SrvNetGetRdmaNicInfo(*(_QWORD *)(a1[12] + 480LL), &v132, &pulResult);
    if ( RdmaNicInfo < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        44,
        &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids,
        (unsigned int)RdmaNicInfo);
    }
  }
  if ( (unsigned int)dword_1400583B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400583B0, 0x400000000000LL, v101) )
  {
    v131 = 1;
    v135 = &v131;
    LOWORD(v123) = *(_WORD *)(v6 + 44);
    v137 = &v123;
    v104 = a1[12];
    v136 = 8;
    v138 = 2;
    v105 = *(_QWORD *)(v104 + 488);
    LOBYTE(v104) = *(_BYTE *)(v105 + 289);
    LOBYTE(v105) = *(_BYTE *)(v6 + 49);
    v117 = v104;
    v139 = &v117;
    v141 = &v118;
    v140 = 1;
    v119 = v105 & 1;
    v143 = &v119;
    v120 = (v105 & 4) != 0;
    LOBYTE(v105) = (v105 & 8) != 0;
    v118 = IsRdmaConnection;
    v145 = &v120;
    v147 = &v121;
    v128 = *(_DWORD *)(v6 + 32);
    v149 = &v128;
    v129 = v132;
    v151 = &v129;
    v153 = (char *)&v129 + 4;
    LODWORD(v124) = v133;
    v155 = &v124;
    LOWORD(Size) = *(_WORD *)(v6 + 140);
    p_Size = &Size;
    v142 = 1;
    v144 = 1;
    v146 = 1;
    v121 = v105;
    v148 = 1;
    v150 = 4;
    v152 = 4;
    v154 = 4;
    v156 = 4;
    v158 = 2;
    tlgWriteAgg(v105, (int)&dword_140042EA9, v103, 14, &v134);
  }
  *(_DWORD *)(a1[39] + 36LL) = 129;
  if ( v53 )
  {
    memmove((void *)(v99 + 128), Src, v53);
    *(_WORD *)(v99 + 120) = 128;
    *(_WORD *)(v99 + 122) = v53;
    *(_DWORD *)(a1[39] + 36LL) = v53 + 128;
  }
  if ( *(_WORD *)(v6 + 44) >= 0x311u )
  {
    NegotiateSecurityInfo = Smb2AddPreauthIntegrityCapabilitiesToResponse(a1, *(unsigned int *)(v6 + 132), WORD2(Size));
    if ( NegotiateSecurityInfo < 0 )
    {
      v51 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_326;
      }
      v52 = 45;
      goto LABEL_315;
    }
    if ( v110 )
    {
      NegotiateSecurityInfo = Smb2AddEncryptionCapabilitiesToResponse(a1, *(unsigned int *)(v6 + 136));
      if ( NegotiateSecurityInfo < 0 )
      {
        v51 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_326;
        }
        v52 = 46;
        goto LABEL_315;
      }
    }
    if ( v111 )
    {
      NegotiateSecurityInfo = Smb2AddSigningCapabilitiesToResponse(a1, *(unsigned int *)(v6 + 140));
      if ( NegotiateSecurityInfo < 0 )
      {
        v51 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_326;
        }
        v52 = 47;
        goto LABEL_315;
      }
    }
    if ( v112 )
    {
      NegotiateSecurityInfo = Smb2AddRdmaTransformCapabilitiesToResponse(a1, &v127, (unsigned __int16)v125);
      if ( NegotiateSecurityInfo < 0 )
      {
        v51 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_326;
        }
        v52 = 48;
        goto LABEL_315;
      }
    }
    if ( v113 )
    {
      NegotiateSecurityInfo = Smb2AddCompressionCapabilitiesToResponse(
                                a1,
                                *(unsigned int *)(v6 + 144),
                                *(unsigned int *)(v6 + 148));
      if ( NegotiateSecurityInfo < 0 )
      {
        v51 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_326;
        }
        v52 = 49;
        goto LABEL_315;
      }
    }
    if ( v114 )
    {
      v127 = 0;
      NegotiateSecurityInfo = Smb2AddNegotiateContextToResponse(a1, 6, 4, &v127);
      if ( NegotiateSecurityInfo < 0 )
      {
        v51 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_326;
        }
        v52 = 50;
        goto LABEL_315;
      }
      *v127 = v126;
    }
  }
  if ( (_BYTE)v116 )
  {
    NegotiateSecurityInfo = Smb2AddNetworkInterfaceCapabilitiesToResponse(a1);
    if ( NegotiateSecurityInfo < 0 )
    {
      v51 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_326;
      }
      v52 = 51;
LABEL_315:
      WPP_SF_qD(v51->AttachedDevice, v52, &WPP_c42acf1e461733399d557abc8a3740b7_Traceguids, a1, NegotiateSecurityInfo);
      goto LABEL_326;
    }
  }
  if ( *(_WORD *)(v6 + 44) >= 0x311u )
    a1[67] = Smb2UpdatePreauthIntegrityHashForResponse;
  NegotiateSecurityInfo = 0;
LABEL_326:
  if ( Src )
    FreeContextBuffer(Src);
  if ( NegotiateSecurityInfo < 0 )
    Smb2SetError(
      a1,
      (unsigned int)NegotiateSecurityInfo,
      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\negotiate.c",
      2149);
  else
    Smb2SetSuccess(a1, 0);
  return Srv2CompleteWorkItem(a1, 0);
}

```

## disassembly

```asm
0x140090240  push    rbp
0x140090242  push    rbx
0x140090243  push    rsi
0x140090244  push    rdi
0x140090245  push    r12
0x140090247  push    r13
0x140090249  push    r14
0x14009024b  push    r15
0x14009024d  lea     rbp, [rsp-0B8h]
0x140090255  sub     rsp, 1B8h
0x14009025c  mov     rax, cs:__security_cookie
0x140090263  xor     rax, rsp
0x140090266  mov     [rbp+0F0h+var_50], rax
0x14009026d  mov     rax, [rcx+60h]
0x140090271  xor     r14d, r14d
0x140090274  mov     r13, [rcx+230h]
0x14009027b  mov     r15, rcx
0x14009027e  mov     [rsp+1F0h+var_178], r13
0x140090283  mov     [rbp+0F0h+var_16C], r14d
0x140090287  mov     rdi, [rax+1F0h]
0x14009028e  lea     r12d, [r14+2]
0x140090292  xor     eax, eax
0x140090294  mov     dword ptr [rsp+1F0h+Size+4], r14d
0x140090299  mov     [rbp+0F0h+Src], rax
0x14009029d  mov     dword ptr [rsp+1F0h+Size], eax
0x1400902a1  mov     [rsp+1F0h+var_180], eax
0x1400902a5  mov     [rbp+0F0h+var_170], eax
0x1400902a8  mov     [rsp+1F0h+var_194], ax
0x1400902ad  movzx   eax, word ptr [r13+106h]
0x1400902b5  mov     ecx, eax
0x1400902b7  mov     [rdi+2Ch], ax
0x1400902bb  mov     [rsp+1F0h+pulResult], r14d
0x1400902c0  lea     eax, [r14+7]
0x1400902c4  mov     [rsp+1F0h+var_1A0], r14b
0x1400902c9  mov     [rsp+1F0h+var_19F], r14b
0x1400902ce  lea     ebx, [rax-6]
0x1400902d1  mov     [rsp+1F0h+var_19D], r14b
0x1400902d6  mov     [rsp+1F0h+var_19C], r14b
0x1400902db  mov     [rsp+1F0h+var_19E], r14b
0x1400902e0  sub     ecx, 202h
0x1400902e6  jz      short loc_140090335
0x1400902e8  sub     ecx, 0Eh
0x1400902eb  jz      short loc_140090335
0x1400902ed  sub     ecx, 0F0h
0x1400902f3  jz      short loc_140090330
0x1400902f5  sub     ecx, r12d
0x1400902f8  jz      short loc_140090320
0x1400902fa  sub     ecx, 0Fh
0x1400902fd  jz      short loc_140090317
0x1400902ff  cmp     ecx, ebx
0x140090301  jnz     short loc_140090345
0x140090303  mov     [rdi+28h], eax
0x140090306  mov     dword ptr [rdi+20h], 3
0x14009030d  mov     byte ptr [rdi+30h], 3
0x140090311  mov     [rdi+2Eh], ax
0x140090315  jmp     short loc_140090345
0x140090317  mov     dword ptr [rdi+28h], 3
0x14009031e  jmp     short loc_140090306
0x140090320  mov     [rdi+20h], r12d
0x140090324  mov     dword ptr [rdi+28h], 3
0x14009032b  mov     [rdi+30h], bl
0x14009032e  jmp     short loc_140090340
0x140090330  mov     [rdi+20h], ebx
0x140090333  jmp     short loc_140090339
0x140090335  mov     [rdi+20h], r14d
0x140090339  mov     [rdi+30h], r14b
0x14009033d  mov     [rdi+28h], ebx
0x140090340  mov     [rdi+2Eh], r14w
0x140090345  mov     [rdi+74h], bx
0x140090349  mov     rcx, [r15+40h]
0x14009034d  call    Srv2IsSigningRequiredForInstance
0x140090352  test    al, al
0x140090354  jnz     short loc_14009037A
0x140090356  cmp     cs:Smb2SigningRequiredForLoopback, r14b
0x14009035d  jz      short loc_140090382
0x14009035f  mov     rcx, [rdi+38h]
0x140090363  mov     rcx, [rcx+1E0h]
0x14009036a  call    cs:__imp_SrvNetIsConnectionLoopback
0x140090371  nop     dword ptr [rax+rax+00h]
0x140090376  test    al, al
0x140090378  jz      short loc_140090382
0x14009037a  or      [rdi+74h], r12w
0x14009037f  or      [rdi+31h], bl
0x140090382  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140090389  lea     rax, WPP_GLOBAL_Control
0x140090390  cmp     rcx, rax
0x140090393  jz      short loc_1400903C7
0x140090395  test    dword ptr [rcx+2Ch], 8000h
0x14009039c  jz      short loc_1400903C7
0x14009039e  cmp     [rcx+29h], r12b
0x1400903a2  jb      short loc_1400903C7
0x1400903a4  mov     rax, [r15+40h]
0x1400903a8  mov     edx, 19h
0x1400903ad  movzx   r8d, byte ptr [rdi+31h]
0x1400903b2  mov     rcx, [rcx+18h]
0x1400903b6  and     r8d, ebx
0x1400903b9  mov     dword ptr [rsp+1F0h+var_1D0], r8d
0x1400903be  movzx   r9d, byte ptr [rax]
0x1400903c2  call    WPP_SF_Dl
0x1400903c7  mov     esi, 300h
0x1400903cc  cmp     [rdi+2Ch], si
0x1400903d0  jnb     short loc_140090415
0x1400903d2  cmp     cs:AuditClientDoesNotSupportEncryption, r14b
0x1400903d9  jz      short loc_140090415
0x1400903db  test    cs:byte_14004C33B, 8
0x1400903e2  jz      short loc_140090415
0x1400903e4  mov     rcx, [r15+60h]
0x1400903e8  movzx   eax, cs:Smb2EncryptionEnabled
0x1400903ef  mov     dword ptr [rsp+1F0h+var_1C0], r12d
0x1400903f4  mov     dword ptr [rsp+1F0h+var_1C8], eax
0x1400903f8  movzx   r9d, word ptr [rcx+168h]
0x140090400  mov     rax, [rcx+170h]
0x140090407  shr     r9w, 1
0x14009040b  mov     [rsp+1F0h+var_1D0], rax
0x140090410  call    McTemplateK0hzr0tq_EtwWriteTransfer
0x140090415  movzx   r8d, word ptr [rdi+2Ch]
0x14009041a  mov     eax, r14d
0x14009041d  cmp     r8w, si
0x140090421  mov     r9d, 10h
0x140090427  setnb   al
0x14009042a  mov     [rdi+8Ch], eax
0x140090430  mov     eax, 210h
0x140090435  or      [rdi+6Ch], ebx
0x140090438  lea     r10d, [r9+30h]
0x14009043c  mov     edx, [rdi+6Ch]
0x14009043f  cmp     r8w, ax
0x140090443  jb      loc_140090582
0x140090449  cmp     cs:Smb2LeasingEnabled, r14b
0x140090450  jz      short loc_140090458
0x140090452  or      edx, r12d
0x140090455  mov     [rdi+6Ch], edx
0x140090458  mov     rax, [r15+60h]
0x14009045c  mov     rcx, [rax+1E8h]
0x140090463  cmp     [rcx+121h], r14b
0x14009046a  jnz     short loc_140090476
0x14009046c  or      edx, 4
0x14009046f  or      [rdi+31h], r12b
0x140090473  mov     [rdi+6Ch], edx
0x140090476  cmp     r8w, si
0x14009047a  jb      loc_140090582
0x140090480  cmp     cs:Smb2IsRkfInstalled, r14b
0x140090487  lea     rbx, [r13+0F8h]
0x14009048e  jz      short loc_1400904A1
0x140090490  mov     eax, [rbx]
0x140090492  test    r9b, al
0x140090495  jz      short loc_1400904A1
0x140090497  or      byte ptr [rdi+31h], 4
0x14009049b  or      edx, r9d
0x14009049e  mov     [rdi+6Ch], edx
0x1400904a1  cmp     cs:Smb2MultiChannelEnabled, r14b
0x1400904a8  jz      short loc_1400904B6
0x1400904aa  mov     eax, [rbx]
0x1400904ac  test    al, 8
0x1400904ae  jz      short loc_1400904B6
0x1400904b0  or      edx, 8
0x1400904b3  mov     [rdi+6Ch], edx
0x1400904b6  cmp     cs:Smb2DirLeasingEnabled, r14b
0x1400904bd  jz      short loc_1400904CB
0x1400904bf  mov     eax, [rbx]
0x1400904c1  test    al, 20h
0x1400904c3  jz      short loc_1400904CB
0x1400904c5  or      edx, 20h
0x1400904c8  mov     [rdi+6Ch], edx
0x1400904cb  cmp     cs:Smb2EncryptionEnabled, r14b
0x1400904d2  mov     ecx, 311h
0x1400904d7  jz      short loc_140090503
0x1400904d9  mov     eax, [rbx]
0x1400904db  test    r10b, al
0x1400904de  jz      short loc_140090503
0x1400904e0  cmp     r8w, cx
0x1400904e4  jnb     short loc_140090503
0x1400904e6  mov     rcx, r15
0x1400904e9  call    Smb2SelectCommonCipherForConnection
0x1400904ee  test    byte ptr [rdi+31h], 8
0x1400904f2  mov     r10d, 40h ; '@'
0x1400904f8  mov     ecx, 311h
0x1400904fd  jz      short loc_140090503
0x1400904ff  or      [rdi+6Ch], r10d
0x140090503  mov     eax, [rbx]
0x140090505  test    r10b, al
0x140090508  jnz     short loc_140090559
0x14009050a  cmp     [rdi+2Ch], cx
0x14009050e  jnb     short loc_140090559
0x140090510  cmp     cs:AuditClientDoesNotSupportEncryption, r14b
0x140090517  jz      short loc_140090559
0x140090519  test    cs:byte_14004C33B, 8
0x140090520  jz      short loc_140090559
0x140090522  mov     rcx, [r15+60h]
0x140090526  movzx   eax, cs:Smb2EncryptionEnabled
0x14009052d  mov     dword ptr [rsp+1F0h+var_1C0], r14d
0x140090532  mov     dword ptr [rsp+1F0h+var_1C8], eax
0x140090536  movzx   r9d, word ptr [rcx+168h]
0x14009053e  mov     rax, [rcx+170h]
0x140090545  shr     r9w, 1
0x140090549  mov     [rsp+1F0h+var_1D0], rax
0x14009054e  call    McTemplateK0hzr0tq_EtwWriteTransfer
0x140090553  mov     r10d, 40h ; '@'
0x140090559  cmp     cs:Smb2NotificationsEnabled, r14b
0x140090560  jz      short loc_14009057D
0x140090562  mov     eax, [rbx]
0x140090564  mov     r11d, 80h
0x14009056a  lea     ebx, [r11-7Fh]
0x14009056e  test    r11b, al
0x140090571  jz      short loc_140090582
0x140090573  or      [rdi+31h], r10b
0x140090577  or      [rdi+6Ch], r11d
0x14009057b  jmp     short loc_140090582
0x14009057d  mov     ebx, 1
0x140090582  mov     esi, 311h
0x140090587  lea     r12, WPP_c42acf1e461733399d557abc8a3740b7_Traceguids
0x14009058e  cmp     [rdi+2Ch], si
0x140090592  jb      loc_140090B99
0x140090598  movzx   edx, word ptr [r13+0FCh]
0x1400905a0  lea     rbx, [rdi+84h]
0x1400905a7  mov     rcx, [r13+0D0h]
0x1400905ae  mov     r8, rbx
0x1400905b1  call    Smb2SelectPreauthIntegrityHashAlgorithm
0x1400905b6  test    eax, eax
0x1400905b8  jns     short loc_14009060A
0x1400905ba  mov     esi, 0C05D0000h
0x1400905bf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400905c6  lea     rdx, WPP_GLOBAL_Control
0x1400905cd  cmp     rcx, rdx
0x1400905d0  jz      loc_1400916EE
0x1400905d6  test    dword ptr [rcx+2Ch], 8000h
0x1400905dd  jz      loc_1400916EE
0x1400905e3  cmp     byte ptr [rcx+29h], 1
0x1400905e7  jb      loc_1400916EE
0x1400905ed  mov     rcx, [rcx+18h]
0x1400905f1  lea     r8, WPP_c42acf1e461733399d557abc8a3740b7_Traceguids
0x1400905f8  mov     edx, 1Ah
0x1400905fd  mov     r9, r15
0x140090600  call    WPP_SF_q
0x140090605  jmp     loc_1400916EE
0x14009060a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140090611  lea     rdx, WPP_GLOBAL_Control
0x140090618  cmp     rcx, rdx
0x14009061b  jz      short loc_140090646
0x14009061d  test    dword ptr [rcx+2Ch], 8000h
0x140090624  jz      short loc_140090646
0x140090626  cmp     byte ptr [rcx+29h], 4
0x14009062a  jb      short loc_140090646
0x14009062c  mov     eax, [rbx]
0x14009062e  mov     edx, 1Bh
0x140090633  mov     rcx, [rcx+18h]
0x140090637  mov     r9, r15
0x14009063a  mov     r8, r12
0x14009063d  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x140090641  call    WPP_SF_qD
0x140090646  mov     edx, [rbx]
0x140090648  lea     r14, [r13+0C8h]
0x14009064f  mov     rcx, r14
0x140090652  mov     r8b, 1
0x140090655  call    cs:__imp_SmbCryptoHashCreate
0x14009065c  nop     dword ptr [rax+rax+00h]
0x140090661  mov     esi, eax
0x140090663  test    eax, eax
0x140090665  jns     short loc_1400906BA
0x140090667  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14009066e  lea     rax, WPP_GLOBAL_Control
0x140090675  cmp     r10, rax
0x140090678  jz      loc_1400916EE
0x14009067e  test    dword ptr [r10+2Ch], 8000h
0x140090686  jz      loc_1400916EE
0x14009068c  cmp     byte ptr [r10+29h], 1
0x140090691  jb      loc_1400916EE
0x140090697  mov     eax, [rbx]
0x140090699  mov     edx, 1Ch
0x14009069e  mov     rcx, [r10+18h]
0x1400906a2  mov     dword ptr [rsp+1F0h+var_1C8], esi
0x1400906a6  mov     r8, r12
0x1400906a9  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x1400906ad  mov     r9, r15
0x1400906b0  call    WPP_SF_qDD
0x1400906b5  jmp     loc_1400916EE
0x1400906ba  mov     rcx, [r14]
0x1400906bd  call    cs:__imp_SmbCryptoHashGetOutputLength
0x1400906c4  nop     dword ptr [rax+rax+00h]
0x1400906c9  mov     edx, eax
0x1400906cb  mov     ecx, 100h
0x1400906d0  mov     r8d, 6332534Ch
0x1400906d6  mov     [rdi+80h], edx
0x1400906dc  call    cs:__imp_ExAllocatePool2
0x1400906e3  nop     dword ptr [rax+rax+00h]
0x1400906e8  mov     [rdi+78h], rax
0x1400906ec  mov     rdx, rax
0x1400906ef  test    rax, rax
0x1400906f2  jnz     short loc_140090741
0x1400906f4  mov     esi, 0C000009Ah
0x1400906f9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140090700  lea     rax, WPP_GLOBAL_Control
0x140090707  cmp     rcx, rax
0x14009070a  jz      loc_1400916EE
0x140090710  test    dword ptr [rcx+2Ch], 8000h
0x140090717  jz      loc_1400916EE
0x14009071d  cmp     byte ptr [rcx+29h], 1
0x140090721  jb      loc_1400916EE
0x140090727  mov     eax, [rdi+80h]
0x14009072d  mov     edx, 1Dh
0x140090732  mov     dword ptr [rsp+1F0h+var_1C8], eax
  ... truncated ...
```
