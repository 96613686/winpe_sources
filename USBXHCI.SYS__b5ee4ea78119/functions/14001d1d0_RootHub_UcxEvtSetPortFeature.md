# RootHub_UcxEvtSetPortFeature

- ea: `0x14001d1d0`
- end: `0x14001e6b7`
- name: `RootHub_UcxEvtSetPortFeature`
- size: `5351`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400038c0`
- `0x14000c264`
- `0x140019454`
- `0x14001999c`
- `0x14001ac48`
- `0x14001d02c`
- `0x14001d118`
- `0x14001d1d0`
- `0x14001f830`
- `0x14001fb30`
- `0x140021830`
- `0x140021964`
- `0x14002b2c0`
- `0x140046070`
- `0x14004b624`
- `0x140059970`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14001d895`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14001d895`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001d874`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001d874`

## string_xrefs

- `0x14001dca1`: `Code Path Requires Passive Level`
- `0x14001d393`: `A register read returned all FFs. Controller is considered physically removed`

## pseudocode

```c
__int64 __fastcall RootHub_UcxEvtSetPortFeature(__int64 a1, __int64 a2)
{
  __int64 v3; // r14
  __int64 v4; // rcx
  __int64 v5; // r12
  __int16 v6; // ax
  __int64 v7; // rbp
  int v8; // edx
  int Ulong; // eax
  int v10; // edx
  __int64 v11; // rbx
  __int64 v12; // rax
  int v13; // edx
  unsigned int v14; // r11d
  unsigned int v15; // ebx
  unsigned int v16; // r8d
  int v17; // edi
  __int64 v18; // r13
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // edx
  int v22; // edi
  unsigned int v23; // edi
  char v24; // al
  int v25; // edx
  int v26; // edi
  int v27; // edi
  int v28; // edi
  int v29; // eax
  int v30; // edx
  int v31; // ebx
  unsigned int v32; // ebx
  char v33; // al
  int v34; // edx
  int v35; // r9d
  int v36; // edi
  int v37; // edi
  int v38; // edi
  int v39; // edi
  int v40; // edi
  int v41; // edi
  __int16 v42; // ax
  __int16 v43; // di
  _UNKNOWN **v44; // rdx
  int v45; // edi
  unsigned int v46; // ebx
  __int64 v47; // r8
  int v49; // eax
  int v50; // edx
  int v51; // ebx
  unsigned int v52; // ebx
  int v53; // edx
  int v54; // r8d
  int v55; // r9d
  int v56; // eax
  int v57; // edx
  int v58; // ebx
  unsigned int v59; // ebx
  int v60; // edi
  int v61; // eax
  int v62; // edx
  int v63; // ebx
  unsigned int v64; // ebx
  int v65; // eax
  int v66; // r9d
  int v67; // edx
  int v68; // edi
  unsigned int v69; // edi
  unsigned int v70; // eax
  char v71; // al
  int v72; // edx
  int v73; // edx
  int v74; // r8d
  int v75; // edi
  int v76; // edx
  int v77; // ebx
  unsigned int v78; // ebx
  int v79; // edx
  int v80; // ebx
  unsigned int v81; // ebx
  int v82; // edx
  int v83; // edi
  unsigned int v84; // ebx
  int v85; // edx
  int v86; // edi
  unsigned int v87; // edi
  int v88; // eax
  int v89; // edx
  int v90; // ebx
  unsigned int v91; // ebx
  int v92; // eax
  int v93; // edx
  int v94; // ebx
  unsigned int v95; // ebx
  int v96; // eax
  int v97; // edx
  int v98; // ebx
  unsigned int v99; // ebx
  int v100; // eax
  int v101; // eax
  int v102; // edx
  int v103; // edi
  int v104; // edi
  unsigned int v105; // edi
  char v106; // al
  int v107; // edx
  __int64 v108; // r8
  int v109; // eax
  unsigned int v110; // [rsp+70h] [rbp-88h]
  unsigned int v111; // [rsp+74h] [rbp-84h]
  __int64 v112; // [rsp+78h] [rbp-80h]
  __int64 v113; // [rsp+80h] [rbp-78h]
  __int128 v115; // [rsp+90h] [rbp-68h] BYREF
  __int128 v116; // [rsp+A0h] [rbp-58h]
  __int64 v117; // [rsp+B0h] [rbp-48h]

  v117 = 0;
  v115 = 0;
  v116 = 0;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006C130);
  v4 = *(_QWORD *)(v3 + 8);
  v5 = *(_QWORD *)(v4 + 88);
  if ( *(_BYTE *)(v4 + 1041) && KeGetCurrentIrql() )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sds(WPP_GLOBAL_Control->DeviceExtension, v53, v54, v55);
    if ( !KdRefreshDebuggerNotPresent() )
      __debugbreak();
  }
  v115 = 0;
  v117 = 0;
  v116 = 0;
  if ( !WdfClientVersionHigherThanFramework )
  {
    v6 = 40;
LABEL_4:
    LOWORD(v115) = v6;
    goto LABEL_5;
  }
  if ( (unsigned int)WdfStructureCount <= 0x33 )
  {
    v6 = -1;
    goto LABEL_4;
  }
  LOWORD(v115) = *(_WORD *)(WdfStructures + 408);
