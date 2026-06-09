# WorkerTaskStarting::RunCleanStartSteps(void)

- ea: `0x14009318c`
- end: `0x140093b2b`
- name: `?RunCleanStartSteps@WorkerTaskStarting@@AEAAJXZ`
- size: `2463`
- prototype: `__int64 __fastcall(WorkerTaskStarting *__hidden this)`
- caller_count: `2`
- callee_count: `46`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14017e5dc`
- `0x14017fb40`

## callees

- `0x140031094`
- `0x140042240`
- `0x1400561a8`
- `0x14005b628`
- `0x14005e684`
- `0x14005e7e4`
- `0x14005eca0`
- `0x140067f4c`
- `0x14007bec0`
- `0x14007c3e0`
- `0x14009318c`
- `0x140093b34`
- `0x140093bbc`
- `0x140093c74`
- `0x140093d34`
- `0x140093f84`
- `0x140093fb4`
- `0x140094074`
- `0x1400940a0`
- `0x1400941dc`
- `0x140094234`
- `0x14009f9ec`
- `0x1400c83f0`
- `0x1400cf8a0`
- `0x1400d5d94`
- `0x140111070`
- `0x140119298`
- `0x140132940`
- `0x1401335fc`
- `0x14014120c`
- `0x14014c9c8`
- `0x140162430`
- `0x14016ad80`
- `0x140170910`
- `0x14017cef8`
- `0x14017cf24`
- `0x14017cf5c`
- `0x14017d00c`
- `0x14017d038`
- `0x14017e420`
- `0x140180104`
- `0x140180404`
- `0x140180644`
- `0x14018073c`
- `0x140180828`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400933f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140093754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400933f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140093754`
- `vid!VidVsmSetPartitionConfig` at `0x1400934c4`
- `vid!VidVsmSetPartitionConfig` at `0x1400934c4`
- `vid!VidTrimPartitionMemory` at `0x1400938d7`
- `vid!VidTrimPartitionMemory` at `0x1400938d7`
- `vid!VidChangePartitionLifeState` at `0x1400933e4`
- `vid!VidChangePartitionLifeState` at `0x140093744`
- `vid!VidChangePartitionLifeState` at `0x1400933e4`
- `vid!VidChangePartitionLifeState` at `0x140093744`

## string_xrefs

