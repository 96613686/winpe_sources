# UlSendHttpResponseOrEntityBodyIoctl

- ea: `0x1400f1b08`
- end: `0x1400f2b18`
- name: `UlSendHttpResponseOrEntityBodyIoctl`
- size: `4112`
- prototype: `__int64 __fastcall(PIRP Irp, __int64, unsigned __int8)`
- caller_count: `2`
- callee_count: `41`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14009ee50`
- `0x1400f1ae0`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x140019f88`
- `0x14001a794`
- `0x14001f2c0`
- `0x14001f9f4`
- `0x140020290`
- `0x140022610`
- `0x140033830`
- `0x1400354a0`
- `0x140035a50`
- `0x140039340`
- `0x140062bd0`
- `0x1400829a0`
- `0x14008aaf0`
- `0x14009da24`
- `0x1400a69ec`
- `0x1400b1acc`
- `0x1400b379c`
- `0x1400c8dd0`
- `0x1400d3cd0`
- `0x1400e35c0`
- `0x1400e36dc`
- `0x1400e3c84`
- `0x1400ee304`
- `0x1400f1b08`
- `0x1400f677c`
- `0x1400f71f0`
- `0x1400fb744`
- `0x1400fb7ec`
- `0x1400fce98`
- `0x140129028`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c37f8`
- `0x1401cdb74`
- `0x1401cdbcc`
- `0x1401cdfe8`
- `0x1401da550`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400f29b0`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f29b0`
- `ntoskrnl!IofCompleteRequest` at `0x1400f2abd`
- `ntoskrnl!IofCompleteRequest` at `0x1400f2abd`
- `ntoskrnl!IoIs32bitProcess` at `0x1400f1c54`
- `ntoskrnl!IoIs32bitProcess` at `0x1400f1c54`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f1ecb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f1ecb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f23a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f23ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f23d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f23a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f23ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f23d1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400f1e7e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400f1e7e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400f1ebf`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400f1ebf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f1e63`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f1e63`

## pseudocode

