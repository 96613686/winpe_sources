# PerflibciLocalQueryCounterData

- ea: `0x180006930`
- end: `0x180007f75`
- name: `PerflibciLocalQueryCounterData`
- size: `5701`
- prototype: `__int64 __fastcall(struct _PERF_QUERY *, __int64, unsigned int, _DWORD *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003cc0`
- `0x1800160c0`

## callees

- `0x180005e40`
- `0x180006930`
- `0x180008028`
- `0x180008830`
- `0x180008a40`
- `0x180008c94`
- `0x180009034`
- `0x180017100`
- `0x18003b748`
- `0x18003d048`
- `0x180065042`
- `0x18006505a`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x180006a4a`
- `ntdll!NtSetInformationThread` at `0x180006aee`
- `ntdll!NtSetInformationThread` at `0x180006a4a`
- `ntdll!NtSetInformationThread` at `0x180006aee`
- `ntdll!NtQueryInformationThread` at `0x180006a15`
- `ntdll!NtQueryInformationThread` at `0x180006a15`
- `ntdll!NtQueryPerformanceCounter` at `0x180006f57`
- `ntdll!NtQueryPerformanceCounter` at `0x180006f57`
- `ntdll!RtlNtStatusToDosError` at `0x1800070bb`
- `ntdll!RtlNtStatusToDosError` at `0x1800070bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006f49`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006f49`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180006f3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180006f3f`
- `KERNEL32!LocalFree` at `0x180006c69`
- `KERNEL32!LocalFree` at `0x180006e81`
- `KERNEL32!LocalFree` at `0x180006ec2`
- `KERNEL32!LocalFree` at `0x18000704e`
- `KERNEL32!LocalFree` at `0x180007462`
- `KERNEL32!LocalFree` at `0x1800076aa`
- `KERNEL32!LocalFree` at `0x18000775d`
- `KERNEL32!LocalFree` at `0x180007ba3`
- `KERNEL32!LocalFree` at `0x180007c02`
- `KERNEL32!LocalFree` at `0x180006c69`
- `KERNEL32!LocalFree` at `0x180006e81`
- `KERNEL32!LocalFree` at `0x180006ec2`
- `KERNEL32!LocalFree` at `0x18000704e`
- `KERNEL32!LocalFree` at `0x180007462`
- `KERNEL32!LocalFree` at `0x1800076aa`
- `KERNEL32!LocalFree` at `0x18000775d`
- `KERNEL32!LocalFree` at `0x180007ba3`
- `KERNEL32!LocalFree` at `0x180007c02`
- `KERNEL32!CompareStringOrdinal` at `0x18000728c`
- `KERNEL32!CompareStringOrdinal` at `0x18000728c`
- `KERNEL32!SetLastError` at `0x1800073ef`
- `KERNEL32!SetLastError` at `0x180007482`
- `KERNEL32!SetLastError` at `0x1800073ef`
- `KERNEL32!SetLastError` at `0x180007482`
- `api-ms-win-core-pcw-l1-1-0!PcwSendNotification` at `0x1800070ac`
- `api-ms-win-core-pcw-l1-1-0!PcwSendNotification` at `0x1800070ac`

## pseudocode

```c
__int64 __fastcall PerflibciLocalQueryCounterData(struct _PERF_QUERY *a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  char *QuadPart; // r13
  unsigned int v5; // esi
  __int64 v6; // r14
  struct _PERF_QUERY *v7; // rbx
  unsigned int v9; // ecx
  __int64 v10; // rdx
  __int64 v11; // rax
  bool v12; // zf
  __int64 v13; // r12
  LARGE_INTEGER v14; // rdi
  unsigned int v15; // eax
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // r8
  __int64 v18; // r15
  struct PERFLIBCI_RED_BLACK_NODE **v19; // r13
  int v20; // ecx
  _DWORD *v21; // rdx
  int v22; // r8d
  int v23; // ebx
  unsigned __int16 *v24; // rbx
  __int64 CounterSet; // rax
  __int64 v26; // rdi
  bool v27; // r9
  unsigned int v28; // ebx
  const unsigned __int16 *v29; // r11
  char v30; // r10
  __int64 v31; // rsi
  int v32; // eax
  __int64 v33; // r15
  char v34; // al
  _DWORD *v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rcx
  _QWORD *v38; // r15
  unsigned int *v39; // rdi
  _QWORD *v40; // r13
  unsigned int v41; // r14d
  __int64 v42; // rsi
  _DWORD *v43; // rdx
  _DWORD *v44; // rdx
  unsigned int v45; // ecx
  int v46; // esi
  int v47; // esi
  __int64 v48; // r15
  __int64 v49; // r12
  unsigned int v50; // ebx
  unsigned int v51; // r14d
  char *v52; // rax
  NTSTATUS v53; // eax
  unsigned int v54; // edx
  unsigned int *v55; // rcx
  unsigned int v56; // eax
  unsigned int v57; // edi
  _DWORD *v58; // r15
  unsigned int v59; // eax
  int v60; // ecx
  __int64 v61; // r14
  __int64 v62; // rax
  _DWORD *v63; // rbx
  int v64; // ecx
  unsigned int v65; // r9d
  struct PERFLIBCI_RED_BLACK_NODE **v66; // rdi
  __int64 v67; // rsi
  unsigned int v68; // r12d
  WCHAR *v69; // rdx
  __int64 v70; // r10
  bool v71; // cc
  unsigned int v72; // edx
  unsigned int i; // ecx
  __int64 v74; // rcx
  _QWORD *v75; // r14
  unsigned int *v76; // r13
  int v77; // esi
  const WCHAR *v78; // r15
  __int64 v79; // rbx
  int v80; // eax
  _QWORD *v81; // rax
  DWORD v82; // ecx
  unsigned int v83; // ecx
  unsigned int v84; // eax
  unsigned int v85; // ebx
  unsigned int **v86; // r14
  unsigned int ***v87; // rcx
  unsigned int *v88; // r15
  unsigned int *v89; // rax
  struct PERFLIBCI_RED_BLACK_NODE **v90; // r10
  __int64 v91; // r10
  unsigned int v92; // eax
  __int64 v93; // rcx
  __int64 v94; // rax
  int v95; // eax
  __int64 v96; // rbx
  unsigned int v97; // esi
  _DWORD *v98; // rbx
  __int64 v99; // rdi
  _DWORD *v100; // r12
  LARGE_INTEGER v101; // r13
  const unsigned __int16 *v102; // r15
  int v103; // r10d
  unsigned int v104; // r9d
  __int64 v105; // rdx
  __int64 v106; // r8
  __int64 v107; // rax
  int v108; // edx
  __int64 v109; // rcx
  int v110; // eax
  double v111; // xmm0_8
  double v112; // xmm0_8
  int v113; // eax
  int v114; // eax
  void *v115; // rbx
  __int64 v116; // rax
  __int64 v117; // rdx
  __int64 v118; // r8
  int v119; // ebx
  double v120; // xmm1_8
  __int64 v121; // rcx
  unsigned int v122; // eax
  LARGE_INTEGER v123; // rsi
  unsigned int v124; // eax
  _DWORD *v125; // r10
  const unsigned __int16 *v126; // r8
  _DWORD *v127; // rbx
  int v128; // r8d
  unsigned int v129; // r11d
  __int64 v130; // r9
  const unsigned __int16 *v131; // r13
  _DWORD *v132; // rcx
  int j; // eax
  __int64 v134; // r13
  unsigned int v135; // eax
  __int64 v136; // r15
  int v137; // r11d
  const WCHAR *v138; // r8
  __int64 v139; // rcx
  _QWORD *v140; // r10
  __int64 v141; // rdx
  _WORD *v142; // rax
  _WORD *v143; // rcx
  __int64 v144; // rdi
  void *v145; // r8
  __int64 v146; // r14
  _DWORD *v147; // rbx
  _DWORD *v148; // r12
  _DWORD *v149; // r8
  int v150; // eax
  int v151; // eax
  int v152; // eax
  double v153; // xmm0_8
  unsigned __int64 v154; // rcx
  __int64 v155; // rax
  int v156; // eax
  int v157; // eax
  int v158; // eax
  __int64 v159; // rax
  int v160; // ecx
  unsigned int v161; // ecx
  ULONG v162; // edi
  unsigned int v163; // ebx
  struct _PERF_INSTANCE_HEADER *v164; // rdx
  struct _PERF_COUNTER_DATA *v165; // r8
  ULONG v166; // eax
  int v167; // eax
  int v168; // edx
  const void *v169; // rdx
  size_t v170; // r8
  __int64 v171; // rax
  int v172; // ecx
  int v173; // eax
  __int64 v174; // rax
  unsigned int v175; // ecx
  _DWORD *v176; // r8
  int v177; // eax
  double v178; // xmm1_8
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  bool v180; // [rsp+40h] [rbp-C0h]
  bool v181; // [rsp+41h] [rbp-BFh]
  char v182; // [rsp+41h] [rbp-BFh]
  unsigned int v183; // [rsp+44h] [rbp-BCh]
  int v184; // [rsp+48h] [rbp-B8h]
  int v185; // [rsp+48h] [rbp-B8h]
  __int64 v186; // [rsp+50h] [rbp-B0h]
  unsigned int *v187; // [rsp+50h] [rbp-B0h]
  int v188; // [rsp+58h] [rbp-A8h] BYREF
  size_t Size; // [rsp+60h] [rbp-A0h]
  _DWORD *v190; // [rsp+68h] [rbp-98h]
  _DWORD *v191; // [rsp+70h] [rbp-90h]
  __int64 v192; // [rsp+78h] [rbp-88h]
  LARGE_INTEGER Frequency; // [rsp+80h] [rbp-80h] BYREF
  struct PERFLIBCI_RED_BLACK_NODE **v194; // [rsp+88h] [rbp-78h]
  LARGE_INTEGER Counter; // [rsp+90h] [rbp-70h] BYREF
  const unsigned __int16 *v196; // [rsp+98h] [rbp-68h]
  void *Src; // [rsp+A0h] [rbp-60h]
  int v198; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v199; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD *v200; // [rsp+B8h] [rbp-48h]
  unsigned int ***v201; // [rsp+C0h] [rbp-40h]
  void *v202; // [rsp+C8h] [rbp-38h]
  __int64 v203; // [rsp+D0h] [rbp-30h]
  _OWORD ThreadInformation[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v205; // [rsp+F8h] [rbp-8h]

  QuadPart = 0;
  v5 = a3;
  LODWORD(Size) = 0;
  v6 = a2;
  v198 = 0;
  v7 = a1;
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
  if ( !*((_QWORD *)v7 + 5) )
    return 14;
  v9 = 0;
  for ( LODWORD(v190) = 0; v9 < *((_DWORD *)v7 + 12); ++v9 )
  {
    v10 = *((_QWORD *)v7 + 5);
    v11 = 32LL * v9;
    v12 = (*(_BYTE *)(v11 + v10 + 24) & 8) == 0;
    *(_QWORD *)(v11 + v10 + 16) = 232;
    if ( v12 )
      *(_QWORD *)(v11 + v10 + 8) = 0;
  }
  v188 = 15;
  LODWORD(v13) = 48;
  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  v205 = 0;
  if ( NtQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadBasicInformation, ThreadInformation, 0x30u, 0) < 0 )
  {
    v181 = 0;
  }
  else if ( SDWORD2(v205) >= v188 )
  {
    v181 = 0;
  }
  else
  {
    v198 = DWORD2(v205);
    v181 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPriority, &v188, 4u) >= 0;
  }
  if ( v5 >= 0x30 )
  {
    v183 = 0;
    Counter.QuadPart = 0;
    Frequency.QuadPart = 0;
    *(_QWORD *)v6 = 0;
    GetSystemTime((LPSYSTEMTIME)(v6 + 32));
    GetSystemTimeAsFileTime((LPFILETIME)(v6 + 16));
    NtQueryPerformanceCounter(&Counter, &Frequency);
    *(LARGE_INTEGER *)(v6 + 8) = Counter;
    *(LARGE_INTEGER *)(v6 + 24) = Frequency;
  }
  else
  {
    v183 = 8;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_98cc76a206513ba905b421ef2a045de0_Traceguids);
  PerfpCollectKernelData(v7);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_98cc76a206513ba905b421ef2a045de0_Traceguids);
  v14 = *(LARGE_INTEGER *)((char *)v7 + 24);
  Counter = v14;
  if ( v14.QuadPart )
  {
    do
    {
      if ( *(_DWORD *)(*(_QWORD *)(v14.QuadPart + 8) + 32LL) != 1 && (*(_BYTE *)(v14.QuadPart + 36) & 4) == 0 )
      {
        v46 = *((_DWORD *)v7 + 23);
        LODWORD(Size) = 0x2000;
        v47 = *(_DWORD *)(v14.QuadPart + 28) + v46;
        v48 = *(_QWORD *)(v14.QuadPart + 16);
        v49 = *(_QWORD *)(v14.QuadPart + 48);
        v50 = (*(unsigned __int16 *)(v14.QuadPart + 32) << 16) | 4;
        v199 = -20000000;
        do
        {
          LocalFree(QuadPart);
          v51 = Size;
          v52 = (char *)operator new((unsigned int)Size, (const struct std::nothrow_t *)&std::nothrow);
          Frequency.QuadPart = (LONGLONG)v52;
          QuadPart = v52;
          if ( !v52 )
            goto LABEL_162;
          memset_0(v52, 0, v51);
          ReturnLength = v47;
          v53 = PcwSendNotification(v49, v50, &v199, v48);
        }
        while ( v53 == -2147483643 );
        if ( !RtlNtStatusToDosError(v53) )
        {
          v54 = 8;
          while ( v54 < (unsigned int)Size )
          {
            v55 = (unsigned int *)&QuadPart[v54];
            v187 = v55;
            v54 += *v55;
            v56 = v55[3];
            LODWORD(v192) = v54;
            if ( v56 == 4203 )
            {
              *(_DWORD *)(v14.QuadPart + 36) |= 4u;
            }
            else if ( !v56 )
            {
              v57 = 16;
              v188 = 16;
              while ( v57 < *v55 )
              {
                v58 = (unsigned int *)((char *)v55 + v57);
                v200 = v58;
                v59 = v58[3];
                if ( v59 < *((_DWORD *)a1 + 12) )
                {
                  v60 = v58[1];
                  v61 = *((_QWORD *)a1 + 5) + 32LL * v59;
                  v203 = v61;
                  if ( v60 == 6 )
                  {
                    v62 = (unsigned int)v58[4];
                    v12 = *(_DWORD *)((char *)v58 + v62 + 20) == 0;
                    v63 = (_DWORD *)((char *)v58 + v62 + 16);
                    v194 = (struct PERFLIBCI_RED_BLACK_NODE **)(v58 + 4);
                    v191 = v63;
                    if ( !v12 )
                    {
                      if ( !*(_QWORD *)(v61 + 8) )
                      {
                        v93 = (unsigned int)(v62 + 24);
                        if ( (unsigned int)v62 < (unsigned int)v93 )
                        {
                          v94 = operator new(v93);
                          *(_QWORD *)(v61 + 8) = v94;
                          if ( v94 )
                          {
                            *(_QWORD *)(v94 + 16) = v94 + 24;
                            memcpy_0((void *)(v94 + 24), v58 + 4, (unsigned int)v58[4]);
                          }
                        }
                        if ( !*(_QWORD *)(v61 + 8) )
                        {
LABEL_156:
                          *(_QWORD *)(v61 + 16) = 14;
                          goto LABEL_157;
                        }
                      }
                      v64 = *v58;
                      *(_DWORD *)(v61 + 16) = *v58;
                      *(_DWORD *)(v61 + 20) = v58[1];
                      if ( v64 )
                        *(_DWORD *)(v61 + 16) = 0;
                      v65 = *v63;
                      if ( *v63 <= 8u )
                        goto LABEL_157;
                      v66 = v194;
                      LODWORD(v67) = 8;
                      while ( 2 )
                      {
                        v68 = 0;
                        v69 = (WCHAR *)((char *)v63 + (unsigned int)v67);
                        Src = v69;
                        v70 = *(unsigned int *)v69;
                        v67 = (unsigned int)(v70 + v67);
                        v185 = v67;
                        v71 = (unsigned int)v67 <= v65;
                        if ( (unsigned int)v67 < v65 )
                        {
                          _mm_lfence();
                          v72 = *((_DWORD *)v66 + 1);
                          for ( i = 0; i < v72; v68 += *(_DWORD *)((char *)v63 + v68 + v67 + 4) )
                            ++i;
                          v69 = (WCHAR *)Src;
                          LODWORD(v67) = v68 + v67;
                          v185 = v67;
                          v71 = (unsigned int)v67 <= v65;
                        }
                        if ( !v71 || !v68 )
                          goto LABEL_147;
                        if ( ((*(_DWORD *)(v61 + 24) - 4) & 0xFFFFFFF7) == 0 )
                        {
                          v172 = (_DWORD)v190 + 1;
                          *((_DWORD *)v69 + 1) = (_DWORD)v190;
                          LODWORD(v190) = v172;
                        }
                        v74 = *(_QWORD *)(v61 + 8);
                        v201 = (unsigned int ***)v74;
                        if ( !v74 || !v69 || (v202 = (char *)v69 + v70) == 0 )
                        {
                          SetLastError(0xDu);
                          goto LABEL_147;
                        }
                        v75 = *(_QWORD **)(v74 + 8);
                        v76 = 0;
                        LODWORD(v196) = 0;
                        v77 = 0;
                        v194 = (struct PERFLIBCI_RED_BLACK_NODE **)(v74 + 8);
                        v78 = v69 + 4;
                        if ( v75 )
                        {
                          while ( 2 )
                          {
                            v79 = v75[4] + 8LL;
                            if ( v75[4] == -8 )
                            {
                              v82 = 13;
                              goto LABEL_134;
                            }
                            v80 = CompareStringOrdinal(v78, -1, (LPCWCH)(v75[4] + 16LL), -1, 1);
                            v77 = v80 - 2;
                            if ( v80 == 2 )
                            {
                              v92 = *(_DWORD *)(v79 + 4);
                              if ( *((_DWORD *)Src + 1) < v92 )
                              {
                                v77 = -1;
                                goto LABEL_351;
                              }
                              if ( *((_DWORD *)Src + 1) <= v92 )
                              {
                                v63 = v191;
                                LODWORD(v67) = v185;
                                if ( v75 )
                                  goto LABEL_147;
                                v82 = 87;
LABEL_151:
                                SetLastError(v82);
                                goto LABEL_147;
                              }
                              v77 = 1;
LABEL_131:
                              v81 = v75 + 1;
                            }
                            else
                            {
                              if ( v77 >= 0 )
                                goto LABEL_131;
LABEL_351:
                              v81 = v75;
                            }
                            v76 = (unsigned int *)v75;
                            v75 = (_QWORD *)*v81;
                            if ( !*v81 )
                            {
                              v82 = (unsigned int)v196;
LABEL_134:
                              if ( v82 )
                                goto LABEL_150;
                              v69 = (WCHAR *)Src;
                              break;
                            }
                            continue;
                          }
                        }
                        v83 = *(_DWORD *)v69 + 56;
                        if ( *(_DWORD *)v69 >= v83
                          || (v84 = v83 + v68, v68 > v83 + v68)
                          || v83 > v84
                          || (v85 = v83 + v68,
                              (v86 = (unsigned int **)operator new(v84, (const struct std::nothrow_t *)&std::nothrow)) == 0) )
                        {
                          v82 = 14;
LABEL_150:
                          LODWORD(v67) = v185;
                          v63 = v191;
                          goto LABEL_151;
                        }
                        memset_0(v86, 0, v85);
                        v87 = v201;
                        v88 = (unsigned int *)Src;
                        v86[4] = (unsigned int *)(v86 + 6);
                        v86[3] = (unsigned int *)*v87;
                        *v87 = v86;
                        v89 = v86[4];
                        v86[2] = v76;
                        *((_DWORD *)v86 + 10) = 1;
                        *v89 = v68;
                        memcpy_0(v86 + 7, v88, *v88);
                        memcpy_0((char *)v86 + *v88 + 56, v202, v68);
                        v90 = v194;
                        if ( v76 )
                        {
                          if ( v77 < 0 )
                            *(_QWORD *)v76 = v86;
                          else
                            *((_QWORD *)v76 + 1) = v86;
                        }
                        else
                        {
                          *v194 = (struct PERFLIBCI_RED_BLACK_NODE *)v86;
                        }
                        PerflibciInsertRedBlackNode(v90, (struct PERFLIBCI_RED_BLACK_NODE *)v86);
                        v63 = v191;
                        LODWORD(v67) = v185;
                        *(_DWORD *)(*(_QWORD *)v91 + 40LL) = 0;
LABEL_147:
                        v65 = *v63;
                        v61 = v203;
                        if ( (unsigned int)v67 < *v63 )
                          continue;
                        break;
                      }
                      v58 = v200;
                      v57 = v188;
                    }
LABEL_157:
                    v55 = v187;
                    goto LABEL_158;
                  }
                  if ( v60 )
                  {
                    switch ( v60 )
                    {
                      case 1:
                        v115 = *(void **)(v61 + 8);
                        v171 = operator new((unsigned int)v58[5]);
                        *(_QWORD *)(v61 + 8) = v171;
                        if ( !v171 )
                        {
LABEL_211:
                          v55 = v187;
                          if ( v115 )
                            *(_QWORD *)(v61 + 8) = v115;
                          else
                            *(_QWORD *)(v61 + 16) = 14;
                          goto LABEL_158;
                        }
                        LocalFree(v115);
                        v169 = v58 + 4;
                        *(_DWORD *)(v61 + 16) = *v58;
                        *(_DWORD *)(v61 + 20) = v58[1];
                        v170 = (unsigned int)v58[5];
LABEL_311:
                        memcpy_0(*(void **)(v61 + 8), v169, v170);
                        v55 = v187;
                        if ( *(_DWORD *)(v61 + 16) )
                          *(_DWORD *)(v61 + 16) = 0;
                        goto LABEL_158;
                      case 2:
                        v115 = *(void **)(v61 + 8);
                        v116 = operator new((unsigned int)v58[2]);
                        *(_QWORD *)(v61 + 8) = v116;
                        if ( !v116 )
                          goto LABEL_211;
                        LocalFree(v115);
                        v169 = v58;
                        *(_DWORD *)(v61 + 16) = *v58;
                        *(_DWORD *)(v61 + 20) = v58[1];
                        v170 = (unsigned int)v58[2];
                        goto LABEL_311;
                      case 4:
                        if ( v58[5] )
                        {
                          if ( !*(_QWORD *)(v61 + 8) )
                          {
                            v159 = operator new(24);
                            *(_QWORD *)(v61 + 8) = v159;
                            if ( !v159 )
                              goto LABEL_156;
                          }
                          v160 = *v58;
                          *(_DWORD *)(v61 + 16) = *v58;
                          *(_DWORD *)(v61 + 20) = v58[1];
                          if ( v160 )
                            *(_DWORD *)(v61 + 16) = 0;
                          v161 = v58[4];
                          if ( v161 > 8 )
                          {
                            v162 = (unsigned int)v190;
                            v163 = 8;
                            do
                            {
                              v164 = (struct _PERF_INSTANCE_HEADER *)((char *)v58 + v163 + 16);
                              v163 += v164->Size;
                              if ( v163 <= v161 )
                              {
                                v165 = (struct _PERF_COUNTER_DATA *)((char *)v58 + v163 + 16);
                                v163 += v165->dwSize;
                                if ( v163 <= v161 )
                                {
                                  if ( ((*(_DWORD *)(v61 + 24) - 4) & 0xFFFFFFF7) == 0 )
                                  {
                                    v166 = v162++;
                                    v164->InstanceId = v166;
                                  }
                                  PerflibciFindOutputInstance(
                                    *(struct PERFLIBCI_MULTI_INSTS **)(v61 + 8),
                                    v164,
                                    v165,
                                    v165->dwSize,
                                    ReturnLength);
                                }
                              }
                              v161 = v58[4];
                            }
                            while ( v163 < v161 );
                            LODWORD(v190) = v162;
                            v57 = v188;
                          }
                        }
                        goto LABEL_157;
                    }
                  }
                  if ( v60 )
                    *v58 = 13;
                  v173 = *(_DWORD *)(v61 + 16);
                  if ( v173 && v173 != *v58 )
                  {
                    v12 = (*(_BYTE *)(v61 + 24) & 8) == 0;
                    *(_DWORD *)(v61 + 16) = *v58;
                    v55 = v187;
                    *(_DWORD *)(v61 + 20) = v58[1];
                    if ( v12 )
                      *(_QWORD *)(v61 + 8) = 0;
                    goto LABEL_158;
                  }
                  goto LABEL_157;
                }
LABEL_158:
                v95 = v58[2];
                v57 += v95;
                v188 = v57;
                if ( !v95 )
                  break;
              }
              v14 = Counter;
              QuadPart = (char *)Frequency.QuadPart;
              v54 = v192;
            }
          }
        }
        LocalFree(QuadPart);
LABEL_162:
        v7 = a1;
        QuadPart = 0;
      }
      v14 = *(LARGE_INTEGER *)v14.QuadPart;
      Counter = v14;
    }
    while ( v14.QuadPart );
    v6 = a2;
    LODWORD(v13) = 48;
    v5 = a3;
  }
  if ( v181 )
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPriority, &v198, 4u);
  if ( *((_DWORD *)v7 + 12) )
  {
    v15 = 0;
    v16 = v5;
    v188 = 0;
    Counter.QuadPart = v5;
    v17 = v5;
    while ( 1 )
    {
      v18 = *((_QWORD *)v7 + 5);
      v19 = (struct PERFLIBCI_RED_BLACK_NODE **)(32LL * v15);
      v194 = v19;
      v192 = v18;
      v20 = *(_DWORD *)((char *)v19 + v18 + 20);
      if ( !v20 )
      {
LABEL_30:
        if ( (v20 & 0xFFFFFFF9) != 0 )
          *(_DWORD *)((char *)v19 + v18 + 16) = 13;
        if ( (unsigned __int64)(unsigned int)v13 + 16 > v17 )
          goto LABEL_213;
        *(_DWORD *)((unsigned int)v13 + v6) = *(_DWORD *)((char *)v19 + v18 + 16);
        *(_DWORD *)((unsigned int)v13 + v6 + 4) = 0;
        *(_QWORD *)((unsigned int)v13 + v6 + 8) = 16;
LABEL_34:
        LODWORD(v13) = v13 + 16;
        goto LABEL_35;
      }
      if ( v20 != 1 )
        break;
      v21 = *(struct PERFLIBCI_RED_BLACK_NODE **)((char *)v19 + v18 + 8);
      if ( !v21 )
      {
        if ( (unsigned __int64)(unsigned int)v13 + 16 <= v17 )
        {
          *(_QWORD *)((unsigned int)v13 + v6) = 232;
          *(_QWORD *)((unsigned int)v13 + v6 + 8) = 16;
          goto LABEL_34;
        }
LABEL_213:
        v183 = 8;
        goto LABEL_34;
      }
      v22 = v21[1] + 16;
      v23 = v22 + v13;
      if ( v22 + (int)v13 > v5 )
      {
        v183 = 8;
      }
      else
      {
        *(_DWORD *)((unsigned int)v13 + v6) = *(_DWORD *)((char *)v19 + v18 + 16);
        *(_DWORD *)((unsigned int)v13 + v6 + 4) = *(_DWORD *)((char *)v19 + v18 + 20);
        *(_DWORD *)((unsigned int)v13 + v6 + 8) = v22;
        *(_DWORD *)((unsigned int)v13 + v6 + 12) = 0;
        memcpy_0((void *)(v6 + (unsigned int)v13 + 16LL), v21, (unsigned int)v21[1]);
      }
      LODWORD(v13) = v23;
      LocalFree(*(struct PERFLIBCI_RED_BLACK_NODE **)((char *)v19 + v18 + 8));
      v7 = a1;
      v17 = v16;
      *(struct PERFLIBCI_RED_BLACK_NODE **)((char *)v19 + v18 + 8) = 0;
LABEL_35:
      v15 = v188 + 1;
      v188 = v15;
      if ( v15 >= *((_DWORD *)v7 + 12) )
        goto LABEL_36;
      v6 = a2;
    }
    if ( v20 == 2 )
    {
      v117 = *(__int64 *)((char *)v19 + v18 + 8);
      if ( v117 )
      {
        v118 = *(unsigned int *)(v117 + 8);
        v119 = v118 + v13;
        if ( (int)v118 + (int)v13 <= v5 )
        {
          *(_DWORD *)((unsigned int)v13 + v6) = *(_DWORD *)((char *)v19 + v18 + 16);
          v167 = *(_DWORD *)((char *)v19 + v18 + 20);
          *(_DWORD *)((unsigned int)v13 + v6 + 8) = v118;
          *(_DWORD *)((unsigned int)v13 + v6 + 4) = v167;
          *(_DWORD *)((unsigned int)v13 + v6 + 12) = 0;
          memcpy_0((void *)(v6 + (unsigned int)v13 + 16LL), (const void *)(v117 + 16), v118 - 16);
        }
        else
        {
          v183 = 8;
        }
        LODWORD(v13) = v119;
        LocalFree(*(struct PERFLIBCI_RED_BLACK_NODE **)((char *)v19 + v18 + 8));
        v7 = a1;
        *(struct PERFLIBCI_RED_BLACK_NODE **)((char *)v19 + v18 + 8) = 0;
      }
      else
      {
        if ( (unsigned __int64)(unsigned int)v13 + 16 > v16 )
        {
          v183 = 8;
        }
        else
        {
          *(_QWORD *)((unsigned int)v13 + v6) = 232;
          *(_QWORD *)((unsigned int)v13 + v6 + 8) = 16;
        }
        LODWORD(v13) = v13 + 16;
      }
      v17 = v16;
      goto LABEL_35;
    }
    if ( v20 != 4 && v20 != 6 )
      goto LABEL_30;
    v24 = *(unsigned __int16 **)(v18 + 32LL * v15);
    v191 = 0;
    v196 = v24;
    Frequency.QuadPart = 0;
    if ( v24 )
    {
      CounterSet = PerflibciCreateOrFindCounterSet(v24, 0, 0, 0, 0);
      v26 = CounterSet;
      if ( CounterSet )
      {
        if ( (*(_BYTE *)(CounterSet + 88) & 4) != 0 )
        {
          v27 = 1;
          v180 = 1;
          if ( *((_DWORD *)v24 + 6) == -1 )
            v28 = *(_DWORD *)(CounterSet + 128);
          else
            v28 = 1;
LABEL_50:
          v29 = v196;
          if ( *((_DWORD *)v196 + 5) > 0x28u && PerflibciWildcardInstance(v196 + 20) )
          {
            v30 = 1;
            v182 = 1;
            if ( v27 )
            {
              v168 = v29[20] - 42;
              if ( v29[20] == 42 )
                v168 = v29[21];
              v27 = v168 == 0;
              v180 = v168 == 0;
            }
          }
          else
          {
            v30 = 0;
            v182 = 0;
          }
          Src = (void *)Counter.QuadPart;
          if ( (unsigned __int64)(unsigned int)v13 + 16 > Counter.QuadPart )
          {
            v31 = 0;
            v183 = 8;
            v186 = 0;
          }
          else
          {
            v31 = (unsigned int)v13 + v6;
            v186 = v31;
            *(_DWORD *)v31 = *(_DWORD *)((char *)v19 + v18 + 16);
            *(_QWORD *)(v31 + 8) = 16;
            if ( v30 )
              v32 = *(_DWORD *)((char *)v19 + v18 + 20);
            else
              v32 = (*(_DWORD *)((char *)v19 + v18 + 20) == 6) + 1;
            *(_DWORD *)(v31 + 4) = v32;
          }
          v13 = (unsigned int)(v13 + 16);
          v33 = *(__int64 *)((char *)v19 + v18 + 8);
          v184 = v13;
          if ( *(_DWORD *)((char *)v19 + v192 + 20) == 6 )
          {
            if ( v33 )
            {
              v44 = *(_DWORD **)(v33 + 16);
              v191 = v44;
              v45 = *v44;
              if ( *v44 + (int)v13 > a3 )
              {
                v183 = 8;
              }
              else
              {
                memcpy_0((void *)(v6 + (unsigned int)v13), v44, v45);
                v44 = v191;
                v27 = v180;
                v29 = v196;
                v45 = *v191;
              }
              if ( v31 )
                *(_DWORD *)(v31 + 8) += v45;
              v13 = (unsigned int)(*v44 + v13);
              v184 = v13;
            }
            else
            {
              v183 = 13;
            }
          }
          if ( !v27 )
            goto LABEL_59;
          Frequency.QuadPart = 0;
          v121 = *((_QWORD *)a1 + 7);
          if ( !v121 )
            goto LABEL_329;
          v122 = *((_DWORD *)v29 + 8);
          if ( *((_DWORD *)a1 + 16) <= v122 )
            goto LABEL_329;
          v123.QuadPart = v121 + 16LL * v122;
          Frequency = v123;
          v124 = *(_DWORD *)(v123.QuadPart + 8);
          if ( v124 < v28 )
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
            v174 = operator new(saturated_mul(v28, 0x18u));
            v175 = 0;
            *(_QWORD *)v123.QuadPart = v174;
            if ( v174 )
              v175 = v28;
            *(_DWORD *)(v123.QuadPart + 8) = v175;
          }
          v125 = *(_DWORD **)v123.QuadPart;
          if ( !*(_QWORD *)v123.QuadPart )
          {
LABEL_329:
            v27 = 0;
            v180 = 0;
LABEL_59:
            v34 = v182;
            if ( v182 )
            {
              if ( (unsigned __int64)(v13 + 8) > Counter.QuadPart )
              {
                v35 = 0;
                v183 = 8;
              }
              else
              {
                v35 = (_DWORD *)(v13 + v6);
                *(_QWORD *)(v13 + v6) = 8;
              }
              v36 = v186;
              v190 = v35;
              if ( v186 )
                *(_DWORD *)(v186 + 8) += 8;
              v34 = v182;
              LODWORD(v13) = v13 + 8;
              v184 = v13;
            }
            else
            {
              v36 = v186;
              v35 = 0;
              v190 = 0;
            }
            v37 = v192;
            if ( *(struct PERFLIBCI_RED_BLACK_NODE **)((char *)v19 + v192 + 8) )
            {
              v38 = *(_QWORD **)v33;
              v199 = (__int64)v38;
              if ( v38 )
              {
                while ( 1 )
                {
                  v39 = (unsigned int *)v38[4];
                  v40 = (_QWORD *)v38[3];
                  v200 = v40;
                  if ( v39 )
                  {
                    v41 = *v39;
                    v42 = v39[2];
                    if ( v34 )
                    {
                      if ( (unsigned int)v42 + v41 + (unsigned int)v13 > a3 )
                      {
                        v183 = 8;
                        if ( v35 )
                        {
                          ++v35[1];
                          *v35 += v41 + v39[2];
                        }
                        if ( v36 )
                          *(_DWORD *)(v36 + 8) += v41 + v39[2];
                      }
                      else
                      {
                        memcpy_0((void *)(a2 + (unsigned int)v13), v39 + 2, (unsigned int)v42 + v41);
                        v43 = v190;
                        ++v190[1];
                        *v43 += v41 + v39[2];
                        *(_DWORD *)(v186 + 8) += v41 + v39[2];
                      }
                      v27 = v180;
                      LODWORD(v13) = v41 + v39[2] + v13;
                      v37 = v192;
                      v184 = v13;
                    }
                    if ( v27 && !v183 )
                    {
                      v96 = v42 + 8;
                      v97 = 0;
                      v98 = (unsigned int *)((char *)v39 + v96);
                      v99 = 0;
                      if ( v41 )
                        break;
                    }
                  }
LABEL_73:
                  if ( (*((_BYTE *)v194 + v37 + 24) & 8) == 0 )
                  {
                    LocalFree(v38);
                    v37 = v192;
                  }
                  v35 = v190;
                  v38 = v40;
                  v36 = v186;
                  v27 = v180;
                  v34 = v182;
                  v199 = (__int64)v40;
                  if ( !v40 )
                  {
                    v19 = v194;
                    goto LABEL_77;
                  }
                }
                v100 = v191;
                v101 = Frequency;
                v102 = v196;
                while ( 1 )
                {
                  v103 = *((_DWORD *)v102 + 6);
                  if ( v103 == -1 && v100 && (unsigned int)v99 < v100[1] )
                    v103 = v100[v99 + 2];
                  if ( v101.QuadPart )
                  {
                    if ( v103 != -1 )
                    {
                      if ( *(_QWORD *)v101.QuadPart )
                      {
                        v104 = *(_DWORD *)(v101.QuadPart + 12);
                        if ( v104 )
                        {
                          v105 = 0;
                          while ( 1 )
                          {
                            v106 = *(_QWORD *)v101.QuadPart + 24 * v105;
                            if ( *(_DWORD *)(v106 + 8) == v103 )
                              break;
                            v105 = (unsigned int)(v105 + 1);
                            if ( (unsigned int)v105 >= v104 )
                              goto LABEL_179;
                          }
                          if ( v106 )
                            break;
                        }
                      }
                    }
                  }
LABEL_179:
                  v107 = (unsigned int)v98[1];
                  v97 += v107;
                  if ( v97 < (unsigned int)v107 || v97 >= v41 )
                  {
                    v38 = (_QWORD *)v199;
                    LODWORD(v13) = v184;
                    v40 = v200;
                    v37 = v192;
                    goto LABEL_73;
                  }
                  v99 = (unsigned int)(v99 + 1);
                  v98 = (_DWORD *)((char *)v98 + v107);
                }
                v108 = *(_DWORD *)(v106 + 16);
                if ( !v108 )
                  *(_DWORD *)(v106 + 20) = *v98;
                if ( *v98 == 4 )
                {
                  v109 = (unsigned int)v98[2];
                }
                else if ( *v98 == 8 )
                {
                  v109 = *((_QWORD *)v98 + 1);
                }
                else
                {
                  v109 = 0;
                }
                v110 = *(_DWORD *)(v106 + 12);
                if ( v110 == 2 || (v113 = v110 - 1) == 0 )
                {
                  if ( v109 < 0 )
                    v111 = (double)(int)(v109 & 1 | ((unsigned __int64)v109 >> 1))
                         + (double)(int)(v109 & 1 | ((unsigned __int64)v109 >> 1));
                  else
                    v111 = (double)(int)v109;
                  v112 = v111 + *(double *)v106;
                }
                else
                {
                  v114 = v113 - 2;
                  if ( v114 )
                  {
                    if ( v114 != 1 )
                      goto LABEL_193;
                    if ( v108 )
                    {
                      if ( v109 < 0 )
                        v112 = (double)(int)(v109 & 1 | ((unsigned __int64)v109 >> 1))
                             + (double)(int)(v109 & 1 | ((unsigned __int64)v109 >> 1));
                      else
                        v112 = (double)(int)v109;
                      if ( v112 <= *(double *)v106 )
                      {
                        *(_DWORD *)(v106 + 16) = v108 + 1;
                        goto LABEL_179;
                      }
                      goto LABEL_192;
                    }
                  }
                  else if ( v108 )
                  {
                    if ( v109 < 0 )
                      v120 = (double)(int)(v109 & 1 | ((unsigned __int64)v109 >> 1))
                           + (double)(int)(v109 & 1 | ((unsigned __int64)v109 >> 1));
                    else
                      v120 = (double)(int)v109;
                    if ( *(double *)v106 > v120 )
                    {
                      *(double *)v106 = v120;
                      *(_DWORD *)(v106 + 16) = v108 + 1;
                      goto LABEL_179;
                    }
                    goto LABEL_193;
                  }
                  if ( v109 < 0 )
                    v112 = (double)(int)(v109 & 1 | ((unsigned __int64)v109 >> 1))
                         + (double)(int)(v109 & 1 | ((unsigned __int64)v109 >> 1));
                  else
                    v112 = (double)(int)v109;
                }
LABEL_192:
                *(double *)v106 = v112;
LABEL_193:
                *(_DWORD *)(v106 + 16) = v108 + 1;
                goto LABEL_179;
              }
LABEL_77:
              if ( (*((_BYTE *)v19 + v37 + 24) & 8) == 0 )
              {
                LocalFree(*(struct PERFLIBCI_RED_BLACK_NODE **)((char *)v19 + v37 + 8));
                *(struct PERFLIBCI_RED_BLACK_NODE **)((char *)v19 + v192 + 8) = 0;
              }
            }
            v7 = a1;
            if ( v180 )
            {
              v134 = *((_QWORD *)a1 + 7);
              if ( v134 )
              {
                v135 = *((_DWORD *)v196 + 8);
                if ( *((_DWORD *)a1 + 16) > v135 )
                {
                  v136 = 2LL * v135;
                  if ( *(_QWORD *)(v134 + 16LL * v135) )
                  {
                    if ( *(_DWORD *)(v134 + 16LL * v135 + 12) )
                    {
                      if ( v182 )
                      {
                        v137 = v13 + 24;
                        if ( (int)v13 + 24 > a3 )
                        {
                          v183 = 8;
                          LODWORD(v13) = v13 + 24;
                          v184 = v137;
                        }
                        else
                        {
                          v138 = L"_Total";
                          v139 = 2147483646;
                          v140 = (_QWORD *)(a2 + (unsigned int)v13);
                          v141 = 7;
                          *v140 = 24;
                          v142 = v140 + 1;
                          do
                          {
                            if ( !v139 )
                              break;
                            if ( !*v138 )
                              break;
                            *v142++ = *v138++;
                            --v139;
                            --v141;
                          }
                          while ( v141 );
                          v184 = v13 + 24;
                          v143 = v142 - 1;
                          LODWORD(v13) = v13 + 24;
                          if ( v141 )
                            v143 = v142;
                          *v143 = 0;
                          if ( v140 )
                          {
                            v176 = v190;
                            if ( v190 )
                            {
                              ++v190[1];
                              *v176 += *(_DWORD *)v140;
                            }
                            if ( v186 )
                              *(_DWORD *)(v186 + 8) += *(_DWORD *)v140;
                          }
                        }
                      }
                      v144 = 0;
                      if ( *(_DWORD *)(v134 + 8 * v136 + 12) )
                      {
                        v145 = Src;
                        while ( 2 )
                        {
                          v146 = *(_QWORD *)(v134 + 8 * v136);
                          v147 = (_DWORD *)(v146 + 20 + 24 * v144);
                          if ( (unsigned int)v13 + (unsigned __int64)((*v147 + 7) & 0xFFFFFFF8) + 8 > (unsigned __int64)v145 )
                          {
                            v183 = 8;
                            goto LABEL_281;
                          }
                          v148 = (_DWORD *)((unsigned int)v13 + a2);
                          LODWORD(v192) = ((*(_DWORD *)(v146 + 20 + 24 * v144) + 7) & 0xFFFFFFF8) + 8;
                          memset_0(v148, 0, (unsigned int)v192);
                          v149 = v190;
                          *v148 = *v147;
                          v150 = v192;
                          v148[1] = v192;
                          if ( v149 )
                            *v149 += v150;
                          if ( v186 )
                            *(_DWORD *)(v186 + 8) += v148[1];
                          v151 = *(_DWORD *)(v146 + 24 * v144 + 12);
                          if ( v151 == 4 )
                            goto LABEL_273;
                          if ( !v151 )
                            goto LABEL_289;
                          v156 = v151 - 1;
                          if ( !v156 )
                          {
LABEL_273:
                            v152 = *(_DWORD *)(v146 + 20 + 24 * v144);
                            v147 = (_DWORD *)(v146 + 20 + 24 * v144);
                            if ( v152 == 4 )
                            {
                              v148[2] = (int)*(double *)(v146 + 24 * v144);
                              goto LABEL_280;
                            }
                            if ( v152 != 8 )
                              goto LABEL_280;
                            v153 = *(double *)(v146 + 24 * v144);
                            v154 = 0;
                            if ( v153 >= 9.223372036854776e18 )
                            {
                              v153 = v153 - 9.223372036854776e18;
                              if ( v153 < 9.223372036854776e18 )
                                v154 = 0x8000000000000000uLL;
                            }
                            v155 = (unsigned int)(int)v153;
                          }
                          else
                          {
                            v157 = v156 - 1;
                            if ( v157 )
                            {
                              if ( v157 != 1 )
                              {
LABEL_289:
                                v158 = *(_DWORD *)(v146 + 20 + 24 * v144);
                                v147 = (_DWORD *)(v146 + 20 + 24 * v144);
                                if ( v158 == 4 )
                                {
                                  v148[2] = 0;
                                }
                                else if ( v158 == 8 )
                                {
                                  *((_QWORD *)v148 + 1) = 0;
                                }
                                goto LABEL_280;
                              }
                              goto LABEL_273;
                            }
                            v177 = *(_DWORD *)(v146 + 20 + 24 * v144);
                            v147 = (_DWORD *)(v146 + 20 + 24 * v144);
                            if ( v177 == 4 )
                            {
                              v148[2] = (int)(*(double *)(v146 + 24 * v144) / (double)*(int *)(v146 + 24 * v144 + 16));
                              goto LABEL_280;
                            }
                            if ( v177 != 8 )
                            {
LABEL_280:
                              LODWORD(v13) = v184;
                              v145 = Src;
LABEL_281:
                              v144 = (unsigned int)(v144 + 1);
                              LODWORD(v13) = ((*v147 + 7) & 0xFFFFFFF8) + v13 + 8;
                              v184 = v13;
                              if ( (unsigned int)v144 >= *(_DWORD *)(v134 + 8 * v136 + 12) )
                              {
                                v7 = a1;
                                goto LABEL_80;
                              }
                              continue;
                            }
                            v154 = 0;
                            v178 = *(double *)(v146 + 24 * v144) / (double)*(int *)(v146 + 24 * v144 + 16);
                            if ( v178 >= 9.223372036854776e18 )
                            {
                              v178 = v178 - 9.223372036854776e18;
                              if ( v178 < 9.223372036854776e18 )
                                v154 = 0x8000000000000000uLL;
                            }
                            v155 = (unsigned int)(int)v178;
                          }
                          break;
                        }
                        *((_QWORD *)v148 + 1) = v154 + v155;
                        goto LABEL_280;
                      }
                    }
                  }
                }
              }
            }
LABEL_80:
            v17 = (unsigned __int64)Src;
            v5 = a3;
            v16 = (unsigned __int64)Src;
            goto LABEL_35;
          }
          v126 = v196;
          v127 = v191;
          *(_DWORD *)(v123.QuadPart + 12) = 0;
          v128 = *((_DWORD *)v126 + 6);
          if ( v128 == -1 )
          {
            if ( !v127 || (v129 = v127[1], v130 = 0, !v129) )
            {
LABEL_249:
              if ( *(_DWORD *)(v123.QuadPart + 12) )
              {
                v27 = v180;
              }
              else
              {
                v27 = 0;
                v180 = 0;
              }
              goto LABEL_59;
            }
          }
          else
          {
            v129 = 1;
            v130 = 0;
          }
          v131 = v196;
          do
          {
            if ( *((_DWORD *)v131 + 6) == -1 )
              v128 = v127[v130 + 2];
            v132 = *(_DWORD **)(v26 + 120);
            for ( j = *(_DWORD *)(v26 + 128); j; --j )
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
          v19 = v194;
          goto LABEL_249;
        }
        v27 = 0;
        v28 = 0;
      }
      else
      {
        v27 = 0;
        v28 = 0;
      }
    }
    else
    {
      v26 = 0;
      v27 = 0;
      v28 = 0;
    }
    v180 = 0;
    goto LABEL_50;
  }
