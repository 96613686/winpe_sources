# CAudioDeviceGraph::Initialize(AUDIO_DEVICE_PIPE_DESCRIPTOR *,IUnknown *,IAudioGraphCallback *,ulong)

- ea: `0x140067680`
- end: `0x1400683ac`
- name: `?Initialize@CAudioDeviceGraph@@UEAAJPEAUAUDIO_DEVICE_PIPE_DESCRIPTOR@@PEAUIUnknown@@PEAUIAudioGraphCallback@@K@Z`
- size: `3372`
- prototype: `__int64 __usercall@<rax>(CAudioDeviceGraph *__hidden this@<rcx>, struct AUDIO_DEVICE_PIPE_DESCRIPTOR *@<rdx>, struct IUnknown *@<r8>, struct IAudioGraphCallback *@<r9>, unsigned int)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140008124`
- `0x140008580`
- `0x14000ac0c`
- `0x14000c33c`
- `0x14000e11c`
- `0x140011ea8`
- `0x14001a3b0`
- `0x14001af2c`
- `0x14001c9d8`
- `0x14001d790`
- `0x14001d854`
- `0x140024c18`
- `0x14002fa54`
- `0x1400332b4`
- `0x140036100`
- `0x14003de5c`
- `0x14004877c`
- `0x140050d40`
- `0x1400516e8`
- `0x14005d0e0`
- `0x140067680`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006771d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140067e43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006800d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400680b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140068381`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006771d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140067e43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006800d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400680b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140068381`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400676e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140067f78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400676e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140067f78`
- `MMDevAPI!__imp_mmdDevGetInstanceIdFromMMDeviceId` at `0x140067cf5`
- `MMDevAPI!__imp_mmdDevGetInstanceIdFromMMDeviceId` at `0x140067cf5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140067dd1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140067dd1`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CAudioDeviceGraph::Initialize(
        CAudioDeviceGraph *this,
        struct AUDIO_DEVICE_PIPE_DESCRIPTOR *a2,
        struct _RTL_CRITICAL_SECTION *a3,
        struct IAudioGraphCallback *a4,
        unsigned int a5)
{
  struct AUDIO_DEVICE_PIPE_DESCRIPTOR *v6; // r12
  CAudioDeviceGraph *v7; // r13
  struct _RTL_CRITICAL_SECTION *v8; // r14
  int DeviceGraphObjectCacheManager; // ebx
  __int64 v10; // rdx
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  __int64 v13; // rax
  __int64 v14; // r15
  __int64 v15; // rdx
  struct IAudioPump *v16; // rdi
  void (__fastcall *v17)(struct IAudioPump *, const struct _tlgProvider_t *); // rbx
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  _QWORD *v21; // r15
  int v22; // eax
  __int64 v23; // rcx
  struct IAudioPump *v24; // rdi
  void (__fastcall *v25)(struct IAudioPump *, const struct _tlgProvider_t *); // rbx
  const struct _tlgProvider_t *v26; // rdx
  __int64 v27; // rcx
  int v28; // eax
  unsigned int v29; // edx
  CPipeInstance *v30; // rcx
  __int64 v31; // rcx
  int v32; // eax
  unsigned int v33; // edx
  CPipeInstance *v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rbx
  struct Windows::Media::Devices::IAudioDeviceModulesManager **v37; // rdi
  __int64 v38; // rcx
  __int64 v39; // rcx
  unsigned int v40; // edx
  CPipeInstance *v41; // rcx
  __int64 v42; // rcx
  int v43; // eax
  unsigned int v44; // edx
  CPipeInstance *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rcx
  int v49; // eax
  unsigned int v50; // edx
  CPipeInstance *v51; // rcx
  __int64 v52; // rcx
  HRESULT Instance; // eax
  unsigned int v54; // edi
  unsigned int v55; // edx
  CPipeInstance *v56; // rcx
  __int64 v57; // rcx
  int v58; // eax
  unsigned int v59; // edx
  CPipeInstance *v60; // rcx
  __int64 v61; // rcx
  int v62; // eax
  unsigned int v63; // edx
  CPipeInstance *v64; // rcx
  __int64 v65; // rcx
  struct _RTL_CRITICAL_SECTION *v66; // rbx
  __int64 v67; // r8
  __int64 v68; // rax
  char *v69; // rdi
  unsigned int v70; // edx
  CPipeInstance *v71; // rcx
  __int64 v72; // rcx
  CPipeInstance *v73; // rax
  int v74; // ebx
  unsigned int v75; // ecx
  struct IAudioPump *v76; // rax
  __int64 v77; // rcx
  const struct _tlgProvider_t *v78; // rax
  __int64 v79; // r8
  int v80; // r9d
  unsigned int v81; // edx
  CPipeInstance *v82; // rcx
  ATL::CAtlException *v83; // rbx
  int ppv; // [rsp+20h] [rbp-188h]
  int ppva; // [rsp+20h] [rbp-188h]
  int ppvb; // [rsp+20h] [rbp-188h]
  CPipeInstance *v87; // [rsp+80h] [rbp-128h] BYREF
  struct IDeviceGraphObjectCacheManager *v88; // [rsp+88h] [rbp-120h] BYREF
  bool v89[8]; // [rsp+90h] [rbp-118h]
  struct IAudioPump *v90; // [rsp+98h] [rbp-110h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A0h] [rbp-108h] BYREF
  char *v92; // [rsp+A8h] [rbp-100h] BYREF
  struct IAudioGraphCallback *v93; // [rsp+B0h] [rbp-F8h] BYREF
  char **v94; // [rsp+B8h] [rbp-F0h] BYREF
  struct _RTL_CRITICAL_SECTION *v95; // [rsp+C0h] [rbp-E8h] BYREF
  struct AUDIO_DEVICE_PIPE_DESCRIPTOR *v96; // [rsp+C8h] [rbp-E0h] BYREF
  CAudioDeviceGraph *v97; // [rsp+D0h] [rbp-D8h] BYREF
  char *v98; // [rsp+D8h] [rbp-D0h] BYREF
  __int128 *v99; // [rsp+E0h] [rbp-C8h] BYREF
  _QWORD *v100; // [rsp+E8h] [rbp-C0h] BYREF
  double v101; // [rsp+F0h] [rbp-B8h] BYREF
  char *v102; // [rsp+F8h] [rbp-B0h] BYREF
  _DWORD *v103; // [rsp+100h] [rbp-A8h]
  __int64 *v104; // [rsp+108h] [rbp-A0h]
  CAudioDeviceGraph *v105; // [rsp+110h] [rbp-98h]
  char v106; // [rsp+118h] [rbp-90h]
  struct _RTL_CRITICAL_SECTION *v107; // [rsp+120h] [rbp-88h]
  char *v108; // [rsp+128h] [rbp-80h]
  ATL::CAtlException *v109; // [rsp+130h] [rbp-78h] BYREF
  __int64 v110; // [rsp+138h] [rbp-70h] BYREF
  __int128 v111; // [rsp+140h] [rbp-68h]
  __int128 v112; // [rsp+150h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v93 = a4;
  lpCriticalSection = a3;
  v6 = a2;
  v7 = this;
  v97 = this;
  v96 = a2;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 264);
  v95 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 264);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  v107 = v8;
  if ( !a4 )
  {
    DeviceGraphObjectCacheManager = -2147467261;
    v10 = 124;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodevicegraph.cpp",
      (const char *)(unsigned int)DeviceGraphObjectCacheManager,
      ppv);
LABEL_4:
    if ( !v8 )
      return (unsigned int)DeviceGraphObjectCacheManager;
    v11 = v8;
LABEL_6:
    LeaveCriticalSection(v11);
    return (unsigned int)DeviceGraphObjectCacheManager;
  }
  v99 = (__int128 *)((char *)v7 + 256);
  if ( *((_DWORD *)v7 + 64) )
  {
    DeviceGraphObjectCacheManager = -2005139440;
    v10 = 127;
    goto LABEL_3;
  }
  DeviceGraphObjectCacheManager = ValidateDevicePipeDescriptor(v6);
  if ( DeviceGraphObjectCacheManager < 0 )
  {
    v10 = 130;
    goto LABEL_3;
  }
  v13 = *((_QWORD *)v6 + 4);
  if ( (double)(int)v13 > 25000000.0 )
  {
    DeviceGraphObjectCacheManager = -2147024809;
    v10 = 133;
    goto LABEL_3;
  }
  *(_QWORD *)&v101 = (char *)v7 + 128;
  *((_QWORD *)v7 + 16) = v13;
  v103 = (_DWORD *)((char *)v7 + 140);
  *((_DWORD *)v7 + 35) = *((_DWORD *)v6 + 18);
  *((_DWORD *)v7 + 76) = *((_DWORD *)v6 + 34);
  v102 = (char *)v7 + 344;
  *(_OWORD *)((char *)v7 + 344) = *(_OWORD *)((char *)v6 + 148);
  v14 = *((_QWORD *)v6 + 1);
  v92 = (char *)v14;
  v98 = (char *)v14;
  *((_DWORD *)v7 + 77) = *((_DWORD *)v6 + 25);
  *((float *)v7 + 34) = (float)*(int *)(v14 + 4);
  v88 = 0;
  DeviceGraphObjectCacheManager = GetDeviceGraphObjectCacheManager(&v88);
  if ( DeviceGraphObjectCacheManager < 0 )
  {
    v15 = 154;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodevicegraph.cpp",
      (const char *)(unsigned int)DeviceGraphObjectCacheManager,
      ppv);
LABEL_17:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v88);
    goto LABEL_4;
  }
  v90 = 0;
  (**(void (__fastcall ***)(struct IDeviceGraphObjectCacheManager *, GUID *, struct IAudioPump **))v88)(
    v88,
    &GUID_bba447bc_0c11_4b7a_ba32_c5284a54692f,
    &v90);
  v16 = v90;
  v17 = *(void (__fastcall **)(struct IAudioPump *, const struct _tlgProvider_t *))(*(_QWORD *)v90 + 24LL);
  v18 = AudioDgTelemetryProvider::Provider();
  v17(v16, v18);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v90);
  v111 = 0;
  v110 = *((_QWORD *)v6 + 4);
  *(float *)&v111 = (float)*(int *)(v14 + 4);
  DWORD1(v111) = *(unsigned __int16 *)(v14 + 2);
  DWORD2(v111) = *((_DWORD *)v6 + 25) == 1;
  v94 = (char **)((char *)v6 + 56);
  ppv = (_DWORD)v7 + 336;
  DeviceGraphObjectCacheManager = (*(__int64 (__fastcall **)(struct IDeviceGraphObjectCacheManager *, _QWORD, __int64 *, LPCRITICAL_SECTION))(*(_QWORD *)v88 + 24LL))(
                                    v88,
                                    *((_QWORD *)v6 + 7),
                                    &v110,
                                    lpCriticalSection);
  if ( DeviceGraphObjectCacheManager < 0 )
  {
    v15 = 168;
    goto LABEL_16;
  }
  v21 = (_QWORD *)((char *)v7 + 144);
  v104 = (__int64 *)((char *)v7 + 144);
  DeviceGraphObjectCacheManager = ATL::CComCreator<ATL::CComObject<CAudioProcessor>>::CreateInstance(
                                    v20,
                                    v19,
                                    (char *)v7 + 144);
  if ( DeviceGraphObjectCacheManager < 0 )
  {
    v15 = 171;
    goto LABEL_16;
  }
  v105 = v7;
  v106 = 1;
  v22 = (*(__int64 (__fastcall **)(_QWORD, bool, _QWORD, LPCRITICAL_SECTION))(*(_QWORD *)*v21 + 24LL))(
          *v21,
          *v103 != 0,
          *((_QWORD *)v7 + 42),
          lpCriticalSection);
  DeviceGraphObjectCacheManager = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodevicegraph.cpp",
      (const char *)(unsigned int)v22,
      ppv);
    v23 = *v21;
    if ( *v21 )
    {
      *v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    goto LABEL_17;
  }
  v90 = 0;
  (**(void (__fastcall ***)(_QWORD, GUID *, struct IAudioPump **))*v21)(
    *v21,
    &GUID_bba447bc_0c11_4b7a_ba32_c5284a54692f,
    &v90);
  v24 = v90;
  v25 = *(void (__fastcall **)(struct IAudioPump *, const struct _tlgProvider_t *))(*(_QWORD *)v90 + 24LL);
  v26 = AudioDgTelemetryProvider::Provider();
  v25(v24, v26);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v90);
  v87 = 0;
  DeviceGraphObjectCacheManager = CPipeInstance::CreateDevicePipeInstance(
                                    *v21,
                                    *((_QWORD *)v7 + 42),
                                    v6,
                                    lpCriticalSection);
  if ( DeviceGraphObjectCacheManager < 0 )
  {
    v87 = 0;
    v27 = *v21;
    if ( *v21 )
    {
      *v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    goto LABEL_17;
  }
  v28 = CPipeInstance::Initialize(v87);
  DeviceGraphObjectCacheManager = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodevicegraph.cpp",
      (const char *)(unsigned int)v28,
      (int)&v87);
    v30 = v87;
    v87 = 0;
    if ( v30 )
      CPipeInstance::`scalar deleting destructor'(v30, v29);
    v31 = *v21;
    if ( *v21 )
    {
      *v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    goto LABEL_17;
  }
  v32 = CPipeInstance::ConnectAPOs(v87, v93);
  DeviceGraphObjectCacheManager = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodevicegraph.cpp",
      (const char *)(unsigned int)v32,
      (int)&v87);
    v34 = v87;
    v87 = 0;
    if ( v34 )
      CPipeInstance::`scalar deleting destructor'(v34, v33);
    v35 = *v21;
    if ( *v21 )
    {
      *v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    goto LABEL_17;
  }
  v36 = *(_QWORD *)(*(_QWORD *)ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::GetTail((char *)v87 + 16)
                  + 32LL);
  v37 = (struct Windows::Media::Devices::IAudioDeviceModulesManager **)((char *)v7 + 376);
  v38 = *((_QWORD *)v7 + 47);
  *((_QWORD *)v7 + 47) = 0;
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v7 == (CAudioDeviceGraph *)-376LL )
  {
    DeviceGraphObjectCacheManager = -2147467261;
  }
  else
  {
    *v37 = *(struct Windows::Media::Devices::IAudioDeviceModulesManager **)(v36 + 16);
    v39 = *(_QWORD *)(v36 + 16);
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
    DeviceGraphObjectCacheManager = 0;
  }
  if ( DeviceGraphObjectCacheManager < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC6,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodevicegraph.cpp",
      (const char *)(unsigned int)DeviceGraphObjectCacheManager,
      (int)&v87);
    v41 = v87;
    v87 = 0;
    if ( v41 )
      CPipeInstance::`scalar deleting destructor'(v41, v40);
    v42 = *v21;
    if ( *v21 )
    {
      *v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    goto LABEL_17;
  }
  v43 = CPipeInstance::AddConnectionsAndActivateAPOs(v87, *v37);
  DeviceGraphObjectCacheManager = v43;
  if ( v43 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodevicegraph.cpp",
      (const char *)(unsigned int)v43,
      (int)&v87);
    v45 = v87;
    v87 = 0;
    if ( v45 )
      CPipeInstance::`scalar deleting destructor'(v45, v44);
    v46 = *v21;
    if ( *v21 )
    {
      *v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    goto LABEL_17;
  }
  v89[0] = (a5 & 0x400001) != 0;
  v100 = (_QWORD *)((char *)v7 + 384);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    (char *)v7 + 384,
    0);
  mmdDevGetInstanceIdFromMMDeviceId(*v94, (char *)v7 + 384);
  v47 = *(_QWORD *)((char *)v6 + 164) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( !v47 )
    v47 = *(_QWORD *)((char *)v6 + 172) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  v48 = *((_QWORD *)v7 + 49);
  *((_QWORD *)v7 + 49) = 0;
  if ( v47 )
  {
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    Instance = CoCreateInstance(
                 (const IID *const)((char *)v6 + 164),
                 0,
                 0x17u,
                 &GUID_c4e70434_407d_416b_94be_9717b79065fb,
                 (LPVOID *)v7 + 49);
    v54 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDA,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodevicegraph.cpp",
        (const char *)(unsigned int)Instance,
        ppva);
      v56 = v87;
      v87 = 0;
      if ( v56 )
        CPipeInstance::`scalar deleting destructor'(v56, v55);
      v57 = *v21;
      if ( *v21 )
      {
        *v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v88);
      if ( v8 )
        LeaveCriticalSection(v8);
      return v54;
    }
    v58 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v7 + 49) + 24LL))(
            *((_QWORD *)v7 + 49),
            (__int64)v6 + 180);
    DeviceGraphObjectCacheManager = v58;
    if ( v58 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodevicegraph.cpp",
        (const char *)(unsigned int)v58,
        ppva);
      v60 = v87;
      v87 = 0;
      if ( v60 )
        CPipeInstance::`scalar deleting destructor'(v60, v59);
      v61 = *v21;
      if ( *v21 )
      {
        *v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      }
      goto LABEL_17;
    }
  }
  else
  {
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    v49 = Microsoft::WRL::Details::MakeAndInitialize<CStandardCrossProcessEventManager,ICrossProcessEventManager,>((char *)v7 + 392);
    DeviceGraphObjectCacheManager = v49;
    if ( v49 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodevicegraph.cpp",
        (const char *)(unsigned int)v49,
        (int)&v87);
      v51 = v87;
      v87 = 0;
      if ( v51 )
        CPipeInstance::`scalar deleting destructor'(v51, v50);
      v52 = *v21;
      if ( *v21 )
      {
        *v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      }
      goto LABEL_17;
    }
  }
  v90 = 0;
  v62 = CAudioDeviceGraph::CreateAndInitializePump(v7, &v90, v87, v6, v89[0], (struct IUnknown *)lpCriticalSection);
  DeviceGraphObjectCacheManager = v62;
  if ( v62 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodevicegraph.cpp",
      (const char *)(unsigned int)v62,
      ppvb);
    wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v90);
    v64 = v87;
    v87 = 0;
    if ( v64 )
      CPipeInstance::`scalar deleting destructor'(v64, v63);
    v65 = *v21;
    if ( *v21 )
    {
      *v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    }
    goto LABEL_17;
  }
  v66 = (struct _RTL_CRITICAL_SECTION *)((char *)v7 + 216);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)v7 + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 216));
  try
  {
    v108 = (char *)v7 + 216;
    v93 = v87;
    v68 = ATL::CAtlList<CChildSubmixInstance *,ATL::CElementTraits<CChildSubmixInstance *>>::NewNode(
            (char *)v7 + 168,
            &v93,
            v67,
            *((_QWORD *)v7 + 21));
    if ( *((_QWORD *)v7 + 21) )
      *(_QWORD *)(*((_QWORD *)v7 + 21) + 8LL) = v68;
    else
      *((_QWORD *)v7 + 22) = v68;
    *((_QWORD *)v7 + 21) = v68;
    v69 = v92;
  }
  catch ( ATL::CAtlException *v109 )
  {
    v83 = v109;
    if ( *(_DWORD *)v109 == -1073741571 )
      _o__resetstkoflw();
    LODWORD(v92) = *(_DWORD *)v83;
    DeviceGraphObjectCacheManager = (int)v92;
    if ( (int)v92 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodevicegraph.cpp",
        (const char *)(unsigned int)v92,
        ppvb);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v90);
      v71 = v87;
      v87 = 0;
      if ( v71 )
        CPipeInstance::`scalar deleting destructor'(v71, v70);
      v72 = *v104;
      if ( *v104 )
      {
        *v104 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v88);
      v11 = v95;
      if ( !v95 )
        return (unsigned int)DeviceGraphObjectCacheManager;
      goto LABEL_6;
    }
    v6 = v96;
    v7 = v97;
    v8 = v95;
    v69 = v98;
    v66 = lpCriticalSection;
  }
  if ( v66 )
    LeaveCriticalSection(v66);
  v73 = v87;
  v87 = 0;
  *((_QWORD *)v7 + 20) = v73;
  *(_DWORD *)v99 = 1;
  *((_DWORD *)v7 + 28) = 0;
  v112 = 0;
  if ( *(_WORD *)v69 == 0xFFFE )
  {
    v112 = *(_OWORD *)(v69 + 24);
  }
  else
  {
    *(_QWORD *)((char *)&v112 + 4) = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
    HIDWORD(v112) = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
    LODWORD(v112) = *(unsigned __int16 *)v69;
  }
  v74 = 0;
  v75 = 0;
  if ( *((_DWORD *)v6 + 24) )
  {
    while ( *((_QWORD *)v6 + 2 * v75 + 27) != *(_QWORD *)&GUID_0fa53099_5317_46af_9376_9a04a4b550f9.Data1
         || *((_QWORD *)v6 + 2 * v75 + 28) != *(_QWORD *)GUID_0fa53099_5317_46af_9376_9a04a4b550f9.Data4 )
    {
      if ( ++v75 >= *((_DWORD *)v6 + 24) )
        goto LABEL_120;
    }
    v74 = 1;
  }