LABEL_5:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01033 + 2128))(
    WdfDriverGlobals,
    a2,
    &v115);
  v7 = *((_QWORD *)&v115 + 1);
  if ( !(unsigned __int8)Controller_IsControllerAccessible(*(_QWORD *)(v3 + 8)) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v8,
        11,
        124,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
    }
    goto LABEL_67;
  }
  Ulong = XilRegister_ReadUlong(v5, *(_QWORD *)(v3 + 32) + 4LL);
  if ( Ulong == -1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v10,
        11,
        125,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
    }
    v11 = *(_QWORD *)(v3 + 8);
    v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01033 + 1616))(
            WdfDriverGlobals,
            *(_QWORD *)v11,
            off_14006C2C0);
    if ( !*(_BYTE *)(v11 + 797) )
    {
      if ( (*(_DWORD *)(v12 + 28) & 0x10) != 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = 4;
          WPP_RECORDER_SF_(*(_QWORD *)(v11 + 72), v13, 4, 228, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
        }
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = 2;
          WPP_RECORDER_SF_(*(_QWORD *)(v11 + 72), v13, 4, 227, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
        }
        Controller_HwVerifierBreakIfEnabled(
          v11,
          0,
          0,
          64,
          (__int64)"A register read returned all FFs. Controller is considered physically removed",
          0,
          0);
      }
    }
    *(_BYTE *)(v11 + 797) = 1;
    Controller_ReportFatalError(v11, 16, 0, 0, 0, 0, 0);
