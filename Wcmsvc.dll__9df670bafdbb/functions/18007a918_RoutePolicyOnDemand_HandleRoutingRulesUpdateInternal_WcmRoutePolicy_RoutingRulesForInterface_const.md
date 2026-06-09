# RoutePolicyOnDemand::HandleRoutingRulesUpdateInternal(WcmRoutePolicy::RoutingRulesForInterface const *)

- ea: `0x18007a918`
- end: `0x18007aa9f`
- name: `?HandleRoutingRulesUpdateInternal@RoutePolicyOnDemand@@AEAAXPEBURoutingRulesForInterface@WcmRoutePolicy@@@Z`
- size: `391`
- prototype: `void(RoutePolicyOnDemand *__hidden this, const struct WcmRoutePolicy::RoutingRulesForInterface *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a808c`

## callees

- `0x18000dd88`
- `0x180012410`
- `0x18002706c`
- `0x180027630`
- `0x18007a918`
- `0x18007aaa8`
- `0x180084f50`
- `0x1800a23a8`
- `0x1800a37ac`
- `0x1800a3848`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007aa19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007aa47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007aa19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007aa47`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007aa5c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007aa5c`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18007a950`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18007a950`

## string_xrefs

- `0x18007a965`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall RoutePolicyOnDemand::HandleRoutingRulesUpdateInternal(RoutePolicyOnDemand *this, const NET_LUID *a2)
{
  unsigned int v4; // eax
  _DWORD *v5; // rdi
  unsigned int i; // esi
  const char *v7; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-88h] BYREF
  RoutePolicyOnDemand *v9; // [rsp+28h] [rbp-80h] BYREF
  GUID v10; // [rsp+30h] [rbp-78h]
  _BYTE v11[24]; // [rsp+40h] [rbp-68h] BYREF
  __int128 v12; // [rsp+58h] [rbp-50h] BYREF
  __int64 v13; // [rsp+68h] [rbp-40h]
  GUID InterfaceGuid; // [rsp+70h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  InterfaceGuid = 0;
  v4 = ConvertInterfaceLuidToGuid(a2, &InterfaceGuid);
  try
  {
    if ( v4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x7D4,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        (const char *)v4,
        (unsigned int)lpCriticalSection);
    v12 = 0;
    v13 = 0;
    std::vector<FirewallManager::TrafficDescriptor>::vector<FirewallManager::TrafficDescriptor>(&v12);
    v5 = (_DWORD *)&a2[1].Info + 1;
    for ( i = 0; i < LODWORD(a2[1].Value); ++i )
    {
      if ( *v5 )
      {
        if ( (*v5 & 0xFFFEE7FF) == 0 )
        {
          std::vector<WWAN_TRAFFIC_DESCRIPTOR>::_Emplace_one_at_back<WWAN_TRAFFIC_DESCRIPTOR const &>(&v12, v5);
          v5 = (_DWORD *)((char *)v5 + (unsigned int)v5[117] + 472);
        }
      }
    }
    v9 = this;
    v10 = InterfaceGuid;
    std::vector<SleepStudy::Singleton::ApplicationNetworkActivity>::vector<SleepStudy::Singleton::ApplicationNetworkActivity>(
      v11,
      &v12);
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, (char *)this + 104);
    if ( *((_BYTE *)this + 368) )
    {
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
    }
    else
    {
      if ( *((_DWORD *)this + 24) == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__RoutePolicyOnDemand::HandleRoutingRulesUpdateInternal_::_3_::_lambda_1___(
          (char *)this + 248,
          &v9);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__RoutePolicyOnDemand::HandleRoutingRulesUpdateInternal_::_3_::_lambda_1___(
          (char *)this + 328,
          &v9);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      _InterlockedIncrement64((volatile signed __int64 *)this + 29);
      SubmitThreadpoolWork(*((PTP_WORK *)this + 28));
    }
    std::vector<WWAN_TRAFFIC_DESCRIPTOR>::_Tidy(v11);
    std::vector<WWAN_TRAFFIC_DESCRIPTOR>::_Tidy(&v12);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x7FF,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
      v7);
  }
}

