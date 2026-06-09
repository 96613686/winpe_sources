# Windows::WU::Telemetry::WuProvider::Scan::Stop(SystemInterface::Telemetry::CorrelationVector &,wchar_t const *)

- ea: `0x1402cb020`
- end: `0x1402cbcf3`
- name: `?Stop@Scan@WuProvider@Telemetry@WU@Windows@@QEAAXAEAVCorrelationVector@3SystemInterface@@PEB_W@Z`
- size: `3283`
- prototype: `void __fastcall(Windows::WU::Telemetry::WuProvider::Scan *__hidden this, struct SystemInterface::Telemetry::CorrelationVector *, const wchar_t *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1402d2fd0`

## callees

- `0x140014774`
- `0x140014b7c`
- `0x140014d4c`
- `0x140015118`
- `0x14002a7d8`
- `0x14002b5f0`
- `0x14002cc08`
- `0x140044f20`
- `0x140045404`
- `0x14012d7d8`
- `0x1402ca644`
- `0x1402cb020`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402cb602`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402cbbc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402cb602`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402cbbc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cb0b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cb4be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cb7ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cbacb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cb0b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cb4be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cb7ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cbacb`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall Windows::WU::Telemetry::WuProvider::Scan::Stop(
        Windows::WU::Telemetry::WuProvider::Scan *this,
        struct SystemInterface::Telemetry::CorrelationVector *a2,
        const wchar_t *a3)
{
  char IsEnabled; // al
  char *v7; // rdi
  int *v8; // rdx
  int v9; // ecx
  int *v10; // r15
  _DWORD **v11; // r14
  const struct _tlgProvider_t *v12; // rax
  int v13; // r14d
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  _QWORD *v20; // rax
  volatile signed __int32 *v21; // rdi
  volatile signed __int32 *v22; // rdi
  __int64 v23; // rdx
  volatile signed __int32 *v24; // rdi
  volatile signed __int32 *v25; // rdi
  const struct _tlgProvider_t *v26; // rax
  int v27; // r14d
  _QWORD *v28; // rax
  _QWORD *v29; // rax
  _QWORD *v30; // rax
  _QWORD *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rcx
  _QWORD *v34; // rax
  __int64 v35; // r8
  volatile signed __int32 *v36; // rdi
  volatile signed __int32 *v37; // rdi
  __int64 v38; // rdx
  volatile signed __int32 *v39; // rdi
  int *v40; // r15
  _DWORD **v41; // r14
  const struct _tlgProvider_t *v42; // rax
  int v43; // r14d
  _QWORD *v44; // rax
  __int64 System; // rax
  __int64 v46; // rcx
  _QWORD *v47; // rax
  volatile signed __int32 *v48; // rdi
  volatile signed __int32 *v49; // rdi
  const struct _tlgProvider_t *v50; // rax
  int v51; // r14d
  _QWORD *v52; // rax
  __int64 v53; // rax
  __int64 v54; // rcx
  _QWORD *v55; // rax
  _DWORD *v56; // r8
  volatile signed __int32 *v57; // rdi
  volatile signed __int32 *v58; // rdi
  PSRWLOCK SRWLock; // [rsp+E0h] [rbp-80h] BYREF
  int v60; // [rsp+E8h] [rbp-78h] BYREF
  DWORD CurrentThreadId; // [rsp+ECh] [rbp-74h] BYREF
  __int64 v62; // [rsp+F0h] [rbp-70h] BYREF
  __int64 v63; // [rsp+F8h] [rbp-68h] BYREF
  __int64 v64; // [rsp+100h] [rbp-60h] BYREF
  int v65; // [rsp+108h] [rbp-58h] BYREF
  int v66; // [rsp+10Ch] [rbp-54h] BYREF
  int v67; // [rsp+110h] [rbp-50h] BYREF
  int v68; // [rsp+114h] [rbp-4Ch] BYREF
  __int64 v69; // [rsp+118h] [rbp-48h] BYREF
  __int64 v70; // [rsp+120h] [rbp-40h] BYREF
  __int64 v71; // [rsp+128h] [rbp-38h] BYREF
  __int64 v72; // [rsp+130h] [rbp-30h] BYREF
  __int64 v73; // [rsp+138h] [rbp-28h] BYREF
  __int64 v74; // [rsp+140h] [rbp-20h] BYREF
  __int64 v75; // [rsp+148h] [rbp-18h] BYREF
  __int64 v76; // [rsp+150h] [rbp-10h] BYREF
  __int64 v77; // [rsp+158h] [rbp-8h] BYREF
  __int64 v78; // [rsp+160h] [rbp+0h] BYREF
  __int64 v79; // [rsp+168h] [rbp+8h] BYREF
  __int64 v80; // [rsp+170h] [rbp+10h] BYREF
  _BYTE v81[8]; // [rsp+178h] [rbp+18h] BYREF
  volatile signed __int32 *v82; // [rsp+180h] [rbp+20h]
  _BYTE v83[8]; // [rsp+188h] [rbp+28h] BYREF
  volatile signed __int32 *v84; // [rsp+190h] [rbp+30h]
  __int64 v85; // [rsp+198h] [rbp+38h] BYREF
  _BYTE v86[8]; // [rsp+1A0h] [rbp+40h] BYREF
  volatile signed __int32 *v87; // [rsp+1A8h] [rbp+48h]
  _BYTE v88[8]; // [rsp+1B0h] [rbp+50h] BYREF
  volatile signed __int32 *v89; // [rsp+1B8h] [rbp+58h]
  _BYTE v90[32]; // [rsp+1C0h] [rbp+60h] BYREF
  _BYTE v91[32]; // [rsp+1E0h] [rbp+80h] BYREF

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl);
  v7 = (char *)this + 272;
  v8 = (int *)*((_QWORD *)this + 34);
  v9 = v8[18];
  if ( !IsEnabled )
  {
    if ( v9 < 0 && (v40 = v8 + 20, v9 == v8[22]) )
    {
      v41 = (_DWORD **)((char *)this + 272);
      if ( v8 != (int *)-80LL )
      {
        SRWLock = 0;
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
          this,
          &SRWLock);
        **(_DWORD **)v7 = 2;
        if ( SRWLock )
          ReleaseSRWLockExclusive(SRWLock);
        v42 = Windows::WU::Telemetry::WuProvider::Provider();
        v43 = (int)v42;
        if ( *(_DWORD *)v42 <= 5u
          || (*((_QWORD *)v42 + 2) & 0x400000000000LL) == 0
          || (*((_QWORD *)v42 + 3) & 0x400000000000LL) != *((_QWORD *)v42 + 3) )
        {
          goto LABEL_90;
        }
        v71 = (__int64)"1507.2603.28012.0";
        v44 = (_QWORD *)(*(__int64 (__fastcall **)(struct SystemInterface::Telemetry::CorrelationVector *, _BYTE *))(*(_QWORD *)a2 + 8LL))(
                          a2,
                          v90);
        if ( v44[3] > 0xFu )
          v44 = (_QWORD *)*v44;
        v70 = (__int64)v44;
        System = SystemInterface::Providers::GetSystem(v81);
        v46 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
        v47 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v46 + 8LL))(v46, v83);
        v64 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v47 + 104LL))(*v47)
            - (unsigned __int64)*((unsigned int *)this + 86);
        LODWORD(SRWLock) = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 41) + 8LL))(
                                             *((_QWORD *)this + 41),
                                             &v62)
                         / 60000000;
        v62 = (__int64)a3;
        v63 = (__int64)L"[]";
        v69 = *((_QWORD *)v40 + 15);
        v72 = *((_QWORD *)v40 + 14);
        CurrentThreadId = v40[26];
        v80 = *((_QWORD *)v40 + 12);
        v79 = *((_QWORD *)v40 + 11);
        v60 = v40[20];
        v78 = *((_QWORD *)v40 + 9);
        v68 = v40[8];
        v77 = *((_QWORD *)v40 + 3);
        v67 = *v40;
        v76 = *((_QWORD *)v40 + 16);
        v66 = v40[16];
        v75 = *((_QWORD *)v40 + 7);
        v65 = v40[2];
        v74 = 0x1000000;
        v73 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v43,
          (int)&byte_1404A3E61,
          *(_DWORD *)v7 + 8,
          (__int64)&v73,
          (__int64)&v74,
          (__int64)&v65,
          (__int64)&v75,
          (__int64)&v66,
          (__int64)&v76,
          (__int64)&v67,
          (__int64)&v77,
          (__int64)&v68,
          (__int64)&v78,
          (__int64)&v60,
          (__int64)&v79,
          (__int64)&v80,
          (__int64)&CurrentThreadId,
          (__int64)&v72,
          (__int64)&v69,
          (__int64)&v63,
          (__int64)&v62,
          (__int64)&SRWLock,
          (__int64)&v64,
          (__int64)&v70,
          (__int64)&v71);
        v48 = v84;
        if ( v84 )
        {
          if ( _InterlockedExchangeAdd(v84 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
            if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
          }
        }
        v49 = v82;
        if ( v82 )
        {
          if ( _InterlockedExchangeAdd(v82 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
            if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
          }
        }
        goto LABEL_89;
      }
    }
    else
    {
      v41 = (_DWORD **)((char *)this + 272);
    }
    SRWLock = 0;
    wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **v41 = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v50 = Windows::WU::Telemetry::WuProvider::Provider();
    v51 = (int)v50;
    if ( *(_DWORD *)v50 <= 5u
      || (*((_QWORD *)v50 + 2) & 0x400000000000LL) == 0
      || (*((_QWORD *)v50 + 3) & 0x400000000000LL) != *((_QWORD *)v50 + 3) )
    {
      goto LABEL_90;
    }
    v71 = (__int64)"1507.2603.28012.0";
    v52 = (_QWORD *)(*(__int64 (__fastcall **)(struct SystemInterface::Telemetry::CorrelationVector *, _BYTE *))(*(_QWORD *)a2 + 8LL))(
                      a2,
                      v90);
    if ( v52[3] > 0xFu )
      v52 = (_QWORD *)*v52;
    v70 = (__int64)v52;
    v53 = SystemInterface::Providers::GetSystem(v81);
    v54 = *(_QWORD *)v53 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v53 + 8LL) + 4LL);
    v55 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v54 + 8LL))(v54, v83);
    v64 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v55 + 104LL))(*v55)
        - (unsigned __int64)*((unsigned int *)this + 86);
    LODWORD(SRWLock) = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 41) + 8LL))(
                                    *((_QWORD *)this + 41),
                                    &v62)
                     / 60000000LL;
    v62 = (__int64)a3;
    v63 = (__int64)L"[]";
    CurrentThreadId = GetCurrentThreadId();
    v56 = *(_DWORD **)v7;
    v60 = *(_DWORD *)(*(_QWORD *)v7 + 72LL);
    v69 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v51,
      (int)&byte_1404A3FD3,
      (_DWORD)v56 + 8,
      (__int64)&v69,
      (__int64)&v60,
      (__int64)&CurrentThreadId,
      (__int64)&v63,
      (__int64)&v62,
      (__int64)&SRWLock,
      (__int64)&v64,
      (__int64)&v70,
      (__int64)&v71);
    v57 = v84;
    if ( v84 )
    {
      if ( _InterlockedExchangeAdd(v84 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
        if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
      }
    }
    v58 = v82;
    if ( v82 )
    {
      if ( _InterlockedExchangeAdd(v82 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
        if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
      }
    }
LABEL_89:
    std::string::_Tidy_deallocate(v90);
    goto LABEL_90;
  }
  if ( v9 < 0 && (v10 = v8 + 20, v9 == v8[22]) )
  {
    v11 = (_DWORD **)((char *)this + 272);
    if ( v8 != (int *)-80LL )
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
        v85 = (__int64)"1507.2603.28012.0";
        v14 = (_QWORD *)SystemInterface::Providers::GetSystem(v83);
        v15 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v14 + 40LL))(*v14, v81);
        v16 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v15 + 440LL))(*v15, v90);
        if ( v16[3] > 7u )
          v16 = (_QWORD *)*v16;
        v73 = (__int64)v16;
        v17 = (_QWORD *)(*(__int64 (__fastcall **)(struct SystemInterface::Telemetry::CorrelationVector *, _BYTE *))(*(_QWORD *)a2 + 8LL))(
                          a2,
                          v91);
        if ( v17[3] > 0xFu )
          v17 = (_QWORD *)*v17;
        v74 = (__int64)v17;
        v18 = SystemInterface::Providers::GetSystem(v88);
        v19 = *(_QWORD *)v18 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v18 + 8LL) + 4LL);
        v20 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v19 + 8LL))(v19, v86);
        v75 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 104LL))(*v20)
            - (unsigned __int64)*((unsigned int *)this + 86);
        v65 = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 41) + 8LL))(
                                *((_QWORD *)this + 41),
                                &v64)
            / 60000000;
        v76 = (__int64)a3;
        v77 = (__int64)L"[]";
        v78 = *((_QWORD *)v10 + 15);
        v79 = *((_QWORD *)v10 + 14);
        v66 = v10[26];
        v80 = *((_QWORD *)v10 + 12);
        v72 = *((_QWORD *)v10 + 11);
        v67 = v10[20];
        v69 = *((_QWORD *)v10 + 9);
        v68 = v10[8];
        v63 = *((_QWORD *)v10 + 3);
        v60 = *v10;
        v62 = *((_QWORD *)v10 + 16);
        CurrentThreadId = v10[16];
        v64 = *((_QWORD *)v10 + 7);
        LODWORD(SRWLock) = v10[2];
        v70 = 0x1000000;
        v71 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          v13,
          (int)&byte_1404A424F,
          *(_DWORD *)v7 + 8,
          (__int64)&v71,
          (__int64)&v70,
          (__int64)&SRWLock,
          (__int64)&v64,
          (__int64)&CurrentThreadId,
          (__int64)&v62,
          (__int64)&v60,
          (__int64)&v63,
          (__int64)&v68,
          (__int64)&v69,
          (__int64)&v67,
          (__int64)&v72,
          (__int64)&v80,
          (__int64)&v66,
          (__int64)&v79,
          (__int64)&v78,
          (__int64)&v77,
          (__int64)&v76,
          (__int64)&v65,
          (__int64)&v75,
          (__int64)&v74,
          (__int64)&v73,
          (__int64)&v85);
        v21 = v87;
        if ( v87 )
        {
          if ( _InterlockedExchangeAdd(v87 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
            if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
          }
        }
        v22 = v89;
        if ( v89 )
        {
          if ( _InterlockedExchangeAdd(v89 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
            if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
          }
        }
        std::string::_Tidy_deallocate(v91);
        std::wstring::~wstring(v90, v23);
        v24 = v82;
        if ( v82 )
        {
          if ( _InterlockedExchangeAdd(v82 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
            if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
          }
        }
        v25 = v84;
LABEL_27:
        if ( v25 )
        {
          if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
            if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          }
        }
        goto LABEL_90;
      }
      goto LABEL_90;
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
  **v11 = 2;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v26 = Windows::WU::Telemetry::WuProvider::Provider();
  v27 = (int)v26;
  if ( *(_DWORD *)v26 > 5u
    && (*((_QWORD *)v26 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v26 + 3) & 0x400000000000LL) == *((_QWORD *)v26 + 3) )
  {
    v71 = (__int64)"1507.2603.28012.0";
    v28 = (_QWORD *)SystemInterface::Providers::GetSystem(v86);
    v29 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v28 + 40LL))(*v28, v88);
    v30 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v29 + 440LL))(*v29, v91);
    if ( v30[3] > 7u )
      v30 = (_QWORD *)*v30;
    v70 = (__int64)v30;
    v31 = (_QWORD *)(*(__int64 (__fastcall **)(struct SystemInterface::Telemetry::CorrelationVector *, _BYTE *))(*(_QWORD *)a2 + 8LL))(
                      a2,
                      v90);
    if ( v31[3] > 0xFu )
      v31 = (_QWORD *)*v31;
    v64 = (__int64)v31;
    v32 = SystemInterface::Providers::GetSystem(v81);
    v33 = *(_QWORD *)v32 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v32 + 8LL) + 4LL);
    v34 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v33 + 8LL))(v33, v83);
    v62 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v34 + 104LL))(*v34)
        - (unsigned __int64)*((unsigned int *)this + 86);
    LODWORD(SRWLock) = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 41) + 8LL))(
                                    *((_QWORD *)this + 41),
                                    &v63)
                     / 60000000LL;
    v63 = (__int64)a3;
    v69 = (__int64)L"[]";
    CurrentThreadId = GetCurrentThreadId();
    v35 = *(_QWORD *)v7;
    v60 = *(_DWORD *)(*(_QWORD *)v7 + 72LL);
    v72 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
      v27,
      (int)&word_1404A43CA,
      v35 + 8,
      (__int64)&v72,
      (__int64)&v60,
      (__int64)&CurrentThreadId,
      (__int64)&v69,
      (__int64)&v63,
      (__int64)&SRWLock,
      (__int64)&v62,
      (__int64)&v64,
      (__int64)&v70,
      (__int64)&v71);
    v36 = v84;
    if ( v84 )
    {
      if ( _InterlockedExchangeAdd(v84 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
        if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
      }
    }
    v37 = v82;
    if ( v82 )
    {
      if ( _InterlockedExchangeAdd(v82 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
        if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
      }
    }
    std::string::_Tidy_deallocate(v90);
    std::wstring::~wstring(v91, v38);
    v39 = v89;
    if ( v89 )
    {
      if ( _InterlockedExchangeAdd(v89 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
        if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
      }
    }
    v25 = v87;
    goto LABEL_27;
  }
LABEL_90:
  wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x1402cb020  mov     [rsp-8+arg_10], rbx
0x1402cb025  mov     [rsp-8+arg_18], rsi
0x1402cb02a  push    rbp
0x1402cb02b  push    rdi
0x1402cb02c  push    r12
0x1402cb02e  push    r14
0x1402cb030  push    r15
0x1402cb032  lea     rbp, [rsp-0A0h]
0x1402cb03a  sub     rsp, 200h
0x1402cb041  mov     r12, r8
0x1402cb044  mov     rbx, rdx
0x1402cb047  mov     rsi, rcx
0x1402cb04a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections> `wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl(void)'::`2'::impl
0x1402cb051  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(void)
0x1402cb056  lea     rdi, [rsi+110h]
0x1402cb05d  mov     rdx, [rdi]
0x1402cb060  mov     ecx, [rdx+48h]
0x1402cb063  test    al, al
0x1402cb065  jz      loc_1402CB766
0x1402cb06b  test    ecx, ecx
0x1402cb06d  jns     loc_1402CB495
0x1402cb073  lea     r15, [rdx+50h]
0x1402cb077  cmp     ecx, [r15+8]
0x1402cb07b  jnz     loc_1402CB495
0x1402cb081  mov     r14, rdi
0x1402cb084  test    r15, r15
0x1402cb087  jz      loc_1402CB498
0x1402cb08d  mov     [rbp+0C0h+SRWLock], 0
0x1402cb095  lea     rdx, [rbp+0C0h+SRWLock]
0x1402cb099  mov     rcx, rsi
0x1402cb09c  call    ?LockExclusive@?$ActivityBase@VBaseCore@Telemetry@Windows@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1402cb0a1  mov     rax, [rdi]
0x1402cb0a4  mov     dword ptr [rax], 2
0x1402cb0aa  mov     rcx, [rbp+0C0h+SRWLock]; SRWLock
0x1402cb0ae  test    rcx, rcx
0x1402cb0b1  jz      short loc_1402CB0B9
0x1402cb0b3  call    cs:__imp_ReleaseSRWLockExclusive
0x1402cb0b9  call    ?Provider@WuProvider@Telemetry@WU@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::WU::Telemetry::WuProvider::Provider(void)
0x1402cb0be  mov     r14, rax
0x1402cb0c1  cmp     dword ptr [rax], 5
0x1402cb0c4  jbe     loc_1402CBCD0
0x1402cb0ca  mov     rdx, 400000000000h
0x1402cb0d4  test    [rax+10h], rdx
0x1402cb0d8  jz      loc_1402CBCD0
0x1402cb0de  mov     rcx, [rax+18h]
0x1402cb0e2  and     rcx, rdx
0x1402cb0e5  cmp     rcx, [rax+18h]
0x1402cb0e9  jnz     loc_1402CBCD0
0x1402cb0ef  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1402cb0f6  mov     [rbp+0C0h+var_88], rax
0x1402cb0fa  lea     rcx, [rbp+0C0h+var_98]
0x1402cb0fe  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1402cb103  nop
0x1402cb104  mov     rcx, [rax]
0x1402cb107  mov     rax, [rcx]
0x1402cb10a  lea     rdx, [rbp+0C0h+var_A8]
0x1402cb10e  mov     rax, [rax+28h]
0x1402cb112  call    _guard_dispatch_icall
0x1402cb117  nop
0x1402cb118  mov     rcx, [rax]
0x1402cb11b  mov     rax, [rcx]
0x1402cb11e  lea     rdx, [rbp+0C0h+var_60]
0x1402cb122  mov     rax, [rax+1B8h]
0x1402cb129  call    _guard_dispatch_icall
0x1402cb12e  nop
0x1402cb12f  cmp     qword ptr [rax+18h], 7
0x1402cb134  jbe     short loc_1402CB139
0x1402cb136  mov     rax, [rax]
0x1402cb139  mov     [rbp+0C0h+var_E8], rax
0x1402cb13d  mov     rax, [rbx]
0x1402cb140  lea     rdx, [rbp+0C0h+var_40]
0x1402cb147  mov     rcx, rbx
0x1402cb14a  mov     rax, [rax+8]
0x1402cb14e  call    _guard_dispatch_icall
0x1402cb153  nop
0x1402cb154  cmp     qword ptr [rax+18h], 0Fh
0x1402cb159  jbe     short loc_1402CB15E
0x1402cb15b  mov     rax, [rax]
0x1402cb15e  mov     [rbp+0C0h+var_E0], rax
0x1402cb162  lea     rcx, [rbp+0C0h+var_70]
0x1402cb166  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1402cb16b  nop
0x1402cb16c  mov     rdx, [rax]
0x1402cb16f  mov     rax, [rdx+8]
0x1402cb173  movsxd  rcx, dword ptr [rax+4]
0x1402cb177  add     rdx, 8
0x1402cb17b  add     rcx, rdx
0x1402cb17e  mov     rax, [rcx]
0x1402cb181  lea     rdx, [rbp+0C0h+var_80]
0x1402cb185  mov     rax, [rax+8]
0x1402cb189  call    _guard_dispatch_icall
0x1402cb18e  nop
0x1402cb18f  mov     rcx, [rax]
0x1402cb192  mov     rax, [rcx]
0x1402cb195  mov     rax, [rax+68h]
0x1402cb199  call    _guard_dispatch_icall
0x1402cb19e  mov     ecx, eax
0x1402cb1a0  mov     eax, [rsi+158h]
0x1402cb1a6  sub     rcx, rax
0x1402cb1a9  mov     [rbp+0C0h+var_D8], rcx
0x1402cb1ad  mov     rcx, [rsi+148h]
0x1402cb1b4  mov     rax, [rcx]
0x1402cb1b7  lea     rdx, [rbp+0C0h+var_120]
0x1402cb1bb  mov     rax, [rax+8]
0x1402cb1bf  call    _guard_dispatch_icall
0x1402cb1c4  mov     rcx, [rax]
0x1402cb1c7  mov     rax, 8F2A633943A6D729h
0x1402cb1d1  imul    rcx
0x1402cb1d4  add     rdx, rcx
0x1402cb1d7  sar     rdx, 19h
0x1402cb1db  mov     rax, rdx
0x1402cb1de  shr     rax, 3Fh
0x1402cb1e2  add     rdx, rax
0x1402cb1e5  mov     dword ptr [rbp+0C0h+var_118], edx
0x1402cb1e8  mov     [rbp+0C0h+var_D0], r12
0x1402cb1ec  lea     rax, asc_14047AB74; "[]"
0x1402cb1f3  mov     [rbp+0C0h+var_C8], rax
0x1402cb1f7  mov     rax, [r15+78h]
0x1402cb1fb  mov     [rbp+0C0h+var_C0], rax
0x1402cb1ff  mov     rax, [r15+70h]
0x1402cb203  mov     [rbp+0C0h+var_B8], rax
0x1402cb207  mov     eax, [r15+68h]
0x1402cb20b  mov     dword ptr [rbp+0C0h+var_118+4], eax
0x1402cb20e  mov     rax, [r15+60h]
0x1402cb212  mov     [rbp+0C0h+var_B0], rax
0x1402cb216  mov     rax, [r15+58h]
0x1402cb21a  mov     [rbp+0C0h+var_F0], rax
0x1402cb21e  mov     eax, [r15+50h]
0x1402cb222  mov     dword ptr [rbp+0C0h+var_110], eax
0x1402cb225  mov     rax, [r15+48h]
0x1402cb229  mov     [rbp+0C0h+var_108], rax
0x1402cb22d  mov     eax, [r15+20h]
0x1402cb231  mov     dword ptr [rbp+0C0h+var_110+4], eax
0x1402cb234  mov     rax, [r15+18h]
0x1402cb238  mov     [rbp+0C0h+var_128], rax
0x1402cb23c  mov     eax, [r15]
0x1402cb23f  mov     dword ptr [rbp+0C0h+var_138], eax
0x1402cb242  mov     rax, [r15+80h]
0x1402cb249  mov     [rbp+0C0h+var_130], rax
0x1402cb24d  mov     eax, [r15+40h]
0x1402cb251  mov     dword ptr [rbp+0C0h+var_138+4], eax
0x1402cb254  mov     rax, [r15+38h]
0x1402cb258  mov     [rbp+0C0h+var_120], rax
0x1402cb25c  mov     eax, [r15+8]
0x1402cb260  mov     dword ptr [rbp+0C0h+SRWLock], eax
0x1402cb263  mov     eax, 1000000h
0x1402cb268  mov     [rbp+0C0h+var_100], rax
0x1402cb26c  mov     [rbp+0C0h+var_F8], rax
0x1402cb270  mov     r8, [rdi]
0x1402cb273  add     r8, 8; int
0x1402cb277  lea     rax, [rbp+0C0h+var_88]
0x1402cb27b  mov     [rsp+220h+var_150], rax; __int64
0x1402cb283  lea     rax, [rbp+0C0h+var_E8]
0x1402cb287  mov     [rsp+220h+var_158], rax; __int64
0x1402cb28f  lea     rax, [rbp+0C0h+var_E0]
0x1402cb293  mov     [rsp+220h+var_160], rax; __int64
0x1402cb29b  lea     rax, [rbp+0C0h+var_D8]
0x1402cb29f  mov     [rsp+220h+var_168], rax; __int64
0x1402cb2a7  lea     rax, [rbp+0C0h+var_118]
0x1402cb2ab  mov     [rsp+220h+var_170], rax; __int64
0x1402cb2b3  lea     rax, [rbp+0C0h+var_D0]
0x1402cb2b7  mov     [rsp+220h+var_178], rax; __int64
0x1402cb2bf  lea     rax, [rbp+0C0h+var_C8]
0x1402cb2c3  mov     [rsp+220h+var_180], rax; __int64
0x1402cb2cb  lea     rax, [rbp+0C0h+var_C0]
0x1402cb2cf  mov     [rsp+220h+var_188], rax; __int64
0x1402cb2d7  lea     rax, [rbp+0C0h+var_B8]
0x1402cb2db  mov     [rsp+220h+var_190], rax; __int64
0x1402cb2e3  lea     rax, [rbp+0C0h+var_118+4]
0x1402cb2e7  mov     [rsp+220h+var_198], rax; __int64
0x1402cb2ef  lea     rax, [rbp+0C0h+var_B0]
0x1402cb2f3  mov     [rsp+220h+var_1A0], rax; __int64
0x1402cb2fb  lea     rax, [rbp+0C0h+var_F0]
0x1402cb2ff  mov     [rsp+220h+var_1A8], rax; __int64
0x1402cb304  lea     rax, [rbp+0C0h+var_110]
0x1402cb308  mov     [rsp+220h+var_1B0], rax; __int64
0x1402cb30d  lea     rax, [rbp+0C0h+var_108]
0x1402cb311  mov     [rsp+220h+var_1B8], rax; __int64
0x1402cb316  lea     rax, [rbp+0C0h+var_110+4]
0x1402cb31a  mov     [rsp+220h+var_1C0], rax; __int64
0x1402cb31f  lea     rax, [rbp+0C0h+var_128]
0x1402cb323  mov     [rsp+220h+var_1C8], rax; __int64
0x1402cb328  lea     rax, [rbp+0C0h+var_138]
0x1402cb32c  mov     [rsp+220h+var_1D0], rax; __int64
0x1402cb331  lea     rax, [rbp+0C0h+var_130]
0x1402cb335  mov     [rsp+220h+var_1D8], rax; __int64
0x1402cb33a  lea     rax, [rbp+0C0h+var_138+4]
0x1402cb33e  mov     [rsp+220h+var_1E0], rax; __int64
0x1402cb343  lea     rax, [rbp+0C0h+var_120]
0x1402cb347  mov     [rsp+220h+var_1E8], rax; __int64
0x1402cb34c  lea     rax, [rbp+0C0h+SRWLock]
0x1402cb350  mov     [rsp+220h+var_1F0], rax; __int64
0x1402cb355  lea     rax, [rbp+0C0h+var_100]
0x1402cb359  mov     [rsp+220h+var_1F8], rax; __int64
0x1402cb35e  lea     rax, [rbp+0C0h+var_F8]
0x1402cb362  mov     [rsp+220h+var_200], rax; __int64
0x1402cb367  lea     rdx, byte_1404A424F; int
0x1402cb36e  mov     rcx, r14; int
0x1402cb371  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U2@U1@U3@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564566643565@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x1402cb376  nop
0x1402cb377  or      ebx, 0FFFFFFFFh
0x1402cb37a  mov     rdi, [rbp+0C0h+var_78]
0x1402cb37e  test    rdi, rdi
0x1402cb381  jz      short loc_1402CB3B7
0x1402cb383  mov     eax, ebx
0x1402cb385  lock xadd [rdi+8], eax
0x1402cb38a  add     eax, ebx
0x1402cb38c  jnz     short loc_1402CB3B7
0x1402cb38e  mov     rax, [rdi]
0x1402cb391  mov     rcx, rdi
0x1402cb394  mov     rax, [rax]
0x1402cb397  call    _guard_dispatch_icall
0x1402cb39c  mov     eax, ebx
0x1402cb39e  lock xadd [rdi+0Ch], eax
0x1402cb3a3  add     eax, ebx
0x1402cb3a5  jnz     short loc_1402CB3B7
0x1402cb3a7  mov     rax, [rdi]
0x1402cb3aa  mov     rcx, rdi
0x1402cb3ad  mov     rax, [rax+8]
0x1402cb3b1  call    _guard_dispatch_icall
0x1402cb3b6  nop
0x1402cb3b7  mov     rdi, [rbp+0C0h+var_68]
0x1402cb3bb  test    rdi, rdi
0x1402cb3be  jz      short loc_1402CB3F4
0x1402cb3c0  mov     eax, ebx
0x1402cb3c2  lock xadd [rdi+8], eax
0x1402cb3c7  add     eax, ebx
0x1402cb3c9  jnz     short loc_1402CB3F4
0x1402cb3cb  mov     rax, [rdi]
0x1402cb3ce  mov     rcx, rdi
0x1402cb3d1  mov     rax, [rax]
0x1402cb3d4  call    _guard_dispatch_icall
0x1402cb3d9  mov     eax, ebx
0x1402cb3db  lock xadd [rdi+0Ch], eax
0x1402cb3e0  add     eax, ebx
0x1402cb3e2  jnz     short loc_1402CB3F4
0x1402cb3e4  mov     rax, [rdi]
0x1402cb3e7  mov     rcx, rdi
0x1402cb3ea  mov     rax, [rax+8]
0x1402cb3ee  call    _guard_dispatch_icall
0x1402cb3f3  nop
0x1402cb3f4  lea     rcx, [rbp+0C0h+var_40]
0x1402cb3fb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1402cb400  nop
0x1402cb401  lea     rcx, [rbp+0C0h+var_60]
0x1402cb405  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402cb40a  nop
0x1402cb40b  mov     rdi, [rbp+0C0h+var_A0]
0x1402cb40f  test    rdi, rdi
0x1402cb412  jz      short loc_1402CB448
0x1402cb414  mov     eax, ebx
0x1402cb416  lock xadd [rdi+8], eax
0x1402cb41b  add     eax, ebx
0x1402cb41d  jnz     short loc_1402CB448
0x1402cb41f  mov     rax, [rdi]
0x1402cb422  mov     rcx, rdi
0x1402cb425  mov     rax, [rax]
0x1402cb428  call    _guard_dispatch_icall
0x1402cb42d  mov     eax, ebx
0x1402cb42f  lock xadd [rdi+0Ch], eax
0x1402cb434  add     eax, ebx
0x1402cb436  jnz     short loc_1402CB448
0x1402cb438  mov     rax, [rdi]
0x1402cb43b  mov     rcx, rdi
0x1402cb43e  mov     rax, [rax+8]
0x1402cb442  call    _guard_dispatch_icall
0x1402cb447  nop
0x1402cb448  mov     rdi, [rbp+0C0h+var_90]
0x1402cb44c  test    rdi, rdi
0x1402cb44f  jz      loc_1402CBCD0
0x1402cb455  mov     eax, ebx
0x1402cb457  lock xadd [rdi+8], eax
0x1402cb45c  add     eax, ebx
0x1402cb45e  jnz     loc_1402CBCD0
0x1402cb464  mov     rax, [rdi]
0x1402cb467  mov     rcx, rdi
0x1402cb46a  mov     rax, [rax]
0x1402cb46d  call    _guard_dispatch_icall
0x1402cb472  mov     eax, ebx
0x1402cb474  lock xadd [rdi+0Ch], eax
0x1402cb479  add     eax, ebx
0x1402cb47b  jnz     loc_1402CBCD0
0x1402cb481  mov     rax, [rdi]
0x1402cb484  mov     rcx, rdi
0x1402cb487  mov     rax, [rax+8]
0x1402cb48b  call    _guard_dispatch_icall
0x1402cb490  jmp     loc_1402CBCD0
0x1402cb495  mov     r14, rdi
0x1402cb498  mov     [rbp+0C0h+SRWLock], 0
0x1402cb4a0  lea     rdx, [rbp+0C0h+SRWLock]
0x1402cb4a4  mov     rcx, rsi
0x1402cb4a7  call    ?LockExclusive@?$ActivityBase@VBaseCore@Telemetry@Windows@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1402cb4ac  mov     rax, [r14]
0x1402cb4af  mov     dword ptr [rax], 2
0x1402cb4b5  mov     rcx, [rbp+0C0h+SRWLock]; SRWLock
0x1402cb4b9  test    rcx, rcx
0x1402cb4bc  jz      short loc_1402CB4C4
0x1402cb4be  call    cs:__imp_ReleaseSRWLockExclusive
0x1402cb4c4  call    ?Provider@WuProvider@Telemetry@WU@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::WU::Telemetry::WuProvider::Provider(void)
0x1402cb4c9  mov     r14, rax
  ... truncated ...
```
