# StatusPipeCompletion

- ea: `0x14000a7bc`
- end: `0x14000b4c7`
- name: `StatusPipeCompletion`
- size: `3339`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400013a0`

## callees

- `0x140002964`
- `0x140002a24`
- `0x140004adc`
- `0x140008430`
- `0x140008720`
- `0x14000a450`
- `0x14000a7bc`
- `0x14000b4d0`
- `0x14000b980`
- `0x14000bafc`
- `0x14000bca0`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000ae4f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000b3ba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000b47c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000ae4f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000b3ba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000b47c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a805`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a805`
- `ntoskrnl!IoCancelIrp` at `0x14000aec2`
- `ntoskrnl!IoCancelIrp` at `0x14000b426`
- `ntoskrnl!IoCancelIrp` at `0x14000aec2`
- `ntoskrnl!IoCancelIrp` at `0x14000b426`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a84c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a8d5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a978`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a9e5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000aa64`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000ab2c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000abb1`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000ac9c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000ad21`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000ae08`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000ae8b`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000af1a`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000afc5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000b081`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000b108`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000b1f3`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000b27a`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000b361`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000b3ef`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a84c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a8d5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a978`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a9e5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000aa64`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000ab2c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000abb1`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000ac9c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000ad21`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000ae08`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000ae8b`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000af1a`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000afc5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000b081`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000b108`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000b1f3`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000b27a`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000b361`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000b3ef`

## pseudocode

```c
__int64 __fastcall StatusPipeCompletion(__int64 a1, unsigned __int8 *a2, int a3, __int64 a4, __int64 a5)
{
  int v8; // r12d
  __int64 v9; // rdi
  __int64 v10; // rsi
  int Default; // eax
  int v12; // edx
  __int64 v13; // rax
  int v14; // ebx
  int v15; // eax
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  unsigned __int16 v19; // r12
  IRP *v20; // r15
  __int64 v21; // rbp
  int v22; // ebx
  unsigned __int16 v23; // di
  int v24; // eax
  int v25; // edx
  int v26; // eax
  int v27; // edx
  int v28; // r8d
  __int64 v29; // rdi
  int v30; // eax
  int v31; // edx
  int v32; // r8d
  __int64 v33; // rcx
  __int64 v34; // rdi
  __int64 v35; // rax
  __int64 v36; // rcx
  __int16 v37; // bx
  int v38; // eax
  int v39; // edx
  __int16 v40; // bx
  int v41; // eax
  int v42; // edx
  int v43; // r8d
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // r8
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int16 v51; // bx
  __int64 v52; // rdi
  int v53; // eax
  int v54; // edx
  __int16 v55; // bx
  int v56; // eax
  int v57; // edx
  int v58; // r8d
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rax
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int16 v66; // bx
  __int64 v67; // rdi
  int v68; // eax
  int v69; // edx
  __int16 v70; // bx
  int v71; // eax
  int v72; // edx
  __int64 v73; // r9
  _BYTE *v74; // rdx
  __int64 v75; // r8
  __int64 *v76; // rcx
  int v78; // eax
  int v79; // edx
  __int64 v80; // rdi
  int v81; // eax
  int v82; // edx
  int v83; // r8d
  int v84; // r9d
  __int64 v85; // rcx
  __int64 v86; // rdi
  __int64 v87; // rax
  __int64 v88; // rcx
  __int16 v89; // bx
  int v90; // eax
  int v91; // edx
  __int16 v92; // bx
  int v93; // eax
  int v94; // edx
  int v95; // r8d
  __int64 v96; // rcx
  __int64 v97; // rax
  __int64 v98; // rcx
  __int64 v99; // rax
  __int64 v100; // r8
  __int64 v101; // rdx
  __int64 v102; // rcx
  __int16 v103; // bx
  __int64 v104; // rdi
  int v105; // eax
  int v106; // edx
  __int16 v107; // bx
  int v108; // eax
  int v109; // edx
  int v110; // r8d
  __int64 v111; // rcx
  __int64 v112; // rax
  __int64 v113; // rcx
  __int64 v114; // rax
  __int64 v115; // r8
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int16 v118; // bx
  __int64 v119; // rdi
  int v120; // eax
  int v121; // edx
  __int16 v122; // bx
  int v123; // eax
  int v124; // edx
  int v125; // [rsp+20h] [rbp-A8h]
  __int64 v126; // [rsp+70h] [rbp-58h]
  __int64 v127; // [rsp+70h] [rbp-58h]
  __int64 v128; // [rsp+70h] [rbp-58h]
  __int64 v129; // [rsp+70h] [rbp-58h]
  __int64 v130; // [rsp+70h] [rbp-58h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+78h] [rbp-50h] BYREF
  __int64 v132; // [rsp+D0h] [rbp+8h]

  memset(&LockHandle, 0, sizeof(LockHandle));
  v8 = a3;
  v9 = **(_QWORD **)(a1 + 8);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v9 + 1136), &LockHandle);
  v10 = *(_QWORD *)(a1 + 8);
  if ( v8 < 0 )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_iD(Default, v12, 2, 20, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, a4, v8);
    }
    if ( a4 == *(_QWORD *)(v10 + 128) )
    {
      v13 = *(_QWORD *)(v10 + 96);
    }
    else
    {
      if ( a4 != *(_QWORD *)(v10 + 136) )
        goto LABEL_109;
      v13 = *(_QWORD *)(v10 + 104);
    }
    if ( *(_DWORD *)(v13 + 4) != -1073676288 || (v14 = *(_DWORD *)(v13 + 36)) == 0 )
    {
LABEL_107:
      if ( a4 == *(_QWORD *)(v10 + 136) )
      {
        *(_DWORD *)(v10 + 20) = 3;
        goto LABEL_110;
      }
LABEL_109:
      *(_DWORD *)(v10 + 16) = 3;
LABEL_110:
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v75 = (unsigned int)v8;
      v73 = a5;
      v74 = a2;
      v76 = (__int64 *)v10;
      if ( a4 != *(_QWORD *)(v10 + 136) )
        return SenseIUCompletion(v76, v74, v75, v73);
      return ReadyIUCompletion(v76, v74, v75, v73);
    }
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      WPP_RECORDER_SF_id(v15, v16, v17, v18, v125, a4, v14);
    }
  }
  v19 = __ROR2__(*((_WORD *)a2 + 1), 8) - 1;
  if ( v19 >= *(_WORD *)(v9 + 1280) )
    goto LABEL_23;
  v20 = 0;
  v21 = *(_QWORD *)(v9 + 1176) + 224LL * v19;
  if ( *a2 != 3 && *a2 != 4 )
  {
    if ( (unsigned int)*a2 - 6 > 1 )
      goto LABEL_23;
    v22 = *(_DWORD *)(v21 + 20);
    if ( v22 == 2 )
    {
      v132 = *(_QWORD *)(v21 + 136);
      if ( a4 != v132 )
      {
        v29 = *(_QWORD *)(v21 + 128);
        if ( a4 == v29 )
        {
          if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v30 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
            WPP_RECORDER_SF_iDiDDiDi(v30, v31, v32, 32, v125, a4, v19, v29, v19, v19, v29, v19, v132);
          }
          v33 = *(_QWORD *)(v21 + 104);
          v34 = *(_QWORD *)(v21 + 136);
          *(_QWORD *)(v21 + 104) = *(_QWORD *)(v21 + 96);
          *(_QWORD *)(v21 + 136) = *(_QWORD *)(v21 + 128);
          v35 = *(_QWORD *)(v21 + 208);
          *(_QWORD *)(v21 + 96) = v33;
          v36 = *(_QWORD *)(v21 + 216);
          *(_QWORD *)(v21 + 216) = v35;
          *(_QWORD *)(v21 + 128) = v34;
          *(_QWORD *)(v21 + 208) = v36;
          if ( *(_BYTE *)(v21 + 202) )
          {
            if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v37 = *(_WORD *)(v21 + 40) - 1;
              v38 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
              LOBYTE(v39) = 2;
              WPP_RECORDER_SF_iD(v38, v39, 2, 33, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, v34, v37);
            }
            v20 = *(IRP **)(v21 + 128);
          }
        }
        else
        {
          v126 = *(_QWORD *)(v10 + 136);
          if ( a4 == v126 )
          {
            if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v40 = *(_WORD *)(v10 + 40) - 1;
              v41 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
              WPP_RECORDER_SF_iDiDDiDi(v41, v42, v43, 34, v125, a4, v19, v126, v40, v19, v126, v40, v132);
            }
            v44 = *(_QWORD *)(v10 + 104);
            *(_QWORD *)(v10 + 104) = *(_QWORD *)(v21 + 104);
            v45 = *(_QWORD *)(v21 + 136);
            *(_QWORD *)(v21 + 104) = v44;
            v46 = *(_QWORD *)(v10 + 136);
            *(_QWORD *)(v10 + 136) = v45;
            v47 = *(_QWORD *)(v21 + 216);
            *(_QWORD *)(v21 + 136) = v46;
            v48 = *(_QWORD *)(v10 + 216);
            *(_QWORD *)(v10 + 216) = v47;
            *(_QWORD *)(v21 + 216) = v48;
            v49 = *(_QWORD *)(v10 + 216);
            v50 = *(_QWORD *)(v49 + 8);
            *(_QWORD *)(v49 + 8) = *(_QWORD *)(v48 + 8);
            *(_QWORD *)(v48 + 8) = v50;
            if ( *(_BYTE *)(v10 + 203) )
            {
              if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v51 = *(_WORD *)(v10 + 40) - 1;
                v52 = *(_QWORD *)(v10 + 136);
                v53 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
                LOBYTE(v54) = 2;
                WPP_RECORDER_SF_iD(v53, v54, 2, 35, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, v52, v51);
              }
              v20 = *(IRP **)(v10 + 136);
            }
          }
          else
          {
            v127 = *(_QWORD *)(v10 + 128);
            if ( a4 != v127 )
              goto LABEL_23;
            if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v55 = *(_WORD *)(v10 + 40) - 1;
              v56 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
              WPP_RECORDER_SF_iDiDDiDi(v56, v57, v58, 36, v125, a4, v19, v127, v55, v19, v127, v55, v132);
            }
            v59 = *(_QWORD *)(v10 + 96);
            *(_QWORD *)(v10 + 96) = *(_QWORD *)(v21 + 104);
            v60 = *(_QWORD *)(v21 + 136);
            *(_QWORD *)(v21 + 104) = v59;
            v61 = *(_QWORD *)(v10 + 128);
            *(_QWORD *)(v10 + 128) = v60;
            v62 = *(_QWORD *)(v21 + 216);
            *(_QWORD *)(v21 + 136) = v61;
            v63 = *(_QWORD *)(v10 + 208);
            *(_QWORD *)(v10 + 208) = v62;
            *(_QWORD *)(v21 + 216) = v63;
            v64 = *(_QWORD *)(v10 + 208);
            v65 = *(_QWORD *)(v64 + 8);
            *(_QWORD *)(v64 + 8) = *(_QWORD *)(v63 + 8);
            *(_QWORD *)(v63 + 8) = v65;
            if ( *(_BYTE *)(v10 + 202) )
            {
              if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v66 = *(_WORD *)(v10 + 40) - 1;
                v67 = *(_QWORD *)(v10 + 128);
                v68 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
                LOBYTE(v69) = 2;
                WPP_RECORDER_SF_iD(v68, v69, 2, 37, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, v67, v66);
              }
              v20 = *(IRP **)(v10 + 128);
            }
          }
        }
      }
      *(_DWORD *)(v21 + 20) = 3;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      if ( v20 )
      {
        if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v70 = *(_WORD *)(v10 + 40) - 1;
          v71 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          LOBYTE(v72) = 2;
          WPP_RECORDER_SF_iD(v71, v72, 2, 38, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, (char)v20, v70);
        }
        IoCancelIrp(v20);
      }
      v73 = a5;
      v74 = a2;
      LODWORD(v75) = a3;
      v76 = (__int64 *)v21;
      return ReadyIUCompletion(v76, v74, v75, v73);
    }
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = 31;
LABEL_22:
      v24 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v25) = 2;
      WPP_RECORDER_SF_d(v24, v25, 2, v23, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, v22);
    }
