# Windows::WU::Telemetry::WuProvider::Scan::Stop(SystemInterface::Telemetry::CorrelationVector &,std::vector<std::shared_ptr<Update>,std::allocator<std::shared_ptr<Update>>> const &)

- ea: `0x1402cbcfc`
- end: `0x1402cca5f`
- name: `?Stop@Scan@WuProvider@Telemetry@WU@Windows@@QEAAXAEAVCorrelationVector@3SystemInterface@@AEBV?$vector@V?$shared_ptr@VUpdate@@@std@@V?$allocator@V?$shared_ptr@VUpdate@@@std@@@2@@std@@@Z`
- size: `3427`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

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
- `0x1401cf4a4`
- `0x1402ca644`
- `0x1402cbcfc`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402cc31c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402cc933`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402cc31c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402cc933`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cbd89`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cc1bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cc4d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cc819`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cbd89`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cc1bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cc4d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402cc819`

## string_xrefs

- `0x1402cbebe`: `Completed`
- `0x1402cc2f1`: `Completed`
- `0x1402cc5c3`: `Completed`
- `0x1402cc908`: `Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall Windows::WU::Telemetry::WuProvider::Scan::Stop(__int64 a1, __int64 a2)
{
  char IsEnabled; // al
  __int64 *v5; // rdi
  __int64 v6; // r14
  int v7; // ecx
  int *v8; // r14
  _DWORD **v9; // r15
  const struct _tlgProvider_t *v10; // rax
  int v11; // r15d
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  _QWORD *v18; // rax
  _QWORD *v19; // rax
  __int64 v20; // rdx
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
  _QWORD *v35; // rax
  __int64 v36; // r8
  __int64 v37; // rdx
  volatile signed __int32 *v38; // rdi
  volatile signed __int32 *v39; // rdi
  __int64 v40; // rdx
  volatile signed __int32 *v41; // rdi
  int *v42; // r14
  _DWORD **v43; // r15
  const struct _tlgProvider_t *v44; // rax
  int v45; // r15d
  _QWORD *v46; // rax
  __int64 System; // rax
  __int64 v48; // rcx
  _QWORD *v49; // rax
  _QWORD *v50; // rax
  __int64 v51; // rdx
  volatile signed __int32 *v52; // rdi
  volatile signed __int32 *v53; // rdi
  const struct _tlgProvider_t *v54; // rax
  int v55; // r14d
  _QWORD *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rcx
  _QWORD *v59; // rax
  _QWORD *v60; // rax
  _DWORD *v61; // r8
  __int64 v62; // rdx
  volatile signed __int32 *v63; // rdi
  volatile signed __int32 *v64; // rdi
  PSRWLOCK SRWLock; // [rsp+E0h] [rbp-80h] BYREF
  int v67; // [rsp+E8h] [rbp-78h] BYREF
  DWORD CurrentThreadId; // [rsp+ECh] [rbp-74h] BYREF
  __int64 v69; // [rsp+F0h] [rbp-70h] BYREF
  __int64 v70; // [rsp+F8h] [rbp-68h] BYREF
  __int64 v71; // [rsp+100h] [rbp-60h] BYREF
  int v72; // [rsp+108h] [rbp-58h] BYREF
  int v73; // [rsp+10Ch] [rbp-54h] BYREF
  int v74; // [rsp+110h] [rbp-50h] BYREF
  int v75; // [rsp+114h] [rbp-4Ch] BYREF
  __int64 v76; // [rsp+118h] [rbp-48h] BYREF
  __int64 v77; // [rsp+120h] [rbp-40h] BYREF
  __int64 v78; // [rsp+128h] [rbp-38h] BYREF
  __int64 v79; // [rsp+130h] [rbp-30h] BYREF
  __int64 v80; // [rsp+138h] [rbp-28h] BYREF
  __int64 v81; // [rsp+140h] [rbp-20h] BYREF
  __int64 v82; // [rsp+148h] [rbp-18h] BYREF
  __int64 v83; // [rsp+150h] [rbp-10h] BYREF
  __int64 v84; // [rsp+158h] [rbp-8h] BYREF
  __int64 v85; // [rsp+160h] [rbp+0h] BYREF
  __int64 v86; // [rsp+168h] [rbp+8h] BYREF
  __int64 v87; // [rsp+170h] [rbp+10h] BYREF
  _BYTE v88[8]; // [rsp+178h] [rbp+18h] BYREF
  volatile signed __int32 *v89; // [rsp+180h] [rbp+20h]
  _BYTE v90[8]; // [rsp+188h] [rbp+28h] BYREF
  volatile signed __int32 *v91; // [rsp+190h] [rbp+30h]
  __int64 v92; // [rsp+198h] [rbp+38h] BYREF
  _BYTE v93[8]; // [rsp+1A0h] [rbp+40h] BYREF
  volatile signed __int32 *v94; // [rsp+1A8h] [rbp+48h]
  _BYTE v95[8]; // [rsp+1B0h] [rbp+50h] BYREF
  volatile signed __int32 *v96; // [rsp+1B8h] [rbp+58h]
  _BYTE v97[32]; // [rsp+1C0h] [rbp+60h] BYREF
  _BYTE v98[32]; // [rsp+1E0h] [rbp+80h] BYREF
  _BYTE Src[80]; // [rsp+200h] [rbp+A0h] BYREF

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl);
  v5 = (__int64 *)(a1 + 272);
  v6 = *(_QWORD *)(a1 + 272);
  v7 = *(_DWORD *)(v6 + 72);
  if ( !IsEnabled )
  {
    if ( v7 < 0 && (v42 = (int *)(v6 + 80), v7 == v42[2]) )
    {
      v43 = (_DWORD **)(a1 + 272);
      if ( v42 )
      {
        SRWLock = 0;
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
          a1,
          &SRWLock);
        *(_DWORD *)*v5 = 2;
        if ( SRWLock )
          ReleaseSRWLockExclusive(SRWLock);
        v44 = Windows::WU::Telemetry::WuProvider::Provider();
        v45 = (int)v44;
        if ( *(_DWORD *)v44 <= 5u
          || (*((_QWORD *)v44 + 2) & 0x400000000000LL) == 0
          || (*((_QWORD *)v44 + 3) & 0x400000000000LL) != *((_QWORD *)v44 + 3) )
        {
          return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
        }
        v78 = (__int64)"1507.2603.28012.0";
        v46 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v97);
        if ( v46[3] > 0xFu )
          v46 = (_QWORD *)*v46;
        v77 = (__int64)v46;
        System = SystemInterface::Providers::GetSystem(v88);
        v48 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
        v49 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v48 + 8LL))(v48, v90);
        v71 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v49 + 104LL))(*v49)
            - (unsigned __int64)*(unsigned int *)(a1 + 344);
        LODWORD(SRWLock) = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 328) + 8LL))(
                                             *(_QWORD *)(a1 + 328),
                                             &v69)
                         / 60000000;
        v69 = (__int64)L"Completed";
        v50 = (_QWORD *)Update::list_to_telemetry<std::vector<std::shared_ptr<Update>>>(v98);
        if ( v50[3] > 7u )
          v50 = (_QWORD *)*v50;
        v70 = (__int64)v50;
        v76 = *((_QWORD *)v42 + 15);
        v79 = *((_QWORD *)v42 + 14);
        CurrentThreadId = v42[26];
        v87 = *((_QWORD *)v42 + 12);
        v86 = *((_QWORD *)v42 + 11);
        v67 = v42[20];
        v85 = *((_QWORD *)v42 + 9);
        v75 = v42[8];
        v84 = *((_QWORD *)v42 + 3);
        v74 = *v42;
        v83 = *((_QWORD *)v42 + 16);
        v73 = v42[16];
        v82 = *((_QWORD *)v42 + 7);
        v72 = v42[2];
        v81 = 0x1000000;
        v80 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v45,
          (int)&byte_1404A3CEF,
          *(_DWORD *)v5 + 8,
          (__int64)&v80,
          (__int64)&v81,
          (__int64)&v72,
          (__int64)&v82,
          (__int64)&v73,
          (__int64)&v83,
          (__int64)&v74,
          (__int64)&v84,
          (__int64)&v75,
          (__int64)&v85,
          (__int64)&v67,
          (__int64)&v86,
          (__int64)&v87,
          (__int64)&CurrentThreadId,
          (__int64)&v79,
          (__int64)&v76,
          (__int64)&v70,
          (__int64)&v69,
          (__int64)&SRWLock,
          (__int64)&v71,
          (__int64)&v77,
          (__int64)&v78);
        std::wstring::~wstring(v98, v51);
        v52 = v91;
        if ( v91 )
        {
          if ( _InterlockedExchangeAdd(v91 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
            if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
          }
        }
        v53 = v89;
        if ( v89 )
        {
          if ( _InterlockedExchangeAdd(v89 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
            if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
          }
        }
        goto LABEL_97;
      }
    }
    else
    {
      v43 = (_DWORD **)(a1 + 272);
    }
    SRWLock = 0;
    wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    **v43 = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v54 = Windows::WU::Telemetry::WuProvider::Provider();
    v55 = (int)v54;
    if ( *(_DWORD *)v54 <= 5u
      || (*((_QWORD *)v54 + 2) & 0x400000000000LL) == 0
      || (*((_QWORD *)v54 + 3) & 0x400000000000LL) != *((_QWORD *)v54 + 3) )
    {
      return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
    }
    v78 = (__int64)"1507.2603.28012.0";
    v56 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v97);
    if ( v56[3] > 0xFu )
      v56 = (_QWORD *)*v56;
    v77 = (__int64)v56;
    v57 = SystemInterface::Providers::GetSystem(v88);
    v58 = *(_QWORD *)v57 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v57 + 8LL) + 4LL);
    v59 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v58 + 8LL))(v58, v90);
    v71 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v59 + 104LL))(*v59)
        - (unsigned __int64)*(unsigned int *)(a1 + 344);
    LODWORD(SRWLock) = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 328) + 8LL))(
                                         *(_QWORD *)(a1 + 328),
                                         &v69)
                     / 60000000;
    v69 = (__int64)L"Completed";
    v60 = (_QWORD *)Update::list_to_telemetry<std::vector<std::shared_ptr<Update>>>(v98);
    if ( v60[3] > 7u )
      v60 = (_QWORD *)*v60;
    v70 = (__int64)v60;
    CurrentThreadId = GetCurrentThreadId();
    v61 = (_DWORD *)*v5;
    v67 = *(_DWORD *)(*v5 + 72);
    v76 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v55,
      (int)&byte_1404A3A41,
      (_DWORD)v61 + 8,
      (__int64)&v76,
      (__int64)&v67,
      (__int64)&CurrentThreadId,
      (__int64)&v70,
      (__int64)&v69,
      (__int64)&SRWLock,
      (__int64)&v71,
      (__int64)&v77,
      (__int64)&v78);
    std::wstring::~wstring(v98, v62);
    v63 = v91;
    if ( v91 )
    {
      if ( _InterlockedExchangeAdd(v91 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v63)(v63);
        if ( _InterlockedExchangeAdd(v63 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v63 + 8LL))(v63);
      }
    }
    v64 = v89;
    if ( v89 )
    {
      if ( _InterlockedExchangeAdd(v89 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v64)(v64);
        if ( _InterlockedExchangeAdd(v64 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v64 + 8LL))(v64);
      }
    }
LABEL_97:
    std::string::_Tidy_deallocate(v97);
    return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
  }
  if ( v7 < 0 && (v8 = (int *)(v6 + 80), v7 == v8[2]) )
  {
    v9 = (_DWORD **)(a1 + 272);
    if ( v8 )
    {
      SRWLock = 0;
      wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        a1,
        &SRWLock);
      *(_DWORD *)*v5 = 2;
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      v10 = Windows::WU::Telemetry::WuProvider::Provider();
      v11 = (int)v10;
      if ( *(_DWORD *)v10 > 5u
        && (*((_QWORD *)v10 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v10 + 3) & 0x400000000000LL) == *((_QWORD *)v10 + 3) )
      {
        v92 = (__int64)"1507.2603.28012.0";
        v12 = (_QWORD *)SystemInterface::Providers::GetSystem(v90);
        v13 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v12 + 40LL))(*v12, v88);
        v14 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v13 + 440LL))(*v13, v98);
        if ( v14[3] > 7u )
          v14 = (_QWORD *)*v14;
        v80 = (__int64)v14;
        v15 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v97);
        if ( v15[3] > 0xFu )
          v15 = (_QWORD *)*v15;
        v81 = (__int64)v15;
        v16 = SystemInterface::Providers::GetSystem(v95);
        v17 = *(_QWORD *)v16 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v16 + 8LL) + 4LL);
        v18 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v17 + 8LL))(v17, v93);
        v82 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 104LL))(*v18)
            - (unsigned __int64)*(unsigned int *)(a1 + 344);
        v72 = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 328) + 8LL))(
                                *(_QWORD *)(a1 + 328),
                                &v71)
            / 60000000;
        v83 = (__int64)L"Completed";
        v19 = (_QWORD *)Update::list_to_telemetry<std::vector<std::shared_ptr<Update>>>(Src);
        if ( v19[3] > 7u )
          v19 = (_QWORD *)*v19;
        v84 = (__int64)v19;
        v85 = *((_QWORD *)v8 + 15);
        v86 = *((_QWORD *)v8 + 14);
        v73 = v8[26];
        v87 = *((_QWORD *)v8 + 12);
        v79 = *((_QWORD *)v8 + 11);
        v74 = v8[20];
        v76 = *((_QWORD *)v8 + 9);
        v75 = v8[8];
        v70 = *((_QWORD *)v8 + 3);
        v67 = *v8;
        v69 = *((_QWORD *)v8 + 16);
        CurrentThreadId = v8[16];
        v71 = *((_QWORD *)v8 + 7);
        LODWORD(SRWLock) = v8[2];
        v77 = 0x1000000;
        v78 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          v11,
          (int)&word_1404A406E,
          *(_DWORD *)v5 + 8,
          (__int64)&v78,
          (__int64)&v77,
          (__int64)&SRWLock,
          (__int64)&v71,
          (__int64)&CurrentThreadId,
          (__int64)&v69,
          (__int64)&v67,
          (__int64)&v70,
          (__int64)&v75,
          (__int64)&v76,
          (__int64)&v74,
          (__int64)&v79,
          (__int64)&v87,
          (__int64)&v73,
          (__int64)&v86,
          (__int64)&v85,
          (__int64)&v84,
          (__int64)&v83,
          (__int64)&v72,
          (__int64)&v82,
          (__int64)&v81,
          (__int64)&v80,
          (__int64)&v92);
        std::wstring::~wstring(Src, v20);
        v21 = v94;
        if ( v94 )
        {
          if ( _InterlockedExchangeAdd(v94 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
            if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
          }
        }
        v22 = v96;
        if ( v96 )
        {
          if ( _InterlockedExchangeAdd(v96 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
            if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
          }
        }
        std::string::_Tidy_deallocate(v97);
        std::wstring::~wstring(v98, v23);
        v24 = v89;
        if ( v89 )
        {
          if ( _InterlockedExchangeAdd(v89 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
            if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
          }
        }
        v25 = v91;
LABEL_29:
        if ( v25 )
        {
          if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
            if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          }
        }
        return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
      }
      return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
    }
  }
  else
  {
    v9 = (_DWORD **)(a1 + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  **v9 = 2;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v26 = Windows::WU::Telemetry::WuProvider::Provider();
  v27 = (int)v26;
  if ( *(_DWORD *)v26 > 5u
    && (*((_QWORD *)v26 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v26 + 3) & 0x400000000000LL) == *((_QWORD *)v26 + 3) )
  {
    v78 = (__int64)"1507.2603.28012.0";
    v28 = (_QWORD *)SystemInterface::Providers::GetSystem(v93);
    v29 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v28 + 40LL))(*v28, v95);
    v30 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v29 + 440LL))(*v29, Src);
    if ( v30[3] > 7u )
      v30 = (_QWORD *)*v30;
    v77 = (__int64)v30;
    v31 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v97);
    if ( v31[3] > 0xFu )
      v31 = (_QWORD *)*v31;
    v71 = (__int64)v31;
    v32 = SystemInterface::Providers::GetSystem(v88);
    v33 = *(_QWORD *)v32 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v32 + 8LL) + 4LL);
    v34 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v33 + 8LL))(v33, v90);
    v69 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v34 + 104LL))(*v34)
        - (unsigned __int64)*(unsigned int *)(a1 + 344);
    LODWORD(SRWLock) = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 328) + 8LL))(
                                         *(_QWORD *)(a1 + 328),
                                         &v70)
                     / 60000000;
    v70 = (__int64)L"Completed";
    v35 = (_QWORD *)Update::list_to_telemetry<std::vector<std::shared_ptr<Update>>>(v98);
    if ( v35[3] > 7u )
      v35 = (_QWORD *)*v35;
    v76 = (__int64)v35;
    CurrentThreadId = GetCurrentThreadId();
    v36 = *v5;
    v67 = *(_DWORD *)(*v5 + 72);
    v79 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
      v27,
      (int)&byte_1404A3C4B,
      v36 + 8,
      (__int64)&v79,
      (__int64)&v67,
      (__int64)&CurrentThreadId,
      (__int64)&v76,
      (__int64)&v70,
      (__int64)&SRWLock,
      (__int64)&v69,
      (__int64)&v71,
      (__int64)&v77,
      (__int64)&v78);
    std::wstring::~wstring(v98, v37);
    v38 = v91;
    if ( v91 )
    {
      if ( _InterlockedExchangeAdd(v91 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
        if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
      }
    }
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
    std::string::_Tidy_deallocate(v97);
    std::wstring::~wstring(Src, v40);
    v41 = v96;
    if ( v96 )
    {
      if ( _InterlockedExchangeAdd(v96 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
        if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
      }
    }
    v25 = v94;
    goto LABEL_29;
  }
  return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x1402cbcfc  push    rbp
0x1402cbcfe  push    rbx
0x1402cbcff  push    rsi
0x1402cbd00  push    rdi
0x1402cbd01  push    r12
0x1402cbd03  push    r14
0x1402cbd05  push    r15
0x1402cbd07  lea     rbp, [rsp-0C0h]
0x1402cbd0f  sub     rsp, 220h
0x1402cbd16  mov     r12, r8
0x1402cbd19  mov     rbx, rdx
0x1402cbd1c  mov     rsi, rcx
0x1402cbd1f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections> `wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl(void)'::`2'::impl
0x1402cbd26  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(void)
0x1402cbd2b  lea     rdi, [rsi+110h]
0x1402cbd32  mov     r14, [rdi]
0x1402cbd35  mov     ecx, [r14+48h]
0x1402cbd39  test    al, al
0x1402cbd3b  jz      loc_1402CC48C
0x1402cbd41  test    ecx, ecx
0x1402cbd43  jns     loc_1402CC193
0x1402cbd49  add     r14, 50h ; 'P'
0x1402cbd4d  cmp     ecx, [r14+8]
0x1402cbd51  jnz     loc_1402CC193
0x1402cbd57  mov     r15, rdi
0x1402cbd5a  test    r14, r14
0x1402cbd5d  jz      loc_1402CC196
0x1402cbd63  mov     [rbp+0F0h+SRWLock], 0
0x1402cbd6b  lea     rdx, [rbp+0F0h+SRWLock]
0x1402cbd6f  mov     rcx, rsi
0x1402cbd72  call    ?LockExclusive@?$ActivityBase@VBaseCore@Telemetry@Windows@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1402cbd77  mov     rax, [rdi]
0x1402cbd7a  mov     dword ptr [rax], 2
0x1402cbd80  mov     rcx, [rbp+0F0h+SRWLock]; SRWLock
0x1402cbd84  test    rcx, rcx
0x1402cbd87  jz      short loc_1402CBD8F
0x1402cbd89  call    cs:__imp_ReleaseSRWLockExclusive
0x1402cbd8f  call    ?Provider@WuProvider@Telemetry@WU@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::WU::Telemetry::WuProvider::Provider(void)
0x1402cbd94  mov     r15, rax
0x1402cbd97  cmp     dword ptr [rax], 5
0x1402cbd9a  jbe     loc_1402CCA46
0x1402cbda0  mov     rdx, 400000000000h
0x1402cbdaa  test    [rax+10h], rdx
0x1402cbdae  jz      loc_1402CCA46
0x1402cbdb4  mov     rcx, [rax+18h]
0x1402cbdb8  and     rcx, rdx
0x1402cbdbb  cmp     rcx, [rax+18h]
0x1402cbdbf  jnz     loc_1402CCA46
0x1402cbdc5  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1402cbdcc  mov     [rbp+0F0h+var_B8], rax
0x1402cbdd0  lea     rcx, [rbp+0F0h+var_C8]
0x1402cbdd4  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1402cbdd9  nop
0x1402cbdda  mov     rcx, [rax]
0x1402cbddd  mov     rax, [rcx]
0x1402cbde0  lea     rdx, [rbp+0F0h+var_D8]
0x1402cbde4  mov     rax, [rax+28h]
0x1402cbde8  call    _guard_dispatch_icall
0x1402cbded  nop
0x1402cbdee  mov     rcx, [rax]
0x1402cbdf1  mov     rax, [rcx]
0x1402cbdf4  lea     rdx, [rbp+0F0h+var_70]
0x1402cbdfb  mov     rax, [rax+1B8h]
0x1402cbe02  call    _guard_dispatch_icall
0x1402cbe07  nop
0x1402cbe08  cmp     qword ptr [rax+18h], 7
0x1402cbe0d  jbe     short loc_1402CBE12
0x1402cbe0f  mov     rax, [rax]
0x1402cbe12  mov     [rbp+0F0h+var_118], rax
0x1402cbe16  mov     rax, [rbx]
0x1402cbe19  lea     rdx, [rbp+0F0h+var_90]
0x1402cbe1d  mov     rcx, rbx
0x1402cbe20  mov     rax, [rax+8]
0x1402cbe24  call    _guard_dispatch_icall
0x1402cbe29  nop
0x1402cbe2a  cmp     qword ptr [rax+18h], 0Fh
0x1402cbe2f  jbe     short loc_1402CBE34
0x1402cbe31  mov     rax, [rax]
0x1402cbe34  mov     [rbp+0F0h+var_110], rax
0x1402cbe38  lea     rcx, [rbp+0F0h+var_A0]
0x1402cbe3c  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1402cbe41  nop
0x1402cbe42  mov     rdx, [rax]
0x1402cbe45  mov     rax, [rdx+8]
0x1402cbe49  movsxd  rcx, dword ptr [rax+4]
0x1402cbe4d  add     rdx, 8
0x1402cbe51  add     rcx, rdx
0x1402cbe54  mov     rax, [rcx]
0x1402cbe57  lea     rdx, [rbp+0F0h+var_B0]
0x1402cbe5b  mov     rax, [rax+8]
0x1402cbe5f  call    _guard_dispatch_icall
0x1402cbe64  nop
0x1402cbe65  mov     rcx, [rax]
0x1402cbe68  mov     rax, [rcx]
0x1402cbe6b  mov     rax, [rax+68h]
0x1402cbe6f  call    _guard_dispatch_icall
0x1402cbe74  mov     ecx, eax
0x1402cbe76  mov     eax, [rsi+158h]
0x1402cbe7c  sub     rcx, rax
0x1402cbe7f  mov     [rbp+0F0h+var_108], rcx
0x1402cbe83  mov     rcx, [rsi+148h]
0x1402cbe8a  mov     rax, [rcx]
0x1402cbe8d  lea     rdx, [rbp+0F0h+var_150]
0x1402cbe91  mov     rax, [rax+8]
0x1402cbe95  call    _guard_dispatch_icall
0x1402cbe9a  mov     rcx, [rax]
0x1402cbe9d  mov     rax, 8F2A633943A6D729h
0x1402cbea7  imul    rcx
0x1402cbeaa  add     rdx, rcx
0x1402cbead  sar     rdx, 19h
0x1402cbeb1  mov     rax, rdx
0x1402cbeb4  shr     rax, 3Fh
0x1402cbeb8  add     rdx, rax
0x1402cbebb  mov     dword ptr [rbp+0F0h+var_148], edx
0x1402cbebe  lea     rax, aCompleted; "Completed"
0x1402cbec5  mov     [rbp+0F0h+var_100], rax
0x1402cbec9  xor     r8d, r8d
0x1402cbecc  mov     rdx, r12
0x1402cbecf  lea     rcx, [rbp+0F0h+Src]; Src
0x1402cbed6  call    ??$list_to_telemetry@V?$vector@V?$shared_ptr@VUpdate@@@std@@V?$allocator@V?$shared_ptr@VUpdate@@@std@@@2@@std@@@Update@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$shared_ptr@VUpdate@@@std@@V?$allocator@V?$shared_ptr@VUpdate@@@std@@@2@@2@_N@Z; Update::list_to_telemetry<std::vector<std::shared_ptr<Update>>>(std::vector<std::shared_ptr<Update>> const &,bool)
0x1402cbedb  cmp     qword ptr [rax+18h], 7
0x1402cbee0  jbe     short loc_1402CBEE5
0x1402cbee2  mov     rax, [rax]
0x1402cbee5  mov     [rbp+0F0h+var_F8], rax
0x1402cbee9  mov     rax, [r14+78h]
0x1402cbeed  mov     [rbp+0F0h+var_F0], rax
0x1402cbef1  mov     rax, [r14+70h]
0x1402cbef5  mov     [rbp+0F0h+var_E8], rax
0x1402cbef9  mov     eax, [r14+68h]
0x1402cbefd  mov     dword ptr [rbp+0F0h+var_148+4], eax
0x1402cbf00  mov     rax, [r14+60h]
0x1402cbf04  mov     [rbp+0F0h+var_E0], rax
0x1402cbf08  mov     rax, [r14+58h]
0x1402cbf0c  mov     [rbp+0F0h+var_120], rax
0x1402cbf10  mov     eax, [r14+50h]
0x1402cbf14  mov     dword ptr [rbp+0F0h+var_140], eax
0x1402cbf17  mov     rax, [r14+48h]
0x1402cbf1b  mov     [rbp+0F0h+var_138], rax
0x1402cbf1f  mov     eax, [r14+20h]
0x1402cbf23  mov     dword ptr [rbp+0F0h+var_140+4], eax
0x1402cbf26  mov     rax, [r14+18h]
0x1402cbf2a  mov     [rbp+0F0h+var_158], rax
0x1402cbf2e  mov     eax, [r14]
0x1402cbf31  mov     dword ptr [rbp+0F0h+var_168], eax
0x1402cbf34  mov     rax, [r14+80h]
0x1402cbf3b  mov     [rbp+0F0h+var_160], rax
0x1402cbf3f  mov     eax, [r14+40h]
0x1402cbf43  mov     dword ptr [rbp+0F0h+var_168+4], eax
0x1402cbf46  mov     rax, [r14+38h]
0x1402cbf4a  mov     [rbp+0F0h+var_150], rax
0x1402cbf4e  mov     eax, [r14+8]
0x1402cbf52  mov     dword ptr [rbp+0F0h+SRWLock], eax
0x1402cbf55  mov     eax, 1000000h
0x1402cbf5a  mov     [rbp+0F0h+var_130], rax
0x1402cbf5e  mov     [rbp+0F0h+var_128], rax
0x1402cbf62  mov     r8, [rdi]
0x1402cbf65  add     r8, 8; int
0x1402cbf69  lea     rax, [rbp+0F0h+var_B8]
0x1402cbf6d  mov     [rsp+250h+var_180], rax; __int64
0x1402cbf75  lea     rax, [rbp+0F0h+var_118]
0x1402cbf79  mov     [rsp+250h+var_188], rax; __int64
0x1402cbf81  lea     rax, [rbp+0F0h+var_110]
0x1402cbf85  mov     [rsp+250h+var_190], rax; __int64
0x1402cbf8d  lea     rax, [rbp+0F0h+var_108]
0x1402cbf91  mov     [rsp+250h+var_198], rax; __int64
0x1402cbf99  lea     rax, [rbp+0F0h+var_148]
0x1402cbf9d  mov     [rsp+250h+var_1A0], rax; __int64
0x1402cbfa5  lea     rax, [rbp+0F0h+var_100]
0x1402cbfa9  mov     [rsp+250h+var_1A8], rax; __int64
0x1402cbfb1  lea     rax, [rbp+0F0h+var_F8]
0x1402cbfb5  mov     [rsp+250h+var_1B0], rax; __int64
0x1402cbfbd  lea     rax, [rbp+0F0h+var_F0]
0x1402cbfc1  mov     [rsp+250h+var_1B8], rax; __int64
0x1402cbfc9  lea     rax, [rbp+0F0h+var_E8]
0x1402cbfcd  mov     [rsp+250h+var_1C0], rax; __int64
0x1402cbfd5  lea     rax, [rbp+0F0h+var_148+4]
0x1402cbfd9  mov     [rsp+250h+var_1C8], rax; __int64
0x1402cbfe1  lea     rax, [rbp+0F0h+var_E0]
0x1402cbfe5  mov     [rsp+250h+var_1D0], rax; __int64
0x1402cbfed  lea     rax, [rbp+0F0h+var_120]
0x1402cbff1  mov     [rsp+250h+var_1D8], rax; __int64
0x1402cbff6  lea     rax, [rbp+0F0h+var_140]
0x1402cbffa  mov     [rsp+250h+var_1E0], rax; __int64
0x1402cbfff  lea     rax, [rbp+0F0h+var_138]
0x1402cc003  mov     [rsp+250h+var_1E8], rax; __int64
0x1402cc008  lea     rax, [rbp+0F0h+var_140+4]
0x1402cc00c  mov     [rsp+250h+var_1F0], rax; __int64
0x1402cc011  lea     rax, [rbp+0F0h+var_158]
0x1402cc015  mov     [rsp+250h+var_1F8], rax; __int64
0x1402cc01a  lea     rax, [rbp+0F0h+var_168]
0x1402cc01e  mov     [rsp+250h+var_200], rax; __int64
0x1402cc023  lea     rax, [rbp+0F0h+var_160]
0x1402cc027  mov     [rsp+250h+var_208], rax; __int64
0x1402cc02c  lea     rax, [rbp+0F0h+var_168+4]
0x1402cc030  mov     [rsp+250h+var_210], rax; __int64
0x1402cc035  lea     rax, [rbp+0F0h+var_150]
0x1402cc039  mov     [rsp+250h+var_218], rax; __int64
0x1402cc03e  lea     rax, [rbp+0F0h+SRWLock]
0x1402cc042  mov     [rsp+250h+var_220], rax; __int64
0x1402cc047  lea     rax, [rbp+0F0h+var_130]
0x1402cc04b  mov     [rsp+250h+var_228], rax; __int64
0x1402cc050  lea     rax, [rbp+0F0h+var_128]
0x1402cc054  mov     [rsp+250h+var_230], rax; __int64
0x1402cc059  lea     rdx, word_1404A406E; int
0x1402cc060  mov     rcx, r15; int
0x1402cc063  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U2@U1@U3@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564566643565@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x1402cc068  lea     rcx, [rbp+0F0h+Src]
0x1402cc06f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402cc074  nop
0x1402cc075  or      ebx, 0FFFFFFFFh
0x1402cc078  mov     rdi, [rbp+0F0h+var_A8]
0x1402cc07c  test    rdi, rdi
0x1402cc07f  jz      short loc_1402CC0B5
0x1402cc081  mov     eax, ebx
0x1402cc083  lock xadd [rdi+8], eax
0x1402cc088  add     eax, ebx
0x1402cc08a  jnz     short loc_1402CC0B5
0x1402cc08c  mov     rax, [rdi]
0x1402cc08f  mov     rcx, rdi
0x1402cc092  mov     rax, [rax]
0x1402cc095  call    _guard_dispatch_icall
0x1402cc09a  mov     eax, ebx
0x1402cc09c  lock xadd [rdi+0Ch], eax
0x1402cc0a1  add     eax, ebx
0x1402cc0a3  jnz     short loc_1402CC0B5
0x1402cc0a5  mov     rax, [rdi]
0x1402cc0a8  mov     rcx, rdi
0x1402cc0ab  mov     rax, [rax+8]
0x1402cc0af  call    _guard_dispatch_icall
0x1402cc0b4  nop
0x1402cc0b5  mov     rdi, [rbp+0F0h+var_98]
0x1402cc0b9  test    rdi, rdi
0x1402cc0bc  jz      short loc_1402CC0F2
0x1402cc0be  mov     eax, ebx
0x1402cc0c0  lock xadd [rdi+8], eax
0x1402cc0c5  add     eax, ebx
0x1402cc0c7  jnz     short loc_1402CC0F2
0x1402cc0c9  mov     rax, [rdi]
0x1402cc0cc  mov     rcx, rdi
0x1402cc0cf  mov     rax, [rax]
0x1402cc0d2  call    _guard_dispatch_icall
0x1402cc0d7  mov     eax, ebx
0x1402cc0d9  lock xadd [rdi+0Ch], eax
0x1402cc0de  add     eax, ebx
0x1402cc0e0  jnz     short loc_1402CC0F2
0x1402cc0e2  mov     rax, [rdi]
0x1402cc0e5  mov     rcx, rdi
0x1402cc0e8  mov     rax, [rax+8]
0x1402cc0ec  call    _guard_dispatch_icall
0x1402cc0f1  nop
0x1402cc0f2  lea     rcx, [rbp+0F0h+var_90]
0x1402cc0f6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1402cc0fb  nop
0x1402cc0fc  lea     rcx, [rbp+0F0h+var_70]
0x1402cc103  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402cc108  nop
0x1402cc109  mov     rdi, [rbp+0F0h+var_D0]
0x1402cc10d  test    rdi, rdi
0x1402cc110  jz      short loc_1402CC146
0x1402cc112  mov     eax, ebx
0x1402cc114  lock xadd [rdi+8], eax
0x1402cc119  add     eax, ebx
0x1402cc11b  jnz     short loc_1402CC146
0x1402cc11d  mov     rax, [rdi]
0x1402cc120  mov     rcx, rdi
0x1402cc123  mov     rax, [rax]
0x1402cc126  call    _guard_dispatch_icall
0x1402cc12b  mov     eax, ebx
0x1402cc12d  lock xadd [rdi+0Ch], eax
0x1402cc132  add     eax, ebx
0x1402cc134  jnz     short loc_1402CC146
0x1402cc136  mov     rax, [rdi]
0x1402cc139  mov     rcx, rdi
0x1402cc13c  mov     rax, [rax+8]
0x1402cc140  call    _guard_dispatch_icall
0x1402cc145  nop
0x1402cc146  mov     rdi, [rbp+0F0h+var_C0]
0x1402cc14a  test    rdi, rdi
0x1402cc14d  jz      loc_1402CCA46
0x1402cc153  mov     eax, ebx
0x1402cc155  lock xadd [rdi+8], eax
0x1402cc15a  add     eax, ebx
0x1402cc15c  jnz     loc_1402CCA46
0x1402cc162  mov     rax, [rdi]
0x1402cc165  mov     rcx, rdi
0x1402cc168  mov     rax, [rax]
0x1402cc16b  call    _guard_dispatch_icall
0x1402cc170  mov     eax, ebx
0x1402cc172  lock xadd [rdi+0Ch], eax
0x1402cc177  add     eax, ebx
0x1402cc179  jnz     loc_1402CCA46
0x1402cc17f  mov     rax, [rdi]
0x1402cc182  mov     rcx, rdi
0x1402cc185  mov     rax, [rax+8]
0x1402cc189  call    _guard_dispatch_icall
0x1402cc18e  jmp     loc_1402CCA46
0x1402cc193  mov     r15, rdi
0x1402cc196  mov     [rbp+0F0h+SRWLock], 0
0x1402cc19e  lea     rdx, [rbp+0F0h+SRWLock]
0x1402cc1a2  mov     rcx, rsi
  ... truncated ...
```
