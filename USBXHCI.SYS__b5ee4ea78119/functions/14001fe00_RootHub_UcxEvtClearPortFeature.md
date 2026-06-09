# RootHub_UcxEvtClearPortFeature

- ea: `0x14001fe00`
- end: `0x1400214d5`
- name: `RootHub_UcxEvtClearPortFeature`
- size: `5845`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400038c0`
- `0x14001999c`
- `0x14001ac48`
- `0x14001d02c`
- `0x14001d118`
- `0x14001f830`
- `0x14001fb30`
- `0x14001fe00`
- `0x140021830`
- `0x140021964`
- `0x14002b2c0`
- `0x14003b7d0`
- `0x140046070`
- `0x14004b624`
- `0x140059970`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14002045c`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14002045c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002043b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002043b`

## string_xrefs

- `0x1400208ac`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall RootHub_UcxEvtClearPortFeature(__int64 a1, __int64 a2)
{
  __int64 v3; // rbp
  __int64 v4; // rcx
  __int64 v5; // r15
  __int64 v6; // r14
  int v7; // edx
  int Ulong; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v12; // r11d
  int v13; // r8d
  unsigned int v14; // r12d
  int v15; // ebx
  __int64 v16; // r13
  unsigned int v17; // edx
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  int v24; // ebx
  int v25; // ebx
  int v26; // edx
  int v27; // ebx
  unsigned int v28; // ebx
  char v29; // al
  int v30; // edx
  int v31; // r9d
  int v32; // eax
  int v33; // eax
  int v34; // ebx
  _UNKNOWN **v35; // rdx
  unsigned int v36; // ebx
  char v37; // al
  int v38; // edx
  __int64 v39; // rdx
  unsigned __int16 v40; // ax
  int v41; // edx
  int v42; // ebx
  unsigned int v43; // ebx
  int v44; // ebx
  int v45; // ebx
  int v46; // ebx
  int v47; // ebx
  int v48; // ebx
  int v49; // ebx
  int v50; // ebx
  int v51; // edx
  int v52; // ebx
  unsigned int v53; // ebx
  int v54; // edx
  int v55; // r8d
  int v56; // r9d
  int v57; // edx
  int v58; // ebx
  unsigned int v59; // ebx
  int v60; // edx
  int v61; // ebx
  unsigned int v62; // ebx
  int v63; // edx
  int v64; // ebx
  unsigned int v65; // ebx
  int v66; // eax
  int v67; // ebx
  _UNKNOWN **v68; // rdx
  bool v69; // zf
  __int64 v70; // rbx
  __int64 v71; // rax
  int v72; // r9d
  int v73; // edx
  int v74; // ebx
  unsigned int v75; // ebx
  int v76; // eax
  int v77; // ebx
  int v78; // edx
  int v79; // ebx
  unsigned int v80; // ebx
  int v81; // r9d
  int v82; // edx
  int v83; // r8d
  int v84; // edx
  int v85; // ebx
  unsigned int v86; // ebx
  int v87; // edx
  int v88; // ebx
  unsigned int v89; // ebx
  int v90; // edx
  int v91; // ebx
  unsigned int v92; // ebx
  int v93; // eax
  int v94; // ebx
  _UNKNOWN **v95; // rdx
  __int64 v96; // r10
  unsigned int v97; // ebx
  int v98; // r9d
  __int64 v99; // rcx
  int v100; // edx
  int v101; // ebx
  unsigned int v102; // ebx
  __int64 v103; // r13
  int v104; // eax
  int v105; // edx
  int v106; // ebx
  unsigned int v107; // ebx
  int v108; // edx
  int v109; // ebx
  unsigned int v110; // ebx
  int v111; // edx
  int v112; // ebx
  unsigned int v113; // ebx
  unsigned int v114; // [rsp+70h] [rbp-88h]
  int v115; // [rsp+70h] [rbp-88h]
  int v116; // [rsp+70h] [rbp-88h]
  int v117; // [rsp+74h] [rbp-84h]
  __int64 v118; // [rsp+78h] [rbp-80h]
  __int128 v120; // [rsp+88h] [rbp-70h] BYREF
  __int128 v121; // [rsp+98h] [rbp-60h]
  __int64 v122; // [rsp+A8h] [rbp-50h]

  v122 = 0;
  v120 = 0;
  v121 = 0;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006C130);
  v4 = *(_QWORD *)(v3 + 8);
  v5 = *(_QWORD *)(v4 + 88);
  if ( *(_BYTE *)(v4 + 1041) && KeGetCurrentIrql() )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sds(WPP_GLOBAL_Control->DeviceExtension, v54, v55, v56);
    if ( !KdRefreshDebuggerNotPresent() )
      __debugbreak();
  }
  v120 = 0;
  v122 = 0;
  v121 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x33 )
      LOWORD(v120) = -1;
    else
      LOWORD(v120) = *(_WORD *)(WdfStructures + 408);
  }
  else
  {
    LOWORD(v120) = 40;
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01033 + 2128))(
    WdfDriverGlobals,
    a2,
    &v120);
  v6 = *((_QWORD *)&v120 + 1);
  if ( !(unsigned __int8)Controller_IsControllerAccessible(*(_QWORD *)(v3 + 8)) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v7,
        11,
        39,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
    }
    goto LABEL_9;
  }
  Ulong = XilRegister_ReadUlong(v5, *(_QWORD *)(v3 + 32) + 4LL);
  if ( Ulong == -1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v9,
        11,
        40,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
    }
    LOBYTE(v9) = 1;
    Controller_SetControllerGone(*(_QWORD *)(v3 + 8), v9);
LABEL_9:
    *(_DWORD *)(v6 + 4) = -1073713152;
    v10 = 3221225486LL;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
             WdfDriverGlobals,
             a2,
             v10);
  }
  if ( (Ulong & 1) == 0 )
  {
    v12 = *(unsigned __int8 *)(v6 + 132);
    v13 = *(unsigned __int8 *)(v6 + 133);
    v114 = v12;
    v117 = v13;
    if ( *(_WORD *)(v6 + 128) != 291 || !*(_BYTE *)(v6 + 132) || v12 > *(_DWORD *)(v3 + 16) || *(_WORD *)(v6 + 134) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v82 = *(unsigned __int8 *)(v6 + 134);
        v81 = 42;
        v83 = *(unsigned __int8 *)(v6 + 131);
        goto LABEL_207;
      }
      goto LABEL_84;
    }
    v14 = v12 - 1;
    v15 = *(unsigned __int16 *)(v6 + 130);
    v17 = v12 - 1;
    v16 = *(_QWORD *)(v3 + 40) + 16LL * (v12 - 1);
    v118 = 120LL * (v12 - 1);
    LOBYTE(v17) = *(_BYTE *)(*(_QWORD *)(v3 + 48) + v118 + 13);
    if ( (_BYTE)v17 == 2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = 4;
        WPP_RECORDER_SF_ddd(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v17,
          11,
          43,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
          v12,
          v15,
          v13);
        v12 = v114;
        v13 = v117;
      }
      if ( v15 == 22 )
      {
LABEL_169:
        if ( (unsigned __int8)v13 > 3u )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v81 = 57;
            goto LABEL_129;
          }
          goto LABEL_84;
        }
        RootHub_AcquireReadModifyWriteLock(v3, v14);
        v101 = XilRegister_ReadUlong(v5, v16);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v100) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v100,
            11,
            58,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v101);
        }
        v102 = v101 & 0xE000200;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v100) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v100,
            11,
            59,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v102);
        }
        XilRegister_WriteUlong(v5, v16, v102);
        RootHub_ReleaseReadModifyWriteLock(v3, v14);
        v29 = XilRegister_ReadUlong(v5, v16);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_54;
        v31 = 60;
LABEL_53:
        LOBYTE(v30) = 4;
        WPP_RECORDER_SF_D(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v30,
          11,
          v31,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
          v29);
LABEL_54:
        *(_DWORD *)(v6 + 4) = 0;
        v10 = 0;
        return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
                 WdfDriverGlobals,
                 a2,
                 v10);
      }
      if ( v13 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v81 = 44;
LABEL_129:
          v82 = *(unsigned __int8 *)(v6 + 134);
          v83 = *(unsigned __int8 *)(v6 + 133);
LABEL_207:
          WPP_RECORDER_SF_DDDDDDDD(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL), v82, v83, v81);
        }
LABEL_84:
        v10 = 3221225473LL;
        goto LABEL_85;
      }
      v18 = v15 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( !v19 )
        {
          v32 = RootHub_WaitForPendingU3TransitionCompletion(v3, v12, 0);
          v10 = (unsigned int)v32;
          if ( v32 >= 0 )
          {
            RootHub_AcquireReadModifyWriteLock(v3, v14);
            v33 = XilRegister_ReadUlong(v5, v16);
            v34 = v33;
            v35 = &WPP_RECORDER_INITIALIZED;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v35) = 4;
              WPP_RECORDER_SF_D(
                *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                (_DWORD)v35,
                11,
                50,
                (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                v33);
              v35 = &WPP_RECORDER_INITIALIZED;
            }
            if ( ((v34 & 2) == 0 || (v34 & 0x1E0) != 0x60 && (v34 & 0x1E0) != 0x1E0)
              && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v35) = 2;
              WPP_RECORDER_SF_(
                *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                (_DWORD)v35,
                11,
                51,
                (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
            }
            v36 = v34 & 0xE00C200 | 0x101E0;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v35) = 4;
              WPP_RECORDER_SF_D(
                *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                (_DWORD)v35,
                11,
                52,
                (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                v36);
            }
            XilRegister_WriteUlong(v5, v16, v36);
            RootHub_ReleaseReadModifyWriteLock(v3, v14);
            v37 = XilRegister_ReadUlong(v5, v16);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v38) = 4;
              WPP_RECORDER_SF_D(
                *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                v38,
                11,
                53,
                (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                v37);
            }
            v39 = *(_QWORD *)(v3 + 48);
            if ( *(int *)(v39 + v118 + 48) > 0 )
              v40 = *(_WORD *)(v39 + v118 + 52);
            else
              v40 = 50;
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01033 + 2552))(
              WdfDriverGlobals,
              *(_QWORD *)(v39 + v118 + 40),
              -10000LL * v40);
            goto LABEL_54;
          }
LABEL_85:
          *(_DWORD *)(v6 + 4) = -1073741820;
          return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
                   WdfDriverGlobals,
                   a2,
                   v10);
        }
        v20 = v19 - 6;
        if ( !v20 )
        {
          RootHub_AcquireReadModifyWriteLock(v3, v14);
          v91 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v90) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v90,
              11,
              54,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v91);
          }
          v92 = v91 & 0xE00C000;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v90) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v90,
              11,
              55,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v92);
          }
          XilRegister_WriteUlong(v5, v16, v92);
          RootHub_ReleaseReadModifyWriteLock(v3, v14);
          v29 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_54;
          v31 = 56;
          goto LABEL_53;
        }
        v21 = v20 - 8;
        if ( !v21 )
        {
          RootHub_AcquireReadModifyWriteLock(v3, v14);
          v42 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v41) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v41,
              11,
              61,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v42);
          }
          v43 = v42 & 0xE00C200 | 0x20000;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v41) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v41,
              11,
              62,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v43);
          }
          XilRegister_WriteUlong(v5, v16, v43);
          RootHub_ReleaseReadModifyWriteLock(v3, v14);
          v29 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_54;
          v31 = 63;
          goto LABEL_53;
        }
        v22 = v21 - 1;
        if ( !v22 )
        {
          RootHub_AcquireReadModifyWriteLock(v3, v14);
          v88 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v87) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v87,
              11,
              67,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v88);
          }
          v89 = v88 & 0xE00C200 | 0x40000;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v87) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v87,
              11,
              68,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v89);
          }
          XilRegister_WriteUlong(v5, v16, v89);
          RootHub_ReleaseReadModifyWriteLock(v3, v14);
          v29 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_54;
          v31 = 69;
          goto LABEL_53;
        }
        v23 = v22 - 1;
        if ( !v23 )
        {
          RootHub_AcquireReadModifyWriteLock(v3, v14);
          v58 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v57) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v57,
              11,
              70,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v58);
          }
          v59 = v58 & 0xE00C200 | 0x400000;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v57) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v57,
              11,
              71,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v59);
          }
          XilRegister_WriteUlong(v5, v16, v59);
          RootHub_ReleaseReadModifyWriteLock(v3, v14);
          v29 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_54;
          v31 = 72;
          goto LABEL_53;
        }
        v24 = v23 - 1;
        if ( !v24 )
        {
          RootHub_AcquireReadModifyWriteLock(v3, v14);
          v85 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v84) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v84,
              11,
              73,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v85);
          }
          v86 = v85 & 0xE00C200 | 0x100000;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v84) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v84,
              11,
              74,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v86);
          }
          XilRegister_WriteUlong(v5, v16, v86);
          RootHub_ReleaseReadModifyWriteLock(v3, v14);
          v29 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_54;
          v31 = 75;
          goto LABEL_53;
        }
        v25 = v24 - 1;
        if ( !v25 )
        {
          RootHub_AcquireReadModifyWriteLock(v3, v14);
          v27 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v26) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v26,
              11,
              64,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v27);
          }
          v28 = v27 & 0xE00C200 | 0x200000;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v26) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v26,
              11,
              65,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v28);
          }
          XilRegister_WriteUlong(v5, v16, v28);
          RootHub_ReleaseReadModifyWriteLock(v3, v14);
          v29 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_54;
          v31 = 66;
          goto LABEL_53;
        }
        if ( v25 != 2 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v81 = 76;
            goto LABEL_129;
          }
          goto LABEL_84;
        }
        goto LABEL_169;
      }
      RootHub_AcquireReadModifyWriteLock(v3, v14);
      v93 = XilRegister_ReadUlong(v5, v16);
      v94 = v93;
      v95 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v95) = 4;
        WPP_RECORDER_SF_D(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          (_DWORD)v95,
          11,
          45,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
          v93);
        v95 = &WPP_RECORDER_INITIALIZED;
      }
      v96 = *(_QWORD *)(v3 + 8);
      if ( (*(_DWORD *)(v96 + 736) & 0x2000000) != 0 )
      {
        if ( ((v94 & 2) == 0 || (v94 & 0x1E0u) >= 0x60)
          && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v95) = 3;
          WPP_RECORDER_SF_(
            *(_QWORD *)(v96 + 72),
            (_DWORD)v95,
            11,
            46,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
        }
        v97 = v94 & 0xE00C200 | 0x10060;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_167;
        v98 = 47;
        v99 = *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL);
      }
      else
      {
        v97 = v94 & 0xE00C200 | 2;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_167:
          XilRegister_WriteUlong(v5, v16, v97);
          RootHub_ReleaseReadModifyWriteLock(v3, v14);
          v29 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_54;
          v31 = 49;
          goto LABEL_53;
        }
        v99 = *(_QWORD *)(v96 + 72);
        v98 = 48;
      }
      LOBYTE(v95) = 4;
      WPP_RECORDER_SF_D(v99, (_DWORD)v95, 11, v98, (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids, v97);
      goto LABEL_167;
    }
    if ( (_BYTE)v17 != 3 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v81 = 106;
        v82 = *(unsigned __int8 *)(v6 + 134);
        v83 = *(unsigned __int8 *)(v6 + 131);
        goto LABEL_207;
      }
      goto LABEL_84;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = 4;
      WPP_RECORDER_SF_ddd(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v17,
        11,
        77,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        v12,
        v15,
        v13);
      LOBYTE(v13) = v117;
    }
    if ( (_BYTE)v13 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v81 = 78;
        goto LABEL_129;
      }
      goto LABEL_84;
    }
    v44 = v15 - 8;
    if ( !v44 )
    {
      RootHub_AcquireReadModifyWriteLock(v3, v14);
      v112 = XilRegister_ReadUlong(v5, v16);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v111) = 4;
        WPP_RECORDER_SF_D(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v111,
          11,
          79,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
          v112);
      }
      v113 = v112 & 0xE00C000;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v111) = 4;
        WPP_RECORDER_SF_D(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v111,
          11,
          80,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
          v113);
      }
      XilRegister_WriteUlong(v5, v16, v113);
      RootHub_ReleaseReadModifyWriteLock(v3, v14);
      v29 = XilRegister_ReadUlong(v5, v16);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_54;
      v31 = 81;
      goto LABEL_53;
    }
    v45 = v44 - 8;
    if ( v45 )
    {
      v46 = v45 - 3;
      if ( !v46 )
      {
        RootHub_AcquireReadModifyWriteLock(v3, v14);
        v61 = XilRegister_ReadUlong(v5, v16);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v60) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v60,
            11,
            89,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v61);
        }
        v62 = v61 & 0xE00C200 | 0x100000;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v60) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v60,
            11,
            90,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v62);
        }
        XilRegister_WriteUlong(v5, v16, v62);
        RootHub_ReleaseReadModifyWriteLock(v3, v14);
        v29 = XilRegister_ReadUlong(v5, v16);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_54;
        v31 = 91;
        goto LABEL_53;
      }
      v47 = v46 - 1;
      if ( !v47 )
      {
        RootHub_AcquireReadModifyWriteLock(v3, v14);
        v79 = XilRegister_ReadUlong(v5, v16);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v78) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v78,
            11,
            86,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v79);
        }
        v80 = v79 & 0xE00C200 | 0x200000;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v78) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v78,
            11,
            87,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v80);
        }
        XilRegister_WriteUlong(v5, v16, v80);
        RootHub_ReleaseReadModifyWriteLock(v3, v14);
        v29 = XilRegister_ReadUlong(v5, v16);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_54;
        v31 = 88;
        goto LABEL_53;
      }
      v48 = v47 - 5;
      if ( v48 )
      {
        v49 = v48 - 1;
        if ( v49 )
        {
          v50 = v49 - 3;
          if ( v50 )
          {
            if ( v50 != 1 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v81 = 105;
                goto LABEL_129;
              }
              goto LABEL_84;
            }
            v103 = v16 + 4;
            v104 = XilRegister_ReadUlong(v5, v103);
            v106 = v104;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v105) = 4;
              WPP_RECORDER_SF_D(
                *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                v105,
                11,
                102,
                (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                v104);
            }
            v107 = v106 & 0xFFFEFFFF;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v105) = 4;
              WPP_RECORDER_SF_D(
                *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                v105,
                11,
                103,
                (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                v107);
            }
            XilRegister_WriteUlong(v5, v103, v107);
            v29 = XilRegister_ReadUlong(v5, v103);
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_54;
            v31 = 104;
          }
          else
          {
            RootHub_AcquireReadModifyWriteLock(v3, v14);
            v52 = XilRegister_ReadUlong(v5, v16);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v51) = 4;
              WPP_RECORDER_SF_D(
                *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                v51,
                11,
                99,
                (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                v52);
            }
            v53 = v52 & 0xE00C200 | 0x80000;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v51) = 4;
              WPP_RECORDER_SF_D(
                *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                v51,
                11,
                100,
                (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                v53);
            }
            XilRegister_WriteUlong(v5, v16, v53);
            RootHub_ReleaseReadModifyWriteLock(v3, v14);
            v29 = XilRegister_ReadUlong(v5, v16);
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_54;
            v31 = 101;
          }
        }
        else
        {
          RootHub_AcquireReadModifyWriteLock(v3, v14);
          v109 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v108) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v108,
              11,
              96,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v109);
          }
          v110 = v109 & 0xE00C200 | 0x800000;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v108) = 4;
            WPP_RECORDER_SF_D(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v108,
              11,
              97,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
              v110);
          }
          XilRegister_WriteUlong(v5, v16, v110);
          RootHub_ReleaseReadModifyWriteLock(v3, v14);
          v29 = XilRegister_ReadUlong(v5, v16);
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_54;
          v31 = 98;
        }
        goto LABEL_53;
      }
      RootHub_AcquireReadModifyWriteLock(v3, v14);
      v74 = XilRegister_ReadUlong(v5, v16);
      v116 = v74;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v73) = 4;
        WPP_RECORDER_SF_D(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v73,
          11,
          92,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
          v74);
      }
      v75 = v74 & 0xE00C200 | 0x400000;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v73) = 4;
        WPP_RECORDER_SF_D(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v73,
          11,
          93,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
          v75);
      }
      XilRegister_WriteUlong(v5, v16, v75);
      RootHub_ReleaseReadModifyWriteLock(v3, v14);
      v76 = XilRegister_ReadUlong(v5, v16);
      v77 = v76;
      v68 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v68) = 4;
        WPP_RECORDER_SF_D(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          (_DWORD)v68,
          11,
          94,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
          v76);
        v68 = &WPP_RECORDER_INITIALIZED;
      }
      if ( (*(_DWORD *)(*(_QWORD *)(v3 + 8) + 744LL) & 0x1000000) == 0 )
        goto LABEL_54;
      v69 = v116 == v77;
      v70 = 120LL * v14;
      v71 = *(_QWORD *)(v3 + 48);
      if ( v69 )
      {
        ++*(_DWORD *)(v118 + v71 + 112);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v72 = 95;
LABEL_102:
          LOBYTE(v68) = 2;
          WPP_RECORDER_SF_(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            (_DWORD)v68,
            11,
            v72,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
        }
LABEL_196:
        if ( *(_DWORD *)(*(_QWORD *)(v3 + 48) + v70 + 112) == 10 )
          Controller_ReportFatalError(*(_QWORD *)(v3 + 8), 64, 4144, 0, 0, 0, 0);
        goto LABEL_54;
      }
    }
    else
    {
      RootHub_AcquireReadModifyWriteLock(v3, v14);
      v64 = XilRegister_ReadUlong(v5, v16);
      v115 = v64;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v63) = 4;
        WPP_RECORDER_SF_D(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v63,
          11,
          82,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
          v64);
      }
      v65 = v64 & 0xE00C200 | 0x20000;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v63) = 4;
        WPP_RECORDER_SF_D(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v63,
          11,
          83,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
          v65);
      }
      XilRegister_WriteUlong(v5, v16, v65);
      RootHub_ReleaseReadModifyWriteLock(v3, v14);
      v66 = XilRegister_ReadUlong(v5, v16);
      v67 = v66;
      v68 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v68) = 4;
        WPP_RECORDER_SF_D(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          (_DWORD)v68,
          11,
          84,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
          v66);
        v68 = &WPP_RECORDER_INITIALIZED;
      }
      if ( (*(_DWORD *)(*(_QWORD *)(v3 + 8) + 744LL) & 0x1000000) == 0 )
        goto LABEL_54;
      v69 = v115 == v67;
      v70 = 120LL * v14;
      v71 = *(_QWORD *)(v3 + 48);
      if ( v69 )
      {
        ++*(_DWORD *)(v118 + v71 + 112);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_196;
        v72 = 85;
        goto LABEL_102;
      }
    }
    *(_DWORD *)(v70 + v71 + 112) = 0;
    goto LABEL_196;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_(
      *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
      v9,
      11,
      41,
      (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
  }
  *(_DWORD *)(v6 + 4) = -1073741807;
  v10 = 3221225666LL;
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
           WdfDriverGlobals,
           a2,
           v10);
}

```

