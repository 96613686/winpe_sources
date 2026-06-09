# CAudioSessionManager::CreateAudioSession(IAudioProcess *,CAudioSessionInstanceId &,ulong,ulong,ulong,CAudioSession * *)

- ea: `0x18000fe60`
- end: `0x18001075d`
- name: `?CreateAudioSession@CAudioSessionManager@@QEAAJPEAUIAudioProcess@@AEAVCAudioSessionInstanceId@@KKKPEAPEAVCAudioSession@@@Z`
- size: `2301`
- prototype: `__int64 __usercall@<rax>(CAudioSessionManager *__hidden this@<rcx>, struct IAudioProcess *@<rdx>, struct CAudioSessionInstanceId *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int, struct CAudioSession **)`
- caller_count: `4`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800111e0`
- `0x180011d70`
- `0x180014ad0`
- `0x18007d700`

## callees

- `0x18000fe60`
- `0x1800126bc`
- `0x180013790`
- `0x180014160`
- `0x1800151fc`
- `0x180018d00`
- `0x18001b3d0`
- `0x18002f9ec`
- `0x18003323c`
- `0x180034abc`
- `0x1800470d0`
- `0x18004dd88`
- `0x18007a704`
- `0x1800ae06c`
- `0x1800cf8c0`
- `0x1800cfd60`
- `0x1800cfd9c`
- `0x1800d0764`
- `0x1800e5870`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180010113`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800101b8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180010113`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800101b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000febd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ff28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010006`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010311`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000febd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ff28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010006`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010311`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ff03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ffa0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fffd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010054`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001051b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001064c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800106e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001071d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ff03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ffa0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fffd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010054`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001051b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001064c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800106e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001071d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ff0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001005c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ff0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001005c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010049`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ffc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ffc3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800103b3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800103b3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800103f6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800103f6`

## string_xrefs

- `0x18000ff86`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x1800101fa`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x1800102de`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x18001043a`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x1800106b8`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CAudioSessionManager::CreateAudioSession(
        union _RTL_RUN_ONCE *this,
        struct IAudioProcess *a2,
        struct CAudioSessionInstanceId *a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        struct CAudioSession **a7)
{
  struct _RTL_CRITICAL_SECTION *v10; // rsi
  struct _RTL_CRITICAL_SECTION *v11; // rdi
  CAudioSession *v12; // rbx
  int AudioSession; // eax
  DWORD LastError; // edi
  CAudioSession *v15; // r14
  struct _RTL_CRITICAL_SECTION *v16; // rdi
  unsigned int v17; // eax
  int v18; // eax
  unsigned int v19; // ebx
  const char *v20; // r9
  __int64 result; // rax
  DWORD v22; // ebx
  int v23; // r12d
  CAudioSession *v24; // rbx
  char *v25; // rax
  char *v26; // r14
  char *v27; // rax
  char *v28; // r14
  CAudioSession *v29; // rcx
  bool v30; // zf
  GUID v31; // xmm6
  char v32; // al
  struct CAudioSessionInstanceId *v33; // r14
  int v34; // eax
  unsigned int v35; // ebx
  void *v36; // rdx
  unsigned int v37; // r8d
  const char *v38; // r9
  _QWORD *i; // rbx
  int v40; // eax
  unsigned int v41; // r12d
  __int64 v42; // rcx
  CAudioSession *v43; // r14
  _QWORD *j; // rbx
  PVOID *v45; // rbx
  union _RTL_RUN_ONCE *v46; // rdx
  PVOID *Ptr; // rax
  union _RTL_RUN_ONCE v48; // rax
  _QWORD *v49; // rcx
  PVOID v50; // rcx
  struct CAudioSession *v51; // r14
  __int64 v52; // r14
  int v53; // r8d
  int v54; // r9d
  unsigned int v55; // eax
  int v56; // eax
  unsigned int v57; // esi
  int v58; // [rsp+20h] [rbp-128h]
  char v59; // [rsp+50h] [rbp-F8h]
  CAudioSession *v60; // [rsp+58h] [rbp-F0h] BYREF
  struct CAudioSessionInstanceId *v61; // [rsp+60h] [rbp-E8h] BYREF
  struct CAudioSession *v62; // [rsp+68h] [rbp-E0h] BYREF
  int v63[2]; // [rsp+70h] [rbp-D8h] BYREF
  WINBOOL fPending[2]; // [rsp+78h] [rbp-D0h] BYREF
  struct _RTL_CRITICAL_SECTION *v65; // [rsp+80h] [rbp-C8h]
  GUID v66; // [rsp+90h] [rbp-B8h] BYREF
  struct CAudioSession **v67; // [rsp+A0h] [rbp-A8h]
  CAudioSessionManager *v68; // [rsp+A8h] [rbp-A0h]
  CAudioSession **v69; // [rsp+B0h] [rbp-98h]
  char v70; // [rsp+B8h] [rbp-90h]
  CAudioSessionManager *v71; // [rsp+C0h] [rbp-88h]
  GUID *v72; // [rsp+C8h] [rbp-80h]
  char v73; // [rsp+D0h] [rbp-78h]
  struct _RTL_CRITICAL_SECTION *v74; // [rsp+D8h] [rbp-70h]
  union _RTL_RUN_ONCE *v75; // [rsp+E0h] [rbp-68h] BYREF
  int v76; // [rsp+E8h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v63[0] = a4;
  v61 = a3;
  v67 = a7;
  *a7 = 0;
  v10 = (struct _RTL_CRITICAL_SECTION *)&this[1];
  EnterCriticalSection((LPCRITICAL_SECTION)&this[1]);
  v11 = v10;
  v65 = v10;
  v12 = 0;
  v62 = 0;
  v60 = 0;
  AudioSession = CAudioSessionManager::FindAudioSession((CAudioSessionManager *)this, a3, &v60);
  try
  {
    if ( AudioSession < 0 )
    {
      v15 = v60;
    }
    else
    {
      if ( v10 )
      {
        LastError = GetLastError();
        LeaveCriticalSection(v10);
        SetLastError(LastError);
      }
      v65 = 0;
      v15 = v60;
      v16 = (struct _RTL_CRITICAL_SECTION *)((char *)v60 + 544);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v60 + 544));
      *(_QWORD *)fPending = v16;
      if ( (*(unsigned int (__fastcall **)(__int64))(*((_QWORD *)v15 + 1) + 32LL))((__int64)v15 + 8) != 2 )
      {
        v17 = (*(__int64 (__fastcall **)(struct IAudioProcess *))(*(_QWORD *)a2 + 40LL))(a2);
        if ( !CAudioSession::IsLinkedToProcess(v15, v17) )
        {
          v18 = CAudioSession::RegisterOwnerProcess(v15, a2);
          v19 = v18;
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC7,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosessionmanager.cpp",
              (const char *)(unsigned int)v18,
              v58);
            if ( v16 )
              LeaveCriticalSection(v16);
            if ( v15 )
              (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)v15 + 16LL))(v15);
            return v19;
          }
        }
        *((_QWORD *)v15 + 40) = GetTickCount64();
        CAudioSession::StartInactiveTimer(v15);
        v12 = v15;
        v62 = v15;
        if ( v15 )
          (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)v15 + 8LL))(v15);
      }
      if ( v16 )
        LeaveCriticalSection(v16);
      EnterCriticalSection(v10);
      v11 = v10;
      v65 = v10;
    }
    v59 = 1;
    if ( v15 )
      (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v12 )
    {
      if ( (v63[0] & 0x20) != 0 )
        *((_DWORD *)v12 + 102) = 1;
    }
    else
    {
      if ( v10 )
      {
        v22 = GetLastError();
        LeaveCriticalSection(v11);
        SetLastError(v22);
      }
      v11 = 0;
      v65 = 0;
      v60 = 0;
      v23 = v63[0];
      v24 = 0;
      if ( (v63[0] & 8) != 0 )
      {
        v25 = (char *)operator new[](0x3E0u, (const struct std::nothrow_t *)&std::nothrow);
        v26 = v25;
        if ( v25 )
        {
          memset_0(v25, 0, 0x3E0u);
          CAudioSession::CAudioSession((CAudioSession *)v26);
          *(_QWORD *)v26 = &CPerStreamVolumeAudioSession::`vftable'{for `IInspectable'};
          *((_QWORD *)v26 + 1) = &CAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWeakReferenceSource,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>'};
          *((_QWORD *)v26 + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>::`vftable'{for `IWeakReferenceSource'};
          *((_QWORD *)v26 + 3) = &CAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>'};
          *((_QWORD *)v26 + 4) = &CAudioSession::`vftable'{for `IAudioSessionDuckingControl'};
          *((_QWORD *)v26 + 5) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'};
          v26[920] = 1;
          *((_QWORD *)v26 + 116) = 0;
          InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 936), 0, 0);
          *((_DWORD *)v26 + 244) = 0;
          *((_QWORD *)v26 + 123) = 0;
          v24 = (CAudioSession *)v26;
        }
      }
      else
      {
        v27 = (char *)operator new[](0x3D0u, (const struct std::nothrow_t *)&std::nothrow);
        v28 = v27;
        if ( v27 )
        {
          memset_0(v27, 0, 0x3D0u);
          CAudioSession::CAudioSession((CAudioSession *)v28);
          *(_QWORD *)v28 = &CPerEndpointVolumeAudioSession::`vftable'{for `IInspectable'};
          *((_QWORD *)v28 + 1) = &CPerEndpointVolumeAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWeakReferenceSource,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>'};
          *((_QWORD *)v28 + 2) = &CPerEndpointVolumeAudioSession::`vftable'{for `IWeakReferenceSource'};
          *((_QWORD *)v28 + 3) = &CPerEndpointVolumeAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>'};
          *((_QWORD *)v28 + 4) = &CPerEndpointVolumeAudioSession::`vftable'{for `IAudioSessionDuckingControl'};
          *((_QWORD *)v28 + 5) = &CPerEndpointVolumeAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'};
          *((_QWORD *)v28 + 115) = &CPerEndpointVolumeAudioSession::`vftable';
          InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v28 + 928), 0, 0);
          *((_QWORD *)v28 + 121) = 0;
          v24 = (CAudioSession *)v28;
        }
      }
      v29 = v60;
      v30 = v60 == 0;
      v60 = v24;
      if ( !v30 )
        (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)v29 + 16LL))(v29);
      if ( !v60 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosessionmanager.cpp",
          (const char *)0x8007000ELL,
          v58);
        if ( v60 )
          (*(void (__fastcall **)(CAudioSession *, _QWORD))(*(_QWORD *)v60 + 16LL))(v60, *(_QWORD *)v60);
        return 2147942414LL;
      }
      v31 = GUID_00000000_0000_0000_0000_000000000000;
      if ( (v23 & 4) != 0 )
      {
        v33 = v61;
      }
      else
      {
        v32 = (*(__int64 (__fastcall **)(struct IAudioProcess *))(*(_QWORD *)a2 + 448LL))(a2);
        v33 = v61;
        if ( !v32 )
          v31 = *(GUID *)(*(__int64 (__fastcall **)(struct IAudioProcess *, union _RTL_RUN_ONCE **, char *))(*(_QWORD *)a2 + 464LL))(
                           a2,
                           &v75,
                           (char *)v61 + 24);
      }
      v66 = v31;
      v58 = v23;
      v34 = (*(__int64 (__fastcall **)(CAudioSession *, union _RTL_RUN_ONCE *, struct IAudioProcess *, struct CAudioSessionInstanceId *))(*(_QWORD *)v60 + 168LL))(
              v60,
              this,
              a2,
              v33);
      v35 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x119,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosessionmanager.cpp",
          (const char *)(unsigned int)v34,
          v23);
        if ( v60 )
          (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)v60 + 16LL))(v60);
        return v35;
      }
      EnterCriticalSection(v10);
      v74 = v10;
      v62 = 0;
      if ( (int)CAudioSessionManager::FindAudioSession((CAudioSessionManager *)this, v33, &v62) >= 0 )
      {
        v12 = v62;
      }
      else
      {
        std::_Hash<std::_Umap_traits<CAudioSessionInstanceId,wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>,std::_Uhash_compare<CAudioSessionInstanceId,std::hash<CAudioSessionInstanceId>,std::equal_to<CAudioSessionInstanceId>>,std::allocator<std::pair<CAudioSessionInstanceId const,wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>>>,0>>::emplace<CAudioSessionInstanceId &,wil::com_ptr_t<CAudioSession,wil::err_returncode_policy> &>(
          &this[6],
          &v66,
          v33,
          &v60);
        v71 = (CAudioSessionManager *)this;
        v72 = &v66;
        v73 = 1;
        v68 = (CAudioSessionManager *)this;
        v69 = &v60;
        v70 = 1;
        v61 = (struct CAudioSessionInstanceId *)this;
        fPending[0] = 0;
        if ( !InitOnceBeginInitialize(this + 37, 0, fPending, 0) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, v36, v37, v38);
        if ( fPending[0] )
        {
          v75 = this + 37;
          v76 = 4;
          lambda_f00ad828a2d515e855b0de47f172bf9e_::operator()(&v61);
          InitOnceComplete(this + 37, 0, 0);
        }
        for ( i = this[36].Ptr; i; i = (_QWORD *)*i )
        {
          v40 = (*(__int64 (__fastcall **)(CAudioSession *, _QWORD))(*(_QWORD *)v60 + 152LL))(v60, i[1]);
          v41 = v40;
          if ( v40 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x12B,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosessionmanager.cpp",
              (const char *)(unsigned int)v40,
              v58);
            v43 = v60;
            for ( j = this[36].Ptr; j; j = (_QWORD *)*j )
              (*(void (__fastcall **)(CAudioSession *, _QWORD))(*(_QWORD *)v43 + 160LL))(v43, j[1]);
            v45 = *(PVOID **)&v66.Data1;
            v46 = (union _RTL_RUN_ONCE *)((char *)this[9].Ptr
                                        + 16
                                        * (std::_Uhash_compare<CAudioSessionInstanceId,std::hash<CAudioSessionInstanceId>,std::equal_to<CAudioSessionInstanceId>>::operator()<CAudioSessionInstanceId>(
                                             v42,
                                             *(_QWORD *)&v66.Data1 + 16LL)
                                         & (__int64)this[12].Ptr));
            Ptr = (PVOID *)v46->Ptr;
            if ( v46[1].Ptr == v45 )
            {
              if ( Ptr == v45 )
              {
                v48.Ptr = this[7].Ptr;
                v46->Ptr = v48.Ptr;
              }
              else
              {
                v48.Ptr = v45[1];
              }
              v46[1].Ptr = v48.Ptr;
            }
            else if ( Ptr == v45 )
            {
              v46->Ptr = *v45;
            }
            v49 = *v45;
            --this[8].Ptr;
            *(_QWORD *)v45[1] = v49;
            v49[1] = v45[1];
            v50 = v45[12];
            if ( v50 )
              (*(void (__fastcall **)(PVOID))(*(_QWORD *)v50 + 16LL))(v50);
            CAudioSessionInstanceId::~CAudioSessionInstanceId((CAudioSessionInstanceId *)(v45 + 2));
            operator delete(v45, (const struct std::nothrow_t *)0x68);
            if ( v10 )
              LeaveCriticalSection(v10);
            if ( v60 )
              (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)v60 + 16LL))(v60);
            if ( v62 )
              (*(void (__fastcall **)(struct CAudioSession *))(*(_QWORD *)v62 + 16LL))(v62);
            return v41;
          }
        }
        CAudioSessionManager::NotifyActiveSession((CAudioSessionManager *)this, v60, v37);
        v12 = v60;
        v51 = v62;
        v62 = v60;
        if ( v60 )
          (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)v60 + 8LL))(v60);
        if ( v51 )
          (*(void (__fastcall **)(struct CAudioSession *))(*(_QWORD *)v51 + 16LL))(v51);
        v70 = 0;
        v73 = 0;
        v52 = *((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
        if ( *(_DWORD *)v52 > 4u
          && (*(_QWORD *)(v52 + 16) & 0x200LL) != 0
          && (*(_QWORD *)(v52 + 24) & 0x200LL) == *(_QWORD *)(v52 + 24) )
        {
          fPending[0] = (*(__int64 (__fastcall **)(struct IAudioProcess *))(*(_QWORD *)a2 + 40LL))(a2);
          LODWORD(v61) = v63[0];
          *(_QWORD *)v63 = *((_QWORD *)v12 + 82);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v52,
            (unsigned int)&unk_1801A29D6,
            v53,
            v54,
            (__int64)v63,
            (__int64)&v61,
            (__int64)fPending);
        }
        v59 = 0;
      }
      if ( v10 )
        LeaveCriticalSection(v10);
      if ( v60 )
        (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)v60 + 16LL))(v60);
    }
    v55 = (*(__int64 (__fastcall **)(struct IAudioProcess *))(*(_QWORD *)a2 + 40LL))(a2);
    if ( CAudioSession::IsLinkedToProcess(v12, v55)
      || (v56 = CAudioSession::RegisterOwnerProcess(v12, a2), v57 = v56, v56 >= 0) )
    {
      if ( v59 )
        (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)v12 + 184LL))(v12);
      *v67 = v12;
      if ( v11 )
        LeaveCriticalSection(v11);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosessionmanager.cpp",
        (const char *)(unsigned int)v56,
        v58);
      if ( v12 )
        (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v11 )
        LeaveCriticalSection(v11);
      result = v57;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x172,
                           (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosessionmanager.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x18000fe60  push    rbx
0x18000fe62  push    rsi
0x18000fe63  push    rdi
0x18000fe64  push    r12
0x18000fe66  push    r13
0x18000fe68  push    r14
0x18000fe6a  push    r15
0x18000fe6c  sub     rsp, 110h
0x18000fe73  movaps  [rsp+148h+var_48], xmm6
0x18000fe7b  mov     rax, cs:__security_cookie
0x18000fe82  xor     rax, rsp
0x18000fe85  mov     [rsp+148h+var_58], rax
0x18000fe8d  mov     [rsp+148h+var_D8], r9d
0x18000fe92  mov     r14, r8
0x18000fe95  mov     [rsp+148h+var_E8], r8
0x18000fe9a  mov     r13, rdx
0x18000fe9d  mov     r15, rcx
0x18000fea0  mov     rax, [rsp+148h+arg_30]
0x18000fea8  mov     [rsp+148h+var_A8], rax
0x18000feb0  xor     r12d, r12d
0x18000feb3  mov     [rax], r12
0x18000feb6  lea     rsi, [rcx+8]
0x18000feba  mov     rcx, rsi; lpCriticalSection
0x18000febd  call    cs:__imp_EnterCriticalSection
0x18000fec3  mov     rdi, rsi
0x18000fec6  mov     [rsp+148h+var_C8], rsi
0x18000fece  mov     ebx, r12d
0x18000fed1  mov     [rsp+148h+var_E0], rbx
0x18000fed6  mov     [rsp+148h+var_F0], r12
0x18000fedb  lea     r8, [rsp+148h+var_F0]; struct CAudioSession **
0x18000fee0  mov     rdx, r14; struct CAudioSessionInstanceId *
0x18000fee3  mov     rcx, r15; this
0x18000fee6  call    ?FindAudioSession@CAudioSessionManager@@IEAAJAEAVCAudioSessionInstanceId@@PEAPEAVCAudioSession@@@Z; CAudioSessionManager::FindAudioSession(CAudioSessionInstanceId &,CAudioSession * *)
0x18000feeb  test    eax, eax
0x18000feed  js      loc_180010019
0x18000fef3  test    rsi, rsi
0x18000fef6  jz      short loc_18000FF11
0x18000fef8  call    cs:__imp_GetLastError
0x18000fefe  mov     edi, eax
0x18000ff00  mov     rcx, rsi; lpCriticalSection
0x18000ff03  call    cs:__imp_LeaveCriticalSection
0x18000ff09  mov     ecx, edi; dwErrCode
0x18000ff0b  call    cs:__imp_SetLastError
0x18000ff11  mov     [rsp+148h+var_C8], r12
0x18000ff19  mov     r14, [rsp+148h+var_F0]
0x18000ff1e  lea     rdi, [r14+220h]
0x18000ff25  mov     rcx, rdi; lpCriticalSection
0x18000ff28  call    cs:__imp_EnterCriticalSection
0x18000ff2e  mov     qword ptr [rsp+148h+fPending], rdi
0x18000ff33  lea     rcx, [r14+8]
0x18000ff37  mov     rax, [rcx]
0x18000ff3a  mov     rax, [rax+20h]
0x18000ff3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff43  cmp     eax, 2
0x18000ff46  jz      loc_18000FFF5
0x18000ff4c  mov     rax, [r13+0]
0x18000ff50  mov     rcx, r13
0x18000ff53  mov     rax, [rax+28h]
0x18000ff57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff5c  mov     edx, eax; unsigned int
0x18000ff5e  mov     rcx, r14; this
0x18000ff61  call    ?IsLinkedToProcess@CAudioSession@@QEAA_NK@Z; CAudioSession::IsLinkedToProcess(ulong)
0x18000ff66  test    al, al
0x18000ff68  jnz     short loc_18000FFC3
0x18000ff6a  mov     rdx, r13; struct IAudioProcess *
0x18000ff6d  mov     rcx, r14; this
0x18000ff70  call    ?RegisterOwnerProcess@CAudioSession@@QEAAJPEAUIAudioProcess@@@Z; CAudioSession::RegisterOwnerProcess(IAudioProcess *)
0x18000ff75  mov     ebx, eax
0x18000ff77  test    eax, eax
0x18000ff79  jns     short loc_18000FFC3
0x18000ff7b  mov     rcx, [rsp+148h]; this
0x18000ff83  mov     r9d, eax; char *
0x18000ff86  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18000ff8d  mov     edx, 0C7h; void *
0x18000ff92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ff97  nop
0x18000ff98  test    rdi, rdi
0x18000ff9b  jz      short loc_18000FFA7
0x18000ff9d  mov     rcx, rdi; lpCriticalSection
0x18000ffa0  call    cs:__imp_LeaveCriticalSection
0x18000ffa6  nop
0x18000ffa7  test    r14, r14
0x18000ffaa  jz      short loc_18000FFBC
0x18000ffac  mov     rax, [r14]
0x18000ffaf  mov     rcx, r14
0x18000ffb2  mov     rax, [rax+10h]
0x18000ffb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffbb  nop
0x18000ffbc  mov     eax, ebx
0x18000ffbe  jmp     loc_18001072B
0x18000ffc3  call    cs:__imp_GetTickCount64
0x18000ffc9  mov     [r14+140h], rax
0x18000ffd0  mov     rcx, r14; this
0x18000ffd3  call    ?StartInactiveTimer@CAudioSession@@QEAAXXZ; CAudioSession::StartInactiveTimer(void)
0x18000ffd8  mov     rbx, r14
0x18000ffdb  mov     [rsp+148h+var_E0], rbx
0x18000ffe0  test    r14, r14
0x18000ffe3  jz      short loc_18000FFF5
0x18000ffe5  mov     rax, [r14]
0x18000ffe8  mov     rcx, rbx
0x18000ffeb  mov     rax, [rax+8]
0x18000ffef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fff4  nop
0x18000fff5  test    rdi, rdi
0x18000fff8  jz      short loc_180010003
0x18000fffa  mov     rcx, rdi; lpCriticalSection
0x18000fffd  call    cs:__imp_LeaveCriticalSection
0x180010003  mov     rcx, rsi; lpCriticalSection
0x180010006  call    cs:__imp_EnterCriticalSection
0x18001000c  mov     rdi, rsi
0x18001000f  mov     [rsp+148h+var_C8], rsi
0x180010017  jmp     short loc_18001001E
0x180010019  mov     r14, [rsp+148h+var_F0]
0x18001001e  mov     r12, rsi
0x180010021  mov     [rsp+148h+var_F8], 1
0x180010026  test    r14, r14
0x180010029  jz      short loc_18001003B
0x18001002b  mov     rax, [r14]
0x18001002e  mov     rcx, r14
0x180010031  mov     rax, [rax+10h]
0x180010035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001003a  nop
0x18001003b  test    rbx, rbx
0x18001003e  jnz     loc_18001066C
0x180010044  test    r12, r12
0x180010047  jz      short loc_180010062
0x180010049  call    cs:__imp_GetLastError
0x18001004f  mov     ebx, eax
0x180010051  mov     rcx, rdi; lpCriticalSection
0x180010054  call    cs:__imp_LeaveCriticalSection
0x18001005a  mov     ecx, ebx; dwErrCode
0x18001005c  call    cs:__imp_SetLastError
0x180010062  xor     edi, edi
0x180010064  mov     [rsp+148h+var_C8], rdi
0x18001006c  mov     [rsp+148h+var_F0], rdi
0x180010071  mov     r12d, [rsp+148h+var_D8]
0x180010076  xor     ebx, ebx
0x180010078  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001007f  test    r12b, 8
0x180010083  jz      loc_18001012F
0x180010089  mov     ecx, 3E0h; unsigned __int64
0x18001008e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010093  mov     r14, rax
0x180010096  test    rax, rax
0x180010099  jz      loc_18001012A
0x18001009f  xor     edx, edx; Val
0x1800100a1  mov     r8d, 3E0h; Size
0x1800100a7  mov     rcx, rax; void *
0x1800100aa  call    memset_0
0x1800100af  mov     rcx, r14; this
0x1800100b2  call    ??0CAudioSession@@IEAA@XZ; CAudioSession::CAudioSession(void)
0x1800100b7  lea     rax, ??_7CPerStreamVolumeAudioSession@@6BIInspectable@@@; const CPerStreamVolumeAudioSession::`vftable'{for `IInspectable'}
0x1800100be  mov     [r14], rax
0x1800100c1  lea     rax, ??_7CAudioSession@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ChainInterfaces@UIAudioSessionPolicyControl@@UIAudioSessionInfo@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIWeakReferenceSource@@UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@Details@WRL@Microsoft@@@; const CAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWeakReferenceSource,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>'}
0x1800100c8  mov     [r14+8], rax
0x1800100cc  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ChainInterfaces@UIAudioSessionPolicyControl@@UIAudioSessionInfo@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>::`vftable'{for `IWeakReferenceSource'}
0x1800100d3  mov     [r14+10h], rax
0x1800100d7  lea     rax, ??_7CAudioSession@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@Details@WRL@Microsoft@@@; const CAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>'}
0x1800100de  mov     [r14+18h], rax
0x1800100e2  lea     rax, ??_7CAudioSession@@6BIAudioSessionDuckingControl@@@; const CAudioSession::`vftable'{for `IAudioSessionDuckingControl'}
0x1800100e9  mov     [r14+20h], rax
0x1800100ed  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ChainInterfaces@UIAudioSessionPolicyControl@@UIAudioSessionInfo@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIInspectable@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'}
0x1800100f4  mov     [r14+28h], rax
0x1800100f8  mov     byte ptr [r14+398h], 1
0x180010100  mov     [r14+3A0h], rbx
0x180010107  lea     rcx, [r14+3A8h]; lpCriticalSection
0x18001010e  xor     r8d, r8d; Flags
0x180010111  xor     edx, edx; dwSpinCount
0x180010113  call    cs:__imp_InitializeCriticalSectionEx
0x180010119  mov     [r14+3D0h], ebx
0x180010120  mov     [r14+3D8h], rbx
0x180010127  mov     rbx, r14
0x18001012a  jmp     loc_1800101C8
0x18001012f  mov     ecx, 3D0h; unsigned __int64
0x180010134  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010139  mov     r14, rax
0x18001013c  test    rax, rax
0x18001013f  jz      loc_1800101C8
0x180010145  xor     edx, edx; Val
0x180010147  mov     r8d, 3D0h; Size
0x18001014d  mov     rcx, rax; void *
0x180010150  call    memset_0
0x180010155  mov     rcx, r14; this
0x180010158  call    ??0CAudioSession@@IEAA@XZ; CAudioSession::CAudioSession(void)
0x18001015d  lea     rax, ??_7CPerEndpointVolumeAudioSession@@6BIInspectable@@@; const CPerEndpointVolumeAudioSession::`vftable'{for `IInspectable'}
0x180010164  mov     [r14], rax
0x180010167  lea     rax, ??_7CPerEndpointVolumeAudioSession@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ChainInterfaces@UIAudioSessionPolicyControl@@UIAudioSessionInfo@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIWeakReferenceSource@@UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@Details@WRL@Microsoft@@@; const CPerEndpointVolumeAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWeakReferenceSource,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>'}
0x18001016e  mov     [r14+8], rax
0x180010172  lea     rax, ??_7CPerEndpointVolumeAudioSession@@6BIWeakReferenceSource@@@; const CPerEndpointVolumeAudioSession::`vftable'{for `IWeakReferenceSource'}
0x180010179  mov     [r14+10h], rax
0x18001017d  lea     rax, ??_7CPerEndpointVolumeAudioSession@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@Details@WRL@Microsoft@@@; const CPerEndpointVolumeAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>'}
0x180010184  mov     [r14+18h], rax
0x180010188  lea     rax, ??_7CPerEndpointVolumeAudioSession@@6BIAudioSessionDuckingControl@@@; const CPerEndpointVolumeAudioSession::`vftable'{for `IAudioSessionDuckingControl'}
0x18001018f  mov     [r14+20h], rax
0x180010193  lea     rax, ??_7CPerEndpointVolumeAudioSession@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIInspectable@@@Details@WRL@Microsoft@@@; const CPerEndpointVolumeAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'}
0x18001019a  mov     [r14+28h], rax
0x18001019e  lea     rax, ??_7CPerEndpointVolumeAudioSession@@6B@; const CPerEndpointVolumeAudioSession::`vftable'
0x1800101a5  mov     [r14+398h], rax
0x1800101ac  lea     rcx, [r14+3A0h]; lpCriticalSection
0x1800101b3  xor     r8d, r8d; Flags
0x1800101b6  xor     edx, edx; dwSpinCount
0x1800101b8  call    cs:__imp_InitializeCriticalSectionEx
0x1800101be  mov     [r14+3C8h], rbx
0x1800101c5  mov     rbx, r14
0x1800101c8  mov     rcx, [rsp+148h+var_F0]
0x1800101cd  test    rcx, rcx
0x1800101d0  mov     [rsp+148h+var_F0], rbx
0x1800101d5  jz      short loc_1800101E4
0x1800101d7  mov     rax, [rcx]
0x1800101da  mov     rax, [rax+10h]
0x1800101de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101e3  nop
0x1800101e4  cmp     [rsp+148h+var_F0], 0
0x1800101ea  jnz     short loc_18001022D
0x1800101ec  mov     rcx, [rsp+148h]; this
0x1800101f4  mov     r9d, 8007000Eh; char *
0x1800101fa  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180010201  mov     edx, 101h; void *
0x180010206  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001020b  nop
0x18001020c  mov     rcx, [rsp+148h+var_F0]
0x180010211  test    rcx, rcx
0x180010214  jz      short loc_180010223
0x180010216  mov     rdx, [rcx]
0x180010219  mov     rax, [rdx+10h]
0x18001021d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010222  nop
0x180010223  mov     eax, 8007000Eh
0x180010228  jmp     loc_18001072B
0x18001022d  movups  xmm6, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180010234  test    r12b, 4
0x180010238  jnz     short loc_18001027A
0x18001023a  mov     rax, [r13+0]
0x18001023e  mov     rcx, r13
0x180010241  mov     rax, [rax+1C0h]
0x180010248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001024d  mov     r14, [rsp+148h+var_E8]
0x180010252  test    al, al
0x180010254  jnz     short loc_18001027F
0x180010256  mov     rax, [r13+0]
0x18001025a  lea     r8, [r14+18h]
0x18001025e  lea     rdx, [rsp+148h+var_68]
0x180010266  mov     rcx, r13
0x180010269  mov     rax, [rax+1D0h]
0x180010270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010275  movups  xmm6, xmmword ptr [rax]
0x180010278  jmp     short loc_18001027F
0x18001027a  mov     r14, [rsp+148h+var_E8]
0x18001027f  mov     rcx, [rsp+148h+var_F0]
0x180010284  movdqa  [rsp+148h+var_B8], xmm6
0x18001028d  mov     rax, [rcx]
0x180010290  lea     rdx, [rsp+148h+var_B8]
0x180010298  mov     [rsp+148h+var_110], rdx
0x18001029d  mov     edx, [rsp+148h+arg_28]
0x1800102a4  mov     dword ptr [rsp+148h+var_118], edx
0x1800102a8  mov     edx, [rsp+148h+arg_20]
0x1800102af  mov     dword ptr [rsp+148h+var_120], edx
0x1800102b3  mov     [rsp+148h+var_128], r12d; int
0x1800102b8  mov     r9, r14
0x1800102bb  mov     r8, r13
0x1800102be  mov     rdx, r15
0x1800102c1  mov     rax, [rax+0A8h]
0x1800102c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102cd  mov     ebx, eax
0x1800102cf  test    eax, eax
0x1800102d1  jns     short loc_18001030E
0x1800102d3  mov     rcx, [rsp+148h]; this
0x1800102db  mov     r9d, eax; char *
0x1800102de  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800102e5  mov     edx, 119h; void *
0x1800102ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800102ef  nop
0x1800102f0  mov     rcx, [rsp+148h+var_F0]
0x1800102f5  test    rcx, rcx
0x1800102f8  jz      short loc_180010307
0x1800102fa  mov     rax, [rcx]
0x1800102fd  mov     rax, [rax+10h]
0x180010301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010306  nop
0x180010307  mov     eax, ebx
0x180010309  jmp     loc_18001072B
0x18001030e  mov     rcx, rsi; lpCriticalSection
0x180010311  call    cs:__imp_EnterCriticalSection
0x180010317  mov     [rsp+148h+var_70], rsi
0x18001031f  xor     r12d, r12d
0x180010322  mov     [rsp+148h+var_E0], r12
0x180010327  lea     r8, [rsp+148h+var_E0]; struct CAudioSession **
0x18001032c  mov     rdx, r14; struct CAudioSessionInstanceId *
0x18001032f  mov     rcx, r15; this
0x180010332  call    ?FindAudioSession@CAudioSessionManager@@IEAAJAEAVCAudioSessionInstanceId@@PEAPEAVCAudioSession@@@Z; CAudioSessionManager::FindAudioSession(CAudioSessionInstanceId &,CAudioSession * *)
0x180010337  test    eax, eax
0x180010339  jns     loc_18001063F
0x18001033f  lea     rcx, [r15+30h]
0x180010343  lea     r9, [rsp+148h+var_F0]
0x180010348  mov     r8, r14
0x18001034b  lea     rdx, [rsp+148h+var_B8]
0x180010353  call    ??$emplace@AEAVCAudioSessionInstanceId@@AEAV?$com_ptr_t@VCAudioSession@@Uerr_returncode_policy@wil@@@wil@@@?$_Hash@V?$_Umap_traits@VCAudioSessionInstanceId@@V?$com_ptr_t@VCAudioSession@@Uerr_returncode_policy@wil@@@wil@@V?$_Uhash_compare@VCAudioSessionInstanceId@@U?$hash@VCAudioSessionInstanceId@@@std@@U?$equal_to@VCAudioSessionInstanceId@@@3@@std@@V?$allocator@U?$pair@$$CBVCAudioSessionInstanceId@@V?$com_ptr_t@VCAudioSession@@Uerr_returncode_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCAudioSessionInstanceId@@V?$com_ptr_t@VCAudioSession@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@@std@@_N@1@AEAVCAudioSessionInstanceId@@AEAV?$com_ptr_t@VCAudioSession@@Uerr_returncode_policy@wil@@@wil@@@Z; std::_Hash<std::_Umap_traits<CAudioSessionInstanceId,wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>,std::_Uhash_compare<CAudioSessionInstanceId,std::hash<CAudioSessionInstanceId>,std::equal_to<CAudioSessionInstanceId>>,std::allocator<std::pair<CAudioSessionInstanceId const,wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>>>,0>>::emplace<CAudioSessionInstanceId &,wil::com_ptr_t<CAudioSession,wil::err_returncode_policy> &>(CAudioSessionInstanceId &,wil::com_ptr_t<CAudioSession,wil::err_returncode_policy> &)
0x180010358  mov     [rsp+148h+var_88], r15
0x180010360  lea     rax, [rsp+148h+var_B8]
0x180010368  mov     [rsp+148h+var_80], rax
  ... truncated ...
```
