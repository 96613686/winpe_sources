# Windows::Telemetry::UpdateManagerCore::ScanCritical::Stop(wil::basic_zstring_view<wchar_t>,ProviderType,wil::basic_zstring_view<wchar_t>,bool,bool,SystemInterface::Telemetry::CorrelationVector &,wchar_t const *,unsigned __int64)

- ea: `0x140287530`
- end: `0x14028835a`
- name: `?Stop@ScanCritical@UpdateManagerCore@Telemetry@Windows@@QEAAXV?$basic_zstring_view@_W@wil@@W4ProviderType@@0_N2AEAVCorrelationVector@3SystemInterface@@PEB_W_K@Z`
- size: `3626`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x14028fee0`
- `0x14028ffa0`

## callees

- `0x14000883c`
- `0x140008ccc`
- `0x140009384`
- `0x1400097a0`
- `0x14002b5f0`
- `0x14002cd1c`
- `0x140040d8c`
- `0x140043284`
- `0x140044f20`
- `0x140045404`
- `0x140045688`
- `0x14012d7d8`
- `0x140269440`
- `0x140287530`
- `0x140379070`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140287af6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140287c31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140288115`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028823f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140287af6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140287c31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140288115`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028823f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140287648`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402879cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140287cdf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140288011`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140287648`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402879cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140287cdf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140288011`

## string_xrefs

- `0x1402875b6`: `WindowsUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
const struct _tlgProvider_t *__fastcall Windows::Telemetry::UpdateManagerCore::ScanCritical::Stop(
        __int64 a1,
        __int64 *a2,
        int a3,
        RTL_SRWLOCK *a4,
        char a5,
        char a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  int v12; // ebx
  const wchar_t *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r15
  __int64 v16; // r12
  int v17; // eax
  int *v18; // r12
  _DWORD **v19; // r14
  const struct _tlgProvider_t *v20; // rax
  void *v21; // rdx
  int v22; // r14d
  _QWORD *v23; // rax
  __int64 System; // rax
  __int64 v25; // rcx
  _QWORD *v26; // rax
  int v27; // eax
  int v28; // eax
  const wchar_t *v29; // rax
  __int128 *v30; // rax
  volatile signed __int32 *v31; // rdi
  volatile signed __int32 *v32; // rdi
  const struct _tlgProvider_t *v33; // rax
  int v34; // r14d
  _QWORD *v35; // rax
  __int64 v36; // rax
  __int64 v37; // rcx
  _QWORD *v38; // rax
  int v39; // eax
  int v40; // eax
  const wchar_t *v41; // rax
  __int128 *v42; // rax
  _DWORD *v43; // r8
  volatile signed __int32 *v44; // rdi
  volatile signed __int32 *v45; // rdi
  __int64 **v46; // rbx
  unsigned int v47; // r8d
  __int64 *v48; // rcx
  __int64 v49; // rax
  const struct _tlgProvider_t *result; // rax
  __int64 v51; // r14
  __int64 v52; // rbx
  int v53; // eax
  int *v54; // rbx
  _DWORD **v55; // r15
  int v56; // r15d
  _QWORD *v57; // rax
  __int64 v58; // rax
  __int64 v59; // rcx
  _QWORD *v60; // rax
  int v61; // eax
  int v62; // eax
  const wchar_t *v63; // rax
  volatile signed __int32 *v64; // rdi
  volatile signed __int32 *v65; // rdi
  int v66; // ebx
  _QWORD *v67; // rax
  __int64 v68; // rax
  __int64 v69; // rcx
  _QWORD *v70; // rax
  int v71; // eax
  int v72; // eax
  const wchar_t *v73; // rax
  _DWORD *v74; // r8
  volatile signed __int32 *v75; // rdi
  volatile signed __int32 *v76; // rdi
  const struct _tlgProvider_t ***v77; // rbx
  void *v78; // rdx
  unsigned int v79; // r8d
  const struct _tlgProvider_t **v80; // rcx
  int v81; // [rsp+28h] [rbp-150h]
  char v82; // [rsp+F8h] [rbp-80h] BYREF
  _BYTE v83[3]; // [rsp+F9h] [rbp-7Fh] BYREF
  int v84; // [rsp+FCh] [rbp-7Ch] BYREF
  __int64 v85; // [rsp+100h] [rbp-78h] BYREF
  PSRWLOCK v86; // [rsp+108h] [rbp-70h] BYREF
  int v87; // [rsp+110h] [rbp-68h] BYREF
  int v88; // [rsp+114h] [rbp-64h] BYREF
  int v89; // [rsp+118h] [rbp-60h] BYREF
  int v90; // [rsp+11Ch] [rbp-5Ch] BYREF
  __int64 v91; // [rsp+120h] [rbp-58h] BYREF
  __int64 Ptr; // [rsp+128h] [rbp-50h] BYREF
  __int64 v93; // [rsp+130h] [rbp-48h] BYREF
  __int64 v94; // [rsp+138h] [rbp-40h] BYREF
  __int64 v95; // [rsp+140h] [rbp-38h] BYREF
  __int64 v96; // [rsp+148h] [rbp-30h] BYREF
  __int64 v97; // [rsp+150h] [rbp-28h] BYREF
  __int64 v98; // [rsp+158h] [rbp-20h] BYREF
  __int64 v99; // [rsp+160h] [rbp-18h] BYREF
  __int64 v100; // [rsp+168h] [rbp-10h] BYREF
  __int64 v101; // [rsp+170h] [rbp-8h] BYREF
  __int64 v102; // [rsp+178h] [rbp+0h] BYREF
  __int64 v103; // [rsp+180h] [rbp+8h] BYREF
  __int64 v104; // [rsp+188h] [rbp+10h] BYREF
  __int64 v105; // [rsp+190h] [rbp+18h] BYREF
  __int64 v106; // [rsp+198h] [rbp+20h] BYREF
  _BYTE v107[8]; // [rsp+1A0h] [rbp+28h] BYREF
  volatile signed __int32 *v108; // [rsp+1A8h] [rbp+30h]
  _BYTE v109[8]; // [rsp+1B0h] [rbp+38h] BYREF
  volatile signed __int32 *v110; // [rsp+1B8h] [rbp+40h]
  _BYTE pExceptionObject[24]; // [rsp+1C8h] [rbp+50h] BYREF
  __int64 v112; // [rsp+1E0h] [rbp+68h] BYREF
  _BYTE v113[32]; // [rsp+1E8h] [rbp+70h] BYREF
  __int128 v114; // [rsp+208h] [rbp+90h] BYREF
  __int128 v115; // [rsp+218h] [rbp+A0h]
  wil::details::in1diag3 *retaddr; // [rsp+260h] [rbp+E8h]

  v86 = a4;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl) )
  {
    if ( a3 )
    {
      v12 = a3 - 1;
      if ( v12 )
      {
        if ( v12 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)v109, "Unknown provider type");
          throw (std::logic_error *)v109;
        }
        v13 = L"Powershell";
      }
      else
      {
        v13 = L"Executable";
      }
    }
    else
    {
      v13 = L"WindowsUpdate";
    }
    v114 = 0;
    v115 = 0;
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    std::wstring::_Construct<1,wchar_t const *>(&v114, v13, v14);
    v15 = a1 + 272;
    v16 = *(_QWORD *)(a1 + 272);
    v17 = *(_DWORD *)(v16 + 72);
    if ( v17 < 0 && (v18 = (int *)(v16 + 80), v17 == v18[2]) )
    {
      v19 = (_DWORD **)(a1 + 272);
      if ( v18 )
      {
        v85 = 0;
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
          a1,
          &v85);
        **(_DWORD **)v15 = 2;
        if ( v85 )
          ReleaseSRWLockExclusive((PSRWLOCK)v85);
        v20 = Windows::Telemetry::BaseCore::Provider();
        v22 = (int)v20;
        if ( *(_DWORD *)v20 <= 5u )
          goto LABEL_62;
        if ( (*((_QWORD *)v20 + 2) & 0x800000000000LL) == 0 )
          goto LABEL_62;
        v21 = (void *)(*((_QWORD *)v20 + 3) & 0x800000000000LL);
        if ( v21 != *((void **)v20 + 3) )
          goto LABEL_62;
        v112 = (__int64)"1507.2603.28012.0";
        v23 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v113);
        if ( v23[3] > 0xFu )
          v23 = (_QWORD *)*v23;
        v100 = (__int64)v23;
        v101 = a8;
        v102 = a9;
        System = SystemInterface::Providers::GetSystem(v109);
        v25 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
        v26 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v25 + 96LL))(v25, v107);
        v27 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 8LL))(*v26);
        if ( v27 )
        {
          v28 = v27 - 1;
          if ( v28 )
          {
            if ( v28 != 1 )
            {
              std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
              throw (std::logic_error *)pExceptionObject;
            }
            v29 = L"Internet";
          }
          else
          {
            v29 = L"local only";
          }
        }
        else
        {
          v29 = L"none";
        }
        v103 = (__int64)v29;
        v82 = a6;
        v83[0] = a5;
        v86 = (PSRWLOCK)v86->Ptr;
        v30 = &v114;
        if ( *((_QWORD *)&v115 + 1) > 7u )
          v30 = (__int128 *)v114;
        v104 = (__int64)v30;
        v105 = *a2;
        v106 = *((_QWORD *)v18 + 15);
        v98 = *((_QWORD *)v18 + 14);
        v87 = v18[26];
        v99 = *((_QWORD *)v18 + 12);
        v91 = *((_QWORD *)v18 + 11);
        v88 = v18[20];
        Ptr = *((_QWORD *)v18 + 9);
        v89 = v18[8];
        v93 = *((_QWORD *)v18 + 3);
        v90 = *v18;
        v94 = *((_QWORD *)v18 + 16);
        v84 = v18[16];
        v95 = *((_QWORD *)v18 + 7);
        LODWORD(v85) = v18[2];
        v96 = 0x1000000;
        v97 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v22,
          (int)&byte_14049AF67,
          *(_DWORD *)v15 + 8,
          (__int64)&v97,
          (__int64)&v96,
          (__int64)&v85,
          (__int64)&v95,
          (__int64)&v84,
          (__int64)&v94,
          (__int64)&v90,
          (__int64)&v93,
          (__int64)&v89,
          (__int64)&Ptr,
          (__int64)&v88,
          (__int64)&v91,
          (__int64)&v99,
          (__int64)&v87,
          (__int64)&v98,
          (__int64)&v106,
          (__int64)&v105,
          (__int64)&v104,
          (__int64)&v86,
          (__int64)v83,
          (__int64)&v82,
          (__int64)&v103,
          (__int64)&v102,
          (__int64)&v101,
          (__int64)&v100,
          (__int64)&v112);
        v31 = v108;
        if ( v108 )
        {
          if ( _InterlockedExchangeAdd(v108 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
            if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
          }
        }
        v32 = v110;
        if ( v110 )
        {
          if ( _InterlockedExchangeAdd(v110 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
            if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
          }
        }
LABEL_61:
        std::string::_Tidy_deallocate(v113);
LABEL_62:
        if ( *(_DWORD *)(a1 + 312) )
        {
          v46 = (__int64 **)(a1 + 288);
          if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
            wil::details::in1diag3::Log_Hr(retaddr, v21, v47, (const char *)0x8007029CLL, v81);
          *(_DWORD *)(a1 + 312) = 0;
          v48 = *v46;
          while ( 1 )
          {
            v49 = *v48;
            if ( !*v48 )
              break;
            if ( (__int64 **)v49 == v46 )
            {
              *v48 = *(_QWORD *)(a1 + 304);
              break;
            }
            v48 = (__int64 *)(v49 + 16);
            *v46 = (__int64 *)(v49 + 16);
          }
          *v46 = 0;
        }
        return (const struct _tlgProvider_t *)std::wstring::~wstring(&v114, v21);
      }
    }
    else
    {
      v19 = (_DWORD **)(a1 + 272);
    }
    v85 = 0;
    wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &v85);
    **v19 = 2;
    if ( v85 )
      ReleaseSRWLockExclusive((PSRWLOCK)v85);
    v33 = Windows::Telemetry::BaseCore::Provider();
    v34 = (int)v33;
    if ( *(_DWORD *)v33 <= 5u
      || (*((_QWORD *)v33 + 2) & 0x800000000000LL) == 0
      || (*((_QWORD *)v33 + 3) & 0x800000000000LL) != *((_QWORD *)v33 + 3) )
    {
      goto LABEL_62;
    }
    v97 = (__int64)"1507.2603.28012.0";
    v35 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v113);
    if ( v35[3] > 0xFu )
      v35 = (_QWORD *)*v35;
    v96 = (__int64)v35;
    v95 = a8;
    v94 = a9;
    v36 = SystemInterface::Providers::GetSystem(v107);
    v37 = *(_QWORD *)v36 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v36 + 8LL) + 4LL);
    v38 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v37 + 96LL))(v37, v109);
    v39 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v38 + 8LL))(*v38);
    if ( v39 )
    {
      v40 = v39 - 1;
      if ( v40 )
      {
        if ( v40 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
          throw (std::logic_error *)pExceptionObject;
        }
        v41 = L"Internet";
      }
      else
      {
        v41 = L"local only";
      }
    }
    else
    {
      v41 = L"none";
    }
    v93 = (__int64)v41;
    v83[0] = a6;
    v82 = a5;
    Ptr = (__int64)v86->Ptr;
    v42 = &v114;
    if ( *((_QWORD *)&v115 + 1) > 7u )
      v42 = (__int128 *)v114;
    v91 = (__int64)v42;
    v99 = *a2;
    LODWORD(v85) = GetCurrentThreadId();
    v43 = *(_DWORD **)v15;
    v84 = *(_DWORD *)(*(_QWORD *)v15 + 72LL);
    v98 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v34,
      (int)&word_14049AADA,
      (_DWORD)v43 + 8,
      (__int64)&v98,
      (__int64)&v84,
      (__int64)&v85,
      (__int64)&v99,
      (__int64)&v91,
      (__int64)&Ptr,
      (__int64)&v82,
      (__int64)v83,
      (__int64)&v93,
      (__int64)&v94,
      (__int64)&v95,
      (__int64)&v96,
      (__int64)&v97);
    v44 = v110;
    if ( v110 )
    {
      if ( _InterlockedExchangeAdd(v110 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
        if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
      }
    }
    v45 = v108;
    if ( v108 )
    {
      if ( _InterlockedExchangeAdd(v108 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
        if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
      }
    }
    goto LABEL_61;
  }
  v51 = a1 + 272;
  v52 = *(_QWORD *)(a1 + 272);
  v53 = *(_DWORD *)(v52 + 72);
  if ( v53 < 0 && (v54 = (int *)(v52 + 80), v53 == v54[2]) )
  {
    v55 = (_DWORD **)(a1 + 272);
    if ( v54 )
    {
      v86 = 0;
      wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        a1,
        &v86);
      **(_DWORD **)v51 = 2;
      if ( v86 )
        ReleaseSRWLockExclusive(v86);
      result = Windows::Telemetry::BaseCore::Provider();
      v56 = (int)result;
      if ( *(_DWORD *)result > 5u
        && (*((_QWORD *)result + 2) & 0x800000000000LL) != 0
        && (*((_QWORD *)result + 3) & 0x800000000000LL) == *((_QWORD *)result + 3) )
      {
        v97 = (__int64)"1507.2603.28012.0";
        v57 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v113);
        if ( v57[3] > 0xFu )
          v57 = (_QWORD *)*v57;
        v96 = (__int64)v57;
        v95 = a8;
        v94 = a9;
        v58 = SystemInterface::Providers::GetSystem(v107);
        v59 = *(_QWORD *)v58 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v58 + 8LL) + 4LL);
        v60 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v59 + 96LL))(v59, v109);
        v61 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v60 + 8LL))(*v60);
        if ( v61 )
        {
          v62 = v61 - 1;
          if ( v62 )
          {
            if ( v62 != 1 )
            {
              std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
              throw (std::logic_error *)pExceptionObject;
            }
            v63 = L"Internet";
          }
          else
          {
            v63 = L"local only";
          }
        }
        else
        {
          v63 = L"none";
        }
        v93 = (__int64)v63;
        v83[0] = a6;
        v82 = a5;
        Ptr = *a2;
        v91 = *((_QWORD *)v54 + 15);
        v99 = *((_QWORD *)v54 + 14);
        LODWORD(v85) = v54[26];
        v98 = *((_QWORD *)v54 + 12);
        v106 = *((_QWORD *)v54 + 11);
        v84 = v54[20];
        v105 = *((_QWORD *)v54 + 9);
        v90 = v54[8];
        v104 = *((_QWORD *)v54 + 3);
        v89 = *v54;
        v103 = *((_QWORD *)v54 + 16);
        v88 = v54[16];
        v102 = *((_QWORD *)v54 + 7);
        v87 = v54[2];
        v101 = 0x1000000;
        v100 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v56,
          (int)&byte_14049ABB1,
          *(_DWORD *)v51 + 8,
          (__int64)&v100,
          (__int64)&v101,
          (__int64)&v87,
          (__int64)&v102,
          (__int64)&v88,
          (__int64)&v103,
          (__int64)&v89,
          (__int64)&v104,
          (__int64)&v90,
          (__int64)&v105,
          (__int64)&v84,
          (__int64)&v106,
          (__int64)&v98,
          (__int64)&v85,
          (__int64)&v99,
          (__int64)&v91,
          (__int64)&Ptr,
          (__int64)&v82,
          (__int64)v83,
          (__int64)&v93,
          (__int64)&v94,
          (__int64)&v95,
          (__int64)&v96,
          (__int64)&v97);
        v64 = v110;
        if ( v110 )
        {
          if ( _InterlockedExchangeAdd(v110 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v64)(v64);
            if ( _InterlockedExchangeAdd(v64 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v64 + 8LL))(v64);
          }
        }
        v65 = v108;
        if ( v108 )
        {
          if ( _InterlockedExchangeAdd(v108 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
            if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
          }
        }
LABEL_120:
        result = (const struct _tlgProvider_t *)std::string::_Tidy_deallocate(v113);
        goto LABEL_121;
      }
      goto LABEL_121;
    }
  }
  else
  {
    v55 = (_DWORD **)(a1 + 272);
  }
  v86 = 0;
  wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v86);
  **v55 = 2;
  if ( v86 )
    ReleaseSRWLockExclusive(v86);
  result = Windows::Telemetry::BaseCore::Provider();
  v66 = (int)result;
  if ( *(_DWORD *)result > 5u
    && (*((_QWORD *)result + 2) & 0x800000000000LL) != 0
    && (*((_QWORD *)result + 3) & 0x800000000000LL) == *((_QWORD *)result + 3) )
  {
    v97 = (__int64)"1507.2603.28012.0";
    v67 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v113);
    if ( v67[3] > 0xFu )
      v67 = (_QWORD *)*v67;
    v96 = (__int64)v67;
    v95 = a8;
    v94 = a9;
    v68 = SystemInterface::Providers::GetSystem(v107);
    v69 = *(_QWORD *)v68 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v68 + 8LL) + 4LL);
    v70 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v69 + 96LL))(v69, v109);
    v71 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v70 + 8LL))(*v70);
    if ( v71 )
    {
      v72 = v71 - 1;
      if ( v72 )
      {
        if ( v72 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
          throw (std::logic_error *)pExceptionObject;
        }
        v73 = L"Internet";
      }
      else
      {
        v73 = L"local only";
      }
    }
    else
    {
      v73 = L"none";
    }
    v93 = (__int64)v73;
    v83[0] = a6;
    v82 = a5;
    Ptr = *a2;
    LODWORD(v85) = GetCurrentThreadId();
    v74 = *(_DWORD **)v51;
    v84 = *(_DWORD *)(*(_QWORD *)v51 + 72LL);
    v91 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v66,
      (int)&unk_14049AD40,
      (_DWORD)v74 + 8,
      (__int64)&v91,
      (__int64)&v84,
      (__int64)&v85,
      (__int64)&Ptr,
      (__int64)&v82,
      (__int64)v83,
      (__int64)&v93,
      (__int64)&v94,
      (__int64)&v95,
      (__int64)&v96,
      (__int64)&v97);
    v75 = v110;
    if ( v110 )
    {
      if ( _InterlockedExchangeAdd(v110 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
        if ( _InterlockedExchangeAdd(v75 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
      }
    }
    v76 = v108;
    if ( v108 )
    {
      if ( _InterlockedExchangeAdd(v108 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
        if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
      }
    }
    goto LABEL_120;
  }
LABEL_121:
  if ( *(_DWORD *)(a1 + 312) )
  {
    v77 = (const struct _tlgProvider_t ***)(a1 + 288);
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v78, v79, (const char *)0x8007029CLL, v81);
    *(_DWORD *)(a1 + 312) = 0;
    v80 = *v77;
    while ( 1 )
    {
      result = *v80;
      if ( !*v80 )
        break;
      if ( result == (const struct _tlgProvider_t *)v77 )
      {
        result = *(const struct _tlgProvider_t **)(a1 + 304);
        *v80 = result;
        break;
      }
      v80 = (const struct _tlgProvider_t **)((char *)result + 16);
      *v77 = (const struct _tlgProvider_t **)((char *)result + 16);
    }
    *v77 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140287530  mov     rax, rsp
0x140287533  mov     [rax+10h], rbx
0x140287537  mov     [rax+18h], rsi
0x14028753b  mov     [rax+20h], rdi
0x14028753f  push    rbp
0x140287540  push    r12
0x140287542  push    r13
0x140287544  push    r14
0x140287546  push    r15
0x140287548  lea     rbp, [rax-0E8h]
0x14028754f  sub     rsp, 230h
0x140287556  mov     rax, cs:__security_cookie
0x14028755d  xor     rax, rsp
0x140287560  mov     [rbp+0E0h+var_30], rax
0x140287567  mov     [rbp+0E0h+var_150], r9
0x14028756b  mov     ebx, r8d
0x14028756e  mov     r13, rdx
0x140287571  mov     rsi, rcx
0x140287574  mov     rdi, [rbp+0E0h+arg_30]
0x14028757b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl(void)'::`2'::impl
0x140287582  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(void)
0x140287587  xor     r12d, r12d
0x14028758a  test    al, al
0x14028758c  jz      loc_140287C8F
0x140287592  test    ebx, ebx
0x140287594  jz      short loc_1402875B6
0x140287596  sub     ebx, 1
0x140287599  jz      short loc_1402875AD
0x14028759b  cmp     ebx, 1
0x14028759e  jnz     loc_1402882D6
0x1402875a4  lea     rdx, aPowershell_0; "Powershell"
0x1402875ab  jmp     short loc_1402875BD
0x1402875ad  lea     rdx, aExecutable; "Executable"
0x1402875b4  jmp     short loc_1402875BD
0x1402875b6  lea     rdx, aWindowsupdate_0; "WindowsUpdate"
0x1402875bd  xorps   xmm0, xmm0
0x1402875c0  movups  [rbp+0E0h+var_50], xmm0
0x1402875c7  xorps   xmm1, xmm1
0x1402875ca  movdqu  [rbp+0E0h+var_40], xmm1
0x1402875d2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1402875d6  mov     r8, rbx
0x1402875d9  inc     r8
0x1402875dc  cmp     [rdx+r8*2], r12w
0x1402875e1  jnz     short loc_1402875D9
0x1402875e3  lea     rcx, [rbp+0E0h+var_50]
0x1402875ea  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402875ef  nop
0x1402875f0  lea     r15, [rsi+110h]
0x1402875f7  mov     r12, [r15]
0x1402875fa  mov     eax, [r12+48h]
0x1402875ff  test    eax, eax
0x140287601  jns     loc_1402879A3
0x140287607  add     r12, 50h ; 'P'
0x14028760b  cmp     eax, [r12+8]
0x140287610  jnz     loc_1402879A3
0x140287616  mov     r14, r15
0x140287619  test    r12, r12
0x14028761c  jz      loc_1402879A6
0x140287622  mov     [rbp+0E0h+var_158], 0
0x14028762a  lea     rdx, [rbp+0E0h+var_158]
0x14028762e  mov     rcx, rsi
0x140287631  call    ?LockExclusive@?$ActivityBase@VBaseCore@Telemetry@Windows@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140287636  mov     rax, [r15]
0x140287639  mov     dword ptr [rax], 2
0x14028763f  mov     rcx, [rbp+0E0h+var_158]; SRWLock
0x140287643  test    rcx, rcx
0x140287646  jz      short loc_14028764E
0x140287648  call    cs:__imp_ReleaseSRWLockExclusive
0x14028764e  call    ?Provider@BaseCore@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::BaseCore::Provider(void)
0x140287653  mov     r14, rax
0x140287656  cmp     dword ptr [rax], 5
0x140287659  jbe     loc_140287C21
0x14028765f  mov     r8, 800000000000h
0x140287669  test    [rax+10h], r8
0x14028766d  jz      loc_140287C21
0x140287673  mov     rdx, [rax+18h]
0x140287677  and     rdx, r8
0x14028767a  cmp     rdx, [rax+18h]
0x14028767e  jnz     loc_140287C21
0x140287684  lea     rax, a15072603280120; "1507.2603.28012.0"
0x14028768b  mov     [rbp+0E0h+var_78], rax
0x14028768f  mov     rax, [rdi]
0x140287692  lea     rdx, [rbp+0E0h+var_70]
0x140287696  mov     rcx, rdi
0x140287699  mov     rax, [rax+8]
0x14028769d  call    _guard_dispatch_icall
0x1402876a2  nop
0x1402876a3  cmp     qword ptr [rax+18h], 0Fh
0x1402876a8  jbe     short loc_1402876AD
0x1402876aa  mov     rax, [rax]
0x1402876ad  mov     [rbp+0E0h+var_F0], rax
0x1402876b1  mov     rax, [rbp+0E0h+arg_38]
0x1402876b8  mov     [rbp+0E0h+var_E8], rax
0x1402876bc  mov     rax, [rbp+0E0h+arg_40]
0x1402876c3  mov     [rbp+0E0h+var_E0], rax
0x1402876c7  lea     rcx, [rbp+0E0h+var_A8]
0x1402876cb  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1402876d0  nop
0x1402876d1  mov     rdx, [rax]
0x1402876d4  mov     rax, [rdx+8]
0x1402876d8  movsxd  rcx, dword ptr [rax+4]
0x1402876dc  add     rdx, 8
0x1402876e0  add     rcx, rdx
0x1402876e3  mov     rax, [rcx]
0x1402876e6  lea     rdx, [rbp+0E0h+var_B8]
0x1402876ea  mov     rax, [rax+60h]
0x1402876ee  call    _guard_dispatch_icall
0x1402876f3  nop
0x1402876f4  mov     rcx, [rax]
0x1402876f7  mov     rax, [rcx]
0x1402876fa  mov     rax, [rax+8]
0x1402876fe  call    _guard_dispatch_icall
0x140287703  test    eax, eax
0x140287705  jz      short loc_140287727
0x140287707  sub     eax, 1
0x14028770a  jz      short loc_14028771E
0x14028770c  cmp     eax, 1
0x14028770f  jnz     loc_1402882F7
0x140287715  lea     rax, aInternet; "Internet"
0x14028771c  jmp     short loc_14028772E
0x14028771e  lea     rax, aLocalOnly; "local only"
0x140287725  jmp     short loc_14028772E
0x140287727  lea     rax, aNone; "none"
0x14028772e  mov     [rbp+0E0h+var_D8], rax
0x140287732  mov     al, [rbp+0E0h+arg_28]
0x140287738  mov     byte ptr [rbp+0E0h+var_160], al
0x14028773b  mov     al, [rbp+0E0h+arg_20]
0x140287741  mov     byte ptr [rbp+0E0h+var_160+1], al
0x140287744  mov     rax, [rbp+0E0h+var_150]
0x140287748  mov     rax, [rax]
0x14028774b  mov     [rbp+0E0h+var_150], rax
0x14028774f  lea     rax, [rbp+0E0h+var_50]
0x140287756  cmp     qword ptr [rbp+0E0h+var_40+8], 7
0x14028775e  cmova   rax, qword ptr [rbp+0E0h+var_50]
0x140287766  mov     [rbp+0E0h+var_D0], rax
0x14028776a  mov     rax, [r13+0]
0x14028776e  mov     [rbp+0E0h+var_C8], rax
0x140287772  mov     rax, [r12+78h]
0x140287777  mov     [rbp+0E0h+var_C0], rax
0x14028777b  mov     rax, [r12+70h]
0x140287780  mov     [rbp+0E0h+var_100], rax
0x140287784  mov     eax, [r12+68h]
0x140287789  mov     dword ptr [rbp+0E0h+var_148], eax
0x14028778c  mov     rax, [r12+60h]
0x140287791  mov     [rbp+0E0h+var_F8], rax
0x140287795  mov     rax, [r12+58h]
0x14028779a  mov     [rbp+0E0h+var_138], rax
0x14028779e  mov     eax, [r12+50h]
0x1402877a3  mov     dword ptr [rbp+0E0h+var_148+4], eax
0x1402877a6  mov     rax, [r12+48h]
0x1402877ab  mov     [rbp+0E0h+var_130], rax
0x1402877af  mov     eax, [r12+20h]
0x1402877b4  mov     dword ptr [rbp+0E0h+var_140], eax
0x1402877b7  mov     rax, [r12+18h]
0x1402877bc  mov     [rbp+0E0h+var_128], rax
0x1402877c0  mov     eax, [r12]
0x1402877c4  mov     dword ptr [rbp+0E0h+var_140+4], eax
0x1402877c7  mov     rax, [r12+80h]
0x1402877cf  mov     [rbp+0E0h+var_120], rax
0x1402877d3  mov     eax, [r12+40h]
0x1402877d8  mov     dword ptr [rbp+0E0h+var_160+4], eax
0x1402877db  mov     rax, [r12+38h]
0x1402877e0  mov     [rbp+0E0h+var_118], rax
0x1402877e4  mov     eax, [r12+8]
0x1402877e9  mov     dword ptr [rbp+0E0h+var_158], eax
0x1402877ec  mov     eax, 1000000h
0x1402877f1  mov     [rbp+0E0h+var_110], rax
0x1402877f5  mov     [rbp+0E0h+var_108], rax
0x1402877f9  mov     r8, [r15]
0x1402877fc  add     r8, 8; int
0x140287800  lea     rax, [rbp+0E0h+var_78]
0x140287804  mov     [rsp+250h+var_168], rax; __int64
0x14028780c  lea     rax, [rbp+0E0h+var_F0]
0x140287810  mov     [rsp+250h+var_170], rax; __int64
0x140287818  lea     rax, [rbp+0E0h+var_E8]
0x14028781c  mov     [rsp+250h+var_178], rax; __int64
0x140287824  lea     rax, [rbp+0E0h+var_E0]
0x140287828  mov     [rsp+250h+var_180], rax; __int64
0x140287830  lea     rax, [rbp+0E0h+var_D8]
0x140287834  mov     [rsp+250h+var_188], rax; __int64
0x14028783c  lea     rax, [rbp+0E0h+var_160]
0x140287840  mov     [rsp+250h+var_190], rax; __int64
0x140287848  lea     rax, [rbp+0E0h+var_160+1]
0x14028784c  mov     [rsp+250h+var_198], rax; __int64
0x140287854  lea     rax, [rbp+0E0h+var_150]
0x140287858  mov     [rsp+250h+var_1A0], rax; __int64
0x140287860  lea     rax, [rbp+0E0h+var_D0]
0x140287864  mov     [rsp+250h+var_1A8], rax; __int64
0x14028786c  lea     rax, [rbp+0E0h+var_C8]
0x140287870  mov     [rsp+250h+var_1B0], rax; __int64
0x140287878  lea     rax, [rbp+0E0h+var_C0]
0x14028787c  mov     [rsp+250h+var_1B8], rax; __int64
0x140287884  lea     rax, [rbp+0E0h+var_100]
0x140287888  mov     [rsp+250h+var_1C0], rax; __int64
0x140287890  lea     rax, [rbp+0E0h+var_148]
0x140287894  mov     [rsp+250h+var_1C8], rax; __int64
0x14028789c  lea     rax, [rbp+0E0h+var_F8]
0x1402878a0  mov     [rsp+250h+var_1D0], rax; __int64
0x1402878a8  lea     rax, [rbp+0E0h+var_138]
0x1402878ac  mov     [rsp+250h+var_1D8], rax; __int64
0x1402878b1  lea     rax, [rbp+0E0h+var_148+4]
0x1402878b5  mov     [rsp+250h+var_1E0], rax; __int64
0x1402878ba  lea     rax, [rbp+0E0h+var_130]
0x1402878be  mov     [rsp+250h+var_1E8], rax; __int64
0x1402878c3  lea     rax, [rbp+0E0h+var_140]
0x1402878c7  mov     [rsp+250h+var_1F0], rax; __int64
0x1402878cc  lea     rax, [rbp+0E0h+var_128]
0x1402878d0  mov     [rsp+250h+var_1F8], rax; __int64
0x1402878d5  lea     rax, [rbp+0E0h+var_140+4]
0x1402878d9  mov     [rsp+250h+var_200], rax; __int64
0x1402878de  lea     rax, [rbp+0E0h+var_120]
0x1402878e2  mov     [rsp+250h+var_208], rax; __int64
0x1402878e7  lea     rax, [rbp+0E0h+var_160+4]
0x1402878eb  mov     [rsp+250h+var_210], rax; __int64
0x1402878f0  lea     rax, [rbp+0E0h+var_118]
0x1402878f4  mov     [rsp+250h+var_218], rax; __int64
0x1402878f9  lea     rax, [rbp+0E0h+var_158]
0x1402878fd  mov     [rsp+250h+var_220], rax; __int64
0x140287902  lea     rax, [rbp+0E0h+var_110]
0x140287906  mov     [rsp+250h+var_228], rax; __int64
0x14028790b  lea     rax, [rbp+0E0h+var_108]
0x14028790f  mov     [rsp+250h+var_230], rax; __int64
0x140287914  lea     rdx, byte_14049AF67; int
0x14028791b  mov     rcx, r14; int
0x14028791e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U4@U?$_tlgWrapperByVal@$00@@U5@U4@U1@U4@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456666AEBU?$_tlgWrapperByVal@$00@@763655@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x140287923  nop
0x140287924  mov     rdi, [rbp+0E0h+var_B0]
0x140287928  test    rdi, rdi
0x14028792b  jz      short loc_140287961
0x14028792d  mov     eax, ebx
0x14028792f  lock xadd [rdi+8], eax
0x140287934  add     eax, ebx
0x140287936  jnz     short loc_140287961
0x140287938  mov     rax, [rdi]
0x14028793b  mov     rcx, rdi
0x14028793e  mov     rax, [rax]
0x140287941  call    _guard_dispatch_icall
0x140287946  mov     eax, ebx
0x140287948  lock xadd [rdi+0Ch], eax
0x14028794d  add     eax, ebx
0x14028794f  jnz     short loc_140287961
0x140287951  mov     rax, [rdi]
0x140287954  mov     rcx, rdi
0x140287957  mov     rax, [rax+8]
0x14028795b  call    _guard_dispatch_icall
0x140287960  nop
0x140287961  mov     rdi, [rbp+0E0h+var_A0]
0x140287965  test    rdi, rdi
0x140287968  jz      short loc_14028799E
0x14028796a  mov     eax, ebx
0x14028796c  lock xadd [rdi+8], eax
0x140287971  add     eax, ebx
0x140287973  jnz     short loc_14028799E
0x140287975  mov     rax, [rdi]
0x140287978  mov     rcx, rdi
0x14028797b  mov     rax, [rax]
0x14028797e  call    _guard_dispatch_icall
0x140287983  mov     eax, ebx
0x140287985  lock xadd [rdi+0Ch], eax
0x14028798a  add     eax, ebx
0x14028798c  jnz     short loc_14028799E
0x14028798e  mov     rax, [rdi]
0x140287991  mov     rcx, rdi
0x140287994  mov     rax, [rax+8]
0x140287998  call    _guard_dispatch_icall
0x14028799d  nop
0x14028799e  jmp     loc_140287C18
0x1402879a3  mov     r14, r15
0x1402879a6  mov     [rbp+0E0h+var_158], 0
0x1402879ae  lea     rdx, [rbp+0E0h+var_158]
0x1402879b2  mov     rcx, rsi
0x1402879b5  call    ?LockExclusive@?$ActivityBase@VBaseCore@Telemetry@Windows@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1402879ba  mov     rax, [r14]
0x1402879bd  mov     dword ptr [rax], 2
0x1402879c3  mov     rcx, [rbp+0E0h+var_158]; SRWLock
0x1402879c7  test    rcx, rcx
0x1402879ca  jz      short loc_1402879D2
0x1402879cc  call    cs:__imp_ReleaseSRWLockExclusive
0x1402879d2  call    ?Provider@BaseCore@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::BaseCore::Provider(void)
0x1402879d7  mov     r14, rax
0x1402879da  cmp     dword ptr [rax], 5
0x1402879dd  jbe     loc_140287C21
0x1402879e3  mov     r8, 800000000000h
0x1402879ed  test    [rax+10h], r8
0x1402879f1  jz      loc_140287C21
0x1402879f7  mov     rcx, [rax+18h]
0x1402879fb  and     rcx, r8
0x1402879fe  cmp     rcx, [rax+18h]
0x140287a02  jnz     loc_140287C21
0x140287a08  lea     rax, a15072603280120; "1507.2603.28012.0"
0x140287a0f  mov     [rbp+0E0h+var_108], rax
0x140287a13  mov     rax, [rdi]
0x140287a16  lea     rdx, [rbp+0E0h+var_70]
0x140287a1a  mov     rcx, rdi
0x140287a1d  mov     rax, [rax+8]
0x140287a21  call    _guard_dispatch_icall
0x140287a26  nop
0x140287a27  cmp     qword ptr [rax+18h], 0Fh
0x140287a2c  jbe     short loc_140287A31
0x140287a2e  mov     rax, [rax]
  ... truncated ...
```