- `0x1400931e6`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`
- `0x1400932b1`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`
- `0x1400932f3`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WorkerTaskStarting::RunCleanStartSteps(WorkerTaskStarting *this)
{
  WorkerAsyncTaskBase *v1; // r15
  VirtualMachine **v2; // r14
  __int64 v3; // rcx
  unsigned int *v4; // r13
  const struct _GUID *v5; // rdi
  int v6; // eax
  __int64 ConfigRepository; // rax
  char v8; // di
  int v9; // edi
  __int64 v10; // rsi
  __int64 v11; // rax
  unsigned int v12; // edi
  __int64 v13; // r8
  unsigned int v14; // esi
  signed int LastError; // eax
  __int64 v16; // rax
  const char *v17; // r9
  __int64 IgvmFileIntoGuest; // rax
  wil *v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  VirtualMachine *v22; // rdi
  __int64 v23; // rax
  signed int v24; // eax
  int v25; // eax
  int v26; // eax
  int started; // eax
  __int64 v28; // rax
  __int64 v29; // rdx
  VirtualMachine *v30; // rdi
  __int64 v31; // rdx
  __int64 v32; // rcx
  void (*v33)(void); // rax
  __int64 v34; // rdx
  int v36; // [rsp+20h] [rbp-388h]
  int v37; // [rsp+20h] [rbp-388h]
  int v38; // [rsp+24h] [rbp-384h] BYREF
  _QWORD v39[2]; // [rsp+28h] [rbp-380h] BYREF
  _BYTE v40[8]; // [rsp+38h] [rbp-370h] BYREF
  WorkerAsyncTaskBase *v41; // [rsp+40h] [rbp-368h]
  _BYTE v42[336]; // [rsp+50h] [rbp-358h] BYREF
  unsigned int v43; // [rsp+1A0h] [rbp-208h] BYREF
  int v44; // [rsp+1A4h] [rbp-204h] BYREF
  wil::details::in1diag3 *v45; // [rsp+1A8h] [rbp-200h] BYREF
  __int128 v46; // [rsp+1B0h] [rbp-1F8h] BYREF
  __int64 v47; // [rsp+1C0h] [rbp-1E8h]
  __int128 v48; // [rsp+1C8h] [rbp-1E0h] BYREF
  __int64 v49; // [rsp+1D8h] [rbp-1D0h]
  _QWORD v50[2]; // [rsp+1E0h] [rbp-1C8h] BYREF
  __int128 v51; // [rsp+1F0h] [rbp-1B8h] BYREF
  __int128 v52; // [rsp+200h] [rbp-1A8h]
  __int64 v53; // [rsp+210h] [rbp-198h]
  _QWORD v54[42]; // [rsp+220h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+0h]

  v1 = this;
  v41 = this;
  v2 = (VirtualMachine **)((char *)this + 16);
  v50[0] = (char *)this + 16;
  v3 = *((_QWORD *)this + 2);
  if ( !*(_QWORD *)(*(_QWORD *)(v3 + 1416) + 88LL) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1AF,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
      (const char *)retaddr);
  v38 = 0;
  v48 = 0;
  v49 = 0;
  v4 = (unsigned int *)((char *)v1 + 400);
  v39[0] = (char *)v1 + 400;
  if ( *((_DWORD *)v1 + 100) != 2 )
    goto LABEL_8;
  LODWORD(v5) = VirtualMotherboard::StartReservingResources(*(_QWORD *)(v3 + 984), 0, 0);
  if ( (int)v5 >= 0 )
  {
    memset_0(v54, 0, sizeof(v54));
    WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(v1, v42);
    VmPerf::StartRelatedActivity_VmWorkerTrace::ConstructGuestRam_VmWorkerTrace::StartingTask__GUID_const___((VmWorkerTrace::ConstructGuestRam *)v54);
    VmWorkerTrace::StartingTask::~StartingTask((VmWorkerTrace::StartingTask *)v42);
    v6 = VirtualMachine::ConstructGuestRam(
           *v2,
           0,
           *((struct IVmSimpleTask **)v1 + 3),
           (const struct _GUID *)(v54[34] + 8LL));
    LODWORD(v5) = v6;
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1C5,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
        (const char *)(unsigned int)v6,
        v36);
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v54, (unsigned int)v5);
    VmWorkerTrace::ConstructGuestRam::~ConstructGuestRam((VmWorkerTrace::ConstructGuestRam *)v54);
    if ( (int)v5 >= 0 )
    {
LABEL_8:
      v37 = 0;
      v44 = 0;
      (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)*v2 + 134) + 88LL))(*((_QWORD *)*v2 + 134), &v44);
      if ( v44 )
      {
        v45 = 0;
        v46 = 0;
        v47 = 0;
        ConfigRepository = VirtualMachine::GetConfigRepository(*v2, v40);
        v8 = *(_BYTE *)Marshal::FromRepository<Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> &,Config::VmWorkerProcess::IsolationSettings,>(
                         &v51,
                         ConfigRepository,
                         &v45);
        std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy((char *)&v51 + 8);
        Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(v40);
        if ( !v8 )
        {
          LODWORD(v5) = -2147024809;
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v46);
          goto LABEL_84;
        }
        v9 = DWORD2(v46);
        v10 = v46;
        v11 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v2 + 128) + 24LL))(*((_QWORD *)*v2 + 128) + 24LL);
        v12 = v9 - v10;
        v13 = v10;
        v14 = 1;
        if ( !(unsigned int)VidChangePartitionLifeState(v11, 1, v13, v12) )
        {
          LastError = GetLastError();
          LODWORD(v5) = LastError;
          if ( LastError > 0 )
            LODWORD(v5) = (unsigned __int16)LastError | 0x80070000;
          if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
            VmlDebugTraceWithError(16416, &off_1402D9C28, (unsigned int)v5);
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v46);
          goto LABEL_45;
        }
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v46);
      }
      else
      {
        v14 = 1;
      }
      if ( *((_BYTE *)*v2 + 2664) )
      {
        v16 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v2 + 128) + 24LL))(*((_QWORD *)*v2 + 128) + 24LL);
        v51 = 0;
        v52 = 0;
        v53 = 0;
        LODWORD(v51) = 5;
        BYTE8(v52) = 0;
        HIDWORD(v52) = 15;
        if ( !(unsigned int)VidVsmSetPartitionConfig(v16, 40, &v51) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x57,
            (unsigned int)"onecore\\vm\\worker\\wpcore\\workerhclloader.cpp",
            v17);
      }
      if ( *((_BYTE *)*v2 + 2968) )
      {
        try
        {
          IgvmFileIntoGuest = VirtualMachine::LoadIgvmFileIntoGuest((struct _GUID *)*v2, (__int64)&v45);
          std::vector<unsigned char>::operator=(&v48, IgvmFileIntoGuest);
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v45);
        }
        catch ( ... )
        {
          LODWORD(v5) = wil::ResultFromCaughtException(v19);
          v25 = 0;
          v1 = v41;
          v2 = (VirtualMachine **)v50[0];
          v4 = (unsigned int *)v39[0];
          goto LABEL_46;
        }
      }
      LODWORD(v5) = WorkerTaskStarting::PowerOnVirtualMotherboard(v1, 0, 0);
      if ( (int)v5 >= 0 )
      {
        LODWORD(v5) = VirtualMachine::RegisterGuestCrashManager(*v2);
        if ( (int)v5 >= 0 )
        {
          if ( *v4 > 0x33
            || (v20 = 0x8000100008004LL, !_bittest64(&v20, (int)*v4))
            || (LODWORD(v5) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)*v2 + 133) + 48LL))(*((_QWORD *)*v2 + 133)),
                (int)v5 >= 0) )
          {
            WorkerAsyncTaskBase::UpdateStatusProgress(v1, 0x32u, &v38);
            if ( v38 )
            {
              LODWORD(v5) = -2147023673;
            }
            else
            {
              if ( *v4 != 32 )
                (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)*v2 + 130) + 656LL))(*((_QWORD *)*v2 + 130), 1);
              memset_0(v54, 0, sizeof(v54));
              v5 = (const struct _GUID *)*v2;
              wil::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v54);
              v54[0] = &VmWorkerTrace::BootStateImporterFlush::`vftable';
              VmWorkerTrace::BootStateImporterFlush::StartActivity(
                (VmWorkerTrace::BootStateImporterFlush *)v54,
                v5 + 71);
              v39[0] = v1;
              v21 = wil::ResultFromException__lambda_1e435c07f28aa931d7536c0492f26ff8___(v39);
              LODWORD(v5) = v21;
              if ( v21 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x249,
                  (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
                  (const char *)(unsigned int)v21,
                  0);
              wil::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
                v54,
                (unsigned int)v5);
              if ( (int)v5 >= 0 )
              {
                v37 = 1;
                VmWorkerTrace::BootStateImporterFlush::~BootStateImporterFlush((VmWorkerTrace::BootStateImporterFlush *)v54);
                if ( v44 )
                {
                  memset_0(v54, 0, sizeof(v54));
                  v22 = *v2;
                  wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v54);
                  v54[0] = &VmWorkerTrace::IsolatedVmBootImport::`vftable';
                  VmWorkerTrace::IsolatedVmBootImport::StartActivity(
                    (VmWorkerTrace::IsolatedVmBootImport *)v54,
                    (const struct _GUID *)v22 + 71);
                  v23 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v2 + 128) + 24LL))(*((_QWORD *)*v2 + 128) + 24LL);
                  if ( !(unsigned int)VidChangePartitionLifeState(v23, 2, v48, (unsigned int)(DWORD2(v48) - v48)) )
                  {
                    v24 = GetLastError();
                    LODWORD(v5) = v24;
                    if ( v24 > 0 )
                      LODWORD(v5) = (unsigned __int16)v24 | 0x80070000;
                    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
                      VmlDebugTraceWithError(16416, &off_1402D9C10, (unsigned int)v5);
                    VmWorkerTrace::IsolatedVmBootImport::~IsolatedVmBootImport((VmWorkerTrace::IsolatedVmBootImport *)v54);
LABEL_45:
                    v25 = v37;
LABEL_46:
                    if ( (int)v5 < 0 )
                      goto LABEL_76;
                    goto LABEL_79;
                  }
                  wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v54);
                  VmWorkerTrace::IsolatedVmBootImport::~IsolatedVmBootImport((VmWorkerTrace::IsolatedVmBootImport *)v54);
                }
                switch ( *v4 )
                {
                  case 2u:
                    v43 = 1;
                    break;
                  case 0xFu:
                    v43 = 6;
                    break;
                  case 0x20u:
                    v43 = 17;
                    break;
                  default:
                    v26 = 22;
                    if ( *v4 != 51 )
                      v26 = 0;
                    v43 = v26;
                    break;
                }
                memset_0(v54, 0, sizeof(v54));
                v5 = (const struct _GUID *)*v2;
                wil::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v54);
                v54[0] = &VmWorkerTrace::StartVm::`vftable';
                VmWorkerTrace::StartVm::StartActivity((VmWorkerTrace::StartVm *)v54, v5 + 71);
                started = VirtualMachine::StartVm(*v2, 0, v43);
                LODWORD(v5) = started;
                if ( started < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x285,
                    (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
                    (const char *)(unsigned int)started,
                    1);
                wil::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
                  v54,
                  (unsigned int)v5);
                VmWorkerTrace::StartVm::~StartVm((VmWorkerTrace::StartVm *)v54);
                if ( (int)v5 >= 0 )
                {
                  v28 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v2 + 128) + 24LL))(*((_QWORD *)*v2 + 128) + 24LL);
                  VidTrimPartitionMemory(v28);
                  WorkerAsyncTaskBase::UpdateStatusProgress(v1, *((_BYTE *)*v2 + 2664) != 0 ? 95 : 99, &v38);
                  if ( v38 )
                  {
                    LODWORD(v5) = -2147023673;
                  }
                  else
                  {
                    v29 = *((_QWORD *)v1 + 51);
                    *((_QWORD *)v1 + 51) = 0;
                    if ( v29 )
                      std::default_delete<ProcessPriorityBooster>::operator()();
                    v30 = *v2;
                    if ( !*((_BYTE *)*v2 + 2665) )
                      goto LABEL_78;
                    v43 = 60;
                    memset_0(v54, 0, sizeof(v54));
                    wil::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v54);
                    v54[0] = &VmWorkerTrace::StartVtl0::`vftable';
                    VmWorkerTrace::StartVtl0::StartActivity(
                      (VmWorkerTrace::StartVtl0 *)v54,
                      (const struct _GUID *)v30 + 71);
                    v39[0] = &v43;
                    v39[1] = v1;
                    v45 = retaddr;
                    *(_QWORD *)&v46 = "onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp";
                    *((_QWORD *)&v46 + 1) = 0;
                    LOWORD(v47) = 683;
                    v50[0] = &off_1402CA7B8;
                    v50[1] = v39;
                    v5 = (const struct _GUID *)(unsigned int)wil::details::ResultFromException(&v45, v31, v50);
                    wil::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v54, v5);
                    VmWorkerTrace::StartVtl0::~StartVtl0((VmWorkerTrace::StartVtl0 *)v54);
                    if ( (int)v5 >= 0 )
                    {
LABEL_78:
                      LODWORD(v5) = 0;
LABEL_79:
                      if ( *v4 <= 0x33 && (v32 = 0x8000100008000LL, _bittest64(&v32, (int)*v4)) )
                        v33 = *(void (**)(void))(**((_QWORD **)*v2 + 133) + 72LL);
                      else
                        v33 = *(void (**)(void))(**((_QWORD **)*v2 + 133) + 56LL);
                      v33();
                      WorkerAsyncTaskBase::UpdateStatusProgress(v1, 0x64u, &v38);
                      goto LABEL_84;
                    }
                  }
                  if ( *v4 != 2 )
                  {
                    if ( *v4 == 15 )
                    {
                      v14 = 7;
                    }
                    else if ( *v4 == 32 )
                    {
                      v14 = 24;
                    }
                    else
                    {
                      v14 = 30;
                      if ( *v4 != 51 )
                        v14 = 0;
                    }
                  }
                  VirtualMachine::StopVm(*v2, 0, v14);
                  v25 = v37;
