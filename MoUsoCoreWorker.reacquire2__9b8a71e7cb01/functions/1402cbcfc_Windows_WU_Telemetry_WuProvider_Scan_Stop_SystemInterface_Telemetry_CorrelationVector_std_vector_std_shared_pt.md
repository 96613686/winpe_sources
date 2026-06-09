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
  volatile signed __int32 *v20; // rdi
  volatile signed __int32 *v21; // rdi
  volatile signed __int32 *v22; // rdi
  volatile signed __int32 *v23; // rdi
  const struct _tlgProvider_t *v24; // rax
  int v25; // r14d
  _QWORD *v26; // rax
  _QWORD *v27; // rax
  _QWORD *v28; // rax
  _QWORD *v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  _QWORD *v32; // rax
  _QWORD *v33; // rax
  __int64 v34; // r8
  volatile signed __int32 *v35; // rdi
  volatile signed __int32 *v36; // rdi
  volatile signed __int32 *v37; // rdi
  int *v38; // r14
  _DWORD **v39; // r15
  const struct _tlgProvider_t *v40; // rax
  int v41; // r15d
  _QWORD *v42; // rax
  __int64 System; // rax
  __int64 v44; // rcx
  _QWORD *v45; // rax
  _QWORD *v46; // rax
  volatile signed __int32 *v47; // rdi
  volatile signed __int32 *v48; // rdi
  const struct _tlgProvider_t *v49; // rax
  int v50; // r14d
  _QWORD *v51; // rax
  __int64 v52; // rax
  __int64 v53; // rcx
  _QWORD *v54; // rax
  _QWORD *v55; // rax
  _DWORD *v56; // r8
  volatile signed __int32 *v57; // rdi
  volatile signed __int32 *v58; // rdi
  PSRWLOCK SRWLock; // [rsp+E0h] [rbp-80h] BYREF
  int v61; // [rsp+E8h] [rbp-78h] BYREF
  DWORD CurrentThreadId; // [rsp+ECh] [rbp-74h] BYREF
  __int64 v63; // [rsp+F0h] [rbp-70h] BYREF
  __int64 v64; // [rsp+F8h] [rbp-68h] BYREF
  __int64 v65; // [rsp+100h] [rbp-60h] BYREF
  int v66; // [rsp+108h] [rbp-58h] BYREF
  int v67; // [rsp+10Ch] [rbp-54h] BYREF
  int v68; // [rsp+110h] [rbp-50h] BYREF
  int v69; // [rsp+114h] [rbp-4Ch] BYREF
  __int64 v70; // [rsp+118h] [rbp-48h] BYREF
  __int64 v71; // [rsp+120h] [rbp-40h] BYREF
  __int64 v72; // [rsp+128h] [rbp-38h] BYREF
  __int64 v73; // [rsp+130h] [rbp-30h] BYREF
  __int64 v74; // [rsp+138h] [rbp-28h] BYREF
  __int64 v75; // [rsp+140h] [rbp-20h] BYREF
  __int64 v76; // [rsp+148h] [rbp-18h] BYREF
  __int64 v77; // [rsp+150h] [rbp-10h] BYREF
  __int64 v78; // [rsp+158h] [rbp-8h] BYREF
  __int64 v79; // [rsp+160h] [rbp+0h] BYREF
  __int64 v80; // [rsp+168h] [rbp+8h] BYREF
  __int64 v81; // [rsp+170h] [rbp+10h] BYREF
  _BYTE v82[8]; // [rsp+178h] [rbp+18h] BYREF
  volatile signed __int32 *v83; // [rsp+180h] [rbp+20h]
  _BYTE v84[8]; // [rsp+188h] [rbp+28h] BYREF
  volatile signed __int32 *v85; // [rsp+190h] [rbp+30h]
  __int64 v86; // [rsp+198h] [rbp+38h] BYREF
  _BYTE v87[8]; // [rsp+1A0h] [rbp+40h] BYREF
  volatile signed __int32 *v88; // [rsp+1A8h] [rbp+48h]
  _BYTE v89[8]; // [rsp+1B0h] [rbp+50h] BYREF
  volatile signed __int32 *v90; // [rsp+1B8h] [rbp+58h]
  _BYTE v91[32]; // [rsp+1C0h] [rbp+60h] BYREF
  _BYTE v92[32]; // [rsp+1E0h] [rbp+80h] BYREF
  _BYTE Src[80]; // [rsp+200h] [rbp+A0h] BYREF

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl);
  v5 = (__int64 *)(a1 + 272);
  v6 = *(_QWORD *)(a1 + 272);
  v7 = *(_DWORD *)(v6 + 72);
  if ( !IsEnabled )
  {
    if ( v7 < 0 && (v38 = (int *)(v6 + 80), v7 == v38[2]) )
    {
      v39 = (_DWORD **)(a1 + 272);
      if ( v38 )
      {
        SRWLock = 0;
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
          a1,
          &SRWLock);
        *(_DWORD *)*v5 = 2;
        if ( SRWLock )
          ReleaseSRWLockExclusive(SRWLock);
        v40 = Windows::WU::Telemetry::WuProvider::Provider();
        v41 = (int)v40;
        if ( *(_DWORD *)v40 <= 5u
          || (*((_QWORD *)v40 + 2) & 0x400000000000LL) == 0
          || (*((_QWORD *)v40 + 3) & 0x400000000000LL) != *((_QWORD *)v40 + 3) )
        {
          return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
        }
        v72 = (__int64)"1507.2603.28012.0";
        v42 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v91);
        if ( v42[3] > 0xFu )
          v42 = (_QWORD *)*v42;
        v71 = (__int64)v42;
        System = SystemInterface::Providers::GetSystem(v82);
        v44 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
        v45 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v44 + 8LL))(v44, v84);
        v65 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v45 + 104LL))(*v45)
            - (unsigned __int64)*(unsigned int *)(a1 + 344);
        LODWORD(SRWLock) = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 328) + 8LL))(
                                             *(_QWORD *)(a1 + 328),
                                             &v63)
                         / 60000000;
        v63 = (__int64)L"Completed";
        v46 = (_QWORD *)Update::list_to_telemetry<std::vector<std::shared_ptr<Update>>>(v92);
        if ( v46[3] > 7u )
          v46 = (_QWORD *)*v46;
        v64 = (__int64)v46;
        v70 = *((_QWORD *)v38 + 15);
        v73 = *((_QWORD *)v38 + 14);
        CurrentThreadId = v38[26];
        v81 = *((_QWORD *)v38 + 12);
        v80 = *((_QWORD *)v38 + 11);
        v61 = v38[20];
        v79 = *((_QWORD *)v38 + 9);
        v69 = v38[8];
        v78 = *((_QWORD *)v38 + 3);
        v68 = *v38;
        v77 = *((_QWORD *)v38 + 16);
        v67 = v38[16];
        v76 = *((_QWORD *)v38 + 7);
        v66 = v38[2];
        v75 = 0x1000000;
        v74 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v41,
          (int)&byte_1404A3CEF,
          *(_DWORD *)v5 + 8,
          (__int64)&v74,
          (__int64)&v75,
          (__int64)&v66,
          (__int64)&v76,
          (__int64)&v67,
          (__int64)&v77,
          (__int64)&v68,
          (__int64)&v78,
          (__int64)&v69,
          (__int64)&v79,
          (__int64)&v61,
          (__int64)&v80,
          (__int64)&v81,
          (__int64)&CurrentThreadId,
          (__int64)&v73,
          (__int64)&v70,
          (__int64)&v64,
          (__int64)&v63,
          (__int64)&SRWLock,
          (__int64)&v65,
          (__int64)&v71,
          (__int64)&v72);
        std::wstring::~wstring(v92);
        v47 = v85;
        if ( v85 )
        {
          if ( _InterlockedExchangeAdd(v85 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
            if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
          }
        }
        v48 = v83;
        if ( v83 )
        {
          if ( _InterlockedExchangeAdd(v83 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
            if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
          }
        }
        goto LABEL_97;
      }
    }
    else
    {
      v39 = (_DWORD **)(a1 + 272);
    }
    SRWLock = 0;
    wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    **v39 = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v49 = Windows::WU::Telemetry::WuProvider::Provider();
    v50 = (int)v49;
    if ( *(_DWORD *)v49 <= 5u
      || (*((_QWORD *)v49 + 2) & 0x400000000000LL) == 0
      || (*((_QWORD *)v49 + 3) & 0x400000000000LL) != *((_QWORD *)v49 + 3) )
    {
      return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
    }
    v72 = (__int64)"1507.2603.28012.0";
    v51 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v91);
    if ( v51[3] > 0xFu )
      v51 = (_QWORD *)*v51;
    v71 = (__int64)v51;
    v52 = SystemInterface::Providers::GetSystem(v82);
    v53 = *(_QWORD *)v52 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v52 + 8LL) + 4LL);
    v54 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v53 + 8LL))(v53, v84);
    v65 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v54 + 104LL))(*v54)
        - (unsigned __int64)*(unsigned int *)(a1 + 344);
    LODWORD(SRWLock) = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 328) + 8LL))(
                                         *(_QWORD *)(a1 + 328),
                                         &v63)
                     / 60000000;
    v63 = (__int64)L"Completed";
    v55 = (_QWORD *)Update::list_to_telemetry<std::vector<std::shared_ptr<Update>>>(v92);
    if ( v55[3] > 7u )
      v55 = (_QWORD *)*v55;
    v64 = (__int64)v55;
    CurrentThreadId = GetCurrentThreadId();
    v56 = (_DWORD *)*v5;
    v61 = *(_DWORD *)(*v5 + 72);
    v70 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v50,
      (int)&byte_1404A3A41,
      (_DWORD)v56 + 8,
      (__int64)&v70,
      (__int64)&v61,
      (__int64)&CurrentThreadId,
      (__int64)&v64,
      (__int64)&v63,
      (__int64)&SRWLock,
      (__int64)&v65,
      (__int64)&v71,
      (__int64)&v72);
    std::wstring::~wstring(v92);
    v57 = v85;
    if ( v85 )
    {
      if ( _InterlockedExchangeAdd(v85 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
        if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
      }
    }
    v58 = v83;
    if ( v83 )
    {
      if ( _InterlockedExchangeAdd(v83 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
        if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
      }
    }
LABEL_97:
    std::string::_Tidy_deallocate(v91);
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
        v86 = (__int64)"1507.2603.28012.0";
        v12 = (_QWORD *)SystemInterface::Providers::GetSystem(v84);
        v13 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v12 + 40LL))(*v12, v82);
        v14 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v13 + 440LL))(*v13, v92);
        if ( v14[3] > 7u )
          v14 = (_QWORD *)*v14;
        v74 = (__int64)v14;
        v15 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v91);
        if ( v15[3] > 0xFu )
          v15 = (_QWORD *)*v15;
        v75 = (__int64)v15;
        v16 = SystemInterface::Providers::GetSystem(v89);
        v17 = *(_QWORD *)v16 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v16 + 8LL) + 4LL);
        v18 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v17 + 8LL))(v17, v87);
        v76 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 104LL))(*v18)
            - (unsigned __int64)*(unsigned int *)(a1 + 344);
        v66 = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 328) + 8LL))(
                                *(_QWORD *)(a1 + 328),
                                &v65)
            / 60000000;
        v77 = (__int64)L"Completed";
        v19 = (_QWORD *)Update::list_to_telemetry<std::vector<std::shared_ptr<Update>>>(Src);
        if ( v19[3] > 7u )
          v19 = (_QWORD *)*v19;
        v78 = (__int64)v19;
        v79 = *((_QWORD *)v8 + 15);
        v80 = *((_QWORD *)v8 + 14);
        v67 = v8[26];
        v81 = *((_QWORD *)v8 + 12);
        v73 = *((_QWORD *)v8 + 11);
        v68 = v8[20];
        v70 = *((_QWORD *)v8 + 9);
        v69 = v8[8];
        v64 = *((_QWORD *)v8 + 3);
        v61 = *v8;
        v63 = *((_QWORD *)v8 + 16);
        CurrentThreadId = v8[16];
        v65 = *((_QWORD *)v8 + 7);
        LODWORD(SRWLock) = v8[2];
        v71 = 0x1000000;
        v72 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          v11,
          (int)&word_1404A406E,
          *(_DWORD *)v5 + 8,
          (__int64)&v72,
          (__int64)&v71,
          (__int64)&SRWLock,
          (__int64)&v65,
          (__int64)&CurrentThreadId,
          (__int64)&v63,
          (__int64)&v61,
          (__int64)&v64,
          (__int64)&v69,
          (__int64)&v70,
          (__int64)&v68,
          (__int64)&v73,
          (__int64)&v81,
          (__int64)&v67,
          (__int64)&v80,
          (__int64)&v79,
          (__int64)&v78,
          (__int64)&v77,
          (__int64)&v66,
          (__int64)&v76,
          (__int64)&v75,
          (__int64)&v74,
          (__int64)&v86);
        std::wstring::~wstring(Src);
        v20 = v88;
        if ( v88 )
        {
          if ( _InterlockedExchangeAdd(v88 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
            if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
          }
        }
        v21 = v90;
        if ( v90 )
        {
          if ( _InterlockedExchangeAdd(v90 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
            if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
          }
        }
        std::string::_Tidy_deallocate(v91);
        std::wstring::~wstring(v92);
        v22 = v83;
        if ( v83 )
        {
          if ( _InterlockedExchangeAdd(v83 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
            if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
          }
        }
        v23 = v85;
LABEL_29:
        if ( v23 )
        {
          if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
            if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
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
  v24 = Windows::WU::Telemetry::WuProvider::Provider();
  v25 = (int)v24;
  if ( *(_DWORD *)v24 > 5u
    && (*((_QWORD *)v24 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v24 + 3) & 0x400000000000LL) == *((_QWORD *)v24 + 3) )
  {
    v72 = (__int64)"1507.2603.28012.0";
    v26 = (_QWORD *)SystemInterface::Providers::GetSystem(v87);
    v27 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v26 + 40LL))(*v26, v89);
    v28 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v27 + 440LL))(*v27, Src);
    if ( v28[3] > 7u )
      v28 = (_QWORD *)*v28;
    v71 = (__int64)v28;
    v29 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v91);
    if ( v29[3] > 0xFu )
      v29 = (_QWORD *)*v29;
    v65 = (__int64)v29;
    v30 = SystemInterface::Providers::GetSystem(v82);
    v31 = *(_QWORD *)v30 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v30 + 8LL) + 4LL);
    v32 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 8LL))(v31, v84);
    v63 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 104LL))(*v32)
        - (unsigned __int64)*(unsigned int *)(a1 + 344);
    LODWORD(SRWLock) = (int)*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 328) + 8LL))(
                                         *(_QWORD *)(a1 + 328),
                                         &v64)
                     / 60000000;
    v64 = (__int64)L"Completed";
    v33 = (_QWORD *)Update::list_to_telemetry<std::vector<std::shared_ptr<Update>>>(v92);
    if ( v33[3] > 7u )
      v33 = (_QWORD *)*v33;
    v70 = (__int64)v33;
    CurrentThreadId = GetCurrentThreadId();
    v34 = *v5;
    v61 = *(_DWORD *)(*v5 + 72);
    v73 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
      v25,
      (int)&byte_1404A3C4B,
      v34 + 8,
      (__int64)&v73,
      (__int64)&v61,
      (__int64)&CurrentThreadId,
      (__int64)&v70,
      (__int64)&v64,
      (__int64)&SRWLock,
      (__int64)&v63,
      (__int64)&v65,
      (__int64)&v71,
      (__int64)&v72);
    std::wstring::~wstring(v92);
    v35 = v85;
    if ( v85 )
    {
      if ( _InterlockedExchangeAdd(v85 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
        if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
      }
    }
    v36 = v83;
    if ( v83 )
    {
      if ( _InterlockedExchangeAdd(v83 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
        if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
      }
    }
    std::string::_Tidy_deallocate(v91);
    std::wstring::~wstring(Src);
    v37 = v90;
    if ( v90 )
    {
      if ( _InterlockedExchangeAdd(v90 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
        if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
      }
    }
    v23 = v88;
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