## disassembly

```asm
0x14001fe00  mov     r11, rsp
0x14001fe03  mov     [r11+18h], rbx
0x14001fe07  push    rbp
0x14001fe08  push    rsi
0x14001fe09  push    rdi
0x14001fe0a  push    r12
0x14001fe0c  push    r13
0x14001fe0e  push    r14
0x14001fe10  push    r15
0x14001fe12  sub     rsp, 0C0h
0x14001fe19  mov     rax, cs:__security_cookie
0x14001fe20  xor     rax, rsp
0x14001fe23  mov     [rsp+0F8h+var_48], rax
0x14001fe2b  mov     r8, cs:off_14006C130
0x14001fe32  xor     eax, eax
0x14001fe34  mov     [r11-50h], rax
0x14001fe38  xorps   xmm0, xmm0
0x14001fe3b  mov     rax, cs:WdfFunctions_01033
0x14001fe42  mov     rbx, rdx
0x14001fe45  mov     [rsp+0F8h+var_78], rdx
0x14001fe4d  mov     rdx, rcx
0x14001fe50  mov     rcx, cs:WdfDriverGlobals
0x14001fe57  movups  xmmword ptr [r11-70h], xmm0
0x14001fe5c  movups  xmmword ptr [r11-60h], xmm0
0x14001fe61  mov     rax, [rax+650h]
0x14001fe68  call    _guard_dispatch_icall
0x14001fe6d  xor     edi, edi
0x14001fe6f  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001fe76  mov     rbp, rax
0x14001fe79  mov     rcx, [rax+8]
0x14001fe7d  mov     r15, [rcx+58h]
0x14001fe81  cmp     [rcx+411h], dil
0x14001fe88  jnz     loc_14002043B
0x14001fe8e  xor     eax, eax
0x14001fe90  xorps   xmm0, xmm0
0x14001fe93  cmp     cs:WdfClientVersionHigherThanFramework, dil
0x14001fe9a  movups  [rsp+0F8h+var_70], xmm0
0x14001fea2  mov     [rsp+0F8h+var_50], rax
0x14001feaa  lea     r12d, [rax+28h]
0x14001feae  movups  [rsp+0F8h+var_60], xmm0
0x14001feb6  jnz     loc_1400208DA
0x14001febc  mov     word ptr [rsp+0F8h+var_70], r12w
0x14001fec5  mov     rax, cs:WdfFunctions_01033
0x14001fecc  lea     r8, [rsp+0F8h+var_70]
0x14001fed4  mov     rcx, cs:WdfDriverGlobals
0x14001fedb  mov     rdx, rbx
0x14001fede  mov     rax, [rax+850h]
0x14001fee5  call    _guard_dispatch_icall
0x14001feea  mov     rcx, [rbp+8]
0x14001feee  mov     r14, qword ptr [rsp+0F8h+var_70+8]
0x14001fef6  call    Controller_IsControllerAccessible
0x14001fefb  test    al, al
0x14001fefd  jz      loc_140020910
0x14001ff03  mov     rdx, [rbp+20h]
0x14001ff07  mov     rcx, r15
0x14001ff0a  add     rdx, 4
0x14001ff0e  call    XilRegister_ReadUlong
0x14001ff13  cmp     eax, 0FFFFFFFFh
0x14001ff16  jnz     short loc_14001FF66
0x14001ff18  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14001ff1f  jnz     loc_140020947
0x14001ff25  mov     rcx, [rbp+8]
0x14001ff29  mov     dl, 1
0x14001ff2b  call    Controller_SetControllerGone
0x14001ff30  mov     dword ptr [r14+4], 0C0007000h
0x14001ff38  mov     r8d, 0C000000Eh
0x14001ff3e  mov     rax, cs:WdfFunctions_01033
0x14001ff45  mov     rdx, [rsp+0F8h+var_78]
0x14001ff4d  mov     rcx, cs:WdfDriverGlobals
0x14001ff54  mov     rax, [rax+838h]
0x14001ff5b  call    _guard_dispatch_icall
0x14001ff60  jmp     loc_1400214AA
0x14001ff66  test    al, 1
0x14001ff68  jnz     loc_140020970
0x14001ff6e  movzx   ecx, byte ptr [r14+80h]
0x14001ff76  movzx   r11d, byte ptr [r14+84h]
0x14001ff7e  movzx   r8d, byte ptr [r14+85h]
0x14001ff86  mov     [rsp+0F8h+var_88], r11d
0x14001ff8b  mov     [rsp+0F8h+var_84], r8d
0x14001ff90  cmp     cl, 23h ; '#'
0x14001ff93  jnz     loc_140020597
0x14001ff99  cmp     byte ptr [r14+81h], 1
0x14001ffa1  jnz     loc_140020597
0x14001ffa7  test    r11d, r11d
0x14001ffaa  jz      loc_140020597
0x14001ffb0  cmp     r11d, [rbp+10h]
0x14001ffb4  ja      loc_140020597
0x14001ffba  cmp     [r14+86h], di
0x14001ffc2  jnz     loc_140020597
0x14001ffc8  mov     rax, [rbp+30h]
0x14001ffcc  lea     r12d, [r11-1]
0x14001ffd0  movzx   ebx, word ptr [r14+82h]
0x14001ffd8  mov     edx, r12d
0x14001ffdb  imul    rcx, rdx, 78h ; 'x'
0x14001ffdf  mov     r13d, r12d
0x14001ffe2  shl     r13, 4
0x14001ffe6  add     r13, [rbp+28h]
0x14001ffea  mov     [rsp+0F8h+var_80], rcx
0x14001ffef  mov     dl, [rax+rcx+0Dh]
0x14001fff3  cmp     dl, 2
0x14001fff6  jnz     loc_14002031E
0x14001fffc  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140020003  mov     edi, 0Bh
0x140020008  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002000f  lea     rsi, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x140020016  jnz     loc_14002063D
0x14002001c  cmp     ebx, 16h
0x14002001f  jz      loc_140020E1C
0x140020025  test    r8d, r8d
0x140020028  jnz     loc_1400209B1
0x14002002e  sub     ebx, 1
0x140020031  jz      loc_140020CE7
0x140020037  sub     ebx, 1
0x14002003a  jz      loc_140020119
0x140020040  sub     ebx, 6
0x140020043  jz      loc_140020BE3
0x140020049  sub     ebx, 8
0x14002004c  jz      loc_140020259
0x140020052  sub     ebx, 1
0x140020055  jz      loc_140020B1C
0x14002005b  sub     ebx, 1
0x14002005e  jz      loc_140020476
0x140020064  sub     ebx, 1
0x140020067  jz      loc_140020A55
0x14002006d  sub     ebx, 1
0x140020070  jnz     loc_140020A34
0x140020076  mov     edx, r12d
0x140020079  mov     rcx, rbp
0x14002007c  call    RootHub_AcquireReadModifyWriteLock
0x140020081  mov     rdx, r13
0x140020084  mov     rcx, r15
0x140020087  call    XilRegister_ReadUlong
0x14002008c  mov     ebx, eax
0x14002008e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140020095  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002009c  jnz     loc_14002056A
0x1400200a2  and     ebx, 0E00C200h
0x1400200a8  bts     ebx, 15h
0x1400200ac  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x1400200b3  jz      short loc_1400200D6
0x1400200b5  mov     rcx, [rbp+8]
0x1400200b9  mov     r9d, 41h ; 'A'
0x1400200bf  mov     dword ptr [rsp+0F8h+var_D0], ebx
0x1400200c3  mov     r8d, edi
0x1400200c6  mov     dl, 4
0x1400200c8  mov     [rsp+0F8h+var_D8], rsi
0x1400200cd  mov     rcx, [rcx+48h]
0x1400200d1  call    WPP_RECORDER_SF_D
0x1400200d6  mov     r8d, ebx
0x1400200d9  mov     rdx, r13
0x1400200dc  mov     rcx, r15
0x1400200df  call    XilRegister_WriteUlong
0x1400200e4  mov     edx, r12d
0x1400200e7  mov     rcx, rbp
0x1400200ea  call    RootHub_ReleaseReadModifyWriteLock
0x1400200ef  mov     rdx, r13
0x1400200f2  mov     rcx, r15
0x1400200f5  call    XilRegister_ReadUlong
0x1400200fa  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140020101  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140020108  jz      loc_14002030E
0x14002010e  mov     r9d, 42h ; 'B'
0x140020114  jmp     loc_1400202F3
0x140020119  xor     r8d, r8d
0x14002011c  mov     edx, r11d
0x14002011f  mov     rcx, rbp
0x140020122  call    RootHub_WaitForPendingU3TransitionCompletion
0x140020127  mov     r8d, eax
0x14002012a  test    eax, eax
0x14002012c  js      loc_1400205AA
0x140020132  mov     edx, r12d
0x140020135  mov     rcx, rbp
0x140020138  call    RootHub_AcquireReadModifyWriteLock
0x14002013d  mov     rdx, r13
0x140020140  mov     rcx, r15
0x140020143  call    XilRegister_ReadUlong
0x140020148  mov     ebx, eax
0x14002014a  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140020151  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140020158  jz      short loc_140020182
0x14002015a  mov     rcx, [rbp+8]
0x14002015e  mov     r9d, 32h ; '2'
0x140020164  mov     dword ptr [rsp+0F8h+var_D0], eax
0x140020168  mov     r8d, edi
0x14002016b  mov     dl, 4
0x14002016d  mov     [rsp+0F8h+var_D8], rsi
0x140020172  mov     rcx, [rcx+48h]
0x140020176  call    WPP_RECORDER_SF_D
0x14002017b  lea     rdx, WPP_RECORDER_INITIALIZED
0x140020182  test    bl, 2
0x140020185  jz      loc_140020CAE
0x14002018b  mov     eax, ebx
0x14002018d  mov     ecx, 1E0h
0x140020192  and     eax, ecx
0x140020194  cmp     eax, 60h ; '`'
0x140020197  jnz     loc_140020CA6
0x14002019d  and     ebx, 0E00C200h
0x1400201a3  or      ebx, 101E0h
0x1400201a9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400201b0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400201b7  jnz     loc_140020415
0x1400201bd  mov     r8d, ebx
0x1400201c0  mov     rdx, r13
0x1400201c3  mov     rcx, r15
0x1400201c6  call    XilRegister_WriteUlong
0x1400201cb  mov     edx, r12d
0x1400201ce  mov     rcx, rbp
0x1400201d1  call    RootHub_ReleaseReadModifyWriteLock
0x1400201d6  mov     rdx, r13
0x1400201d9  mov     rcx, r15
0x1400201dc  call    XilRegister_ReadUlong
0x1400201e1  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400201e8  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400201ef  jz      short loc_140020212
0x1400201f1  mov     rcx, [rbp+8]
0x1400201f5  mov     r9d, 35h ; '5'
0x1400201fb  mov     dword ptr [rsp+0F8h+var_D0], eax
0x1400201ff  mov     r8d, edi
0x140020202  mov     dl, 4
0x140020204  mov     [rsp+0F8h+var_D8], rsi
0x140020209  mov     rcx, [rcx+48h]
0x14002020d  call    WPP_RECORDER_SF_D
0x140020212  mov     rdx, [rbp+30h]
0x140020216  mov     rcx, [rsp+0F8h+var_80]
0x14002021b  cmp     dword ptr [rdx+rcx+30h], 0
0x140020220  jg      loc_140020CDD
0x140020226  mov     eax, 32h ; '2'
0x14002022b  mov     rdx, [rdx+rcx+28h]
0x140020230  mov     rcx, cs:WdfDriverGlobals
0x140020237  movzx   eax, ax
0x14002023a  imul    r8, rax, 0FFFFFFFFFFFFD8F0h
0x140020241  mov     rax, cs:WdfFunctions_01033
0x140020248  mov     rax, [rax+9F8h]
0x14002024f  call    _guard_dispatch_icall
0x140020254  jmp     loc_14002030E
0x140020259  mov     edx, r12d
0x14002025c  mov     rcx, rbp
0x14002025f  call    RootHub_AcquireReadModifyWriteLock
0x140020264  mov     rdx, r13
0x140020267  mov     rcx, r15
0x14002026a  call    XilRegister_ReadUlong
0x14002026f  mov     ebx, eax
0x140020271  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140020278  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002027f  jnz     loc_14002053D
0x140020285  and     ebx, 0E00C200h
0x14002028b  bts     ebx, 11h
0x14002028f  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x140020296  jz      short loc_1400202B9
0x140020298  mov     rcx, [rbp+8]
0x14002029c  mov     r9d, 3Eh ; '>'
0x1400202a2  mov     dword ptr [rsp+0F8h+var_D0], ebx
0x1400202a6  mov     r8d, edi
0x1400202a9  mov     dl, 4
0x1400202ab  mov     [rsp+0F8h+var_D8], rsi
0x1400202b0  mov     rcx, [rcx+48h]
0x1400202b4  call    WPP_RECORDER_SF_D
0x1400202b9  mov     r8d, ebx
0x1400202bc  mov     rdx, r13
0x1400202bf  mov     rcx, r15
0x1400202c2  call    XilRegister_WriteUlong
0x1400202c7  mov     edx, r12d
0x1400202ca  mov     rcx, rbp
0x1400202cd  call    RootHub_ReleaseReadModifyWriteLock
0x1400202d2  mov     rdx, r13
0x1400202d5  mov     rcx, r15
0x1400202d8  call    XilRegister_ReadUlong
0x1400202dd  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400202e4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400202eb  jz      short loc_14002030E
0x1400202ed  mov     r9d, 3Fh ; '?'
0x1400202f3  mov     rcx, [rbp+8]
0x1400202f7  mov     r8d, edi
0x1400202fa  mov     dword ptr [rsp+0F8h+var_D0], eax
0x1400202fe  mov     dl, 4
0x140020300  mov     [rsp+0F8h+var_D8], rsi
0x140020305  mov     rcx, [rcx+48h]
0x140020309  call    WPP_RECORDER_SF_D
0x14002030e  mov     dword ptr [r14+4], 0
0x140020316  xor     r8d, r8d
0x140020319  jmp     loc_14001FF3E
0x14002031e  cmp     dl, 3
0x140020321  jnz     loc_1400213D9
0x140020327  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002032e  mov     edi, 0Bh
0x140020333  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002033a  lea     rsi, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x140020341  jnz     loc_140020EFD
0x140020347  test    r8b, r8b
0x14002034a  jnz     loc_140020F39
0x140020350  sub     ebx, 8
0x140020353  jz      loc_140021316
0x140020359  sub     ebx, 8
0x14002035c  jz      loc_14002067E
0x140020362  sub     ebx, 3
0x140020365  jz      loc_1400205B7
0x14002036b  sub     ebx, 1
0x14002036e  jz      loc_14002081F
0x140020374  sub     ebx, 5
0x140020377  jz      loc_14002075A
  ... truncated ...
```
