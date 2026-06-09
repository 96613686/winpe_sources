# Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl::PostModifierChangedEvent(void)

- ea: `0x18005a1d4`
- end: `0x18005a5e9`
- name: `?PostModifierChangedEvent@AutobrightnessConfigurationNitsImpl@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@IEAA?AW4Event@?$AutobrightnessConfigurationStateMachine@VAutobrightnessConfigurationNitsImpl@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@23456@XZ`
- size: `1045`
- prototype: `__int64 __fastcall(Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl *this)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005a5f0`

## callees

- `0x180005860`
- `0x180008ae8`
- `0x180008c50`
- `0x180008e3c`
- `0x180009a84`
- `0x180009aa4`
- `0x18000a0c4`
- `0x18000f778`
- `0x18000fa98`
- `0x180011fe8`
- `0x1800121d0`
- `0x18001df1c`
- `0x18001f19c`
- `0x18001f644`
- `0x180028350`
- `0x18002f318`
- `0x1800348a0`
- `0x180034958`
- `0x180037dd0`
- `0x180050c74`
- `0x180050ff4`
- `0x180051858`
- `0x180057ef4`
- `0x180058564`
- `0x180058824`
- `0x18005a1d4`
- `0x18005aed0`
- `0x18005afb8`
- `0x1800753fc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005a4de`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005a4de`

## string_xrefs

- `0x18005a2c5`: `Settings update function was nullptr`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl::PostModifierChangedEvent(
        Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl *this)
{
  __int64 v2; // rax
  __int64 v3; // rax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // edx
  int v8; // r8d
  int v9; // edx
  int v10; // r8d
  _QWORD **v11; // rdi
  _QWORD *i; // rbx
  __int64 v13; // rsi
  _QWORD *v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  _QWORD *v17; // r9
  _QWORD *v18; // rdi
  _QWORD *j; // rbx
  __int64 v20; // rsi
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  _QWORD **v24; // rcx
  _QWORD *v25; // rbx
  _QWORD *v26; // rdi
  std::_Ref_count_base *v27; // rcx
  int v29; // [rsp+40h] [rbp-C0h]
  _BYTE v30[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v31; // [rsp+68h] [rbp-98h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v33; // [rsp+80h] [rbp-80h]
  std::_Ref_count_base *v34[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 *v35; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-58h]
  _BYTE v37[56]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v38; // [rsp+E8h] [rbp-18h]
  _BYTE v39[56]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v40; // [rsp+148h] [rbp+48h]
  _BYTE v41[96]; // [rsp+150h] [rbp+50h] BYREF

  v2 = Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCausation::CreateAutobrightnessCausation(&v32);
  v38 = 0;
  Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged::ModifierChanged(
    v41,
    v37,
    v2);
  v40 = 0;
  while ( *((_QWORD *)this + 18) )
  {
    std::function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>::~function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>(v39);
    Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(
      (Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard *)v30,
      (Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl *)((char *)this + 80));
    v3 = *((_QWORD *)this + 17);
    v4 = *(_DWORD *)(*(_QWORD *)v3 + 16LL);
    std::function<void (void)>::operator=(v39, *(_QWORD *)v3 + 24LL);
    v5 = **((_QWORD **)this + 17);
    v6 = *(_QWORD *)v5;
    --*((_QWORD *)this + 18);
    **(_QWORD **)(v5 + 8) = v6;
    *(_QWORD *)(v6 + 8) = *(_QWORD *)(v5 + 8);
    std::_List_node<std::pair<enum Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl::BrightnessInputType,std::function<void (void)>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<enum Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl::BrightnessInputType,std::function<void (void)>>,void *>>>(
      v6,
      (char *)v5);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v30);
    if ( v40 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || (LOBYTE(v7) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
      {
        LOBYTE(v7) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (LOBYTE(v8) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
      {
        LOBYTE(v8) = 0;
      }
      if ( (_BYTE)v7 || (_BYTE)v8 )
        WPP_RECORDER_AND_TRACE_SF_sdq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v7,
          v8,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          5,
          2,
          22,
          &WPP_37151b776b4f3d967dad118b1e9941cf_Traceguids,
          v29,
          v4,
          (char)this);
      std::_Func_class<void,std::unique_ptr<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessManager> &>::operator()(v39);
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredArgs("Settings update function was nullptr", v4, v4);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || (LOBYTE(v9) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
      {
        LOBYTE(v9) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (LOBYTE(v10) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
      {
        LOBYTE(v10) = 0;
      }
      if ( (_BYTE)v9 || (_BYTE)v10 )
        WPP_RECORDER_AND_TRACE_SF_sdq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v9,
          v10,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          5,
          2,
          23,
          &WPP_37151b776b4f3d967dad118b1e9941cf_Traceguids,
          v29,
          v4,
          (char)this);
    }
  }
  Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl::UpdateBrightnessModifierFunctor(this);
  Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(
    (Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard *)v30,
    (Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl *)((char *)this + 96));
  Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged::operator=(
    v41,
    (char *)this + 152);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v30);
  v31 = 0;
  std::list<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Occlusion::OcclusionAdapterImpl::OcclusionDataUpdateRegistrationInternal>>::_Alloc_sentinel_and_proxy(&v31);
  Microsoft::Windows::DisplayEnhancement::Foundation::SharedSRWLockguard::SharedSRWLockguard(
    (Microsoft::Windows::DisplayEnhancement::Foundation::SharedSRWLockguard *)v30,
    (Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl *)((char *)this + 88));
  v11 = (_QWORD **)*((_QWORD *)this + 15);
  for ( i = *v11; i != v11; i = (_QWORD *)*i )
  {
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>(
      &v32,
      i + 2);
    *(_OWORD *)v34 = 0;
    std::_Ptr_base<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged>>::_Construct_from_weak<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged>>(
      (__int64)v34,
      v32 + 16);
    if ( v34[0] )
    {
      if ( *((_QWORD *)&v31 + 1) == 0x7FFFFFFFFFFFFFFLL )
        std::_Xlength_error("list too long");
      v35 = &v31;
      v36 = 0;
      v13 = v31;
      v14 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
      std::_Default_allocator_traits<std::allocator<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::OverrideMonitorContext>>>::construct<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::OverrideMonitorContext>,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::OverrideMonitorContext> &>(
        v15,
        v14 + 2,
        v34);
      ++*((_QWORD *)&v31 + 1);
      v16 = *(_QWORD **)(v13 + 8);
      *v17 = v13;
      v17[1] = v16;
      v36 = 0;
      *(_QWORD *)(v13 + 8) = v17;
      *v16 = v17;
      std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdate>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdate>>,void *>>>(&v35);
    }
    if ( v34[1] )
      std::_Ref_count_base::_Decref(v34[1]);
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v30);
  v18 = (_QWORD *)v31;
  for ( j = *(_QWORD **)v31; j != v18; j = (_QWORD *)*j )
  {
    v20 = j[2];
    v21 = Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged::ModifierChanged(
            (Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged *)v37,
            (const struct Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged *)v41);
    Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged>::TryUpdateStatus(
      v20,
      v21);
  }
  Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(
    (Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard *)v30,
    (Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl *)((char *)this + 96));
  v22 = Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCausation::CreateAutobrightnessCausation(&v32);
  Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCausation::operator=((char *)this + 248, v22);
  std::_List_node<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessModifier,void *>::_Free_non_head<std::allocator<std::_List_node<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessModifier,void *>>>(
    v23,
    v33);
  std::_Deallocate<16>(v33, (struct std::nothrow_t *)0x20);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v30);
  v24 = (_QWORD **)v31;
  **(_QWORD **)(v31 + 8) = 0;
  v25 = *v24;
  if ( *v24 )
  {
    do
    {
      v26 = (_QWORD *)*v25;
      v27 = (std::_Ref_count_base *)v25[3];
      if ( v27 )
        std::_Ref_count_base::_Decref(v27);
      std::_Deallocate<16>(v25, (struct std::nothrow_t *)0x20);
      v25 = v26;
    }
    while ( v26 );
  }
  std::_Deallocate<16>((void *)v31, (struct std::nothrow_t *)0x20);
  std::function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>::~function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>(v39);
  Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged::~ModifierChanged((Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged *)v41);
  return 6;
}

```

