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
  volatile signed __int32 *v26; // rsi
  volatile signed __int32 *v27; // rsi
  _DWORD *v28; // rax
  int v29; // esi
  const struct _tlgProvider_t *v30; // rax
  _QWORD *v31; // rax
  _QWORD *v32; // rax
  __int64 v33; // rax
  const OLECHAR *v34; // r13
  __int64 v35; // rax
  const CHAR *v36; // r12
  __int64 v37; // rax
  __int64 v38; // rcx
  _QWORD *v39; // rax
  __int64 v40; // r15
  __int64 v41; // rax
  const OLECHAR *v42; // r15
  __int64 v43; // r8
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rax
  int v47; // eax
  const OLECHAR *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // rsi
  volatile signed __int32 *v52; // rsi
  volatile signed __int32 *v53; // rsi
  volatile signed __int32 *v54; // rsi
  int *v55; // rbx
  _DWORD **v56; // rsi
  const struct _tlgProvider_t *v57; // rax
  int v58; // esi
  _QWORD *v59; // rax
  __int64 System; // rax
  __int64 v61; // rcx
  _QWORD *v62; // rax
  __int64 v63; // rcx
  __int64 v64; // rax
  _QWORD *v65; // rax
  volatile signed __int32 *v66; // rsi
  volatile signed __int32 *v67; // rsi
  const struct _tlgProvider_t *v68; // rax
  int v69; // ebx
  _QWORD *v70; // rax
  __int64 v71; // rax
  __int64 v72; // rcx
  _QWORD *v73; // rax
  __int64 v74; // rcx
  __int64 v75; // rax
  _QWORD *v76; // rax
  _DWORD *v77; // r8
  volatile signed __int32 *v78; // rsi
  volatile signed __int32 *v79; // rsi
  PSRWLOCK SRWLock; // [rsp+E0h] [rbp-80h] BYREF
  int v81; // [rsp+E8h] [rbp-78h] BYREF
  DWORD CurrentThreadId; // [rsp+ECh] [rbp-74h] BYREF
  __int64 v83; // [rsp+F0h] [rbp-70h] BYREF
  __int64 v84; // [rsp+F8h] [rbp-68h] BYREF
  int v85; // [rsp+100h] [rbp-60h] BYREF
  int v86; // [rsp+104h] [rbp-5Ch] BYREF
  int v87; // [rsp+108h] [rbp-58h] BYREF
  int v88; // [rsp+10Ch] [rbp-54h] BYREF
  __int64 v89; // [rsp+110h] [rbp-50h] BYREF
  __int64 v90; // [rsp+118h] [rbp-48h] BYREF
  __int64 v91; // [rsp+120h] [rbp-40h] BYREF
  __int64 v92; // [rsp+128h] [rbp-38h] BYREF
  __int64 v93; // [rsp+130h] [rbp-30h] BYREF
  __int64 v94; // [rsp+138h] [rbp-28h] BYREF
  __int64 v95; // [rsp+140h] [rbp-20h] BYREF
  __int64 v96; // [rsp+148h] [rbp-18h] BYREF
  __int64 v97; // [rsp+150h] [rbp-10h] BYREF
  __int64 v98; // [rsp+158h] [rbp-8h] BYREF
  __int64 v99; // [rsp+160h] [rbp+0h] BYREF
  __int64 v100; // [rsp+168h] [rbp+8h] BYREF
  __int64 v101; // [rsp+170h] [rbp+10h] BYREF
  __int64 v102; // [rsp+178h] [rbp+18h] BYREF
  _BYTE v103[8]; // [rsp+180h] [rbp+20h] BYREF
  volatile signed __int32 *v104; // [rsp+188h] [rbp+28h]
  _BYTE v105[8]; // [rsp+190h] [rbp+30h] BYREF
  volatile signed __int32 *v106; // [rsp+198h] [rbp+38h]
  __int64 v107; // [rsp+1A0h] [rbp+40h] BYREF
  _BYTE v108[8]; // [rsp+1A8h] [rbp+48h] BYREF
  volatile signed __int32 *v109; // [rsp+1B0h] [rbp+50h]
  _BYTE v110[8]; // [rsp+1B8h] [rbp+58h] BYREF
  volatile signed __int32 *v111; // [rsp+1C0h] [rbp+60h]
  _BYTE v112[44]; // [rsp+1C8h] [rbp+68h] BYREF
  int i; // [rsp+1F4h] [rbp+94h]
  _BYTE v114[32]; // [rsp+200h] [rbp+A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v115; // [rsp+220h] [rbp+C0h] BYREF
  __int64 *v116; // [rsp+240h] [rbp+E0h]
  __int64 v117; // [rsp+248h] [rbp+E8h]
  int *v118; // [rsp+250h] [rbp+F0h]
  __int64 v119; // [rsp+258h] [rbp+F8h]
  DWORD *p_CurrentThreadId; // [rsp+260h] [rbp+100h]
  __int64 v121; // [rsp+268h] [rbp+108h]
  const OLECHAR *v122; // [rsp+270h] [rbp+110h]
  int v123; // [rsp+278h] [rbp+118h]
  int v124; // [rsp+27Ch] [rbp+11Ch]
  const wchar_t *v125; // [rsp+280h] [rbp+120h]
  __int64 v126; // [rsp+288h] [rbp+128h]
  const OLECHAR *v127; // [rsp+290h] [rbp+130h]
  int v128; // [rsp+298h] [rbp+138h]
  int v129; // [rsp+29Ch] [rbp+13Ch]
  PSRWLOCK *p_SRWLock; // [rsp+2A0h] [rbp+140h]
  __int64 v131; // [rsp+2A8h] [rbp+148h]
  __int64 *v132; // [rsp+2B0h] [rbp+150h]
  __int64 v133; // [rsp+2B8h] [rbp+158h]
  const CHAR *v134; // [rsp+2C0h] [rbp+160h]
  int v135; // [rsp+2C8h] [rbp+168h]
  int v136; // [rsp+2CCh] [rbp+16Ch]
  const OLECHAR *v137; // [rsp+2D0h] [rbp+170h]
  int v138; // [rsp+2D8h] [rbp+178h]
  int v139; // [rsp+2DCh] [rbp+17Ch]
  const char *v140; // [rsp+2E0h] [rbp+180h]
  __int64 v141; // [rsp+2E8h] [rbp+188h]

  v89 = (__int64)a3;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl);
  v7 = (char *)this + 272;
  v8 = *((_QWORD *)this + 34);
  v9 = *(_DWORD *)(v8 + 72);
  if ( !IsEnabled )
  {
    if ( v9 < 0 && (v55 = (int *)(v8 + 80), v9 == v55[2]) )
    {
      v56 = (_DWORD **)((char *)this + 272);
      if ( v55 )
      {
        SRWLock = 0;
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
          this,
          &SRWLock);
        **(_DWORD **)v7 = 2;
        if ( SRWLock )
          ReleaseSRWLockExclusive(SRWLock);
        v57 = Windows::WU::Telemetry::WuProvider::Provider();
        v58 = (int)v57;
        if ( *(_DWORD *)v57 <= 5u
          || (*((_QWORD *)v57 + 2) & 0x400000000000LL) == 0
          || (*((_QWORD *)v57 + 3) & 0x400000000000LL) != *((_QWORD *)v57 + 3) )
        {
          goto LABEL_92;
        }
        v90 = (__int64)"1507.2603.28012.0";
        v59 = (_QWORD *)(*(__int64 (__fastcall **)(struct SystemInterface::Telemetry::CorrelationVector *, _BYTE *))(*(_QWORD *)a2 + 8LL))(
                          a2,
                          v112);
        if ( v59[3] > 0xFu )
          v59 = (_QWORD *)*v59;
        v89 = (__int64)v59;
        System = SystemInterface::Providers::GetSystem(v103);
        v61 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
        v62 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v61 + 8LL))(v61, v105);
        v84 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v62 + 104LL))(*v62)
            - (unsigned __int64)*((unsigned int *)this + 88);
        LODWORD(SRWLock) = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 42) + 8LL))(
                                             *((_QWORD *)this + 42),
                                             &v83)
                         / 60000000;
        v83 = (__int64)a3;
        v91 = (__int64)L"[]";
        v63 = qword_140549FC0;
        v64 = *(_QWORD *)(qword_140549FC0 + 8);
        for ( i = 0; !*(_BYTE *)(v64 + 25); v64 = *(_QWORD *)v64 )
        {
          if ( *(_DWORD *)(v64 + 32) >= *((_DWORD *)this + 82) )
            v63 = v64;
          else
            v64 += 16;
        }
        if ( *(_BYTE *)(v63 + 25) || *((_DWORD *)this + 82) < *(_DWORD *)(v63 + 32) )
          std::_Xout_of_range("invalid map<K, T> key");
        v65 = (_QWORD *)(v63 + 64);
        if ( *(_QWORD *)(v63 + 88) > 7u )
          v65 = (_QWORD *)*v65;
        v93 = (__int64)v65;
        v92 = *((_QWORD *)v55 + 15);
        v102 = *((_QWORD *)v55 + 14);
        CurrentThreadId = v55[26];
        v101 = *((_QWORD *)v55 + 12);
        v100 = *((_QWORD *)v55 + 11);
        v81 = v55[20];
        v99 = *((_QWORD *)v55 + 9);
        v88 = v55[8];
        v98 = *((_QWORD *)v55 + 3);
        v87 = *v55;
        v97 = *((_QWORD *)v55 + 16);
        v86 = v55[16];
        v96 = *((_QWORD *)v55 + 7);
        v85 = v55[2];
        v95 = 0x1000000;
        v94 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v58,
          (int)&word_1404A3716,
          *(_DWORD *)v7 + 8,
          (__int64)&v94,
          (__int64)&v95,
          (__int64)&v85,
          (__int64)&v96,
          (__int64)&v86,
          (__int64)&v97,
          (__int64)&v87,
          (__int64)&v98,
          (__int64)&v88,
          (__int64)&v99,
          (__int64)&v81,
          (__int64)&v100,
          (__int64)&v101,
          (__int64)&CurrentThreadId,
          (__int64)&v102,
          (__int64)&v92,
          (__int64)&v93,
          (__int64)&v91,
          (__int64)&v83,
          (__int64)&SRWLock,
          (__int64)&v84,
          (__int64)&v89,
          (__int64)&v90);
        v66 = v106;
        if ( v106 )
        {
          if ( _InterlockedExchangeAdd(v106 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
            if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
          }
        }
        v67 = v104;
        if ( v104 )
        {
          if ( _InterlockedExchangeAdd(v104 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v67)(v67);
            if ( _InterlockedExchangeAdd(v67 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v67 + 8LL))(v67);
          }
        }
        goto LABEL_120;
      }
    }
    else
    {
      v56 = (_DWORD **)((char *)this + 272);
    }
    SRWLock = 0;
    wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **v56 = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v68 = Windows::WU::Telemetry::WuProvider::Provider();
    v69 = (int)v68;
    if ( *(_DWORD *)v68 <= 5u
      || (*((_QWORD *)v68 + 2) & 0x400000000000LL) == 0
      || (*((_QWORD *)v68 + 3) & 0x400000000000LL) != *((_QWORD *)v68 + 3) )
    {
      goto LABEL_92;
    }
    v90 = (__int64)"1507.2603.28012.0";
    v70 = (_QWORD *)(*(__int64 (__fastcall **)(struct SystemInterface::Telemetry::CorrelationVector *, _BYTE *))(*(_QWORD *)a2 + 8LL))(
                      a2,
                      v112);
    if ( v70[3] > 0xFu )
      v70 = (_QWORD *)*v70;
    v89 = (__int64)v70;
    v71 = SystemInterface::Providers::GetSystem(v103);
    v72 = *(_QWORD *)v71 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v71 + 8LL) + 4LL);
    v73 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v72 + 8LL))(v72, v105);
    v84 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v73 + 104LL))(*v73)
        - (unsigned __int64)*((unsigned int *)this + 88);
    LODWORD(SRWLock) = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 42) + 8LL))(
                                         *((_QWORD *)this + 42),
                                         &v83)
                     / 60000000;
    v83 = (__int64)a3;
    v91 = (__int64)L"[]";
    v74 = qword_140549FC0;
    v75 = *(_QWORD *)(qword_140549FC0 + 8);
    for ( i = 0; !*(_BYTE *)(v75 + 25); v75 = *(_QWORD *)v75 )
    {
      if ( *(_DWORD *)(v75 + 32) >= *((_DWORD *)this + 82) )
        v74 = v75;
      else
        v75 += 16;
    }
    if ( *(_BYTE *)(v74 + 25) || *((_DWORD *)this + 82) < *(_DWORD *)(v74 + 32) )
      std::_Xout_of_range("invalid map<K, T> key");
    v76 = (_QWORD *)(v74 + 64);
    if ( *(_QWORD *)(v74 + 88) > 7u )
      v76 = (_QWORD *)*v76;
    v93 = (__int64)v76;
    CurrentThreadId = GetCurrentThreadId();
    v77 = *(_DWORD **)v7;
    v81 = *(_DWORD *)(*(_QWORD *)v7 + 72LL);
    v92 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v69,
      (int)&dword_1404A342C,
      (_DWORD)v77 + 8,
      (__int64)&v92,
      (__int64)&v81,
      (__int64)&CurrentThreadId,
      (__int64)&v93,
      (__int64)&v91,
      (__int64)&v83,
      (__int64)&SRWLock,
      (__int64)&v84,
      (__int64)&v89,
      (__int64)&v90);
    v78 = v106;
    if ( v106 )
    {
      if ( _InterlockedExchangeAdd(v106 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v78)(v78);
        if ( _InterlockedExchangeAdd(v78 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v78 + 8LL))(v78);
      }
    }
    v79 = v104;
    if ( v104 )
    {
      if ( _InterlockedExchangeAdd(v104 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v79)(v79);
        if ( _InterlockedExchangeAdd(v79 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v79 + 8LL))(v79);
      }
    }