```c
__int64 __fastcall UlSendHttpResponseOrEntityBodyIoctl(PIRP Irp, __int64 a2, unsigned __int8 a3)
{
  int v3; // r12d
  IRP *v5; // r13
  __int64 v6; // rsi
  unsigned __int16 v7; // bx
  BOOLEAN v8; // r15
  __int64 v9; // rdx
  __int64 v10; // rdx
  int ConsumerAndApiVersion; // edi
  unsigned int v12; // ebx
  int v13; // eax
  _WORD *v14; // r14
  char v15; // r15
  __int64 v16; // rcx
  __int64 *v17; // rdx
  __int64 v18; // r8
  int v19; // r9d
  bool v20; // di
  const char *v21; // r9
  __int64 v22; // rax
  unsigned int v23; // r10d
  __int16 v24; // cx
  char v25; // al
  unsigned __int8 v26; // dl
  char v27; // al
  bool v28; // r12
  unsigned __int8 v29; // r15
  bool v30; // r14
  __int16 v31; // ax
  __int64 v32; // r8
  int v33; // eax
  int v34; // ecx
  __int64 v35; // r15
  unsigned int v36; // eax
  __int64 v37; // r15
  PVOID v38; // rbx
  __int64 v39; // rdx
  char v40; // r13
  __int16 v41; // r14
  int v42; // eax
  __int64 v43; // r8
  int v44; // r9d
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // r9
  __int64 v51; // rdx
  bool v52; // zf
  int v53; // eax
  __int64 v54; // rbx
  unsigned int v55; // eax
  __int64 v56; // rbx
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // r14
  int v60; // eax
  __int64 v61; // rcx
  ULONG_PTR v62; // rdx
  int v63; // eax
  __int64 v64; // rbx
  __int64 v65; // rsi
  __int64 v66; // r9
  __int16 v67; // bx
  __int64 v69; // [rsp+20h] [rbp-120h]
  int v70[2]; // [rsp+28h] [rbp-118h]
  int v71; // [rsp+40h] [rbp-100h]
  unsigned int v72; // [rsp+48h] [rbp-F8h]
  char v73; // [rsp+58h] [rbp-E8h]
  int v74; // [rsp+70h] [rbp-D0h]
  char v75; // [rsp+C0h] [rbp-80h]
  char v77; // [rsp+C3h] [rbp-7Dh]
  char v78; // [rsp+C4h] [rbp-7Ch] BYREF
  _BYTE v79[3]; // [rsp+C5h] [rbp-7Bh] BYREF
  PVOID P; // [rsp+C8h] [rbp-78h] BYREF
  __int64 v81; // [rsp+D0h] [rbp-70h] BYREF
  char v82; // [rsp+D8h] [rbp-68h] BYREF
  char v83[11]; // [rsp+D9h] [rbp-67h] BYREF
  int v84; // [rsp+E4h] [rbp-5Ch]
  int v85; // [rsp+E8h] [rbp-58h] BYREF
  PVOID v86; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v87; // [rsp+F8h] [rbp-48h]
  __int64 v88; // [rsp+100h] [rbp-40h] BYREF
  __int64 v89; // [rsp+108h] [rbp-38h] BYREF
  IRP *v90; // [rsp+110h] [rbp-30h]
  __int64 v91[2]; // [rsp+118h] [rbp-28h] BYREF
  __int128 v92; // [rsp+128h] [rbp-18h]
  __int128 v93; // [rsp+138h] [rbp-8h]
  __int64 v94; // [rsp+148h] [rbp+8h]
  __int64 v95; // [rsp+150h] [rbp+10h] BYREF
  __int64 v96[3]; // [rsp+158h] [rbp+18h] BYREF
  __int64 v97[18]; // [rsp+170h] [rbp+30h] BYREF
  _BYTE v98[576]; // [rsp+200h] [rbp+C0h] BYREF
  __int64 v99[18]; // [rsp+440h] [rbp+300h] BYREF
  __int128 v100; // [rsp+4D0h] [rbp+390h] BYREF
  __int64 v101; // [rsp+4E0h] [rbp+3A0h] BYREF
  __int128 v102; // [rsp+4E8h] [rbp+3A8h]
  __int64 v103; // [rsp+4F8h] [rbp+3B8h]
  _BYTE v104[288]; // [rsp+500h] [rbp+3C0h] BYREF

  v3 = a3;
  v90 = Irp;
  v5 = Irp;
  v95 = 0;
  v94 = 0;
  v6 = 0;
  *(_OWORD *)v91 = 0;
  v92 = 0;
  v93 = 0;
  memset(v98, 0, 0x238u);
  v86 = 0;
  v89 = 0;
  v103 = 0;
  v77 = 0;
  v83[3] = 0;
  v102 = 0;
  LODWORD(v101) = 0;
  memset(v104, 0, sizeof(v104));
  P = 0;
  v83[2] = 0;
  memset(v97, 0, sizeof(v97));
  v81 = 0;
  v7 = 0;
  *(_WORD *)&v83[7] = 0;
  v83[1] = 0;
  v85 = 0;
  v84 = 0;
  v100 = 0;
  v79[0] = 0;
  v78 = 0;
  v82 = 0;
  v88 = 0;
  memset(v99, 0, 0x88u);
  v83[4] = 0;
  v75 = 0;
  v87 = 0;
  v83[0] = 0;
  v96[0] = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qqD(1033, 71, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, v5, a2, v3);
  v8 = IoIs32bitProcess(v5);
  ConsumerAndApiVersion = UlGetConsumerAndApiVersion(*(_QWORD *)(a2 + 48), v9, &v89, &v85);
  if ( ConsumerAndApiVersion >= 0 )
  {
    v12 = v85;
    LOBYTE(v10) = v5->RequestorMode;
    v13 = UlParseHttpSendHttpResponseIoctls(
            v5,
            v10,
            v8,
            v3,
            *(_QWORD *)(a2 + 32),
            *(_DWORD *)(a2 + 16),
            v85,
            0,
            (__int64)v91,
            v98,
            (__int64)v97,
            &v86,
            (__int64)&v83[3],
            (__int64)v99,
            v74,
            (__int64)&v101,
            (__int64)&P,
            (__int64)&v83[2],
            (__int64)&v81,
            (__int64)&v83[1],
            v83,
            (__int64)v96,
            (__int64)&v83[7]);
    v14 = v86;
    ConsumerAndApiVersion = v13;
    if ( v13 < 0 )
      goto LABEL_99;
    if ( v86 )
      v84 = *((unsigned __int16 *)v86 + 4);
    if ( (BYTE8(v93) & 2) != 0 )
    {
      v75 = 0;
      v15 = 0;
    }
    else
    {
      v15 = v93;
      v75 = 1;
      v87 = v93;
      *((_QWORD *)&v100 + 1) = *((_QWORD *)&UlEtwBaseOpaqueIdActivityGuid + 1);
      *(_QWORD *)&v100 = v93;
      v16 = *(_QWORD *)(*(_QWORD *)(v89 + 8) + 328LL);
      if ( (_BYTE)v3 )
      {
        if ( (*(_BYTE *)(v16 + 1760) & 4) == 0 )
          goto LABEL_15;
        v17 = HTTP_EVENT_RECEIVE_BODY_FROM_USERMODE_LEGACY;
        goto LABEL_11;
      }
      if ( (*(_BYTE *)(v16 + 1760) & 4) != 0 )
      {
        v17 = HTTP_EVENT_RECEIVE_RESPONSE_FROM_USERMODE_LEGACY;
LABEL_11:
        McTemplateK0x_EtwWriteTransfer(v16 + 1688, v17, &v100, v93);
      }
    }
LABEL_15:
    ConsumerAndApiVersion = UlGetRequest(v93, v89, &v95);
    if ( ConsumerAndApiVersion < 0 )
    {
      v6 = v95;
      goto LABEL_99;
    }
    v20 = 0;
    v6 = v95;
    if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
    {
      v21 = "entity body";
      if ( !(_BYTE)v3 )
        v21 = "response";
      WPP_SF_siDi(
        (unsigned int)"response",
        1,
        v18,
        (_DWORD)v21,
        v15,
        SBYTE8(v93),
        *(_QWORD *)(*(_QWORD *)(v95 + 24) + 48LL));
    }
    if ( (_BYTE)v3 )
    {
      if ( *(_QWORD *)(v6 + 2488) )
      {
        v85 = 0;
        KeEnterCriticalRegion();
        ExAcquirePushLockSharedEx(*(_QWORD *)(v6 + 24) + 576LL, 0);
        v22 = *(_QWORD *)(v6 + 2512);
        if ( v22 && !*(_DWORD *)(v22 + 136) )
        {
          v20 = *(_DWORD *)(v22 + 256) == 1;
          v85 = v20;
        }
        ExReleasePushLockSharedEx(*(_QWORD *)(v6 + 24) + 576LL, 0);
        KeLeaveCriticalRegion();
        if ( v20 )
          goto LABEL_35;
      }
      else
      {
        LOBYTE(v85) = 0;
      }
      if ( !*(_DWORD *)(v6 + 2212) )
      {
        v23 = DWORD2(v93);
        if ( (BYTE8(v93) & 4) != 0 || (unsigned __int8)UlAutomaticChunkingTransformationNeeded(v6, DWORD2(v93), v18) )
          goto LABEL_36;
        if ( (unsigned __int8)UxTpIsFastSendPossible(*(_QWORD *)(v6 + 24) + 976LL) )
        {
          v24 = *(_WORD *)&v83[7];
          if ( *(_WORD *)&v83[7] == 1 && !*(_DWORD *)P && (unsigned int)(*((_DWORD *)P + 4) - 1) <= 0xFFFF )
          {
            v23 = DWORD2(v93);
            v25 = 1;
            goto LABEL_37;
          }
        }
      }
LABEL_35:
      v23 = DWORD2(v93);
LABEL_36:
      v24 = *(_WORD *)&v83[7];
      v25 = 0;
LABEL_37:
      v26 = v75 || (v23 & 1) != 0;
      if ( v25 )
      {
        if ( !v24 )
        {
          v27 = 0;
          goto LABEL_76;
        }
LABEL_75:
        v27 = 1;
LABEL_76:
        LOBYTE(v19) = v14 != 0;
        v33 = UlCheckSendResponseFlags(v6, v23, (unsigned __int16)v84, v19, 0, v27);
        ConsumerAndApiVersion = v33;
        if ( v33 < 0 )
        {
          if ( (BYTE8(xmmword_1401A2C90) & 0x40) == 0 )
            goto LABEL_99;
          v39 = 73;
        }
        else
        {
          v33 = UlCheckForZombieConnection(v6, *(_QWORD *)(v6 + 24), DWORD2(v93), v94, v5->RequestorMode);
          ConsumerAndApiVersion = v33;
          if ( v33 >= 0 )
          {
            v34 = DWORD2(v93);
            if ( (WORD4(v93) & 0x100) != 0 )
            {
              v35 = *(_QWORD *)(v6 + 24);
              if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
                WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v35 + 496, 51, 0, 0, 0, 0);
              v36 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(v35 + 504)
                                                                                               + 136LL))(
                      *(_QWORD *)(v35 + 496),
                      51,
                      0,
                      0,
                      0,
                      0);
              ConsumerAndApiVersion = v36;
              if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
                WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v36);
              v14 = v86;
              if ( ConsumerAndApiVersion < 0 )
              {
                v77 = 1;
                goto LABEL_99;
              }
              v34 = DWORD2(v93);
            }
            v37 = v81;
            v72 = v12;
            v38 = P;
            ConsumerAndApiVersion = UlFastSendHttpResponse(
                                      (_DWORD)v14,
                                      v94,
                                      (_DWORD)P,
                                      1,
                                      *((_DWORD *)P + 4),
                                      0,
                                      0,
                                      v34,
                                      v6,
                                      v72,
                                      (__int64)v5,
                                      v5->RequestorMode,
                                      v81,
                                      0,
                                      0,
                                      0);
LABEL_100:
            if ( v83[1] )
              ExFreePoolWithTag(*(PVOID *)(v37 + 16), 0);
            if ( v83[2] )
              ExFreePoolWithTag(v38, 0);
            if ( v83[3] )
              ExFreePoolWithTag(v14, 0);
            LOBYTE(v3) = a3;
            v7 = v84;
            goto LABEL_154;
          }
          if ( (BYTE8(xmmword_1401A2C90) & 0x40) == 0 )
            goto LABEL_99;
          v39 = 74;
        }
LABEL_89:
        WPP_SF_d(774, v39, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, (unsigned int)v33);
        goto LABEL_99;
      }
      v28 = 0;
      v29 = 0;
      v30 = 0;
      goto LABEL_94;
    }
    v28 = 0;
    if ( DWORD2(v92) )
      v28 = (*(_DWORD *)(v6 + 2200) & 2) != 0;
    v29 = *(_QWORD *)(v6 + 2488)
       && (BYTE8(v93) & 0x10) == 0
       && (BYTE8(v93) & 0x40) == 0
       && ((unsigned __int16)v12 < 2u || !v14[276])
       && ((v31 = v14[4], v31 == 200) || v31 == 206)
       && *(_DWORD *)(v6 + 2676) <= 1u;
    if ( v28 )
    {
      v30 = v28;
    }
    else if ( v29 )
    {
      v30 = (*(_DWORD *)(v6 + 2200) & 4) != 0;
    }
    else
    {
      v30 = 0;
    }
    ConsumerAndApiVersion = UlProcessResponseInfo(
                              v6,
                              v89,
                              (unsigned int)v99,
                              (unsigned int)&v100,
                              (__int64)&v78,
                              (__int64)&v82);
    if ( ConsumerAndApiVersion < 0 )
      goto LABEL_98;
    LOBYTE(v85) = 0;
    if ( !v29 && !v28 && !LOBYTE(v99[0]) )
    {
      v23 = DWORD2(v93);
      if ( (BYTE8(v93) & 4) != 0
        || (BYTE8(v93) & 0x20) != 0
        || (unsigned __int8)UlAutomaticChunkingTransformationNeeded(v6, DWORD2(v93), v32) )
      {
        goto LABEL_93;
      }
      if ( (unsigned __int8)UxTpIsFastSendPossible(*(_QWORD *)(v6 + 24) + 976LL)
        && *(_WORD *)&v83[7] == 1
        && !*(_DWORD *)P
        && (unsigned int)(*((_DWORD *)P + 4) - 1) <= 0xFFFF
        && !v78
        && !v82 )
      {
        v23 = DWORD2(v93);
        v14 = v86;
        goto LABEL_75;
      }
    }
    v23 = DWORD2(v93);
LABEL_93:
    v26 = 0;
LABEL_94:
    v40 = v83[0];
    v73 = v30;
    v41 = *(_WORD *)&v83[7];
    v42 = UlCaptureHttpResponse(
            v89,
            v12,
            (__int64)v86,
            v6,
            v90,
            *(unsigned __int16 *)&v83[7],
            (__int64)P,
            SHIDWORD(v99[0]),
            v99[16],
            v90->RequestorMode,
            v23,
            v73,
            0,
            v94,
            v29,
            v26,
            v83[0],
            v96[0],
            v81,
            v78,
            &v88);
    ConsumerAndApiVersion = v42;
    if ( v42 < 0 )
    {
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
        WPP_SF_d(774, 75, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, (unsigned int)v42);
      v5 = v90;
      goto LABEL_98;
    }
    if ( a3 )
    {
      if ( *(_DWORD *)(v6 + 2212) == 1 )
      {
        ConsumerAndApiVersion = 0;
        v5 = v90;
        v90->IoStatus.Information = *(_QWORD *)(v88 + 520);
LABEL_98:
        v14 = v86;
        goto LABEL_99;
      }
      v45 = *(_QWORD *)(v6 + 24);
      if ( v45 )
      {
        v46 = *(_QWORD *)(v45 + 1096);
        if ( (*(_BYTE *)(v46 + 1760) & 4) != 0
          && (!*(_QWORD *)(v46 + 1776) || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(v6, v45, 0)) )
        {
          McTemplateK0xx_EtwWriteTransfer(
            *(_QWORD *)(*(_QWORD *)(v6 + 24) + 1096LL) + 1688LL,
            v45,
            v6 + 72,
            *(_QWORD *)(v6 + 56),
            *(_QWORD *)(*(_QWORD *)(v6 + 24) + 48LL));
        }
      }
    }
    else
    {
      v47 = *(_QWORD *)(v6 + 24);
      if ( v47 )
      {
        v48 = *(_QWORD *)(v47 + 1096);
        if ( (*(_BYTE *)(v48 + 1760) & 4) != 0
          && (!*(_QWORD *)(v48 + 1776) || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(v6, v47, 0)) )
        {
          v49 = UlVerbToString(*(unsigned int *)(v88 + 156), v88, v43, *(_QWORD *)(v6 + 24));
          McTemplateK0xxhsqhq_EtwWriteTransfer(
            *(_QWORD *)(v50 + 1096) + 1688,
            (unsigned int)HTTP_EVENT_RECEIVE_RESPONSE_FROM_USERMODE,
            v6 + 72,
            *(_QWORD *)(v6 + 56),
            *(_QWORD *)(v50 + 48),
            *(_WORD *)(v51 + 152),
            v49,
            *(_DWORD *)(v51 + 168),
            v91[1],
            SBYTE8(v92));
        }
      }
      if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
      {
        LOWORD(v71) = v91[1];
        LOWORD(v70[0]) = *(_WORD *)(v88 + 152);
        WPP_SF_iiHLLHL(
          v88,
          76,
          WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids,
          *(_QWORD *)(v6 + 56),
          *(_QWORD *)(*(_QWORD *)(v6 + 24) + 48LL),
          v70[0],
          *(_DWORD *)(v88 + 156),
          *(_DWORD *)(v88 + 168),
          v71,
          DWORD2(v92));
      }
    }
    v52 = v41 == 0;
    v14 = v86;
    LOBYTE(v44) = v86 != 0;
    v53 = UlCheckSendResponseFlags(v6, DWORD2(v93), (unsigned __int16)v84, v44, v40, !v52);
    ConsumerAndApiVersion = v53;
    if ( v53 < 0 )
    {
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
        WPP_SF_d(774, 77, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, (unsigned int)v53);
      v5 = v90;
      goto LABEL_99;
    }
    v5 = v90;
    v33 = UlCheckForZombieConnection(v6, *(_QWORD *)(v6 + 24), DWORD2(v93), v94, v90->RequestorMode);
    ConsumerAndApiVersion = v33;
    if ( v33 < 0 )
    {
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) == 0 )
        goto LABEL_99;
      v39 = 78;
      goto LABEL_89;
    }
    if ( !v94 || !v75 || (v33 = UlCaptureUserLogData(v94, v6, v88 + 512), ConsumerAndApiVersion = v33, v33 >= 0) )
    {
      if ( (WORD4(v93) & 0x100) == 0 )
        goto LABEL_210;
      v54 = *(_QWORD *)(v6 + 24);
      if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v54 + 496, 51, 0, 0, 0, 0);
      *(_QWORD *)v70 = 0;
      v69 = 0;
      v55 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)(v54 + 504) + 136LL))(
              *(_QWORD *)(v54 + 496),
              51,
              0,
              0);
      ConsumerAndApiVersion = v55;
      if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v55);
      v14 = v86;
      if ( ConsumerAndApiVersion < 0 )
      {
        v77 = 1;
      }
      else
      {
LABEL_210:
        if ( (unsigned __int8)UlSetSendIrpCancelRoutine(*(_QWORD *)(v6 + 24), v5) )
        {
          *(_QWORD *)(v88 + 592) = v5;
          v56 = v88;
          v88 = 0;
          if ( a3 )
          {
            *(_BYTE *)(v56 + 51) = v85;
          }
          else if ( v29 )
          {
            *(_BYTE *)(v56 + 50) = UlpSetResponseCacheClassification(v6, v56, *((_QWORD *)&v92 + 1));
          }
          if ( !v28
            || (ConsumerAndApiVersion = UlCacheAndSendResponse(v6, v56, v89, DWORD2(v92), v69, v56, (__int64)v79),
                ConsumerAndApiVersion >= 0)
            && !v79[0] )
          {
            ConsumerAndApiVersion = UlSendHttpResponse(v6, v56, (unsigned int)UlRestartSendHttpResponseIoctl, v56, 0);
          }
          if ( ConsumerAndApiVersion != 259 )
          {
            UlRestartSendHttpResponseIoctl(v56, (unsigned int)ConsumerAndApiVersion, 0);
            v77 = 1;
            ConsumerAndApiVersion = 259;
          }
        }
        else
        {
          ConsumerAndApiVersion = -1073741536;
        }
      }
      goto LABEL_99;
    }
    if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
    {
      v39 = 79;
      goto LABEL_89;
    }
LABEL_99:
    v38 = P;
    v37 = v81;
    goto LABEL_100;
  }
LABEL_154:
  UlFreeResponseInfoParsedElements(v99);
  if ( !v6 )
  {
    v59 = v87;
    goto LABEL_183;
  }
  if ( !(_BYTE)v3 )
  {
    if ( !v79[0] && ConsumerAndApiVersion != -1073741766 )
      UlpFlushHttpPushList(v6, 0);
    if ( !v7 )
    {
      v7 = *(_WORD *)(v6 + 1690);
      v84 = v7;
    }
    if ( v75 )
    {
      if ( (int)(ConsumerAndApiVersion + 0x80000000) >= 0 && ConsumerAndApiVersion != -1073741766 )
      {
        v57 = *(_QWORD *)(v6 + 24);
        if ( v57
          && (v58 = *(_QWORD *)(v57 + 1096), (*(_BYTE *)(v58 + 1760) & 0x20) != 0)
          && (!*(_QWORD *)(v58 + 1776) || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(v6, v57, 0)) )
        {
          v59 = v87;
          LOWORD(v69) = v7;
          McTemplateK0xh_EtwWriteTransfer(
            *(_QWORD *)(*(_QWORD *)(v6 + 24) + 1096LL) + 1688LL,
            HTTP_EVENT_COMPLETE_SEND_ERROR_LEGACY,
            &v100,
            v87,
            v69);
        }
        else
        {
          v59 = v87;
        }
        v83[4] = 1;
        goto LABEL_176;
      }
LABEL_173:
      v59 = v87;
      if ( !v77 )
        goto LABEL_177;
      goto LABEL_176;
    }
  }
  if ( (int)(ConsumerAndApiVersion + 0x80000000) < 0 || ConsumerAndApiVersion == -1073741766 )
    goto LABEL_173;
  v59 = v87;
LABEL_176:
  UlCloseConnection(*(_QWORD *)(v6 + 24));
LABEL_177:
  v60 = _InterlockedDecrement((volatile signed __int32 *)(v6 + 48));
  if ( UxDebugCheckRefcount && v60 <= -1 )
    UlBugCheckEx(3u, v6 + 48, 0xBu, v60);
  if ( !v60 )
    UlpQueueFreeHttpRequest(v6);
LABEL_183:
  v61 = v88;
  if ( v88 )
  {
    v62 = v88 + 20;
    v63 = _InterlockedDecrement((volatile signed __int32 *)(v88 + 20));
    if ( UxDebugCheckRefcount && v63 <= -1 )
      UlBugCheckEx(3u, v62, 1u, v63);
    if ( !v63 )
    {
      v64 = v61 + 608;
      *(_OWORD *)v96 = 0;
      if ( *(_QWORD *)(v61 + 608) || *(_QWORD *)(v61 + 624) || *(_QWORD *)(v61 + 640) )
        UlBugCheckEx(1u, v61 + 608, (ULONG_PTR)"minio\\http\\sys\\sendresponse.h", 0x453u);
      v65 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v61 + 24) + 24LL) + 1088LL);
      if ( KeGetCurrentIrql() )
      {
        LOBYTE(v66) = 1;
        UlThreadPoolEnqueueWorkItem(0, v64, UlDestroyCapturedResponse, v66, v65, -1);
      }
      else
      {
        UxPodAttachThread(v65, v96);
        UlDestroyCapturedResponse(v64);
        UxPodDetachThread(v96);
      }
    }
  }
  if ( v75 && ConsumerAndApiVersion < 0 )
  {
    if ( ConsumerAndApiVersion != -1073741766 )
    {
      v67 = v84;
      if ( !v83[4] )
      {
        v61 = *(_QWORD *)(*(_QWORD *)(v89 + 8) + 328LL);
        if ( (*(_BYTE *)(v61 + 1760) & 0x20) != 0 )
        {
          LOWORD(v69) = v84;
          McTemplateK0xh_EtwWriteTransfer(v61 + 1688, HTTP_EVENT_COMPLETE_SEND_ERROR_LEGACY, &v100, v59, v69);
        }
      }
      if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
      {
        LOWORD(v70[0]) = v67;
        WPP_SF_diH(
          v61,
          80,
          WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids,
          (unsigned int)ConsumerAndApiVersion,
          v59,
          *(_QWORD *)v70);
      }
    }
  }
  else if ( ConsumerAndApiVersion == 259 )
  {
    goto LABEL_205;
  }
  v5->IoStatus.Status = ConsumerAndApiVersion;
  IofCompleteRequest(v5, 0);
LABEL_205:
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1033, 81, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, (unsigned int)ConsumerAndApiVersion);
  return (unsigned int)ConsumerAndApiVersion;
}

```