LABEL_67:
    *(_DWORD *)(v7 + 4) = -1073713152;
    v47 = 3221225486LL;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
             WdfDriverGlobals,
             a2,
             v47);
  }
  if ( (Ulong & 1) == 0 )
  {
    v14 = *(unsigned __int8 *)(v7 + 132);
    v15 = *(unsigned __int8 *)(v7 + 133);
    v111 = v14;
    if ( *(_WORD *)(v7 + 128) != 803 || !*(_BYTE *)(v7 + 132) || v14 > *(_DWORD *)(v3 + 16) || *(_WORD *)(v7 + 134) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v73 = *(unsigned __int8 *)(v7 + 134);
        v66 = 127;
        v74 = *(unsigned __int8 *)(v7 + 131);
LABEL_115:
        WPP_RECORDER_SF_DDDDDDDD(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL), v73, v74, v66);
        goto LABEL_102;
      }
      goto LABEL_102;
    }
    v16 = v14 - 1;
    v17 = *(unsigned __int16 *)(v7 + 130);
    v19 = 120LL * (v14 - 1);
    v18 = *(_QWORD *)(v3 + 40) + 16LL * (v14 - 1);
    v112 = v19;
    LOBYTE(v19) = *(_BYTE *)(*(_QWORD *)(v3 + 48) + v19 + 13);
    v110 = v14 - 1;
    v20 = v18 + 4;
    v113 = v18 + 4;
    if ( (_BYTE)v19 != 2 )
    {
      if ( (_BYTE)v19 != 3 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_102;
        v66 = 183;
        v73 = *(unsigned __int8 *)(v7 + 134);
        v74 = *(unsigned __int8 *)(v7 + 131);
        goto LABEL_115;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = 4;
        WPP_RECORDER_SF_ddd(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v19,
          11,
          153,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
          v14,
          v17,
          v15);
        v14 = v111;
        v20 = v18 + 4;
        v16 = v110;
      }
      switch ( v17 )
      {
        case 27:
          goto LABEL_55;
        case 23:
LABEL_25:
          v22 = XilRegister_ReadUlong(v5, v20);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v21) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v21,
              11,
              165,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v22);
          }
          v23 = v15 | v22 & 0xFFFFFF00;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v21) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v21,
              11,
              166,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v23);
          }
          XilRegister_WriteUlong(v5, v18 + 4, v23);
          v24 = XilRegister_ReadUlong(v5, v18 + 4);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v25) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v25,
              11,
              167,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v24);
          }
          *(_BYTE *)(*(_QWORD *)(v3 + 48) + v112 + 21) = v15;
          goto LABEL_63;
        case 24:
          goto LABEL_106;
      }
      if ( v17 != 5 )
      {
        if ( v15 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_102;
          v66 = 154;
          goto LABEL_126;
        }
        v36 = v17 - 4;
        if ( !v36 )
        {
          RootHub_AcquireReadModifyWriteLock(v3, v16);
          v96 = XilRegister_ReadUlong(v5, v18);
          v98 = v96;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v97) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v97,
              11,
              155,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v96);
          }
          v99 = v98 & 0xE00C200 | 0x10;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v97) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v97,
              11,
              156,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v99);
          }
          XilRegister_WriteUlong(v5, v18, v99);
          RootHub_ReleaseReadModifyWriteLock(v3, v110);
          v33 = XilRegister_ReadUlong(v5, v18);
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_63;
          v35 = 157;
          goto LABEL_77;
        }
        v37 = v36 - 1;
        if ( v37 )
        {
          v38 = v37 - 3;
          if ( !v38 )
          {
            RootHub_AcquireReadModifyWriteLock(v3, v16);
            v92 = XilRegister_ReadUlong(v5, v18);
            v94 = v92;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v93) = 4;
              WPP_RECORDER_SF_D(
                *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                v93,
                11,
                161,
                (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                v92);
            }
            v95 = v94 & 0xE00C000 | 0x200;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v93) = 4;
              WPP_RECORDER_SF_D(
                *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                v93,
                11,
                162,
                (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                v95);
            }
            XilRegister_WriteUlong(v5, v18, v95);
            RootHub_ReleaseReadModifyWriteLock(v3, v110);
            v33 = XilRegister_ReadUlong(v5, v18);
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_63;
            v35 = 163;
            goto LABEL_77;
          }
          v39 = v38 - 15;
          if ( !v39 )
            goto LABEL_25;
          v40 = v39 - 1;
          if ( v40 )
          {
            v41 = v40 - 3;
            if ( !v41 )
            {
LABEL_55:
              if ( (unsigned __int8)v15 < 8u )
              {
                RootHub_AcquireReadModifyWriteLock(v3, v16);
                v42 = XilRegister_ReadUlong(v5, v18);
                v43 = v42;
                v44 = &WPP_RECORDER_INITIALIZED;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v44) = 4;
                  WPP_RECORDER_SF_D(
                    *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                    (_DWORD)v44,
                    11,
                    176,
                    (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                    v42);
                  v44 = &WPP_RECORDER_INITIALIZED;
                }
                v45 = v43 & 0xC200;
                if ( (*(_DWORD *)(*(_QWORD *)(v3 + 48) + v112 + 64) & 2) != 0 )
                  v46 = v45;
                else
                  v46 = v45 | ((v15 & 7) << 25);
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v44) = 4;
                  WPP_RECORDER_SF_D(
                    *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                    (_DWORD)v44,
                    11,
                    177,
                    (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                    v46);
                }
                XilRegister_WriteUlong(v5, v18, v46);
                RootHub_ReleaseReadModifyWriteLock(v3, v110);
                v33 = XilRegister_ReadUlong(v5, v18);
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  goto LABEL_63;
                v35 = 178;
                goto LABEL_77;
              }
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_102;
              v66 = 175;
              goto LABEL_126;
            }
            v60 = v41 - 1;
            if ( v60 )
            {
              if ( v60 != 2 )
              {
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  goto LABEL_102;
                v66 = 182;
                goto LABEL_126;
              }
              v88 = XilRegister_ReadUlong(v5, v20);
              v90 = v88;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v89) = 4;
                WPP_RECORDER_SF_D(
                  *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                  v89,
                  11,
                  179,
                  (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                  v88);
              }
              v91 = v90 | 0x10000;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v89) = 4;
                WPP_RECORDER_SF_D(
                  *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                  v89,
                  11,
                  180,
                  (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                  v91);
              }
              XilRegister_WriteUlong(v5, v113, v91);
              v33 = XilRegister_ReadUlong(v5, v113);
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_63;
              v35 = 181;
            }
            else
            {
              RootHub_AcquireReadModifyWriteLock(v3, v16);
              v61 = XilRegister_ReadUlong(v5, v18);
              v63 = v61;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v62) = 4;
                WPP_RECORDER_SF_D(
                  *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                  v62,
                  11,
                  158,
                  (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                  v61);
              }
              v64 = v63 & 0xE00C200 | 0x80000000;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v62) = 4;
                WPP_RECORDER_SF_D(
                  *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                  v62,
                  11,
                  159,
                  (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                  v64);
              }
              XilRegister_WriteUlong(v5, v18, v64);
              RootHub_ReleaseReadModifyWriteLock(v3, v110);
              v33 = XilRegister_ReadUlong(v5, v18);
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_63;
              v35 = 160;
            }
LABEL_77:
            LOBYTE(v34) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v34,
              11,
              v35,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v33);
LABEL_63:
            *(_DWORD *)(v7 + 4) = 0;
            v47 = 0;
            return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
                     WdfDriverGlobals,
                     a2,
                     v47);
          }