LABEL_120:
  v106 = 0;
  v76 = v90;
  v90 = 0;
  v77 = *((_QWORD *)v7 + 19);
  *((_QWORD *)v7 + 19) = v76;
  if ( v77 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
  v78 = AudioDgTelemetryProvider::Provider();
  if ( *(_DWORD *)v78 > 4u && (unsigned __int8)tlgKeywordOn(v78, 0x400000000001LL, v79) )
  {
    LODWORD(v92) = v74;
    v99 = &v112;
    v100 = (_QWORD *)*v100;
    v98 = *v94;
    v97 = (struct AUDIO_DEVICE_PIPE_DESCRIPTOR *)((char *)v6 + 120);
    v96 = (struct AUDIO_DEVICE_PIPE_DESCRIPTOR *)((char *)v6 + 104);
    LODWORD(v93) = DWORD2(v111);
    LODWORD(v94) = DWORD1(v111);
    LODWORD(v95) = v111;
    LODWORD(lpCriticalSection) = *v103;
    v101 = (double)(int)**(_QWORD **)&v101 / 10000000.0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v80,
      (unsigned int)&unk_1400D1598,
      (_DWORD)v102,
      v80,
      (__int64)&v102,
      (__int64)&v101,
      (__int64)&lpCriticalSection,
      (__int64)&v95,
      (__int64)&v94,
      (__int64)&v93,
      (__int64)&v96,
      (__int64)&v97,
      (__int64)&v98,
      (__int64)&v100,
      (__int64)&v99,
      (__int64)&v92);
  }
  wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v90);
  v82 = v87;
  v87 = 0;
  if ( v82 )
    CPipeInstance::`scalar deleting destructor'(v82, v81);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v88);
  if ( v8 )
    LeaveCriticalSection(v8);
  return 0;
}

```