LABEL_23:
    if ( a3 < 0 )
    {
      v8 = a3;
    }
    else
    {
      if ( gTracingEnabled )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v26 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          LOBYTE(v27) = 2;
          WPP_RECORDER_SF_DD(v26, v27, v28, 39);
        }
      }
      v8 = -1073741823;
    }
    goto LABEL_107;
  }
  if ( a2[6] == 40 && gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v78 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    LOBYTE(v79) = 2;
    WPP_RECORDER_SF_(v78, v79, 2, 22, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids);
  }
  v22 = *(_DWORD *)(v21 + 16);
  if ( v22 != 2 )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = 23;
      goto LABEL_22;
    }
    goto LABEL_23;
  }
  v80 = *(_QWORD *)(v21 + 128);
  if ( a4 != v80 )
  {
    v128 = *(_QWORD *)(v21 + 136);
    if ( a4 == v128 )
    {
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v81 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        WPP_RECORDER_SF_iDDDiDi(v81, v82, v83, v84, v125, a4, v19, v19, v19, v128, v19, v80);
      }
      v85 = *(_QWORD *)(v21 + 96);
      v86 = *(_QWORD *)(v21 + 128);
      *(_QWORD *)(v21 + 96) = *(_QWORD *)(v21 + 104);
      *(_QWORD *)(v21 + 128) = *(_QWORD *)(v21 + 136);
      v87 = *(_QWORD *)(v21 + 216);
      *(_QWORD *)(v21 + 104) = v85;
      v88 = *(_QWORD *)(v21 + 208);
      *(_QWORD *)(v21 + 208) = v87;
      *(_QWORD *)(v21 + 136) = v86;
      *(_QWORD *)(v21 + 216) = v88;
      if ( *(_BYTE *)(v21 + 203) )
      {
        if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v89 = *(_WORD *)(v21 + 40) - 1;
          v90 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          LOBYTE(v91) = 2;
          WPP_RECORDER_SF_iD(v90, v91, 2, 25, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, v86, v89);
        }
        v20 = *(IRP **)(v21 + 136);
      }
    }
    else
    {
      v129 = *(_QWORD *)(v10 + 128);
      if ( a4 == v129 )
      {
        if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v92 = *(_WORD *)(v10 + 40) - 1;
          v93 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          WPP_RECORDER_SF_iDiDDiDi(v93, v94, v95, 26, v125, a4, v19, v129, v92, v19, v129, v92, v80);
        }
        v96 = *(_QWORD *)(v10 + 96);
        *(_QWORD *)(v10 + 96) = *(_QWORD *)(v21 + 96);
        v97 = *(_QWORD *)(v21 + 128);
        *(_QWORD *)(v21 + 96) = v96;
        v98 = *(_QWORD *)(v10 + 128);
        *(_QWORD *)(v10 + 128) = v97;
        v99 = *(_QWORD *)(v21 + 208);
        *(_QWORD *)(v21 + 128) = v98;
        v100 = *(_QWORD *)(v10 + 208);
        *(_QWORD *)(v10 + 208) = v99;
        *(_QWORD *)(v21 + 208) = v100;
        v101 = *(_QWORD *)(v10 + 208);
        v102 = *(_QWORD *)(v101 + 8);
        *(_QWORD *)(v101 + 8) = *(_QWORD *)(v100 + 8);
        *(_QWORD *)(v100 + 8) = v102;
        if ( *(_BYTE *)(v10 + 202) )
        {
          if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v103 = *(_WORD *)(v10 + 40) - 1;
            v104 = *(_QWORD *)(v10 + 128);
            v105 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
            LOBYTE(v106) = 2;
            WPP_RECORDER_SF_iD(v105, v106, 2, 27, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, v104, v103);
          }
          v20 = *(IRP **)(v10 + 128);
        }
      }
      else
      {
        v130 = *(_QWORD *)(v10 + 136);
        if ( a4 != v130 )
          goto LABEL_23;
        if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v107 = *(_WORD *)(v10 + 40) - 1;
          v108 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          WPP_RECORDER_SF_iDiDDiDi(v108, v109, v110, 28, v125, a4, v19, v130, v107, v19, v130, v107, v80);
        }
        v111 = *(_QWORD *)(v10 + 104);
        *(_QWORD *)(v10 + 104) = *(_QWORD *)(v21 + 96);
        v112 = *(_QWORD *)(v21 + 128);
        *(_QWORD *)(v21 + 96) = v111;
        v113 = *(_QWORD *)(v10 + 136);
        *(_QWORD *)(v10 + 136) = v112;
        v114 = *(_QWORD *)(v21 + 208);
        *(_QWORD *)(v21 + 128) = v113;
        v115 = *(_QWORD *)(v10 + 216);
        *(_QWORD *)(v10 + 216) = v114;
        *(_QWORD *)(v21 + 208) = v115;
        v116 = *(_QWORD *)(v10 + 216);
        v117 = *(_QWORD *)(v116 + 8);
        *(_QWORD *)(v116 + 8) = *(_QWORD *)(v115 + 8);
        *(_QWORD *)(v115 + 8) = v117;
        if ( *(_BYTE *)(v10 + 203) )
        {
          if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v118 = *(_WORD *)(v10 + 40) - 1;
            v119 = *(_QWORD *)(v10 + 136);
            v120 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
            LOBYTE(v121) = 2;
            WPP_RECORDER_SF_iD(v120, v121, 2, 29, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, v119, v118);
          }
          v20 = *(IRP **)(v10 + 136);
        }
      }
    }
  }
  *(_DWORD *)(v21 + 16) = 3;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v20 )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v122 = *(_WORD *)(v10 + 40) - 1;
      v123 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v124) = 2;
      WPP_RECORDER_SF_iD(v123, v124, 2, 30, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, (char)v20, v122);
    }
    IoCancelIrp(v20);
  }
  v74 = a2;
  v73 = a5;
  v76 = (__int64 *)v21;
  v75 = (unsigned int)a3;
  if ( *a2 == 4 )
    return ResponseIUCompletion(v21, a2, (unsigned int)a3, a5);
  return SenseIUCompletion(v76, v74, v75, v73);
}

