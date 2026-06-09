# Windows::WU::Telemetry::WuProvider::ScanService::Stop(SystemInterface::Telemetry::CorrelationVector &,wchar_t const *)

- ea: `0x1402cd844`
- end: `0x1402ce80f`
- name: `?Stop@ScanService@WuProvider@Telemetry@WU@Windows@@QEAAXAEAVCorrelationVector@3SystemInterface@@PEB_W@Z`
- size: `4043`
- prototype: `void __fastcall(Windows::WU::Telemetry::WuProvider::ScanService *__hidden this, struct SystemInterface::Telemetry::CorrelationVector *, const wchar_t *)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, installer_update`

## callers

- `0x1402cf4cc`
- `0x1402d0950`

## callees

- `0x140001f74`
- `0x1400152b8`
- `0x1400156f8`
- `0x140015afc`
- `0x14002a7d8`
- `0x14002b5f0`
- `0x14002cc08`
- `0x140044f20`
- `0x140045404`
- `0x1400574cc`
- `0x14012d7d8`
- `0x1402ca644`
- `0x1402cd844`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402cde9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402ce6ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402cde9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402ce6ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cd8e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cdd14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402ce1e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402ce56f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cd8e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cdd14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402ce1e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402ce56f`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall Windows::WU::Telemetry::WuProvider::ScanService::Stop(
        Windows::WU::Telemetry::WuProvider::ScanService *this,
        struct SystemInterface::Telemetry::CorrelationVector *a2,
        const wchar_t *a3)
{
  char IsEnabled; // al
  char *v7; // r14
  __int64 v8; // rbx
  int v9; // ecx
  int *v10; // rbx
  _DWORD **v11; // rsi
  const struct _tlgProvider_t *v12; // rax
  int v13; // esi
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  _QWORD *v23; // rax
  volatile signed __int32 *v24; // rsi
  volatile signed __int32 *v25; // rsi
  __int64 v26; // rdx
  volatile signed __int32 *v27; // rsi
  volatile signed __int32 *v28; // rsi
  _DWORD *v29; // rax
  int v30; // esi
  const struct _tlgProvider_t *v31; // rax
  _QWORD *v32; // rax
  _QWORD *v33; // rax
  __int64 v34; // rax
  const OLECHAR *v35; // r13
  __int64 v36; // rax
  const CHAR *v37; // r12
  __int64 v38; // rax
  __int64 v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // r15
  __int64 v42; // rax
  const OLECHAR *v43; // r15
  __int64 v44; // r8
  __int64 v45; // rax
  int v46; // eax
  __int64 v47; // rax
  int v48; // eax
  const OLECHAR *v49; // rcx
  __int64 v50; // rax
  int v51; // eax
  __int64 v52; // rsi
  volatile signed __int32 *v53; // rsi
  volatile signed __int32 *v54; // rsi
  __int64 v55; // rdx
  volatile signed __int32 *v56; // rsi
  int *v57; // rbx
  _DWORD **v58; // rsi
  const struct _tlgProvider_t *v59; // rax
  int v60; // esi
  _QWORD *v61; // rax
  __int64 System; // rax
  __int64 v63; // rcx
  _QWORD *v64; // rax
  __int64 v65; // rcx
  __int64 v66; // rax
  _QWORD *v67; // rax
  volatile signed __int32 *v68; // rsi
  volatile signed __int32 *v69; // rsi
  const struct _tlgProvider_t *v70; // rax
  int v71; // ebx
  _QWORD *v72; // rax
  __int64 v73; // rax
  __int64 v74; // rcx
  _QWORD *v75; // rax
  __int64 v76; // rcx
  __int64 v77; // rax
  _QWORD *v78; // rax
  _DWORD *v79; // r8
  volatile signed __int32 *v80; // rsi
  volatile signed __int32 *v81; // rsi
  PSRWLOCK SRWLock; // [rsp+E0h] [rbp-80h] BYREF
  int v83; // [rsp+E8h] [rbp-78h] BYREF
  DWORD CurrentThreadId; // [rsp+ECh] [rbp-74h] BYREF
  __int64 v85; // [rsp+F0h] [rbp-70h] BYREF
  __int64 v86; // [rsp+F8h] [rbp-68h] BYREF
  int v87; // [rsp+100h] [rbp-60h] BYREF
  int v88; // [rsp+104h] [rbp-5Ch] BYREF
  int v89; // [rsp+108h] [rbp-58h] BYREF
  int v90; // [rsp+10Ch] [rbp-54h] BYREF
  __int64 v91; // [rsp+110h] [rbp-50h] BYREF
  __int64 v92; // [rsp+118h] [rbp-48h] BYREF
  __int64 v93; // [rsp+120h] [rbp-40h] BYREF
  __int64 v94; // [rsp+128h] [rbp-38h] BYREF
  __int64 v95; // [rsp+130h] [rbp-30h] BYREF
  __int64 v96; // [rsp+138h] [rbp-28h] BYREF
  __int64 v97; // [rsp+140h] [rbp-20h] BYREF
  __int64 v98; // [rsp+148h] [rbp-18h] BYREF
  __int64 v99; // [rsp+150h] [rbp-10h] BYREF
  __int64 v100; // [rsp+158h] [rbp-8h] BYREF
  __int64 v101; // [rsp+160h] [rbp+0h] BYREF
  __int64 v102; // [rsp+168h] [rbp+8h] BYREF
  __int64 v103; // [rsp+170h] [rbp+10h] BYREF
  __int64 v104; // [rsp+178h] [rbp+18h] BYREF
  _BYTE v105[8]; // [rsp+180h] [rbp+20h] BYREF
  volatile signed __int32 *v106; // [rsp+188h] [rbp+28h]
  _BYTE v107[8]; // [rsp+190h] [rbp+30h] BYREF
  volatile signed __int32 *v108; // [rsp+198h] [rbp+38h]
  __int64 v109; // [rsp+1A0h] [rbp+40h] BYREF
  _BYTE v110[8]; // [rsp+1A8h] [rbp+48h] BYREF
  volatile signed __int32 *v111; // [rsp+1B0h] [rbp+50h]
  _BYTE v112[8]; // [rsp+1B8h] [rbp+58h] BYREF
  volatile signed __int32 *v113; // [rsp+1C0h] [rbp+60h]
  _BYTE v114[44]; // [rsp+1C8h] [rbp+68h] BYREF
  int i; // [rsp+1F4h] [rbp+94h]
  _BYTE v116[32]; // [rsp+200h] [rbp+A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v117; // [rsp+220h] [rbp+C0h] BYREF
  __int64 *v118; // [rsp+240h] [rbp+E0h]
  __int64 v119; // [rsp+248h] [rbp+E8h]
  int *v120; // [rsp+250h] [rbp+F0h]
  __int64 v121; // [rsp+258h] [rbp+F8h]
  DWORD *p_CurrentThreadId; // [rsp+260h] [rbp+100h]
  __int64 v123; // [rsp+268h] [rbp+108h]
  const OLECHAR *v124; // [rsp+270h] [rbp+110h]
  int v125; // [rsp+278h] [rbp+118h]
  int v126; // [rsp+27Ch] [rbp+11Ch]
  const wchar_t *v127; // [rsp+280h] [rbp+120h]
  __int64 v128; // [rsp+288h] [rbp+128h]
  const OLECHAR *v129; // [rsp+290h] [rbp+130h]
  int v130; // [rsp+298h] [rbp+138h]
  int v131; // [rsp+29Ch] [rbp+13Ch]
  PSRWLOCK *p_SRWLock; // [rsp+2A0h] [rbp+140h]
  __int64 v133; // [rsp+2A8h] [rbp+148h]
  __int64 *v134; // [rsp+2B0h] [rbp+150h]
  __int64 v135; // [rsp+2B8h] [rbp+158h]
  const CHAR *v136; // [rsp+2C0h] [rbp+160h]
  int v137; // [rsp+2C8h] [rbp+168h]
  int v138; // [rsp+2CCh] [rbp+16Ch]
  const OLECHAR *v139; // [rsp+2D0h] [rbp+170h]
  int v140; // [rsp+2D8h] [rbp+178h]
  int v141; // [rsp+2DCh] [rbp+17Ch]
  const char *v142; // [rsp+2E0h] [rbp+180h]
  __int64 v143; // [rsp+2E8h] [rbp+188h]

  v91 = (__int64)a3;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl);
  v7 = (char *)this + 272;
  v8 = *((_QWORD *)this + 34);
  v9 = *(_DWORD *)(v8 + 72);
  if ( !IsEnabled )
  {
    if ( v9 < 0 && (v57 = (int *)(v8 + 80), v9 == v57[2]) )
    {
      v58 = (_DWORD **)((char *)this + 272);
      if ( v57 )
      {
        SRWLock = 0;
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
          this,
          &SRWLock);
        **(_DWORD **)v7 = 2;
        if ( SRWLock )
          ReleaseSRWLockExclusive(SRWLock);
        v59 = Windows::WU::Telemetry::WuProvider::Provider();
        v60 = (int)v59;
        if ( *(_DWORD *)v59 <= 5u
          || (*((_QWORD *)v59 + 2) & 0x400000000000LL) == 0
          || (*((_QWORD *)v59 + 3) & 0x400000000000LL) != *((_QWORD *)v59 + 3) )
        {
          goto LABEL_92;
        }
        v92 = (__int64)"1507.2603.28012.0";
        v61 = (_QWORD *)(*(__int64 (__fastcall **)(struct SystemInterface::Telemetry::CorrelationVector *, _BYTE *))(*(_QWORD *)a2 + 8LL))(
                          a2,
                          v114);
        if ( v61[3] > 0xFu )
          v61 = (_QWORD *)*v61;
        v91 = (__int64)v61;
        System = SystemInterface::Providers::GetSystem(v105);
        v63 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
        v64 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v63 + 8LL))(v63, v107);
        v86 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v64 + 104LL))(*v64)
            - (unsigned __int64)*((unsigned int *)this + 88);
        LODWORD(SRWLock) = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 42) + 8LL))(
                                             *((_QWORD *)this + 42),
                                             &v85)
                         / 60000000;
        v85 = (__int64)a3;
        v93 = (__int64)L"[]";
        v65 = qword_140549FC0;
        v66 = *(_QWORD *)(qword_140549FC0 + 8);
        for ( i = 0; !*(_BYTE *)(v66 + 25); v66 = *(_QWORD *)v66 )
        {
          if ( *(_DWORD *)(v66 + 32) >= *((_DWORD *)this + 82) )
            v65 = v66;
          else
            v66 += 16;
        }
        if ( *(_BYTE *)(v65 + 25) || *((_DWORD *)this + 82) < *(_DWORD *)(v65 + 32) )
          std::_Xout_of_range("invalid map<K, T> key");
        v67 = (_QWORD *)(v65 + 64);
        if ( *(_QWORD *)(v65 + 88) > 7u )
          v67 = (_QWORD *)*v67;
        v95 = (__int64)v67;
        v94 = *((_QWORD *)v57 + 15);
        v104 = *((_QWORD *)v57 + 14);
        CurrentThreadId = v57[26];
        v103 = *((_QWORD *)v57 + 12);
        v102 = *((_QWORD *)v57 + 11);
        v83 = v57[20];
        v101 = *((_QWORD *)v57 + 9);
        v90 = v57[8];
        v100 = *((_QWORD *)v57 + 3);
        v89 = *v57;
        v99 = *((_QWORD *)v57 + 16);
        v88 = v57[16];
        v98 = *((_QWORD *)v57 + 7);
        v87 = v57[2];
        v97 = 0x1000000;
        v96 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v60,
          (int)&word_1404A3716,
          *(_DWORD *)v7 + 8,
          (__int64)&v96,
          (__int64)&v97,
          (__int64)&v87,
          (__int64)&v98,
          (__int64)&v88,
          (__int64)&v99,
          (__int64)&v89,
          (__int64)&v100,
          (__int64)&v90,
          (__int64)&v101,
          (__int64)&v83,
          (__int64)&v102,
          (__int64)&v103,
          (__int64)&CurrentThreadId,
          (__int64)&v104,
          (__int64)&v94,
          (__int64)&v95,
          (__int64)&v93,
          (__int64)&v85,
          (__int64)&SRWLock,
          (__int64)&v86,
          (__int64)&v91,
          (__int64)&v92);
        v68 = v108;
        if ( v108 )
        {
          if ( _InterlockedExchangeAdd(v108 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
            if ( _InterlockedExchangeAdd(v68 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
          }
        }
        v69 = v106;
        if ( v106 )
        {
          if ( _InterlockedExchangeAdd(v106 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
            if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
          }
        }
        goto LABEL_120;
      }
    }
    else
    {
      v58 = (_DWORD **)((char *)this + 272);
    }
    SRWLock = 0;
    wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **v58 = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v70 = Windows::WU::Telemetry::WuProvider::Provider();
    v71 = (int)v70;
    if ( *(_DWORD *)v70 <= 5u
      || (*((_QWORD *)v70 + 2) & 0x400000000000LL) == 0
      || (*((_QWORD *)v70 + 3) & 0x400000000000LL) != *((_QWORD *)v70 + 3) )
    {
      goto LABEL_92;
    }
    v92 = (__int64)"1507.2603.28012.0";
    v72 = (_QWORD *)(*(__int64 (__fastcall **)(struct SystemInterface::Telemetry::CorrelationVector *, _BYTE *))(*(_QWORD *)a2 + 8LL))(
                      a2,
                      v114);
    if ( v72[3] > 0xFu )
      v72 = (_QWORD *)*v72;
    v91 = (__int64)v72;
    v73 = SystemInterface::Providers::GetSystem(v105);
    v74 = *(_QWORD *)v73 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v73 + 8LL) + 4LL);
    v75 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v74 + 8LL))(v74, v107);
    v86 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v75 + 104LL))(*v75)
        - (unsigned __int64)*((unsigned int *)this + 88);
    LODWORD(SRWLock) = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 42) + 8LL))(
                                         *((_QWORD *)this + 42),
                                         &v85)
                     / 60000000;
    v85 = (__int64)a3;
    v93 = (__int64)L"[]";
    v76 = qword_140549FC0;
    v77 = *(_QWORD *)(qword_140549FC0 + 8);
    for ( i = 0; !*(_BYTE *)(v77 + 25); v77 = *(_QWORD *)v77 )
    {
      if ( *(_DWORD *)(v77 + 32) >= *((_DWORD *)this + 82) )
        v76 = v77;
      else
        v77 += 16;
    }
    if ( *(_BYTE *)(v76 + 25) || *((_DWORD *)this + 82) < *(_DWORD *)(v76 + 32) )
      std::_Xout_of_range("invalid map<K, T> key");
    v78 = (_QWORD *)(v76 + 64);
    if ( *(_QWORD *)(v76 + 88) > 7u )
      v78 = (_QWORD *)*v78;
    v95 = (__int64)v78;
    CurrentThreadId = GetCurrentThreadId();
    v79 = *(_DWORD **)v7;
    v83 = *(_DWORD *)(*(_QWORD *)v7 + 72LL);
    v94 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v71,
      (int)&dword_1404A342C,
      (_DWORD)v79 + 8,
      (__int64)&v94,
      (__int64)&v83,
      (__int64)&CurrentThreadId,
      (__int64)&v95,
      (__int64)&v93,
      (__int64)&v85,
      (__int64)&SRWLock,
      (__int64)&v86,
      (__int64)&v91,
      (__int64)&v92);
    v80 = v108;
    if ( v108 )
    {
      if ( _InterlockedExchangeAdd(v108 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v80)(v80);
        if ( _InterlockedExchangeAdd(v80 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v80 + 8LL))(v80);
      }
    }
    v81 = v106;
    if ( v106 )
    {
      if ( _InterlockedExchangeAdd(v106 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v81)(v81);
        if ( _InterlockedExchangeAdd(v81 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v81 + 8LL))(v81);
      }
    }
LABEL_120:
    std::string::_Tidy_deallocate(v114);
    goto LABEL_92;
  }
  if ( v9 < 0 && (v10 = (int *)(v8 + 80), v9 == v10[2]) )
  {
    v11 = (_DWORD **)((char *)this + 272);
    if ( v10 )
    {
      SRWLock = 0;
      wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        this,
        &SRWLock);
      **(_DWORD **)v7 = 2;
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      v12 = Windows::WU::Telemetry::WuProvider::Provider();
      v13 = (int)v12;
      if ( *(_DWORD *)v12 > 5u
        && (*((_QWORD *)v12 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v12 + 3) & 0x400000000000LL) == *((_QWORD *)v12 + 3) )
      {
        v109 = (__int64)"1507.2603.28012.0";
        v14 = (_QWORD *)SystemInterface::Providers::GetSystem(v107);
        v15 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v14 + 40LL))(*v14, v105);
        v16 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v15 + 440LL))(*v15, v114);
        if ( v16[3] > 7u )
          v16 = (_QWORD *)*v16;
        v96 = (__int64)v16;
        v17 = (_QWORD *)(*(__int64 (__fastcall **)(struct SystemInterface::Telemetry::CorrelationVector *, _BYTE *))(*(_QWORD *)a2 + 8LL))(
                          a2,
                          v116);
        if ( v17[3] > 0xFu )
          v17 = (_QWORD *)*v17;
        v97 = (__int64)v17;
        v18 = SystemInterface::Providers::GetSystem(v112);
        v19 = *(_QWORD *)v18 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v18 + 8LL) + 4LL);
        v20 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v19 + 8LL))(v19, v110);
        v98 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 104LL))(*v20)
            - (unsigned __int64)*((unsigned int *)this + 88);
        v87 = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 42) + 8LL))(
                                *((_QWORD *)this + 42),
                                &v86)
            / 60000000;
        v99 = (__int64)a3;
        v100 = (__int64)L"[]";
        v21 = qword_140549FC0;
        v22 = *(_QWORD *)(qword_140549FC0 + 8);
        for ( i = 0; !*(_BYTE *)(v22 + 25); v22 = *(_QWORD *)v22 )
        {
          if ( *(_DWORD *)(v22 + 32) >= *((_DWORD *)this + 82) )
            v21 = v22;
          else
            v22 += 16;
        }
        if ( *(_BYTE *)(v21 + 25) || *((_DWORD *)this + 82) < *(_DWORD *)(v21 + 32) )
          std::_Xout_of_range("invalid map<K, T> key");
        v23 = (_QWORD *)(v21 + 64);
        if ( *(_QWORD *)(v21 + 88) > 7u )
          v23 = (_QWORD *)*v23;
        v101 = (__int64)v23;
        v102 = *((_QWORD *)v10 + 15);
        v103 = *((_QWORD *)v10 + 14);
        v88 = v10[26];
        v104 = *((_QWORD *)v10 + 12);
        v94 = *((_QWORD *)v10 + 11);
        v89 = v10[20];
        v95 = *((_QWORD *)v10 + 9);
        v90 = v10[8];
        v93 = *((_QWORD *)v10 + 3);
        v83 = *v10;
        v85 = *((_QWORD *)v10 + 16);
        CurrentThreadId = v10[16];
        v86 = *((_QWORD *)v10 + 7);
        LODWORD(SRWLock) = v10[2];
        v91 = 0x1000000;
        v92 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          v13,
          (int)&byte_1404A34D7,
          *(_DWORD *)v7 + 8,
          (__int64)&v92,
          (__int64)&v91,
          (__int64)&SRWLock,
          (__int64)&v86,
          (__int64)&CurrentThreadId,
          (__int64)&v85,
          (__int64)&v83,
          (__int64)&v93,
          (__int64)&v90,
          (__int64)&v95,
          (__int64)&v89,
          (__int64)&v94,
          (__int64)&v104,
          (__int64)&v88,
          (__int64)&v103,
          (__int64)&v102,
          (__int64)&v101,
          (__int64)&v100,
          (__int64)&v99,
          (__int64)&v87,
          (__int64)&v98,
          (__int64)&v97,
          (__int64)&v96,
          (__int64)&v109);
        v24 = v111;
        if ( v111 )
        {
          if ( _InterlockedExchangeAdd(v111 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
            if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
          }
        }
        v25 = v113;
        if ( v113 )
        {
          if ( _InterlockedExchangeAdd(v113 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
            if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          }
        }
        std::string::_Tidy_deallocate(v116);
        std::wstring::~wstring(v114, v26);
        v27 = v106;
        if ( v106 )
        {
          if ( _InterlockedExchangeAdd(v106 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
            if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
          }
        }
        v28 = v108;
LABEL_88:
        if ( v28 )
        {
          if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
            if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
          }
        }
        goto LABEL_92;
      }
      goto LABEL_92;
    }
  }
  else
  {
    v11 = (_DWORD **)((char *)this + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v29 = *v11;
  v30 = 2;
  *v29 = 2;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v31 = Windows::WU::Telemetry::WuProvider::Provider();
  v85 = (__int64)v31;
  if ( *(_DWORD *)v31 > 5u
    && (*((_QWORD *)v31 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v31 + 3) & 0x400000000000LL) == *((_QWORD *)v31 + 3) )
  {
    v32 = (_QWORD *)SystemInterface::Providers::GetSystem(v110);
    v33 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v32 + 40LL))(*v32, v112);
    v34 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v33 + 440LL))(*v33, v116);
    v35 = (const OLECHAR *)v34;
    if ( *(_QWORD *)(v34 + 24) > 7u )
      v35 = *(const OLECHAR **)v34;
    v36 = (*(__int64 (__fastcall **)(struct SystemInterface::Telemetry::CorrelationVector *, _BYTE *))(*(_QWORD *)a2 + 8LL))(
            a2,
            v114);
    v37 = (const CHAR *)v36;
    if ( *(_QWORD *)(v36 + 24) > 0xFu )
      v37 = *(const CHAR **)v36;
    v38 = SystemInterface::Providers::GetSystem(v105);
    v39 = *(_QWORD *)v38 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v38 + 8LL) + 4LL);
    v40 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v39 + 8LL))(v39, v107);
    v92 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v40 + 104LL))(*v40)
        - (unsigned __int64)*((unsigned int *)this + 88);
    LODWORD(SRWLock) = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 42) + 8LL))(
                                         *((_QWORD *)this + 42),
                                         &v93)
                     / 60000000;
    v41 = qword_140549FC0;
    v42 = *(_QWORD *)(qword_140549FC0 + 8);
    for ( i = 0; !*(_BYTE *)(v42 + 25); v42 = *(_QWORD *)v42 )
    {
      if ( *(_DWORD *)(v42 + 32) >= *((_DWORD *)this + 82) )
        v41 = v42;
      else
        v42 += 16;
    }
    if ( *(_BYTE *)(v41 + 25) || *((_DWORD *)this + 82) < *(_DWORD *)(v41 + 32) )
      std::_Xout_of_range("invalid map<K, T> key");
    v43 = (const OLECHAR *)(v41 + 64);
    if ( *((_QWORD *)v43 + 3) > 7u )
      v43 = *(const OLECHAR **)v43;
    CurrentThreadId = GetCurrentThreadId();
    v44 = *(_QWORD *)v7;
    v83 = *(_DWORD *)(*(_QWORD *)v7 + 72LL);
    v86 = 0x1000000;
    v142 = "1507.2603.28012.0";
    v143 = 18;
    if ( v35 )
    {
      v45 = -1;
      do
        ++v45;
      while ( v35[v45] );
      v46 = 2 * v45 + 2;
    }
    else
    {
      v35 = &psz;
      v46 = 2;
    }
    v139 = v35;
    v140 = v46;
    v141 = 0;
    if ( v37 )
    {
      v47 = -1;
      do
        ++v47;
      while ( v37[v47] );
      v48 = v47 + 1;
    }
    else
    {
      v37 = &pszCabPath;
      v48 = 1;
    }
    v136 = v37;
    v137 = v48;
    v138 = 0;
    v134 = &v92;
    v135 = 8;
    p_SRWLock = &SRWLock;
    v133 = 4;
    v49 = (const OLECHAR *)v91;
    if ( v91 )
    {
      v50 = -1;
      do
        ++v50;
      while ( *(_WORD *)(v91 + 2 * v50) );
      v51 = 2 * v50 + 2;
    }
    else
    {
      v49 = &psz;
      v51 = 2;
    }
    v129 = v49;
    v130 = v51;
    v131 = 0;
    v127 = L"[]";
    v128 = 6;
    if ( v43 )
    {
      v52 = -1;
      do
        ++v52;
      while ( v43[v52] );
      v30 = 2 * v52 + 2;
    }
    else
    {
      v43 = &psz;
    }
    v124 = v43;
    v125 = v30;
    v126 = 0;
    p_CurrentThreadId = &CurrentThreadId;
    v123 = 4;
    v120 = &v83;
    v121 = 4;
    v118 = &v86;
    v119 = 8;
    tlgWriteTransfer_EventWriteTransfer(v85, (int)&word_1404A3662, v44 + 8, 0, 0xDu, &v117);
    v53 = v108;
    if ( v108 )
    {
      if ( _InterlockedExchangeAdd(v108 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
        if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
      }
    }
    v54 = v106;
    if ( v106 )
    {
      if ( _InterlockedExchangeAdd(v106 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
        if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
      }
    }
    std::string::_Tidy_deallocate(v114);
    std::wstring::~wstring(v116, v55);
    v56 = v113;
    if ( v113 )
    {
      if ( _InterlockedExchangeAdd(v113 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
        if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
      }
    }
    v28 = v111;
    goto LABEL_88;
  }
LABEL_92:
  wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x1402cd844  mov     [rsp-8+arg_10], rbx
0x1402cd849  push    rbp
0x1402cd84a  push    rsi
0x1402cd84b  push    rdi
0x1402cd84c  push    r12
0x1402cd84e  push    r13
0x1402cd850  push    r14
0x1402cd852  push    r15
0x1402cd854  lea     rbp, [rsp-1A0h]
0x1402cd85c  sub     rsp, 300h
0x1402cd863  mov     rax, cs:__security_cookie
0x1402cd86a  xor     rax, rsp
0x1402cd86d  mov     [rbp+1D0h+var_40], rax
0x1402cd874  mov     r12, r8
0x1402cd877  mov     [rbp+1D0h+var_220], r8
0x1402cd87b  mov     r15, rdx
0x1402cd87e  mov     rdi, rcx
0x1402cd881  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections> `wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl(void)'::`2'::impl
0x1402cd888  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(void)
0x1402cd88d  lea     r14, [rdi+110h]
0x1402cd894  mov     rbx, [r14]
0x1402cd897  mov     ecx, [rbx+48h]
0x1402cd89a  xor     r13d, r13d
0x1402cd89d  test    al, al
0x1402cd89f  jz      loc_1402CE1A2
0x1402cd8a5  test    ecx, ecx
0x1402cd8a7  jns     loc_1402CDCEE
0x1402cd8ad  add     rbx, 50h ; 'P'
0x1402cd8b1  cmp     ecx, [rbx+8]
0x1402cd8b4  jnz     loc_1402CDCEE
0x1402cd8ba  mov     rsi, r14
0x1402cd8bd  test    rbx, rbx
0x1402cd8c0  jz      loc_1402CDCF1
0x1402cd8c6  mov     [rbp+1D0h+SRWLock], r13
0x1402cd8ca  lea     rdx, [rbp+1D0h+SRWLock]
0x1402cd8ce  mov     rcx, rdi
0x1402cd8d1  call    ?LockExclusive@?$ActivityBase@VBaseCore@Telemetry@Windows@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1402cd8d6  mov     rax, [r14]
0x1402cd8d9  mov     dword ptr [rax], 2
0x1402cd8df  mov     rcx, [rbp+1D0h+SRWLock]; SRWLock
0x1402cd8e3  test    rcx, rcx
0x1402cd8e6  jz      short loc_1402CD8EE
0x1402cd8e8  call    cs:__imp_ReleaseSRWLockExclusive
0x1402cd8ee  call    ?Provider@WuProvider@Telemetry@WU@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::WU::Telemetry::WuProvider::Provider(void)
0x1402cd8f3  mov     rsi, rax
0x1402cd8f6  cmp     dword ptr [rax], 5
0x1402cd8f9  jbe     loc_1402CE170
0x1402cd8ff  mov     rcx, 400000000000h
0x1402cd909  test    [rax+10h], rcx
0x1402cd90d  jz      loc_1402CE170
0x1402cd913  mov     rax, [rax+18h]
0x1402cd917  and     rax, rcx
0x1402cd91a  cmp     rax, [rsi+18h]
0x1402cd91e  jnz     loc_1402CE170
0x1402cd924  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1402cd92b  mov     [rbp+1D0h+var_190], rax
0x1402cd92f  lea     rcx, [rbp+1D0h+var_1A0]
0x1402cd933  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1402cd938  nop
0x1402cd939  mov     rcx, [rax]
0x1402cd93c  mov     rax, [rcx]
0x1402cd93f  lea     rdx, [rbp+1D0h+var_1B0]
0x1402cd943  mov     rax, [rax+28h]
0x1402cd947  call    _guard_dispatch_icall
0x1402cd94c  nop
0x1402cd94d  mov     rcx, [rax]
0x1402cd950  mov     rax, [rcx]
0x1402cd953  lea     rdx, [rbp+1D0h+var_168]
0x1402cd957  mov     rax, [rax+1B8h]
0x1402cd95e  call    _guard_dispatch_icall
0x1402cd963  nop
0x1402cd964  cmp     qword ptr [rax+18h], 7
0x1402cd969  jbe     short loc_1402CD96E
0x1402cd96b  mov     rax, [rax]
0x1402cd96e  mov     [rbp+1D0h+var_1F8], rax
0x1402cd972  mov     rax, [r15]
0x1402cd975  lea     rdx, [rbp+1D0h+var_130]
0x1402cd97c  mov     rcx, r15
0x1402cd97f  mov     rax, [rax+8]
0x1402cd983  call    _guard_dispatch_icall
0x1402cd988  nop
0x1402cd989  cmp     qword ptr [rax+18h], 0Fh
0x1402cd98e  jbe     short loc_1402CD993
0x1402cd990  mov     rax, [rax]
0x1402cd993  mov     [rbp+1D0h+var_1F0], rax
0x1402cd997  lea     rcx, [rbp+1D0h+var_178]
0x1402cd99b  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1402cd9a0  nop
0x1402cd9a1  mov     rdx, [rax]
0x1402cd9a4  mov     rax, [rdx+8]
0x1402cd9a8  movsxd  rcx, dword ptr [rax+4]
0x1402cd9ac  add     rdx, 8
0x1402cd9b0  add     rcx, rdx
0x1402cd9b3  mov     rax, [rcx]
0x1402cd9b6  lea     rdx, [rbp+1D0h+var_188]
0x1402cd9ba  mov     rax, [rax+8]
0x1402cd9be  call    _guard_dispatch_icall
0x1402cd9c3  nop
0x1402cd9c4  mov     rcx, [rax]
0x1402cd9c7  mov     rax, [rcx]
0x1402cd9ca  mov     rax, [rax+68h]
0x1402cd9ce  call    _guard_dispatch_icall
0x1402cd9d3  mov     ecx, eax
0x1402cd9d5  mov     eax, [rdi+160h]
0x1402cd9db  sub     rcx, rax
0x1402cd9de  mov     [rbp+1D0h+var_1E8], rcx
0x1402cd9e2  mov     rcx, [rdi+150h]
0x1402cd9e9  mov     rax, [rcx]
0x1402cd9ec  lea     rdx, [rbp+1D0h+var_238]
0x1402cd9f0  mov     rax, [rax+8]
0x1402cd9f4  call    _guard_dispatch_icall
0x1402cd9f9  mov     rcx, [rax]
0x1402cd9fc  mov     rax, 8F2A633943A6D729h
0x1402cda06  imul    rcx
0x1402cda09  add     rdx, rcx
0x1402cda0c  sar     rdx, 19h
0x1402cda10  mov     rax, rdx
0x1402cda13  shr     rax, 3Fh
0x1402cda17  add     rdx, rax
0x1402cda1a  mov     dword ptr [rbp+1D0h+var_230], edx
0x1402cda1d  mov     [rbp+1D0h+var_1E0], r12
0x1402cda21  lea     rax, asc_14047AB74; "[]"
0x1402cda28  mov     [rbp+1D0h+var_1D8], rax
0x1402cda2c  mov     rcx, cs:qword_140549FC0
0x1402cda33  mov     rax, [rcx+8]
0x1402cda37  xor     edx, edx
0x1402cda39  mov     [rbp+1D0h+var_13C], edx
0x1402cda3f  cmp     [rax+19h], r13b
0x1402cda43  jnz     short loc_1402CDA62
0x1402cda45  mov     edx, [rdi+148h]
0x1402cda4b  cmp     [rax+20h], edx
0x1402cda4e  jge     short loc_1402CDA56
0x1402cda50  add     rax, 10h
0x1402cda54  jmp     short loc_1402CDA59
0x1402cda56  mov     rcx, rax
0x1402cda59  mov     rax, [rax]
0x1402cda5c  cmp     [rax+19h], r13b
0x1402cda60  jz      short loc_1402CDA4B
0x1402cda62  cmp     [rcx+19h], r13b
0x1402cda66  jnz     loc_1402CE7F5
0x1402cda6c  mov     eax, [rcx+20h]
0x1402cda6f  cmp     [rdi+148h], eax
0x1402cda75  jl      loc_1402CE7F5
0x1402cda7b  lea     rax, [rcx+40h]
0x1402cda7f  cmp     qword ptr [rax+18h], 7
0x1402cda84  jbe     short loc_1402CDA89
0x1402cda86  mov     rax, [rax]
0x1402cda89  mov     [rbp+1D0h+var_1D0], rax
0x1402cda8d  mov     rax, [rbx+78h]
0x1402cda91  mov     [rbp+1D0h+var_1C8], rax
0x1402cda95  mov     rax, [rbx+70h]
0x1402cda99  mov     [rbp+1D0h+var_1C0], rax
0x1402cda9d  mov     eax, [rbx+68h]
0x1402cdaa0  mov     dword ptr [rbp+1D0h+var_230+4], eax
0x1402cdaa3  mov     rax, [rbx+60h]
0x1402cdaa7  mov     [rbp+1D0h+var_1B8], rax
0x1402cdaab  mov     rax, [rbx+58h]
0x1402cdaaf  mov     [rbp+1D0h+var_208], rax
0x1402cdab3  mov     eax, [rbx+50h]
0x1402cdab6  mov     dword ptr [rbp+1D0h+var_228], eax
0x1402cdab9  mov     rax, [rbx+48h]
0x1402cdabd  mov     [rbp+1D0h+var_200], rax
0x1402cdac1  mov     eax, [rbx+20h]
0x1402cdac4  mov     dword ptr [rbp+1D0h+var_228+4], eax
0x1402cdac7  mov     rax, [rbx+18h]
0x1402cdacb  mov     [rbp+1D0h+var_210], rax
0x1402cdacf  mov     eax, [rbx]
0x1402cdad1  mov     dword ptr [rbp+1D0h+var_248], eax
0x1402cdad4  mov     rax, [rbx+80h]
0x1402cdadb  mov     [rbp+1D0h+var_240], rax
0x1402cdadf  mov     eax, [rbx+40h]
0x1402cdae2  mov     dword ptr [rbp+1D0h+var_248+4], eax
0x1402cdae5  mov     rax, [rbx+38h]
0x1402cdae9  mov     [rbp+1D0h+var_238], rax
0x1402cdaed  mov     eax, [rbx+8]
0x1402cdaf0  mov     dword ptr [rbp+1D0h+SRWLock], eax
0x1402cdaf3  mov     eax, 1000000h
0x1402cdaf8  mov     [rbp+1D0h+var_220], rax
0x1402cdafc  mov     [rbp+1D0h+var_218], rax
0x1402cdb00  mov     r8, [r14]
0x1402cdb03  add     r8, 8; int
0x1402cdb07  lea     rax, [rbp+1D0h+var_190]
0x1402cdb0b  mov     [rsp+330h+var_258], rax; __int64
0x1402cdb13  lea     rax, [rbp+1D0h+var_1F8]
0x1402cdb17  mov     [rsp+330h+var_260], rax; __int64
0x1402cdb1f  lea     rax, [rbp+1D0h+var_1F0]
0x1402cdb23  mov     [rsp+330h+var_268], rax; __int64
0x1402cdb2b  lea     rax, [rbp+1D0h+var_1E8]
0x1402cdb2f  mov     [rsp+330h+var_270], rax; __int64
0x1402cdb37  lea     rax, [rbp+1D0h+var_230]
0x1402cdb3b  mov     [rsp+330h+var_278], rax; __int64
0x1402cdb43  lea     rax, [rbp+1D0h+var_1E0]
0x1402cdb47  mov     [rsp+330h+var_280], rax; __int64
0x1402cdb4f  lea     rax, [rbp+1D0h+var_1D8]
0x1402cdb53  mov     [rsp+330h+var_288], rax; __int64
0x1402cdb5b  lea     rax, [rbp+1D0h+var_1D0]
0x1402cdb5f  mov     [rsp+330h+var_290], rax; __int64
0x1402cdb67  lea     rax, [rbp+1D0h+var_1C8]
0x1402cdb6b  mov     [rsp+330h+var_298], rax; __int64
0x1402cdb73  lea     rax, [rbp+1D0h+var_1C0]
0x1402cdb77  mov     [rsp+330h+var_2A0], rax; __int64
0x1402cdb7f  lea     rax, [rbp+1D0h+var_230+4]
0x1402cdb83  mov     [rsp+330h+var_2A8], rax; __int64
0x1402cdb8b  lea     rax, [rbp+1D0h+var_1B8]
0x1402cdb8f  mov     [rsp+330h+var_2B0], rax; __int64
0x1402cdb97  lea     rax, [rbp+1D0h+var_208]
0x1402cdb9b  mov     [rsp+330h+var_2B8], rax; __int64
0x1402cdba0  lea     rax, [rbp+1D0h+var_228]
0x1402cdba4  mov     [rsp+330h+var_2C0], rax; __int64
0x1402cdba9  lea     rax, [rbp+1D0h+var_200]
0x1402cdbad  mov     [rsp+330h+var_2C8], rax; __int64
0x1402cdbb2  lea     rax, [rbp+1D0h+var_228+4]
0x1402cdbb6  mov     [rsp+330h+var_2D0], rax; __int64
0x1402cdbbb  lea     rax, [rbp+1D0h+var_210]
0x1402cdbbf  mov     [rsp+330h+var_2D8], rax; __int64
0x1402cdbc4  lea     rax, [rbp+1D0h+var_248]
0x1402cdbc8  mov     [rsp+330h+var_2E0], rax; __int64
0x1402cdbcd  lea     rax, [rbp+1D0h+var_240]
0x1402cdbd1  mov     [rsp+330h+var_2E8], rax; __int64
0x1402cdbd6  lea     rax, [rbp+1D0h+var_248+4]
0x1402cdbda  mov     [rsp+330h+var_2F0], rax; __int64
0x1402cdbdf  lea     rax, [rbp+1D0h+var_238]
0x1402cdbe3  mov     [rsp+330h+var_2F8], rax; __int64
0x1402cdbe8  lea     rax, [rbp+1D0h+SRWLock]
0x1402cdbec  mov     [rsp+330h+var_300], rax; __int64
0x1402cdbf1  lea     rax, [rbp+1D0h+var_220]
0x1402cdbf5  mov     [rsp+330h+var_308], rax; __int64
0x1402cdbfa  lea     rax, [rbp+1D0h+var_218]
0x1402cdbfe  mov     qword ptr [rsp+330h+var_310], rax; __int64
0x1402cdc03  lea     rdx, byte_1404A34D7; int
0x1402cdc0a  mov     rcx, rsi; int
0x1402cdc0d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U4@U2@U1@U3@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@4545645666643565@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x1402cdc12  nop
0x1402cdc13  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1402cdc17  mov     rsi, [rbp+1D0h+var_180]
0x1402cdc1b  test    rsi, rsi
0x1402cdc1e  jz      short loc_1402CDC54
0x1402cdc20  mov     eax, ebx
0x1402cdc22  lock xadd [rsi+8], eax
0x1402cdc27  add     eax, ebx
0x1402cdc29  jnz     short loc_1402CDC54
0x1402cdc2b  mov     rax, [rsi]
0x1402cdc2e  mov     rcx, rsi
0x1402cdc31  mov     rax, [rax]
0x1402cdc34  call    _guard_dispatch_icall
0x1402cdc39  mov     eax, ebx
0x1402cdc3b  lock xadd [rsi+0Ch], eax
0x1402cdc40  add     eax, ebx
0x1402cdc42  jnz     short loc_1402CDC54
0x1402cdc44  mov     rax, [rsi]
0x1402cdc47  mov     rcx, rsi
0x1402cdc4a  mov     rax, [rax+8]
0x1402cdc4e  call    _guard_dispatch_icall
0x1402cdc53  nop
0x1402cdc54  mov     rsi, [rbp+1D0h+var_170]
0x1402cdc58  test    rsi, rsi
0x1402cdc5b  jz      short loc_1402CDC91
0x1402cdc5d  mov     eax, ebx
0x1402cdc5f  lock xadd [rsi+8], eax
0x1402cdc64  add     eax, ebx
0x1402cdc66  jnz     short loc_1402CDC91
0x1402cdc68  mov     rax, [rsi]
0x1402cdc6b  mov     rcx, rsi
0x1402cdc6e  mov     rax, [rax]
0x1402cdc71  call    _guard_dispatch_icall
0x1402cdc76  mov     eax, ebx
0x1402cdc78  lock xadd [rsi+0Ch], eax
0x1402cdc7d  add     eax, ebx
0x1402cdc7f  jnz     short loc_1402CDC91
0x1402cdc81  mov     rax, [rsi]
0x1402cdc84  mov     rcx, rsi
0x1402cdc87  mov     rax, [rax+8]
0x1402cdc8b  call    _guard_dispatch_icall
0x1402cdc90  nop
0x1402cdc91  lea     rcx, [rbp+1D0h+var_130]
0x1402cdc98  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1402cdc9d  nop
0x1402cdc9e  lea     rcx, [rbp+1D0h+var_168]
0x1402cdca2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402cdca7  nop
0x1402cdca8  mov     rsi, [rbp+1D0h+var_1A8]
0x1402cdcac  test    rsi, rsi
0x1402cdcaf  jz      short loc_1402CDCE5
0x1402cdcb1  mov     eax, ebx
0x1402cdcb3  lock xadd [rsi+8], eax
0x1402cdcb8  add     eax, ebx
0x1402cdcba  jnz     short loc_1402CDCE5
0x1402cdcbc  mov     rax, [rsi]
0x1402cdcbf  mov     rcx, rsi
0x1402cdcc2  mov     rax, [rax]
0x1402cdcc5  call    _guard_dispatch_icall
0x1402cdcca  mov     eax, ebx
0x1402cdccc  lock xadd [rsi+0Ch], eax
0x1402cdcd1  add     eax, ebx
0x1402cdcd3  jnz     short loc_1402CDCE5
0x1402cdcd5  mov     rax, [rsi]
0x1402cdcd8  mov     rcx, rsi
0x1402cdcdb  mov     rax, [rax+8]
0x1402cdcdf  call    _guard_dispatch_icall
0x1402cdce4  nop
  ... truncated ...
```
