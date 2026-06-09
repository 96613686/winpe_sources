# Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::GetProcessedPerformanceCounterValues(Microsoft::DiagnosticsHub::EtwProvider::ProcessCounterType,unsigned __int64,unsigned __int64,std::function<bool (unsigned __int64)>,uint,std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DataPoint,std::allocator<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DataPoint>> &)

- ea: `0x18002c0f8`
- end: `0x18002cb88`
- name: `?GetProcessedPerformanceCounterValues@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJW4ProcessCounterType@EtwProvider@34@_K1V?$function@$$A6A_N_K@Z@std@@IAEAV?$vector@UDataPoint@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UDataPoint@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@8@@Z`
- size: `2704`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800134f0`

## callees

- `0x180009570`
- `0x180009e14`
- `0x180009f84`
- `0x180015250`
- `0x180026af8`
- `0x180027108`
- `0x18002c0f8`
- `0x18002cef8`
- `0x18002cfc8`
- `0x18002d128`
- `0x180049b50`
- `0x18004a078`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x18002c467`
- `VCRUNTIME140!memmove` at `0x18002c4d0`
- `VCRUNTIME140!memmove` at `0x18002c709`
- `VCRUNTIME140!memmove` at `0x18002c725`
- `VCRUNTIME140!memmove` at `0x18002c89e`
- `VCRUNTIME140!memmove` at `0x18002c8bd`
- `VCRUNTIME140!memmove` at `0x18002c467`
- `VCRUNTIME140!memmove` at `0x18002c4d0`
- `VCRUNTIME140!memmove` at `0x18002c709`
- `VCRUNTIME140!memmove` at `0x18002c725`
- `VCRUNTIME140!memmove` at `0x18002c89e`
- `VCRUNTIME140!memmove` at `0x18002c8bd`
- `KERNEL32!LeaveCriticalSection` at `0x18002c510`
- `KERNEL32!LeaveCriticalSection` at `0x18002c510`
- `KERNEL32!EnterCriticalSection` at `0x18002c1d8`
- `KERNEL32!EnterCriticalSection` at `0x18002c1d8`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x18002c96c`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x18002c96c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002c2a0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002c965`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002c2a0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002c965`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::GetProcessedPerformanceCounterValues(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        __int64 a5,
        int a6,
        const void **a7)
{
  __int64 v10; // r14
  const void **v11; // r12
  __int64 v12; // rcx
  __int64 v14; // rcx
  struct _RTL_CRITICAL_SECTION *v15; // rsi
  char *v16; // r11
  char *v17; // rcx
  unsigned __int64 v18; // rcx
  void **v19; // rbx
  void *v20; // rcx
  char *v21; // r8
  __int64 v22; // rdx
  char *v23; // r12
  char *v24; // rbx
  char *v25; // r14
  char *v26; // rcx
  char *v27; // r12
  char *v28; // rdi
  _OWORD *v29; // rdx
  unsigned __int64 v30; // rdx
  unsigned __int64 v31; // rcx
  char *v32; // rax
  size_t v33; // r14
  char *v34; // r14
  size_t v35; // rbx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rdx
  unsigned int v40; // edi
  __int64 v41; // r11
  int v42; // esi
  void **v43; // rbx
  __int64 v44; // rcx
  char v45; // al
  char *v46; // rcx
  char *v47; // rdi
  __int64 v48; // rbx
  unsigned __int64 v49; // rcx
  unsigned __int64 v50; // rdx
  unsigned __int64 v51; // r13
  char *v52; // rax
  __int64 v53; // rbx
  char *v54; // r8
  _BYTE *v55; // rdx
  char *v56; // rcx
  size_t v57; // r8
  __int64 v58; // rbx
  __int64 v59; // rdi
  int *v60; // r8
  unsigned __int64 v61; // rax
  int v62; // edx
  unsigned __int64 v63; // rsi
  __int64 v64; // rcx
  __int128 *v65; // rax
  __int64 v66; // rbx
  __int64 v67; // rdi
  int *v68; // rcx
  int *v69; // rax
  _DWORD *v70; // rcx
  __int64 v71; // r13
  unsigned __int64 v72; // rcx
  unsigned __int64 v73; // rcx
  unsigned __int64 v74; // rax
  _DWORD *v75; // rax
  _BYTE *v76; // r8
  _BYTE *v77; // rcx
  void *v78; // rdx
  _DWORD *v79; // rcx
  _QWORD *v80; // rcx
  unsigned __int64 v81; // rcx
  __int64 v82; // r8
  __int64 v83; // r9
  __int64 v84; // rcx
  __int64 v85; // rdx
  double v86; // xmm0_8
  __int64 v87; // rcx
  double v88; // xmm1_8
  double v89; // xmm1_8
  __int64 v90; // rax
  double *v91; // rdx
  int v92; // r8d
  unsigned __int64 v93; // r10
  int **v94; // r9
  unsigned __int64 v95; // rdx
  int *v96; // rax
  __int64 v97; // rcx
  __int64 v98; // r8
  double v99; // xmm0_8
  double *v100; // rdx
  __int64 v101; // rdx
  __int64 v102; // rcx
  unsigned int v103; // [rsp+38h] [rbp-B1h]
  unsigned int v104; // [rsp+38h] [rbp-B1h]
  __int64 v105; // [rsp+40h] [rbp-A9h]
  void **v106; // [rsp+48h] [rbp-A1h]
  _DWORD *v107; // [rsp+48h] [rbp-A1h]
  char *v109; // [rsp+50h] [rbp-99h]
  unsigned __int64 v110; // [rsp+50h] [rbp-99h]
  __int64 v111; // [rsp+58h] [rbp-91h] BYREF
  double v112; // [rsp+60h] [rbp-89h]
  __int64 v113; // [rsp+68h] [rbp-81h]
  __int64 v114; // [rsp+70h] [rbp-79h]
  __int64 v115; // [rsp+78h] [rbp-71h]
  void *Block[2]; // [rsp+80h] [rbp-69h] BYREF
  void *v117; // [rsp+90h] [rbp-59h]
  void *Src; // [rsp+98h] [rbp-51h] BYREF
  __int128 v119; // [rsp+A0h] [rbp-49h] BYREF
  _OWORD *v120; // [rsp+B0h] [rbp-39h]
  __int128 v121; // [rsp+B8h] [rbp-31h] BYREF
  __int64 v122; // [rsp+C8h] [rbp-21h]
  __int128 v123; // [rsp+D0h] [rbp-19h] BYREF
  __int128 v124; // [rsp+E0h] [rbp-9h] BYREF

  v10 = a5;
  v115 = a5;
  v11 = a7;
  if ( *(_DWORD *)a1 == -1 )
  {
    v12 = *(_QWORD *)(a5 + 56);
    if ( v12 )
    {
      LOBYTE(a2) = v12 != a5;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 32LL))(v12, a2);
      *(_QWORD *)(a5 + 56) = 0;
    }
    return 2147942405LL;
  }
  if ( a3 > a4 )
  {
    v14 = *(_QWORD *)(a5 + 56);
    if ( v14 )
    {
      LOBYTE(a2) = v14 != a5;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 32LL))(v14, a2);
      *(_QWORD *)(a5 + 56) = 0;
    }
    return 2147942487LL;
  }
  v119 = 0;
  v120 = 0;
  *(_OWORD *)Block = 0;
  v117 = 0;
  v15 = (struct _RTL_CRITICAL_SECTION *)(a1 + 144);
  v111 = a1 + 144;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 144));
  *(_BYTE *)(a1 + 328) = 1;
  v103 = *(_DWORD *)(a1 + 556);
  v123 = *(_OWORD *)(a1 + 384);
  v16 = *(char **)(a1 + 336);
  v17 = *(char **)(a1 + 344);
  if ( v16 != v17 )
  {
    v18 = (v17 - v16) >> 4;
    if ( *(_QWORD *)v16 < a3 || *(_QWORD *)&v16[16 * v18 - 16] >= a4 )
    {
      v21 = *(char **)(a1 + 336);
      while ( 1 )
      {
        while ( 1 )
        {
          if ( (__int64)v18 <= 0 )
          {
            v24 = v21;
            v25 = v21;
            goto LABEL_26;
          }
          v22 = 16 * (v18 >> 1);
          v23 = &v21[v22];
          if ( *(_QWORD *)&v21[v22] >= a3 )
            break;
          v21 = v23 + 16;
          v18 += -1LL - (v18 >> 1);
        }
        if ( *(_QWORD *)v23 < a4 )
          break;
        v18 >>= 1;
      }
      v25 = v21;
      v30 = v22 >> 4;
      while ( (__int64)v30 > 0 )
      {
        if ( *(_QWORD *)&v25[16 * (v30 >> 1)] < a3 )
        {
          v25 += 16 * (v30 >> 1) + 16;
          v30 += -1LL - (v30 >> 1);
        }
        else
        {
          v30 >>= 1;
        }
      }
      v24 = v23 + 16;
      v31 = (__int64)&v21[16 * v18 - (_QWORD)(v23 + 16)] >> 4;
      while ( (__int64)v31 > 0 )
      {
        if ( *(_QWORD *)&v24[16 * (v31 >> 1)] < a3 || *(_QWORD *)&v24[16 * (v31 >> 1)] < a4 )
        {
          v24 += 16 * (v31 >> 1) + 16;
          v31 += -1LL - (v31 >> 1);
        }
        else
        {
          v31 >>= 1;
        }
      }
LABEL_26:
      v26 = *(char **)(a1 + 360);
      v27 = &v26[(v25 - v16) & 0xFFFFFFFFFFFFFFF0uLL];
      v28 = &v26[(v24 - v16) & 0xFFFFFFFFFFFFFFF0uLL];
      if ( v27 != v26 )
        v123 = *((_OWORD *)v27 - 1);
      if ( v25 != v24 )
      {
        v29 = (_OWORD *)*((_QWORD *)&v119 + 1);
        do
        {
          if ( v29 == v120 )
          {
            std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(
              &v119,
              v29,
              v25);
            v29 = (_OWORD *)*((_QWORD *)&v119 + 1);
          }
          else
          {
            *v29 = *(_OWORD *)v25;
            v29 = (_OWORD *)(*((_QWORD *)&v119 + 1) + 16LL);
            *((_QWORD *)&v119 + 1) += 16LL;
          }
          v25 += 16;
        }
        while ( v25 != v24 );
      }
      v32 = *(char **)(a1 + 336);
      v109 = v32;
      if ( v32 != v24 )
      {
        v33 = *(_QWORD *)(a1 + 344) - (_QWORD)v24;
        memmove(v32, v24, v33);
        *(_QWORD *)(a1 + 344) = &v109[v33];
      }
      while ( v27 != v28 )
      {
        if ( Block[1] == v117 )
        {
          std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(
            Block,
            Block[1],
            v27);
        }
        else
        {
          *(_OWORD *)Block[1] = *(_OWORD *)v27;
          Block[1] = (char *)Block[1] + 16;
        }
        v27 += 16;
      }
      v34 = *(char **)(a1 + 360);
      if ( v34 != v28 )
      {
        v35 = *(_QWORD *)(a1 + 368) - (_QWORD)v28;
        memmove(*(void **)(a1 + 360), v28, v35);
        *(_QWORD *)(a1 + 368) = &v34[v35];
      }
      v11 = a7;
      v10 = a5;
    }
    else
    {
      std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DataPoint>::operator=(&v119);
      v19 = (void **)(a1 + 360);
      if ( Block != (void **)(a1 + 360) )
      {
        v20 = Block[0];
        if ( Block[0] )
        {
          if ( (((unsigned __int64)v117 - (unsigned __int64)Block[0]) & 0xFFFFFFFFFFFFFFF0uLL) >= 0x1000 )
          {
            _mm_lfence();
            v20 = (void *)*((_QWORD *)Block[0] - 1);
            if ( (unsigned __int64)((char *)Block[0] - (char *)v20 - 8) > 0x1F )
              _invoke_watson(0, 0, 0, 0, 0);
          }
          operator delete(v20);
          *(_OWORD *)Block = 0;
          v117 = 0;
        }
        Block[0] = *v19;
        Block[1] = *(void **)(a1 + 368);
        v117 = *(void **)(a1 + 376);
        *v19 = 0;
        *(_QWORD *)(a1 + 368) = 0;
        *(_QWORD *)(a1 + 376) = 0;
      }
    }
  }
  if ( Block[0] != Block[1] )
    *(_OWORD *)(a1 + 384) = *(_OWORD *)((char *)Block[0]
                                      + (((char *)Block[1] - (char *)Block[0]) & 0xFFFFFFFFFFFFFFF0uLL)
                                      - 16);
  LeaveCriticalSection(v15);
  if ( (_QWORD)v119 == *((_QWORD *)&v119 + 1) )
  {
    std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::~vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(Block);
    std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::~vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(&v119);
    v38 = *(_QWORD *)(v10 + 56);
    if ( v38 )
    {
      LOBYTE(v37) = v38 != v10;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 32LL))(v38, v37);
      *(_QWORD *)(v10 + 56) = 0;
    }
    return 1;
  }
  v39 = 0x64 % v103;
  v40 = 0x64 / v103;
  v104 = v40;
  v121 = 0;
  v122 = 0;
  if ( v40 > 1 )
  {
    _mm_lfence();
    std::vector<std::vector<int>>::_Resize_reallocate<std::_Value_init_tag>(&v121, v40);
  }
  v110 = 0;
  v41 = 0;
  v105 = 0;
  v124 = 0;
  v42 = -1;
  if ( (int)((__int64)(*((_QWORD *)&v119 + 1) - v119) >> 4) > -1 )
  {
    while ( 1 )
    {
      if ( v42 == -1 )
      {
        v43 = (void **)&v124;
        v106 = (void **)&v124;
      }
      else
      {
        v43 = (void **)(v119 + 16LL * v42);
        v106 = v43;
        Src = *v43;
        v44 = *(_QWORD *)(v10 + 56);
        if ( !v44 )
        {
          std::_Xbad_function_call();
          __debugbreak();
        }
        v45 = (*(__int64 (__fastcall **)(__int64, void **, __int64, __int64))(*(_QWORD *)v44 + 16LL))(
                v44,
                &Src,
                v36,
                0xFFFFFFFFFFFFFFFLL);
        v41 = v105;
        if ( !v45 )
          goto LABEL_84;
      }
      if ( v40 > 1 )
        break;
      if ( v42 != -1 )
      {
        v46 = (char *)v11[2];
        v47 = (char *)v11[1];
        if ( v47 == v46 )
        {
          v48 = (v47 - (_BYTE *)*v11) >> 4;
          if ( v48 == 0xFFFFFFFFFFFFFFFLL )
            std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(
              v46,
              v39);
          v113 = v48 + 1;
          v49 = (v46 - (_BYTE *)*v11) >> 4;
          v50 = v49 >> 1;
          if ( v49 <= 0xFFFFFFFFFFFFFFFLL - (v49 >> 1) )
          {
            v51 = v48 + 1;
            if ( v49 + v50 >= v48 + 1 )
              v51 = v49 + v50;
            if ( v51 > 0xFFFFFFFFFFFFFFFLL )
              goto LABEL_140;
          }
          else
          {
            v51 = 0xFFFFFFFFFFFFFFFLL;
          }
          _mm_lfence();
          v52 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(16 * v51);
          Src = v52;
          v53 = 16 * v48;
          *(_OWORD *)&v52[v53] = *(_OWORD *)v106;
          v54 = (char *)v11[1];
          v55 = *v11;
          v56 = v52;
          if ( v47 == v54 )
          {
            v57 = v54 - v55;
          }
          else
          {
            memmove(v52, v55, v47 - (_BYTE *)*v11);
            v57 = (_BYTE *)v11[1] - v47;
            v56 = (char *)Src + v53 + 16;
            v55 = v47;
          }
          memmove(v56, v55, v57);
          std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DataPoint>::_Change_array(
            v11,
            Src,
            v113,
            v51);
          v40 = v104;
LABEL_83:
          v41 = v105;
          goto LABEL_84;
        }
        *(_OWORD *)v47 = *(_OWORD *)v43;
        v11[1] = (char *)v11[1] + 16;
        v40 = v104;
      }
LABEL_84:
      if ( ++v42 >= (int)((__int64)(*((_QWORD *)&v119 + 1) - v119) >> 4) )
        goto LABEL_85;
    }
    _mm_lfence();
    v39 = (v42 + 1) % v40;
    v111 = v39;
    v66 = 3LL * (unsigned int)v39;
    v67 = v121;
    v68 = *(int **)(v121 + 24LL * (unsigned int)v39 + 16);
    v69 = *(int **)(v121 + 24LL * (unsigned int)v39 + 8);
    Src = v69;
    if ( v69 == v68 )
    {
      _mm_lfence();
      v71 = ((__int64)v69 - *(_QWORD *)(v121 + 24LL * (unsigned int)v39)) >> 2;
      if ( v71 == 0x3FFFFFFFFFFFFFFFLL )
        std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(v68, v39);
      v113 = v71 + 1;
      v72 = ((__int64)v68 - *(_QWORD *)(v121 + 24LL * (unsigned int)v39)) >> 2;
      if ( v72 <= 0x3FFFFFFFFFFFFFFFLL - (v72 >> 1) )
      {
        v74 = v72 + (v72 >> 1);
        v73 = v71 + 1;
        if ( v74 >= v71 + 1 )
          v73 = v74;
        if ( v73 > 0x3FFFFFFFFFFFFFFFLL )
LABEL_140:
          __scrt_throw_std_bad_array_new_length();
      }
      else
      {
        v73 = 0x3FFFFFFFFFFFFFFFLL;
      }
      _mm_lfence();
      v114 = 4 * v73;
      v75 = (_DWORD *)std::_Allocate<16,std::_Default_allocate_traits>(4 * v73);
      v107 = v75;
      v75[v71] = v42;
      v76 = *(_BYTE **)(v67 + 8 * v66 + 8);
      v77 = Src;
      _mm_lfence();
      v78 = *(void **)(v67 + 8 * v66);
      if ( v77 == v76 )
      {
        v79 = v75;
      }
      else
      {
        memmove(v75, v78, (_BYTE *)Src - (_BYTE *)v78);
        v76 = *(_BYTE **)(v67 + 8 * v66 + 8);
        v78 = Src;
        v79 = &v107[v71 + 1];
      }
      memmove(v79, v78, v76 - (_BYTE *)v78);
      v80 = *(_QWORD **)(v67 + 8 * v66);
      if ( v80 )
      {
        _mm_lfence();
        if ( ((*(_QWORD *)(v67 + 8 * v66 + 16) - (_QWORD)v80) & 0xFFFFFFFFFFFFFFFCuLL) >= 0x1000 )
        {
          _mm_lfence();
          if ( (unsigned __int64)v80 - *(v80 - 1) - 8 > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
          v80 = (_QWORD *)*(v80 - 1);
        }
        operator delete(v80);
      }
      *(_QWORD *)(v67 + 8 * v66) = v107;
      v70 = &v107[v113];
      *(_QWORD *)(v67 + 8 * v66 + 8) = v70;
      *(_QWORD *)(v67 + 8 * v66 + 16) = &v107[(unsigned __int64)v114 / 4];
      v39 = v111;
    }
    else
    {
      *v69 = v42;
      *(_QWORD *)(v67 + 24LL * (unsigned int)v39 + 8) += 4LL;
      v70 = *(_DWORD **)(v67 + 24LL * (unsigned int)v39 + 8);
    }
    v81 = ((__int64)v70 - *(_QWORD *)(v67 + 8 * v66)) >> 2;
    v40 = v104;
    if ( v81 > v110 )
    {
      v110 = v81;
      v41 = v39;
      v105 = v39;
      goto LABEL_84;
    }
    goto LABEL_83;
  }
LABEL_85:
  if ( v40 > 1 )
  {
    _mm_lfence();
    v58 = 3 * v41;
    v59 = v121;
    v60 = *(int **)(v121 + 24 * v41);
    v61 = (__int64)(*(_QWORD *)(v121 + 24 * v41 + 8) - (_QWORD)v60) >> 2;
    if ( v61 > 1 )
    {
      _mm_lfence();
      v62 = *v60;
      v63 = 1;
      v64 = *(_QWORD *)(v121 + 24 * v41);
      if ( (unsigned __int64)((*(_QWORD *)(v121 + 24 * v41 + 8) - v64) >> 2) > 1 )
      {
        do
        {
          if ( v62 == -1 )
            v65 = &v123;
          else
            v65 = (__int128 *)((char *)Block[0] + 16 * v62);
          v82 = 2LL * *(int *)(v64 + 4 * v63);
          v83 = *((_QWORD *)v65 + 1);
          v84 = *((_QWORD *)Block[0] + 2 * *(int *)(v64 + 4 * v63) + 1);
          if ( v84 != v83 )
          {
            v85 = *((_QWORD *)Block[0] + v82) - *(_QWORD *)v65;
            if ( v85 < 0 )
              v86 = (double)(int)(v85 & 1 | ((unsigned __int64)v85 >> 1))
                  + (double)(int)(v85 & 1 | ((unsigned __int64)v85 >> 1));
            else
              v86 = (double)(int)v85;
            v87 = v84 - v83;
            if ( v87 < 0 )
              v88 = (double)(int)(v87 & 1 | ((unsigned __int64)v87 >> 1))
                  + (double)(int)(v87 & 1 | ((unsigned __int64)v87 >> 1));
            else
              v88 = (double)(int)v87;
            v89 = fmin(100.0, v86 / v88 * 100.0);
            v90 = *(_QWORD *)(v119 + 8 * v82);
            v111 = v90;
            v112 = v89;
            v91 = (double *)v11[1];
            if ( v91 == v11[2] )
            {
              std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(
                v11,
                v91,
                &v111);
            }
            else
            {
              *(_QWORD *)v91 = v90;
              v91[1] = v89;
              v11[1] = (char *)v11[1] + 16;
            }
          }
          v64 = *(_QWORD *)(v59 + 8 * v58);
          v62 = *(_DWORD *)(v64 + 4 * v63++);
        }
        while ( v63 < (*(_QWORD *)(v59 + 8 * v58 + 8) - v64) >> 2 );
      }
      goto LABEL_135;
    }
    if ( v61 == 1 )
    {
      _mm_lfence();
      v92 = *v60;
      if ( v92 != -1 )
      {
LABEL_132:
        v97 = 2LL * v92;
        v98 = *(_QWORD *)(v119 + 16LL * v92);
        v111 = v98;
        v99 = *(double *)(v119 + 8 * v97 + 8);
        v112 = v99;
        v100 = (double *)v11[1];
        if ( v100 == v11[2] )
        {
          std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(
            v11,
            v100,
            &v111);
        }
        else
        {
          *(_QWORD *)v100 = v98;
          v100[1] = v99;
          v11[1] = (char *)v11[1] + 16;
        }
        goto LABEL_135;
      }
      v93 = 0;
      v94 = (int **)v121;
      v95 = (*((_QWORD *)&v121 + 1) - (_QWORD)v121) / 24LL;
      if ( v95 )
      {
        do
        {
          if ( v93 != v41 )
          {
            v96 = *v94;
            if ( *v94 != v94[1] )
            {
              v92 = *v96;
              if ( *v96 != -1 )
                goto LABEL_132;
            }
          }
          ++v93;
          v94 += 3;
        }
        while ( v93 < v95 );
      }
    }
  }
LABEL_135:
  std::vector<std::vector<int>>::~vector<std::vector<int>>(&v121);
  std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::~vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(Block);
  std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::~vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(&v119);
  v102 = *(_QWORD *)(v10 + 56);
  if ( v102 )
  {
    LOBYTE(v101) = v102 != v10;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v102 + 32LL))(v102, v101);
    *(_QWORD *)(v10 + 56) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18002c0f8  mov     rax, rsp
0x18002c0fb  mov     [rax+10h], rbx
0x18002c0ff  mov     [rax+18h], rsi
0x18002c103  push    rbp
0x18002c104  push    rdi
0x18002c105  push    r12
0x18002c107  push    r13
0x18002c109  push    r14
0x18002c10b  lea     rbp, [rax-47h]
0x18002c10f  sub     rsp, 100h
0x18002c116  movaps  xmmword ptr [rax-38h], xmm6
0x18002c11a  mov     rax, cs:__security_cookie
0x18002c121  xor     rax, rsp
0x18002c124  mov     [rbp+3Fh+var_38], rax
0x18002c128  mov     rbx, r9
0x18002c12b  mov     [rsp+120h+var_D8], rbx
0x18002c130  mov     rdi, r8
0x18002c133  mov     r13, rcx
0x18002c136  mov     r14, [rbp+3Fh+arg_20]
0x18002c13a  mov     [rsp+120h+var_E8], r14
0x18002c13f  mov     [rbp+3Fh+var_B0], r14
0x18002c143  mov     r12, [rbp+3Fh+arg_30]
0x18002c147  mov     [rsp+120h+var_E0], r12
0x18002c14c  cmp     dword ptr [rcx], 0FFFFFFFFh
0x18002c14f  jnz     short loc_18002C17F
0x18002c151  mov     rcx, [r14+38h]
0x18002c155  test    rcx, rcx
0x18002c158  jz      short loc_18002C175
0x18002c15a  cmp     rcx, r14
0x18002c15d  setnz   dl
0x18002c160  mov     rax, [rcx]
0x18002c163  mov     rax, [rax+20h]
0x18002c167  call    cs:__guard_dispatch_icall_fptr
0x18002c16d  mov     qword ptr [r14+38h], 0
0x18002c175  mov     eax, 80070005h
0x18002c17a  jmp     loc_18002CB49
0x18002c17f  cmp     rdi, rbx
0x18002c182  jbe     short loc_18002C1B2
0x18002c184  mov     rcx, [r14+38h]
0x18002c188  test    rcx, rcx
0x18002c18b  jz      short loc_18002C1A8
0x18002c18d  cmp     rcx, r14
0x18002c190  setnz   dl
0x18002c193  mov     rax, [rcx]
0x18002c196  mov     rax, [rax+20h]
0x18002c19a  call    cs:__guard_dispatch_icall_fptr
0x18002c1a0  mov     qword ptr [r14+38h], 0
0x18002c1a8  mov     eax, 80070057h
0x18002c1ad  jmp     loc_18002CB49
0x18002c1b2  xor     eax, eax
0x18002c1b4  xorps   xmm1, xmm1
0x18002c1b7  movdqu  [rbp+3Fh+var_88], xmm1
0x18002c1bc  mov     [rbp+3Fh+var_78], rax
0x18002c1c0  movdqu  xmmword ptr [rbp+3Fh+Block], xmm1
0x18002c1c5  mov     [rbp+3Fh+var_98], rax
0x18002c1c9  lea     rsi, [rcx+90h]
0x18002c1d0  mov     [rsp+120h+var_D0], rsi
0x18002c1d5  mov     rcx, rsi; lpCriticalSection
0x18002c1d8  call    cs:__imp_EnterCriticalSection
0x18002c1de  nop
0x18002c1df  mov     byte ptr [r13+148h], 1
0x18002c1e7  mov     eax, [r13+22Ch]
0x18002c1ee  mov     dword ptr [rsp+120h+var_F0], eax
0x18002c1f2  movups  xmm0, xmmword ptr [r13+180h]
0x18002c1fa  movdqu  [rbp+3Fh+var_58], xmm0
0x18002c1ff  lea     rdx, [r13+150h]
0x18002c206  mov     r11, [rdx]
0x18002c209  mov     rcx, [rdx+8]
0x18002c20d  cmp     r11, rcx
0x18002c210  jz      loc_18002C4EB
0x18002c216  sub     rcx, r11
0x18002c219  sar     rcx, 4
0x18002c21d  mov     rax, rcx
0x18002c220  add     rax, rax
0x18002c223  cmp     [r11], rdi
0x18002c226  jb      loc_18002C2EF
0x18002c22c  cmp     [r11+rax*8-10h], rbx
0x18002c231  jnb     loc_18002C2EF
0x18002c237  lea     rcx, [rbp+3Fh+var_88]
0x18002c23b  call    ??4?$vector@UDataPoint@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UDataPoint@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DataPoint>::operator=(std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DataPoint> &&)
0x18002c240  lea     rbx, [r13+168h]
0x18002c247  lea     rax, [rbp+3Fh+Block]
0x18002c24b  cmp     rax, rbx
0x18002c24e  jz      loc_18002C4EB
0x18002c254  mov     rcx, [rbp+3Fh+Block]; Block
0x18002c258  test    rcx, rcx
0x18002c25b  jz      short loc_18002C2BC
0x18002c25d  mov     rdx, [rbp+3Fh+var_98]
0x18002c261  sub     rdx, rcx
0x18002c264  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18002c268  cmp     rdx, 1000h
0x18002c26f  jb      short loc_18002C2A7
0x18002c271  lfence
0x18002c274  add     rdx, 27h ; '''
0x18002c278  mov     rax, [rbp+3Fh+Block]
0x18002c27c  mov     rcx, [rax-8]
0x18002c280  sub     rax, rcx
0x18002c283  sub     rax, 8
0x18002c287  cmp     rax, 1Fh
0x18002c28b  jbe     short loc_18002C2A7
0x18002c28d  mov     [rsp+120h+Reserved], 0; Reserved
0x18002c296  xor     r9d, r9d; LineNo
0x18002c299  xor     r8d, r8d; FileName
0x18002c29c  xor     edx, edx; FunctionName
0x18002c29e  xor     ecx, ecx; Expression
0x18002c2a0  call    cs:__imp__invoke_watson
0x18002c2a7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c2ac  xorps   xmm0, xmm0
0x18002c2af  movdqu  xmmword ptr [rbp+3Fh+Block], xmm0
0x18002c2b4  mov     [rbp+3Fh+var_98], 0
0x18002c2bc  mov     rax, [rbx]
0x18002c2bf  mov     [rbp+3Fh+Block], rax
0x18002c2c3  mov     rax, [rbx+8]
0x18002c2c7  mov     [rbp+3Fh+Block+8], rax
0x18002c2cb  mov     rax, [rbx+10h]
0x18002c2cf  mov     [rbp+3Fh+var_98], rax
0x18002c2d3  mov     qword ptr [rbx], 0
0x18002c2da  mov     qword ptr [rbx+8], 0
0x18002c2e2  mov     qword ptr [rbx+10h], 0
0x18002c2ea  jmp     loc_18002C4EB
0x18002c2ef  mov     r8, r11
0x18002c2f2  jmp     short loc_18002C329
0x18002c2f4  mov     r9, rcx
0x18002c2f7  shr     r9, 1
0x18002c2fa  mov     rdx, r9
0x18002c2fd  shl     rdx, 4
0x18002c301  lea     r12, [rdx+r8]
0x18002c305  cmp     [r12], rdi
0x18002c309  jb      short loc_18002C31A
0x18002c30b  cmp     [r12], rbx
0x18002c30f  jb      loc_18002C395
0x18002c315  mov     rcx, r9
0x18002c318  jmp     short loc_18002C329
0x18002c31a  lea     r8, [r12+10h]
0x18002c31f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c323  sub     rax, r9
0x18002c326  add     rcx, rax
0x18002c329  test    rcx, rcx
0x18002c32c  jg      short loc_18002C2F4
0x18002c32e  mov     rbx, r8
0x18002c331  mov     r14, r8
0x18002c334  mov     rcx, [r13+168h]
0x18002c33b  mov     r12, r14
0x18002c33e  sub     r12, r11
0x18002c341  and     r12, 0FFFFFFFFFFFFFFF0h
0x18002c345  add     r12, rcx
0x18002c348  mov     rdi, rbx
0x18002c34b  sub     rdi, r11
0x18002c34e  and     rdi, 0FFFFFFFFFFFFFFF0h
0x18002c352  add     rdi, rcx
0x18002c355  cmp     r12, rcx
0x18002c358  jz      short loc_18002C365
0x18002c35a  movups  xmm0, xmmword ptr [r12-10h]
0x18002c360  movdqu  [rbp+3Fh+var_58], xmm0
0x18002c365  cmp     r14, rbx
0x18002c368  jz      loc_18002C443
0x18002c36e  mov     rdx, qword ptr [rbp+3Fh+var_88+8]
0x18002c372  cmp     rdx, [rbp+3Fh+var_78]
0x18002c376  jz      loc_18002C426
0x18002c37c  movups  xmm0, xmmword ptr [r14]
0x18002c380  movdqu  xmmword ptr [rdx], xmm0
0x18002c384  mov     rdx, qword ptr [rbp+3Fh+var_88+8]
0x18002c388  add     rdx, 10h
0x18002c38c  mov     qword ptr [rbp+3Fh+var_88+8], rdx
0x18002c390  jmp     loc_18002C436
0x18002c395  mov     r14, r8
0x18002c398  sar     rdx, 4
0x18002c39c  jmp     short loc_18002C3C7
0x18002c39e  mov     r9, rdx
0x18002c3a1  shr     r9, 1
0x18002c3a4  mov     r10, r9
0x18002c3a7  add     r10, r10
0x18002c3aa  cmp     [r14+r10*8], rdi
0x18002c3ae  jb      short loc_18002C3B5
0x18002c3b0  mov     rdx, r9
0x18002c3b3  jmp     short loc_18002C3C7
0x18002c3b5  lea     r14, [r14+r10*8]
0x18002c3b9  add     r14, 10h
0x18002c3bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c3c1  sub     rax, r9
0x18002c3c4  add     rdx, rax
0x18002c3c7  test    rdx, rdx
0x18002c3ca  jg      short loc_18002C39E
0x18002c3cc  lea     rbx, [r12+10h]
0x18002c3d1  shl     rcx, 4
0x18002c3d5  sub     rcx, rbx
0x18002c3d8  add     rcx, r8
0x18002c3db  sar     rcx, 4
0x18002c3df  test    rcx, rcx
0x18002c3e2  jle     loc_18002C334
0x18002c3e8  mov     r8, [rsp+120h+var_D8]
0x18002c3ed  mov     rdx, rcx
0x18002c3f0  shr     rdx, 1
0x18002c3f3  mov     r9, rdx
0x18002c3f6  add     r9, r9
0x18002c3f9  cmp     [rbx+r9*8], rdi
0x18002c3fd  jb      short loc_18002C40A
0x18002c3ff  cmp     [rbx+r9*8], r8
0x18002c403  jb      short loc_18002C40A
0x18002c405  mov     rcx, rdx
0x18002c408  jmp     short loc_18002C41C
0x18002c40a  lea     rbx, [rbx+r9*8]
0x18002c40e  add     rbx, 10h
0x18002c412  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c416  sub     rax, rdx
0x18002c419  add     rcx, rax
0x18002c41c  test    rcx, rcx
0x18002c41f  jg      short loc_18002C3ED
0x18002c421  jmp     loc_18002C334
0x18002c426  mov     r8, r14
0x18002c429  lea     rcx, [rbp+3Fh+var_88]
0x18002c42d  call    ??$_Emplace_reallocate@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@?$vector@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@AEAAPEATRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@QEAT234567@$$QEAT234567@@Z; std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint * const,Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint &&)
0x18002c432  mov     rdx, qword ptr [rbp+3Fh+var_88+8]
0x18002c436  add     r14, 10h
0x18002c43a  cmp     r14, rbx
0x18002c43d  jnz     loc_18002C372
0x18002c443  mov     rax, [r13+150h]
0x18002c44a  mov     [rsp+120h+var_D8], rax
0x18002c44f  cmp     rax, rbx
0x18002c452  jz      short loc_18002C4AC
0x18002c454  mov     r14, [r13+158h]
0x18002c45b  sub     r14, rbx
0x18002c45e  mov     r8, r14; Size
0x18002c461  mov     rdx, rbx; Src
0x18002c464  mov     rcx, rax; void *
0x18002c467  call    cs:__imp_memmove
0x18002c46d  mov     rax, [rsp+120h+var_D8]
0x18002c472  add     rax, r14
0x18002c475  mov     [r13+158h], rax
0x18002c47c  jmp     short loc_18002C4AC
0x18002c47e  mov     rax, [rbp+3Fh+Block+8]
0x18002c482  cmp     rax, [rbp+3Fh+var_98]
0x18002c486  jz      short loc_18002C498
0x18002c488  movups  xmm0, xmmword ptr [r12]
0x18002c48d  movdqu  xmmword ptr [rax], xmm0
0x18002c491  add     [rbp+3Fh+Block+8], 10h
0x18002c496  jmp     short loc_18002C4A8
0x18002c498  mov     r8, r12
0x18002c49b  mov     rdx, [rbp+3Fh+Block+8]
0x18002c49f  lea     rcx, [rbp+3Fh+Block]
0x18002c4a3  call    ??$_Emplace_reallocate@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@?$vector@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@AEAAPEATRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@QEAT234567@$$QEAT234567@@Z; std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint * const,Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint &&)
0x18002c4a8  add     r12, 10h
0x18002c4ac  cmp     r12, rdi
0x18002c4af  jnz     short loc_18002C47E
0x18002c4b1  mov     r14, [r13+168h]
0x18002c4b8  cmp     r14, rdi
0x18002c4bb  jz      short loc_18002C4E1
0x18002c4bd  mov     rbx, [r13+170h]
0x18002c4c4  sub     rbx, rdi
0x18002c4c7  mov     r8, rbx; Size
0x18002c4ca  mov     rdx, rdi; Src
0x18002c4cd  mov     rcx, r14; void *
0x18002c4d0  call    cs:__imp_memmove
0x18002c4d6  lea     rax, [rbx+r14]
0x18002c4da  mov     [r13+170h], rax
0x18002c4e1  mov     r12, [rsp+120h+var_E0]
0x18002c4e6  mov     r14, [rsp+120h+var_E8]
0x18002c4eb  mov     rcx, [rbp+3Fh+Block]
0x18002c4ef  mov     rax, [rbp+3Fh+Block+8]
0x18002c4f3  cmp     rcx, rax
0x18002c4f6  jz      short loc_18002C50D
0x18002c4f8  sub     rax, rcx
0x18002c4fb  and     rax, 0FFFFFFFFFFFFFFF0h
0x18002c4ff  movups  xmm0, xmmword ptr [rax+rcx-10h]
0x18002c504  movdqu  xmmword ptr [r13+180h], xmm0
0x18002c50d  mov     rcx, rsi; lpCriticalSection
0x18002c510  call    cs:__imp_LeaveCriticalSection
0x18002c516  mov     rax, qword ptr [rbp+3Fh+var_88+8]
0x18002c51a  cmp     qword ptr [rbp+3Fh+var_88], rax
0x18002c51e  jnz     short loc_18002C562
0x18002c520  lea     rcx, [rbp+3Fh+Block]
0x18002c524  call    ??1?$vector@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::~vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(void)
0x18002c529  nop
0x18002c52a  lea     rcx, [rbp+3Fh+var_88]
0x18002c52e  call    ??1?$vector@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::~vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(void)
0x18002c533  nop
0x18002c534  mov     rcx, [r14+38h]
0x18002c538  test    rcx, rcx
0x18002c53b  jz      short loc_18002C558
0x18002c53d  cmp     rcx, r14
0x18002c540  setnz   dl
0x18002c543  mov     r8, [rcx]
0x18002c546  mov     rax, [r8+20h]
0x18002c54a  call    cs:__guard_dispatch_icall_fptr
0x18002c550  mov     qword ptr [r14+38h], 0
0x18002c558  mov     eax, 1
0x18002c55d  jmp     loc_18002CB49
0x18002c562  xor     edx, edx
0x18002c564  lea     eax, [rdx+64h]
0x18002c567  div     dword ptr [rsp+120h+var_F0]
0x18002c56b  mov     edi, eax
0x18002c56d  mov     dword ptr [rsp+120h+var_F0], edi
0x18002c571  xor     eax, eax
0x18002c573  xorps   xmm1, xmm1
0x18002c576  movdqu  [rbp+3Fh+var_70], xmm1
0x18002c57b  mov     [rbp+3Fh+var_60], rax
0x18002c57f  cmp     edi, 1
0x18002c582  jbe     short loc_18002C596
0x18002c584  mov     edx, edi
0x18002c586  test    edi, edi
  ... truncated ...
```