LABEL_76:
                  if ( !v25 )
                    goto LABEL_84;
                }
              }
              else
              {
                VmWorkerTrace::BootStateImporterFlush::~BootStateImporterFlush((VmWorkerTrace::BootStateImporterFlush *)v54);
              }
            }
          }
        }
        else if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        {
          VmlDebugTraceWithError(16416, &off_1402D9C40, (unsigned int)v5);
        }
        VirtualMotherboard::PowerOff(*((_QWORD *)*v2 + 123), 0);
      }
    }
  }
LABEL_84:
  v34 = *((_QWORD *)v1 + 51);
  *((_QWORD *)v1 + 51) = 0;
  if ( v34 )
    std::default_delete<ProcessPriorityBooster>::operator()();
  std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v48);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14009318c  mov     [rsp+arg_8], rbx
0x140093191  mov     [rsp+arg_10], rsi
0x140093196  push    rdi
0x140093197  push    r12
0x140093199  push    r13
0x14009319b  push    r14
0x14009319d  push    r15
0x14009319f  sub     rsp, 380h
0x1400931a6  mov     rax, cs:__security_cookie
0x1400931ad  xor     rax, rsp
0x1400931b0  mov     [rsp+3A8h+var_38], rax
0x1400931b8  mov     r15, rcx
0x1400931bb  mov     [rsp+3A8h+var_368], rcx
0x1400931c0  lea     r14, [rcx+10h]
0x1400931c4  mov     [rsp+3A8h+var_1C8], r14
0x1400931cc  mov     rcx, [r14]
0x1400931cf  mov     r9, [rsp+3A8h]; char *
0x1400931d7  mov     rax, [rcx+588h]
0x1400931de  xor     ebx, ebx
0x1400931e0  cmp     [rax+58h], rbx
0x1400931e4  jnz     short loc_1400931FB
0x1400931e6  lea     r8, aOnecoreVmWorke_44; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400931ed  mov     edx, 1AFh; void *
0x1400931f2  mov     rcx, r9; this
0x1400931f5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400931fb  mov     [rsp+3A8h+var_384], ebx
0x1400931ff  xorps   xmm1, xmm1
0x140093202  movdqu  [rsp+3A8h+var_1E0], xmm1
0x14009320b  mov     [rsp+3A8h+var_1D0], rbx
0x140093213  lea     r13, [r15+190h]
0x14009321a  mov     [rsp+3A8h+var_380], r13
0x14009321f  cmp     dword ptr [r13+0], 2
0x140093224  jnz     loc_1400932F3
0x14009322a  xor     r8d, r8d
0x14009322d  xor     edx, edx
0x14009322f  mov     rcx, [rcx+3D8h]
0x140093236  call    ?StartReservingResources@VirtualMotherboard@@QEAAJPEAVVmRepository@@W4VmbReserveResourcesFlags@@@Z; VirtualMotherboard::StartReservingResources(VmRepository *,VmbReserveResourcesFlags)
0x14009323b  mov     edi, eax
0x14009323d  test    eax, eax
0x14009323f  js      loc_140093AD5
0x140093245  xor     edx, edx; Val
0x140093247  mov     r8d, 150h; Size
0x14009324d  lea     rcx, [rsp+3A8h+var_188]; void *
0x140093255  call    memset_0
0x14009325a  mov     rdi, [r14]
0x14009325d  lea     rdx, [rsp+3A8h+var_358]
0x140093262  mov     rcx, r15
0x140093265  call    ?GetCurrentActivity@?$WorkerAsyncTask@VStartingTask@VmWorkerTrace@@@@IEAA?AVStartingTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(void)
0x14009326a  nop
0x14009326b  lea     r8, [rdi+470h]
0x140093272  mov     rdx, rax
0x140093275  lea     rcx, [rsp+3A8h+var_188]; this
0x14009327d  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ConstructGuestRam_VmWorkerTrace__StartingTask__GUID_const___
0x140093282  nop
0x140093283  lea     rcx, [rsp+3A8h+var_358]; this
0x140093288  call    ??1StartingTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::StartingTask::~StartingTask(void)
0x14009328d  mov     r9, [rsp+3A8h+var_78]
0x140093295  add     r9, 8; struct _GUID *
0x140093299  mov     r8, [r15+18h]; struct IVmSimpleTask *
0x14009329d  xor     edx, edx; struct VmRepository *
0x14009329f  mov     rcx, [r14]; this
0x1400932a2  call    ?ConstructGuestRam@VirtualMachine@@QEAAJPEAVVmRepository@@PEAUIVmSimpleTask@@PEBU_GUID@@@Z; VirtualMachine::ConstructGuestRam(VmRepository *,IVmSimpleTask *,_GUID const *)
0x1400932a7  mov     edi, eax
0x1400932a9  mov     rcx, [rsp+3A8h]; this
0x1400932b1  lea     r12, aOnecoreVmWorke_44; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400932b8  test    eax, eax
0x1400932ba  jns     short loc_1400932CC
0x1400932bc  mov     r9d, eax; char *
0x1400932bf  mov     r8, r12; unsigned int
0x1400932c2  mov     edx, 1C5h; void *
0x1400932c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400932cc  mov     edx, edi
0x1400932ce  lea     rcx, [rsp+3A8h+var_188]
0x1400932d6  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0BA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400932db  nop
0x1400932dc  lea     rcx, [rsp+3A8h+var_188]; this
0x1400932e4  call    ??1ConstructGuestRam@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ConstructGuestRam::~ConstructGuestRam(void)
0x1400932e9  test    edi, edi
0x1400932eb  js      loc_140093AD5
0x1400932f1  jmp     short loc_1400932FA
0x1400932f3  lea     r12, aOnecoreVmWorke_44; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400932fa  mov     [rsp+3A8h+var_388], ebx; int
0x1400932fe  mov     [rsp+3A8h+var_204], ebx
0x140093305  mov     rax, [r14]
0x140093308  mov     rcx, [rax+430h]
0x14009330f  mov     rax, [rcx]
0x140093312  lea     rdx, [rsp+3A8h+var_204]
0x14009331a  mov     rax, [rax+58h]
0x14009331e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140093323  cmp     [rsp+3A8h+var_204], ebx
0x14009332a  jz      loc_140093452
0x140093330  mov     [rsp+3A8h+var_200], rbx
0x140093338  xorps   xmm0, xmm0
0x14009333b  movdqu  [rsp+3A8h+var_1F8], xmm0
0x140093344  mov     [rsp+3A8h+var_1E8], rbx
0x14009334c  lea     rdx, [rsp+3A8h+var_370]
0x140093351  mov     rcx, [r14]
0x140093354  call    ?GetConfigRepository@VirtualMachine@@UEBA?AV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@XZ; VirtualMachine::GetConfigRepository(void)
0x140093359  nop
0x14009335a  lea     r8, [rsp+3A8h+var_200]
0x140093362  mov     rdx, rax
0x140093365  lea     rcx, [rsp+3A8h+var_1B8]
0x14009336d  call    ??$FromRepository@AEAV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@UIsolationSettings@VmWorkerProcess@Config@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@AEAV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@PEAUIsolationSettings@VmWorkerProcess@Config@@W4UnmarshalFlags@0@@Z; Marshal::FromRepository<Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> &,Config::VmWorkerProcess::IsolationSettings,>(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> &,Config::VmWorkerProcess::IsolationSettings *,Marshal::UnmarshalFlags)
0x140093372  mov     dil, [rax]
0x140093375  lea     rcx, [rsp+3A8h+var_1B8+8]
0x14009337d  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x140093382  nop
0x140093383  lea     rcx, [rsp+3A8h+var_370]
0x140093388  call    ??1?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(void)
0x14009338d  test    dil, dil
0x140093390  jnz     short loc_1400933A9
0x140093392  mov     edi, 80070057h
0x140093397  lea     rcx, [rsp+3A8h+var_1F8]
0x14009339f  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1400933a4  jmp     loc_140093AD5
0x1400933a9  mov     rsi, qword ptr [rsp+3A8h+var_1F8]
0x1400933b1  mov     rdi, qword ptr [rsp+3A8h+var_1F8+8]
0x1400933b9  mov     rax, [r14]
0x1400933bc  mov     rcx, [rax+400h]
0x1400933c3  add     rcx, 18h
0x1400933c7  mov     rax, [rcx]
0x1400933ca  mov     rax, [rax]
0x1400933cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400933d2  sub     edi, esi
0x1400933d4  mov     r9d, edi
0x1400933d7  mov     r8, rsi
0x1400933da  mov     esi, 1
0x1400933df  mov     edx, esi
0x1400933e1  mov     rcx, rax
0x1400933e4  call    cs:__imp_VidChangePartitionLifeState
0x1400933eb  nop     dword ptr [rax+rax+00h]
0x1400933f0  test    eax, eax
0x1400933f2  jnz     short loc_140093443
0x1400933f4  call    cs:__imp_GetLastError
0x1400933fb  nop     dword ptr [rax+rax+00h]
0x140093400  mov     edi, eax
0x140093402  test    eax, eax
0x140093404  jle     short loc_14009340F
0x140093406  movzx   edi, ax
0x140093409  or      edi, 80070000h
0x14009340f  mov     esi, 4020h
0x140093414  mov     ecx, esi
0x140093416  call    VmlIsDebugTraceEnabled
0x14009341b  test    eax, eax
0x14009341d  jz      short loc_140093431
0x14009341f  mov     r8d, edi
0x140093422  lea     rdx, off_1402D9C28; "Unable to begin isolated VM boot import"...
0x140093429  mov     ecx, esi
0x14009342b  call    VmlDebugTraceWithError
0x140093430  nop
0x140093431  lea     rcx, [rsp+3A8h+var_1F8]
0x140093439  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14009343e  jmp     loc_14009379E
0x140093443  lea     rcx, [rsp+3A8h+var_1F8]
0x14009344b  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140093450  jmp     short loc_140093457
0x140093452  mov     esi, 1
0x140093457  mov     rax, [r14]
0x14009345a  cmp     [rax+0A68h], bl
0x140093460  jz      loc_1400934EC
0x140093466  mov     rcx, [rax+400h]
0x14009346d  add     rcx, 18h
0x140093471  mov     rax, [rcx]
0x140093474  mov     rax, [rax]
0x140093477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009347c  xorps   xmm0, xmm0
0x14009347f  xor     ecx, ecx
0x140093481  movups  [rsp+3A8h+var_1B8], xmm0
0x140093489  movups  [rsp+3A8h+var_1A8], xmm0
0x140093491  mov     [rsp+3A8h+var_198], rcx
0x140093499  mov     dword ptr [rsp+3A8h+var_1B8], 5
0x1400934a4  mov     byte ptr [rsp+3A8h+var_1A8+8], bl
0x1400934ab  mov     dword ptr [rsp+3A8h+var_1A8+0Ch], 0Fh
0x1400934b6  lea     r8, [rsp+3A8h+var_1B8]
0x1400934be  lea     edx, [rcx+28h]
0x1400934c1  mov     rcx, rax
0x1400934c4  call    cs:__imp_VidVsmSetPartitionConfig
0x1400934cb  nop     dword ptr [rax+rax+00h]
0x1400934d0  mov     rcx, [rsp+3A8h]; this
0x1400934d8  test    eax, eax
0x1400934da  jnz     short loc_1400934EC
0x1400934dc  lea     r8, aOnecoreVmWorke_17; "onecore\\vm\\worker\\wpcore\\workerhcll"...
0x1400934e3  lea     edx, [rax+57h]; void *
0x1400934e6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400934ec  mov     rcx, [r14]
0x1400934ef  cmp     [rcx+0B98h], bl
0x1400934f5  jz      short loc_140093522
0x1400934f7  lea     rdx, [rsp+3A8h+var_200]
0x1400934ff  call    ?LoadIgvmFileIntoGuest@VirtualMachine@@UEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; VirtualMachine::LoadIgvmFileIntoGuest(void)
0x140093504  mov     rdx, rax
0x140093507  lea     rcx, [rsp+3A8h+var_1E0]
0x14009350f  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140093514  lea     rcx, [rsp+3A8h+var_200]
0x14009351c  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140093521  nop
0x140093522  mov     r8, rbx
0x140093525  xor     edx, edx
0x140093527  mov     rcx, r15
0x14009352a  call    ?PowerOnVirtualMotherboard@WorkerTaskStarting@@AEAAJPEAVVmRepository@@T_VM_PERSIST_FLAGS@@@Z; WorkerTaskStarting::PowerOnVirtualMotherboard(VmRepository *,_VM_PERSIST_FLAGS)
0x14009352f  mov     edi, eax
0x140093531  test    eax, eax
0x140093533  js      loc_140093AD5
0x140093539  mov     rcx, [r14]; this
0x14009353c  call    ?RegisterGuestCrashManager@VirtualMachine@@QEAAJXZ; VirtualMachine::RegisterGuestCrashManager(void)
0x140093541  mov     edi, eax
0x140093543  test    eax, eax
0x140093545  jns     short loc_140093590
0x140093547  mov     esi, 4020h
0x14009354c  mov     ecx, esi
0x14009354e  call    VmlIsDebugTraceEnabled
0x140093553  test    eax, eax
0x140093555  jz      loc_140093A6A
0x14009355b  mov     r8d, edi
0x14009355e  lea     rdx, off_1402D9C40; "Failed to register the Guest Crash Mana"...
0x140093565  mov     ecx, esi
0x140093567  call    VmlDebugTraceWithError
0x14009356c  jmp     loc_140093A6A
0x140093571  xor     ebx, ebx
0x140093573  mov     edi, [rsp+3A8h+var_388]
0x140093577  mov     eax, ebx
0x140093579  mov     r15, [rsp+3A8h+var_368]
0x14009357e  mov     r14, [rsp+3A8h+var_1C8]
0x140093586  mov     r13, [rsp+3A8h+var_380]
0x14009358b  jmp     loc_1400937A2
0x140093590  cmp     dword ptr [r13+0], 33h ; '3'
0x140093595  ja      short loc_1400935CB
0x140093597  movsxd  rax, dword ptr [r13+0]
0x14009359b  mov     rcx, 8000100008004h
0x1400935a5  bt      rcx, rax
0x1400935a9  jnb     short loc_1400935CB
0x1400935ab  mov     rax, [r14]
0x1400935ae  mov     rcx, [rax+428h]
0x1400935b5  mov     rax, [rcx]
0x1400935b8  mov     rax, [rax+30h]
0x1400935bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400935c1  mov     edi, eax
0x1400935c3  test    eax, eax
0x1400935c5  js      loc_140093A6A
0x1400935cb  lea     r8, [rsp+3A8h+var_384]; int *
0x1400935d0  mov     edx, 32h ; '2'; unsigned int
0x1400935d5  mov     rcx, r15; this
0x1400935d8  call    ?UpdateStatusProgress@WorkerAsyncTaskBase@@MEAAXIAEAH@Z; WorkerAsyncTaskBase::UpdateStatusProgress(uint,int &)
0x1400935dd  cmp     [rsp+3A8h+var_384], ebx
0x1400935e1  jz      short loc_1400935ED
0x1400935e3  mov     edi, 800704C7h
0x1400935e8  jmp     loc_140093A6A
0x1400935ed  cmp     dword ptr [r13+0], 20h ; ' '
0x1400935f2  jz      short loc_14009360F
0x1400935f4  mov     rax, [r14]
0x1400935f7  mov     rcx, [rax+410h]
0x1400935fe  mov     rax, [rcx]
0x140093601  mov     edx, esi
0x140093603  mov     rax, [rax+290h]
0x14009360a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009360f  xor     edx, edx; Val
0x140093611  mov     r8d, 150h; Size
0x140093617  lea     rcx, [rsp+3A8h+var_188]; void *
0x14009361f  call    memset_0
0x140093624  mov     rdi, [r14]
0x140093627  lea     rcx, [rsp+3A8h+var_188]; struct wil::details::IFailureCallback *
0x14009362f  call    ??0?$ActivityBase@VVmWorkerTrace@@$01$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140093634  lea     rax, ??_7BootStateImporterFlush@VmWorkerTrace@@6B@; const VmWorkerTrace::BootStateImporterFlush::`vftable'
0x14009363b  mov     [rsp+3A8h+var_188], rax
0x140093643  lea     rdx, [rdi+470h]; struct _GUID *
0x14009364a  lea     rcx, [rsp+3A8h+var_188]; this
0x140093652  call    ?StartActivity@BootStateImporterFlush@VmWorkerTrace@@QEAAXAEBU_GUID@@@Z; VmWorkerTrace::BootStateImporterFlush::StartActivity(_GUID const &)
0x140093657  nop
0x140093658  mov     [rsp+3A8h+var_380], r15
0x14009365d  lea     rcx, [rsp+3A8h+var_380]
0x140093662  call    wil__ResultFromException__lambda_1e435c07f28aa931d7536c0492f26ff8___
0x140093667  mov     edi, eax
0x140093669  mov     rcx, [rsp+3A8h]; this
0x140093671  test    eax, eax
0x140093673  jns     short loc_140093685
0x140093675  mov     r9d, eax; char *
0x140093678  mov     r8, r12; unsigned int
0x14009367b  mov     edx, 249h; void *
0x140093680  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140093685  mov     edx, edi
0x140093687  lea     rcx, [rsp+3A8h+var_188]
0x14009368f  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$01$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140093694  lea     rcx, [rsp+3A8h+var_188]; this
0x14009369c  test    edi, edi
0x14009369e  jns     short loc_1400936AA
0x1400936a0  call    ??1BootStateImporterFlush@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::BootStateImporterFlush::~BootStateImporterFlush(void)
0x1400936a5  jmp     loc_140093A6A
0x1400936aa  mov     [rsp+3A8h+var_388], esi; int
0x1400936ae  call    ??1BootStateImporterFlush@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::BootStateImporterFlush::~BootStateImporterFlush(void)
0x1400936b3  cmp     [rsp+3A8h+var_204], ebx
0x1400936ba  jz      loc_1400937CA
0x1400936c0  xor     edx, edx; Val
0x1400936c2  mov     r8d, 150h; Size
0x1400936c8  lea     rcx, [rsp+3A8h+var_188]; void *
0x1400936d0  call    memset_0
0x1400936d5  mov     rdi, [r14]
0x1400936d8  lea     rdx, aIsolatedvmboot; "IsolatedVmBootImport"
0x1400936df  lea     rcx, [rsp+3A8h+var_188]; struct wil::details::IFailureCallback *
0x1400936e7  call    ??0?$ActivityBase@VVmWorkerTrace@@$01$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400936ec  lea     rax, ??_7IsolatedVmBootImport@VmWorkerTrace@@6B@; const VmWorkerTrace::IsolatedVmBootImport::`vftable'
0x1400936f3  mov     [rsp+3A8h+var_188], rax
  ... truncated ...
```