## disassembly

```asm
0x18005a1d4  push    rbp
0x18005a1d6  push    rbx
0x18005a1d7  push    rsi
0x18005a1d8  push    rdi
0x18005a1d9  push    r12
0x18005a1db  push    r13
0x18005a1dd  push    r14
0x18005a1df  push    r15
0x18005a1e1  lea     rbp, [rsp-0C8h]
0x18005a1e9  sub     rsp, 1C8h
0x18005a1f0  mov     rax, cs:__security_cookie
0x18005a1f7  xor     rax, rsp
0x18005a1fa  mov     [rbp+100h+var_50], rax
0x18005a201  mov     r14, rcx
0x18005a204  lea     rcx, [rsp+200h+var_188]
0x18005a209  call    ?CreateAutobrightnessCausation@BrightnessCausation@Foundation@DisplayEnhancement@Windows@Microsoft@@SA?AU12345@XZ; Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCausation::CreateAutobrightnessCausation(void)
0x18005a20e  xor     r12d, r12d
0x18005a211  mov     [rbp+100h+var_118], r12
0x18005a215  mov     r8, rax
0x18005a218  lea     rdx, [rbp+100h+var_150]
0x18005a21c  lea     rcx, [rbp+100h+var_B0]
0x18005a220  call    ??0ModifierChanged@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@QEAA@V?$function@$$A6AII@Z@std@@UBrightnessCausation@Foundation@345@_NJ@Z; Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged::ModifierChanged(std::function<uint (uint)>,Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCausation,bool,long)
0x18005a225  nop
0x18005a226  mov     [rbp+100h+var_B8], r12
0x18005a22a  lea     r15, WPP_GLOBAL_Control
0x18005a231  lea     edi, [r12+2]
0x18005a236  lea     rsi, WPP_RECORDER_INITIALIZED
0x18005a23d  lea     r13, WPP_37151b776b4f3d967dad118b1e9941cf_Traceguids
0x18005a244  cmp     [r14+90h], r12
0x18005a24b  jz      loc_18005A3B6
0x18005a251  lea     rcx, [rbp+100h+var_F0]
0x18005a255  call    ??1?$function@$$A6A?AVDeManagementULongSettingType@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@XZ@std@@QEAA@XZ; std::function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>::~function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>(void)
0x18005a25a  lea     rdx, [r14+50h]; struct wil::srwlock *
0x18005a25e  lea     rcx, [rsp+200h+var_1A0]; this
0x18005a263  call    ??0ExclusiveSRWLockguard@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAA@AEAVsrwlock@wil@@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(wil::srwlock &)
0x18005a268  nop
0x18005a269  mov     rax, [r14+88h]
0x18005a270  mov     rdx, [rax]
0x18005a273  mov     ebx, [rdx+10h]
0x18005a276  add     rdx, 18h
0x18005a27a  lea     rcx, [rbp+100h+var_F0]
0x18005a27e  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> const &)
0x18005a283  mov     rax, [r14+88h]
0x18005a28a  mov     rdx, [rax]
0x18005a28d  mov     rcx, [rdx]
0x18005a290  dec     qword ptr [r14+90h]
0x18005a297  mov     rax, [rdx+8]
0x18005a29b  mov     [rax], rcx
0x18005a29e  mov     rax, [rdx+8]
0x18005a2a2  mov     [rcx+8], rax
0x18005a2a6  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@W4BrightnessInputType@AutobrightnessConfigurationNitsImpl@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@V?$function@$$A6AXXZ@std@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@W4BrightnessInputType@AutobrightnessConfigurationNitsImpl@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@V?$function@$$A6AXXZ@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@W4BrightnessInputType@AutobrightnessConfigurationNitsImpl@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@V?$function@$$A6AXXZ@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl::BrightnessInputType,std::function<void (void)>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl::BrightnessInputType,std::function<void (void)>>,void *>>>(std::allocator<std::_List_node<std::pair<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl::BrightnessInputType,std::function<void (void)>>,void *>> &,std::_List_node<std::pair<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl::BrightnessInputType,std::function<void (void)>>,void *> *)
0x18005a2ab  nop
0x18005a2ac  lea     rcx, [rsp+200h+var_1A0]
0x18005a2b1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005a2b6  cmp     [rbp+100h+var_B8], r12
0x18005a2ba  jnz     loc_18005A341
0x18005a2c0  mov     r8d, ebx
0x18005a2c3  mov     edx, ebx
0x18005a2c5  lea     rcx, aSettingsUpdate; "Settings update function was nullptr"
0x18005a2cc  call    MicrosoftTelemetryAssertTriggeredArgs
0x18005a2d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a2d8  cmp     rcx, r15
0x18005a2db  jz      short loc_18005A2EB
0x18005a2dd  test    [rcx+1Ch], dil
0x18005a2e1  jz      short loc_18005A2EB
0x18005a2e3  cmp     byte ptr [rcx+19h], 5
0x18005a2e7  mov     dl, 1
0x18005a2e9  jnb     short loc_18005A2EE
0x18005a2eb  mov     dl, r12b; int
0x18005a2ee  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18005a2f5  jz      short loc_18005A301
0x18005a2f7  cmp     [rcx+30h], r12w
0x18005a2fc  mov     r8b, 1
0x18005a2ff  jnz     short loc_18005A304
0x18005a301  mov     r8b, r12b; int
0x18005a304  test    dl, dl
0x18005a306  jnz     short loc_18005A311
0x18005a308  test    r8b, r8b
0x18005a30b  jz      loc_18005A244
0x18005a311  mov     qword ptr [rsp+200h+var_1B0], r14; char
0x18005a316  mov     dword ptr [rsp+200h+var_1B8], ebx; char
0x18005a31a  mov     [rsp+200h+MessageGuid], r13; MessageGuid
0x18005a31f  mov     [rsp+200h+var_1D0], 17h; __int16
0x18005a326  mov     [rsp+200h+var_1D8], edi; int
0x18005a32a  mov     [rsp+200h+var_1E0], 5; char
0x18005a32f  mov     r9, [rcx+28h]; int
0x18005a333  mov     rcx, [rcx+10h]; int
0x18005a337  call    WPP_RECORDER_AND_TRACE_SF_sdq
0x18005a33c  jmp     loc_18005A244
0x18005a341  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a348  cmp     rcx, r15
0x18005a34b  jz      short loc_18005A35B
0x18005a34d  test    [rcx+1Ch], dil
0x18005a351  jz      short loc_18005A35B
0x18005a353  cmp     byte ptr [rcx+19h], 5
0x18005a357  mov     dl, 1
0x18005a359  jnb     short loc_18005A35E
0x18005a35b  mov     dl, r12b; int
0x18005a35e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18005a365  jz      short loc_18005A371
0x18005a367  cmp     [rcx+30h], r12w
0x18005a36c  mov     r8b, 1
0x18005a36f  jnz     short loc_18005A374
0x18005a371  mov     r8b, r12b; int
0x18005a374  test    dl, dl
0x18005a376  jnz     short loc_18005A37D
0x18005a378  test    r8b, r8b
0x18005a37b  jz      short loc_18005A3A8
0x18005a37d  mov     qword ptr [rsp+200h+var_1B0], r14; char
0x18005a382  mov     dword ptr [rsp+200h+var_1B8], ebx; char
0x18005a386  mov     [rsp+200h+MessageGuid], r13; MessageGuid
0x18005a38b  mov     [rsp+200h+var_1D0], 16h; __int16
0x18005a392  mov     [rsp+200h+var_1D8], edi; int
0x18005a396  mov     [rsp+200h+var_1E0], 5; char
0x18005a39b  mov     r9, [rcx+28h]; int
0x18005a39f  mov     rcx, [rcx+10h]; int
0x18005a3a3  call    WPP_RECORDER_AND_TRACE_SF_sdq
0x18005a3a8  lea     rcx, [rbp+100h+var_F0]
0x18005a3ac  call    ??R?$_Func_class@XAEAV?$unique_ptr@VBrightnessManager@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@VBrightnessManager@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@@std@@QEBAXAEAV?$unique_ptr@VBrightnessManager@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@VBrightnessManager@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@std@@@1@@Z; std::_Func_class<void,std::unique_ptr<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessManager> &>::operator()(std::unique_ptr<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessManager> &)
0x18005a3b1  jmp     loc_18005A244
0x18005a3b6  mov     rcx, r14; this
0x18005a3b9  call    ?UpdateBrightnessModifierFunctor@AutobrightnessConfigurationNitsImpl@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@AEAAXXZ; Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::AutobrightnessConfigurationNitsImpl::UpdateBrightnessModifierFunctor(void)
0x18005a3be  lea     rdx, [r14+60h]; struct wil::srwlock *
0x18005a3c2  lea     rcx, [rsp+200h+var_1A0]; this
0x18005a3c7  call    ??0ExclusiveSRWLockguard@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAA@AEAVsrwlock@wil@@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(wil::srwlock &)
0x18005a3cc  nop
0x18005a3cd  lea     rdx, [r14+98h]
0x18005a3d4  lea     rcx, [rbp+100h+var_B0]
0x18005a3d8  call    ??4ModifierChanged@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@QEAAAEAU012345@AEBU012345@@Z; Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged::operator=(Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged const &)
0x18005a3dd  nop
0x18005a3de  lea     rcx, [rsp+200h+var_1A0]
0x18005a3e3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005a3e8  xorps   xmm0, xmm0
0x18005a3eb  movdqu  [rsp+200h+var_198], xmm0
0x18005a3f1  lea     rcx, [rsp+200h+var_198]
0x18005a3f6  call    ?_Alloc_sentinel_and_proxy@?$list@V?$shared_ptr@UOcclusionDataUpdateRegistrationInternal@OcclusionAdapterImpl@Occlusion@DisplayEnhancement@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@UOcclusionDataUpdateRegistrationInternal@OcclusionAdapterImpl@Occlusion@DisplayEnhancement@Windows@Microsoft@@@std@@@2@@std@@AEAAXXZ; std::list<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Occlusion::OcclusionAdapterImpl::OcclusionDataUpdateRegistrationInternal>>::_Alloc_sentinel_and_proxy(void)
0x18005a3fb  nop
0x18005a3fc  lea     rdx, [r14+58h]; struct wil::srwlock *
0x18005a400  lea     rcx, [rsp+200h+var_1A0]; this
0x18005a405  call    ??0SharedSRWLockguard@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAA@AEAVsrwlock@wil@@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::SharedSRWLockguard::SharedSRWLockguard(wil::srwlock &)
0x18005a40a  nop
0x18005a40b  mov     rdi, [r14+78h]
0x18005a40f  mov     rbx, [rdi]
0x18005a412  mov     r13d, 20h ; ' '
0x18005a418  cmp     rbx, rdi
0x18005a41b  jz      loc_18005A4E5
0x18005a421  lea     rdx, [rbx+10h]
0x18005a425  lea     rcx, [rsp+200h+var_188]
0x18005a42a  call    ??0?$shared_ptr@V?$OEMSetting@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>> const &)
0x18005a42f  nop
0x18005a430  xorps   xmm0, xmm0
0x18005a433  movdqu  xmmword ptr [rbp+100h+var_170], xmm0
0x18005a438  mov     rdx, [rsp+200h+var_188]
0x18005a43d  add     rdx, 10h
0x18005a441  lea     rcx, [rbp+100h+var_170]
0x18005a445  call    ??$_Construct_from_weak@V?$TokenWithStatusServer@UModifierChanged@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@?$_Ptr_base@V?$TokenWithStatusServer@UModifierChanged@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@IEAA_NAEBV?$weak_ptr@V?$TokenWithStatusServer@UModifierChanged@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@1@@Z; std::_Ptr_base<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged>>::_Construct_from_weak<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged>>(std::weak_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged>> const &)
0x18005a44a  nop
0x18005a44b  cmp     [rbp+100h+var_170], r12
0x18005a44f  jz      short loc_18005A4B2
0x18005a451  mov     rax, 7FFFFFFFFFFFFFFh
0x18005a45b  cmp     qword ptr [rsp+200h+var_198+8], rax
0x18005a460  jz      short loc_18005A4D7
0x18005a462  lea     rax, [rsp+200h+var_198]
0x18005a467  mov     [rbp+100h+var_160], rax
0x18005a46b  mov     [rbp+100h+var_158], r12
0x18005a46f  mov     rsi, qword ptr [rsp+200h+var_198]
0x18005a474  mov     rcx, r13
0x18005a477  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18005a47c  mov     r9, rax
0x18005a47f  lea     rdx, [rax+10h]
0x18005a483  lea     r8, [rbp+100h+var_170]
0x18005a487  call    ??$construct@V?$shared_ptr@UOverrideMonitorContext@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@AEAV12@@?$_Default_allocator_traits@V?$allocator@V?$shared_ptr@UOverrideMonitorContext@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@@std@@SAXAEAV?$allocator@V?$shared_ptr@UOverrideMonitorContext@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@@1@QEAV?$shared_ptr@UOverrideMonitorContext@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@@1@AEAV31@@Z; std::_Default_allocator_traits<std::allocator<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::OverrideMonitorContext>>>::construct<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::OverrideMonitorContext>,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::OverrideMonitorContext> &>(std::allocator<std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::OverrideMonitorContext>> &,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::OverrideMonitorContext> * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::OverrideMonitorContext> &)
0x18005a48c  nop
0x18005a48d  inc     qword ptr [rsp+200h+var_198+8]
0x18005a492  mov     rcx, [rsi+8]
0x18005a496  mov     [r9], rsi
0x18005a499  mov     [r9+8], rcx
0x18005a49d  mov     [rbp+100h+var_158], r12
0x18005a4a1  mov     [rsi+8], r9
0x18005a4a5  mov     [rcx], r9
0x18005a4a8  lea     rcx, [rbp+100h+var_160]
0x18005a4ac  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$shared_ptr@V?$TokenWithStatusServer@UBrightnessUpdate@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdate>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdate>>,void *>>>(void)
0x18005a4b1  nop
0x18005a4b2  mov     rcx, [rbp+100h+var_170+8]; this
0x18005a4b6  test    rcx, rcx
0x18005a4b9  jz      short loc_18005A4C1
0x18005a4bb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005a4c0  nop
0x18005a4c1  mov     rcx, [rbp+100h+var_180]; this
0x18005a4c5  test    rcx, rcx
0x18005a4c8  jz      short loc_18005A4CF
0x18005a4ca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005a4cf  mov     rbx, [rbx]
0x18005a4d2  jmp     loc_18005A418
0x18005a4d7  lea     rcx, aListTooLong; "list too long"
0x18005a4de  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18005a4e5  lea     rcx, [rsp+200h+var_1A0]
0x18005a4ea  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005a4ef  mov     rdi, qword ptr [rsp+200h+var_198]
0x18005a4f4  mov     rbx, [rdi]
0x18005a4f7  cmp     rbx, rdi
0x18005a4fa  jz      short loc_18005A51D
0x18005a4fc  mov     rsi, [rbx+10h]
0x18005a500  lea     rdx, [rbp+100h+var_B0]; struct Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged *
0x18005a504  lea     rcx, [rbp+100h+var_150]; this
0x18005a508  call    ??0ModifierChanged@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@QEAA@AEBU012345@@Z; Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged::ModifierChanged(Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged const &)
0x18005a50d  mov     rdx, rax
0x18005a510  mov     rcx, rsi
0x18005a513  call    ?TryUpdateStatus@?$TokenWithStatusServer@UModifierChanged@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@QEAA_NUModifierChanged@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@4@@Z; Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged>::TryUpdateStatus(Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged)
0x18005a518  mov     rbx, [rbx]
0x18005a51b  jmp     short loc_18005A4F7
0x18005a51d  lea     rdx, [r14+60h]; struct wil::srwlock *
0x18005a521  lea     rcx, [rsp+200h+var_1A0]; this
0x18005a526  call    ??0ExclusiveSRWLockguard@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAA@AEAVsrwlock@wil@@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(wil::srwlock &)
0x18005a52b  nop
0x18005a52c  lea     rcx, [rsp+200h+var_188]
0x18005a531  call    ?CreateAutobrightnessCausation@BrightnessCausation@Foundation@DisplayEnhancement@Windows@Microsoft@@SA?AU12345@XZ; Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCausation::CreateAutobrightnessCausation(void)
0x18005a536  nop
0x18005a537  lea     rcx, [r14+0F8h]
0x18005a53e  mov     rdx, rax
0x18005a541  call    ??4BrightnessCausation@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAAXAEBU01234@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCausation::operator=(Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCausation const &)
0x18005a546  nop
0x18005a547  mov     rdx, [rbp+100h+var_180]
0x18005a54b  call    ??$_Free_non_head@V?$allocator@U?$_List_node@UBrightnessModifier@Foundation@DisplayEnhancement@Windows@Microsoft@@PEAX@std@@@std@@@?$_List_node@UBrightnessModifier@Foundation@DisplayEnhancement@Windows@Microsoft@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@UBrightnessModifier@Foundation@DisplayEnhancement@Windows@Microsoft@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessModifier,void *>::_Free_non_head<std::allocator<std::_List_node<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessModifier,void *>>>(std::allocator<std::_List_node<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessModifier,void *>> &,std::_List_node<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessModifier,void *> *)
0x18005a550  mov     rdx, r13
0x18005a553  mov     rcx, [rbp+100h+var_180]
0x18005a557  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005a55c  nop
0x18005a55d  lea     rcx, [rsp+200h+var_1A0]
0x18005a562  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005a567  nop
0x18005a568  mov     rcx, qword ptr [rsp+200h+var_198]
0x18005a56d  mov     rax, [rcx+8]
0x18005a571  mov     [rax], r12
0x18005a574  mov     rbx, [rcx]
0x18005a577  test    rbx, rbx
0x18005a57a  jz      short loc_18005A5A0
0x18005a57c  mov     rdi, [rbx]
0x18005a57f  mov     rcx, [rbx+18h]; this
0x18005a583  test    rcx, rcx
0x18005a586  jz      short loc_18005A58D
0x18005a588  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005a58d  mov     rdx, r13
0x18005a590  mov     rcx, rbx
0x18005a593  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005a598  mov     rbx, rdi
0x18005a59b  test    rdi, rdi
0x18005a59e  jnz     short loc_18005A57C
0x18005a5a0  mov     rdx, r13
0x18005a5a3  mov     rcx, qword ptr [rsp+200h+var_198]
0x18005a5a8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005a5ad  nop
0x18005a5ae  lea     rcx, [rbp+100h+var_F0]
0x18005a5b2  call    ??1?$function@$$A6A?AVDeManagementULongSettingType@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@XZ@std@@QEAA@XZ; std::function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>::~function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>(void)
0x18005a5b7  nop
0x18005a5b8  lea     rcx, [rbp+100h+var_B0]; this
0x18005a5bc  call    ??1ModifierChanged@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged::~ModifierChanged(void)
0x18005a5c1  mov     eax, 6
0x18005a5c6  mov     rcx, [rbp+100h+var_50]
0x18005a5cd  xor     rcx, rsp; StackCookie
0x18005a5d0  call    __security_check_cookie
0x18005a5d5  add     rsp, 1C8h
0x18005a5dc  pop     r15
0x18005a5de  pop     r14
0x18005a5e0  pop     r13
0x18005a5e2  pop     r12
0x18005a5e4  pop     rdi
0x18005a5e5  pop     rsi
0x18005a5e6  pop     rbx
0x18005a5e7  pop     rbp
0x18005a5e8  retn
```
