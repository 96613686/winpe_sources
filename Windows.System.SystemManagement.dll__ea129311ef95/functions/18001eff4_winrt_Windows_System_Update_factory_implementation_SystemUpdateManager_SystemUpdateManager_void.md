# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SystemUpdateManager(void)

- ea: `0x18001eff4`
- end: `0x18001f1b8`
- name: `??0SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA@XZ`
- size: `452`
- prototype: `winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *__fastcall(winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800050bc`

## callees

- `0x180002dc0`
- `0x180003e90`
- `0x180005ce4`
- `0x180010580`
- `0x18001e248`
- `0x18001e5cc`
- `0x18001edec`
- `0x18001eff4`
- `0x18001f988`
- `0x180023414`

## pseudocode

```c
winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *__fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SystemUpdateManager(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this)
{
  __int64 v2; // rdx
  _QWORD *v3; // rax
  __int64 v4; // rdx
  _QWORD *v5; // rax
  __int64 v6; // rdx
  _QWORD *v7; // rax
  __int64 v9; // [rsp+20h] [rbp-49h] BYREF
  __int64 v10; // [rsp+28h] [rbp-41h] BYREF
  _BYTE v11[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 (__fastcall **v12)(); // [rsp+38h] [rbp-31h] BYREF
  __int64 v13; // [rsp+40h] [rbp-29h]
  __int64 (__fastcall ***v14)(); // [rsp+A0h] [rbp+37h]

  winrt::impl::producers_base<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::System::Update::ISystemUpdateManagerStatics>>::producers_base<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::System::Update::ISystemUpdateManagerStatics>>();
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  std::atomic<unsigned __int64>::atomic<unsigned __int64>((char *)this + 8);
  *(_QWORD *)this = &winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::`vftable';
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 14) = 0;
  if ( winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsSupported(this) )
  {
    v2 = *wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
            &v10,
            (__int64)this);
    v12 = off_18002EDB0;
    v13 = v2;
    v14 = &v12;
    v3 = wil::make_wnf_subscription<wil::details::empty_wnf_state>(&v9, (__int64)&WNF_USO_STATE_CHANGE, (__int64)v11);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
      (char *)this + 64,
      v3);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v9);
    wistd::function<void (void)>::~function<void (void)>(v11);
    v4 = *wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
            &v10,
            (__int64)this);
    v12 = off_18002EDB0;
    v13 = v4;
    v14 = &v12;
    v5 = wil::make_wnf_subscription<wil::details::empty_wnf_state>(&v9, (__int64)&WNF_USO_UPDATE_PROGRESS, (__int64)v11);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
      (char *)this + 72,
      v5);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v9);
    wistd::function<void (void)>::~function<void (void)>(v11);
    v6 = *wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
            &v10,
            (__int64)this);
    v12 = off_18002ED88;
    v13 = v6;
    v14 = &v12;
    v7 = wil::make_wnf_subscription<wil::details::empty_wnf_state>(
           &v9,
           (__int64)&WNF_USO_STATE_ATTENTION_REQUIRED,
           (__int64)v11);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
      (char *)this + 80,
      v7);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v9);
    wistd::function<void (void)>::~function<void (void)>(v11);
  }
  return this;
}

