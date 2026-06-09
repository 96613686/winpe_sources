# Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl::~DeRequestCoordinatorImpl(void)

- ea: `0x1800c1d24`
- end: `0x1800c1f92`
- name: `??1DeRequestCoordinatorImpl@Coordinator@DisplayEnhancement@Windows@Microsoft@@UEAA@XZ`
- size: `622`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c2830`

## callees

- `0x180005cac`
- `0x180008e3c`
- `0x180009b3c`
- `0x18000f778`
- `0x18000f7b0`
- `0x18000fb14`
- `0x18000fdd8`
- `0x18001918c`
- `0x18001db58`
- `0x18001f958`
- `0x18002f318`
- `0x1800753fc`
- `0x18009775c`
- `0x1800c0454`
- `0x1800c1c50`
- `0x1800c1d24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1d75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1d75`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c1e3a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c1e3a`

## string_xrefs

- `0x1800c1d80`: `Microsoft.Graphics.Display.DisplayEnhancementService.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl::~DeRequestCoordinatorImpl(
        Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl *this)
{
  SmFx::StateMachineEngine::StateMachineEngineImpl *v2; // rcx
  _QWORD *v3; // rsi
  unsigned int v4; // r8d
  int v5; // r9d
  BOOL v6; // ebx
  DWORD LastError; // eax
  std::_Ref_count_base *v8; // rcx
  std::_Ref_count_base *v9; // rcx
  std::_Ref_count_base *v10; // rcx
  std::_Ref_count_base *v11; // rcx
  std::_Ref_count_base *v12; // rcx
  std::_Ref_count_base *v13; // rcx
  std::_Ref_count_base *v14; // rcx
  __int64 v15; // rcx
  _QWORD *v16; // rdx
  _QWORD *v17; // rbx
  _QWORD **v18; // rcx
  _QWORD *v19; // rdx
  _QWORD *v20; // rbx
  _QWORD **v21; // rcx
  _QWORD *v22; // rdx
  _QWORD *v23; // rbx
  std::_Ref_count_base *v24; // rcx
  std::_Ref_count_base *v25; // rcx
  std::_Ref_count_base *v26; // rcx

  *(_QWORD *)this = &Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl::`vftable';
  v2 = (SmFx::StateMachineEngine::StateMachineEngineImpl *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    SmFx::StateMachineEngine::StateMachineEngineImpl::EnqueueEvent(v2, 4u);
    v3 = (_QWORD *)((char *)this + 720);
    if ( !wil::handle_wait(*((wil **)this + 90), (void *)0xFFFFFFFFLL, v4, v5) )
    {
      v6 = *v3 != 0;
      LastError = GetLastError();
      MicrosoftTelemetryAssertTriggeredArgs("Microsoft.Graphics.Display.DisplayEnhancementService.dll", LastError, v6);
    }
  }
  else
  {
    v3 = (_QWORD *)((char *)this + 720);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v3);
  v8 = (std::_Ref_count_base *)*((_QWORD *)this + 89);
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  v9 = (std::_Ref_count_base *)*((_QWORD *)this + 87);
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  v10 = (std::_Ref_count_base *)*((_QWORD *)this + 85);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  v11 = (std::_Ref_count_base *)*((_QWORD *)this + 83);
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  std::_List_node<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessModifier,void *>::_Free_non_head<std::allocator<std::_List_node<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessModifier,void *>>>(
    v11,
    *((_QWORD *)this + 73));
  std::_Deallocate<16>(*((void **)this + 73), (struct std::nothrow_t *)0x20);
  `eh vector destructor iterator'(
    (char *)this + 448,
    0x18u,
    3u,
    (void (*)(void *))Microsoft::Windows::DisplayEnhancement::Foundation::XYZ::~XYZ);
  `eh vector destructor iterator'(
    (char *)this + 344,
    0x18u,
    3u,
    (void (*)(void *))Microsoft::Windows::DisplayEnhancement::Foundation::XYZ::~XYZ);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  v12 = (std::_Ref_count_base *)*((_QWORD *)this + 33);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  v13 = (std::_Ref_count_base *)*((_QWORD *)this + 31);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  v14 = (std::_Ref_count_base *)*((_QWORD *)this + 29);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>((char *)this + 216);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>((char *)this + 208);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>((char *)this + 200);
  std::unique_ptr<Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapter<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl>>::~unique_ptr<Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapter<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl>>((char *)this + 192);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delegate_wnf_subscription_state_to_callback(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delegate_wnf_subscription_state_to_callback(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>((char *)this + 184);
  v15 = *((_QWORD *)this + 20);
  **(_QWORD **)(v15 + 8) = 0;
  v16 = *(_QWORD **)v15;
  if ( *(_QWORD *)v15 )
  {
    do
    {
      v17 = (_QWORD *)*v16;
      std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdateRegistrationInternal>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdateRegistrationInternal>,void *>>>(
        v15,
        v16);
      v16 = v17;
    }
    while ( v17 );
  }
  std::_Deallocate<16>(*((void **)this + 20), (struct std::nothrow_t *)0x20);
  v18 = (_QWORD **)*((_QWORD *)this + 17);
  *v18[1] = 0;
  v19 = *v18;
  if ( *v18 )
  {
    do
    {
      v20 = (_QWORD *)*v19;
      std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::ClientRegistrationInternal>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::ClientRegistrationInternal>,void *>>>();
      v19 = v20;
    }
    while ( v20 );
  }
  std::_Deallocate<16>(*((void **)this + 17), (struct std::nothrow_t *)0x20);
  v21 = (_QWORD **)*((_QWORD *)this + 15);
  *v21[1] = 0;
  v22 = *v21;
  if ( *v21 )
  {
    do
    {
      v23 = (_QWORD *)*v22;
      std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::ClientRegistrationInternal>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::ClientRegistrationInternal>,void *>>>();
      v22 = v23;
    }
    while ( v23 );
  }
  std::_Deallocate<16>(*((void **)this + 15), (struct std::nothrow_t *)0x20);
  v24 = (std::_Ref_count_base *)*((_QWORD *)this + 13);
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
  v25 = (std::_Ref_count_base *)*((_QWORD *)this + 11);
  if ( v25 )
    std::_Ref_count_base::_Decref(v25);
  std::wstring::_Tidy_deallocate((char *)this + 32);
  v26 = (std::_Ref_count_base *)*((_QWORD *)this + 3);
  if ( v26 )
    std::_Ref_count_base::_Decwref(v26);
}

```

## disassembly

```asm
0x1800c1d24  push    rbx
0x1800c1d26  push    rsi
0x1800c1d27  push    rdi
0x1800c1d28  push    r14
0x1800c1d2a  sub     rsp, 28h
0x1800c1d2e  mov     rdi, rcx
0x1800c1d31  lea     rax, ??_7DeRequestCoordinatorImpl@Coordinator@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl::`vftable'
0x1800c1d38  mov     [rcx], rax
0x1800c1d3b  mov     rcx, [rcx+8]; this
0x1800c1d3f  test    rcx, rcx
0x1800c1d42  jnz     short loc_1800C1D4D
0x1800c1d44  lea     rsi, [rdi+2D0h]
0x1800c1d4b  jmp     short loc_1800C1D8C
0x1800c1d4d  mov     edx, 4; unsigned __int16
0x1800c1d52  call    ?EnqueueEvent@StateMachineEngineImpl@StateMachineEngine@SmFx@@QEAAXG@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::EnqueueEvent(ushort)
0x1800c1d57  lea     rsi, [rdi+2D0h]
0x1800c1d5e  or      edx, 0FFFFFFFFh; void *
0x1800c1d61  mov     rcx, [rsi]; this
0x1800c1d64  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x1800c1d69  test    al, al
0x1800c1d6b  jnz     short loc_1800C1D8C
0x1800c1d6d  xor     ebx, ebx
0x1800c1d6f  cmp     [rsi], rbx
0x1800c1d72  setnz   bl
0x1800c1d75  call    cs:__imp_GetLastError
0x1800c1d7b  mov     edx, eax
0x1800c1d7d  mov     r8d, ebx
0x1800c1d80  lea     rcx, aMicrosoftGraph_0; "Microsoft.Graphics.Display.DisplayEnhan"...
0x1800c1d87  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800c1d8c  mov     rcx, rsi
0x1800c1d8f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c1d94  mov     rcx, [rdi+2C8h]; this
0x1800c1d9b  test    rcx, rcx
0x1800c1d9e  jz      short loc_1800C1DA5
0x1800c1da0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c1da5  mov     rcx, [rdi+2B8h]; this
0x1800c1dac  test    rcx, rcx
0x1800c1daf  jz      short loc_1800C1DB6
0x1800c1db1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c1db6  mov     rcx, [rdi+2A8h]; this
0x1800c1dbd  test    rcx, rcx
0x1800c1dc0  jz      short loc_1800C1DC7
0x1800c1dc2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c1dc7  mov     rcx, [rdi+298h]; this
0x1800c1dce  test    rcx, rcx
0x1800c1dd1  jz      short loc_1800C1DD8
0x1800c1dd3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c1dd8  mov     rdx, [rdi+248h]
0x1800c1ddf  call    ??$_Free_non_head@V?$allocator@U?$_List_node@UBrightnessModifier@Foundation@DisplayEnhancement@Windows@Microsoft@@PEAX@std@@@std@@@?$_List_node@UBrightnessModifier@Foundation@DisplayEnhancement@Windows@Microsoft@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@UBrightnessModifier@Foundation@DisplayEnhancement@Windows@Microsoft@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessModifier,void *>::_Free_non_head<std::allocator<std::_List_node<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessModifier,void *>>>(std::allocator<std::_List_node<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessModifier,void *>> &,std::_List_node<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessModifier,void *> *)
0x1800c1de4  mov     r14d, 20h ; ' '
0x1800c1dea  mov     edx, r14d
0x1800c1ded  mov     rcx, [rdi+248h]
0x1800c1df4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c1df9  nop
0x1800c1dfa  lea     rcx, [rdi+1C0h]; void *
0x1800c1e01  lea     r9, ??1XYZ@Foundation@DisplayEnhancement@Windows@Microsoft@@UEAA@XZ; void (*)(void *)
0x1800c1e08  lea     esi, [r14-1Dh]
0x1800c1e0c  mov     r8d, esi; unsigned __int64
0x1800c1e0f  lea     ebx, [rsi+15h]
0x1800c1e12  mov     edx, ebx; unsigned __int64
0x1800c1e14  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800c1e19  nop
0x1800c1e1a  lea     rcx, [rdi+158h]; void *
0x1800c1e21  lea     r9, ??1XYZ@Foundation@DisplayEnhancement@Windows@Microsoft@@UEAA@XZ; void (*)(void *)
0x1800c1e28  mov     r8d, esi; unsigned __int64
0x1800c1e2b  mov     edx, ebx; unsigned __int64
0x1800c1e2d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800c1e32  nop
0x1800c1e33  lea     rcx, [rdi+110h]; lpCriticalSection
0x1800c1e3a  call    cs:__imp_DeleteCriticalSection
0x1800c1e40  mov     rcx, [rdi+108h]; this
0x1800c1e47  test    rcx, rcx
0x1800c1e4a  jz      short loc_1800C1E51
0x1800c1e4c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c1e51  mov     rcx, [rdi+0F8h]; this
0x1800c1e58  test    rcx, rcx
0x1800c1e5b  jz      short loc_1800C1E62
0x1800c1e5d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c1e62  mov     rcx, [rdi+0E8h]; this
0x1800c1e69  test    rcx, rcx
0x1800c1e6c  jz      short loc_1800C1E73
0x1800c1e6e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c1e73  lea     rcx, [rdi+0D8h]
0x1800c1e7a  call    ??1?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(void)
0x1800c1e7f  lea     rcx, [rdi+0D0h]
0x1800c1e86  call    ??1?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(void)
0x1800c1e8b  lea     rcx, [rdi+0C8h]
0x1800c1e92  call    ??1?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(void)
0x1800c1e97  lea     rcx, [rdi+0C0h]
0x1800c1e9e  call    ??1?$unique_ptr@V?$DeviceWatcherAdapter@VMonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@@DeviceWatcher@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@V?$DeviceWatcherAdapter@VMonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@@DeviceWatcher@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapter<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl>>::~unique_ptr<Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapter<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl>>(void)
0x1800c1ea3  lea     rcx, [rdi+0B8h]
0x1800c1eaa  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delegate_wnf_subscription_state_to_callback@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delegate_wnf_subscription_state_to_callback(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delegate_wnf_subscription_state_to_callback(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800c1eaf  mov     rcx, [rdi+0A0h]
0x1800c1eb6  mov     rax, [rcx+8]
0x1800c1eba  mov     qword ptr [rax], 0
0x1800c1ec1  mov     rdx, [rcx]
0x1800c1ec4  test    rdx, rdx
0x1800c1ec7  jz      short loc_1800C1ED9
0x1800c1ec9  mov     rbx, [rdx]
0x1800c1ecc  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$shared_ptr@UBrightnessUpdateRegistrationInternal@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@UBrightnessUpdateRegistrationInternal@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@UBrightnessUpdateRegistrationInternal@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdateRegistrationInternal>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdateRegistrationInternal>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdateRegistrationInternal>,void *>> &,std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdateRegistrationInternal>,void *> *)
0x1800c1ed1  mov     rdx, rbx
0x1800c1ed4  test    rbx, rbx
0x1800c1ed7  jnz     short loc_1800C1EC9
0x1800c1ed9  mov     rdx, r14
0x1800c1edc  mov     rcx, [rdi+0A0h]
0x1800c1ee3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c1ee8  mov     rcx, [rdi+88h]
0x1800c1eef  mov     rax, [rcx+8]
0x1800c1ef3  mov     qword ptr [rax], 0
0x1800c1efa  mov     rdx, [rcx]
0x1800c1efd  test    rdx, rdx
0x1800c1f00  jz      short loc_1800C1F12
0x1800c1f02  mov     rbx, [rdx]
0x1800c1f05  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$shared_ptr@UClientRegistrationInternal@Coordinator@DisplayEnhancement@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@UClientRegistrationInternal@Coordinator@DisplayEnhancement@Windows@Microsoft@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@UClientRegistrationInternal@Coordinator@DisplayEnhancement@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::ClientRegistrationInternal>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::ClientRegistrationInternal>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::ClientRegistrationInternal>,void *>> &,std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::ClientRegistrationInternal>,void *> *)
0x1800c1f0a  mov     rdx, rbx
0x1800c1f0d  test    rbx, rbx
0x1800c1f10  jnz     short loc_1800C1F02
0x1800c1f12  mov     rdx, r14
0x1800c1f15  mov     rcx, [rdi+88h]
0x1800c1f1c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c1f21  mov     rcx, [rdi+78h]
0x1800c1f25  mov     rax, [rcx+8]
0x1800c1f29  mov     qword ptr [rax], 0
0x1800c1f30  mov     rdx, [rcx]
0x1800c1f33  test    rdx, rdx
0x1800c1f36  jz      short loc_1800C1F48
0x1800c1f38  mov     rbx, [rdx]
0x1800c1f3b  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$shared_ptr@UClientRegistrationInternal@Coordinator@DisplayEnhancement@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@UClientRegistrationInternal@Coordinator@DisplayEnhancement@Windows@Microsoft@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@UClientRegistrationInternal@Coordinator@DisplayEnhancement@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::ClientRegistrationInternal>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::ClientRegistrationInternal>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::ClientRegistrationInternal>,void *>> &,std::_List_node<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::ClientRegistrationInternal>,void *> *)
0x1800c1f40  mov     rdx, rbx
0x1800c1f43  test    rbx, rbx
0x1800c1f46  jnz     short loc_1800C1F38
0x1800c1f48  mov     rdx, r14
0x1800c1f4b  mov     rcx, [rdi+78h]
0x1800c1f4f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c1f54  mov     rcx, [rdi+68h]; this
0x1800c1f58  test    rcx, rcx
0x1800c1f5b  jz      short loc_1800C1F62
0x1800c1f5d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c1f62  mov     rcx, [rdi+58h]; this
0x1800c1f66  test    rcx, rcx
0x1800c1f69  jz      short loc_1800C1F70
0x1800c1f6b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c1f70  lea     rcx, [rdi+20h]
0x1800c1f74  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c1f79  mov     rcx, [rdi+18h]; this
0x1800c1f7d  test    rcx, rcx
0x1800c1f80  jz      short loc_1800C1F88
0x1800c1f82  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800c1f87  nop
0x1800c1f88  add     rsp, 28h
0x1800c1f8c  pop     r14
0x1800c1f8e  pop     rdi
0x1800c1f8f  pop     rsi
0x1800c1f90  pop     rbx
0x1800c1f91  retn
```