## disassembly

```asm
0x1400f1b08  mov     [rsp-8+arg_18], rbx
0x1400f1b0d  push    rbp
0x1400f1b0e  push    rsi
0x1400f1b0f  push    rdi
0x1400f1b10  push    r12
0x1400f1b12  push    r13
0x1400f1b14  push    r14
0x1400f1b16  push    r15
0x1400f1b18  lea     rbp, [rsp-4F0h]
0x1400f1b20  sub     rsp, 630h
0x1400f1b27  mov     rax, cs:__security_cookie
0x1400f1b2e  xor     rax, rsp
0x1400f1b31  mov     [rbp+520h+var_40], rax
0x1400f1b38  xorps   xmm0, xmm0
0x1400f1b3b  movzx   r12d, r8b
0x1400f1b3f  mov     r14, rdx
0x1400f1b42  mov     [rbp+520h+var_550], rcx
0x1400f1b46  mov     r13, rcx
0x1400f1b49  mov     [rbp+520h+var_59E], r12b
0x1400f1b4d  xor     edi, edi
0x1400f1b4f  lea     rcx, [rbp+520h+var_460]; void *
0x1400f1b56  xor     eax, eax
0x1400f1b58  mov     [rbp+520h+var_510], rdi
0x1400f1b5c  xor     edx, edx; Val
0x1400f1b5e  mov     [rbp+520h+var_518], rax
0x1400f1b62  mov     r8d, 238h; Size
0x1400f1b68  mov     esi, edi
0x1400f1b6a  movups  xmmword ptr [rbp+520h+var_548], xmm0
0x1400f1b6e  movups  [rbp+520h+var_538], xmm0
0x1400f1b72  movups  [rbp+520h+var_528], xmm0
0x1400f1b76  call    memset
0x1400f1b7b  xorps   xmm0, xmm0
0x1400f1b7e  mov     [rbp+520h+var_570], rdi
0x1400f1b82  xor     eax, eax
0x1400f1b84  mov     [rbp+520h+var_558], rdi
0x1400f1b88  xor     edx, edx; Val
0x1400f1b8a  mov     [rbp+520h+var_168], rax
0x1400f1b91  mov     r8d, 120h; Size
0x1400f1b97  mov     [rbp+520h+var_59D], dil
0x1400f1b9b  lea     rcx, [rbp+520h+var_160]; void *
0x1400f1ba2  mov     [rbp+520h+var_587+3], dil
0x1400f1ba6  movups  [rbp+520h+var_178], xmm0
0x1400f1bad  mov     dword ptr [rbp+520h+var_180], edi
0x1400f1bb3  call    memset
0x1400f1bb8  xor     edx, edx; Val
0x1400f1bba  mov     [rbp+520h+P], rdi
0x1400f1bbe  mov     r8d, 90h; Size
0x1400f1bc4  mov     [rbp+520h+var_587+2], dil
0x1400f1bc8  lea     rcx, [rbp+520h+var_4F0]; void *
0x1400f1bcc  call    memset
0x1400f1bd1  xorps   xmm0, xmm0
0x1400f1bd4  mov     [rbp+520h+var_590], rdi
0x1400f1bd8  mov     ebx, edi
0x1400f1bda  mov     word ptr [rbp+520h+var_587+7], di
0x1400f1bde  xor     edx, edx; Val
0x1400f1be0  mov     [rbp+520h+var_587+1], dil
0x1400f1be4  mov     r8d, 88h; Size
0x1400f1bea  mov     [rbp+520h+var_578], edi
0x1400f1bed  lea     rcx, [rbp+520h+var_220]; void *
0x1400f1bf4  mov     [rbp+520h+var_57C], ebx
0x1400f1bf7  movups  [rbp+520h+var_190], xmm0
0x1400f1bfe  mov     [rbp+520h+var_59B], dil
0x1400f1c02  mov     [rbp+520h+var_59C], dil
0x1400f1c06  mov     [rbp+520h+var_588], dil
0x1400f1c0a  mov     [rbp+520h+var_560], rdi
0x1400f1c0e  call    memset
0x1400f1c13  mov     [rbp+520h+var_587+4], dil
0x1400f1c17  mov     [rbp+520h+var_5A0], dil
0x1400f1c1b  mov     [rbp+520h+var_568], rdi
0x1400f1c1f  mov     [rbp+520h+var_587], dil
0x1400f1c23  mov     [rbp+520h+var_508], rdi
0x1400f1c27  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400f1c2e  jz      short loc_1400F1C51
0x1400f1c30  lea     edx, [rdi+47h]
0x1400f1c33  mov     [rsp+660h+var_638], r12d
0x1400f1c38  mov     ecx, 409h
0x1400f1c3d  mov     [rsp+660h+var_640], r14
0x1400f1c42  mov     r9, r13
0x1400f1c45  lea     r8, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids
0x1400f1c4c  call    WPP_SF_qqD
0x1400f1c51  mov     rcx, r13; Irp
0x1400f1c54  call    cs:__imp_IoIs32bitProcess
0x1400f1c5b  nop     dword ptr [rax+rax+00h]
0x1400f1c60  mov     rcx, [r14+30h]
0x1400f1c64  lea     r9, [rbp+520h+var_578]
0x1400f1c68  lea     r8, [rbp+520h+var_558]
0x1400f1c6c  mov     r15b, al
0x1400f1c6f  call    UlGetConsumerAndApiVersion
0x1400f1c74  xor     ecx, ecx
0x1400f1c76  mov     edi, eax
0x1400f1c78  test    eax, eax
0x1400f1c7a  js      loc_1400F27F4
0x1400f1c80  mov     ebx, [rbp+520h+var_578]
0x1400f1c83  lea     rax, [rbp+520h+var_587+7]
0x1400f1c87  mov     [rsp+660h+var_5B0], rax; __int64
0x1400f1c8f  mov     r9b, r12b
0x1400f1c92  mov     dl, [r13+40h]
0x1400f1c96  lea     rax, [rbp+520h+var_508]
0x1400f1c9a  mov     [rsp+660h+var_5B8], rax; __int64
0x1400f1ca2  mov     r8b, r15b
0x1400f1ca5  lea     rax, [rbp+520h+var_587]
0x1400f1ca9  mov     [rsp+660h+var_5C0], rax; __int64
0x1400f1cb1  lea     rax, [rbp+520h+var_587+1]
0x1400f1cb5  mov     [rsp+660h+var_5C8], rax; __int64
0x1400f1cbd  lea     rax, [rbp+520h+var_590]
0x1400f1cc1  mov     [rsp+660h+var_5D0], rax; __int64
0x1400f1cc9  lea     rax, [rbp+520h+var_587+2]
0x1400f1ccd  mov     [rsp+660h+var_5D8], rax; __int64
0x1400f1cd5  lea     rax, [rbp+520h+P]
0x1400f1cd9  mov     [rsp+660h+var_5E0], rax; __int64
0x1400f1ce1  lea     rax, [rbp+520h+var_180]
0x1400f1ce8  mov     [rsp+660h+var_5E8], rax; __int64
0x1400f1ced  lea     rax, [rbp+520h+var_220]
0x1400f1cf4  mov     [rsp+660h+var_5F8], rax; __int64
0x1400f1cf9  lea     rax, [rbp+520h+var_587+3]
0x1400f1cfd  mov     qword ptr [rsp+660h+var_600], rax; char
0x1400f1d02  lea     rax, [rbp+520h+var_570]
0x1400f1d06  mov     [rsp+660h+var_608], rax; __int64
0x1400f1d0b  lea     rax, [rbp+520h+var_4F0]
0x1400f1d0f  mov     [rsp+660h+var_610], rax; __int64
0x1400f1d14  lea     rax, [rbp+520h+var_460]
0x1400f1d1b  mov     [rsp+660h+var_618], rax; void *
0x1400f1d20  lea     rax, [rbp+520h+var_548]
0x1400f1d24  mov     [rsp+660h+var_620], rax; __int64
0x1400f1d29  mov     eax, [r14+10h]
0x1400f1d2d  mov     [rsp+660h+var_628], cl; char
0x1400f1d31  mov     rcx, r13; Irp
0x1400f1d34  mov     [rsp+660h+var_630], ebx; int
0x1400f1d38  mov     [rsp+660h+var_638], eax; int
0x1400f1d3c  mov     rax, [r14+20h]
0x1400f1d40  mov     [rsp+660h+var_640], rax; __int64
0x1400f1d45  call    UlParseHttpSendHttpResponseIoctls
0x1400f1d4a  mov     r14, [rbp+520h+var_570]
0x1400f1d4e  mov     edi, eax
0x1400f1d50  test    eax, eax
0x1400f1d52  js      loc_1400F238C
0x1400f1d58  test    r14, r14
0x1400f1d5b  jz      short loc_1400F1D65
0x1400f1d5d  movzx   eax, word ptr [r14+8]
0x1400f1d62  mov     [rbp+520h+var_57C], eax
0x1400f1d65  test    byte ptr [rbp+520h+var_528+8], 2
0x1400f1d69  jnz     short loc_1400F1DDB
0x1400f1d6b  mov     r15, qword ptr [rbp+520h+var_528]
0x1400f1d6f  mov     rax, [rbp+520h+var_558]
0x1400f1d73  mov     [rbp+520h+var_5A0], 1
0x1400f1d77  mov     [rbp+520h+var_568], r15
0x1400f1d7b  movups  xmm0, cs:UlEtwBaseOpaqueIdActivityGuid
0x1400f1d82  movdqu  [rbp+520h+var_190], xmm0
0x1400f1d8a  mov     qword ptr [rbp+520h+var_190], r15
0x1400f1d91  mov     rcx, [rax+8]
0x1400f1d95  mov     rcx, [rcx+148h]
0x1400f1d9c  test    r12b, r12b
0x1400f1d9f  jz      short loc_1400F1DC9
0x1400f1da1  test    byte ptr [rcx+6E0h], 4
0x1400f1da8  jz      short loc_1400F1DE2
0x1400f1daa  lea     rdx, HTTP_EVENT_RECEIVE_BODY_FROM_USERMODE_LEGACY
0x1400f1db1  lea     r8, [rbp+520h+var_190]
0x1400f1db8  mov     r9, r15
0x1400f1dbb  add     rcx, 698h
0x1400f1dc2  call    McTemplateK0x_EtwWriteTransfer
0x1400f1dc7  jmp     short loc_1400F1DE2
0x1400f1dc9  test    byte ptr [rcx+6E0h], 4
0x1400f1dd0  jz      short loc_1400F1DE2
0x1400f1dd2  lea     rdx, HTTP_EVENT_RECEIVE_RESPONSE_FROM_USERMODE_LEGACY
0x1400f1dd9  jmp     short loc_1400F1DB1
0x1400f1ddb  mov     [rbp+520h+var_5A0], sil
0x1400f1ddf  mov     r15, rsi
0x1400f1de2  mov     rdx, [rbp+520h+var_558]
0x1400f1de6  lea     r8, [rbp+520h+var_510]
0x1400f1dea  mov     rcx, qword ptr [rbp+520h+var_528]
0x1400f1dee  call    UlGetRequest
0x1400f1df3  mov     edi, eax
0x1400f1df5  test    eax, eax
0x1400f1df7  js      loc_1400F27EB
0x1400f1dfd  xor     edi, edi
0x1400f1dff  mov     [rbp+520h+var_59F], dil
0x1400f1e03  mov     rsi, [rbp+520h+var_510]
0x1400f1e07  lea     edx, [rdi+1]
0x1400f1e0a  test    byte ptr cs:xmmword_1401A2CA0+2, dl
0x1400f1e10  jz      short loc_1400F1E48
0x1400f1e12  mov     rax, [rsi+18h]
0x1400f1e16  lea     rcx, aResponse; "response"
0x1400f1e1d  test    r12b, r12b
0x1400f1e20  lea     r9, aEntityBody; "entity body"
0x1400f1e27  cmovz   r9, rcx
0x1400f1e2b  mov     rax, [rax+30h]
0x1400f1e2f  mov     qword ptr [rsp+660h+var_630], rax
0x1400f1e34  mov     eax, dword ptr [rbp+520h+var_528+8]
0x1400f1e37  mov     [rsp+660h+var_638], eax
0x1400f1e3b  mov     [rsp+660h+var_640], r15
0x1400f1e40  call    WPP_SF_siDi
0x1400f1e45  lea     edx, [rdi+1]
0x1400f1e48  test    r12b, r12b
0x1400f1e4b  jz      loc_1400F1F8C
0x1400f1e51  cmp     [rsi+9B8h], rdi
0x1400f1e58  jnz     short loc_1400F1E60
0x1400f1e5a  mov     byte ptr [rbp+520h+var_578], dil
0x1400f1e5e  jmp     short loc_1400F1EDE
0x1400f1e60  mov     [rbp+520h+var_578], edi
0x1400f1e63  call    cs:__imp_KeEnterCriticalRegion
0x1400f1e6a  nop     dword ptr [rax+rax+00h]
0x1400f1e6f  mov     rcx, [rsi+18h]
0x1400f1e73  mov     r12d, 240h
0x1400f1e79  add     rcx, r12
0x1400f1e7c  xor     edx, edx
0x1400f1e7e  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400f1e85  nop     dword ptr [rax+rax+00h]
0x1400f1e8a  mov     rax, [rsi+9D0h]
0x1400f1e91  xor     r15d, r15d
0x1400f1e94  test    rax, rax
0x1400f1e97  jz      short loc_1400F1EB6
0x1400f1e99  cmp     [rax+88h], r15d
0x1400f1ea0  jnz     short loc_1400F1EB6
0x1400f1ea2  lea     ecx, [r15+1]
0x1400f1ea6  movzx   edi, dil
0x1400f1eaa  cmp     [rax+100h], ecx
0x1400f1eb0  cmovz   edi, ecx
0x1400f1eb3  mov     [rbp+520h+var_578], edi
0x1400f1eb6  mov     rcx, [rsi+18h]
0x1400f1eba  xor     edx, edx
0x1400f1ebc  add     rcx, r12
0x1400f1ebf  call    cs:__imp_ExReleasePushLockSharedEx
0x1400f1ec6  nop     dword ptr [rax+rax+00h]
0x1400f1ecb  call    cs:__imp_KeLeaveCriticalRegion
0x1400f1ed2  nop     dword ptr [rax+rax+00h]
0x1400f1ed7  test    dil, dil
0x1400f1eda  jnz     short loc_1400F1F43
0x1400f1edc  xor     edi, edi
0x1400f1ede  cmp     [rsi+8A4h], edi
0x1400f1ee4  jnz     short loc_1400F1F45
0x1400f1ee6  mov     r10d, dword ptr [rbp+520h+var_528+8]
0x1400f1eea  test    r10b, 4
0x1400f1eee  jnz     short loc_1400F1F49
0x1400f1ef0  mov     edx, r10d
0x1400f1ef3  mov     rcx, rsi
0x1400f1ef6  call    UlAutomaticChunkingTransformationNeeded
0x1400f1efb  test    al, al
0x1400f1efd  jnz     short loc_1400F1F49
0x1400f1eff  mov     rcx, [rsi+18h]
0x1400f1f03  add     rcx, 3D0h
0x1400f1f0a  call    UxTpIsFastSendPossible
0x1400f1f0f  test    al, al
0x1400f1f11  jz      short loc_1400F1F45
0x1400f1f13  movzx   ecx, word ptr [rbp+520h+var_587+7]
0x1400f1f17  mov     r12d, 1
0x1400f1f1d  cmp     cx, r12w
0x1400f1f21  jnz     short loc_1400F1F45
0x1400f1f23  mov     r8, [rbp+520h+P]
0x1400f1f27  cmp     [r8], edi
0x1400f1f2a  jnz     short loc_1400F1F45
0x1400f1f2c  mov     eax, [r8+10h]
0x1400f1f30  sub     eax, r12d
0x1400f1f33  cmp     eax, 0FFFFh
0x1400f1f38  ja      short loc_1400F1F45
0x1400f1f3a  mov     r10d, dword ptr [rbp+520h+var_528+8]
0x1400f1f3e  mov     al, r12b
0x1400f1f41  jmp     short loc_1400F1F56
0x1400f1f43  xor     edi, edi
0x1400f1f45  mov     r10d, dword ptr [rbp+520h+var_528+8]
0x1400f1f49  movzx   ecx, word ptr [rbp+520h+var_587+7]
0x1400f1f4d  mov     al, dil
0x1400f1f50  mov     r12d, 1
0x1400f1f56  cmp     [rbp+520h+var_5A0], dil
0x1400f1f5a  jnz     short loc_1400F1F61
0x1400f1f5c  test    r12b, r10b
0x1400f1f5f  jz      short loc_1400F1F66
0x1400f1f61  mov     dl, r12b
0x1400f1f64  jmp     short loc_1400F1F69
0x1400f1f66  mov     dl, [rbp+520h+var_59F]
0x1400f1f69  test    al, al
0x1400f1f6b  jz      short loc_1400F1F7E
0x1400f1f6d  test    cx, cx
0x1400f1f70  jnz     loc_1400F20F8
0x1400f1f76  mov     al, dil
0x1400f1f79  jmp     loc_1400F20FB
0x1400f1f7e  mov     r12b, dil
0x1400f1f81  mov     r15b, dil
0x1400f1f84  mov     r14b, dil
0x1400f1f87  jmp     loc_1400F22AE
0x1400f1f8c  mov     r12b, dil
0x1400f1f8f  cmp     dword ptr [rbp+520h+var_538+8], edi
0x1400f1f92  jz      short loc_1400F1FA1
0x1400f1f94  mov     r12d, [rsi+898h]
0x1400f1f9b  shr     r12d, 1
0x1400f1f9e  and     r12b, dl
0x1400f1fa1  cmp     [rsi+9B8h], rdi
0x1400f1fa8  jnz     short loc_1400F1FAF
0x1400f1faa  mov     r15b, dil
0x1400f1fad  jmp     short loc_1400F1FEE
0x1400f1faf  test    byte ptr [rbp+520h+var_528+8], 10h
0x1400f1fb3  jnz     short loc_1400F1FAA
0x1400f1fb5  test    byte ptr [rbp+520h+var_528+8], 40h
0x1400f1fb9  jnz     short loc_1400F1FAA
0x1400f1fbb  cmp     bx, 2
0x1400f1fbf  jb      short loc_1400F1FCB
0x1400f1fc1  cmp     [r14+228h], di
0x1400f1fc9  ja      short loc_1400F1FAA
0x1400f1fcb  movzx   eax, word ptr [r14+8]
0x1400f1fd0  mov     ecx, 0C8h
0x1400f1fd5  cmp     ax, cx
  ... truncated ...
```