```

## disassembly

```asm
0x18001eff4  mov     [rsp-8+arg_8], rbx
0x18001eff9  mov     [rsp-8+arg_10], rsi
0x18001effe  push    rbp
0x18001efff  push    rdi
0x18001f000  push    r14
0x18001f002  lea     rbp, [rsp-47h]
0x18001f007  sub     rsp, 0B0h
0x18001f00e  mov     rax, cs:__security_cookie
0x18001f015  xor     rax, rsp
0x18001f018  mov     [rbp+57h+var_18], rax
0x18001f01c  mov     rbx, rcx
0x18001f01f  add     rcx, 10h
0x18001f023  call    ??0?$producers_base@USystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@V?$tuple@UIActivationFactory@Foundation@Windows@winrt@@UISystemUpdateManagerStatics@Update@System@34@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::System::Update::ISystemUpdateManagerStatics>>::producers_base<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::System::Update::ISystemUpdateManagerStatics>>(void)
0x18001f028  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001f02f  lea     rcx, [rbx+8]
0x18001f033  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x18001f038  lea     rcx, ??_7SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@6B@; const winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::`vftable'
0x18001f03f  mov     [rbx], rcx
0x18001f042  mov     qword ptr [rbx+20h], 0
0x18001f04a  mov     qword ptr [rbx+28h], 0
0x18001f052  mov     qword ptr [rbx+30h], 0
0x18001f05a  mov     qword ptr [rbx+40h], 0
0x18001f062  mov     qword ptr [rbx+48h], 0
0x18001f06a  mov     qword ptr [rbx+50h], 0
0x18001f072  mov     dword ptr [rbx+38h], 0
0x18001f079  mov     rcx, rbx; this
0x18001f07c  call    ?IsSupported@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsSupported(void)
0x18001f081  test    al, al
0x18001f083  jz      loc_18001F191
0x18001f089  mov     rdx, rbx
0x18001f08c  lea     rcx, [rbp+57h+var_98]
0x18001f090  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001f095  mov     rdx, [rax]
0x18001f098  lea     rax, off_18002EDB0
0x18001f09f  mov     [rbp+57h+var_88], rax
0x18001f0a3  mov     [rbp+57h+var_80], rdx
0x18001f0a7  lea     rax, [rbp+57h+var_88]
0x18001f0ab  mov     [rbp+57h+var_20], rax
0x18001f0af  lea     r8, [rbp+57h+var_90]
0x18001f0b3  lea     rdx, WNF_USO_STATE_CHANGE
0x18001f0ba  lea     rcx, [rbp+57h+var_A0]
0x18001f0be  call    ??$make_wnf_subscription@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x18001f0c3  mov     rdx, rax
0x18001f0c6  lea     rcx, [rbx+40h]
0x18001f0ca  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18001f0cf  lea     rcx, [rbp+57h+var_A0]
0x18001f0d3  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18001f0d8  lea     rcx, [rbp+57h+var_90]
0x18001f0dc  call    ??1?$function@$$A6AXXZ@wistd@@QEAA@XZ; wistd::function<void (void)>::~function<void (void)>(void)
0x18001f0e1  mov     rdx, rbx
0x18001f0e4  lea     rcx, [rbp+57h+var_98]
0x18001f0e8  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001f0ed  mov     rdx, [rax]
0x18001f0f0  lea     rax, off_18002EDB0
0x18001f0f7  mov     [rbp+57h+var_88], rax
0x18001f0fb  mov     [rbp+57h+var_80], rdx
0x18001f0ff  lea     rax, [rbp+57h+var_88]
0x18001f103  mov     [rbp+57h+var_20], rax
0x18001f107  lea     r8, [rbp+57h+var_90]
0x18001f10b  lea     rdx, WNF_USO_UPDATE_PROGRESS
0x18001f112  lea     rcx, [rbp+57h+var_A0]
0x18001f116  call    ??$make_wnf_subscription@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x18001f11b  mov     rdx, rax
0x18001f11e  lea     rcx, [rbx+48h]
0x18001f122  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18001f127  lea     rcx, [rbp+57h+var_A0]
0x18001f12b  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18001f130  lea     rcx, [rbp+57h+var_90]
0x18001f134  call    ??1?$function@$$A6AXXZ@wistd@@QEAA@XZ; wistd::function<void (void)>::~function<void (void)>(void)
0x18001f139  mov     rdx, rbx
0x18001f13c  lea     rcx, [rbp+57h+var_98]
0x18001f140  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001f145  mov     rdx, [rax]
0x18001f148  lea     rax, off_18002ED88
0x18001f14f  mov     [rbp+57h+var_88], rax
0x18001f153  mov     [rbp+57h+var_80], rdx
0x18001f157  lea     rax, [rbp+57h+var_88]
0x18001f15b  mov     [rbp+57h+var_20], rax
0x18001f15f  lea     r8, [rbp+57h+var_90]
0x18001f163  lea     rdx, WNF_USO_STATE_ATTENTION_REQUIRED
0x18001f16a  lea     rcx, [rbp+57h+var_A0]
0x18001f16e  call    ??$make_wnf_subscription@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x18001f173  mov     rdx, rax
0x18001f176  lea     rcx, [rbx+50h]
0x18001f17a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18001f17f  lea     rcx, [rbp+57h+var_A0]
0x18001f183  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18001f188  lea     rcx, [rbp+57h+var_90]
0x18001f18c  call    ??1?$function@$$A6AXXZ@wistd@@QEAA@XZ; wistd::function<void (void)>::~function<void (void)>(void)
0x18001f191  mov     rax, rbx
0x18001f194  mov     rcx, [rbp+57h+var_18]
0x18001f198  xor     rcx, rsp; StackCookie
0x18001f19b  call    __security_check_cookie
0x18001f1a0  lea     r11, [rsp+0C0h+var_10]
0x18001f1a8  mov     rbx, [r11+28h]
0x18001f1ac  mov     rsi, [r11+30h]
0x18001f1b0  mov     rsp, r11
0x18001f1b3  pop     r14
0x18001f1b5  pop     rdi
0x18001f1b6  pop     rbp
0x18001f1b7  retn
```