LABEL_106:
          v68 = XilRegister_ReadUlong(v5, v20);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v67) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v67,
              11,
              168,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v68);
          }
          v69 = v68 & 0xFFFF00FF;
          v70 = v69 | (v15 << 8);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v67) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v67,
              11,
              169,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v69);
            v70 = v69 | (v15 << 8);
          }
          XilRegister_WriteUlong(v5, v18 + 4, v70);
          v71 = XilRegister_ReadUlong(v5, v18 + 4);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v72) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v72,
              11,
              170,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v71);
          }
          *(_BYTE *)(*(_QWORD *)(v3 + 48) + v112 + 22) = v15;
          goto LABEL_63;
        }
LABEL_188:
        if ( (*(_DWORD *)(*(_QWORD *)(v3 + 8) + 736LL) & 0x80000) != 0 )
        {
          if ( v15 )
          {
            v100 = RootHub_ForceU0AndWait(v3, v14);
            goto LABEL_192;
          }
        }
        else if ( v15 )
        {
LABEL_195:
          RootHub_AcquireReadModifyWriteLock(v3, v110);
          if ( v15 == 3 )
            *(_BYTE *)(*(_QWORD *)(v3 + 48) + v112 + 18) = 0;
          v101 = XilRegister_ReadUlong(v5, v18);
          v103 = v101;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v102) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v102,
              11,
              172,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v101);
          }
          v104 = v103 & 0xE00C200;
          if ( v15 == 4 )
            v105 = v104 | 2;
          else
            v105 = (32 * (v15 & 0xF | 0x800)) | v104;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v102) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v102,
              11,
              173,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v105);
          }
          XilRegister_WriteUlong(v5, v18, v105);
          RootHub_ReleaseReadModifyWriteLock(v3, v110);
          v106 = XilRegister_ReadUlong(v5, v18);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v107) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v107,
              11,
              174,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v106);
          }
          if ( v15 != 3 )
            goto LABEL_63;
          if ( (*(_DWORD *)(*(_QWORD *)(v3 + 8) + 736LL) & 0x4000000) == 0 )
            goto LABEL_63;
          LOBYTE(v108) = 1;
          v109 = RootHub_WaitForPendingU3TransitionCompletion(v3, v111, v108);
          v47 = (unsigned int)v109;
          if ( v109 >= 0 )
            goto LABEL_63;
LABEL_103:
          *(_DWORD *)(v7 + 4) = -1073741820;
          return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
                   WdfDriverGlobals,
                   a2,
                   v47);
        }
        v100 = RootHub_WaitForPendingU3TransitionCompletion(v3, v14, 0);
LABEL_192:
        v47 = (unsigned int)v100;
        if ( v100 < 0 )
          goto LABEL_103;
        goto LABEL_195;
      }
      if ( v15 <= 5 )
        goto LABEL_188;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_102:
        v47 = 3221225473LL;
        goto LABEL_103;
      }
      v66 = 171;
