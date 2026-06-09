# OobeEasyConnectTask::~OobeEasyConnectTask(void)

- ea: `0x180047dc4`
- end: `0x180047ec0`
- name: `??1OobeEasyConnectTask@@EEAA@XZ`
- size: `252`
- prototype: `void __fastcall(OobeEasyConnectTask *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800362d0`

## callees

- `0x180002150`
- `0x18000ad20`
- `0x18001f5b8`
- `0x180022a1c`
- `0x180022e9c`
- `0x18003601c`
- `0x1800360b4`
- `0x1800368cc`
- `0x180047dc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180047ea3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180047ea3`

## string_xrefs

- `0x180047df7`: `OobeEasyConnectTask::~OobeEasyConnectTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall OobeEasyConnectTask::~OobeEasyConnectTask(OobeEasyConnectTask *this)
{
  __int64 v2; // rdi
  struct _RTL_CRITICAL_SECTION *v3; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &OobeEasyConnectTask::`vftable'{for `IESimSettingEventHandler'};
  *((_QWORD *)this + 1) = &OobeEasyConnectTask::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Networking::UX::IUXCategoryEventHandler>'};
  MBSettingUXLogging::Info("OobeEasyConnectTask::~OobeEasyConnectTask", 0x4Fu, "Enter");
  v2 = *((_QWORD *)this + 149);
  if ( v2 )
  {
    wil::EnterCriticalSection(&v3, v2 + 200);
    *(_DWORD *)(v2 + 72) |= 0x300u;
    if ( *(_QWORD *)(v2 + 248) )
      tip2::details::shared_data<1,0,0>::complete_helper(v2 + 8, 2);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v3);
  }
  wil::com_ptr_t<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>,wil::err_returncode_policy>((void **)this + 149);
  std::wstring::_Tidy_deallocate((char *)this + 1160);
  std::wstring::_Tidy_deallocate((char *)this + 216);
  std::wstring::_Tidy_deallocate((char *)this + 176);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 136);
  std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>((void **)this + 13);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 72);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 64);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x180047dc4  mov     [rsp+arg_8], rbx
0x180047dc9  mov     [rsp+arg_10], rsi
0x180047dce  push    rdi
0x180047dcf  sub     rsp, 20h
0x180047dd3  lea     rax, ??_7OobeEasyConnectTask@@6BIESimSettingEventHandler@@@; const OobeEasyConnectTask::`vftable'{for `IESimSettingEventHandler'}
0x180047dda  mov     rbx, rcx
0x180047ddd  mov     [rcx], rax
0x180047de0  lea     r8, aEnter; "Enter"
0x180047de7  lea     rax, ??_7OobeEasyConnectTask@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIUXCategoryEventHandler@UX@Networking@Windows@@@Details@WRL@Microsoft@@@; const OobeEasyConnectTask::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Networking::UX::IUXCategoryEventHandler>'}
0x180047dee  mov     edx, 4Fh ; 'O'; unsigned int
0x180047df3  mov     [rcx+8], rax
0x180047df7  lea     rcx, aOobeeasyconnec_13; "OobeEasyConnectTask::~OobeEasyConnectTa"...
0x180047dfe  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180047e03  lea     rsi, [rbx+4A8h]
0x180047e0a  mov     rdi, [rsi]
0x180047e0d  test    rdi, rdi
0x180047e10  jz      short loc_180047E4C
0x180047e12  lea     rdx, [rdi+0C8h]
0x180047e19  lea     rcx, [rsp+28h+arg_0]
0x180047e1e  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180047e23  or      dword ptr [rdi+48h], 300h
0x180047e2a  cmp     qword ptr [rdi+0F8h], 0
0x180047e32  jz      short loc_180047E42
0x180047e34  mov     edx, 2
0x180047e39  lea     rcx, [rdi+8]
0x180047e3d  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x180047e42  lea     rcx, [rsp+28h+arg_0]
0x180047e47  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180047e4c  mov     rcx, rsi
0x180047e4f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>,wil::err_returncode_policy>(void)
0x180047e54  lea     rcx, [rbx+488h]
0x180047e5b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180047e60  lea     rcx, [rbx+0D8h]
0x180047e67  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180047e6c  lea     rcx, [rbx+0B0h]
0x180047e73  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180047e78  lea     rcx, [rbx+88h]
0x180047e7f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047e84  lea     rcx, [rbx+68h]
0x180047e88  call    ??1?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@std@@QEAA@XZ; std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>(void)
0x180047e8d  lea     rcx, [rbx+48h]
0x180047e91  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047e96  lea     rcx, [rbx+40h]
0x180047e9a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047e9f  lea     rcx, [rbx+18h]; lpCriticalSection
0x180047ea3  call    cs:__imp_DeleteCriticalSection
0x180047ea9  mov     rsi, [rsp+28h+arg_10]
0x180047eae  mov     dword ptr [rbx+14h], 0C0000001h
0x180047eb5  mov     rbx, [rsp+28h+arg_8]
0x180047eba  add     rsp, 20h
0x180047ebe  pop     rdi
0x180047ebf  retn
```
