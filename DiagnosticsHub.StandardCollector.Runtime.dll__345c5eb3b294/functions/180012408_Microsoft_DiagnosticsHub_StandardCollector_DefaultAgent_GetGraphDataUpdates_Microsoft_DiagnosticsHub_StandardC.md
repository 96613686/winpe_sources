# Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::GetGraphDataUpdates(Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters &,ushort * const,ulong *,CollectorGraphPoint * * const)

- ea: `0x180012408`
- end: `0x180012be0`
- name: `?GetGraphDataUpdates@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAVProcessCounters@234@QEAGPEAKQEAPEAUCollectorGraphPoint@@@Z`
- size: `2008`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *this, struct Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters *, unsigned __int16 *const, unsigned int *, struct CollectorGraphPoint **const)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180011dd0`
- `0x180011e80`

## callees

- `0x180012408`
- `0x180012be0`
- `0x1800132a4`
- `0x1800134f0`
- `0x18001513c`
- `0x180015250`
- `0x18001c7a0`
- `0x1800293a8`
- `0x18002c000`
- `0x180049b50`
- `0x18004a03c`
- `0x18004a078`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x180012530`
- `VCRUNTIME140!memcpy` at `0x180012530`
- `VCRUNTIME140!memset` at `0x180012538`
- `VCRUNTIME140!memset` at `0x180012aaa`
- `VCRUNTIME140!memset` at `0x180012538`
- `VCRUNTIME140!memset` at `0x180012aaa`
- `KERNEL32!CompareStringOrdinal` at `0x180012493`
- `KERNEL32!CompareStringOrdinal` at `0x1800125ca`
- `KERNEL32!CompareStringOrdinal` at `0x1800125f3`
- `KERNEL32!CompareStringOrdinal` at `0x180012616`
- `KERNEL32!CompareStringOrdinal` at `0x180012493`
- `KERNEL32!CompareStringOrdinal` at `0x1800125ca`
- `KERNEL32!CompareStringOrdinal` at `0x1800125f3`
- `KERNEL32!CompareStringOrdinal` at `0x180012616`
- `KERNEL32!LeaveCriticalSection` at `0x1800124d2`
- `KERNEL32!LeaveCriticalSection` at `0x180012590`
- `KERNEL32!LeaveCriticalSection` at `0x180012693`
- `KERNEL32!LeaveCriticalSection` at `0x1800128b3`
- `KERNEL32!LeaveCriticalSection` at `0x1800124d2`
- `KERNEL32!LeaveCriticalSection` at `0x180012590`
- `KERNEL32!LeaveCriticalSection` at `0x180012693`
- `KERNEL32!LeaveCriticalSection` at `0x1800128b3`
- `KERNEL32!EnterCriticalSection` at `0x1800124b2`
- `KERNEL32!EnterCriticalSection` at `0x180012652`
- `KERNEL32!EnterCriticalSection` at `0x18001284c`
- `KERNEL32!EnterCriticalSection` at `0x1800124b2`
- `KERNEL32!EnterCriticalSection` at `0x180012652`
- `KERNEL32!EnterCriticalSection` at `0x18001284c`
- `ole32!CoTaskMemAlloc` at `0x18001250b`
- `ole32!CoTaskMemAlloc` at `0x180012a8b`
- `ole32!CoTaskMemAlloc` at `0x18001250b`
- `ole32!CoTaskMemAlloc` at `0x180012a8b`
- `ole32!CoTaskMemFree` at `0x180012579`
- `ole32!CoTaskMemFree` at `0x180012587`
- `ole32!CoTaskMemFree` at `0x1800126fb`
- `ole32!CoTaskMemFree` at `0x1800128e7`
- `ole32!CoTaskMemFree` at `0x18001293a`
- `ole32!CoTaskMemFree` at `0x1800129fa`
- `ole32!CoTaskMemFree` at `0x180012a31`
- `ole32!CoTaskMemFree` at `0x180012a47`
- `ole32!CoTaskMemFree` at `0x180012ba9`
- `ole32!CoTaskMemFree` at `0x180012579`
- `ole32!CoTaskMemFree` at `0x180012587`
- `ole32!CoTaskMemFree` at `0x1800126fb`
- `ole32!CoTaskMemFree` at `0x1800128e7`
- `ole32!CoTaskMemFree` at `0x18001293a`
- `ole32!CoTaskMemFree` at `0x1800129fa`
- `ole32!CoTaskMemFree` at `0x180012a31`
- `ole32!CoTaskMemFree` at `0x180012a47`
- `ole32!CoTaskMemFree` at `0x180012ba9`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18001253e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18001253e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18001254a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18001254a`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::GetGraphDataUpdates(
        Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *this,
        struct Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters *a2,
        unsigned __int16 *const a3,
        unsigned int *a4,
        struct CollectorGraphPoint **const a5)
{
  unsigned int v9; // esi
  __int64 v10; // r13
  void *v11; // rbx
  size_t v12; // r15
  void *v13; // rax
  const void *v14; // rdx
  __int64 v15; // rax
  unsigned int v17; // r13d
  char *v18; // rbx
  _QWORD *v19; // rax
  _QWORD **v20; // r13
  int CPUGraphPointsForRangeWithoutDebugOverhead; // r15d
  __int64 v22; // rdx
  _QWORD *v23; // rcx
  unsigned __int64 v24; // r15
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rcx
  _QWORD *v28; // rcx
  _QWORD *v29; // rdi
  _QWORD *v30; // rcx
  _QWORD *v31; // rbx
  __int64 v32; // rdi
  int v33; // ecx
  char *v34; // rdi
  __int64 v35; // rax
  unsigned int v36; // eax
  size_t v37; // r15
  unsigned int v38; // r12d
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // xmm0_8
  __int64 v43; // rax
  struct CollectorGraphPoint *v44; // rax
  char v45; // [rsp+30h] [rbp-D0h] BYREF
  char v46; // [rsp+31h] [rbp-CFh]
  unsigned int *v47; // [rsp+38h] [rbp-C8h]
  _BYTE *v48; // [rsp+40h] [rbp-C0h] BYREF
  char *v49; // [rsp+48h] [rbp-B8h] BYREF
  char *v50; // [rsp+50h] [rbp-B0h]
  unsigned int *v51; // [rsp+58h] [rbp-A8h]
  struct CollectorGraphPoint **v52; // [rsp+60h] [rbp-A0h]
  _QWORD v53[7]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v54; // [rsp+A0h] [rbp-60h]
  __int64 v55; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v56; // [rsp+B0h] [rbp-50h]
  char v57[16]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 *v58; // [rsp+C8h] [rbp-38h]
  _BYTE v59[56]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v60; // [rsp+108h] [rbp+8h]
  unsigned __int64 v61; // [rsp+110h] [rbp+10h] BYREF
  __int128 v62; // [rsp+118h] [rbp+18h] BYREF
  __int64 v63; // [rsp+128h] [rbp+28h]
  __int128 v64; // [rsp+130h] [rbp+30h] BYREF
  __int64 v65; // [rsp+140h] [rbp+40h]
  __int64 v66; // [rsp+148h] [rbp+48h]
  __int64 v67; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v68; // [rsp+158h] [rbp+58h]
  _BYTE v69[16]; // [rsp+160h] [rbp+60h] BYREF
  __int128 *v70; // [rsp+170h] [rbp+70h]
  _BYTE v71[56]; // [rsp+178h] [rbp+78h] BYREF
  __int64 (__fastcall ***v72)(_QWORD, _BYTE *); // [rsp+1B0h] [rbp+B0h]

  v51 = a4;
  v47 = (unsigned int *)a2;
  v52 = a5;
  v9 = 0;
  if ( !a3 || !a4 || !a5 )
    return 2147500035LL;
  *a4 = 0;
  *a5 = 0;
  if ( CompareStringOrdinal(a3, -1, L"DiagnosticsHub.Counters.UserMarks", -1, 0) == 2 )
  {
    *a4 = 0;
    *a5 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
    v10 = (__int64)(*((_QWORD *)this + 37) - *((_QWORD *)this + 36)) >> 5;
    if ( (_DWORD)v10 )
    {
      v11 = 0;
      if ( 0xFFFFFFFFFFFFFFFFuLL / (unsigned int)v10 < 0x20
        || (v12 = 32LL * (unsigned int)v10, v12 > 0x7FFFFFFF)
        || (v13 = CoTaskMemAlloc((unsigned int)v12), (v11 = v13) == 0) )
      {
        CoTaskMemFree(v11);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
        return (unsigned int)-2147024882;
      }
      v14 = (const void *)*((_QWORD *)this + 36);
      if ( v12 )
      {
        if ( v14 )
        {
          memcpy(v13, v14, v12);
        }
        else
        {
          memset(v13, 0, v12);
          *_errno() = 22;
          _invalid_parameter_noinfo();
        }
      }
      *v52 = (struct CollectorGraphPoint *)v11;
      *v51 = v10;
      v15 = *((_QWORD *)this + 36);
      if ( v15 != *((_QWORD *)this + 37) )
        *((_QWORD *)this + 37) = v15;
      CoTaskMemFree(0);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
    return v9;
  }
  if ( *((_QWORD *)this + 22) != *((_QWORD *)this + 23) )
  {
    if ( CompareStringOrdinal(a3, -1, L"DiagnosticsHub.Counters.Process.PrivateBytes", -1, 0) == 2 )
    {
      v17 = 1;
      goto LABEL_26;
    }
    if ( CompareStringOrdinal(a3, -1, L"DiagnosticsHub.Counters.Process.CPU", -1, 0) == 2 )
    {
      v17 = 2;
      goto LABEL_26;
    }
    if ( CompareStringOrdinal(a3, -1, L"DiagnosticsHub.Counters.Process.Time", -1, 0) == 2 )
    {
      v17 = 3;
LABEL_26:
      v18 = 0;
      v49 = 0;
      if ( v17 == 3 )
      {
        v62 = 0;
        v50 = (char *)a2 + 472;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 472));
        v19 = operator new(0x20u);
        *v19 = v19;
        v19[1] = v19;
        v20 = (_QWORD **)*((_QWORD *)a2 + 64);
        *(_QWORD *)&v62 = v20;
        *((_QWORD *)a2 + 64) = v19;
        *((_QWORD *)&v62 + 1) = *((_QWORD *)a2 + 65);
        *((_QWORD *)a2 + 65) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 472));
        CPUGraphPointsForRangeWithoutDebugOverhead = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 11) + 64LL))(
                                                       *((_QWORD *)this + 11),
                                                       &v61);
        if ( CPUGraphPointsForRangeWithoutDebugOverhead < 0 )
        {
LABEL_47:
          *v20[1] = 0;
          v28 = *v20;
          if ( *v20 )
          {
            do
            {
              v29 = (_QWORD *)*v28;
              operator delete(v28);
              v28 = v29;
            }
            while ( v29 );
          }
          operator delete(v20);
          goto LABEL_77;
        }
        v64 = 0;
        v50 = 0;
        if ( *((_BYTE *)this + 281) )
        {
          Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::GetDebugOverheadEvents(
            this,
            *v47,
            *((_QWORD *)this + 10),
            v61,
            (struct DebugOverheadEvents *)&v64);
          if ( (_DWORD)v64 )
          {
            v18 = (char *)*((_QWORD *)&v64 + 1);
            CoTaskMemFree(0);
            v50 = v18;
          }
        }
        v53[0] = &std::_Func_impl_no_alloc<_lambda_65a840783244d8bd5f61d57cbc463176_,bool,unsigned __int64>::`vftable';
        v53[1] = this;
        v54 = v53;
        v47 = (unsigned int *)v53;
        v67 = *((_QWORD *)this + 10);
        v68 = v61;
        std::list<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DebugEvent>::list<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DebugEvent>(
          v69,
          &v62);
        v70 = &v64;
        v48 = v71;
        v72 = 0;
        v23 = v54;
        if ( v54 )
        {
          v72 = (__int64 (__fastcall ***)(_QWORD, _BYTE *))(*(__int64 (__fastcall **)(_QWORD *, _BYTE *))*v54)(v54, v71);
          v23 = v54;
        }
        if ( v23 )
        {
          LOBYTE(v22) = v23 != v53;
          (*(void (__fastcall **)(_QWORD *, __int64))(*v23 + 32LL))(v23, v22);
          v54 = 0;
        }
        v47 = (unsigned int *)&v55;
        v55 = v67;
        v56 = v68;
        std::list<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DebugEvent>::list<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DebugEvent>(
          v57,
          v69);
        v58 = v70;
        v48 = v59;
        v60 = 0;
        if ( v72 )
          v60 = (**v72)(v72, v59);
        v47 = (unsigned int *)&v55;
        v45 = *((_BYTE *)this + 64);
        v46 = *((_BYTE *)this + 65);
        CPUGraphPointsForRangeWithoutDebugOverhead = Microsoft::DiagnosticsHub::GraphPoints::CreateTimeGraphPoints(
                                                       &v55,
                                                       &v45,
                                                       &v48,
                                                       &v49);
        if ( CPUGraphPointsForRangeWithoutDebugOverhead >= 0 )
        {
          v24 = v56;
          EnterCriticalSection((LPCRITICAL_SECTION)this + 6);
          v25 = *((_QWORD *)this + 29);
          if ( v25 )
          {
            while ( 1 )
            {
              v26 = *((_QWORD *)this + 28);
              v27 = *(_QWORD *)(*((_QWORD *)this + 26) + 8 * (v26 & (*((_QWORD *)this + 27) - 1LL)));
              if ( v24 < *(_QWORD *)(v27 + 8) || !*(_QWORD *)(v27 + 8) )
                break;
              *((_QWORD *)this + 29) = --v25;
              if ( !v25 )
              {
                *((_QWORD *)this + 28) = 0;
                break;
              }
              *((_QWORD *)this + 28) = v26 + 1;
            }
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)this + 6);
          *((_BYTE *)this + 64) = v45;
          *((_BYTE *)this + 65) = v46;
          CPUGraphPointsForRangeWithoutDebugOverhead = 0;
        }
        Microsoft::DiagnosticsHub::GraphPoints::TimeDataPoints::~TimeDataPoints((Microsoft::DiagnosticsHub::GraphPoints::TimeDataPoints *)&v55);
        if ( CPUGraphPointsForRangeWithoutDebugOverhead < 0 )
        {
          Microsoft::DiagnosticsHub::GraphPoints::TimeDataPoints::~TimeDataPoints((Microsoft::DiagnosticsHub::GraphPoints::TimeDataPoints *)&v67);
          CoTaskMemFree(v18);
          v18 = v49;
          goto LABEL_47;
        }
        *((_QWORD *)this + 10) = v61;
        Microsoft::DiagnosticsHub::GraphPoints::TimeDataPoints::~TimeDataPoints((Microsoft::DiagnosticsHub::GraphPoints::TimeDataPoints *)&v67);
        CoTaskMemFree(v18);
        *v20[1] = 0;
        v30 = *v20;
        if ( *v20 )
        {
          do
          {
            v31 = (_QWORD *)*v30;
            operator delete(v30);
            v30 = v31;
          }
          while ( v31 );
        }
        operator delete(v20);
        v18 = v49;
        LODWORD(v32) = (_DWORD)v48;
        goto LABEL_71;
      }
      v62 = 0;
      v63 = 0;
      if ( v17 == 2 && *((_BYTE *)this + 281) )
      {
        CPUGraphPointsForRangeWithoutDebugOverhead = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 11) + 64LL))(
                                                       *((_QWORD *)this + 11),
                                                       &v61);
        if ( CPUGraphPointsForRangeWithoutDebugOverhead < 0 )
          goto LABEL_76;
        v64 = 0;
        Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::GetDebugOverheadEvents(
          this,
          *v47,
          *((_QWORD *)this + 9),
          v61,
          (struct DebugOverheadEvents *)&v64);
        v34 = 0;
        v50 = 0;
        if ( (_DWORD)v64 )
        {
          v34 = (char *)*((_QWORD *)&v64 + 1);
          CoTaskMemFree(0);
          v50 = v34;
        }
        CPUGraphPointsForRangeWithoutDebugOverhead = Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::CreateCPUGraphPointsForRangeWithoutDebugOverhead(
                                                       v33,
                                                       *((_QWORD *)this + 9),
                                                       v61,
                                                       (_DWORD)v47,
                                                       (__int64)&v64,
                                                       (__int64)&v62);
        if ( CPUGraphPointsForRangeWithoutDebugOverhead < 0 )
        {
          CoTaskMemFree(v34);
          goto LABEL_76;
        }
        *((_QWORD *)this + 9) = v61;
        CoTaskMemFree(v34);
      }
      else
      {
        CPUGraphPointsForRangeWithoutDebugOverhead = Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::GetPerformanceCounterValue(
                                                       a2,
                                                       v17,
                                                       &v62);
        if ( CPUGraphPointsForRangeWithoutDebugOverhead < 0 )
          goto LABEL_76;
      }
      v35 = (__int64)(*((_QWORD *)&v62 + 1) - v62) >> 4;
      v32 = (unsigned int)v35;
      if ( (_DWORD)v35 )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / (unsigned int)v35 < 0x20 )
          goto LABEL_75;
        v36 = 32 * v35;
        v37 = 32 * v32;
        if ( (unsigned __int64)(32 * v32) > 0x7FFFFFFF )
        {
          v18 = 0;
LABEL_65:
          v49 = v18;
          if ( v18 )
          {
            memset(v18, 0, v37);
            v38 = 0;
            if ( !(_DWORD)v32 )
            {
LABEL_70:
              std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::~vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(&v62);
LABEL_71:
              *v51 = v32;
              v44 = (struct CollectorGraphPoint *)v18;
              v18 = 0;
              *v52 = v44;
              CPUGraphPointsForRangeWithoutDebugOverhead = 0;
LABEL_77:
              CoTaskMemFree(v18);
              return (unsigned int)CPUGraphPointsForRangeWithoutDebugOverhead;
            }
            while ( 1 )
            {
              v39 = v62;
              v40 = 32LL * v38;
              *(_QWORD *)&v18[v40] = *(_QWORD *)(v62 + 16LL * v38);
              *(_QWORD *)&v18[v40 + 8] = *(_QWORD *)(v39 + 16LL * v38 + 8);
              v41 = *((_QWORD *)this + 12);
              v42 = *(_QWORD *)(v39 + 16LL * v38 + 8);
              v43 = *(_QWORD *)(v39 + 16LL * v38);
              *(_QWORD *)&v64 = &Microsoft::DiagnosticsHub::StandardCollector::CounterInfoEvent::`vftable';
              DWORD2(v64) = v17;
              v65 = v43;
              v66 = v42;
              CPUGraphPointsForRangeWithoutDebugOverhead = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::InjectArtificialEvent(
                                                             (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)((v41 - 1024) & -(__int64)(v41 != 0)),
                                                             (const struct Microsoft::DiagnosticsHub::StandardCollector::ArtificialEvent *)&v64);
              if ( (int)(CPUGraphPointsForRangeWithoutDebugOverhead + 0x80000000) >= 0
                && CPUGraphPointsForRangeWithoutDebugOverhead != -2147024891 )
              {
                break;
              }
              if ( ++v38 >= (unsigned int)v32 )
                goto LABEL_70;
            }
LABEL_76:
            std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::~vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(&v62);
            goto LABEL_77;
          }
LABEL_75:
          CPUGraphPointsForRangeWithoutDebugOverhead = -2147024882;
          goto LABEL_76;
        }
      }
      else
      {
        v36 = 0;
        v37 = 32LL * (unsigned int)v32;
      }
      v18 = (char *)CoTaskMemAlloc(v36);
      goto LABEL_65;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180012408  push    rbp
0x18001240a  push    rbx
0x18001240b  push    rsi
0x18001240c  push    rdi
0x18001240d  push    r12
0x18001240f  push    r13
0x180012411  push    r14
0x180012413  push    r15
0x180012415  lea     rbp, [rsp-0D8h]
0x18001241d  sub     rsp, 1D8h
0x180012424  mov     rax, cs:__security_cookie
0x18001242b  xor     rax, rsp
0x18001242e  mov     [rbp+110h+var_50], rax
0x180012435  mov     rdi, r9
0x180012438  mov     [rsp+210h+var_1B8], r9
0x18001243d  mov     rbx, r8
0x180012440  mov     r15, rdx
0x180012443  mov     [rsp+210h+var_1D8], rdx
0x180012448  mov     r14, rcx
0x18001244b  mov     r12, [rbp+110h+arg_20]
0x180012452  mov     [rsp+210h+var_1B0], r12
0x180012457  xor     esi, esi
0x180012459  test    r8, r8
0x18001245c  jz      loc_180012BB8
0x180012462  test    r9, r9
0x180012465  jz      loc_180012BB8
0x18001246b  test    r12, r12
0x18001246e  jz      loc_180012BB8
0x180012474  mov     [r9], esi
0x180012477  mov     [r12], rsi
0x18001247b  mov     [rsp+210h+bIgnoreCase], esi; bIgnoreCase
0x18001247f  or      r13, 0FFFFFFFFFFFFFFFFh
0x180012483  mov     r9d, r13d; cchCount2
0x180012486  lea     r8, aDiagnosticshub_8; "DiagnosticsHub.Counters.UserMarks"
0x18001248d  mov     edx, r13d; cchCount1
0x180012490  mov     rcx, rbx; lpString1
0x180012493  call    cs:__imp_CompareStringOrdinal
0x180012499  cmp     eax, 2
0x18001249c  jnz     loc_1800125A2
0x1800124a2  mov     [rdi], esi
0x1800124a4  mov     [r12], rsi
0x1800124a8  lea     rdi, [r14+138h]
0x1800124af  mov     rcx, rdi; lpCriticalSection
0x1800124b2  call    cs:__imp_EnterCriticalSection
0x1800124b8  mov     r13, [r14+128h]
0x1800124bf  sub     r13, [r14+120h]
0x1800124c6  sar     r13, 5
0x1800124ca  test    r13d, r13d
0x1800124cd  jnz     short loc_1800124DD
0x1800124cf  mov     rcx, rdi; lpCriticalSection
0x1800124d2  call    cs:__imp_LeaveCriticalSection
0x1800124d8  jmp     loc_18001259B
0x1800124dd  mov     rbx, rsi
0x1800124e0  mov     r15d, r13d
0x1800124e3  xor     edx, edx
0x1800124e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800124e9  div     r15
0x1800124ec  mov     r12d, 20h ; ' '
0x1800124f2  cmp     rax, r12
0x1800124f5  jb      loc_180012584
0x1800124fb  shl     r15, 5
0x1800124ff  cmp     r15, 7FFFFFFFh
0x180012506  ja      short loc_180012584
0x180012508  mov     ecx, r15d; cb
0x18001250b  call    cs:__imp_CoTaskMemAlloc
0x180012511  mov     rbx, rax
0x180012514  test    rax, rax
0x180012517  jz      short loc_180012584
0x180012519  mov     rdx, [r14+120h]; Val
0x180012520  test    r15, r15
0x180012523  jz      short loc_180012550
0x180012525  mov     r8, r15; Size
0x180012528  mov     rcx, rax; void *
0x18001252b  test    rdx, rdx
0x18001252e  jz      short loc_180012538
0x180012530  call    cs:__imp_memcpy
0x180012536  jmp     short loc_180012550
0x180012538  call    cs:__imp_memset
0x18001253e  call    cs:__imp__errno
0x180012544  mov     dword ptr [rax], 16h
0x18001254a  call    cs:__imp__invalid_parameter_noinfo
0x180012550  mov     rcx, [rsp+210h+var_1B0]
0x180012555  mov     [rcx], rbx
0x180012558  mov     rax, [rsp+210h+var_1B8]
0x18001255d  mov     [rax], r13d
0x180012560  mov     rax, [r14+120h]
0x180012567  cmp     rax, [r14+128h]
0x18001256e  jz      short loc_180012577
0x180012570  mov     [r14+128h], rax
0x180012577  xor     ecx, ecx; pv
0x180012579  call    cs:__imp_CoTaskMemFree
0x18001257f  jmp     loc_1800124CF
0x180012584  mov     rcx, rbx; pv
0x180012587  call    cs:__imp_CoTaskMemFree
0x18001258d  mov     rcx, rdi; lpCriticalSection
0x180012590  call    cs:__imp_LeaveCriticalSection
0x180012596  mov     esi, 8007000Eh
0x18001259b  mov     eax, esi
0x18001259d  jmp     loc_180012BBD
0x1800125a2  mov     rax, [r14+0B8h]
0x1800125a9  cmp     [r14+0B0h], rax
0x1800125b0  jz      loc_180012BB4
0x1800125b6  mov     [rsp+210h+bIgnoreCase], esi; bIgnoreCase
0x1800125ba  mov     r9d, r13d; cchCount2
0x1800125bd  lea     r8, aDiagnosticshub_9; "DiagnosticsHub.Counters.Process.Private"...
0x1800125c4  mov     edx, r13d; cchCount1
0x1800125c7  mov     rcx, rbx; lpString1
0x1800125ca  call    cs:__imp_CompareStringOrdinal
0x1800125d0  mov     edi, 2
0x1800125d5  cmp     eax, edi
0x1800125d7  jnz     short loc_1800125DF
0x1800125d9  lea     r13d, [rdi-1]
0x1800125dd  jmp     short loc_18001262A
0x1800125df  mov     [rsp+210h+bIgnoreCase], esi; bIgnoreCase
0x1800125e3  mov     r9d, r13d; cchCount2
0x1800125e6  lea     r8, aDiagnosticshub_10; "DiagnosticsHub.Counters.Process.CPU"
0x1800125ed  mov     edx, r13d; cchCount1
0x1800125f0  mov     rcx, rbx; lpString1
0x1800125f3  call    cs:__imp_CompareStringOrdinal
0x1800125f9  cmp     eax, edi
0x1800125fb  jnz     short loc_180012602
0x1800125fd  mov     r13d, edi
0x180012600  jmp     short loc_18001262A
0x180012602  mov     [rsp+210h+bIgnoreCase], esi; bIgnoreCase
0x180012606  mov     r9d, r13d; cchCount2
0x180012609  lea     r8, aDiagnosticshub_11; "DiagnosticsHub.Counters.Process.Time"
0x180012610  mov     edx, r13d; cchCount1
0x180012613  mov     rcx, rbx; lpString1
0x180012616  call    cs:__imp_CompareStringOrdinal
0x18001261c  cmp     eax, edi
0x18001261e  jnz     loc_180012BB4
0x180012624  mov     r13d, 3
0x18001262a  mov     rbx, rsi
0x18001262d  mov     [rsp+210h+var_1C8], rbx
0x180012632  cmp     r13d, 3
0x180012636  jnz     loc_18001297D
0x18001263c  xorps   xmm0, xmm0
0x18001263f  movups  [rbp+110h+var_F8], xmm0
0x180012643  lea     rdi, [r15+1D8h]
0x18001264a  mov     [rsp+210h+var_1C0], rdi
0x18001264f  mov     rcx, rdi; lpCriticalSection
0x180012652  call    cs:__imp_EnterCriticalSection
0x180012658  nop
0x180012659  lea     r12d, [r13+1Dh]
0x18001265d  mov     ecx, r12d; Size
0x180012660  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012665  mov     [rax], rax
0x180012668  mov     [rax+8], rax
0x18001266c  mov     r13, [r15+200h]
0x180012673  mov     qword ptr [rbp+110h+var_F8], r13
0x180012677  mov     [r15+200h], rax
0x18001267e  mov     rax, [r15+208h]
0x180012685  mov     qword ptr [rbp+110h+var_F8+8], rax
0x180012689  mov     [r15+208h], rsi
0x180012690  mov     rcx, rdi; lpCriticalSection
0x180012693  call    cs:__imp_LeaveCriticalSection
0x180012699  nop
0x18001269a  mov     rcx, [r14+58h]
0x18001269e  mov     rax, [rcx]
0x1800126a1  lea     rdx, [rbp+110h+var_100]
0x1800126a5  mov     rax, [rax+40h]
0x1800126a9  call    cs:__guard_dispatch_icall_fptr
0x1800126af  mov     r15d, eax
0x1800126b2  test    eax, eax
0x1800126b4  js      loc_1800128F2
0x1800126ba  xorps   xmm0, xmm0
0x1800126bd  movups  [rbp+110h+var_E0], xmm0
0x1800126c1  mov     [rsp+210h+var_1C0], rbx
0x1800126c6  cmp     [r14+119h], sil
0x1800126cd  jz      short loc_180012706
0x1800126cf  lea     rax, [rbp+110h+var_E0]
0x1800126d3  mov     qword ptr [rsp+210h+bIgnoreCase], rax; struct DebugOverheadEvents *
0x1800126d8  mov     r9, [rbp+110h+var_100]; unsigned __int64
0x1800126dc  mov     r8, [r14+50h]; unsigned __int64
0x1800126e0  mov     r15, [rsp+210h+var_1D8]
0x1800126e5  mov     edx, [r15]; unsigned int
0x1800126e8  mov     rcx, r14; this
0x1800126eb  call    ?GetDebugOverheadEvents@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAXI_K0AEAUDebugOverheadEvents@@@Z; Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::GetDebugOverheadEvents(uint,unsigned __int64,unsigned __int64,DebugOverheadEvents &)
0x1800126f0  cmp     dword ptr [rbp+110h+var_E0], esi
0x1800126f3  jbe     short loc_180012706
0x1800126f5  mov     rbx, qword ptr [rbp+110h+var_E0+8]
0x1800126f9  xor     ecx, ecx; pv
0x1800126fb  call    cs:__imp_CoTaskMemFree
0x180012701  mov     [rsp+210h+var_1C0], rbx
0x180012706  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_65a840783244d8bd5f61d57cbc463176_@@_N_K@std@@6B@; const std::_Func_impl_no_alloc<_lambda_65a840783244d8bd5f61d57cbc463176_,bool,unsigned __int64>::`vftable'
0x18001270d  mov     [rsp+210h+var_1A8], rax
0x180012712  mov     [rsp+210h+var_1A0], r14
0x180012717  lea     rax, [rsp+210h+var_1A8]
0x18001271c  mov     [rbp+110h+var_170], rax
0x180012720  lea     rax, [rsp+210h+var_1A8]
0x180012725  mov     [rsp+210h+var_1D8], rax
0x18001272a  mov     rax, [r14+50h]
0x18001272e  mov     [rbp+110h+var_C0], rax
0x180012732  mov     rax, [rbp+110h+var_100]
0x180012736  mov     [rbp+110h+var_B8], rax
0x18001273a  lea     rdx, [rbp+110h+var_F8]
0x18001273e  lea     rcx, [rbp+110h+var_B0]
0x180012742  call    ??0?$list@UDebugEvent@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UDebugEvent@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@QEAA@AEBV01@@Z; std::list<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DebugEvent>::list<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DebugEvent>(std::list<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DebugEvent> const &)
0x180012747  nop
0x180012748  lea     rax, [rbp+110h+var_E0]
0x18001274c  mov     [rbp+110h+var_A0], rax
0x180012750  lea     rax, [rbp+110h+var_98]
0x180012754  mov     [rsp+210h+var_1D0], rax
0x180012759  mov     [rbp+110h+var_60], rsi
0x180012760  mov     rcx, [rbp+110h+var_170]
0x180012764  test    rcx, rcx
0x180012767  jz      short loc_180012784
0x180012769  mov     rax, [rcx]
0x18001276c  lea     rdx, [rbp+110h+var_98]
0x180012770  mov     rax, [rax]
0x180012773  call    cs:__guard_dispatch_icall_fptr
0x180012779  mov     [rbp+110h+var_60], rax
0x180012780  mov     rcx, [rbp+110h+var_170]
0x180012784  test    rcx, rcx
0x180012787  jz      short loc_1800127A5
0x180012789  lea     rax, [rsp+210h+var_1A8]
0x18001278e  cmp     rcx, rax
0x180012791  setnz   dl
0x180012794  mov     rax, [rcx]
0x180012797  mov     rax, [rax+20h]
0x18001279b  call    cs:__guard_dispatch_icall_fptr
0x1800127a1  mov     [rbp+110h+var_170], rsi
0x1800127a5  lea     rax, [rbp+110h+var_168]
0x1800127a9  mov     [rsp+210h+var_1D8], rax
0x1800127ae  mov     rax, [rbp+110h+var_C0]
0x1800127b2  mov     [rbp+110h+var_168], rax
0x1800127b6  mov     rax, [rbp+110h+var_B8]
0x1800127ba  mov     [rbp+110h+var_160], rax
0x1800127be  lea     rdx, [rbp+110h+var_B0]
0x1800127c2  lea     rcx, [rbp+110h+var_158]
0x1800127c6  call    ??0?$list@UDebugEvent@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UDebugEvent@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@QEAA@AEBV01@@Z; std::list<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DebugEvent>::list<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DebugEvent>(std::list<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DebugEvent> const &)
0x1800127cb  nop
0x1800127cc  mov     rax, [rbp+110h+var_A0]
0x1800127d0  mov     [rbp+110h+var_148], rax
0x1800127d4  lea     rax, [rbp+110h+var_140]
0x1800127d8  mov     [rsp+210h+var_1D0], rax
0x1800127dd  mov     [rbp+110h+var_108], rsi
0x1800127e1  mov     rcx, [rbp+110h+var_60]
0x1800127e8  test    rcx, rcx
0x1800127eb  jz      short loc_180012801
0x1800127ed  mov     rax, [rcx]
0x1800127f0  lea     rdx, [rbp+110h+var_140]
0x1800127f4  mov     rax, [rax]
0x1800127f7  call    cs:__guard_dispatch_icall_fptr
0x1800127fd  mov     [rbp+110h+var_108], rax
0x180012801  lea     rax, [rbp+110h+var_168]
0x180012805  mov     [rsp+210h+var_1D8], rax
0x18001280a  mov     al, [r14+40h]
0x18001280e  mov     [rsp+210h+var_1E0], al
0x180012812  mov     al, [r14+41h]
0x180012816  mov     [rsp+210h+var_1DF], al
0x18001281a  lea     r9, [rsp+210h+var_1C8]
0x18001281f  lea     r8, [rsp+210h+var_1D0]
0x180012824  lea     rdx, [rsp+210h+var_1E0]
0x180012829  lea     rcx, [rbp+110h+var_168]
0x18001282d  call    ?CreateTimeGraphPoints@GraphPoints@DiagnosticsHub@Microsoft@@YAJAEBUTimeDataPoints@123@AEAUCurrentTimeState@123@AEAIAEAV?$CComHeapPtr@UCollectorGraphPoint@@@ATL@@@Z; Microsoft::DiagnosticsHub::GraphPoints::CreateTimeGraphPoints(Microsoft::DiagnosticsHub::GraphPoints::TimeDataPoints const &,Microsoft::DiagnosticsHub::GraphPoints::CurrentTimeState &,uint &,ATL::CComHeapPtr<CollectorGraphPoint> &)
0x180012832  mov     r15d, eax
0x180012835  test    eax, eax
0x180012837  jns     short loc_18001283E
0x180012839  jmp     loc_1800128CC
0x18001283e  mov     r15, [rbp+110h+var_160]
0x180012842  lea     rdi, [r14+0F0h]
0x180012849  mov     rcx, rdi; lpCriticalSection
0x18001284c  call    cs:__imp_EnterCriticalSection
0x180012852  mov     rdx, [r14+0E8h]
0x180012859  test    rdx, rdx
0x18001285c  jz      short loc_1800128B0
0x18001285e  mov     r8, [r14+0E0h]
0x180012865  mov     rcx, [r14+0D8h]
0x18001286c  dec     rcx
0x18001286f  and     rcx, r8
0x180012872  mov     rax, [r14+0D0h]
0x180012879  mov     rcx, [rax+rcx*8]
0x18001287d  cmp     r15, [rcx+8]
0x180012881  jb      short loc_1800128B0
0x180012883  cmp     [rcx+8], rsi
0x180012887  jz      short loc_1800128B0
0x180012889  lea     rax, [rdx-1]
0x18001288d  mov     rdx, rax
0x180012890  mov     [r14+0E8h], rax
0x180012897  test    rax, rax
0x18001289a  jz      short loc_1800128A9
0x18001289c  lea     rax, [r8+1]
0x1800128a0  mov     [r14+0E0h], rax
0x1800128a7  jmp     short loc_18001285E
0x1800128a9  mov     [r14+0E0h], rsi
0x1800128b0  mov     rcx, rdi; lpCriticalSection
0x1800128b3  call    cs:__imp_LeaveCriticalSection
0x1800128b9  mov     al, [rsp+210h+var_1E0]
0x1800128bd  mov     [r14+40h], al
0x1800128c1  mov     al, [rsp+210h+var_1DF]
0x1800128c5  mov     [r14+41h], al
0x1800128c9  mov     r15d, esi
0x1800128cc  lea     rcx, [rbp+110h+var_168]; this
0x1800128d0  call    ??1TimeDataPoints@GraphPoints@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::GraphPoints::TimeDataPoints::~TimeDataPoints(void)
0x1800128d5  test    r15d, r15d
0x1800128d8  jns     short loc_180012925
0x1800128da  lea     rcx, [rbp+110h+var_C0]; this
0x1800128de  call    ??1TimeDataPoints@GraphPoints@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::GraphPoints::TimeDataPoints::~TimeDataPoints(void)
0x1800128e3  nop
  ... truncated ...
```
