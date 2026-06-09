# PerflibciLocalQueryCounterData

- ea: `0x180007020`
- end: `0x180008718`
- name: `PerflibciLocalQueryCounterData`
- size: `5880`
- prototype: `__int64 __fastcall(struct _PERF_QUERY *)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004140`
- `0x18000c6f0`

## callees

- `0x180002e40`
- `0x180006420`
- `0x180007020`
- `0x1800087cc`
- `0x180009000`
- `0x180009090`
- `0x1800092b0`
- `0x180009504`
- `0x180009884`
- `0x18003fd04`
- `0x18004165c`
- `0x180072042`
- `0x18007205a`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x1800071a3`
- `ntdll!NtSetInformationThread` at `0x1800071a3`
- `ntdll!NtQueryPerformanceCounter` at `0x18000766d`
- `ntdll!NtQueryPerformanceCounter` at `0x18000766d`
- `ntdll!RtlNtStatusToDosError` at `0x1800077f2`
- `ntdll!RtlNtStatusToDosError` at `0x1800077f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007654`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007654`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180007644`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180007644`
- `KERNEL32!LocalFree` at `0x180007346`
- `KERNEL32!LocalFree` at `0x18000757c`
- `KERNEL32!LocalFree` at `0x1800075b6`
- `KERNEL32!LocalFree` at `0x180007773`
- `KERNEL32!LocalFree` at `0x180007bfd`
- `KERNEL32!LocalFree` at `0x180007efc`
- `KERNEL32!LocalFree` at `0x180008349`
- `KERNEL32!LocalFree` at `0x1800083ae`
- `KERNEL32!LocalFree` at `0x180007346`
- `KERNEL32!LocalFree` at `0x18000757c`
- `KERNEL32!LocalFree` at `0x1800075b6`
- `KERNEL32!LocalFree` at `0x180007773`
- `KERNEL32!LocalFree` at `0x180007bfd`
- `KERNEL32!LocalFree` at `0x180007efc`
- `KERNEL32!LocalFree` at `0x180008349`
- `KERNEL32!LocalFree` at `0x1800083ae`
- `KERNEL32!CompareStringOrdinal` at `0x1800079ea`
- `KERNEL32!CompareStringOrdinal` at `0x1800079ea`
- `KERNEL32!SetLastError` at `0x180007b81`
- `KERNEL32!SetLastError` at `0x180007c24`
- `KERNEL32!SetLastError` at `0x180007b81`
- `KERNEL32!SetLastError` at `0x180007c24`
- `api-ms-win-core-pcw-l1-1-0!PcwSendNotification` at `0x1800077dd`
- `api-ms-win-core-pcw-l1-1-0!PcwSendNotification` at `0x1800077dd`

## pseudocode