LABEL_120:
    std::string::_Tidy_deallocate(v112);
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
        v107 = (__int64)"1507.2603.28012.0";
        v14 = (_QWORD *)SystemInterface::Providers::GetSystem(v105);
        v15 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v14 + 40LL))(*v14, v103);
        v16 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v15 + 440LL))(*v15, v112);
        if ( v16[3] > 7u )
          v16 = (_QWORD *)*v16;
        v94 = (__int64)v16;
        v17 = (_QWORD *)(*(__int64 (__fastcall **)(struct SystemInterface::Telemetry::CorrelationVector *, _BYTE *))(*(_QWORD *)a2 + 8LL))(
                          a2,
                          v114);
        if ( v17[3] > 0xFu )
          v17 = (_QWORD *)*v17;
        v95 = (__int64)v17;
        v18 = SystemInterface::Providers::GetSystem(v110);
        v19 = *(_QWORD *)v18 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v18 + 8LL) + 4LL);
        v20 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v19 + 8LL))(v19, v108);
        v96 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 104LL))(*v20)
            - (unsigned __int64)*((unsigned int *)this + 88);
        v85 = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 42) + 8LL))(
                                *((_QWORD *)this + 42),
                                &v84)
            / 60000000;
        v97 = (__int64)a3;
        v98 = (__int64)L"[]";
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
        v99 = (__int64)v23;
        v100 = *((_QWORD *)v10 + 15);
        v101 = *((_QWORD *)v10 + 14);
        v86 = v10[26];
        v102 = *((_QWORD *)v10 + 12);
        v92 = *((_QWORD *)v10 + 11);
        v87 = v10[20];
        v93 = *((_QWORD *)v10 + 9);
        v88 = v10[8];
        v91 = *((_QWORD *)v10 + 3);
        v81 = *v10;
        v83 = *((_QWORD *)v10 + 16);
        CurrentThreadId = v10[16];
        v84 = *((_QWORD *)v10 + 7);
        LODWORD(SRWLock) = v10[2];
        v89 = 0x1000000;
        v90 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          v13,
          (int)&byte_1404A34D7,
          *(_DWORD *)v7 + 8,
          (__int64)&v90,
          (__int64)&v89,
          (__int64)&SRWLock,
          (__int64)&v84,
          (__int64)&CurrentThreadId,
          (__int64)&v83,
          (__int64)&v81,
          (__int64)&v91,
          (__int64)&v88,
          (__int64)&v93,
          (__int64)&v87,
          (__int64)&v92,
          (__int64)&v102,
          (__int64)&v86,
          (__int64)&v101,
          (__int64)&v100,
          (__int64)&v99,
          (__int64)&v98,
          (__int64)&v97,
          (__int64)&v85,
          (__int64)&v96,
          (__int64)&v95,
          (__int64)&v94,
          (__int64)&v107);
        v24 = v109;
        if ( v109 )
        {
          if ( _InterlockedExchangeAdd(v109 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
            if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
          }
        }
        v25 = v111;
        if ( v111 )
        {
          if ( _InterlockedExchangeAdd(v111 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
            if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          }
        }
        std::string::_Tidy_deallocate(v114);
        std::wstring::~wstring(v112);
        v26 = v104;
        if ( v104 )
        {
          if ( _InterlockedExchangeAdd(v104 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
            if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
          }
        }
        v27 = v106;
LABEL_88:
        if ( v27 )
        {
          if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
            if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
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
  v28 = *v11;
  v29 = 2;
  *v28 = 2;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v30 = Windows::WU::Telemetry::WuProvider::Provider();
  v83 = (__int64)v30;
  if ( *(_DWORD *)v30 > 5u
    && (*((_QWORD *)v30 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v30 + 3) & 0x400000000000LL) == *((_QWORD *)v30 + 3) )
  {
    v31 = (_QWORD *)SystemInterface::Providers::GetSystem(v108);
    v32 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v31 + 40LL))(*v31, v110);
    v33 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v32 + 440LL))(*v32, v114);
    v34 = (const OLECHAR *)v33;
    if ( *(_QWORD *)(v33 + 24) > 7u )
      v34 = *(const OLECHAR **)v33;
    v35 = (*(__int64 (__fastcall **)(struct SystemInterface::Telemetry::CorrelationVector *, _BYTE *))(*(_QWORD *)a2 + 8LL))(
            a2,
            v112);
    v36 = (const CHAR *)v35;
    if ( *(_QWORD *)(v35 + 24) > 0xFu )
      v36 = *(const CHAR **)v35;
    v37 = SystemInterface::Providers::GetSystem(v103);
    v38 = *(_QWORD *)v37 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v37 + 8LL) + 4LL);
    v39 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v38 + 8LL))(v38, v105);
    v90 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v39 + 104LL))(*v39)
        - (unsigned __int64)*((unsigned int *)this + 88);
    LODWORD(SRWLock) = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 42) + 8LL))(
                                         *((_QWORD *)this + 42),
                                         &v91)
                     / 60000000;
    v40 = qword_140549FC0;
    v41 = *(_QWORD *)(qword_140549FC0 + 8);
    for ( i = 0; !*(_BYTE *)(v41 + 25); v41 = *(_QWORD *)v41 )
    {
      if ( *(_DWORD *)(v41 + 32) >= *((_DWORD *)this + 82) )
        v40 = v41;
      else
        v41 += 16;
    }
    if ( *(_BYTE *)(v40 + 25) || *((_DWORD *)this + 82) < *(_DWORD *)(v40 + 32) )
      std::_Xout_of_range("invalid map<K, T> key");
    v42 = (const OLECHAR *)(v40 + 64);
    if ( *((_QWORD *)v42 + 3) > 7u )
      v42 = *(const OLECHAR **)v42;
    CurrentThreadId = GetCurrentThreadId();
    v43 = *(_QWORD *)v7;
    v81 = *(_DWORD *)(*(_QWORD *)v7 + 72LL);
    v84 = 0x1000000;
    v140 = "1507.2603.28012.0";
    v141 = 18;
    if ( v34 )
    {
      v44 = -1;
      do
        ++v44;
      while ( v34[v44] );
      v45 = 2 * v44 + 2;
    }
    else
    {
      v34 = &psz;
      v45 = 2;
    }
    v137 = v34;
    v138 = v45;
    v139 = 0;
    if ( v36 )
    {
      v46 = -1;
      do
        ++v46;
      while ( v36[v46] );
      v47 = v46 + 1;
    }
    else
    {
      v36 = &pszCabPath;
      v47 = 1;
    }
    v134 = v36;
    v135 = v47;
    v136 = 0;
    v132 = &v90;
    v133 = 8;
    p_SRWLock = &SRWLock;
    v131 = 4;
    v48 = (const OLECHAR *)v89;
    if ( v89 )
    {
      v49 = -1;
      do
        ++v49;
      while ( *(_WORD *)(v89 + 2 * v49) );
      v50 = 2 * v49 + 2;
    }
    else
    {
      v48 = &psz;
      v50 = 2;
    }
    v127 = v48;
    v128 = v50;
    v129 = 0;
    v125 = L"[]";
    v126 = 6;
    if ( v42 )
    {
      v51 = -1;
      do
        ++v51;
      while ( v42[v51] );
      v29 = 2 * v51 + 2;
    }
    else
    {
      v42 = &psz;
    }
    v122 = v42;
    v123 = v29;
    v124 = 0;
    p_CurrentThreadId = &CurrentThreadId;
    v121 = 4;
    v118 = &v81;
    v119 = 4;
    v116 = &v84;
    v117 = 8;
    tlgWriteTransfer_EventWriteTransfer(v83, (int)&word_1404A3662, v43 + 8, 0, 0xDu, &v115);
    v52 = v106;
    if ( v106 )
    {
      if ( _InterlockedExchangeAdd(v106 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
        if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
      }
    }
    v53 = v104;
    if ( v104 )
    {
      if ( _InterlockedExchangeAdd(v104 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
        if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
      }
    }
    std::string::_Tidy_deallocate(v112);
    std::wstring::~wstring(v114);
    v54 = v111;
    if ( v111 )
    {
      if ( _InterlockedExchangeAdd(v111 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
        if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
      }
    }
    v27 = v109;
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
