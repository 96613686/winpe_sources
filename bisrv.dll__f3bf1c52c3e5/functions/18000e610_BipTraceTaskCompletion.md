# BipTraceTaskCompletion

- ea: `0x18000e610`
- end: `0x18000f017`
- name: `BipTraceTaskCompletion`
- size: `2567`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000db40`
- `0x180012960`

## callees

- `0x18000e610`
- `0x180014ea0`
- `0x180026360`
- `0x180035e2c`
- `0x180036740`
- `0x18006d364`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlQueryUnbiasedInterruptTime` at `0x18000e879`
- `ntdll!RtlQueryUnbiasedInterruptTime` at `0x18000e879`
- `ntdll!RtlFreeHeap` at `0x18000eff7`
- `ntdll!RtlFreeHeap` at `0x18000eff7`
- `ntdll!RtlAllocateHeap` at `0x18000e827`
- `ntdll!RtlAllocateHeap` at `0x18000e827`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18000e854`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18000e854`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ede0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ede0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000e7e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000e7e9`

## pseudocode

```c
BOOLEAN __fastcall BipTraceTaskCompletion(__int64 a1, __int128 *a2, __int64 a3, int a4)
{
  __int64 *v4; // r12
  int v6; // ecx
  char v7; // di
  __int128 *v8; // r13
  __int64 v9; // rcx
  int v10; // ecx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  __int64 *v14; // rsi
  const wchar_t *v15; // r14
  __int64 *v16; // rax
  __int64 *v17; // r15
  __int64 v18; // rcx
  int v19; // r9d
  __int16 v20; // ax
  int v21; // edx
  int v22; // r8d
  __int16 v23; // dx
  __int16 v24; // cx
  __int16 v25; // ax
  unsigned __int8 IsUserActive; // al
  __int64 v27; // rcx
  __int64 v28; // r13
  __int64 *Heap; // rax
  __int64 *v30; // rdi
  __int64 v31; // rcx
  __int64 v32; // rdi
  __int64 v33; // rax
  __int64 *v34; // rcx
  __int64 v35; // rax
  bool v36; // zf
  int v37; // eax
  __int64 *v38; // rdx
  __int64 v39; // rax
  int v40; // eax
  __int64 v41; // rax
  int v42; // eax
  int v43; // ecx
  __int64 v44; // r15
  __int64 v45; // rax
  int v46; // eax
  int v47; // eax
  __int64 v48; // rax
  int v49; // eax
  unsigned __int64 v50; // rsi
  BOOLEAN result; // al
  unsigned __int16 v52; // ax
  unsigned __int16 v53; // cx
  const wchar_t *v54; // rcx
  int v55; // edx
  __int64 v56; // rax
  int v57; // eax
  unsigned __int8 IsWorkItemPackageImportant; // [rsp+38h] [rbp-D0h]
  unsigned __int8 v59; // [rsp+39h] [rbp-CFh]
  int v60; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v61; // [rsp+40h] [rbp-C8h] BYREF
  int v62; // [rsp+48h] [rbp-C0h]
  int v63; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v64; // [rsp+50h] [rbp-B8h] BYREF
  __int128 *v65; // [rsp+58h] [rbp-B0h] BYREF
  int v66; // [rsp+60h] [rbp-A8h] BYREF
  int v67; // [rsp+64h] [rbp-A4h] BYREF
  int v68; // [rsp+68h] [rbp-A0h] BYREF
  int v69; // [rsp+6Ch] [rbp-9Ch] BYREF
  int v70; // [rsp+70h] [rbp-98h] BYREF
  int v71; // [rsp+74h] [rbp-94h] BYREF
  int v72; // [rsp+78h] [rbp-90h] BYREF
  int v73; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v74; // [rsp+80h] [rbp-88h] BYREF
  int v75; // [rsp+84h] [rbp-84h] BYREF
  int v76; // [rsp+88h] [rbp-80h] BYREF
  int v77; // [rsp+8Ch] [rbp-7Ch] BYREF
  int v78; // [rsp+90h] [rbp-78h] BYREF
  int v79; // [rsp+94h] [rbp-74h] BYREF
  int v80; // [rsp+98h] [rbp-70h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v82; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v83; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v84; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v85; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v86; // [rsp+C8h] [rbp-40h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v88; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v89; // [rsp+F0h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+108h] [rbp+0h] BYREF
  __int16 *v91; // [rsp+118h] [rbp+10h]
  int v92; // [rsp+120h] [rbp+18h]
  int v93; // [rsp+124h] [rbp+1Ch]
  __int64 v94; // [rsp+128h] [rbp+20h]
  __int64 v95; // [rsp+130h] [rbp+28h]
  __int128 *v96; // [rsp+138h] [rbp+30h]
  __int64 v97; // [rsp+140h] [rbp+38h]
  __int128 *v98; // [rsp+148h] [rbp+40h]
  __int64 v99; // [rsp+150h] [rbp+48h]
  __int64 *v100; // [rsp+158h] [rbp+50h]
  int v101; // [rsp+160h] [rbp+58h]
  int v102; // [rsp+164h] [rbp+5Ch]
  __int64 *v103; // [rsp+168h] [rbp+60h]
  int v104; // [rsp+170h] [rbp+68h]
  int v105; // [rsp+174h] [rbp+6Ch]
  __int64 *v106; // [rsp+178h] [rbp+70h]
  int v107; // [rsp+180h] [rbp+78h]
  int v108; // [rsp+184h] [rbp+7Ch]
  int *v109; // [rsp+188h] [rbp+80h]
  __int64 v110; // [rsp+190h] [rbp+88h]
  int *v111; // [rsp+198h] [rbp+90h]
  __int64 v112; // [rsp+1A0h] [rbp+98h]
  int *v113; // [rsp+1A8h] [rbp+A0h]
  __int64 v114; // [rsp+1B0h] [rbp+A8h]
  __int128 *v115; // [rsp+1B8h] [rbp+B0h]
  __int64 v116; // [rsp+1C0h] [rbp+B8h]
  __int64 v117; // [rsp+1C8h] [rbp+C0h]
  __int64 v118; // [rsp+1D0h] [rbp+C8h]
  __int128 *v119; // [rsp+1D8h] [rbp+D0h]
  __int64 v120; // [rsp+1E0h] [rbp+D8h]
  __int64 v121; // [rsp+1E8h] [rbp+E0h]
  __int64 v122; // [rsp+1F0h] [rbp+E8h]
  __int128 *v123; // [rsp+1F8h] [rbp+F0h]
  __int64 v124; // [rsp+200h] [rbp+F8h]
  _FILETIME *p_SystemTimeAsFileTime; // [rsp+208h] [rbp+100h]
  __int64 v126; // [rsp+210h] [rbp+108h]
  __int64 *v127; // [rsp+218h] [rbp+110h]
  __int64 v128; // [rsp+220h] [rbp+118h]
  int *v129; // [rsp+228h] [rbp+120h]
  __int64 v130; // [rsp+230h] [rbp+128h]
  __int64 *v131; // [rsp+238h] [rbp+130h]
  __int64 v132; // [rsp+240h] [rbp+138h]
  int *v133; // [rsp+248h] [rbp+140h]
  __int64 v134; // [rsp+250h] [rbp+148h]
  int *v135; // [rsp+258h] [rbp+150h]
  __int64 v136; // [rsp+260h] [rbp+158h]
  int *v137; // [rsp+268h] [rbp+160h]
  __int64 v138; // [rsp+270h] [rbp+168h]
  __int64 *v139; // [rsp+278h] [rbp+170h]
  int v140; // [rsp+280h] [rbp+178h]
  int v141; // [rsp+284h] [rbp+17Ch]
  int *v142; // [rsp+288h] [rbp+180h]
  __int64 v143; // [rsp+290h] [rbp+188h]
  __int64 *v144; // [rsp+298h] [rbp+190h]
  __int64 v145; // [rsp+2A0h] [rbp+198h]
  int *v146; // [rsp+2A8h] [rbp+1A0h]
  __int64 v147; // [rsp+2B0h] [rbp+1A8h]
  int *v148; // [rsp+2B8h] [rbp+1B0h]
  __int64 v149; // [rsp+2C0h] [rbp+1B8h]
  int *v150; // [rsp+2C8h] [rbp+1C0h]
  __int64 v151; // [rsp+2D0h] [rbp+1C8h]
  int *v152; // [rsp+2D8h] [rbp+1D0h]
  __int64 v153; // [rsp+2E0h] [rbp+1D8h]
  int *v154; // [rsp+2E8h] [rbp+1E0h]
  __int64 v155; // [rsp+2F0h] [rbp+1E8h]
  int *v156; // [rsp+2F8h] [rbp+1F0h]
  __int64 v157; // [rsp+300h] [rbp+1F8h]
  int *v158; // [rsp+308h] [rbp+200h]
  __int64 v159; // [rsp+310h] [rbp+208h]
  int *v160; // [rsp+318h] [rbp+210h]
  __int64 v161; // [rsp+320h] [rbp+218h]
  int *v162; // [rsp+328h] [rbp+220h]
  __int64 v163; // [rsp+330h] [rbp+228h]
  __int64 *v164; // [rsp+338h] [rbp+230h]
  __int64 v165; // [rsp+340h] [rbp+238h]
  __int128 **v166; // [rsp+348h] [rbp+240h]
  __int64 v167; // [rsp+350h] [rbp+248h]
  __int64 *v168; // [rsp+358h] [rbp+250h]
  __int64 v169; // [rsp+360h] [rbp+258h]
  char v170[16]; // [rsp+368h] [rbp+260h] BYREF
  __int64 *v171; // [rsp+378h] [rbp+270h]
  __int64 v172; // [rsp+380h] [rbp+278h]
  __int128 **v173; // [rsp+388h] [rbp+280h]
  __int64 v174; // [rsp+390h] [rbp+288h]
  __int64 *v175; // [rsp+398h] [rbp+290h]
  __int64 v176; // [rsp+3A0h] [rbp+298h]
  const wchar_t *v177; // [rsp+3A8h] [rbp+2A0h]
  int v178; // [rsp+3B0h] [rbp+2A8h]
  int v179; // [rsp+3B4h] [rbp+2ACh]
  const wchar_t *v180; // [rsp+3B8h] [rbp+2B0h]
  int v181; // [rsp+3C0h] [rbp+2B8h]
  int v182; // [rsp+3C4h] [rbp+2BCh]

  v4 = 0;
  v6 = *(_DWORD *)(a1 + 400);
  v7 = a3;
  v8 = a2;
  v63 = a4;
  v65 = a2;
  SystemTimeAsFileTime = 0;
  v82 = 0;
  v89 = 0;
  v88 = 0;
  if ( v6 )
  {
    v9 = (unsigned int)(v6 - 1);
    if ( (_DWORD)v9 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v9, a2, a3);
  }
  v10 = *(_DWORD *)(a1 + 400);
  if ( v10 )
  {
    v11 = (unsigned int)(v10 - 1);
    if ( (_DWORD)v11 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v11, a2, a3);
  }
  v12 = *(unsigned int *)(a1 + 400);
  if ( (_DWORD)v12 )
  {
    v12 = (unsigned int)(v12 - 1);
    if ( (_DWORD)v12 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v12, a2, a3);
  }
  v13 = *(_DWORD *)(a1 + 400);
  if ( !v13 )
  {
    v14 = *(__int64 **)(a1 + 424);
    goto LABEL_17;
  }
  if ( v13 == 2 )
  {
    v14 = *(__int64 **)(a1 + 440);
LABEL_17:
    v15 = (const wchar_t *)v14;
    goto LABEL_18;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(v12, a2, a3);
  v12 = *(unsigned int *)(a1 + 400);
  v14 = (__int64 *)MEMORY[8];
  v15 = (const wchar_t *)MEMORY[8];
  if ( (_DWORD)v12 )
  {
    v12 = (unsigned int)(v12 - 1);
    if ( (_DWORD)v12 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v12, a2, a3);
  }
LABEL_18:
  if ( (*(_DWORD *)(a1 + 400) & 0xFFFFFFFD) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, a2, a3);
  v16 = *(__int64 **)(a1 + 392);
  v17 = &qword_1800A1670;
  v18 = *(_QWORD *)(a1 + 72);
  v61 = v18;
  if ( v16 )
    v17 = v16;
  v19 = *(_DWORD *)(v18 + 24);
  v20 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 572LL) != 0 ? 8 : 0;
  if ( (v19 & 0x400) == 0
    || ((v21 = *(_DWORD *)(a1 + 400)) == 0 || v21 == 2)
    && (v19 & 0x2000) != 0
    && *(_DWORD *)(*(_QWORD *)(a1 + 80) + 572LL) )
  {
    v20 |= 4u;
  }
  v22 = *((_DWORD *)v8 + 34);
  v23 = v20 | 0x10;
  v89 = *v8;
  if ( !v7 )
    v23 = v20;
  v24 = v23 | 1;
  if ( (v22 & 0x80u) == 0 )
    v24 = v23;
  v25 = v24 | 2;
  if ( (v22 & 0x100) == 0 )
    v25 = v24;
  LOWORD(v62) = v25;
  v88 = *(_OWORD *)(a1 + 32);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  IsUserActive = BipIsUserActive(
                   *((unsigned int *)v8 + 35),
                   *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 8) + 80LL) + 24LL));
  v27 = *((_QWORD *)v8 + 9);
  v59 = IsUserActive;
  if ( v27 )
  {
    v28 = *(_QWORD *)(v27 + 40);
    Heap = (__int64 *)RtlAllocateHeap(BipHeap, 0, 0x1D0u);
    v30 = Heap;
    if ( Heap )
    {
      v31 = *(_QWORD *)(v28 + 16) + 160LL;
      v60 = 464;
      PsmCreateKey(v31, v28 + 60, Heap, &v60);
      v4 = v30;
    }
    v8 = v65;
  }
  IsWorkItemPackageImportant = BipEnergyBudgetIsWorkItemPackageImportant(qword_1800C45C0);
  RtlQueryUnbiasedInterruptTime(&v82);
  v32 = -1;
  if ( (unsigned int)dword_1800C3098 > 4
    && (qword_1800C30A8 & 0x400000000003LL) != 0
    && (qword_1800C30B0 & 0x400000000003LL) == qword_1800C30B0 )
  {
    v95 = 16;
    v94 = v61 + 32;
    v96 = &v88;
    v98 = &v89;
    v33 = *((_QWORD *)v8 + 8);
    v97 = 16;
    v99 = 16;
    v34 = (__int64 *)(*(_QWORD *)(v33 + 80) + 160LL);
    if ( *(_QWORD *)(v33 + 80) == -160 )
    {
      v38 = &qword_1800A1670;
      v37 = 2;
      v34 = &qword_1800A1670;
    }
    else
    {
      v35 = -1;
      do
        v36 = *((_WORD *)v34 + ++v35) == 0;
      while ( !v36 );
      v37 = 2 * v35 + 2;
      v38 = &qword_1800A1670;
    }
    v100 = v34;
    v101 = v37;
    v102 = 0;
    if ( v14 )
    {
      v39 = -1;
      do
        v36 = *((_WORD *)v14 + ++v39) == 0;
      while ( !v36 );
      v40 = 2 * v39 + 2;
    }
    else
    {
      v14 = &qword_1800A1670;
      v40 = 2;
    }
    v103 = v14;
    v104 = v40;
    v105 = 0;
    if ( v17 )
    {
      v41 = -1;
      do
        v36 = *((_WORD *)v17 + ++v41) == 0;
      while ( !v36 );
      v42 = 2 * v41 + 2;
    }
    else
    {
      v17 = &qword_1800A1670;
      v42 = 2;
    }
    v43 = *(_DWORD *)(a1 + 400);
    v107 = v42;
    v109 = &v63;
    v106 = v17;
    v44 = v61;
    v108 = 0;
    v110 = 4;
    v112 = 4;
    v78 = *(_DWORD *)(v61 + 580);
    v111 = &v78;
    v113 = &v79;
    v115 = v8 + 27;
    v117 = (__int64)v8 + 440;
    v119 = v8 + 28;
    v121 = (__int64)v8 + 456;
    v123 = v8 + 29;
    p_SystemTimeAsFileTime = &SystemTimeAsFileTime;
    v83 = v82 - *((_QWORD *)v8 + 63);
    v127 = &v83;
    v80 = *(_DWORD *)(a1 + 404);
    v129 = &v80;
    v84 = *((_QWORD *)v8 + 59);
    v131 = &v84;
    v66 = *((unsigned __int8 *)v8 + 480);
    v133 = &v66;
    v67 = *((_DWORD *)v8 + 125);
    v135 = &v67;
    LOWORD(v60) = *((_WORD *)v8 + 248);
    v137 = &v60;
    v79 = v43;
    v114 = 4;
    v116 = 8;
    v118 = 8;
    v120 = 8;
    v122 = 8;
    v124 = 8;
    v126 = 8;
    v128 = 8;
    v130 = 4;
    v132 = 8;
    v134 = 4;
    v136 = 4;
    v138 = 2;
    if ( v4 )
    {
      v38 = v4;
      v45 = -1;
      do
        v36 = *((_WORD *)v4 + ++v45) == 0;
      while ( !v36 );
      v46 = 2 * v45 + 2;
    }
    else
    {
      v46 = 2;
    }
    v139 = v38;
    v140 = v46;
    v141 = 0;
    if ( v43 )
    {
      v47 = 1;
      if ( v43 != 2 )
        v47 = 4;
    }
    else
    {
      v47 = *(_DWORD *)(a1 + 448);
    }
    v68 = v47;
    v142 = &v68;
    v85 = *((_QWORD *)v8 + 40);
    v144 = &v85;
    v69 = *(_DWORD *)(a1 + 408);
    v146 = &v69;
    v70 = *(_DWORD *)(a1 + 24);
    v148 = &v70;
    v71 = *(_DWORD *)(v61 + 24);
    v150 = &v71;
    v72 = *((_DWORD *)v8 + 122);
    v152 = &v72;
    v73 = *((unsigned __int8 *)v8 + 481);
    v154 = &v73;
    v74 = IsWorkItemPackageImportant;
    v156 = &v74;
    v75 = *((unsigned __int8 *)v8 + 483);
    v158 = &v75;
    v76 = *((unsigned __int8 *)v8 + 484);
    v160 = &v76;
    v77 = *((unsigned __int8 *)v8 + 482);
    v162 = &v77;
    v48 = *(_QWORD *)(a1 + 192);
    v143 = 4;
    v145 = 8;
    v147 = 4;
    v149 = 4;
    v151 = 4;
    v153 = 4;
    v155 = 4;
    v157 = 4;
    v159 = 4;
    v161 = 4;
    v163 = 4;
    if ( !v48 || (v49 = 1, !*(_QWORD *)(a1 + 200)) )
      v49 = 0;
    LODWORD(v64) = v49;
    v165 = 4;
    v164 = &v64;
    LODWORD(v65) = v59;
    v166 = &v65;
    v168 = &v86;
    *(_DWORD *)&EventDescriptor.Level = 4;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v167 = 4;
    v86 = 0x1000000;
    v169 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0x400000000003LL;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v91 = &word_1800B05C6;
    UserData.Reserved = 2;
    v92 = 563;
    v93 = 1;
    LODWORD(v61) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0x26u, &UserData);
  }
  else
  {
    v44 = v61;
  }
  v50 = (MEMORY[0x7FFE0008] - *((_QWORD *)v8 + 7) - MEMORY[0x7FFE03B0]) / 0x2710uLL;
  if ( *(_QWORD *)(a1 + 80) )
    *(_QWORD *)(a1 + 512) += v50;
  BipEnergyBudgetRecordTaskStats(qword_1800C45C0, 0);
  result = byte_1800C3C01 & 1;
  LOBYTE(v61) = byte_1800C3C01 & 1;
  if ( (byte_1800C3C01 & 1) != 0 )
  {
    v52 = *((_WORD *)v8 + 77);
    v53 = *((_WORD *)v8 + 76);
    LODWORD(v61) = v50;
    v172 = 4;
    if ( v53 > 0xFFu )
      LOBYTE(v53) = -1;
    v174 = 4;
    LOBYTE(v60) = v53;
    v54 = (const wchar_t *)(v44 + 192);
    v176 = 4;
    if ( v52 > 0xFFu )
      LOBYTE(v52) = -1;
    BYTE1(v60) = v52;
    v55 = 10;
    HIWORD(v60) = v62;
    LODWORD(v64) = *(_DWORD *)(v44 + 580);
    LODWORD(v65) = v60;
    v171 = &v61;
    v173 = &v65;
    v175 = &v64;
    if ( v44 == -192 )
    {
      v57 = 10;
      v54 = L"NULL";
    }
    else
    {
      v56 = -1;
      do
        v36 = v54[++v56] == 0;
      while ( !v36 );
      v57 = 2 * v56 + 2;
    }
    v177 = v54;
    v178 = v57;
    v179 = 0;
    if ( v15 )
    {
      do
        v36 = v15[++v32] == 0;
      while ( !v36 );
      v55 = 2 * v32 + 2;
    }
    else
    {
      v15 = L"NULL";
    }
    v181 = v55;
    v180 = v15;
    v182 = 0;
    result = McGenEventWrite_EventWriteTransfer(v54, TaskCompletionPerfTrack, 0, 6, v170);
  }
  if ( v4 )
    return RtlFreeHeap(BipHeap, 0, v4);
  return result;
}