```

## disassembly

```asm
0x18007a918  mov     [rsp+arg_10], rbx
0x18007a91d  push    rsi
0x18007a91e  push    rdi
0x18007a91f  push    r14
0x18007a921  sub     rsp, 90h
0x18007a928  mov     rax, cs:__security_cookie
0x18007a92f  xor     rax, rsp
0x18007a932  mov     [rsp+0A8h+var_28], rax
0x18007a93a  mov     r14, rdx
0x18007a93d  mov     rbx, rcx
0x18007a940  xorps   xmm0, xmm0
0x18007a943  movups  xmmword ptr [rsp+0A8h+InterfaceGuid.Data1], xmm0
0x18007a948  lea     rdx, [rsp+0A8h+InterfaceGuid]; InterfaceGuid
0x18007a94d  mov     rcx, r14; InterfaceLuid
0x18007a950  call    cs:__imp_ConvertInterfaceLuidToGuid
0x18007a956  mov     rcx, [rsp+0A8h]; this
0x18007a95e  test    eax, eax
0x18007a960  jz      short loc_18007A976
0x18007a962  mov     r9d, eax; char *
0x18007a965  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18007a96c  mov     edx, 7D4h; void *
0x18007a971  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18007a976  xorps   xmm0, xmm0
0x18007a979  xor     eax, eax
0x18007a97b  movups  [rsp+0A8h+var_50], xmm0
0x18007a980  mov     [rsp+0A8h+var_40], rax
0x18007a985  lea     rcx, [rsp+0A8h+var_50]
0x18007a98a  call    ??0?$vector@UTrafficDescriptor@FirewallManager@@V?$allocator@UTrafficDescriptor@FirewallManager@@@std@@@std@@QEAA@XZ; std::vector<FirewallManager::TrafficDescriptor>::vector<FirewallManager::TrafficDescriptor>(void)
0x18007a98f  nop
0x18007a990  lea     rdi, [r14+0Ch]
0x18007a994  xor     esi, esi
0x18007a996  cmp     esi, [r14+8]
0x18007a99a  jnb     short loc_18007A9CA
0x18007a99c  cmp     dword ptr [rdi], 0
0x18007a99f  jz      short loc_18007A9C6
0x18007a9a1  test    dword ptr [rdi], 0FFFEE7FFh
0x18007a9a7  jnz     short loc_18007A9C6
0x18007a9a9  mov     rdx, rdi
0x18007a9ac  lea     rcx, [rsp+0A8h+var_50]
0x18007a9b1  call    ??$_Emplace_one_at_back@AEBUWWAN_TRAFFIC_DESCRIPTOR@@@?$vector@UWWAN_TRAFFIC_DESCRIPTOR@@V?$allocator@UWWAN_TRAFFIC_DESCRIPTOR@@@std@@@std@@AEAAAEAUWWAN_TRAFFIC_DESCRIPTOR@@AEBU2@@Z; std::vector<WWAN_TRAFFIC_DESCRIPTOR>::_Emplace_one_at_back<WWAN_TRAFFIC_DESCRIPTOR const &>(WWAN_TRAFFIC_DESCRIPTOR const &)
0x18007a9b6  mov     eax, [rdi+1D4h]
0x18007a9bc  add     rdi, 1D8h
0x18007a9c3  add     rdi, rax
0x18007a9c6  inc     esi
0x18007a9c8  jmp     short loc_18007A996
0x18007a9ca  mov     [rsp+0A8h+var_80], rbx
0x18007a9cf  movups  xmm0, xmmword ptr [rsp+0A8h+InterfaceGuid.Data1]
0x18007a9d4  movdqu  [rsp+0A8h+var_78], xmm0
0x18007a9da  lea     rdx, [rsp+0A8h+var_50]
0x18007a9df  lea     rcx, [rsp+0A8h+var_68]
0x18007a9e4  call    ??0?$vector@UApplicationNetworkActivity@Singleton@SleepStudy@@V?$allocator@UApplicationNetworkActivity@Singleton@SleepStudy@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<SleepStudy::Singleton::ApplicationNetworkActivity>::vector<SleepStudy::Singleton::ApplicationNetworkActivity>(std::vector<SleepStudy::Singleton::ApplicationNetworkActivity> &&)
0x18007a9e9  nop
0x18007a9ea  mov     [rsp+0A8h+lpCriticalSection], 0
0x18007a9f3  lea     rdx, [rbx+68h]
0x18007a9f7  lea     rcx, [rsp+0A8h+lpCriticalSection]
0x18007a9fc  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18007aa01  nop
0x18007aa02  lea     rcx, [rbx+0F8h]
0x18007aa09  cmp     byte ptr [rcx+78h], 0
0x18007aa0d  jz      short loc_18007AA21
0x18007aa0f  mov     rcx, [rsp+0A8h+lpCriticalSection]; lpCriticalSection
0x18007aa14  test    rcx, rcx
0x18007aa17  jz      short loc_18007AA63
0x18007aa19  call    cs:__imp_LeaveCriticalSection
0x18007aa1f  jmp     short loc_18007AA63
0x18007aa21  lea     rdx, [rsp+0A8h+var_80]
0x18007aa26  cmp     dword ptr [rbx+60h], 1
0x18007aa2a  jnz     short loc_18007AA33
0x18007aa2c  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__RoutePolicyOnDemand__HandleRoutingRulesUpdateInternal____3____lambda_1___
0x18007aa31  jmp     short loc_18007AA3D
0x18007aa33  add     rcx, 50h ; 'P'
0x18007aa37  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__RoutePolicyOnDemand__HandleRoutingRulesUpdateInternal____3____lambda_1___
0x18007aa3c  nop
0x18007aa3d  mov     rcx, [rsp+0A8h+lpCriticalSection]; lpCriticalSection
0x18007aa42  test    rcx, rcx
0x18007aa45  jz      short loc_18007AA4D
0x18007aa47  call    cs:__imp_LeaveCriticalSection
0x18007aa4d  lock inc qword ptr [rbx+0E8h]
0x18007aa55  mov     rcx, [rbx+0E0h]; pwk
0x18007aa5c  call    cs:__imp_SubmitThreadpoolWork
0x18007aa62  nop
0x18007aa63  lea     rcx, [rsp+0A8h+var_68]
0x18007aa68  call    ?_Tidy@?$vector@UWWAN_TRAFFIC_DESCRIPTOR@@V?$allocator@UWWAN_TRAFFIC_DESCRIPTOR@@@std@@@std@@AEAAXXZ; std::vector<WWAN_TRAFFIC_DESCRIPTOR>::_Tidy(void)
0x18007aa6d  nop
0x18007aa6e  lea     rcx, [rsp+0A8h+var_50]
0x18007aa73  call    ?_Tidy@?$vector@UWWAN_TRAFFIC_DESCRIPTOR@@V?$allocator@UWWAN_TRAFFIC_DESCRIPTOR@@@std@@@std@@AEAAXXZ; std::vector<WWAN_TRAFFIC_DESCRIPTOR>::_Tidy(void)
0x18007aa78  nop
0x18007aa79  jmp     short $+2
0x18007aa7b  mov     rcx, [rsp+0A8h+var_28]
0x18007aa83  xor     rcx, rsp; StackCookie
0x18007aa86  call    __security_check_cookie
0x18007aa8b  mov     rbx, [rsp+0A8h+arg_10]
0x18007aa93  add     rsp, 90h
0x18007aa9a  pop     r14
0x18007aa9c  pop     rdi
0x18007aa9d  pop     rsi
0x18007aa9e  retn
```