## disassembly

```asm
0x140067680  push    rbx
0x140067682  push    rsi
0x140067683  push    rdi
0x140067684  push    r12
0x140067686  push    r13
0x140067688  push    r14
0x14006768a  push    r15
0x14006768c  sub     rsp, 170h
0x140067693  mov     rax, cs:__security_cookie
0x14006769a  xor     rax, rsp
0x14006769d  mov     [rsp+1A8h+var_48], rax
0x1400676a5  mov     rbx, r9
0x1400676a8  mov     [rsp+1A8h+var_F8], rbx
0x1400676b0  mov     [rsp+1A8h+lpCriticalSection], r8
0x1400676b8  mov     r12, rdx
0x1400676bb  mov     r13, rcx
0x1400676be  mov     [rsp+1A8h+var_D8], rcx
0x1400676c6  mov     [rsp+1A8h+var_E0], rdx
0x1400676ce  lea     r14, [rcx+108h]
0x1400676d5  mov     [rsp+1A8h+var_E8], r14
0x1400676dd  mov     rcx, r14; lpCriticalSection
0x1400676e0  call    cs:__imp_EnterCriticalSection
0x1400676e6  mov     [rsp+1A8h+var_88], r14
0x1400676ee  xor     esi, esi
0x1400676f0  test    rbx, rbx
0x1400676f3  jnz     short loc_14006772A
0x1400676f5  mov     ebx, 80004003h
0x1400676fa  lea     edx, [rsi+7Ch]; void *
0x1400676fd  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140067704  mov     r9d, ebx; char *
0x140067707  mov     rcx, [rsp+1A8h]; this
0x14006770f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140067714  nop
0x140067715  test    r14, r14
0x140067718  jz      short loc_140067723
0x14006771a  mov     rcx, r14; lpCriticalSection
0x14006771d  call    cs:__imp_LeaveCriticalSection
0x140067723  mov     eax, ebx
0x140067725  jmp     loc_140068389
0x14006772a  lea     rax, [r13+100h]
0x140067731  mov     [rsp+1A8h+var_C8], rax
0x140067739  cmp     [rax], esi
0x14006773b  jz      short loc_140067749
0x14006773d  mov     ebx, 887C0010h
0x140067742  mov     edx, 7Fh
0x140067747  jmp     short loc_1400676FD
0x140067749  mov     rcx, r12; struct AUDIO_DEVICE_PIPE_DESCRIPTOR *
0x14006774c  call    ?ValidateDevicePipeDescriptor@@YAJPEAUAUDIO_DEVICE_PIPE_DESCRIPTOR@@@Z; ValidateDevicePipeDescriptor(AUDIO_DEVICE_PIPE_DESCRIPTOR *)
0x140067751  mov     ebx, eax
0x140067753  test    eax, eax
0x140067755  jns     short loc_14006775E
0x140067757  mov     edx, 82h
0x14006775c  jmp     short loc_1400676FD
0x14006775e  mov     rax, [r12+20h]
0x140067763  xorps   xmm0, xmm0
0x140067766  cvtsi2sd xmm0, rax
0x14006776b  comisd  xmm0, cs:__real@4177d78400000000
0x140067773  jbe     short loc_140067784
0x140067775  mov     ebx, 80070057h
0x14006777a  mov     edx, 85h
0x14006777f  jmp     loc_1400676FD
0x140067784  lea     rcx, [r13+80h]
0x14006778b  mov     [rsp+1A8h+var_B8], rcx
0x140067793  mov     [rcx], rax
0x140067796  lea     rcx, [r13+8Ch]
0x14006779d  mov     [rsp+1A8h+var_A8], rcx
0x1400677a5  mov     eax, [r12+48h]
0x1400677aa  mov     [rcx], eax
0x1400677ac  mov     eax, [r12+88h]
0x1400677b4  mov     [r13+130h], eax
0x1400677bb  lea     rax, [r13+158h]
0x1400677c2  mov     [rsp+1A8h+var_B0], rax
0x1400677ca  movups  xmm0, xmmword ptr [r12+94h]
0x1400677d3  movdqu  xmmword ptr [rax], xmm0
0x1400677d7  mov     r15, [r12+8]
0x1400677dc  mov     [rsp+1A8h+var_100], r15
0x1400677e4  mov     [rsp+1A8h+var_D0], r15
0x1400677ec  mov     eax, [r12+64h]
0x1400677f1  mov     [r13+134h], eax
0x1400677f8  mov     eax, [r15+4]
0x1400677fc  xorps   xmm0, xmm0
0x1400677ff  cvtsi2ss xmm0, rax
0x140067804  movss   dword ptr [r13+88h], xmm0
0x14006780d  mov     [rsp+1A8h+var_120], rsi
0x140067815  lea     rcx, [rsp+1A8h+var_120]; struct IDeviceGraphObjectCacheManager **
0x14006781d  call    ?GetDeviceGraphObjectCacheManager@@YAJPEAPEAUIDeviceGraphObjectCacheManager@@@Z; GetDeviceGraphObjectCacheManager(IDeviceGraphObjectCacheManager * *)
0x140067822  mov     ebx, eax
0x140067824  test    eax, eax
0x140067826  jns     short loc_140067857
0x140067828  mov     edx, 9Ah; void *
0x14006782d  mov     rcx, [rsp+1A8h]; this
0x140067835  mov     r9d, ebx; char *
0x140067838  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14006783f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140067844  nop
0x140067845  lea     rcx, [rsp+1A8h+var_120]
0x14006784d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140067852  jmp     loc_140067715
0x140067857  mov     [rsp+1A8h+var_110], rsi
0x14006785f  mov     rcx, [rsp+1A8h+var_120]
0x140067867  mov     rax, [rcx]
0x14006786a  lea     r8, [rsp+1A8h+var_110]
0x140067872  lea     rdx, _GUID_bba447bc_0c11_4b7a_ba32_c5284a54692f
0x140067879  mov     rax, [rax]
0x14006787c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067881  mov     rdi, [rsp+1A8h+var_110]
0x140067889  mov     rax, [rdi]
0x14006788c  mov     rbx, [rax+18h]
0x140067890  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x140067895  mov     rdx, rax
0x140067898  mov     rcx, rdi
0x14006789b  mov     rax, rbx
0x14006789e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400678a3  nop
0x1400678a4  lea     rcx, [rsp+1A8h+var_110]
0x1400678ac  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400678b1  xorps   xmm0, xmm0
0x1400678b4  movdqu  [rsp+1A8h+var_68], xmm0
0x1400678bd  mov     rax, [r12+20h]
0x1400678c2  mov     [rsp+1A8h+var_70], rax
0x1400678ca  mov     eax, [r15+4]
0x1400678ce  xorps   xmm0, xmm0
0x1400678d1  cvtsi2ss xmm0, rax
0x1400678d6  movss   dword ptr [rsp+1A8h+var_68], xmm0
0x1400678df  movzx   eax, word ptr [r15+2]
0x1400678e4  mov     dword ptr [rsp+1A8h+var_68+4], eax
0x1400678eb  mov     eax, dword ptr [rsp+1A8h+var_68+8]
0x1400678f2  mov     edi, 1
0x1400678f7  cmp     [r12+64h], edi
0x1400678fc  cmovz   eax, edi
0x1400678ff  mov     dword ptr [rsp+1A8h+var_68+8], eax
0x140067906  mov     rcx, [rsp+1A8h+var_120]
0x14006790e  lea     r10, [r12+38h]
0x140067913  mov     [rsp+1A8h+var_F0], r10
0x14006791b  lea     rdx, [r13+150h]
0x140067922  mov     rax, [rcx]
0x140067925  mov     [rsp+1A8h+ppv], rdx; int
0x14006792a  mov     r9, [rsp+1A8h+lpCriticalSection]
0x140067932  lea     r8, [rsp+1A8h+var_70]
0x14006793a  mov     rdx, [r10]
0x14006793d  mov     rax, [rax+18h]
0x140067941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067946  mov     ebx, eax
0x140067948  test    eax, eax
0x14006794a  jns     short loc_140067956
0x14006794c  mov     edx, 0A8h
0x140067951  jmp     loc_14006782D
0x140067956  lea     r15, [r13+90h]
0x14006795d  mov     [rsp+1A8h+var_A0], r15
0x140067965  mov     r8, r15
0x140067968  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCAudioProcessor@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CAudioProcessor>>::CreateInstance(void *,_GUID const &,void * *)
0x14006796d  mov     ebx, eax
0x14006796f  test    eax, eax
0x140067971  jns     short loc_14006797D
0x140067973  mov     edx, 0ABh
0x140067978  jmp     loc_14006782D
0x14006797d  mov     [rsp+1A8h+var_98], r13
0x140067985  mov     [rsp+1A8h+var_90], dil
0x14006798d  mov     rcx, [r15]
0x140067990  mov     rax, [rcx]
0x140067993  mov     edx, esi
0x140067995  mov     r8, [rsp+1A8h+var_A8]
0x14006799d  cmp     [r8], esi
0x1400679a0  setnz   dl
0x1400679a3  mov     r9, [rsp+1A8h+lpCriticalSection]
0x1400679ab  mov     r8, [r13+150h]
0x1400679b2  mov     rax, [rax+18h]
0x1400679b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400679bb  mov     ebx, eax
0x1400679bd  test    eax, eax
0x1400679bf  jns     short loc_1400679FB
0x1400679c1  mov     rcx, [rsp+1A8h]; this
0x1400679c9  mov     r9d, eax; char *
0x1400679cc  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400679d3  mov     edx, 0AFh; void *
0x1400679d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400679dd  nop
0x1400679de  mov     rcx, [r15]
0x1400679e1  test    rcx, rcx
0x1400679e4  jz      short loc_1400679F6
0x1400679e6  mov     [r15], rsi
0x1400679e9  mov     rax, [rcx]
0x1400679ec  mov     rax, [rax+10h]
0x1400679f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400679f5  nop
0x1400679f6  jmp     loc_140067845
0x1400679fb  mov     [rsp+1A8h+var_110], rsi
0x140067a03  mov     rcx, [r15]
0x140067a06  mov     rax, [rcx]
0x140067a09  lea     r8, [rsp+1A8h+var_110]
0x140067a11  lea     rdx, _GUID_bba447bc_0c11_4b7a_ba32_c5284a54692f
0x140067a18  mov     rax, [rax]
0x140067a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067a20  nop
0x140067a21  mov     rdi, [rsp+1A8h+var_110]
0x140067a29  mov     rax, [rdi]
0x140067a2c  mov     rbx, [rax+18h]
0x140067a30  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x140067a35  mov     rdx, rax
0x140067a38  mov     rcx, rdi
0x140067a3b  mov     rax, rbx
0x140067a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067a43  nop
0x140067a44  lea     rcx, [rsp+1A8h+var_110]
0x140067a4c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140067a51  mov     [rsp+1A8h+var_128], rsi
0x140067a59  lea     rax, [rsp+1A8h+var_128]
0x140067a61  mov     [rsp+1A8h+ppv], rax; int
0x140067a66  mov     r9, [rsp+1A8h+lpCriticalSection]
0x140067a6e  mov     r8, r12
0x140067a71  mov     rdx, [r13+150h]
0x140067a78  mov     rcx, [r15]
0x140067a7b  call    ?CreateDevicePipeInstance@CPipeInstance@@SAJPEAUIAudioProcessor@@PEAUIDeviceGraphObjectCache@@PEAUAUDIO_DEVICE_PIPE_DESCRIPTOR@@PEAUIUnknown@@AEAV?$unique_ptr@VCPipeInstance@@U?$default_delete@VCPipeInstance@@@wistd@@@wistd@@@Z; CPipeInstance::CreateDevicePipeInstance(IAudioProcessor *,IDeviceGraphObjectCache *,AUDIO_DEVICE_PIPE_DESCRIPTOR *,IUnknown *,wistd::unique_ptr<CPipeInstance,wistd::default_delete<CPipeInstance>> &)
0x140067a80  mov     ebx, eax
0x140067a82  test    eax, eax
0x140067a84  jns     short loc_140067ABE
0x140067a86  mov     rcx, [rsp+1A8h+var_128]; this
0x140067a8e  mov     [rsp+1A8h+var_128], rsi
0x140067a96  test    rcx, rcx
0x140067a99  jz      short loc_140067AA1
0x140067a9b  call    ??_GCPipeInstance@@QEAAPEAXI@Z; CPipeInstance::`scalar deleting destructor'(uint)
0x140067aa0  nop
0x140067aa1  mov     rcx, [r15]
0x140067aa4  test    rcx, rcx
0x140067aa7  jz      short loc_140067AB9
0x140067aa9  mov     [r15], rsi
0x140067aac  mov     rax, [rcx]
0x140067aaf  mov     rax, [rax+10h]
0x140067ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067ab8  nop
0x140067ab9  jmp     loc_140067845
0x140067abe  mov     rcx, [rsp+1A8h+var_128]; this
0x140067ac6  call    ?Initialize@CPipeInstance@@QEAAJXZ; CPipeInstance::Initialize(void)
0x140067acb  mov     ebx, eax
0x140067acd  test    eax, eax
0x140067acf  jns     short loc_140067B26
0x140067ad1  mov     rcx, [rsp+1A8h]; this
0x140067ad9  mov     r9d, eax; char *
0x140067adc  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140067ae3  mov     edx, 0C1h; void *
0x140067ae8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140067aed  nop
0x140067aee  mov     rcx, [rsp+1A8h+var_128]; this
0x140067af6  mov     [rsp+1A8h+var_128], rsi
0x140067afe  test    rcx, rcx
0x140067b01  jz      short loc_140067B09
0x140067b03  call    ??_GCPipeInstance@@QEAAPEAXI@Z; CPipeInstance::`scalar deleting destructor'(uint)
0x140067b08  nop
0x140067b09  mov     rcx, [r15]
0x140067b0c  test    rcx, rcx
0x140067b0f  jz      short loc_140067B21
0x140067b11  mov     [r15], rsi
0x140067b14  mov     rax, [rcx]
0x140067b17  mov     rax, [rax+10h]
0x140067b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067b20  nop
0x140067b21  jmp     loc_140067845
0x140067b26  mov     rdx, [rsp+1A8h+var_F8]; struct IAudioGraphCallback *
0x140067b2e  mov     rcx, [rsp+1A8h+var_128]; this
0x140067b36  call    ?ConnectAPOs@CPipeInstance@@QEAAJPEAUIAudioGraphCallback@@@Z; CPipeInstance::ConnectAPOs(IAudioGraphCallback *)
0x140067b3b  mov     ebx, eax
0x140067b3d  test    eax, eax
0x140067b3f  jns     short loc_140067B96
0x140067b41  mov     rcx, [rsp+1A8h]; this
0x140067b49  mov     r9d, eax; char *
0x140067b4c  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140067b53  mov     edx, 0C3h; void *
0x140067b58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140067b5d  nop
0x140067b5e  mov     rcx, [rsp+1A8h+var_128]; this
0x140067b66  mov     [rsp+1A8h+var_128], rsi
0x140067b6e  test    rcx, rcx
0x140067b71  jz      short loc_140067B79
0x140067b73  call    ??_GCPipeInstance@@QEAAPEAXI@Z; CPipeInstance::`scalar deleting destructor'(uint)
0x140067b78  nop
0x140067b79  mov     rcx, [r15]
0x140067b7c  test    rcx, rcx
0x140067b7f  jz      short loc_140067B91
0x140067b81  mov     [r15], rsi
0x140067b84  mov     rax, [rcx]
0x140067b87  mov     rax, [rax+10h]
0x140067b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067b90  nop
0x140067b91  jmp     loc_140067845
0x140067b96  mov     rcx, [rsp+1A8h+var_128]
0x140067b9e  add     rcx, 10h
0x140067ba2  call    ?GetTail@?$CAtlList@PEAVCProcessNode@@V?$CElementTraits@PEAVCProcessNode@@@ATL@@@ATL@@QEAAAEAPEAVCProcessNode@@XZ; ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::GetTail(void)
0x140067ba7  mov     rcx, [rax]
0x140067baa  mov     rbx, [rcx+20h]
0x140067bae  lea     rdi, [r13+178h]
0x140067bb5  mov     rcx, [rdi]
0x140067bb8  mov     [rdi], rsi
0x140067bbb  test    rcx, rcx
0x140067bbe  jz      short loc_140067BCD
0x140067bc0  mov     rax, [rcx]
0x140067bc3  mov     rax, [rax+10h]
0x140067bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067bcc  nop
0x140067bcd  test    rdi, rdi
0x140067bd0  jnz     short loc_140067BD9
  ... truncated ...
```