```

## disassembly

```asm
0x18000e610  mov     r11, rsp
0x18000e613  push    rbp
0x18000e614  push    r12
0x18000e616  lea     rbp, [r11-308h]
0x18000e61d  sub     rsp, 3F8h
0x18000e624  mov     rax, cs:__security_cookie
0x18000e62b  xor     rax, rsp
0x18000e62e  mov     [rbp+300h+var_40], rax
0x18000e635  mov     [r11+18h], rbx
0x18000e639  xor     r12d, r12d
0x18000e63c  mov     [r11-18h], rsi
0x18000e640  xorps   xmm0, xmm0
0x18000e643  mov     [r11-20h], rdi
0x18000e647  mov     rbx, rcx
0x18000e64a  mov     ecx, [rcx+190h]
0x18000e650  movzx   edi, r8b
0x18000e654  mov     [r11-28h], r13
0x18000e658  mov     r13, rdx
0x18000e65b  mov     [r11-38h], r15
0x18000e65f  mov     [rsp+400h+var_3BC], r9d
0x18000e664  mov     qword ptr [rsp+400h+var_3B0], rdx
0x18000e669  mov     qword ptr [rbp+300h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18000e66d  mov     [rbp+300h+var_360], r12
0x18000e671  movups  [rbp+300h+var_318], xmm0
0x18000e675  movups  [rbp+300h+var_328], xmm0
0x18000e679  test    ecx, ecx
0x18000e67b  jz      short loc_18000E68C
0x18000e67d  sub     ecx, 1
0x18000e680  jz      short loc_18000E687
0x18000e682  cmp     ecx, 1
0x18000e685  jz      short loc_18000E68C
0x18000e687  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e68c  mov     ecx, [rbx+190h]
0x18000e692  test    ecx, ecx
0x18000e694  jz      short loc_18000E6A5
0x18000e696  sub     ecx, 1
0x18000e699  jz      short loc_18000E6A0
0x18000e69b  cmp     ecx, 1
0x18000e69e  jz      short loc_18000E6A5
0x18000e6a0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e6a5  mov     ecx, [rbx+190h]
0x18000e6ab  test    ecx, ecx
0x18000e6ad  jz      short loc_18000E6BE
0x18000e6af  sub     ecx, 1
0x18000e6b2  jz      short loc_18000E6B9
0x18000e6b4  cmp     ecx, 1
0x18000e6b7  jz      short loc_18000E6BE
0x18000e6b9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e6be  mov     eax, [rbx+190h]
0x18000e6c4  mov     esi, 8
0x18000e6c9  mov     [rsp+400h+var_28], r14
0x18000e6d1  test    eax, eax
0x18000e6d3  jz      short loc_18000E709
0x18000e6d5  cmp     eax, 2
0x18000e6d8  jz      short loc_18000E700
0x18000e6da  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e6df  mov     ecx, [rbx+190h]
0x18000e6e5  mov     rsi, [rsi]
0x18000e6e8  mov     r14, rsi
0x18000e6eb  test    ecx, ecx
0x18000e6ed  jz      short loc_18000E713
0x18000e6ef  sub     ecx, 1
0x18000e6f2  jz      short loc_18000E6F9
0x18000e6f4  cmp     ecx, 1
0x18000e6f7  jz      short loc_18000E713
0x18000e6f9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e6fe  jmp     short loc_18000E713
0x18000e700  mov     rsi, [rbx+1B8h]
0x18000e707  jmp     short loc_18000E710
0x18000e709  mov     rsi, [rbx+1A8h]
0x18000e710  mov     r14, rsi
0x18000e713  test    dword ptr [rbx+190h], 0FFFFFFFDh
0x18000e71d  jz      short loc_18000E724
0x18000e71f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e724  mov     rax, [rbx+188h]
0x18000e72b  lea     r15, qword_1800A1670
0x18000e732  mov     rcx, [rbx+48h]
0x18000e736  test    rax, rax
0x18000e739  mov     qword ptr [rsp+400h+var_3C8], rcx
0x18000e73e  cmovnz  r15, rax
0x18000e742  mov     rax, [rbx+50h]
0x18000e746  mov     r9d, [rcx+18h]
0x18000e74a  mov     r10d, [rax+23Ch]
0x18000e751  mov     eax, r10d
0x18000e754  neg     eax
0x18000e756  sbb     ax, ax
0x18000e759  and     ax, 8
0x18000e75d  bt      r9d, 0Ah
0x18000e762  jnb     short loc_18000E797
0x18000e764  mov     edx, [rbx+190h]
0x18000e76a  mov     r8d, edx
0x18000e76d  test    edx, edx
0x18000e76f  jz      short loc_18000E78B
0x18000e771  sub     r8d, 1
0x18000e775  jz      short loc_18000E79B
0x18000e777  cmp     r8d, 1
0x18000e77b  jnz     short loc_18000E79B
0x18000e77d  test    edx, edx
0x18000e77f  jz      short loc_18000E78B
0x18000e781  sub     edx, r8d
0x18000e784  jz      short loc_18000E79B
0x18000e786  cmp     edx, r8d
0x18000e789  jnz     short loc_18000E79B
0x18000e78b  bt      r9d, 0Dh
0x18000e790  jnb     short loc_18000E79B
0x18000e792  test    r10d, r10d
0x18000e795  jz      short loc_18000E79B
0x18000e797  or      ax, 4
0x18000e79b  mov     r8d, [r13+88h]
0x18000e7a2  movzx   edx, ax
0x18000e7a5  movups  xmm0, xmmword ptr [r13+0]
0x18000e7aa  or      dx, 10h
0x18000e7ae  test    dil, dil
0x18000e7b1  movups  [rbp+300h+var_318], xmm0
0x18000e7b5  cmovz   dx, ax
0x18000e7b9  movzx   ecx, dx
0x18000e7bc  or      cx, 1
0x18000e7c0  test    r8b, 80h
0x18000e7c4  cmovz   cx, dx
0x18000e7c8  movzx   eax, cx
0x18000e7cb  or      ax, 2
0x18000e7cf  bt      r8d, 8
0x18000e7d4  cmovnb  ax, cx
0x18000e7d8  mov     word ptr [rsp+400h+var_3C0], ax
0x18000e7dd  movups  xmm0, xmmword ptr [rbx+20h]
0x18000e7e1  lea     rcx, [rbp+300h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000e7e5  movups  [rbp+300h+var_328], xmm0
0x18000e7e9  call    cs:__imp_GetSystemTimeAsFileTime
0x18000e7ef  mov     rax, [r13+40h]
0x18000e7f3  mov     ecx, [r13+8Ch]
0x18000e7fa  mov     rdx, [rax+50h]
0x18000e7fe  mov     rdx, [rdx+18h]
0x18000e802  call    BipIsUserActive
0x18000e807  mov     rcx, [r13+48h]
0x18000e80b  mov     byte ptr [rsp+400h+var_3D0+1], al
0x18000e80f  test    rcx, rcx
0x18000e812  jz      short loc_18000E862
0x18000e814  mov     r13, [rcx+28h]
0x18000e818  xor     edx, edx; Flags
0x18000e81a  mov     rcx, cs:BipHeap; HeapHandle
0x18000e821  mov     r8d, 1D0h; Size
0x18000e827  call    cs:__imp_RtlAllocateHeap
0x18000e82d  mov     rdi, rax
0x18000e830  test    rax, rax
0x18000e833  jz      short loc_18000E85D
0x18000e835  mov     rcx, [r13+10h]
0x18000e839  lea     rdx, [r13+3Ch]
0x18000e83d  add     rcx, 0A0h
0x18000e844  mov     dword ptr [rsp+400h+var_3D0+4], 1D0h
0x18000e84c  lea     r9, [rsp+400h+var_3D0+4]
0x18000e851  mov     r8, rax
0x18000e854  call    cs:__imp_PsmCreateKey
0x18000e85a  mov     r12, rdi
0x18000e85d  mov     r13, qword ptr [rsp+400h+var_3B0]
0x18000e862  mov     rcx, cs:qword_1800C45C0; struct _BI_LOCK *
0x18000e869  mov     rdx, rbx
0x18000e86c  call    BipEnergyBudgetIsWorkItemPackageImportant
0x18000e871  lea     rcx, [rbp+300h+var_360]
0x18000e875  mov     byte ptr [rsp+400h+var_3D0], al
0x18000e879  call    cs:__imp_RtlQueryUnbiasedInterruptTime
0x18000e87f  mov     ecx, cs:dword_1800C3098
0x18000e885  mov     r9d, 4
0x18000e88b  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000e892  cmp     ecx, r9d
0x18000e895  jbe     loc_18000EDE8
0x18000e89b  mov     rdx, cs:qword_1800C30B0
0x18000e8a2  mov     r11, 400000000003h
0x18000e8ac  mov     rcx, cs:qword_1800C30A8
0x18000e8b3  test    r11, rcx
0x18000e8b6  jz      loc_18000EDE8
0x18000e8bc  mov     rax, rdx
0x18000e8bf  and     rax, r11
0x18000e8c2  cmp     rax, rdx
0x18000e8c5  jnz     loc_18000EDE8
0x18000e8cb  mov     rax, qword ptr [rsp+400h+var_3C8]
0x18000e8d0  xor     r8d, r8d; ActivityId
0x18000e8d3  add     rax, 20h ; ' '
0x18000e8d7  mov     [rbp+300h+var_2D8], 10h
0x18000e8df  mov     [rbp+300h+var_2E0], rax
0x18000e8e3  lea     rax, [rbp+300h+var_328]
0x18000e8e7  mov     [rbp+300h+var_2D0], rax
0x18000e8eb  lea     rax, [rbp+300h+var_318]
0x18000e8ef  mov     [rbp+300h+var_2C0], rax
0x18000e8f3  mov     rax, [r13+40h]
0x18000e8f7  mov     [rbp+300h+var_2C8], 10h
0x18000e8ff  mov     [rbp+300h+var_2B8], 10h
0x18000e907  mov     rcx, [rax+50h]
0x18000e90b  add     rcx, 0A0h
0x18000e912  jz      short loc_18000E93C
0x18000e914  mov     rax, rdi
0x18000e917  nop     word ptr [rax+rax+00000000h]
0x18000e920  cmp     [rcx+rax*2+2], r8w
0x18000e926  lea     rax, [rax+1]
0x18000e92a  jnz     short loc_18000E920
0x18000e92c  lea     eax, ds:2[rax*2]
0x18000e933  lea     rdx, qword_1800A1670
0x18000e93a  jmp     short loc_18000E94B
0x18000e93c  lea     rdx, qword_1800A1670
0x18000e943  mov     eax, 2
0x18000e948  mov     rcx, rdx
0x18000e94b  mov     [rbp+300h+var_2B0], rcx
0x18000e94f  mov     [rbp+300h+var_2A8], eax
0x18000e952  mov     [rbp+300h+var_2A4], r8d
0x18000e956  test    rsi, rsi
0x18000e959  jz      short loc_18000E975
0x18000e95b  mov     rax, rdi
0x18000e95e  xchg    ax, ax
0x18000e960  cmp     [rsi+rax*2+2], r8w
0x18000e966  lea     rax, [rax+1]
0x18000e96a  jnz     short loc_18000E960
0x18000e96c  lea     eax, ds:2[rax*2]
0x18000e973  jmp     short loc_18000E97D
0x18000e975  mov     rsi, rdx
0x18000e978  mov     eax, 2
0x18000e97d  mov     [rbp+300h+var_2A0], rsi
0x18000e981  mov     [rbp+300h+var_298], eax
0x18000e984  mov     [rbp+300h+var_294], r8d
0x18000e988  test    r15, r15
0x18000e98b  jz      short loc_18000E9A5
0x18000e98d  mov     rax, rdi
0x18000e990  cmp     [r15+rax*2+2], r8w
0x18000e996  lea     rax, [rax+1]
0x18000e99a  jnz     short loc_18000E990
0x18000e99c  lea     eax, ds:2[rax*2]
0x18000e9a3  jmp     short loc_18000E9AD
0x18000e9a5  mov     r15, rdx
0x18000e9a8  mov     eax, 2
0x18000e9ad  mov     ecx, [rbx+190h]
0x18000e9b3  mov     [rbp+300h+var_288], eax
0x18000e9b6  mov     eax, [rsp+400h+var_3BC]
0x18000e9ba  mov     [rsp+400h+var_3BC], eax
0x18000e9be  lea     rax, [rsp+400h+var_3BC]
0x18000e9c3  mov     [rbp+300h+var_280], rax
0x18000e9ca  mov     [rbp+300h+var_290], r15
0x18000e9ce  mov     r15, qword ptr [rsp+400h+var_3C8]
0x18000e9d3  mov     [rbp+300h+var_284], r8d
0x18000e9d7  mov     [rbp+300h+var_278], r9
0x18000e9de  mov     [rbp+300h+var_268], r9
0x18000e9e5  mov     eax, [r15+244h]
0x18000e9ec  mov     [rbp+300h+var_378], eax
0x18000e9ef  lea     rax, [rbp+300h+var_378]
0x18000e9f3  mov     [rbp+300h+var_270], rax
0x18000e9fa  lea     rax, [rbp+300h+var_374]
0x18000e9fe  mov     [rbp+300h+var_260], rax
0x18000ea05  lea     rax, [r13+1B0h]
0x18000ea0c  mov     [rbp+300h+var_250], rax
0x18000ea13  lea     rax, [r13+1B8h]
0x18000ea1a  mov     [rbp+300h+var_240], rax
0x18000ea21  lea     rax, [r13+1C0h]
0x18000ea28  mov     [rbp+300h+var_230], rax
0x18000ea2f  lea     rax, [r13+1C8h]
0x18000ea36  mov     [rbp+300h+var_220], rax
0x18000ea3d  lea     rax, [r13+1D0h]
0x18000ea44  mov     [rbp+300h+var_210], rax
0x18000ea4b  lea     rax, [rbp+300h+SystemTimeAsFileTime]
0x18000ea4f  mov     [rbp+300h+var_200], rax
0x18000ea56  mov     rax, [rbp+300h+var_360]
0x18000ea5a  sub     rax, [r13+1F8h]
0x18000ea61  mov     [rbp+300h+var_358], rax
0x18000ea65  lea     rax, [rbp+300h+var_358]
0x18000ea69  mov     [rbp+300h+var_1F0], rax
0x18000ea70  mov     eax, [rbx+194h]
0x18000ea76  mov     [rbp+300h+var_370], eax
0x18000ea79  lea     rax, [rbp+300h+var_370]
0x18000ea7d  mov     [rbp+300h+var_1E0], rax
0x18000ea84  mov     rax, [r13+1D8h]
0x18000ea8b  mov     [rbp+300h+var_350], rax
0x18000ea8f  lea     rax, [rbp+300h+var_350]
0x18000ea93  mov     [rbp+300h+var_1D0], rax
0x18000ea9a  movzx   eax, byte ptr [r13+1E0h]
0x18000eaa2  mov     [rsp+400h+var_3A8], eax
0x18000eaa6  lea     rax, [rsp+400h+var_3A8]
0x18000eaab  mov     [rbp+300h+var_1C0], rax
0x18000eab2  mov     eax, [r13+1F4h]
0x18000eab9  mov     [rsp+400h+var_3A4], eax
0x18000eabd  lea     rax, [rsp+400h+var_3A4]
0x18000eac2  mov     [rbp+300h+var_1B0], rax
0x18000eac9  movzx   eax, word ptr [r13+1F0h]
0x18000ead1  mov     word ptr [rsp+400h+var_3D0+4], ax
0x18000ead6  lea     rax, [rsp+400h+var_3D0+4]
0x18000eadb  mov     [rbp+300h+var_1A0], rax
0x18000eae2  mov     [rbp+300h+var_374], ecx
0x18000eae5  mov     [rbp+300h+var_258], r9
0x18000eaec  mov     [rbp+300h+var_248], 8
0x18000eaf7  mov     [rbp+300h+var_238], 8
0x18000eb02  mov     [rbp+300h+var_228], 8
0x18000eb0d  mov     [rbp+300h+var_218], 8
0x18000eb18  mov     [rbp+300h+var_208], 8
0x18000eb23  mov     [rbp+300h+var_1F8], 8
0x18000eb2e  mov     [rbp+300h+var_1E8], 8
0x18000eb39  mov     [rbp+300h+var_1D8], r9
0x18000eb40  mov     [rbp+300h+var_1C8], 8
0x18000eb4b  mov     [rbp+300h+var_1B8], r9
0x18000eb52  mov     [rbp+300h+var_1A8], r9
0x18000eb59  mov     [rbp+300h+var_198], 2
0x18000eb64  test    r12, r12
0x18000eb67  jz      short loc_18000EB85
0x18000eb69  mov     rdx, r12
0x18000eb6c  mov     rax, rdi
0x18000eb6f  nop
  ... truncated ...
```