LABEL_36:
  if ( (v183 & 0xFFFFFFF7) == 0 )
  {
    if ( v5 >= 0x30 )
    {
      *(_DWORD *)a2 = v13;
      *(_DWORD *)(a2 + 4) = *((_DWORD *)v7 + 12);
    }
    *a4 = v13;
  }
  return v183;
}

```

## disassembly

```asm
0x180006930  mov     [rsp-8+arg_18], r9
0x180006935  mov     [rsp-8+arg_10], r8d
0x18000693a  mov     [rsp-8+arg_8], rdx
0x18000693f  mov     [rsp-8+arg_0], rcx
0x180006944  push    rbp
0x180006945  push    rbx
0x180006946  push    rsi
0x180006947  push    r13
0x180006949  push    r14
0x18000694b  lea     rbp, [rsp-40h]
0x180006950  sub     rsp, 140h
0x180006957  xor     r13d, r13d
0x18000695a  mov     esi, r8d
0x18000695d  mov     dword ptr [rsp+160h+Size], r13d
0x180006962  mov     r14, rdx
0x180006965  mov     [rbp+60h+var_B8], r13d
0x180006969  mov     rbx, rcx
0x18000696c  test    r9, r9
0x18000696f  jnz     short loc_180006985
0x180006971  mov     eax, 57h ; 'W'
0x180006976  add     rsp, 140h
0x18000697d  pop     r14
0x18000697f  pop     r13
0x180006981  pop     rsi
0x180006982  pop     rbx
0x180006983  pop     rbp
0x180006984  retn
0x180006985  mov     [r9], r13d
0x180006988  test    esi, esi
0x18000698a  jnz     loc_180007663
0x180006990  call    ?PerflibciNotifyQuery@@YAXPEAU_PERF_QUERY@@@Z; PerflibciNotifyQuery(_PERF_QUERY *)
0x180006995  cmp     [rbx+28h], r13
0x180006999  jz      loc_180007E62
0x18000699f  mov     ecx, r13d
0x1800069a2  mov     [rsp+160h+var_28], rdi
0x1800069aa  mov     [rsp+160h+var_30], r12
0x1800069b2  mov     dword ptr [rsp+160h+var_F8], r13d
0x1800069b7  cmp     [rbx+30h], r13d
0x1800069bb  jbe     short loc_1800069E3
0x1800069bd  mov     rdx, [rbx+28h]
0x1800069c1  mov     eax, ecx
0x1800069c3  shl     rax, 5
0x1800069c7  test    byte ptr [rax+rdx+18h], 8
0x1800069cc  mov     qword ptr [rax+rdx+10h], 0E8h
0x1800069d5  jnz     short loc_1800069DC
0x1800069d7  mov     [rax+rdx+8], r13
0x1800069dc  inc     ecx
0x1800069de  cmp     ecx, [rbx+30h]
0x1800069e1  jb      short loc_1800069BD
0x1800069e3  xorps   xmm0, xmm0
0x1800069e6  mov     [rsp+160h+var_108], 0Fh
0x1800069ee  mov     r12d, 30h ; '0'
0x1800069f4  mov     [rsp+160h+ReturnLength], r13; ReturnLength
0x1800069f9  mov     r9d, r12d; ThreadInformationLength
0x1800069fc  lea     r8, [rbp+60h+ThreadInformation]; ThreadInformation
0x180006a00  xor     edx, edx; ThreadInformationClass
0x180006a02  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180006a09  movups  [rbp+60h+ThreadInformation], xmm0
0x180006a0d  movups  [rbp+60h+var_78], xmm0
0x180006a11  movups  [rbp+60h+var_68], xmm0
0x180006a15  call    cs:__imp_NtQueryInformationThread
0x180006a1b  test    eax, eax
0x180006a1d  js      loc_180007E6C
0x180006a23  mov     eax, dword ptr [rbp+60h+var_68+8]
0x180006a26  cmp     eax, [rsp+160h+var_108]
0x180006a2a  jge     loc_180006F72
0x180006a30  mov     r9d, 4; ThreadInformationLength
0x180006a36  mov     [rbp+60h+var_B8], eax
0x180006a39  lea     r8, [rsp+160h+var_108]; ThreadInformation
0x180006a3e  mov     edx, 2; ThreadInformationClass
0x180006a43  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180006a4a  call    cs:__imp_NtSetInformationThread
0x180006a50  test    eax, eax
0x180006a52  setns   [rsp+160h+var_11F]
0x180006a57  cmp     esi, r12d
0x180006a5a  jnb     loc_180006F2B
0x180006a60  mov     [rsp+160h+var_11C], 8
0x180006a68  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a6f  test    byte ptr [rcx+1Ch], 8
0x180006a73  jnz     loc_180007CFD
0x180006a79  mov     rcx, rbx; struct _PERF_QUERY *
0x180006a7c  call    ?PerfpCollectKernelData@@YAKPEAU_PERF_QUERY@@@Z; PerfpCollectKernelData(_PERF_QUERY *)
0x180006a81  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a88  test    byte ptr [rcx+1Ch], 8
0x180006a8c  jnz     loc_180007D21
0x180006a92  mov     rdi, [rbx+18h]
0x180006a96  mov     [rsp+160h+var_38], r15
0x180006a9e  mov     qword ptr [rbp+60h+Counter], rdi
0x180006aa2  test    rdi, rdi
0x180006aa5  jz      short loc_180006AD1
0x180006aa7  mov     rax, [rdi+8]
0x180006aab  cmp     dword ptr [rax+20h], 1
0x180006aaf  jnz     loc_180007019
0x180006ab5  mov     rdi, [rdi]
0x180006ab8  mov     qword ptr [rbp+60h+Counter], rdi
0x180006abc  test    rdi, rdi
0x180006abf  jnz     short loc_180006AA7
0x180006ac1  mov     r14, [rbp+60h+arg_8]
0x180006ac5  mov     r12d, 30h ; '0'
0x180006acb  mov     esi, [rbp+60h+arg_10]
0x180006ad1  cmp     [rsp+160h+var_11F], 0
0x180006ad6  jz      short loc_180006AF4
0x180006ad8  mov     r9d, 4; ThreadInformationLength
0x180006ade  lea     r8, [rbp+60h+var_B8]; ThreadInformation
0x180006ae2  mov     edx, 2; ThreadInformationClass
0x180006ae7  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180006aee  call    cs:__imp_NtSetInformationThread
0x180006af4  cmp     dword ptr [rbx+30h], 0
0x180006af8  jbe     loc_180006BC4
0x180006afe  mov     eax, r13d
0x180006b01  mov     edi, esi
0x180006b03  movaps  [rsp+160h+var_50], xmm6
0x180006b0b  movsd   xmm6, cs:__real@43e0000000000000
0x180006b13  mov     [rsp+160h+var_108], eax
0x180006b17  mov     qword ptr [rbp+60h+Counter], rdi
0x180006b1b  mov     r8d, esi
0x180006b1e  jmp     short loc_180006B24
0x180006b20  mov     r14, [rbp+60h+arg_8]
0x180006b24  mov     r15, [rbx+28h]
0x180006b28  mov     r13d, eax
0x180006b2b  shl     r13, 5
0x180006b2f  mov     [rbp+60h+var_D8], r13
0x180006b33  mov     [rsp+160h+var_E8], r15
0x180006b38  mov     ecx, [r15+r13+14h]
0x180006b3d  mov     eax, ecx
0x180006b3f  test    ecx, ecx
0x180006b41  jz      short loc_180006B67
0x180006b43  sub     eax, 1
0x180006b46  jz      loc_180006C0B
0x180006b4c  sub     eax, 1
0x180006b4f  jz      loc_18000767C
0x180006b55  sub     eax, 2
0x180006b58  jz      loc_180006C84
0x180006b5e  cmp     eax, 2
0x180006b61  jz      loc_180006C84
0x180006b67  test    ecx, 0FFFFFFF9h
0x180006b6d  jnz     loc_180007D57
0x180006b73  cmp     ecx, 4
0x180006b76  jz      loc_180007D57
0x180006b7c  mov     ecx, r12d
0x180006b7f  lea     rax, [rcx+10h]
0x180006b83  cmp     rax, r8
0x180006b86  ja      loc_180007656
0x180006b8c  mov     eax, [r15+r13+10h]
0x180006b91  mov     [rcx+r14], eax
0x180006b95  xor     eax, eax
0x180006b97  mov     [rcx+r14+4], eax
0x180006b9c  mov     qword ptr [rcx+r14+8], 10h
0x180006ba5  add     r12d, 10h
0x180006ba9  mov     eax, [rsp+160h+var_108]
0x180006bad  inc     eax
0x180006baf  mov     [rsp+160h+var_108], eax
0x180006bb3  cmp     eax, [rbx+30h]
0x180006bb6  jb      loc_180006B20
0x180006bbc  movaps  xmm6, [rsp+160h+var_50]
0x180006bc4  mov     edx, [rsp+160h+var_11C]
0x180006bc8  mov     r15, [rsp+160h+var_38]
0x180006bd0  mov     rdi, [rsp+160h+var_28]
0x180006bd8  test    edx, 0FFFFFFF7h
0x180006bde  jnz     short loc_180006BFC
0x180006be0  cmp     esi, 30h ; '0'
0x180006be3  jb      short loc_180006BF2
0x180006be5  mov     rax, [rbp+60h+arg_8]
0x180006be9  mov     [rax], r12d
0x180006bec  mov     ecx, [rbx+30h]
0x180006bef  mov     [rax+4], ecx
0x180006bf2  mov     rcx, [rbp+60h+arg_18]
0x180006bf9  mov     [rcx], r12d
0x180006bfc  mov     r12, [rsp+160h+var_30]
0x180006c04  mov     eax, edx
0x180006c06  jmp     loc_180006976
0x180006c0b  mov     rdx, [r15+r13+8]; Src
0x180006c10  test    rdx, rdx
0x180006c13  jz      loc_180007F4F
0x180006c19  mov     r8d, [rdx+4]
0x180006c1d  add     r8d, 10h
0x180006c21  lea     ebx, [r8+r12]
0x180006c25  cmp     ebx, esi
0x180006c27  ja      loc_1800075E0
0x180006c2d  mov     eax, [r15+r13+10h]
0x180006c32  mov     ecx, r12d
0x180006c35  mov     [rcx+r14], eax
0x180006c39  mov     eax, [r15+r13+14h]
0x180006c3e  mov     [rcx+r14+4], eax
0x180006c43  mov     [rcx+r14+8], r8d
0x180006c48  mov     dword ptr [rcx+r14+0Ch], 0
0x180006c51  add     rcx, 10h
0x180006c55  mov     r8d, [rdx+4]; Size
0x180006c59  add     rcx, r14; void *
0x180006c5c  call    memcpy_0
0x180006c61  mov     rcx, [r15+r13+8]; hMem
0x180006c66  mov     r12d, ebx
0x180006c69  call    cs:__imp_LocalFree
0x180006c6f  mov     rbx, [rbp+60h+arg_0]
0x180006c73  mov     r8, rdi
0x180006c76  mov     qword ptr [r15+r13+8], 0
0x180006c7f  jmp     loc_180006BA9
0x180006c84  mov     rbx, [r15+r13]
0x180006c88  xor     ecx, ecx
0x180006c8a  mov     [rsp+160h+var_F0], rcx
0x180006c8f  mov     [rbp+60h+var_C8], rbx
0x180006c93  mov     qword ptr [rbp+60h+Frequency], rcx
0x180006c97  test    rbx, rbx
0x180006c9a  jz      loc_180007C4C
0x180006ca0  mov     [rsp+160h+var_130], ecx; int
0x180006ca4  xor     r9d, r9d
0x180006ca7  mov     [rsp+160h+var_138], cx; __int16
0x180006cac  xor     r8d, r8d
0x180006caf  mov     [rsp+160h+ReturnLength], rcx; void *
0x180006cb4  xor     edx, edx; Src
0x180006cb6  mov     rcx, rbx; Buf1
0x180006cb9  call    PerflibciCreateOrFindCounterSet
0x180006cbe  mov     rdi, rax
0x180006cc1  test    rax, rax
0x180006cc4  jz      loc_180007006
0x180006cca  test    byte ptr [rax+58h], 4
0x180006cce  jnz     loc_180007705
0x180006cd4  xor     r9b, r9b
0x180006cd7  xor     ebx, ebx
0x180006cd9  mov     [rsp+160h+var_120], r9b
0x180006cde  mov     r11, [rbp+60h+var_C8]
0x180006ce2  cmp     dword ptr [r11+14h], 28h ; '('
0x180006ce7  jbe     loc_180006F8D
0x180006ced  lea     rcx, [r11+28h]; unsigned __int16 *
0x180006cf1  call    ?PerflibciWildcardInstance@@YAEPEBG@Z; PerflibciWildcardInstance(ushort const *)
0x180006cf6  test    al, al
0x180006cf8  jz      loc_180006F8D
0x180006cfe  mov     r10b, 1
0x180006d01  mov     [rsp+160h+var_11F], r10b
0x180006d06  test    r9b, r9b
0x180006d09  jnz     loc_180007B7A
0x180006d0f  mov     rdx, qword ptr [rbp+60h+Counter]
0x180006d13  mov     ecx, r12d
0x180006d16  mov     [rbp+60h+Src], rdx
0x180006d1a  lea     rax, [rcx+10h]
0x180006d1e  cmp     rax, rdx
0x180006d21  ja      loc_180006FF2
0x180006d27  mov     eax, [r15+r13+10h]
0x180006d2c  lea     rsi, [rcx+r14]
0x180006d30  mov     [rsp+160h+var_110], rsi
0x180006d35  mov     [rsi], eax
0x180006d37  mov     qword ptr [rsi+8], 10h
0x180006d3f  test    r10b, r10b
0x180006d42  jz      loc_180007D45
0x180006d48  mov     eax, [r15+r13+14h]
0x180006d4d  mov     [rsi+4], eax
0x180006d50  mov     rax, [rsp+160h+var_E8]
0x180006d55  add     r12d, 10h
0x180006d59  mov     r15, [r15+r13+8]
0x180006d5e  mov     [rsp+160h+var_118], r12d
0x180006d63  cmp     dword ptr [rax+r13+14h], 6
0x180006d69  jz      loc_180006F9A
0x180006d6f  test    r9b, r9b
0x180006d72  jnz     loc_180007722
0x180006d78  movzx   eax, [rsp+160h+var_11F]
0x180006d7d  test    al, al
0x180006d7f  jz      loc_180006F7C
0x180006d85  lea     rax, [r12+8]
0x180006d8a  cmp     rax, qword ptr [rbp+60h+Counter]
0x180006d8e  ja      loc_1800075FA
0x180006d94  lea     rdx, [r12+r14]
0x180006d98  mov     qword ptr [rdx], 8
0x180006d9f  mov     r8, [rsp+160h+var_110]
0x180006da4  mov     [rsp+160h+var_F8], rdx
0x180006da9  test    r8, r8
0x180006dac  jz      short loc_180006DB3
0x180006dae  add     dword ptr [r8+8], 8
0x180006db3  movzx   eax, [rsp+160h+var_11F]
0x180006db8  add     r12d, 8
0x180006dbc  mov     [rsp+160h+var_118], r12d
0x180006dc1  mov     rcx, [rsp+160h+var_E8]
0x180006dc6  cmp     qword ptr [rcx+r13+8], 0
0x180006dcc  jz      loc_180006ED6
0x180006dd2  mov     r15, [r15]
0x180006dd5  mov     [rbp+60h+var_B0], r15
0x180006dd9  test    r15, r15
0x180006ddc  jz      loc_180006EB5
0x180006de2  nop     dword ptr [rax+00h]
0x180006de6  nop     word ptr [rax+rax+00000000h]
0x180006df0  mov     rdi, [r15+20h]
0x180006df4  mov     r13, [r15+18h]
0x180006df8  mov     [rbp+60h+var_A8], r13
0x180006dfc  test    rdi, rdi
0x180006dff  jz      short loc_180006E73
0x180006e01  mov     r14d, [rdi]
0x180006e04  mov     esi, [rdi+8]
0x180006e07  test    al, al
0x180006e09  jz      short loc_180006E6A
0x180006e0b  lea     ecx, [rsi+r14]
0x180006e0f  lea     eax, [rcx+r12]
0x180006e13  cmp     eax, [rbp+60h+arg_10]
0x180006e19  ja      loc_180006EF7
0x180006e1f  mov     r8d, ecx; Size
0x180006e22  lea     rdx, [rdi+8]; Src
0x180006e26  mov     ecx, r12d
0x180006e29  add     rcx, [rbp+60h+arg_8]; void *
0x180006e2d  call    memcpy_0
0x180006e32  mov     rdx, [rsp+160h+var_F8]
0x180006e37  mov     r8, [rsp+160h+var_110]
0x180006e3c  inc     dword ptr [rdx+4]
  ... truncated ...
```
