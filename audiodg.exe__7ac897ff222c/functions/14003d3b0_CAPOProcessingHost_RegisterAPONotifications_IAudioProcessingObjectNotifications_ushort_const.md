# CAPOProcessingHost::RegisterAPONotifications(IAudioProcessingObjectNotifications *,ushort const *)

- ea: `0x14003d3b0`
- end: `0x14003dc5c`
- name: `?RegisterAPONotifications@CAPOProcessingHost@@UEAAJPEAUIAudioProcessingObjectNotifications@@PEBG@Z`
- size: `2220`
- prototype: `__int64 __fastcall(CAPOProcessingHost *__hidden this, struct IAudioProcessingObjectNotifications *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140008124`
- `0x14000c33c`
- `0x14000e11c`
- `0x14000f3f8`
- `0x140021984`
- `0x140021b28`
- `0x1400223f8`
- `0x1400237ec`
- `0x14002cf6c`
- `0x140031a68`
- `0x140032608`
- `0x140032e10`
- `0x1400338c8`
- `0x1400367dc`
- `0x140039f54`
- `0x14003a800`
- `0x14003ade8`
- `0x14003d3b0`
- `0x1400465b8`
- `0x14004d3e4`
- `0x140053ed8`
- `0x14005411c`
- `0x1400542d8`
- `0x140056f10`
- `0x14005808c`
- `0x140059804`
- `0x14005d7bc`
- `0x14005e168`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d48c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d4c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d48c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d4c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003d42f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003d42f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003d58c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003d62f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003d768`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003d8be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003d990`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003db73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003dbdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003dc17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003d58c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003d62f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003d768`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003d8be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003d990`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003db73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003dbdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003dc17`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CAPOProcessingHost::RegisterAPONotifications(
        CAPOProcessingHost *this,
        struct IAudioProcessingObjectNotifications *a2,
        const unsigned __int16 *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  __int64 v10; // rax
  int v11; // ebx
  void *v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // rbx
  void *v15; // rdi
  unsigned int v16; // r15d
  struct CAPOProcessingHostObject *v17; // rbx
  __int64 v18; // r14
  void *v19; // rcx
  int v20; // eax
  __int64 v21; // rdx
  int started; // eax
  int EnvironmentStateChangedNotificationHandler; // r14d
  void *v24; // rcx
  unsigned int i; // r15d
  __int64 v26; // r14
  int v27; // eax
  int v28; // r14d
  int v29; // eax
  int v30; // eax
  __int64 v31; // rdx
  const struct _tlgProvider_t *v32; // rax
  int v33; // r8d
  int v34; // r9d
  void *v35; // rcx
  void *v36; // rcx
  int v37; // [rsp+20h] [rbp-98h]
  LPVOID pv; // [rsp+40h] [rbp-78h] BYREF
  struct IPropertyStore *v39; // [rsp+48h] [rbp-70h] BYREF
  struct CAPOProcessingHostObject *v40; // [rsp+50h] [rbp-68h] BYREF
  __int64 *v41; // [rsp+58h] [rbp-60h] BYREF
  struct CAPOEnvironmentStateChangedNotificationsHandler *v42; // [rsp+60h] [rbp-58h] BYREF
  struct IPropertyStore *v43; // [rsp+68h] [rbp-50h] BYREF
  void *v44; // [rsp+70h] [rbp-48h] BYREF
  LPVOID *p_pv; // [rsp+78h] [rbp-40h] BYREF
  __int64 v46; // [rsp+80h] [rbp-38h] BYREF
  char v47; // [rsp+88h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  unsigned int v49; // [rsp+D8h] [rbp+20h] BYREF

  v39 = 0;
  try
  {
    v6 = wil::com_query_to_nothrow<IAudioProcessingObject,IAudioProcessingObjectNotifications * &>();
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20C,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
        (const char *)(unsigned int)v6,
        v37);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
      return v7;
    }
    v40 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
    v43 = v39;
    std::_Hash<std::_Umap_traits<IAudioProcessingObject *,wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy>,std::_Uhash_compare<IAudioProcessingObject *,std::hash<IAudioProcessingObject *>,std::equal_to<IAudioProcessingObject *>>,std::allocator<std::pair<IAudioProcessingObject * const,wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy>>>,0>>::find(
      (char *)this + 184,
      &v42,
      &v43);
    if ( v42 == *((struct CAPOEnvironmentStateChangedNotificationsHandler **)this + 24) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x212,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
        (const char *)0x80070490LL,
        v37);
      if ( this != (CAPOProcessingHost *)-144LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
      return 2147943568LL;
    }
    wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy>::operator=(&v40, (char *)v42 + 24);
    if ( this != (CAPOProcessingHost *)-144LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
    pv = 0;
    v49 = 0;
    v41 = 0;
    if ( ((__int64 (__fastcall *)(struct IPropertyStore *, GUID *, __int64 **))v39->lpVtbl->QueryInterface)(
           v39,
           &GUID_ca2cfbde_a9d6_4eb0_bc95_c4d026b380f0,
           &v41) < 0 )
    {
      v13 = *(_QWORD *)a2;
      p_pv = &pv;
      v46 = 0;
      v47 = 1;
      v11 = (*(__int64 (__fastcall **)(struct IAudioProcessingObjectNotifications *, __int64 *, unsigned int *))(v13 + 24))(
              a2,
              &v46,
              &v49);
      wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21F,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
          (const char *)(unsigned int)v11,
          v37);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
        v12 = pv;
        pv = 0;
        if ( !v12 )
          goto LABEL_14;
        goto LABEL_13;
      }
    }
    else
    {
      v10 = *v41;
      p_pv = &pv;
      v46 = 0;
      v47 = 1;
      v11 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *, unsigned int *))(v10 + 40))(v41, 7, &v46, &v49);
      wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21B,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
          (const char *)(unsigned int)v11,
          v37);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
        v12 = pv;
        pv = 0;
        if ( !v12 )
        {
LABEL_14:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
          return (unsigned int)v11;
        }
LABEL_13:
        CoTaskMemFree(v12);
        goto LABEL_14;
      }
    }
    if ( !pv || !v49 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
      v35 = pv;
      pv = 0;
      if ( v35 )
        goto LABEL_85;
      goto LABEL_86;
    }
    v14 = saturated_mul(v49, 4u);
    v15 = operator new[](v14);
    memset_0(v15, 0, v14);
    v44 = v15;
    if ( !v15 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x227,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
        (const char *)0x8007000ELL,
        v37);
      std::unique_ptr<unsigned int [0]>::~unique_ptr<unsigned int [0]>(&v44);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
      v36 = pv;
      pv = 0;
      if ( v36 )
        CoTaskMemFree(v36);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
      return 2147942414LL;
    }
    v16 = 0;
    v17 = v40;
    while ( v16 < v49 )
    {
      v18 = 32LL * v16;
      *((_DWORD *)v15 + v16) = *(_DWORD *)((char *)pv + v18);
      switch ( *(_DWORD *)((char *)pv + v18) )
      {
        case 1:
          goto LABEL_44;
        case 2:
          v20 = CAPOProcessingHost::AddEndpointPropertyChangeNotificationClient(
                  this,
                  (struct AUDIO_ENDPOINT_PROPERTY_CHANGE_APO_NOTIFICATION_DESCRIPTOR *)((char *)pv + v18 + 8),
                  v17);
          if ( v20 >= 0 )
            break;
          v21 = 565;
          goto LABEL_46;
        case 3:
          v20 = CAPOProcessingHost::AddAudioSystemEffectsPropertyStoreNotificationClient(
                  this,
                  (struct AUDIO_SYSTEMEFFECTS_PROPERTY_CHANGE_APO_NOTIFICATION_DESCRIPTOR *)((char *)pv + v18 + 8),
                  v17);
          if ( v20 >= 0 )
            break;
          v21 = 569;
          goto LABEL_46;
        case 4:
LABEL_44:
          v20 = CAPOProcessingHost::AddEndpointVolumeNotificationClient(
                  this,
                  *(unsigned int *)((char *)pv + v18),
                  (char *)pv + v18 + 8,
                  v17);
          if ( v20 >= 0 )
            break;
          v21 = 561;
          goto LABEL_46;
        case 5:
          v20 = CAPOProcessingHost::AddDeviceOrientationNotificationClient(this, v17);
          if ( v20 >= 0 )
            break;
          v21 = 573;
          goto LABEL_46;
        case 6:
          if ( IsCaptureDevice(*(struct IMMDevice **)((char *)pv + v18 + 8)) )
          {
            v20 = CAPOProcessingHost::AddMicBoostNotificationClient(
                    this,
                    (struct AUDIO_MICROPHONE_BOOST_APO_NOTIFICATION_DESCRIPTOR *)((char *)pv + v18 + 8),
                    v17);
            if ( v20 < 0 )
            {
              v21 = 579;
              goto LABEL_46;
            }
          }
          break;
        case 7:
          v20 = CAPOProcessingHost::AddEnvironmentStateChangedNotificationClient(this, a3, v17);
          if ( v20 < 0 )
          {
            v21 = 584;
LABEL_46:
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)v21,
              (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
              (const char *)(unsigned int)v20,
              v37);
          }
          break;
        default:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x24C,
            (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
            (const char *)0x80070057LL,
            v37);
          std::unique_ptr<unsigned int [0]>::~unique_ptr<unsigned int [0]>(&v44);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
          v19 = pv;
          pv = 0;
          if ( v19 )
            CoTaskMemFree(v19);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
          return 2147942487LL;
      }
      ++v16;
    }
    started = CAPOProcessingHostObject::StartSendingNotifications(v17);
    EnvironmentStateChangedNotificationHandler = started;
    if ( started < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x250,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
        (const char *)(unsigned int)started,
        v37);
      std::unique_ptr<unsigned int [0]>::~unique_ptr<unsigned int [0]>(&v44);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
      v24 = pv;
      pv = 0;
      if ( v24 )
LABEL_50:
        CoTaskMemFree(v24);
LABEL_51:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
      return (unsigned int)EnvironmentStateChangedNotificationHandler;
    }
    for ( i = 0; i < v49; ++i )
    {
      v26 = 32LL * i;
      switch ( *(_DWORD *)((char *)pv + v26) )
      {
        case 1:
          goto LABEL_78;
        case 2:
          v30 = QueueInitialEnhancementsEnabledNotification(
                  (struct AUDIO_ENDPOINT_PROPERTY_CHANGE_APO_NOTIFICATION_DESCRIPTOR *)((char *)pv + v26 + 8),
                  v17);
          if ( v30 >= 0 )
            continue;
          v31 = 603;
          goto LABEL_80;
        case 4:
LABEL_78:
          v30 = QueueInitialVolumeNotification(*(unsigned int *)((char *)pv + v26), (char *)pv + v26 + 8, v17);
          if ( v30 >= 0 )
            continue;
          v31 = 600;
          goto LABEL_80;
        case 5:
          v30 = QueueInitialDeviceOrientationNotification(v17);
          if ( v30 >= 0 )
            continue;
          v31 = 606;
          goto LABEL_80;
        case 6:
          if ( IsCaptureDevice(*(struct IMMDevice **)((char *)pv + v26 + 8)) )
          {
            v30 = QueueInitialMicBoostNotification(
                    (struct AUDIO_MICROPHONE_BOOST_APO_NOTIFICATION_DESCRIPTOR *)((char *)pv + v26 + 8),
                    v17);
            if ( v30 < 0 )
            {
              v31 = 611;
LABEL_80:
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)v31,
                (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
                (const char *)(unsigned int)v30,
                v37);
              continue;
            }
          }
          break;
        case 7:
          v42 = 0;
          EnvironmentStateChangedNotificationHandler = CAPOProcessingHost::GetEnvironmentStateChangedNotificationHandler(
                                                         this,
                                                         a3,
                                                         &v42);
          if ( EnvironmentStateChangedNotificationHandler < 0 )
          {
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
            std::unique_ptr<unsigned int [0]>::~unique_ptr<unsigned int [0]>(&v44);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
            v24 = pv;
            pv = 0;
            if ( !v24 )
              goto LABEL_51;
            goto LABEL_50;
          }
          v43 = 0;
          v27 = wil::com_ptr_t<IPropertyStore,wil::err_returncode_policy>::query_to<IPropertyStore>(
                  (char *)v42 + 40,
                  &v43);
          v28 = v27;
          if ( v27 >= 0 )
            v28 = 0;
          else
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3E,
              (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoenvironmentnotificationshandler.cpp",
              (const char *)(unsigned int)v27,
              v37);
          if ( v28 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x26B,
              (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
              (const char *)(unsigned int)v28,
              v37);
          v29 = QueueInitialEnvironmentStatusNotification(a3, v43, v17);
          if ( v29 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x26C,
              (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
              (const char *)(unsigned int)v29,
              v37);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
          break;
      }
    }
    v32 = AudioDgTelemetryProvider::Provider();
    if ( *(_DWORD *)v32 > 4u )
    {
      p_pv = (LPVOID *)v15;
      LOWORD(v46) = v49;
      v43 = (struct IPropertyStore *)v17;
      v42 = (struct CAPOEnvironmentStateChangedNotificationsHandler *)v39;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<4>>(
        (_DWORD)v32,
        (unsigned int)&byte_1400D1137,
        v33,
        v34,
        (__int64)&v42,
        (__int64)&v43,
        (__int64)&p_pv);
    }
    std::unique_ptr<unsigned int [0]>::~unique_ptr<unsigned int [0]>(&v44);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
    v35 = pv;
    pv = 0;
    if ( !v35 )
      goto LABEL_86;
LABEL_85:
    CoTaskMemFree(v35);
LABEL_86:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x27A,
                           (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14003d3b0  mov     rax, rsp
0x14003d3b3  mov     [rax+8], rbx
0x14003d3b7  mov     [rax+18h], rsi
0x14003d3bb  mov     [rax+10h], rdx
0x14003d3bf  push    rdi
0x14003d3c0  push    r12
0x14003d3c2  push    r13
0x14003d3c4  push    r14
0x14003d3c6  push    r15
0x14003d3c8  sub     rsp, 90h
0x14003d3cf  mov     r12, r8
0x14003d3d2  mov     rsi, rdx
0x14003d3d5  mov     r13, rcx
0x14003d3d8  xor     r14d, r14d
0x14003d3db  mov     [rax-70h], r14
0x14003d3df  lea     rdx, [rax-70h]
0x14003d3e3  lea     rcx, [rax+10h]
0x14003d3e7  call    ??$com_query_to_nothrow@UIAudioProcessingObject@@AEAPEAUIAudioProcessingObjectNotifications@@@wil@@YAJAEAPEAUIAudioProcessingObjectNotifications@@PEAPEAUIAudioProcessingObject@@@Z; wil::com_query_to_nothrow<IAudioProcessingObject,IAudioProcessingObjectNotifications * &>(IAudioProcessingObjectNotifications * &,IAudioProcessingObject * *)
0x14003d3ec  mov     ebx, eax
0x14003d3ee  test    eax, eax
0x14003d3f0  jns     short loc_14003D420
0x14003d3f2  mov     rcx, [rsp+0B8h]; this
0x14003d3fa  mov     r9d, eax; char *
0x14003d3fd  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14003d404  mov     edx, 20Ch; void *
0x14003d409  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d40e  nop
0x14003d40f  lea     rcx, [rsp+0B8h+var_70]
0x14003d414  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003d419  mov     eax, ebx
0x14003d41b  jmp     loc_14003DC3E
0x14003d420  mov     [rsp+0B8h+var_68], r14
0x14003d425  lea     rdi, [r13+90h]
0x14003d42c  mov     rcx, rdi; lpCriticalSection
0x14003d42f  call    cs:__imp_EnterCriticalSection
0x14003d435  lea     rbx, [r13+0B8h]
0x14003d43c  mov     rax, [rsp+0B8h+var_70]
0x14003d441  mov     [rsp+0B8h+var_50], rax
0x14003d446  lea     r8, [rsp+0B8h+var_50]
0x14003d44b  lea     rdx, [rsp+0B8h+var_58]
0x14003d450  mov     rcx, rbx
0x14003d453  call    ?find@?$_Hash@V?$_Umap_traits@PEAUIAudioProcessingObject@@V?$com_ptr_t@VCAPOProcessingHostObject@@Uerr_returncode_policy@wil@@@wil@@V?$_Uhash_compare@PEAUIAudioProcessingObject@@U?$hash@PEAUIAudioProcessingObject@@@std@@U?$equal_to@PEAUIAudioProcessingObject@@@3@@std@@V?$allocator@U?$pair@QEAUIAudioProcessingObject@@V?$com_ptr_t@VCAPOProcessingHostObject@@Uerr_returncode_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIAudioProcessingObject@@V?$com_ptr_t@VCAPOProcessingHostObject@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEBQEAUIAudioProcessingObject@@@Z; std::_Hash<std::_Umap_traits<IAudioProcessingObject *,wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy>,std::_Uhash_compare<IAudioProcessingObject *,std::hash<IAudioProcessingObject *>,std::equal_to<IAudioProcessingObject *>>,std::allocator<std::pair<IAudioProcessingObject * const,wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy>>>,0>>::find(IAudioProcessingObject * const &)
0x14003d458  mov     rdx, [rsp+0B8h+var_58]
0x14003d45d  cmp     rdx, [rbx+8]
0x14003d461  jnz     short loc_14003D4AF
0x14003d463  mov     rcx, [rsp+0B8h]; this
0x14003d46b  mov     ebx, 80070490h
0x14003d470  mov     r9d, ebx; char *
0x14003d473  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14003d47a  mov     edx, 212h; void *
0x14003d47f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d484  test    rdi, rdi
0x14003d487  jz      short loc_14003D493
0x14003d489  mov     rcx, rdi; lpCriticalSection
0x14003d48c  call    cs:__imp_LeaveCriticalSection
0x14003d492  nop
0x14003d493  lea     rcx, [rsp+0B8h+var_68]
0x14003d498  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003d49d  nop
0x14003d49e  lea     rcx, [rsp+0B8h+var_70]
0x14003d4a3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003d4a8  mov     eax, ebx
0x14003d4aa  jmp     loc_14003DC3E
0x14003d4af  add     rdx, 18h
0x14003d4b3  lea     rcx, [rsp+0B8h+var_68]
0x14003d4b8  call    ??4?$com_ptr_t@VCAPOProcessingHostObject@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy>::operator=(wil::com_ptr_t<CAPOProcessingHostObject,wil::err_returncode_policy> const &)
0x14003d4bd  test    rdi, rdi
0x14003d4c0  jz      short loc_14003D4CB
0x14003d4c2  mov     rcx, rdi; lpCriticalSection
0x14003d4c5  call    cs:__imp_LeaveCriticalSection
0x14003d4cb  mov     [rsp+0B8h+pv], r14
0x14003d4d0  mov     [rsp+0B8h+arg_18], r14d
0x14003d4d8  mov     [rsp+0B8h+var_60], r14
0x14003d4dd  mov     rcx, [rsp+0B8h+var_70]
0x14003d4e2  mov     rax, [rcx]
0x14003d4e5  lea     r8, [rsp+0B8h+var_60]
0x14003d4ea  lea     rdx, _GUID_ca2cfbde_a9d6_4eb0_bc95_c4d026b380f0
0x14003d4f1  mov     rax, [rax]
0x14003d4f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d4f9  test    eax, eax
0x14003d4fb  js      loc_14003D5AF
0x14003d501  mov     rcx, [rsp+0B8h+var_60]
0x14003d506  mov     rax, [rcx]
0x14003d509  lea     rdx, [rsp+0B8h+pv]
0x14003d50e  mov     [rsp+0B8h+var_40], rdx
0x14003d513  mov     [rsp+0B8h+var_38], r14
0x14003d51b  mov     [rsp+0B8h+var_30], 1
0x14003d523  lea     r9, [rsp+0B8h+arg_18]
0x14003d52b  lea     r8, [rsp+0B8h+var_38]
0x14003d533  mov     edx, 7
0x14003d538  mov     rax, [rax+28h]
0x14003d53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d541  mov     ebx, eax
0x14003d543  lea     rcx, [rsp+0B8h+var_40]
0x14003d548  call    ??1?$out_param_t@V?$unique_ptr@UAPO_REG_PROPERTIES@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x14003d54d  test    ebx, ebx
0x14003d54f  jns     loc_14003D652
0x14003d555  mov     rcx, [rsp+0B8h]; this
0x14003d55d  mov     r9d, ebx; char *
0x14003d560  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14003d567  mov     edx, 21Bh; void *
0x14003d56c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d571  nop
0x14003d572  lea     rcx, [rsp+0B8h+var_60]
0x14003d577  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003d57c  nop
0x14003d57d  mov     rcx, [rsp+0B8h+pv]; pv
0x14003d582  mov     [rsp+0B8h+pv], r14
0x14003d587  test    rcx, rcx
0x14003d58a  jz      short loc_14003D593
0x14003d58c  call    cs:__imp_CoTaskMemFree
0x14003d592  nop
0x14003d593  lea     rcx, [rsp+0B8h+var_68]
0x14003d598  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003d59d  nop
0x14003d59e  lea     rcx, [rsp+0B8h+var_70]
0x14003d5a3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003d5a8  mov     eax, ebx
0x14003d5aa  jmp     loc_14003DC3E
0x14003d5af  mov     rax, [rsi]
0x14003d5b2  lea     rcx, [rsp+0B8h+pv]
0x14003d5b7  mov     [rsp+0B8h+var_40], rcx
0x14003d5bc  mov     [rsp+0B8h+var_38], r14
0x14003d5c4  mov     [rsp+0B8h+var_30], 1
0x14003d5cc  lea     r8, [rsp+0B8h+arg_18]
0x14003d5d4  lea     rdx, [rsp+0B8h+var_38]
0x14003d5dc  mov     rcx, rsi
0x14003d5df  mov     rax, [rax+18h]
0x14003d5e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d5e8  mov     ebx, eax
0x14003d5ea  lea     rcx, [rsp+0B8h+var_40]
0x14003d5ef  call    ??1?$out_param_t@V?$unique_ptr@UAPO_REG_PROPERTIES@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x14003d5f4  test    ebx, ebx
0x14003d5f6  jns     short loc_14003D652
0x14003d5f8  mov     rcx, [rsp+0B8h]; this
0x14003d600  mov     r9d, ebx; char *
0x14003d603  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14003d60a  mov     edx, 21Fh; void *
0x14003d60f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d614  nop
0x14003d615  lea     rcx, [rsp+0B8h+var_60]
0x14003d61a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003d61f  nop
0x14003d620  mov     rcx, [rsp+0B8h+pv]; pv
0x14003d625  mov     [rsp+0B8h+pv], r14
0x14003d62a  test    rcx, rcx
0x14003d62d  jz      short loc_14003D636
0x14003d62f  call    cs:__imp_CoTaskMemFree
0x14003d635  nop
0x14003d636  lea     rcx, [rsp+0B8h+var_68]
0x14003d63b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003d640  nop
0x14003d641  lea     rcx, [rsp+0B8h+var_70]
0x14003d646  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003d64b  mov     eax, ebx
0x14003d64d  jmp     loc_14003DC3E
0x14003d652  cmp     [rsp+0B8h+pv], r14
0x14003d657  jz      loc_14003DBFD
0x14003d65d  mov     eax, [rsp+0B8h+arg_18]
0x14003d664  test    eax, eax
0x14003d666  jz      loc_14003DBFD
0x14003d66c  mov     ecx, eax
0x14003d66e  mov     eax, 4
0x14003d673  mul     rcx
0x14003d676  mov     rbx, rax
0x14003d679  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14003d680  cmovb   rbx, rax
0x14003d684  mov     rcx, rbx; unsigned __int64
0x14003d687  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14003d68c  mov     rdi, rax
0x14003d68f  mov     r8, rbx; Size
0x14003d692  xor     edx, edx; Val
0x14003d694  mov     rcx, rax; void *
0x14003d697  call    memset_0
0x14003d69c  mov     [rsp+0B8h+var_48], rdi
0x14003d6a1  test    rdi, rdi
0x14003d6a4  jz      loc_14003DB96
0x14003d6aa  mov     r15d, r14d
0x14003d6ad  lea     rsi, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14003d6b4  mov     rbx, [rsp+0B8h+var_68]
0x14003d6b9  cmp     r15d, [rsp+0B8h+arg_18]
0x14003d6c1  jnb     loc_14003D86D
0x14003d6c7  mov     edx, r15d
0x14003d6ca  mov     r14d, r15d
0x14003d6cd  shl     r14, 5
0x14003d6d1  mov     rax, [rsp+0B8h+pv]
0x14003d6d6  mov     ecx, [r14+rax]
0x14003d6da  mov     [rdi+rdx*4], ecx
0x14003d6dd  mov     rdx, [rsp+0B8h+pv]
0x14003d6e2  mov     ecx, [r14+rdx]
0x14003d6e6  sub     ecx, 1
0x14003d6e9  jz      loc_14003D833
0x14003d6ef  sub     ecx, 1
0x14003d6f2  jz      loc_14003D816
0x14003d6f8  sub     ecx, 1
0x14003d6fb  jz      loc_14003D7F9
0x14003d701  sub     ecx, 1
0x14003d704  jz      loc_14003D833
0x14003d70a  sub     ecx, 1
0x14003d70d  jz      loc_14003D7E3
0x14003d713  sub     ecx, 1
0x14003d716  jz      loc_14003D7AB
0x14003d71c  cmp     ecx, 1
0x14003d71f  jz      short loc_14003D78B
0x14003d721  mov     rcx, [rsp+0B8h]; this
0x14003d729  mov     ebx, 80070057h
0x14003d72e  mov     r9d, ebx; char *
0x14003d731  mov     r8, rsi; unsigned int
0x14003d734  mov     edx, 24Ch; void *
0x14003d739  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d73e  nop
0x14003d73f  lea     rcx, [rsp+0B8h+var_48]
0x14003d744  call    ??1?$unique_ptr@$$BY0A@IU?$default_delete@$$BY0A@I@std@@@std@@QEAA@XZ; std::unique_ptr<uint [0]>::~unique_ptr<uint [0]>(void)
0x14003d749  nop
0x14003d74a  lea     rcx, [rsp+0B8h+var_60]
0x14003d74f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003d754  nop
0x14003d755  mov     rcx, [rsp+0B8h+pv]; pv
0x14003d75a  mov     [rsp+0B8h+pv], 0
0x14003d763  test    rcx, rcx
0x14003d766  jz      short loc_14003D76F
0x14003d768  call    cs:__imp_CoTaskMemFree
0x14003d76e  nop
0x14003d76f  lea     rcx, [rsp+0B8h+var_68]
0x14003d774  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003d779  nop
0x14003d77a  lea     rcx, [rsp+0B8h+var_70]
0x14003d77f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003d784  mov     eax, ebx
0x14003d786  jmp     loc_14003DC3E
0x14003d78b  mov     r8, rbx; struct CAPOProcessingHostObject *
0x14003d78e  mov     rdx, r12; unsigned __int16 *
0x14003d791  mov     rcx, r13; this
0x14003d794  call    ?AddEnvironmentStateChangedNotificationClient@CAPOProcessingHost@@AEAAJPEBGPEAVCAPOProcessingHostObject@@@Z; CAPOProcessingHost::AddEnvironmentStateChangedNotificationClient(ushort const *,CAPOProcessingHostObject *)
0x14003d799  test    eax, eax
0x14003d79b  jns     loc_14003D865
0x14003d7a1  mov     edx, 248h
0x14003d7a6  jmp     loc_14003D852
0x14003d7ab  mov     rcx, [r14+rdx+8]; struct IMMDevice *
0x14003d7b0  call    ?IsCaptureDevice@@YA_NPEAUIMMDevice@@@Z; IsCaptureDevice(IMMDevice *)
0x14003d7b5  test    al, al
0x14003d7b7  jz      loc_14003D865
0x14003d7bd  mov     rdx, [rsp+0B8h+pv]
0x14003d7c2  add     rdx, 8
0x14003d7c6  add     rdx, r14; struct AUDIO_MICROPHONE_BOOST_APO_NOTIFICATION_DESCRIPTOR *
0x14003d7c9  mov     r8, rbx; struct CAPOProcessingHostObject *
0x14003d7cc  mov     rcx, r13; this
0x14003d7cf  call    ?AddMicBoostNotificationClient@CAPOProcessingHost@@AEAAJPEAUAUDIO_MICROPHONE_BOOST_APO_NOTIFICATION_DESCRIPTOR@@PEAVCAPOProcessingHostObject@@@Z; CAPOProcessingHost::AddMicBoostNotificationClient(AUDIO_MICROPHONE_BOOST_APO_NOTIFICATION_DESCRIPTOR *,CAPOProcessingHostObject *)
0x14003d7d4  test    eax, eax
0x14003d7d6  jns     loc_14003D865
0x14003d7dc  mov     edx, 243h
0x14003d7e1  jmp     short loc_14003D852
0x14003d7e3  mov     rdx, rbx; struct CAPOProcessingHostObject *
0x14003d7e6  mov     rcx, r13; this
0x14003d7e9  call    ?AddDeviceOrientationNotificationClient@CAPOProcessingHost@@AEAAJPEAVCAPOProcessingHostObject@@@Z; CAPOProcessingHost::AddDeviceOrientationNotificationClient(CAPOProcessingHostObject *)
0x14003d7ee  test    eax, eax
0x14003d7f0  jns     short loc_14003D865
0x14003d7f2  mov     edx, 23Dh
0x14003d7f7  jmp     short loc_14003D852
0x14003d7f9  add     rdx, 8
0x14003d7fd  add     rdx, r14; struct AUDIO_SYSTEMEFFECTS_PROPERTY_CHANGE_APO_NOTIFICATION_DESCRIPTOR *
0x14003d800  mov     r8, rbx; struct CAPOProcessingHostObject *
0x14003d803  mov     rcx, r13; this
0x14003d806  call    ?AddAudioSystemEffectsPropertyStoreNotificationClient@CAPOProcessingHost@@AEAAJPEAUAUDIO_SYSTEMEFFECTS_PROPERTY_CHANGE_APO_NOTIFICATION_DESCRIPTOR@@PEAVCAPOProcessingHostObject@@@Z; CAPOProcessingHost::AddAudioSystemEffectsPropertyStoreNotificationClient(AUDIO_SYSTEMEFFECTS_PROPERTY_CHANGE_APO_NOTIFICATION_DESCRIPTOR *,CAPOProcessingHostObject *)
0x14003d80b  test    eax, eax
0x14003d80d  jns     short loc_14003D865
0x14003d80f  mov     edx, 239h
0x14003d814  jmp     short loc_14003D852
0x14003d816  add     rdx, 8
0x14003d81a  add     rdx, r14; struct AUDIO_ENDPOINT_PROPERTY_CHANGE_APO_NOTIFICATION_DESCRIPTOR *
0x14003d81d  mov     r8, rbx; struct CAPOProcessingHostObject *
0x14003d820  mov     rcx, r13; this
0x14003d823  call    ?AddEndpointPropertyChangeNotificationClient@CAPOProcessingHost@@AEAAJPEAUAUDIO_ENDPOINT_PROPERTY_CHANGE_APO_NOTIFICATION_DESCRIPTOR@@PEAVCAPOProcessingHostObject@@@Z; CAPOProcessingHost::AddEndpointPropertyChangeNotificationClient(AUDIO_ENDPOINT_PROPERTY_CHANGE_APO_NOTIFICATION_DESCRIPTOR *,CAPOProcessingHostObject *)
0x14003d828  test    eax, eax
0x14003d82a  jns     short loc_14003D865
0x14003d82c  mov     edx, 235h
0x14003d831  jmp     short loc_14003D852
0x14003d833  lea     r8, [rdx+8]
0x14003d837  add     r8, r14
0x14003d83a  mov     r9, rbx
0x14003d83d  mov     edx, [r14+rdx]
0x14003d841  mov     rcx, r13
0x14003d844  call    ?AddEndpointVolumeNotificationClient@CAPOProcessingHost@@AEAAJW4APO_NOTIFICATION_TYPE@@PEAUAUDIO_ENDPOINT_VOLUME_APO_NOTIFICATION_DESCRIPTOR@@PEAVCAPOProcessingHostObject@@@Z; CAPOProcessingHost::AddEndpointVolumeNotificationClient(APO_NOTIFICATION_TYPE,AUDIO_ENDPOINT_VOLUME_APO_NOTIFICATION_DESCRIPTOR *,CAPOProcessingHostObject *)
0x14003d849  test    eax, eax
0x14003d84b  jns     short loc_14003D865
0x14003d84d  mov     edx, 231h; void *
0x14003d852  mov     r9d, eax; char *
0x14003d855  mov     r8, rsi; unsigned int
0x14003d858  mov     rcx, [rsp+0B8h]; this
0x14003d860  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14003d865  inc     r15d
0x14003d868  jmp     loc_14003D6B9
0x14003d86d  mov     rcx, rbx; this
0x14003d870  call    ?StartSendingNotifications@CAPOProcessingHostObject@@QEAAJXZ; CAPOProcessingHostObject::StartSendingNotifications(void)
0x14003d875  mov     r14d, eax
0x14003d878  test    eax, eax
0x14003d87a  jns     short loc_14003D8E2
0x14003d87c  mov     rcx, [rsp+0B8h]; this
0x14003d884  mov     r9d, eax; char *
0x14003d887  mov     r8, rsi; unsigned int
  ... truncated ...
```