```c
__int64 __fastcall PerflibciLocalQueryCounterData(struct _PERF_QUERY *a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  unsigned int v4; // esi
  __int64 v5; // r14
  struct _PERF_QUERY *v6; // rbp
  unsigned int v8; // ecx
  ULONG v9; // r12d
  __int64 v10; // rdx
  __int64 v11; // rax
  bool v12; // zf
  __int64 v13; // r13
  unsigned __int8 v14; // bl
  unsigned __int64 v15; // rdi
  unsigned int v16; // eax
  unsigned __int64 v17; // r12
  unsigned __int64 v18; // r8
  __int64 v19; // rbp
  __int64 v20; // r15
  int v21; // ecx
  _DWORD *v22; // rdx
  int v23; // r8d
  int v24; // ebx
  __int64 v25; // rdi
  __int64 v26; // r11
  __int64 CounterSet; // rax
  __int64 v28; // rsi
  bool v29; // r9
  unsigned int v30; // ebx
  char v31; // r10
  __int64 v32; // r14
  int v33; // eax
  __int64 v34; // rdi
  __int64 v35; // r12
  char v36; // al
  _DWORD *v37; // r12
  __int64 v38; // rdx
  _QWORD *v39; // rbp
  __int64 v40; // rbx
  unsigned int *v41; // rdi
  _QWORD *v42; // r15
  unsigned int v43; // r14d
  __int64 v44; // rsi
  unsigned int v45; // eax
  unsigned int *v46; // rdx
  unsigned int v47; // ecx
  int v48; // esi
  __int64 v49; // r14
  __int64 v50; // r15
  unsigned int v51; // ebx
  char *v52; // r13
  char *v53; // rax
  NTSTATUS v54; // eax
  unsigned int v55; // edx
  unsigned int *v56; // rcx
  unsigned int v57; // eax
  unsigned int v58; // ebp
  _DWORD *v59; // r14
  unsigned int v60; // eax
  int v61; // ecx
  __int64 v62; // r13
  __int64 v63; // rax
  unsigned int *v64; // rbx
  int v65; // ecx
  unsigned int v66; // r9d
  LARGE_INTEGER v67; // rdi
  unsigned int v68; // esi
  unsigned int v69; // r15d
  WCHAR *v70; // rdx
  __int64 v71; // r10
  bool v72; // cc
  unsigned int v73; // edx
  unsigned int i; // ecx
  unsigned int ***v75; // rcx
  unsigned int **v76; // rbp
  unsigned int *v77; // r12
  int v78; // esi
  const WCHAR *v79; // r14
  __int64 v80; // rbx
  int v81; // eax
  unsigned int ***v82; // rax
  DWORD v83; // ecx
  unsigned int v84; // ecx
  unsigned int v85; // eax
  unsigned int v86; // ebx
  unsigned int **v87; // rbp
  unsigned int ***v88; // rcx
  unsigned int *v89; // r14
  unsigned int *v90; // rax
  struct PERFLIBCI_RED_BLACK_NODE **QuadPart; // r10
  __int64 v92; // r10
  unsigned int v93; // eax
  __int64 v94; // rcx
  __int64 v95; // rax
  int v96; // eax
  __int64 v97; // rbx
  unsigned int v98; // esi
  _DWORD *v99; // rbx
  __int64 v100; // rdi
  unsigned int *v101; // r12
  LARGE_INTEGER v102; // r13
  __int64 v103; // r15
  unsigned int v104; // r10d
  unsigned int v105; // r9d
  __int64 v106; // rdx
  __int64 v107; // r8
  __int64 v108; // rax
  int v109; // edx
  __int64 v110; // rcx
  int v111; // eax
  double v112; // xmm0_8
  double v113; // xmm0_8
  int v114; // eax
  int v115; // eax
  __int64 v116; // rdx
  __int64 v117; // r8
  void *v118; // rbx
  __int64 v119; // rax
  double v120; // xmm1_8
  __int64 v121; // rcx
  unsigned int v122; // eax
  LARGE_INTEGER v123; // r14
  unsigned int v124; // eax
  _DWORD *v125; // r10
  __int64 v126; // rax
  unsigned int *v127; // rbx
  unsigned int v128; // r8d
  unsigned int v129; // r11d
  __int64 v130; // r9
  __int64 v131; // r15
  _DWORD *v132; // rcx
  int j; // eax
  __int64 v134; // r12
  unsigned int v135; // eax
  __int64 v136; // r15
  __int64 v137; // r14
  int v138; // r11d
  const WCHAR *v139; // r8
  __int64 v140; // rcx
  _QWORD *v141; // r10
  __int64 v142; // rdx
  _WORD *v143; // rax
  _WORD *v144; // rcx
  __int64 v145; // rdi
  void *v146; // r8
  __int64 v147; // rbp
  _DWORD *v148; // rbx
  _DWORD *v149; // r14
  unsigned int v150; // r13d
  _DWORD *v151; // r8
  int v152; // eax
  int v153; // eax
  double v154; // xmm0_8
  unsigned __int64 v155; // rcx
  __int64 v156; // rax
  int v157; // eax
  int v158; // eax
  int v159; // eax
  __int64 v160; // rax
  int v161; // ecx
  unsigned int v162; // ecx
  unsigned int v163; // ebx
  struct _PERF_INSTANCE_HEADER *v164; // rdx
  struct _PERF_COUNTER_DATA *v165; // r8
  ULONG v166; // eax
  int v167; // eax
  int v168; // edx
  const void *v169; // rdx
  size_t v170; // r8
  __int64 v171; // rax
  int v172; // eax
  __int64 v173; // rax
  unsigned int v174; // ecx
  int v175; // eax
  _DWORD *v176; // r8
  int v177; // eax
  double v178; // xmm1_8
  int bIgnoreCase; // [rsp+20h] [rbp-108h]
  bool v180; // [rsp+40h] [rbp-E8h]
  unsigned __int8 v181; // [rsp+41h] [rbp-E7h]
  char v182; // [rsp+41h] [rbp-E7h]
  unsigned int v183; // [rsp+44h] [rbp-E4h]
  int v184; // [rsp+48h] [rbp-E0h]
  unsigned int v185; // [rsp+48h] [rbp-E0h]
  __int64 v186; // [rsp+50h] [rbp-D8h]
  unsigned int *v187; // [rsp+50h] [rbp-D8h]
  LARGE_INTEGER Frequency; // [rsp+60h] [rbp-C8h] BYREF
  int v189; // [rsp+68h] [rbp-C0h]
  unsigned int *v190; // [rsp+70h] [rbp-B8h]
  _DWORD *v191; // [rsp+78h] [rbp-B0h]
  LARGE_INTEGER Counter; // [rsp+80h] [rbp-A8h] BYREF
  __int64 v193; // [rsp+88h] [rbp-A0h]
  void *Src; // [rsp+90h] [rbp-98h]
  __int64 v195; // [rsp+98h] [rbp-90h]
  int ThreadInformation; // [rsp+A0h] [rbp-88h] BYREF
  unsigned __int64 v197; // [rsp+A8h] [rbp-80h]
  _DWORD *v198; // [rsp+B0h] [rbp-78h]
  __int64 v199; // [rsp+B8h] [rbp-70h] BYREF
  unsigned int ***v200; // [rsp+C0h] [rbp-68h]
  void *v201; // [rsp+C8h] [rbp-60h]

  v4 = a3;
  v5 = a2;
  ThreadInformation = 0;
  v6 = a1;
  if ( !a4 )
    return 87;
  *a4 = 0;
  if ( a3 )
  {
    if ( !a2 )
      return 87;
    *(_BYTE *)a2 = 0;
    *(_BYTE *)(a3 - 1 + a2) = 0;
  }
  PerflibciNotifyQuery(a1);
  if ( !*((_QWORD *)v6 + 5) )
    return 14;
  v8 = 0;
  v9 = 0;
  for ( LODWORD(v191) = 0; v8 < *((_DWORD *)v6 + 12); ++v8 )
  {
    v10 = *((_QWORD *)v6 + 5);
    v11 = 32LL * v8;
    v12 = (*(_BYTE *)(v11 + v10 + 24) & 8) == 0;
    *(_QWORD *)(v11 + v10 + 16) = 232;
    if ( v12 )
      *(_QWORD *)(v11 + v10 + 8) = 0;
  }
  LODWORD(v13) = 48;
  v181 = PerfpBoostPriority(v8, &ThreadInformation);
  v14 = v181;
  if ( v4 >= 0x30 )
  {
    v183 = 0;
    Counter.QuadPart = 0;
    Frequency.QuadPart = 0;
    *(_QWORD *)v5 = 0;
    GetSystemTime((LPSYSTEMTIME)(v5 + 32));
    GetSystemTimeAsFileTime((LPFILETIME)(v5 + 16));
    NtQueryPerformanceCounter(&Counter, &Frequency);
    *(LARGE_INTEGER *)(v5 + 8) = Counter;
    *(LARGE_INTEGER *)(v5 + 24) = Frequency;
  }
  else
  {
    v183 = 8;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_98cc76a206513ba905b421ef2a045de0_Traceguids);
  PerfpCollectKernelData(v6);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_98cc76a206513ba905b421ef2a045de0_Traceguids);
  v15 = *((_QWORD *)v6 + 3);
  v197 = v15;
  if ( v15 )
  {
    do
    {
      if ( *(_DWORD *)(*(_QWORD *)(v15 + 8) + 32LL) != 1 && (*(_BYTE *)(v15 + 36) & 4) == 0 )
      {
        v48 = *(_DWORD *)(v15 + 28) + *((_DWORD *)v6 + 23);
        v49 = *(_QWORD *)(v15 + 16);
        v50 = *(_QWORD *)(v15 + 48);
        v51 = (*(unsigned __int16 *)(v15 + 32) << 16) | 4;
        v199 = -20000000;
        v52 = 0;
        do
        {
          LocalFree(v52);
          v53 = (char *)operator new(0x2000u, (const struct std::nothrow_t *)&std::nothrow);
          Counter.QuadPart = (LONGLONG)v53;
          v52 = v53;
          if ( !v53 )
            goto LABEL_163;
          memset_0(v53, 0, 0x2000u);
          bIgnoreCase = v48;
          v54 = PcwSendNotification(v50, v51, &v199, v49);
        }
        while ( v54 == -2147483643 );
        if ( !RtlNtStatusToDosError(v54) )
        {
          v55 = 8;
          do
          {
            v56 = (unsigned int *)&v52[v55];
            v187 = v56;
            v55 += *v56;
            v57 = v56[3];
            LODWORD(v193) = v55;
            if ( v57 == 4203 )
            {
              *(_DWORD *)(v15 + 36) |= 4u;
            }
            else if ( !v57 )
            {
              v58 = 16;
              v189 = 16;
              while ( v58 < *v56 )
              {
                v59 = (unsigned int *)((char *)v56 + v58);
                v198 = v59;
                v60 = v59[3];
                if ( v60 < *((_DWORD *)a1 + 12) )
                {
                  v61 = v59[1];
                  v62 = *((_QWORD *)a1 + 5) + 32LL * v60;
                  if ( v61 == 6 )
                  {
                    v63 = (unsigned int)v59[4];
                    v12 = *(_DWORD *)((char *)v59 + v63 + 20) == 0;
                    v64 = (_DWORD *)((char *)v59 + v63 + 16);
                    Frequency.QuadPart = (LONGLONG)(v59 + 4);
                    v190 = v64;
                    if ( !v12 )
                    {
                      if ( !*(_QWORD *)(v62 + 8) )
                      {
                        v94 = (unsigned int)(v63 + 24);
                        if ( (unsigned int)v63 < (unsigned int)v94 )
                        {
                          v95 = operator new(v94);
                          *(_QWORD *)(v62 + 8) = v95;
                          if ( v95 )
                          {
                            *(_QWORD *)(v95 + 16) = v95 + 24;
                            memcpy_0((void *)(v95 + 24), v59 + 4, (unsigned int)v59[4]);
                          }
                        }
                        if ( !*(_QWORD *)(v62 + 8) )
                        {
LABEL_157:
                          *(_QWORD *)(v62 + 16) = 14;
                          goto LABEL_158;
                        }
                      }
                      v65 = *v59;
                      *(_DWORD *)(v62 + 16) = *v59;
                      *(_DWORD *)(v62 + 20) = v59[1];
                      if ( v65 )
                        *(_DWORD *)(v62 + 16) = 0;
                      v66 = *v64;
                      if ( *v64 <= 8 )
                        goto LABEL_158;
                      v67 = Frequency;
                      v68 = 8;
                      while ( 2 )
                      {
                        v69 = 0;
                        v70 = (WCHAR *)((char *)v64 + v68);
                        Src = v70;
                        v71 = *(unsigned int *)v70;
                        v68 += v71;
                        v185 = v68;
                        v72 = v68 <= v66;
                        if ( v68 < v66 )
                        {
                          _mm_lfence();
                          v73 = *(_DWORD *)(v67.QuadPart + 4);
                          for ( i = 0; i < v73; v69 += *(unsigned int *)((char *)v64 + v68 + (unsigned __int64)v69 + 4) )
                            ++i;
                          v70 = (WCHAR *)Src;
                          v68 += v69;
                          v185 = v68;
                          v72 = v68 <= v66;
                        }
                        if ( !v72 || !v69 )
                          goto LABEL_148;
                        if ( ((*(_DWORD *)(v62 + 24) - 4) & 0xFFFFFFF7) == 0 )
                        {
                          LODWORD(v191) = v9 + 1;
                          *((_DWORD *)v70 + 1) = v9;
                        }
                        v75 = *(unsigned int ****)(v62 + 8);
                        v200 = v75;
                        if ( !v75 || !v70 || (v201 = (char *)v70 + v71) == 0 )
                        {
                          SetLastError(0xDu);
                          goto LABEL_148;
                        }
                        v76 = v75[1];
                        v77 = 0;
                        LODWORD(v195) = 0;
                        v78 = 0;
                        Frequency.QuadPart = (LONGLONG)(v75 + 1);
                        v79 = v70 + 4;
                        if ( v76 )
                        {
                          while ( 2 )
                          {
                            v80 = (__int64)(v76[4] + 2);
                            if ( v76[4] == (unsigned int *)-8LL )
                            {
                              v83 = 13;
                              goto LABEL_135;
                            }
                            v81 = CompareStringOrdinal(v79, -1, (LPCWCH)v76[4] + 8, -1, 1);
                            v78 = v81 - 2;
                            if ( v81 == 2 )
                            {
                              v93 = *(_DWORD *)(v80 + 4);
                              if ( *((_DWORD *)Src + 1) < v93 )
                              {
                                v78 = -1;
                                goto LABEL_348;
                              }
                              if ( *((_DWORD *)Src + 1) <= v93 )
                              {
                                v64 = v190;
                                v68 = v185;
                                if ( v76 )
                                  goto LABEL_148;
                                v83 = 87;
LABEL_152:
                                SetLastError(v83);
                                goto LABEL_148;
                              }
                              v78 = 1;
LABEL_132:
                              v82 = (unsigned int ***)(v76 + 1);
                            }
                            else
                            {
                              if ( v78 >= 0 )
                                goto LABEL_132;
LABEL_348:
                              v82 = (unsigned int ***)v76;
                            }
                            v77 = (unsigned int *)v76;
                            v76 = *v82;
                            if ( !*v82 )
                            {
                              v83 = v195;
LABEL_135:
                              if ( v83 )
                                goto LABEL_151;
                              v70 = (WCHAR *)Src;
                              break;
                            }
                            continue;
                          }
                        }
                        v84 = *(_DWORD *)v70 + 56;
                        if ( *(_DWORD *)v70 >= v84
                          || (v85 = v84 + v69, v69 > v84 + v69)
                          || v84 > v85
                          || (v86 = v84 + v69,
                              (v87 = (unsigned int **)operator new(v85, (const struct std::nothrow_t *)&std::nothrow)) == 0) )
                        {
                          v83 = 14;
LABEL_151:
                          v68 = v185;
                          v64 = v190;
                          goto LABEL_152;
                        }
                        memset_0(v87, 0, v86);
                        v88 = v200;
                        v89 = (unsigned int *)Src;
                        v87[4] = (unsigned int *)(v87 + 6);
                        v87[3] = (unsigned int *)*v88;
                        *v88 = v87;
                        v90 = v87[4];
                        v87[2] = v77;
                        *((_DWORD *)v87 + 10) = 1;
                        *v90 = v69;
                        memcpy_0(v87 + 7, v89, *v89);
                        memcpy_0((char *)v87 + *v89 + 56, v201, v69);
                        QuadPart = (struct PERFLIBCI_RED_BLACK_NODE **)Frequency.QuadPart;
                        if ( v77 )
                        {
                          if ( v78 < 0 )
                            *(_QWORD *)v77 = v87;
                          else
                            *((_QWORD *)v77 + 1) = v87;
                        }
                        else
                        {
                          *(_QWORD *)Frequency.QuadPart = v87;
                        }
                        PerflibciInsertRedBlackNode(QuadPart, (struct PERFLIBCI_RED_BLACK_NODE *)v87);
                        v64 = v190;
                        v68 = v185;
                        *(_DWORD *)(*(_QWORD *)v92 + 40LL) = 0;
LABEL_148:
                        v66 = *v64;
                        v9 = (unsigned int)v191;
                        if ( v68 < *v64 )
                          continue;
                        break;
                      }
                      v15 = v197;
                      v59 = v198;
                      v58 = v189;
                    }
LABEL_158:
                    v56 = v187;
                    goto LABEL_159;
                  }
                  if ( v61 )
                  {
                    switch ( v61 )
                    {
                      case 1:
                        v118 = *(void **)(v62 + 8);
                        v171 = operator new((unsigned int)v59[5]);
                        *(_QWORD *)(v62 + 8) = v171;
                        if ( !v171 )
                        {
LABEL_214:
                          v56 = v187;
                          if ( v118 )
                            *(_QWORD *)(v62 + 8) = v118;
                          else
                            *(_QWORD *)(v62 + 16) = 14;
                          goto LABEL_159;
                        }
                        LocalFree(v118);
                        v169 = v59 + 4;
                        *(_DWORD *)(v62 + 16) = *v59;
                        *(_DWORD *)(v62 + 20) = v59[1];
                        v170 = (unsigned int)v59[5];
LABEL_309:
                        memcpy_0(*(void **)(v62 + 8), v169, v170);
                        v56 = v187;
                        if ( *(_DWORD *)(v62 + 16) )
                          *(_DWORD *)(v62 + 16) = 0;
                        goto LABEL_159;
                      case 2:
                        v118 = *(void **)(v62 + 8);
                        v119 = operator new((unsigned int)v59[2]);
                        *(_QWORD *)(v62 + 8) = v119;
                        if ( !v119 )
                          goto LABEL_214;
                        LocalFree(v118);
                        v169 = v59;
                        *(_DWORD *)(v62 + 16) = *v59;
                        *(_DWORD *)(v62 + 20) = v59[1];
                        v170 = (unsigned int)v59[2];
                        goto LABEL_309;
                      case 4:
                        if ( v59[5] )
                        {
                          if ( !*(_QWORD *)(v62 + 8) )
                          {
                            v160 = operator new(24);
                            *(_QWORD *)(v62 + 8) = v160;
                            if ( !v160 )
                              goto LABEL_157;
                          }
                          v161 = *v59;
                          *(_DWORD *)(v62 + 16) = *v59;
                          *(_DWORD *)(v62 + 20) = v59[1];
                          if ( v161 )
                            *(_DWORD *)(v62 + 16) = 0;
                          v162 = v59[4];
                          if ( v162 > 8 )
                          {
                            v163 = 8;
                            do
                            {
                              v164 = (struct _PERF_INSTANCE_HEADER *)((char *)v59 + v163 + 16);
                              v163 += v164->Size;
                              if ( v163 <= v162 )
                              {
                                v165 = (struct _PERF_COUNTER_DATA *)((char *)v59 + v163 + 16);
                                v163 += v165->dwSize;
                                if ( v163 <= v162 )
                                {
                                  if ( ((*(_DWORD *)(v62 + 24) - 4) & 0xFFFFFFF7) == 0 )
                                  {
                                    v166 = v9++;
                                    v164->InstanceId = v166;
                                  }
                                  PerflibciFindOutputInstance(
                                    *(struct PERFLIBCI_MULTI_INSTS **)(v62 + 8),
                                    v164,
                                    v165,
                                    v165->dwSize,
                                    bIgnoreCase);
                                }
                              }
                              v162 = v59[4];
                            }
                            while ( v163 < v162 );
                            LODWORD(v191) = v9;
                          }
                        }
                        goto LABEL_158;
                    }
                  }
                  if ( v61 )
                    *v59 = 13;
                  v172 = *(_DWORD *)(v62 + 16);
                  if ( v172 && v172 != *v59 )
                  {
                    v12 = (*(_BYTE *)(v62 + 24) & 8) == 0;
                    *(_DWORD *)(v62 + 16) = *v59;
                    v56 = v187;
                    *(_DWORD *)(v62 + 20) = v59[1];
                    if ( v12 )
                      *(_QWORD *)(v62 + 8) = 0;
                    goto LABEL_159;
                  }
                  goto LABEL_158;
                }
LABEL_159:
                v96 = v59[2];
                v58 += v96;
                v189 = v58;
                if ( !v96 )
                  break;
              }
              v52 = (char *)Counter.QuadPart;
              v55 = v193;
            }
          }
          while ( v55 < 0x2000 );
        }
        LocalFree(v52);
LABEL_163:
        v6 = a1;
      }
      v15 = *(_QWORD *)v15;
      v197 = v15;
    }
    while ( v15 );
    v14 = v181;
    LODWORD(v13) = 48;
    v5 = a2;
    v4 = a3;
  }
  if ( v14 )
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPriority, &ThreadInformation, 4u);
  if ( *((_DWORD *)v6 + 12) )
  {
    v16 = 0;
    v17 = v4;
    v189 = 0;
    v197 = v4;
    v18 = v4;
    while ( 1 )
    {
      v19 = *((_QWORD *)v6 + 5);
      v20 = 32LL * v16;
      Frequency.QuadPart = v20;
      v193 = v19;
      v21 = *(_DWORD *)(v20 + v19 + 20);
      switch ( v21 )
      {
        case 0:
          goto LABEL_27;
        case 1:
          v22 = *(_DWORD **)(v20 + v19 + 8);
          if ( !v22 )
          {
            if ( (unsigned __int64)(unsigned int)v13 + 16 <= v18 )
            {
              *(_QWORD *)((unsigned int)v13 + v5) = 232;
              *(_QWORD *)((unsigned int)v13 + v5 + 8) = 16;
              goto LABEL_31;
            }
            goto LABEL_216;
          }
          v23 = v22[1] + 16;
          v24 = v23 + v13;
          if ( v23 + (int)v13 > v4 )
          {
LABEL_207:
            v183 = 8;
          }
          else
          {
            *(_DWORD *)((unsigned int)v13 + v5) = *(_DWORD *)(v20 + v19 + 16);
            *(_DWORD *)((unsigned int)v13 + v5 + 4) = *(_DWORD *)(v20 + v19 + 20);
            *(_DWORD *)((unsigned int)v13 + v5 + 8) = v23;
            *(_DWORD *)((unsigned int)v13 + v5 + 12) = 0;
            memcpy_0((void *)(v5 + (unsigned int)v13 + 16LL), v22, (unsigned int)v22[1]);
          }
LABEL_42:
          LODWORD(v13) = v24;
          LocalFree(*(HLOCAL *)(v20 + v19 + 8));
          *(_QWORD *)(v20 + v19 + 8) = 0;
          goto LABEL_43;
        case 2:
          v116 = *(_QWORD *)(v20 + v19 + 8);
          if ( v116 )
          {
            v117 = *(unsigned int *)(v116 + 8);
            v24 = v117 + v13;
            if ( (int)v117 + (int)v13 > v4 )
              goto LABEL_207;
            *(_DWORD *)((unsigned int)v13 + v5) = *(_DWORD *)(v20 + v19 + 16);
            v167 = *(_DWORD *)(v20 + v19 + 20);
            *(_DWORD *)((unsigned int)v13 + v5 + 8) = v117;
            *(_DWORD *)((unsigned int)v13 + v5 + 4) = v167;
            *(_DWORD *)((unsigned int)v13 + v5 + 12) = 0;
            memcpy_0((void *)(v5 + (unsigned int)v13 + 16LL), (const void *)(v116 + 16), v117 - 16);
            goto LABEL_42;
          }
          if ( (unsigned __int64)(unsigned int)v13 + 16 > v17 )
          {
            v183 = 8;
          }
          else
          {
            *(_QWORD *)((unsigned int)v13 + v5) = 232;
            *(_QWORD *)((unsigned int)v13 + v5 + 8) = 16;
          }
          LODWORD(v13) = v13 + 16;
LABEL_43:
          v18 = v17;
          goto LABEL_32;
      }
      if ( v21 != 4 && v21 != 6 )
      {
LABEL_27:
        if ( (v21 & 0xFFFFFFF9) != 0 )
          *(_DWORD *)(v20 + v19 + 16) = 13;
        if ( (unsigned __int64)(unsigned int)v13 + 16 <= v18 )
        {
          *(_DWORD *)((unsigned int)v13 + v5) = *(_DWORD *)(v20 + v19 + 16);
          *(_DWORD *)((unsigned int)v13 + v5 + 4) = 0;
          *(_QWORD *)((unsigned int)v13 + v5 + 8) = 16;
LABEL_31:
          LODWORD(v13) = v13 + 16;
LABEL_32:
          v6 = a1;
          goto LABEL_33;
        }
LABEL_216:
        v183 = 8;
        goto LABEL_31;
      }
      v25 = *(_QWORD *)(v20 + v19);
      v26 = 0;
      v190 = 0;
      v195 = v25;
      Counter.QuadPart = 0;
      if ( !v25 )
      {
        v28 = 0;
        v29 = 0;
        goto LABEL_48;
      }
      CounterSet = PerflibciCreateOrFindCounterSet((void *)v25, 0, 0, 0, 0);
      v28 = CounterSet;
      if ( !CounterSet )
        break;
      if ( (*(_BYTE *)(CounterSet + 88) & 4) == 0 )
      {
        v29 = 0;
        v26 = 0;
LABEL_48:
        v30 = 0;
        v180 = 0;
        goto LABEL_49;
      }
      v26 = 0;
      v29 = 1;
      v180 = 1;
      if ( *(_DWORD *)(v25 + 24) == -1 )
        v30 = *(_DWORD *)(CounterSet + 128);
      else
        v30 = 1;
LABEL_49:
      if ( *(_DWORD *)(v25 + 20) > 0x28u && PerflibciWildcardInstance((const unsigned __int16 *)(v25 + 40)) )
      {
        v31 = 1;
        v182 = 1;
        if ( v29 )
        {
          v168 = *(unsigned __int16 *)(v25 + 40) - 42;
          if ( *(_WORD *)(v25 + 40) == 42 )
            v168 = *(unsigned __int16 *)(v25 + 42) - (unsigned __int16)v26;
          v29 = v168 == 0;
          v180 = v168 == 0;
        }
      }
      else
      {
        v31 = 0;
        v182 = 0;
      }
      Src = (void *)v17;
      if ( (unsigned __int64)(unsigned int)v13 + 16 > v17 )
      {
        v32 = v26;
        v186 = v26;
        v183 = 8;
      }
      else
      {
        v32 = (unsigned int)v13 + v5;
        v186 = v32;
        *(_DWORD *)v32 = *(_DWORD *)(v20 + v19 + 16);
        *(_QWORD *)(v32 + 8) = 16;
        if ( v31 )
        {
          v33 = *(_DWORD *)(v20 + v19 + 20);
        }
        else
        {
          v175 = v26;
          LOBYTE(v175) = *(_DWORD *)(v20 + v19 + 20) == 6;
          v33 = v175 + 1;
        }
        *(_DWORD *)(v32 + 4) = v33;
      }
      v34 = *(_QWORD *)(v20 + v19 + 8);
      v13 = (unsigned int)(v13 + 16);
      v184 = v13;
      if ( *(_DWORD *)(v20 + v19 + 20) != 6 )
        goto LABEL_57;
      if ( !v34 )
      {
        v183 = 13;
LABEL_57:
        v35 = a2;
        goto LABEL_58;
      }
      v46 = *(unsigned int **)(v34 + 16);
      v35 = a2;
      v190 = v46;
      v47 = *v46;
      if ( *v46 + (unsigned int)v13 > a3 )
      {
        v183 = 8;
      }
      else
      {
        memcpy_0((void *)(a2 + (unsigned int)v13), v46, v47);
        v46 = v190;
        v29 = v180;
        v47 = *v190;
      }
      if ( v32 )
        *(_DWORD *)(v32 + 8) += v47;
      v13 = *v46 + (unsigned int)v13;
      v184 = v13;
LABEL_58:
      if ( !v29 )
        goto LABEL_59;
      Counter.QuadPart = 0;
      v121 = *((_QWORD *)a1 + 7);
      if ( !v121 )
        goto LABEL_327;
      v122 = *(_DWORD *)(v195 + 32);
      if ( *((_DWORD *)a1 + 16) <= v122 )
        goto LABEL_327;
      v123.QuadPart = v121 + 16LL * v122;
      Counter = v123;
      v124 = *(_DWORD *)(v123.QuadPart + 8);
      if ( v124 < v30 )
      {
        LocalFree(*(HLOCAL *)v123.QuadPart);
        v124 = 0;
        *(_QWORD *)v123.QuadPart = 0;
        *(_DWORD *)(v123.QuadPart + 8) = 0;
      }
      if ( *(_QWORD *)v123.QuadPart )
      {
        memset_0(*(void **)v123.QuadPart, 0, 24LL * v124);
      }
      else
      {
        v173 = operator new(saturated_mul(v30, 0x18u));
        v174 = 0;
        *(_QWORD *)v123.QuadPart = v173;
        if ( v173 )
          v174 = v30;
        *(_DWORD *)(v123.QuadPart + 8) = v174;
      }
      v125 = *(_DWORD **)v123.QuadPart;
      if ( !*(_QWORD *)v123.QuadPart )
      {
LABEL_327:
        v29 = 0;
        v180 = 0;
        goto LABEL_59;
      }
      v126 = v195;
      v127 = v190;
      *(_DWORD *)(v123.QuadPart + 12) = 0;
      v128 = *(_DWORD *)(v126 + 24);
      if ( v128 != -1 )
      {
        v129 = 1;
        v130 = 0;
LABEL_237:
        v131 = v126;
        do
        {
          if ( *(_DWORD *)(v131 + 24) == -1 )
            v128 = v127[v130 + 2];
          v132 = *(_DWORD **)(v28 + 120);
          for ( j = *(_DWORD *)(v28 + 128); j; --j )
          {
            if ( v128 == *v132 )
            {
              v125[2] = *v132;
              v125[3] = v132[8];
              v125 += 6;
              ++*(_DWORD *)(v123.QuadPart + 12);
              break;
            }
            v132 += 14;
          }
          v130 = (unsigned int)(v130 + 1);
        }
        while ( (unsigned int)v130 < v129 );
        v20 = Frequency.QuadPart;
        goto LABEL_247;
      }
      if ( v127 )
      {
        v129 = v127[1];
        v130 = 0;
        if ( v129 )
          goto LABEL_237;
      }
LABEL_247:
      if ( *(_DWORD *)(v123.QuadPart + 12) )
      {
        v29 = v180;
      }
      else
      {
        v29 = 0;
        v180 = 0;
      }
LABEL_59:
      v36 = v182;
      if ( v182 )
      {
        if ( v13 + 8 > v197 )
        {
          v37 = 0;
          v183 = 8;
        }
        else
        {
          v37 = (_DWORD *)((unsigned int)v13 + v35);
          *(_QWORD *)v37 = 8;
        }
        v38 = v186;
        v191 = v37;
        if ( v186 )
          *(_DWORD *)(v186 + 8) += 8;
        v36 = v182;
        LODWORD(v13) = v13 + 8;
        v184 = v13;
      }
      else
      {
        v38 = v186;
        v37 = 0;
        v191 = 0;
      }
      if ( *(_QWORD *)(v20 + v19 + 8) )
      {
        v39 = *(_QWORD **)v34;
        v40 = v193;
        if ( *(_QWORD *)v34 )
        {
          while ( 1 )
          {
            v41 = (unsigned int *)v39[4];
            v42 = (_QWORD *)v39[3];
            v198 = v42;
            if ( !v41 )
              goto LABEL_75;
            v43 = *v41;
            v44 = v41[2];
            if ( v36 )
              break;
LABEL_73:
            if ( v29 && !v183 )
            {
              v97 = v44 + 8;
              v98 = 0;
              v99 = (unsigned int *)((char *)v41 + v97);
              v100 = 0;
              if ( v43 )
              {
                v101 = v190;
                v102 = Counter;
                v103 = v195;
                while ( 1 )
                {
                  v104 = *(_DWORD *)(v103 + 24);
                  if ( v104 == -1 && v101 && (unsigned int)v100 < v101[1] )
                    v104 = v101[v100 + 2];
                  if ( v102.QuadPart )
                  {
                    if ( v104 != -1 )
                    {
                      if ( *(_QWORD *)v102.QuadPart )
                      {
                        v105 = *(_DWORD *)(v102.QuadPart + 12);
                        if ( v105 )
                        {
                          v106 = 0;
                          while ( 1 )
                          {
                            v107 = *(_QWORD *)v102.QuadPart + 24 * v106;
                            if ( *(_DWORD *)(v107 + 8) == v104 )
                              break;
                            v106 = (unsigned int)(v106 + 1);
                            if ( (unsigned int)v106 >= v105 )
                              goto LABEL_180;
                          }
                          if ( v107 )
                            break;
                        }
                      }
                    }
                  }
LABEL_180:
                  v108 = (unsigned int)v99[1];
                  v98 += v108;
                  if ( v98 < (unsigned int)v108 || v98 >= v43 )
                  {
                    LODWORD(v13) = v184;
                    v42 = v198;
                    v37 = v191;
                    goto LABEL_74;
                  }
                  v100 = (unsigned int)(v100 + 1);
                  v99 = (_DWORD *)((char *)v99 + v108);
                }
                v109 = *(_DWORD *)(v107 + 16);
                if ( !v109 )
                  *(_DWORD *)(v107 + 20) = *v99;
                if ( *v99 == 4 )
                {
                  v110 = (unsigned int)v99[2];
                }
                else if ( *v99 == 8 )
                {
                  v110 = *((_QWORD *)v99 + 1);
                }
                else
                {
                  v110 = 0;
                }
                v111 = *(_DWORD *)(v107 + 12);
                if ( v111 == 2 || (v114 = v111 - 1) == 0 )
                {
                  if ( v110 < 0 )
                    v112 = (double)(int)(v110 & 1 | ((unsigned __int64)v110 >> 1))
                         + (double)(int)(v110 & 1 | ((unsigned __int64)v110 >> 1));
                  else
                    v112 = (double)(int)v110;
                  v113 = v112 + *(double *)v107;
                  goto LABEL_193;
                }
                v115 = v114 - 2;
                if ( v115 )
                {
                  if ( v115 != 1 )
                    goto LABEL_194;
                  if ( v109 )
                  {
                    if ( v110 < 0 )
                      v113 = (double)(int)(v110 & 1 | ((unsigned __int64)v110 >> 1))
                           + (double)(int)(v110 & 1 | ((unsigned __int64)v110 >> 1));
                    else
                      v113 = (double)(int)v110;
                    if ( v113 <= *(double *)v107 )
                    {
                      *(_DWORD *)(v107 + 16) = v109 + 1;
                      goto LABEL_180;
                    }
LABEL_193:
                    *(double *)v107 = v113;
LABEL_194:
                    *(_DWORD *)(v107 + 16) = v109 + 1;
                    goto LABEL_180;
                  }
                }
                else if ( v109 )
                {
                  if ( v110 < 0 )
                    v120 = (double)(int)(v110 & 1 | ((unsigned __int64)v110 >> 1))
                         + (double)(int)(v110 & 1 | ((unsigned __int64)v110 >> 1));
                  else
                    v120 = (double)(int)v110;
                  if ( *(double *)v107 > v120 )
                  {
                    *(double *)v107 = v120;
                    *(_DWORD *)(v107 + 16) = v109 + 1;
                    goto LABEL_180;
                  }
                  goto LABEL_194;
                }
                if ( v110 < 0 )
                  v113 = (double)(int)(v110 & 1 | ((unsigned __int64)v110 >> 1))
                       + (double)(int)(v110 & 1 | ((unsigned __int64)v110 >> 1));
                else
                  v113 = (double)(int)v110;
                goto LABEL_193;
              }
            }
LABEL_74:
            v40 = v193;
LABEL_75:
            if ( (*(_BYTE *)(Frequency.QuadPart + v40 + 24) & 8) == 0 )
              LocalFree(v39);
            v38 = v186;
            v39 = v42;
            v29 = v180;
            v36 = v182;
            if ( !v42 )
            {
              v20 = Frequency.QuadPart;
              goto LABEL_79;
            }
          }
          if ( (unsigned int)v44 + v43 + (unsigned int)v13 > a3 )
          {
            v183 = 8;
            if ( v37 )
            {
              ++v37[1];
              *v37 += v43 + v41[2];
            }
            v45 = v41[2];
            if ( !v38 )
              goto LABEL_72;
          }
          else
          {
            memcpy_0((void *)(a2 + (unsigned int)v13), v41 + 2, (unsigned int)v44 + v43);
            ++v37[1];
            v38 = v186;
            *v37 += v43 + v41[2];
            v45 = v41[2];
          }
          *(_DWORD *)(v38 + 8) += v43 + v45;
LABEL_72:
          v29 = v180;
          LODWORD(v13) = v43 + v41[2] + v13;
          v184 = v13;
          goto LABEL_73;
        }
LABEL_79:
        if ( (*(_BYTE *)(v20 + v40 + 24) & 8) == 0 )
        {
          LocalFree(*(HLOCAL *)(v20 + v40 + 8));
          *(_QWORD *)(v20 + v40 + 8) = 0;
        }
      }
      v6 = a1;
      if ( v180 )
      {
        v134 = *((_QWORD *)a1 + 7);
        if ( v134 )
        {
          v135 = *(_DWORD *)(v195 + 32);
          if ( *((_DWORD *)a1 + 16) > v135 )
          {
            v136 = 2LL * v135;
            if ( *(_QWORD *)(v134 + 16LL * v135) )
            {
              if ( *(_DWORD *)(v134 + 16LL * v135 + 12) )
              {
                v137 = a2;
                if ( v182 )
                {
                  v138 = v13 + 24;
                  if ( (int)v13 + 24 > a3 )
                  {
                    v183 = 8;
                    LODWORD(v13) = v13 + 24;
                    v184 = v138;
                  }
                  else
                  {
                    v139 = L"_Total";
                    v140 = 2147483646;
                    v141 = (_QWORD *)(a2 + (unsigned int)v13);
                    v142 = 7;
                    *v141 = 24;
                    v143 = v141 + 1;
                    do
                    {
                      if ( !v140 )
                        break;
                      if ( !*v139 )
                        break;
                      *v143++ = *v139++;
                      --v140;
                      --v142;
                    }
                    while ( v142 );
                    v184 = v13 + 24;
                    v144 = v143 - 1;
                    LODWORD(v13) = v13 + 24;
                    if ( v142 )
                      v144 = v143;
                    *v144 = 0;
                    if ( v141 )
                    {
                      v176 = v191;
                      if ( v191 )
                      {
                        ++v191[1];
                        *v176 += *(_DWORD *)v141;
                      }
                      if ( v186 )
                        *(_DWORD *)(v186 + 8) += *(_DWORD *)v141;
                    }
                  }
                }
                v145 = 0;
                if ( *(_DWORD *)(v134 + 8 * v136 + 12) )
                {
                  v146 = Src;
                  while ( 2 )
                  {
                    v147 = *(_QWORD *)(v134 + 8 * v136);
                    v148 = (_DWORD *)(v147 + 20 + 24 * v145);
                    if ( (unsigned int)v13 + (unsigned __int64)((*v148 + 7) & 0xFFFFFFF8) + 8 > (unsigned __int64)v146 )
                    {
                      v183 = 8;
                      goto LABEL_279;
                    }
                    v149 = (_DWORD *)((unsigned int)v13 + v137);
                    v150 = ((*(_DWORD *)(v147 + 20 + 24 * v145) + 7) & 0xFFFFFFF8) + 8;
                    memset_0(v149, 0, v150);
                    v151 = v191;
                    *v149 = *v148;
                    v149[1] = v150;
                    if ( v151 )
                      *v151 += v150;
                    if ( v186 )
                      *(_DWORD *)(v186 + 8) += v149[1];
                    v152 = *(_DWORD *)(v147 + 24 * v145 + 12);
                    if ( v152 == 4 )
                      goto LABEL_271;
                    if ( !v152 )
                      goto LABEL_287;
                    v157 = v152 - 1;
                    if ( !v157 )
                    {
LABEL_271:
                      v153 = *(_DWORD *)(v147 + 20 + 24 * v145);
                      v148 = (_DWORD *)(v147 + 20 + 24 * v145);
                      if ( v153 == 4 )
                      {
                        v149[2] = (int)*(double *)(v147 + 24 * v145);
                        goto LABEL_278;
                      }
                      if ( v153 != 8 )
                        goto LABEL_278;
                      v154 = *(double *)(v147 + 24 * v145);
                      v155 = 0;
                      if ( v154 >= 9.223372036854776e18 )
                      {
                        v154 = v154 - 9.223372036854776e18;
                        if ( v154 < 9.223372036854776e18 )
                          v155 = 0x8000000000000000uLL;
                      }
                      v156 = (unsigned int)(int)v154;
                    }
                    else
                    {
                      v158 = v157 - 1;
                      if ( v158 )
                      {
                        if ( v158 != 1 )
                        {
LABEL_287:
                          v159 = *(_DWORD *)(v147 + 20 + 24 * v145);
                          v148 = (_DWORD *)(v147 + 20 + 24 * v145);
                          if ( v159 == 4 )
                          {
                            v149[2] = 0;
                          }
                          else if ( v159 == 8 )
                          {
                            *((_QWORD *)v149 + 1) = 0;
                          }
                          goto LABEL_278;
                        }
                        goto LABEL_271;
                      }
                      v177 = *(_DWORD *)(v147 + 20 + 24 * v145);
                      v148 = (_DWORD *)(v147 + 20 + 24 * v145);
                      if ( v177 == 4 )
                      {
                        v149[2] = (int)(*(double *)(v147 + 24 * v145) / (double)*(int *)(v147 + 24 * v145 + 16));
                        goto LABEL_278;
                      }
                      if ( v177 != 8 )
                      {
LABEL_278:
                        LODWORD(v13) = v184;
                        v146 = Src;
LABEL_279:
                        v137 = a2;
                        v145 = (unsigned int)(v145 + 1);
                        LODWORD(v13) = ((*v148 + 7) & 0xFFFFFFF8) + v13 + 8;
                        v184 = v13;
                        if ( (unsigned int)v145 >= *(_DWORD *)(v134 + 8 * v136 + 12) )
                        {
                          v6 = a1;
                          goto LABEL_82;
                        }
                        continue;
                      }
                      v155 = 0;
                      v178 = *(double *)(v147 + 24 * v145) / (double)*(int *)(v147 + 24 * v145 + 16);
                      if ( v178 >= 9.223372036854776e18 )
                      {
                        v178 = v178 - 9.223372036854776e18;
                        if ( v178 < 9.223372036854776e18 )
                          v155 = 0x8000000000000000uLL;
                      }
                      v156 = (unsigned int)(int)v178;
                    }
                    break;
                  }
                  *((_QWORD *)v149 + 1) = v155 + v156;
                  goto LABEL_278;
                }
              }
            }
          }
        }
      }
LABEL_82:
      v4 = a3;
      v18 = (unsigned __int64)Src;
      v17 = v197;
LABEL_33:
      v16 = v189 + 1;
      v189 = v16;
      if ( v16 >= *((_DWORD *)v6 + 12) )
        goto LABEL_34;
      v5 = a2;
    }
    v26 = 0;
    v29 = 0;
    goto LABEL_48;
  }
LABEL_34:
  if ( (v183 & 0xFFFFFFF7) == 0 )
  {
    if ( v4 >= 0x30 )
    {
      *(_DWORD *)a2 = v13;
      *(_DWORD *)(a2 + 4) = *((_DWORD *)v6 + 12);
    }
    *a4 = v13;
  }
  return v183;
}

```

