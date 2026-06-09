# Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::RegisterForBrightnessCapabilityChanges(void)

- ea: `0x18009ea08`
- end: `0x18009ec9d`
- name: `?RegisterForBrightnessCapabilityChanges@MonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@AEAAXXZ`
- size: `661`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009d6c0`

## callees

- `0x180005860`
- `0x180009904`
- `0x18000fb14`
- `0x180013138`
- `0x180013578`
- `0x1800191a8`
- `0x1800195cc`
- `0x18001ee60`
- `0x180029080`
- `0x180029404`
- `0x1800298c4`
- `0x18003ae70`
- `0x18009dba0`
- `0x18009ea08`
- `0x18009f35c`
- `0x1800ed010`

## import_xrefs

- `ntdll!RtlAllocateWnfSerializationGroup` at `0x18009eb94`
- `ntdll!RtlAllocateWnfSerializationGroup` at `0x18009ec03`
- `ntdll!RtlAllocateWnfSerializationGroup` at `0x18009eb94`
- `ntdll!RtlAllocateWnfSerializationGroup` at `0x18009ec03`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQueryFromId` at `0x18009eb5d`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQueryFromId` at `0x18009eb5d`

## string_xrefs

- `0x18009ec8b`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayadapter\lib\displayadapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::RegisterForBrightnessCapabilityChanges(
        Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl *this)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rax
  int ObjectQueryFromId; // eax
  unsigned int WnfSerializationGroup; // eax
  __int64 v8; // rax
  unsigned int v9; // eax
  __int64 v10; // rax
  __int64 v11; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v12; // [rsp+70h] [rbp-90h] BYREF
  DEVPROPKEY v13; // [rsp+78h] [rbp-88h]
  int v14; // [rsp+8Ch] [rbp-74h]
  __int64 v15; // [rsp+90h] [rbp-70h]
  int v16; // [rsp+98h] [rbp-68h]
  int v17; // [rsp+9Ch] [rbp-64h]
  GUID *v18; // [rsp+A0h] [rbp-60h]
  __int64 v19; // [rsp+A8h] [rbp-58h]
  DEVPROPKEY v20; // [rsp+B0h] [rbp-50h]
  int v21; // [rsp+C4h] [rbp-3Ch]
  __int64 v22; // [rsp+C8h] [rbp-38h]
  int v23; // [rsp+D0h] [rbp-30h]
  int v24; // [rsp+D4h] [rbp-2Ch]
  int *v25; // [rsp+D8h] [rbp-28h]
  _QWORD v26[4]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v27[8]; // [rsp+100h] [rbp+0h] BYREF
  __int64 (__fastcall **v28)(); // [rsp+108h] [rbp+8h] BYREF
  Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl *v29; // [rsp+110h] [rbp+10h]
  __int64 (__fastcall ***v30)(); // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v12 = 2;
  v13 = DEVPKEY_DeviceInterface_ClassGuid;
  v14 = 0;
  v15 = 0;
  v16 = 13;
  v17 = 16;
  v18 = &CLSID_BRIGHTNESS3_CONTROL_INTERFACE;
  v19 = 2;
  v20 = DEVPKEY_DeviceInterface_Enabled;
  v21 = 0;
  v22 = 0;
  v23 = 17;
  v24 = 1;
  v25 = &dword_180106154;
  v26[0] = &v12;
  v26[1] = v26;
  std::vector<_DEVPROP_FILTER_EXPRESSION>::vector<_DEVPROP_FILTER_EXPRESSION>(&v11, v26);
  wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&void DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>::reset(
    (char *)this + 192,
    0);
  v2 = (**(__int64 (__fastcall ***)(Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl *, _QWORD *))this)(
         this,
         v26);
  v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v2, v3, v4);
  ObjectQueryFromId = DevCreateObjectQueryFromId(1, v5);
  if ( ObjectQueryFromId < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1ED,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
      (const char *)(unsigned int)ObjectQueryFromId,
      0);
  std::wstring::_Tidy_deallocate(v26);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl'::`2'::impl)
    && (unsigned __int8)Microsoft::Windows::DisplayEnhancement::MonitorContainer::IsRunningAsService() )
  {
    WnfSerializationGroup = RtlAllocateWnfSerializationGroup();
    v28 = off_1800F3CF0;
    v29 = this;
    v30 = &v28;
    v8 = wil::make_wnf_subscription_blocking<wil::details::empty_wnf_state>(
           v26,
           &WNF_DX_BRIGHTNESS_CAPS_CHANGE,
           v27,
           WnfSerializationGroup);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delegate_wnf_subscription_state_blocking(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
      (char *)this + 200,
      v8);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delegate_wnf_subscription_state_blocking(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delegate_wnf_subscription_state_blocking(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(v26);
    wistd::function<void (unsigned char const &)>::~function<void (unsigned char const &)>(v27);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HdrBrightnessPolicy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HdrBrightnessPolicy>::GetImpl'::`2'::impl)
    && (unsigned __int8)Microsoft::Windows::DisplayEnhancement::MonitorContainer::IsRunningAsService() )
  {
    v9 = RtlAllocateWnfSerializationGroup();
    v28 = off_1800F3CC8;
    v29 = this;
    v30 = &v28;
    v10 = wil::make_wnf_subscription_blocking<wil::details::empty_wnf_state>(
            v26,
            &WNF_DX_HDR_BRIGHTNESS_POLICY_CHANGED,
            v27,
            v9);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delegate_wnf_subscription_state_blocking(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
      (char *)this + 208,
      v10);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delegate_wnf_subscription_state_blocking(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delegate_wnf_subscription_state_blocking(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(v26);
    wistd::function<void (unsigned char const &)>::~function<void (unsigned char const &)>(v27);
  }
  std::vector<_DEVPROP_FILTER_EXPRESSION>::_Tidy(&v11);
}

```

## disassembly

```asm
0x18009ea08  mov     [rsp-8+arg_8], rbx
0x18009ea0d  mov     [rsp-8+arg_10], rsi
0x18009ea12  push    rbp
0x18009ea13  push    rdi
0x18009ea14  push    r14
0x18009ea16  lea     rbp, [rsp-80h]
0x18009ea1b  sub     rsp, 180h
0x18009ea22  mov     rax, cs:__security_cookie
0x18009ea29  xor     rax, rsp
0x18009ea2c  mov     [rbp+90h+var_18], rax
0x18009ea30  mov     r14, rcx
0x18009ea33  mov     [rsp+190h+var_120], 2
0x18009ea3c  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x18009ea43  movups  [rsp+190h+var_118], xmm0
0x18009ea48  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x18009ea4e  mov     [rbp+90h+var_108], eax
0x18009ea51  mov     [rbp+90h+var_104], 0
0x18009ea58  mov     [rbp+90h+var_100], 0
0x18009ea60  mov     [rbp+90h+var_F8], 0Dh
0x18009ea67  mov     [rbp+90h+var_F4], 10h
0x18009ea6e  lea     rax, CLSID_BRIGHTNESS3_CONTROL_INTERFACE
0x18009ea75  mov     [rbp+90h+var_F0], rax
0x18009ea79  mov     [rbp+90h+var_E8], 2
0x18009ea81  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x18009ea88  movaps  [rbp+90h+var_E0], xmm0
0x18009ea8c  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x18009ea92  mov     [rbp+90h+var_D0], eax
0x18009ea95  mov     [rbp+90h+var_CC], 0
0x18009ea9c  mov     [rbp+90h+var_C8], 0
0x18009eaa4  mov     [rbp+90h+var_C0], 11h
0x18009eaab  mov     [rbp+90h+var_BC], 1
0x18009eab2  lea     rax, dword_180106154
0x18009eab9  mov     [rbp+90h+var_B8], rax
0x18009eabd  lea     rax, [rsp+190h+var_120]
0x18009eac2  mov     [rbp+90h+var_B0], rax
0x18009eac6  lea     rax, [rbp+90h+var_B0]
0x18009eaca  mov     [rbp+90h+var_A8], rax
0x18009eace  lea     rdx, [rbp+90h+var_B0]
0x18009ead2  lea     rcx, [rsp+190h+var_140]
0x18009ead7  call    ??0?$vector@U_DEVPROP_FILTER_EXPRESSION@@V?$allocator@U_DEVPROP_FILTER_EXPRESSION@@@std@@@std@@QEAA@V?$initializer_list@U_DEVPROP_FILTER_EXPRESSION@@@1@AEBV?$allocator@U_DEVPROP_FILTER_EXPRESSION@@@1@@Z; std::vector<_DEVPROP_FILTER_EXPRESSION>::vector<_DEVPROP_FILTER_EXPRESSION>(std::initializer_list<_DEVPROP_FILTER_EXPRESSION>,std::allocator<_DEVPROP_FILTER_EXPRESSION> const &)
0x18009eadc  nop
0x18009eadd  lea     rbx, [r14+0C0h]
0x18009eae4  xor     edx, edx
0x18009eae6  mov     rcx, rbx
0x18009eae9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHDEVQUERY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>::reset(HDEVQUERY__ *)
0x18009eaee  mov     rdi, [rsp+190h+var_140]
0x18009eaf3  mov     rsi, [rsp+190h+var_138]
0x18009eaf8  sub     rsi, rdi
0x18009eafb  sar     rsi, 3
0x18009eaff  mov     rax, 6DB6DB6DB6DB6DB7h
0x18009eb09  imul    rsi, rax
0x18009eb0d  mov     rax, [r14]
0x18009eb10  lea     rdx, [rbp+90h+var_B0]
0x18009eb14  mov     rcx, r14
0x18009eb17  mov     rax, [rax]
0x18009eb1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eb1f  nop
0x18009eb20  mov     rcx, rax
0x18009eb23  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009eb28  mov     [rsp+190h+var_148], rbx
0x18009eb2d  mov     [rsp+190h+var_150], r14
0x18009eb32  lea     rdx, ?DevQueryCallbackThunk@MonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::DevQueryCallbackThunk(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18009eb39  mov     [rsp+190h+var_158], rdx
0x18009eb3e  mov     [rsp+190h+var_160], rdi
0x18009eb43  mov     [rsp+190h+var_168], esi
0x18009eb47  mov     qword ptr [rsp+190h+var_170], 0; int
0x18009eb50  xor     r9d, r9d
0x18009eb53  lea     r8d, [r9+1]
0x18009eb57  mov     rdx, rax
0x18009eb5a  mov     ecx, r8d
0x18009eb5d  call    cs:__imp_DevCreateObjectQueryFromId
0x18009eb63  mov     rcx, [rbp+98h]; this
0x18009eb6a  test    eax, eax
0x18009eb6c  js      loc_18009EC88
0x18009eb72  lea     rcx, [rbp+90h+var_B0]
0x18009eb76  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009eb7b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExternalBrightness@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExternalBrightness@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness> `wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl(void)'::`2'::impl
0x18009eb82  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExternalBrightness@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(void)
0x18009eb87  test    al, al
0x18009eb89  jz      short loc_18009EBEA
0x18009eb8b  call    Microsoft__Windows__DisplayEnhancement__MonitorContainer__IsRunningAsService
0x18009eb90  test    al, al
0x18009eb92  jz      short loc_18009EBEA
0x18009eb94  call    cs:__imp_RtlAllocateWnfSerializationGroup
0x18009eb9a  lea     rcx, off_1800F3CF0
0x18009eba1  mov     [rbp+90h+var_88], rcx
0x18009eba5  mov     [rbp+90h+var_80], r14
0x18009eba9  lea     rcx, [rbp+90h+var_88]
0x18009ebad  mov     [rbp+90h+var_20], rcx
0x18009ebb1  mov     r9d, eax
0x18009ebb4  lea     r8, [rbp+90h+var_90]
0x18009ebb8  lea     rdx, WNF_DX_BRIGHTNESS_CAPS_CHANGE
0x18009ebbf  lea     rcx, [rbp+90h+var_B0]
0x18009ebc3  call    ??$make_wnf_subscription_blocking@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delegate_wnf_subscription_state_blocking@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription_blocking<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x18009ebc8  lea     rcx, [r14+0C8h]
0x18009ebcf  mov     rdx, rax
0x18009ebd2  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delegate_wnf_subscription_state_blocking@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delegate_wnf_subscription_state_blocking(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delegate_wnf_subscription_state_blocking(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18009ebd7  lea     rcx, [rbp+90h+var_B0]
0x18009ebdb  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delegate_wnf_subscription_state_blocking@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delegate_wnf_subscription_state_blocking(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delegate_wnf_subscription_state_blocking(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18009ebe0  nop
0x18009ebe1  lea     rcx, [rbp+90h+var_90]
0x18009ebe5  call    ??1?$function@$$A6AXAEBE@Z@wistd@@QEAA@XZ; wistd::function<void (uchar const &)>::~function<void (uchar const &)>(void)
0x18009ebea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HdrBrightnessPolicy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HdrBrightnessPolicy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HdrBrightnessPolicy> `wil::Feature<__WilFeatureTraits_Feature_HdrBrightnessPolicy>::GetImpl(void)'::`2'::impl
0x18009ebf1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HdrBrightnessPolicy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HdrBrightnessPolicy>::__private_IsEnabled(void)
0x18009ebf6  test    al, al
0x18009ebf8  jz      short loc_18009EC5A
0x18009ebfa  call    Microsoft__Windows__DisplayEnhancement__MonitorContainer__IsRunningAsService
0x18009ebff  test    al, al
0x18009ec01  jz      short loc_18009EC5A
0x18009ec03  call    cs:__imp_RtlAllocateWnfSerializationGroup
0x18009ec09  lea     rcx, off_1800F3CC8
0x18009ec10  mov     [rbp+90h+var_88], rcx
0x18009ec14  mov     [rbp+90h+var_80], r14
0x18009ec18  lea     rcx, [rbp+90h+var_88]
0x18009ec1c  mov     [rbp+90h+var_20], rcx
0x18009ec20  mov     r9d, eax
0x18009ec23  lea     r8, [rbp+90h+var_90]
0x18009ec27  lea     rdx, WNF_DX_HDR_BRIGHTNESS_POLICY_CHANGED
0x18009ec2e  lea     rcx, [rbp+90h+var_B0]
0x18009ec32  call    ??$make_wnf_subscription_blocking@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delegate_wnf_subscription_state_blocking@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription_blocking<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x18009ec37  lea     rcx, [r14+0D0h]
0x18009ec3e  mov     rdx, rax
0x18009ec41  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delegate_wnf_subscription_state_blocking@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delegate_wnf_subscription_state_blocking(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delegate_wnf_subscription_state_blocking(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18009ec46  lea     rcx, [rbp+90h+var_B0]
0x18009ec4a  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delegate_wnf_subscription_state_blocking@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delegate_wnf_subscription_state_blocking(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delegate_wnf_subscription_state_blocking(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18009ec4f  nop
0x18009ec50  lea     rcx, [rbp+90h+var_90]
0x18009ec54  call    ??1?$function@$$A6AXAEBE@Z@wistd@@QEAA@XZ; wistd::function<void (uchar const &)>::~function<void (uchar const &)>(void)
0x18009ec59  nop
0x18009ec5a  lea     rcx, [rsp+190h+var_140]
0x18009ec5f  call    ?_Tidy@?$vector@U_DEVPROP_FILTER_EXPRESSION@@V?$allocator@U_DEVPROP_FILTER_EXPRESSION@@@std@@@std@@AEAAXXZ; std::vector<_DEVPROP_FILTER_EXPRESSION>::_Tidy(void)
0x18009ec64  mov     rcx, [rbp+90h+var_18]
0x18009ec68  xor     rcx, rsp; StackCookie
0x18009ec6b  call    __security_check_cookie
0x18009ec70  lea     r11, [rsp+190h+var_10]
0x18009ec78  mov     rbx, [r11+28h]
0x18009ec7c  mov     rsi, [r11+30h]
0x18009ec80  mov     rsp, r11
0x18009ec83  pop     r14
0x18009ec85  pop     rdi
0x18009ec86  pop     rbp
0x18009ec87  retn
0x18009ec88  mov     r9d, eax; char *
0x18009ec8b  lea     r8, aOnecoreuapDriv_42; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18009ec92  mov     edx, 1EDh; void *
0x18009ec97  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