```

## disassembly

```asm
0x14000a7bc  mov     r11, rsp
0x14000a7bf  mov     [r11+10h], rbx
0x14000a7c3  mov     [r11+18h], r8d
0x14000a7c7  push    rbp
0x14000a7c8  push    rsi
0x14000a7c9  push    rdi
0x14000a7ca  push    r12
0x14000a7cc  push    r13
0x14000a7ce  push    r14
0x14000a7d0  push    r15
0x14000a7d2  sub     rsp, 90h
0x14000a7d9  xor     eax, eax
0x14000a7db  xorps   xmm0, xmm0
0x14000a7de  movups  xmmword ptr [rsp+0C8h+LockHandle.LockQueue.Next], xmm0
0x14000a7e3  mov     [r11-40h], rax
0x14000a7e7  mov     r13, rdx
0x14000a7ea  mov     rax, [rcx+8]
0x14000a7ee  lea     rdx, [r11-50h]; LockHandle
0x14000a7f2  mov     rbx, rcx
0x14000a7f5  mov     r14, r9
0x14000a7f8  mov     r12d, r8d
0x14000a7fb  mov     rdi, [rax]
0x14000a7fe  lea     rcx, [rdi+470h]; SpinLock
0x14000a805  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000a80c  nop     dword ptr [rax+rax+00h]
0x14000a811  mov     rsi, [rbx+8]
0x14000a815  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000a81c  xor     r9d, r9d
0x14000a81f  lea     rbp, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x14000a826  test    r12d, r12d
0x14000a829  jns     loc_14000A8F5
0x14000a82f  cmp     cs:gTracingEnabled, r9b
0x14000a836  jz      short loc_14000A884
0x14000a838  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000a83f  jz      short loc_14000A884
0x14000a841  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a848  lea     ebx, [r9+14h]
0x14000a84c  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000a853  nop     dword ptr [rax+rax+00h]
0x14000a858  lea     r8d, [rbx-12h]
0x14000a85c  mov     [rsp+0C8h+var_98], r12d
0x14000a861  mov     dl, r8b
0x14000a864  mov     [rsp+0C8h+var_A0], r14
0x14000a869  mov     rcx, rax
0x14000a86c  mov     [rsp+0C8h+var_A8], rbp
0x14000a871  movzx   r9d, bx
0x14000a875  call    WPP_RECORDER_SF_iD
0x14000a87a  xor     r9d, r9d
0x14000a87d  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000a884  cmp     r14, [rsi+80h]
0x14000a88b  jnz     short loc_14000A893
0x14000a88d  mov     rax, [rsi+60h]
0x14000a891  jmp     short loc_14000A8A4
0x14000a893  cmp     r14, [rsi+88h]
0x14000a89a  jnz     loc_14000B470
0x14000a8a0  mov     rax, [rsi+68h]
0x14000a8a4  cmp     dword ptr [rax+4], 0C0010000h
0x14000a8ab  jnz     loc_14000B45E
0x14000a8b1  mov     ebx, [rax+24h]
0x14000a8b4  test    ebx, ebx
0x14000a8b6  jz      loc_14000B45E
0x14000a8bc  cmp     cs:gTracingEnabled, r9b
0x14000a8c3  jz      short loc_14000A8F5
0x14000a8c5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000a8cc  jz      short loc_14000A8F5
0x14000a8ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a8d5  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000a8dc  nop     dword ptr [rax+rax+00h]
0x14000a8e1  mov     rcx, rax
0x14000a8e4  mov     [rsp+0C8h+var_98], ebx
0x14000a8e8  mov     [rsp+0C8h+var_A0], r14
0x14000a8ed  call    WPP_RECORDER_SF_id
0x14000a8f2  xor     r9d, r9d
0x14000a8f5  movzx   r12d, word ptr [r13+2]
0x14000a8fa  ror     r12w, 8
0x14000a8ff  dec     r12w
0x14000a903  cmp     r12w, [rdi+500h]
0x14000a90b  jnb     loc_14000A9A9
0x14000a911  movzx   ecx, byte ptr [r13+0]
0x14000a916  mov     r15, r9
0x14000a919  movzx   eax, r12w
0x14000a91d  imul    rbp, rax, 0E0h
0x14000a924  add     rbp, [rdi+498h]
0x14000a92b  sub     ecx, 3
0x14000a92e  jz      loc_14000AEEE
0x14000a934  sub     ecx, 1
0x14000a937  jz      loc_14000AEEE
0x14000a93d  sub     ecx, 2
0x14000a940  jz      short loc_14000A947
0x14000a942  cmp     ecx, 1
0x14000a945  jnz     short loc_14000A9A9
0x14000a947  mov     ebx, [rbp+14h]
0x14000a94a  cmp     ebx, 2
0x14000a94d  jz      loc_14000AA12
0x14000a953  cmp     cs:gTracingEnabled, r9b
0x14000a95a  jz      short loc_14000A9A9
0x14000a95c  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000a963  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000a96a  jz      short loc_14000A9B0
0x14000a96c  mov     edi, 1Fh
0x14000a971  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a978  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000a97f  nop     dword ptr [rax+rax+00h]
0x14000a984  mov     r8d, 2
0x14000a98a  mov     dword ptr [rsp+0C8h+var_A0], ebx
0x14000a98e  mov     rcx, rax
0x14000a991  movzx   r9d, di
0x14000a995  lea     rax, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x14000a99c  mov     dl, r8b
0x14000a99f  mov     [rsp+0C8h+var_A8], rax
0x14000a9a4  call    WPP_RECORDER_SF_d
0x14000a9a9  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000a9b0  cmp     [rsp+0C8h+arg_10], 0
0x14000a9b8  jl      loc_14000B456
0x14000a9be  cmp     cs:gTracingEnabled, 0
0x14000a9c5  jz      short loc_14000AA07
0x14000a9c7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000a9ce  jz      short loc_14000AA07
0x14000a9d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a9d7  mov     ebp, 27h ; '''
0x14000a9dc  movzx   edi, byte ptr [r13+0]
0x14000a9e1  movzx   ebx, r12w
0x14000a9e5  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000a9ec  nop     dword ptr [rax+rax+00h]
0x14000a9f1  mov     [rsp+0C8h+var_98], ebx
0x14000a9f5  movzx   r9d, bp
0x14000a9f9  mov     rcx, rax
0x14000a9fc  mov     dword ptr [rsp+0C8h+var_A0], edi
0x14000aa00  mov     dl, 2
0x14000aa02  call    WPP_RECORDER_SF_DD
0x14000aa07  mov     r12d, 0C0000001h
0x14000aa0d  jmp     loc_14000B45E
0x14000aa12  mov     rax, [rbp+88h]
0x14000aa19  mov     [rsp+0C8h+arg_0], rax
0x14000aa21  cmp     r14, rax
0x14000aa24  jz      loc_14000AE43
0x14000aa2a  mov     rdi, [rbp+80h]
0x14000aa31  cmp     r14, rdi
0x14000aa34  jnz     loc_14000AB6C
0x14000aa3a  cmp     cs:gTracingEnabled, r9b
0x14000aa41  jz      short loc_14000AAAB
0x14000aa43  lea     rdx, WPP_RECORDER_INITIALIZED
0x14000aa4a  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000aa51  jz      short loc_14000AAB2
0x14000aa53  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aa5a  movzx   ebx, r12w
0x14000aa5e  mov     r12d, 20h ; ' '
0x14000aa64  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000aa6b  nop     dword ptr [rax+rax+00h]
0x14000aa70  mov     rcx, rax
0x14000aa73  movzx   r9d, r12w
0x14000aa77  mov     rax, [rsp+0C8h+arg_0]
0x14000aa7f  mov     [rsp+0C8h+var_68], rax
0x14000aa84  mov     dword ptr [rsp+0C8h+var_70], ebx
0x14000aa88  mov     [rsp+0C8h+var_78], rdi
0x14000aa8d  mov     dword ptr [rsp+0C8h+var_80], ebx
0x14000aa91  mov     [rsp+0C8h+var_88], ebx
0x14000aa95  mov     [rsp+0C8h+var_90], rdi
0x14000aa9a  mov     [rsp+0C8h+var_98], ebx
0x14000aa9e  mov     [rsp+0C8h+var_A0], r14
0x14000aaa3  call    WPP_RECORDER_SF_iDiDDiDi
0x14000aaa8  xor     r9d, r9d
0x14000aaab  lea     rdx, WPP_RECORDER_INITIALIZED
0x14000aab2  mov     rax, [rbp+60h]
0x14000aab6  mov     rcx, [rbp+68h]
0x14000aaba  mov     rdi, [rbp+88h]
0x14000aac1  mov     [rbp+68h], rax
0x14000aac5  mov     rax, [rbp+80h]
0x14000aacc  mov     [rbp+88h], rax
0x14000aad3  mov     rax, [rbp+0D0h]
0x14000aada  mov     [rbp+60h], rcx
0x14000aade  mov     rcx, [rbp+0D8h]
0x14000aae5  mov     [rbp+0D8h], rax
0x14000aaec  mov     [rbp+80h], rdi
0x14000aaf3  mov     [rbp+0D0h], rcx
0x14000aafa  cmp     [rbp+0CAh], r9b
0x14000ab01  jz      loc_14000AE43
0x14000ab07  cmp     cs:gTracingEnabled, r9b
0x14000ab0e  jz      short loc_14000AB60
0x14000ab10  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000ab17  jz      short loc_14000AB60
0x14000ab19  movzx   ebx, word ptr [rbp+28h]
0x14000ab1d  mov     r14d, 21h ; '!'
0x14000ab23  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ab2a  dec     ebx
0x14000ab2c  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000ab33  nop     dword ptr [rax+rax+00h]
0x14000ab38  lea     r8d, [r14-1Fh]
0x14000ab3c  mov     [rsp+0C8h+var_98], ebx
0x14000ab40  mov     rcx, rax
0x14000ab43  mov     [rsp+0C8h+var_A0], rdi
0x14000ab48  lea     rax, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x14000ab4f  movzx   r9d, r14w
0x14000ab53  mov     dl, r8b
0x14000ab56  mov     [rsp+0C8h+var_A8], rax
0x14000ab5b  call    WPP_RECORDER_SF_iD
0x14000ab60  mov     r15, [rbp+80h]
0x14000ab67  jmp     loc_14000AE43
0x14000ab6c  mov     rax, [rsi+88h]
0x14000ab73  mov     [rsp+0C8h+var_58], rax
0x14000ab78  cmp     r14, rax
0x14000ab7b  jnz     loc_14000ACDC
0x14000ab81  cmp     cs:gTracingEnabled, r9b
0x14000ab88  jz      short loc_14000ABFD
0x14000ab8a  lea     r10, WPP_RECORDER_INITIALIZED
0x14000ab91  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x14000ab98  jz      short loc_14000AC04
0x14000ab9a  movzx   ebx, word ptr [rsi+28h]
0x14000ab9e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aba5  dec     ebx
0x14000aba7  movzx   edi, r12w
0x14000abab  mov     r12d, 22h ; '"'
0x14000abb1  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000abb8  nop     dword ptr [rax+rax+00h]
0x14000abbd  mov     rcx, rax
0x14000abc0  movzx   r9d, r12w
0x14000abc4  mov     rax, [rsp+0C8h+arg_0]
0x14000abcc  mov     [rsp+0C8h+var_68], rax
0x14000abd1  mov     rax, [rsp+0C8h+var_58]
0x14000abd6  mov     dword ptr [rsp+0C8h+var_70], ebx
0x14000abda  mov     [rsp+0C8h+var_78], rax
0x14000abdf  mov     dword ptr [rsp+0C8h+var_80], edi
0x14000abe3  mov     [rsp+0C8h+var_88], ebx
0x14000abe7  mov     [rsp+0C8h+var_90], rax
0x14000abec  mov     [rsp+0C8h+var_98], edi
0x14000abf0  mov     [rsp+0C8h+var_A0], r14
0x14000abf5  call    WPP_RECORDER_SF_iDiDDiDi
0x14000abfa  xor     r9d, r9d
0x14000abfd  lea     r10, WPP_RECORDER_INITIALIZED
0x14000ac04  mov     rax, [rbp+68h]
0x14000ac08  mov     rcx, [rsi+68h]
0x14000ac0c  mov     [rsi+68h], rax
0x14000ac10  mov     rax, [rbp+88h]
0x14000ac17  mov     [rbp+68h], rcx
0x14000ac1b  mov     rcx, [rsi+88h]
0x14000ac22  mov     [rsi+88h], rax
0x14000ac29  mov     rax, [rbp+0D8h]
0x14000ac30  mov     [rbp+88h], rcx
0x14000ac37  mov     r8, [rsi+0D8h]
0x14000ac3e  mov     [rsi+0D8h], rax
0x14000ac45  mov     [rbp+0D8h], r8
0x14000ac4c  mov     rdx, [rsi+0D8h]
0x14000ac53  mov     rax, [r8+8]
0x14000ac57  mov     rcx, [rdx+8]
0x14000ac5b  mov     [rdx+8], rax
0x14000ac5f  mov     [r8+8], rcx
0x14000ac63  cmp     [rsi+0CBh], r9b
0x14000ac6a  jz      loc_14000AE43
0x14000ac70  cmp     cs:gTracingEnabled, r9b
0x14000ac77  jz      short loc_14000ACD0
0x14000ac79  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x14000ac80  jz      short loc_14000ACD0
0x14000ac82  movzx   ebx, word ptr [rsi+28h]
0x14000ac86  mov     r14d, 23h ; '#'
0x14000ac8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ac93  dec     ebx
0x14000ac95  mov     rdi, [rsi+88h]
0x14000ac9c  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000aca3  nop     dword ptr [rax+rax+00h]
0x14000aca8  lea     r8d, [r14-21h]
0x14000acac  mov     [rsp+0C8h+var_98], ebx
0x14000acb0  mov     rcx, rax
0x14000acb3  mov     [rsp+0C8h+var_A0], rdi
0x14000acb8  lea     rax, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x14000acbf  movzx   r9d, r14w
0x14000acc3  mov     dl, r8b
0x14000acc6  mov     [rsp+0C8h+var_A8], rax
0x14000accb  call    WPP_RECORDER_SF_iD
0x14000acd0  mov     r15, [rsi+88h]
0x14000acd7  jmp     loc_14000AE43
0x14000acdc  mov     rax, [rsi+80h]
0x14000ace3  mov     [rsp+0C8h+var_58], rax
0x14000ace8  cmp     r14, rax
0x14000aceb  jnz     loc_14000A9A9
0x14000acf1  cmp     cs:gTracingEnabled, r9b
0x14000acf8  jz      short loc_14000AD6D
0x14000acfa  lea     r10, WPP_RECORDER_INITIALIZED
0x14000ad01  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x14000ad08  jz      short loc_14000AD74
0x14000ad0a  movzx   ebx, word ptr [rsi+28h]
0x14000ad0e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ad15  dec     ebx
0x14000ad17  movzx   edi, r12w
0x14000ad1b  mov     r12d, 24h ; '$'
0x14000ad21  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000ad28  nop     dword ptr [rax+rax+00h]
0x14000ad2d  mov     rcx, rax
0x14000ad30  movzx   r9d, r12w
0x14000ad34  mov     rax, [rsp+0C8h+arg_0]
0x14000ad3c  mov     [rsp+0C8h+var_68], rax
0x14000ad41  mov     rax, [rsp+0C8h+var_58]
0x14000ad46  mov     dword ptr [rsp+0C8h+var_70], ebx
0x14000ad4a  mov     [rsp+0C8h+var_78], rax
0x14000ad4f  mov     dword ptr [rsp+0C8h+var_80], edi
0x14000ad53  mov     [rsp+0C8h+var_88], ebx
0x14000ad57  mov     [rsp+0C8h+var_90], rax
0x14000ad5c  mov     [rsp+0C8h+var_98], edi
0x14000ad60  mov     [rsp+0C8h+var_A0], r14
0x14000ad65  call    WPP_RECORDER_SF_iDiDDiDi
0x14000ad6a  xor     r9d, r9d
  ... truncated ...
```