## disassembly

```asm
0x180007020  mov     [rsp+arg_18], r9
0x180007025  mov     [rsp+arg_10], r8d
0x18000702a  mov     [rsp+arg_8], rdx
0x18000702f  mov     [rsp+arg_0], rcx
0x180007034  push    rbp
0x180007035  push    rsi
0x180007036  push    r14
0x180007038  push    r15
0x18000703a  sub     rsp, 108h
0x180007041  xor     r15d, r15d
0x180007044  mov     esi, r8d
0x180007047  mov     dword ptr [rsp+128h+Size], r15d
0x18000704c  mov     r14, rdx
0x18000704f  mov     [rsp+128h+ThreadInformation], r15d
0x180007057  mov     rbp, rcx
0x18000705a  test    r9, r9
0x18000705d  jnz     short loc_180007073
0x18000705f  mov     eax, 57h ; 'W'
0x180007064  add     rsp, 108h
0x18000706b  pop     r15
0x18000706d  pop     r14
0x18000706f  pop     rsi
0x180007070  pop     rbp
0x180007071  retn
0x180007073  mov     [r9], r15d
0x180007076  test    esi, esi
0x180007078  jnz     loc_180007E32
0x18000707e  call    ?PerflibciNotifyQuery@@YAXPEAU_PERF_QUERY@@@Z; PerflibciNotifyQuery(_PERF_QUERY *)
0x180007083  cmp     [rbp+28h], r15
0x180007087  jz      loc_180008610
0x18000708d  mov     ecx, r15d
0x180007090  mov     [rsp+128h+var_28], rbx
0x180007098  mov     [rsp+128h+var_30], rdi
0x1800070a0  mov     [rsp+128h+var_38], r12
0x1800070a8  mov     r12d, r15d
0x1800070ab  mov     [rsp+128h+var_40], r13
0x1800070b3  mov     dword ptr [rsp+128h+var_B0], r15d
0x1800070b8  cmp     [rbp+30h], r15d
0x1800070bc  jbe     short loc_1800070E4
0x1800070be  mov     rdx, [rbp+28h]
0x1800070c2  mov     eax, ecx
0x1800070c4  shl     rax, 5
0x1800070c8  test    byte ptr [rax+rdx+18h], 8
0x1800070cd  mov     qword ptr [rax+rdx+10h], 0E8h
0x1800070d6  jnz     short loc_1800070DD
0x1800070d8  mov     [rax+rdx+8], r15
0x1800070dd  inc     ecx; int
0x1800070df  cmp     ecx, [rbp+30h]
0x1800070e2  jb      short loc_1800070BE
0x1800070e4  lea     rdx, [rsp+128h+ThreadInformation]; int *
0x1800070ec  call    ?PerfpBoostPriority@@YAEJPEAJ@Z; PerfpBoostPriority(long,long *)
0x1800070f1  mov     r13d, 30h ; '0'
0x1800070f7  mov     [rsp+128h+var_E7], al
0x1800070fb  movzx   ebx, al
0x1800070fe  cmp     esi, r13d
0x180007101  jnb     loc_18000762B
0x180007107  mov     [rsp+128h+var_E4], 8
0x18000710f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007116  test    byte ptr [rcx+1Ch], 8
0x18000711a  jnz     loc_1800084AC
0x180007120  mov     rcx, rbp; struct _PERF_QUERY *
0x180007123  call    ?PerfpCollectKernelData@@YAKPEAU_PERF_QUERY@@@Z; PerfpCollectKernelData(_PERF_QUERY *)
0x180007128  mov     rcx, cs:WPP_GLOBAL_Control
0x18000712f  test    byte ptr [rcx+1Ch], 8
0x180007133  jnz     loc_1800084D0
0x180007139  mov     rdi, [rbp+18h]
0x18000713d  mov     [rsp+128h+var_80], rdi
0x180007145  test    rdi, rdi
0x180007148  jz      short loc_180007185
0x18000714a  mov     rax, [rdi+8]
0x18000714e  cmp     dword ptr [rax+20h], 1
0x180007152  jnz     loc_180007737
0x180007158  mov     rdi, [rdi]
0x18000715b  mov     [rsp+128h+var_80], rdi
0x180007163  test    rdi, rdi
0x180007166  jnz     short loc_18000714A
0x180007168  movzx   ebx, [rsp+128h+var_E7]
0x18000716d  mov     r13d, 30h ; '0'
0x180007173  mov     r14, [rsp+128h+arg_8]
0x18000717b  xor     r15d, r15d
0x18000717e  mov     esi, [rsp+128h+arg_10]
0x180007185  test    bl, bl
0x180007187  jz      short loc_1800071AF
0x180007189  mov     r9d, 4; ThreadInformationLength
0x18000718f  lea     r8, [rsp+128h+ThreadInformation]; ThreadInformation
0x180007197  mov     edx, 2; ThreadInformationClass
0x18000719c  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800071a3  call    cs:__imp_NtSetInformationThread
0x1800071aa  nop     dword ptr [rax+rax+00h]
0x1800071af  cmp     dword ptr [rbp+30h], 0
0x1800071b3  jbe     loc_180007294
0x1800071b9  mov     eax, r15d
0x1800071bc  mov     r12d, esi
0x1800071bf  movaps  [rsp+128h+var_58], xmm6
0x1800071c7  movsd   xmm6, cs:__real@43e0000000000000
0x1800071cf  mov     [rsp+128h+var_C0], eax
0x1800071d3  mov     [rsp+128h+var_80], r12
0x1800071db  mov     r8d, esi
0x1800071de  jmp     short loc_1800071E8
0x1800071e0  mov     r14, [rsp+128h+arg_8]
0x1800071e8  mov     rbp, [rbp+28h]
0x1800071ec  mov     r15d, eax
0x1800071ef  shl     r15, 5
0x1800071f3  mov     qword ptr [rsp+128h+Frequency], r15
0x1800071f8  mov     [rsp+128h+var_A0], rbp
0x180007200  mov     ecx, [r15+rbp+14h]
0x180007205  mov     eax, ecx
0x180007207  test    ecx, ecx
0x180007209  jz      short loc_18000722F
0x18000720b  sub     eax, 1
0x18000720e  jz      loc_1800072E8
0x180007214  sub     eax, 1
0x180007217  jz      loc_180007D90
0x18000721d  sub     eax, 2
0x180007220  jz      loc_180007363
0x180007226  cmp     eax, 2
0x180007229  jz      loc_180007363
0x18000722f  test    ecx, 0FFFFFFF9h
0x180007235  jnz     loc_180008507
0x18000723b  cmp     ecx, 4
0x18000723e  jz      loc_180008507
0x180007244  mov     ecx, r13d
0x180007247  lea     rax, [rcx+10h]
0x18000724b  cmp     rax, r8
0x18000724e  ja      loc_180007E25
0x180007254  mov     eax, [r15+rbp+10h]
0x180007259  mov     [rcx+r14], eax
0x18000725d  xor     eax, eax
0x18000725f  mov     [rcx+r14+4], eax
0x180007264  mov     qword ptr [rcx+r14+8], 10h
0x18000726d  add     r13d, 10h
0x180007271  mov     rbp, [rsp+128h+arg_0]
0x180007279  mov     eax, [rsp+128h+var_C0]
0x18000727d  inc     eax
0x18000727f  mov     [rsp+128h+var_C0], eax
0x180007283  cmp     eax, [rbp+30h]
0x180007286  jb      loc_1800071E0
0x18000728c  movaps  xmm6, [rsp+128h+var_58]
0x180007294  mov     edx, [rsp+128h+var_E4]
0x180007298  mov     r12, [rsp+128h+var_38]
0x1800072a0  mov     rdi, [rsp+128h+var_30]
0x1800072a8  mov     rbx, [rsp+128h+var_28]
0x1800072b0  test    edx, 0FFFFFFF7h
0x1800072b6  jnz     short loc_1800072D9
0x1800072b8  cmp     esi, 30h ; '0'
0x1800072bb  jb      short loc_1800072CE
0x1800072bd  mov     rax, [rsp+128h+arg_8]
0x1800072c5  mov     [rax], r13d
0x1800072c8  mov     ecx, [rbp+30h]
0x1800072cb  mov     [rax+4], ecx
0x1800072ce  mov     rcx, [rsp+128h+arg_18]
0x1800072d6  mov     [rcx], r13d
0x1800072d9  mov     r13, [rsp+128h+var_40]
0x1800072e1  mov     eax, edx
0x1800072e3  jmp     loc_180007064
0x1800072e8  mov     rdx, [r15+rbp+8]; Src
0x1800072ed  test    rdx, rdx
0x1800072f0  jz      loc_1800086F2
0x1800072f6  mov     r8d, [rdx+4]
0x1800072fa  add     r8d, 10h
0x1800072fe  lea     ebx, [r8+r13]
0x180007302  cmp     ebx, esi
0x180007304  ja      loc_180007DAE
0x18000730a  mov     eax, [r15+rbp+10h]
0x18000730f  mov     ecx, r13d
0x180007312  mov     [rcx+r14], eax
0x180007316  mov     eax, [r15+rbp+14h]
0x18000731b  mov     [rcx+r14+4], eax
0x180007320  mov     [rcx+r14+8], r8d
0x180007325  mov     dword ptr [rcx+r14+0Ch], 0
0x18000732e  add     rcx, 10h
0x180007332  mov     r8d, [rdx+4]; Size
0x180007336  add     rcx, r14; void *
0x180007339  call    memcpy_0
0x18000733e  mov     rcx, [r15+rbp+8]; hMem
0x180007343  mov     r13d, ebx
0x180007346  call    cs:__imp_LocalFree
0x18000734d  nop     dword ptr [rax+rax+00h]
0x180007352  mov     qword ptr [r15+rbp+8], 0
0x18000735b  mov     r8, r12
0x18000735e  jmp     loc_180007271
0x180007363  mov     rdi, [r15+rbp]
0x180007367  xor     r11d, r11d
0x18000736a  mov     [rsp+128h+var_B8], r11
0x18000736f  mov     [rsp+128h+var_90], rdi
0x180007377  mov     qword ptr [rsp+128h+Counter], r11
0x18000737f  test    rdi, rdi
0x180007382  jz      loc_1800083FD
0x180007388  mov     [rsp+128h+var_F8], r11d; int
0x18000738d  xor     r9d, r9d
0x180007390  mov     [rsp+128h+var_100], r11w; __int16
0x180007396  xor     r8d, r8d
0x180007399  xor     edx, edx; Src
0x18000739b  mov     qword ptr [rsp+128h+bIgnoreCase], r11; void *
0x1800073a0  mov     rcx, rdi; Buf1
0x1800073a3  call    PerflibciCreateOrFindCounterSet
0x1800073a8  mov     rsi, rax
0x1800073ab  test    rax, rax
0x1800073ae  jz      loc_180007725
0x1800073b4  test    byte ptr [rax+58h], 4
0x1800073b8  jnz     loc_180007E8B
0x1800073be  xor     r9b, r9b
0x1800073c1  xor     r11d, r11d
0x1800073c4  mov     ebx, r11d
0x1800073c7  mov     [rsp+128h+var_E8], r9b
0x1800073cc  cmp     dword ptr [rdi+14h], 28h ; '('
0x1800073d0  jbe     loc_1800076A5
0x1800073d6  lea     rcx, [rdi+28h]; unsigned __int16 *
0x1800073da  call    ?PerflibciWildcardInstance@@YAEPEBG@Z; PerflibciWildcardInstance(ushort const *)
0x1800073df  test    al, al
0x1800073e1  jz      loc_1800076A5
0x1800073e7  mov     r10b, 1
0x1800073ea  mov     [rsp+128h+var_E7], r10b
0x1800073ef  test    r9b, r9b
0x1800073f2  jnz     loc_180008323
0x1800073f8  mov     ecx, r13d
0x1800073fb  mov     [rsp+128h+Src], r12
0x180007403  lea     rax, [rcx+10h]
0x180007407  cmp     rax, r12
0x18000740a  ja      loc_180007710
0x180007410  mov     eax, [r15+rbp+10h]
0x180007415  add     r14, rcx
0x180007418  mov     [rsp+128h+var_D8], r14
0x18000741d  mov     [r14], eax
0x180007420  mov     qword ptr [r14+8], 10h
0x180007428  test    r10b, r10b
0x18000742b  jz      loc_1800084F4
0x180007431  mov     eax, [r15+rbp+14h]
0x180007436  mov     [r14+4], eax
0x18000743a  mov     rdi, [r15+rbp+8]
0x18000743f  add     r13d, 10h
0x180007443  cmp     dword ptr [r15+rbp+14h], 6
0x180007449  mov     [rsp+128h+var_E0], r13d
0x18000744e  jz      loc_1800076B2
0x180007454  mov     r12, [rsp+128h+arg_8]
0x18000745c  test    r9b, r9b
0x18000745f  jnz     loc_180007EAB
0x180007465  movzx   eax, [rsp+128h+var_E7]
0x18000746a  test    al, al
0x18000746c  jz      loc_180007693
0x180007472  lea     rax, [r13+8]
0x180007476  mov     ecx, r13d
0x180007479  cmp     rax, [rsp+128h+var_80]
0x180007481  ja      loc_180007DC8
0x180007487  add     r12, rcx
0x18000748a  mov     qword ptr [r12], 8
0x180007492  mov     rdx, [rsp+128h+var_D8]
0x180007497  mov     [rsp+128h+var_B0], r12
0x18000749c  test    rdx, rdx
0x18000749f  jz      short loc_1800074A5
0x1800074a1  add     dword ptr [rdx+8], 8
0x1800074a5  movzx   eax, [rsp+128h+var_E7]
0x1800074aa  add     r13d, 8
0x1800074ae  mov     [rsp+128h+var_E0], r13d
0x1800074b3  cmp     qword ptr [r15+rbp+8], 0
0x1800074b9  jz      loc_1800075CB
0x1800074bf  mov     rbp, [rdi]
0x1800074c2  mov     rbx, [rsp+128h+var_A0]
0x1800074ca  test    rbp, rbp
0x1800074cd  jz      loc_1800075A9
0x1800074d3  nop     dword ptr [rax+00h]
0x1800074d7  nop     word ptr [rax+rax+00000000h]
0x1800074e0  mov     rdi, [rbp+20h]
0x1800074e4  mov     r15, [rbp+18h]
0x1800074e8  mov     [rsp+128h+var_78], r15
0x1800074f0  test    rdi, rdi
0x1800074f3  jz      short loc_18000756D
0x1800074f5  mov     r14d, [rdi]
0x1800074f8  mov     esi, [rdi+8]
0x1800074fb  test    al, al
0x1800074fd  jz      short loc_18000755C
0x1800074ff  lea     ecx, [rsi+r14]
0x180007503  lea     eax, [rcx+r13]
0x180007507  cmp     eax, [rsp+128h+arg_10]
0x18000750e  ja      loc_1800075FA
0x180007514  mov     r8d, ecx; Size
0x180007517  lea     rdx, [rdi+8]; Src
0x18000751b  mov     ecx, r13d
0x18000751e  add     rcx, [rsp+128h+arg_8]; void *
0x180007526  call    memcpy_0
0x18000752b  inc     dword ptr [r12+4]
0x180007530  mov     eax, [rdi+8]
0x180007533  mov     rdx, [rsp+128h+var_D8]
0x180007538  add     eax, r14d
0x18000753b  add     [r12], eax
0x18000753f  mov     eax, [rdi+8]
0x180007542  add     eax, r14d
0x180007545  add     [rdx+8], eax
0x180007548  mov     eax, [rdi+8]
0x18000754b  movzx   r9d, [rsp+128h+var_E8]
0x180007551  add     eax, r14d
0x180007554  add     r13d, eax
0x180007557  mov     [rsp+128h+var_E0], r13d
0x18000755c  test    r9b, r9b
0x18000755f  jnz     loc_180007C35
0x180007565  mov     rbx, [rsp+128h+var_A0]
0x18000756d  mov     rax, qword ptr [rsp+128h+Frequency]
0x180007572  test    byte ptr [rax+rbx+18h], 8
0x180007577  jnz     short loc_180007588
0x180007579  mov     rcx, rbp; hMem
  ... truncated ...
```