LABEL_126:
      v73 = *(unsigned __int8 *)(v7 + 134);
      v74 = *(unsigned __int8 *)(v7 + 133);
      goto LABEL_115;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = 4;
      WPP_RECORDER_SF_ddd(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v19,
        11,
        128,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        v14,
        v17,
        v15);
      v14 = v111;
      v20 = v18 + 4;
      v16 = v110;
    }
    if ( v17 == 21 )
    {
      if ( v15 > 5 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_102;
        v66 = 144;
        goto LABEL_126;
      }
    }
    else
    {
      if ( v17 == 22 )
      {
        if ( v15 > 3 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_102;
          v66 = 148;
          goto LABEL_126;
        }
        if ( v15 == 3 )
          LOBYTE(v15) = 0;
        goto LABEL_147;
      }
      if ( v15 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_102;
        v66 = 129;
        goto LABEL_126;
      }
      v26 = v17 - 2;
      if ( !v26 )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v3 + 8) + 736LL) & 0x8000000) != 0 )
        {
          v65 = RootHub_ForceU0AndWait(v3, v14);
          v47 = (unsigned int)v65;
          if ( v65 < 0 )
            goto LABEL_103;
        }
        RootHub_AcquireReadModifyWriteLock(v3, v110);
        *(_BYTE *)(*(_QWORD *)(v3 + 48) + v112 + 18) = 0;
        v49 = XilRegister_ReadUlong(v5, v18);
        v51 = v49;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v50) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v50,
            11,
            137,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v49);
        }
        if ( ((v51 & 2) == 0 || (v51 & 0x1E0u) >= 0x60)
          && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v50) = 3;
          WPP_RECORDER_SF_(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v50,
            11,
            138,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
        }
        v52 = v51 & 0xE00C200 | 0x10060;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v50) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v50,
            11,
            139,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v52);
        }
        XilRegister_WriteUlong(v5, v18, v52);
        RootHub_ReleaseReadModifyWriteLock(v3, v110);
        v33 = XilRegister_ReadUlong(v5, v18);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_63;
        v35 = 140;
        goto LABEL_77;
      }
      v27 = v26 - 2;
      if ( !v27 )
      {
        RootHub_AcquireReadModifyWriteLock(v3, v16);
        if ( *(_BYTE *)(*(_QWORD *)(v3 + 48) + v112 + 20) )
        {
          v77 = XilRegister_ReadUlong(v5, v18 + 4);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v76) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v76,
              11,
              130,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v77);
          }
          v78 = v77 & 0xFFFE0007;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v76) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v76,
              11,
              131,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v78);
          }
          XilRegister_WriteUlong(v5, v18 + 4, v78);
          v80 = XilRegister_ReadUlong(v5, v18 + 12);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v79) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v79,
              11,
              132,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v80);
          }
          v81 = v80 & 0xFFFFC000;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v79) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v79,
              11,
              133,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v81);
          }
          XilRegister_WriteUlong(v5, v18 + 12, v81);
          *(_BYTE *)(*(_QWORD *)(v3 + 48) + v112 + 20) = 0;
        }
        v56 = XilRegister_ReadUlong(v5, v18);
        v58 = v56;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v57) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v57,
            11,
            134,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v56);
        }
        v59 = v58 & 0xE00C200 | 0x10;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v57) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v57,
            11,
            135,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v59);
        }
        XilRegister_WriteUlong(v5, v18, v59);
        RootHub_ReleaseReadModifyWriteLock(v3, v110);
        v33 = XilRegister_ReadUlong(v5, v18);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_63;
        v35 = 136;
        goto LABEL_77;
      }
      v28 = v27 - 4;
      if ( !v28 )
      {
        RootHub_AcquireReadModifyWriteLock(v3, v16);
        v29 = XilRegister_ReadUlong(v5, v18);
        v31 = v29;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v30) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v30,
            11,
            141,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v29);
        }
        v32 = v31 & 0xE00C000 | 0x200;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v30) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v30,
            11,
            142,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v32);
        }
        XilRegister_WriteUlong(v5, v18, v32);
        RootHub_ReleaseReadModifyWriteLock(v3, v110);
        v33 = XilRegister_ReadUlong(v5, v18);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_63;
        v35 = 143;
        goto LABEL_77;
      }
      v75 = v28 - 13;
      if ( v75 )
      {
        if ( v75 != 1 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_102;
          v66 = 152;
          goto LABEL_126;
        }
LABEL_147:
        RootHub_AcquireReadModifyWriteLock(v3, v16);
        v83 = XilRegister_ReadUlong(v5, v18);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v82) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v82,
            11,
            149,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v83);
        }
        v84 = v83 & 0xE000200 | ((v15 & 3) << 14);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v82) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v82,
            11,
            150,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v84);
        }
        XilRegister_WriteUlong(v5, v18, v84);
        RootHub_ReleaseReadModifyWriteLock(v3, v110);
        v33 = XilRegister_ReadUlong(v5, v18);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_63;
        v35 = 151;
        goto LABEL_77;
      }
    }
    v86 = XilRegister_ReadUlong(v5, v20);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v85) = 4;
      WPP_RECORDER_SF_D(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v85,
        11,
        145,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        v86);
    }
    v87 = (v15 << 28) | v86 & 0xFFFFFFF;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v85) = 4;
      WPP_RECORDER_SF_D(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v85,
        11,
        146,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        v87);
    }
    XilRegister_WriteUlong(v5, v18 + 4, v87);
    v33 = XilRegister_ReadUlong(v5, v18 + 4);
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_63;
    v35 = 147;
    goto LABEL_77;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_(
      *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
      v10,
      11,
      126,
      (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
  }
  *(_DWORD *)(v7 + 4) = -1073741807;
  v47 = 3221225666LL;
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
           WdfDriverGlobals,
           a2,
           v47);
}

```

## disassembly

```asm
0x14001d1d0  mov     r11, rsp
0x14001d1d3  mov     [r11+18h], rbx
0x14001d1d7  push    rbp
0x14001d1d8  push    rsi
0x14001d1d9  push    rdi
0x14001d1da  push    r12
0x14001d1dc  push    r13
0x14001d1de  push    r14
0x14001d1e0  push    r15
0x14001d1e2  sub     rsp, 0C0h
0x14001d1e9  mov     rax, cs:__security_cookie
0x14001d1f0  xor     rax, rsp
0x14001d1f3  mov     [rsp+0F8h+var_40], rax
0x14001d1fb  mov     r8, cs:off_14006C130
0x14001d202  xor     eax, eax
0x14001d204  mov     [r11-48h], rax
0x14001d208  xorps   xmm0, xmm0
0x14001d20b  mov     rax, cs:WdfFunctions_01033
0x14001d212  mov     rdi, rdx
0x14001d215  mov     [rsp+0F8h+var_70], rdx
0x14001d21d  mov     rdx, rcx
0x14001d220  mov     rcx, cs:WdfDriverGlobals
0x14001d227  movups  xmmword ptr [r11-68h], xmm0
0x14001d22c  movups  xmmword ptr [r11-58h], xmm0
0x14001d231  mov     rax, [rax+650h]
0x14001d238  call    _guard_dispatch_icall
0x14001d23d  xor     r13d, r13d
0x14001d240  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001d247  mov     r14, rax
0x14001d24a  mov     rcx, [rax+8]
0x14001d24e  mov     r12, [rcx+58h]
0x14001d252  cmp     [rcx+411h], r13b
0x14001d259  jnz     loc_14001D874
0x14001d25f  xor     eax, eax
0x14001d261  xorps   xmm0, xmm0
0x14001d264  cmp     cs:WdfClientVersionHigherThanFramework, r13b
0x14001d26b  movups  [rsp+0F8h+var_68], xmm0
0x14001d273  mov     [rsp+0F8h+var_48], rax
0x14001d27b  movups  [rsp+0F8h+var_58], xmm0
0x14001d283  jnz     loc_14001DCCF
0x14001d289  mov     eax, 28h ; '('
0x14001d28e  mov     word ptr [rsp+0F8h+var_68], ax
0x14001d296  mov     rax, cs:WdfFunctions_01033
0x14001d29d  lea     r8, [rsp+0F8h+var_68]
0x14001d2a5  mov     rcx, cs:WdfDriverGlobals
0x14001d2ac  mov     rdx, rdi
0x14001d2af  mov     rax, [rax+850h]
0x14001d2b6  call    _guard_dispatch_icall
0x14001d2bb  mov     rcx, [r14+8]
0x14001d2bf  mov     rbp, qword ptr [rsp+0F8h+var_68+8]
0x14001d2c7  call    Controller_IsControllerAccessible
0x14001d2cc  test    al, al
0x14001d2ce  jz      loc_14001D728
0x14001d2d4  mov     rdx, [r14+20h]
0x14001d2d8  mov     rcx, r12
0x14001d2db  add     rdx, 4
0x14001d2df  call    XilRegister_ReadUlong
0x14001d2e4  cmp     eax, 0FFFFFFFFh
0x14001d2e7  jnz     loc_14001D3BC
0x14001d2ed  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14001d2f4  jz      short loc_14001D322
0x14001d2f6  mov     rcx, [r14+8]
0x14001d2fa  lea     r15, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001d301  mov     r9d, 7Dh ; '}'
0x14001d307  mov     [rsp+0F8h+var_D8], r15
0x14001d30c  mov     dl, 2
0x14001d30e  mov     rcx, [rcx+48h]
0x14001d312  lea     r8d, [r9-72h]
0x14001d316  call    WPP_RECORDER_SF_
0x14001d31b  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001d322  mov     rbx, [r14+8]
0x14001d326  mov     rax, cs:WdfFunctions_01033
0x14001d32d  mov     r8, cs:off_14006C2C0
0x14001d334  mov     rcx, cs:WdfDriverGlobals
0x14001d33b  mov     rdx, [rbx]
0x14001d33e  mov     rax, [rax+650h]
0x14001d345  call    _guard_dispatch_icall
0x14001d34a  cmp     [rbx+31Dh], r13b
0x14001d351  jnz     loc_14001DD54
0x14001d357  mov     eax, [rax+1Ch]
0x14001d35a  test    al, 10h
0x14001d35c  jnz     loc_14001DD27
0x14001d362  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14001d369  jz      short loc_14001D38E
0x14001d36b  mov     rcx, [rbx+48h]
0x14001d36f  lea     rax, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14001d376  mov     r9d, 0E3h
0x14001d37c  mov     [rsp+0F8h+var_D8], rax
0x14001d381  mov     r8d, 4
0x14001d387  mov     dl, 2
0x14001d389  call    WPP_RECORDER_SF_
0x14001d38e  mov     [rsp+0F8h+var_C8], r13
0x14001d393  lea     rax, aARegisterReadR; "A register read returned all FFs. Contr"...
0x14001d39a  mov     [rsp+0F8h+var_D0], r13
0x14001d39f  mov     r9d, 40h ; '@'
0x14001d3a5  xor     r8d, r8d
0x14001d3a8  mov     [rsp+0F8h+var_D8], rax
0x14001d3ad  xor     edx, edx
0x14001d3af  mov     rcx, rbx
0x14001d3b2  call    Controller_HwVerifierBreakIfEnabled
0x14001d3b7  jmp     loc_14001DD54
0x14001d3bc  test    al, 1
0x14001d3be  jnz     loc_14001DD81
0x14001d3c4  movzx   ecx, byte ptr [rbp+80h]
0x14001d3cb  movzx   r11d, byte ptr [rbp+84h]
0x14001d3d3  movzx   ebx, byte ptr [rbp+85h]
0x14001d3da  mov     [rsp+0F8h+var_84], r11d
0x14001d3df  cmp     cl, 23h ; '#'
0x14001d3e2  jnz     loc_14001DC26
0x14001d3e8  cmp     byte ptr [rbp+81h], 3
0x14001d3ef  jnz     loc_14001DC26
0x14001d3f5  test    r11d, r11d
0x14001d3f8  jz      loc_14001DC26
0x14001d3fe  cmp     r11d, [r14+10h]
0x14001d402  ja      loc_14001DC26
0x14001d408  cmp     [rbp+86h], r13w
0x14001d410  jnz     loc_14001DC26
0x14001d416  mov     rax, [r14+30h]
0x14001d41a  lea     r8d, [r11-1]
0x14001d41e  movzx   edi, word ptr [rbp+82h]
0x14001d425  mov     edx, r8d
0x14001d428  imul    rdx, 78h ; 'x'
0x14001d42c  mov     r13d, r8d
0x14001d42f  shl     r13, 4
0x14001d433  add     r13, [r14+28h]
0x14001d437  mov     [rsp+0F8h+var_80], rdx
0x14001d43c  mov     dl, [rax+rdx+0Dh]
0x14001d440  mov     [rsp+0F8h+var_88], r8d
0x14001d445  lea     rcx, [r13+4]
0x14001d449  mov     [rsp+0F8h+var_78], rcx
0x14001d451  cmp     dl, 2
0x14001d454  jz      loc_14001D50C
0x14001d45a  cmp     dl, 3
0x14001d45d  jnz     loc_14001E656
0x14001d463  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001d46a  mov     esi, 0Bh
0x14001d46f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d476  lea     r15, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001d47d  jnz     loc_14001DACF
0x14001d483  cmp     edi, 1Bh
0x14001d486  jz      loc_14001D631
0x14001d48c  cmp     edi, 17h
0x14001d48f  jnz     loc_14001D5E1
0x14001d495  mov     rdx, rcx
0x14001d498  mov     rcx, r12
0x14001d49b  call    XilRegister_ReadUlong
0x14001d4a0  mov     edi, eax
0x14001d4a2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001d4a9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d4b0  jnz     loc_14001E5DD
0x14001d4b6  and     edi, 0FFFFFF00h
0x14001d4bc  or      edi, ebx
0x14001d4be  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x14001d4c5  jnz     loc_14001E60A
0x14001d4cb  mov     r8d, edi
0x14001d4ce  lea     rdx, [r13+4]
0x14001d4d2  mov     rcx, r12
0x14001d4d5  call    XilRegister_WriteUlong
0x14001d4da  lea     rdx, [r13+4]
0x14001d4de  mov     rcx, r12
0x14001d4e1  call    XilRegister_ReadUlong
0x14001d4e6  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001d4ed  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001d4f4  jnz     loc_14001E630
0x14001d4fa  mov     rax, [r14+30h]
0x14001d4fe  mov     rcx, [rsp+0F8h+var_80]
0x14001d503  mov     [rax+rcx+15h], bl
0x14001d507  jmp     loc_14001D6D0
0x14001d50c  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001d513  mov     esi, 0Bh
0x14001d518  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d51f  lea     r15, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001d526  jnz     loc_14001DA63
0x14001d52c  cmp     edi, 15h
0x14001d52f  jz      loc_14001E0D6
0x14001d535  cmp     edi, 16h
0x14001d538  jz      loc_14001DFEC
0x14001d53e  test    ebx, ebx
0x14001d540  jnz     loc_14001DB40
0x14001d546  sub     edi, 2
0x14001d549  jz      loc_14001D744
0x14001d54f  sub     edi, 2
0x14001d552  jz      loc_14001D8AF
0x14001d558  sub     edi, 4
0x14001d55b  jnz     loc_14001DE2A
0x14001d561  mov     edx, r8d
0x14001d564  mov     rcx, r14
0x14001d567  call    RootHub_AcquireReadModifyWriteLock
0x14001d56c  mov     rdx, r13
0x14001d56f  mov     rcx, r12
0x14001d572  call    XilRegister_ReadUlong
0x14001d577  mov     ebx, eax
0x14001d579  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001d580  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001d587  jnz     loc_14001DE54
0x14001d58d  and     ebx, 0E00C000h
0x14001d593  bts     ebx, 9
0x14001d597  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14001d59e  jnz     loc_14001DE7A
0x14001d5a4  mov     r8d, ebx
0x14001d5a7  mov     rdx, r13
0x14001d5aa  mov     rcx, r12
0x14001d5ad  call    XilRegister_WriteUlong
0x14001d5b2  mov     edx, [rsp+0F8h+var_88]
0x14001d5b6  mov     rcx, r14
0x14001d5b9  call    RootHub_ReleaseReadModifyWriteLock
0x14001d5be  mov     rdx, r13
0x14001d5c1  mov     rcx, r12
0x14001d5c4  call    XilRegister_ReadUlong
0x14001d5c9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14001d5d0  jz      loc_14001D6D0
0x14001d5d6  mov     r9d, 8Fh
0x14001d5dc  jmp     loc_14001D84D
0x14001d5e1  cmp     edi, 18h
0x14001d5e4  jz      loc_14001DB7E
0x14001d5ea  cmp     edi, 5
0x14001d5ed  jz      loc_14001DAA7
0x14001d5f3  test    ebx, ebx
0x14001d5f5  jnz     loc_14001E1A0
0x14001d5fb  sub     edi, 4
0x14001d5fe  jz      loc_14001E336
0x14001d604  sub     edi, 1
0x14001d607  jz      loc_14001E412
0x14001d60d  sub     edi, 3
0x14001d610  jz      loc_14001E27C
0x14001d616  sub     edi, 0Fh
0x14001d619  jz      loc_14001D495
0x14001d61f  sub     edi, 1
0x14001d622  jz      loc_14001DB7E
0x14001d628  sub     edi, 3
0x14001d62b  jnz     loc_14001D97C
0x14001d631  cmp     bl, 8
0x14001d634  jnb     loc_14001E3EF
0x14001d63a  mov     edx, r8d
0x14001d63d  mov     rcx, r14
0x14001d640  call    RootHub_AcquireReadModifyWriteLock
0x14001d645  mov     rdx, r13
0x14001d648  mov     rcx, r12
0x14001d64b  call    XilRegister_ReadUlong
0x14001d650  mov     edi, eax
0x14001d652  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001d659  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14001d660  jnz     loc_14001DB13
0x14001d666  mov     rax, [r14+30h]
0x14001d66a  and     edi, 0C200h
0x14001d670  mov     rcx, [rsp+0F8h+var_80]
0x14001d675  mov     ecx, [rax+rcx+40h]
0x14001d679  test    cl, 2
0x14001d67c  jnz     loc_14001D86D
0x14001d682  and     ebx, 7
0x14001d685  shl     ebx, 19h
0x14001d688  or      ebx, edi
0x14001d68a  cmp     cs:WPP_RECORDER_INITIALIZED, rdx; __annotation("TMF:",
0x14001d691  jnz     loc_14001DB58
0x14001d697  mov     r8d, ebx
0x14001d69a  mov     rdx, r13
0x14001d69d  mov     rcx, r12
0x14001d6a0  call    XilRegister_WriteUlong
0x14001d6a5  mov     edx, [rsp+0F8h+var_88]
0x14001d6a9  mov     rcx, r14
0x14001d6ac  call    RootHub_ReleaseReadModifyWriteLock
0x14001d6b1  mov     rdx, r13
0x14001d6b4  mov     rcx, r12
0x14001d6b7  call    XilRegister_ReadUlong
0x14001d6bc  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001d6c3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001d6ca  jnz     loc_14001E407
0x14001d6d0  mov     dword ptr [rbp+4], 0
0x14001d6d7  xor     r8d, r8d
0x14001d6da  mov     rax, cs:WdfFunctions_01033
0x14001d6e1  mov     rdx, [rsp+0F8h+var_70]
0x14001d6e9  mov     rcx, cs:WdfDriverGlobals
0x14001d6f0  mov     rax, [rax+838h]
0x14001d6f7  call    _guard_dispatch_icall
0x14001d6fc  mov     rcx, [rsp+0F8h+var_40]
0x14001d704  xor     rcx, rsp; StackCookie
0x14001d707  call    __security_check_cookie
0x14001d70c  mov     rbx, [rsp+0F8h+arg_10]
0x14001d714  add     rsp, 0C0h
0x14001d71b  pop     r15
0x14001d71d  pop     r14
0x14001d71f  pop     r13
0x14001d721  pop     r12
0x14001d723  pop     rdi
0x14001d724  pop     rsi
0x14001d725  pop     rbp
0x14001d726  retn
0x14001d728  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14001d72f  jnz     loc_14001DCFD
0x14001d735  mov     dword ptr [rbp+4], 0C0007000h
0x14001d73c  mov     r8d, 0C000000Eh
0x14001d742  jmp     short loc_14001D6DA
0x14001d744  mov     rax, [r14+8]
0x14001d748  mov     ecx, [rax+2E0h]
0x14001d74e  bt      rcx, 1Bh
0x14001d753  jb      loc_14001DA22
0x14001d759  mov     edi, [rsp+0F8h+var_88]
0x14001d75d  mov     rcx, r14
0x14001d760  mov     edx, edi
0x14001d762  call    RootHub_AcquireReadModifyWriteLock
  ... truncated ...
```
