# ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(ulong,Concurrency::cancellation_token,Microsoft::Windows::Autopilot::MsaTpmKeyState &,ModernDeployment::Autopilot::Core::AttestationState &)

- ea: `0x1801246a4`
- end: `0x180124993`
- name: `?WaitForCompletion@?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAAJKVcancellation_token@Concurrency@@AEAUMsaTpmKeyState@3Windows@Microsoft@@AEAW4AttestationState@234@@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18012317c`

## callees

- `0x18000b820`
- `0x180067a34`
- `0x180067a54`
- `0x18006df3c`
- `0x18006e104`
- `0x18008cfa4`
- `0x1800953b4`
- `0x1800b1998`
- `0x1800ceee4`
- `0x1800d8480`
- `0x180118938`
- `0x180123e4c`
- `0x1801246a4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18012477c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18012477c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012478e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012478e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801246ed`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801246ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180124838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180124838`
- `msvcp_win!_Mtx_unlock` at `0x180124949`
- `msvcp_win!_Mtx_unlock` at `0x180124949`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18012480c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18012480c`

## string_xrefs

- `0x180124755`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x1801247a7`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x18012485e`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x1801248a4`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x1801248ea`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(
        __int64 a1,
        DWORD a2,
        pplx::cancellation_token_registration *a3,
        _QWORD *a4,
        _DWORD *a5)
{
  __int64 v9; // rax
  unsigned int LastError; // ebx
  const char *v12; // r9
  DWORD v13; // eax
  signed int v14; // eax
  Concurrency::details::_RefCounter *v15; // [rsp+20h] [rbp-91h] BYREF
  _QWORD v16[2]; // [rsp+28h] [rbp-89h] BYREF
  _BYTE v17[8]; // [rsp+38h] [rbp-79h] BYREF
  _QWORD v18[14]; // [rsp+40h] [rbp-71h] BYREF
  HANDLE EventW; // [rsp+B0h] [rbp-1h] BYREF
  HANDLE Handles[2]; // [rsp+B8h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v16[1] = a3;
  *(_BYTE *)(a1 + 160) = 0;
  ResetEvent(*(HANDLE *)(a1 + 152));
  v18[0] = ___7____func_V_lambda_1___1__WaitForCompletion___WnfAttestationHelper_UMsaTpmKeyState_Autopilot_Windows_Microsoft___Core_Autopilot_ModernDeployment__QEAAJKVcancellation_token_Concurrency__AEAUMsaTpmKeyState_5Windows_Microsoft__AEAW4AttestationState_456__Z___A6AXAEBU95Windows_Microsoft___Z___function_wistd__6B_;
  v18[1] = a1;
  v18[13] = v18;
  v9 = wil::make_wnf_subscription_nothrow<Microsoft::Windows::Autopilot::MsaTpmKeyState>(&v15, a1, v17, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    a1 + 144,
    v9);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v15);
  wistd::function<void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)>::~function<void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)>(v17);
  if ( !*(_QWORD *)(a1 + 144) )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\wnfattestationhelper.cpp",
      (const char *)0x8007000ELL,
      (int)v15);
    pplx::cancellation_token_registration::_Clear(a3);
    return LastError;
  }
  Sleep(0x64u);
  EventW = CreateEventW(0, 1, 0, 0);
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x83,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\wnfattestationhelper.cpp",
                  v12);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&EventW);
    pplx::cancellation_token_registration::_Clear(a3);
    return LastError;
  }
  v16[0] = &EventW;
  ___register_callback_V_lambda_2___1__WaitForCompletion___WnfAttestationHelper_UMsaTpmKeyState_Autopilot_Windows_Microsoft___Core_Autopilot_ModernDeployment__QEAAJKVcancellation_token_Concurrency__AEAUMsaTpmKeyState_5Windows_Microsoft__AEAW4AttestationState_456__Z__cancellation_token_Concurrency__QEBA_AVcancellation_token_registration_1_AEBV_lambda_2___1__WaitForCompletion___WnfAttestationHelper_UMsaTpmKeyState_Autopilot_Windows_Microsoft___Core_Autopilot_ModernDeployment__QEAAJKV01_AEAUMsaTpmKeyState_7Windows_Microsoft__AEAW4AttestationState_678__Z__Z(
    a3,
    &v15,
    v16);
  Handles[0] = *(HANDLE *)(a1 + 152);
  Handles[1] = EventW;
  v13 = WaitForMultipleObjects(2u, Handles, 0, a2);
  if ( v13 )
  {
    *a4 = 0;
    *a5 = 0;
    if ( v13 == 1 )
    {
      LastError = -2147467260;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\wnfattestationhelper.cpp",
        (const char *)0x80004004LL,
        (int)v15);
      if ( v15 )
        Concurrency::details::_RefCounter::_Release(v15);
    }
    else if ( v13 == 258 )
    {
      LastError = -2147023436;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA2,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\wnfattestationhelper.cpp",
        (const char *)0x800705B4LL,
        (int)v15);
      if ( v15 )
        Concurrency::details::_RefCounter::_Release(v15);
    }
    else
    {
      v14 = GetLastError();
      LastError = v14;
      if ( v14 > 0 )
        LastError = (unsigned __int16)v14 | 0x80070000;
      if ( (LastError & 0x80000000) == 0 )
        LastError = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\wnfattestationhelper.cpp",
        (const char *)LastError,
        (int)v15);
      if ( v15 )
        Concurrency::details::_RefCounter::_Release(v15);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&EventW);
    pplx::cancellation_token_registration::_Clear(a3);
    return LastError;
  }
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 176));
  *a4 = *(_QWORD *)(a1 + 164);
  *a5 = *(_DWORD *)(a1 + 172);
  _Mtx_unlock((_Mtx_t)(a1 + 176));
  if ( v15 )
    Concurrency::details::_RefCounter::_Release(v15);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&EventW);
  pplx::cancellation_token_registration::_Clear(a3);
  return 0;
}

```

## disassembly

```asm
0x1801246a4  push    rbp
0x1801246a6  push    rbx
0x1801246a7  push    rsi
0x1801246a8  push    rdi
0x1801246a9  push    r12
0x1801246ab  push    r14
0x1801246ad  push    r15
0x1801246af  lea     rbp, [rsp-1Fh]
0x1801246b4  sub     rsp, 0D0h
0x1801246bb  mov     rax, cs:__security_cookie
0x1801246c2  xor     rax, rsp
0x1801246c5  mov     [rbp+4Fh+var_38], rax
0x1801246c9  mov     r14, r9
0x1801246cc  mov     rdi, r8
0x1801246cf  mov     r12d, edx
0x1801246d2  mov     rsi, rcx
0x1801246d5  mov     [rsp+100h+var_D0], r8
0x1801246da  mov     r15, [rbp+4Fh+arg_20]
0x1801246de  xor     eax, eax
0x1801246e0  xchg    al, [rcx+0A0h]
0x1801246e6  mov     rcx, [rcx+98h]; hEvent
0x1801246ed  call    cs:__imp_ResetEvent
0x1801246f3  lea     rax, ??_7?$__func@V_lambda_1_@?1??WaitForCompletion@?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAAJKVcancellation_token@Concurrency@@AEAUMsaTpmKeyState@5Windows@Microsoft@@AEAW4AttestationState@456@@Z@$$A6AXAEBU95Windows@Microsoft@@@Z@__function@wistd@@6B@; const wistd::__function::__func<`ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(ulong,Concurrency::cancellation_token,Microsoft::Windows::Autopilot::MsaTpmKeyState &,ModernDeployment::Autopilot::Core::AttestationState &)'::`2'::_lambda_1_,void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)>::`vftable'
0x1801246fa  mov     [rbp+4Fh+var_C0], rax
0x1801246fe  mov     [rbp+4Fh+var_B8], rsi
0x180124702  lea     rax, [rbp+4Fh+var_C0]
0x180124706  mov     [rbp+4Fh+var_58], rax
0x18012470a  xor     r9d, r9d
0x18012470d  lea     r8, [rbp+4Fh+var_C8]
0x180124711  mov     rdx, rsi
0x180124714  lea     rcx, [rsp+100h+var_E0]
0x180124719  call    ??$make_wnf_subscription_nothrow@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBUMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Z@wistd@@K@Z; wil::make_wnf_subscription_nothrow<Microsoft::Windows::Autopilot::MsaTpmKeyState>(_WNF_STATE_NAME const &,wistd::function<void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)> &&,ulong)
0x18012471e  lea     rbx, [rsi+90h]
0x180124725  mov     rdx, rax
0x180124728  mov     rcx, rbx
0x18012472b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x180124730  lea     rcx, [rsp+100h+var_E0]
0x180124735  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18012473a  lea     rcx, [rbp+4Fh+var_C8]
0x18012473e  call    ??1?$function@$$A6AXAEBUMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Z@wistd@@QEAA@XZ; wistd::function<void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)>::~function<void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)>(void)
0x180124743  cmp     qword ptr [rbx], 0
0x180124747  jnz     short loc_180124777
0x180124749  mov     rcx, [rbp+57h]; this
0x18012474d  mov     ebx, 8007000Eh
0x180124752  mov     r9d, ebx; char *
0x180124755  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012475c  mov     edx, 7Ch ; '|'; void *
0x180124761  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124766  nop
0x180124767  mov     rcx, rdi; this
0x18012476a  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x18012476f  nop
0x180124770  mov     eax, ebx
0x180124772  jmp     loc_180124975
0x180124777  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18012477c  call    cs:__imp_Sleep
0x180124782  xor     r9d, r9d; lpName
0x180124785  xor     r8d, r8d; bInitialState
0x180124788  lea     edx, [r9+1]; bManualReset
0x18012478c  xor     ecx, ecx; lpEventAttributes
0x18012478e  call    cs:__imp_CreateEventW
0x180124794  mov     [rbp+4Fh+var_50], rax
0x180124798  inc     rax
0x18012479b  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801247a1  jnz     short loc_1801247CF
0x1801247a3  mov     rcx, [rbp+57h]; this
0x1801247a7  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801247ae  mov     edx, 83h; void *
0x1801247b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801247b8  mov     ebx, eax
0x1801247ba  lea     rcx, [rbp+4Fh+var_50]
0x1801247be  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801247c3  nop
0x1801247c4  mov     rcx, rdi; this
0x1801247c7  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x1801247cc  nop
0x1801247cd  jmp     short loc_180124770
0x1801247cf  lea     rax, [rbp+4Fh+var_50]
0x1801247d3  mov     [rsp+100h+var_D8], rax
0x1801247d8  lea     r8, [rsp+100h+var_D8]
0x1801247dd  lea     rdx, [rsp+100h+var_E0]
0x1801247e2  mov     rcx, rdi
0x1801247e5  call    ??$register_callback@V_lambda_2_@?1??WaitForCompletion@?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAAJKVcancellation_token@Concurrency@@AEAUMsaTpmKeyState@5Windows@Microsoft@@AEAW4AttestationState@456@@Z@@cancellation_token@Concurrency@@QEBA?AVcancellation_token_registration@1@AEBV_lambda_2_@?1??WaitForCompletion@?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAAJKV01@AEAUMsaTpmKeyState@7Windows@Microsoft@@AEAW4AttestationState@678@@Z@@Z; Concurrency::cancellation_token::register_callback<`ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(ulong,Concurrency::cancellation_token,Microsoft::Windows::Autopilot::MsaTpmKeyState &,ModernDeployment::Autopilot::Core::AttestationState &)'::`2'::_lambda_2_>(`ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(ulong,Concurrency::cancellation_token,Microsoft::Windows::Autopilot::MsaTpmKeyState &,ModernDeployment::Autopilot::Core::AttestationState &)'::`2'::_lambda_2_ const &)
0x1801247ea  nop
0x1801247eb  mov     rax, [rsi+98h]
0x1801247f2  mov     [rbp+4Fh+Handles], rax
0x1801247f6  mov     rax, [rbp+4Fh+var_50]
0x1801247fa  mov     [rbp+4Fh+var_40], rax
0x1801247fe  mov     r9d, r12d; dwMilliseconds
0x180124801  xor     r8d, r8d; bWaitAll
0x180124804  lea     rdx, [rbp+4Fh+Handles]; lpHandles
0x180124808  lea     ecx, [r8+2]; nCount
0x18012480c  call    cs:__imp_WaitForMultipleObjects
0x180124812  test    eax, eax
0x180124814  jz      loc_180124924
0x18012481a  mov     qword ptr [r14], 0
0x180124821  mov     dword ptr [r15], 0
0x180124828  cmp     eax, 1
0x18012482b  jz      loc_1801248DE
0x180124831  cmp     eax, 102h
0x180124836  jz      short loc_180124898
0x180124838  call    cs:__imp_GetLastError
0x18012483e  mov     ebx, eax
0x180124840  test    eax, eax
0x180124842  jle     short loc_18012484D
0x180124844  movzx   ebx, ax
0x180124847  or      ebx, 80070000h
0x18012484d  mov     eax, 8000FFFFh
0x180124852  test    ebx, ebx
0x180124854  cmovns  ebx, eax
0x180124857  mov     rcx, [rbp+57h]; this
0x18012485b  mov     r9d, ebx; char *
0x18012485e  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x180124865  mov     edx, 0A9h; void *
0x18012486a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012486f  nop
0x180124870  mov     rcx, [rsp+100h+var_E0]; this
0x180124875  test    rcx, rcx
0x180124878  jz      short loc_180124880
0x18012487a  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18012487f  nop
0x180124880  lea     rcx, [rbp+4Fh+var_50]
0x180124884  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180124889  nop
0x18012488a  mov     rcx, rdi; this
0x18012488d  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x180124892  nop
0x180124893  jmp     loc_180124770
0x180124898  mov     rcx, [rbp+57h]; this
0x18012489c  mov     ebx, 800705B4h
0x1801248a1  mov     r9d, ebx; char *
0x1801248a4  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801248ab  mov     edx, 0A2h; void *
0x1801248b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801248b5  nop
0x1801248b6  mov     rcx, [rsp+100h+var_E0]; this
0x1801248bb  test    rcx, rcx
0x1801248be  jz      short loc_1801248C6
0x1801248c0  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x1801248c5  nop
0x1801248c6  lea     rcx, [rbp+4Fh+var_50]
0x1801248ca  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801248cf  nop
0x1801248d0  mov     rcx, rdi; this
0x1801248d3  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x1801248d8  nop
0x1801248d9  jmp     loc_180124770
0x1801248de  mov     rcx, [rbp+57h]; this
0x1801248e2  mov     ebx, 80004004h
0x1801248e7  mov     r9d, ebx; char *
0x1801248ea  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801248f1  mov     edx, 9Dh; void *
0x1801248f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801248fb  nop
0x1801248fc  mov     rcx, [rsp+100h+var_E0]; this
0x180124901  test    rcx, rcx
0x180124904  jz      short loc_18012490C
0x180124906  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18012490b  nop
0x18012490c  lea     rcx, [rbp+4Fh+var_50]
0x180124910  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180124915  nop
0x180124916  mov     rcx, rdi; this
0x180124919  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x18012491e  nop
0x18012491f  jmp     loc_180124770
0x180124924  lea     rbx, [rsi+0B0h]
0x18012492b  mov     rcx, rbx; this
0x18012492e  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180124933  mov     rax, [rsi+0A4h]
0x18012493a  mov     [r14], rax
0x18012493d  mov     eax, [rsi+0ACh]
0x180124943  mov     [r15], eax
0x180124946  mov     rcx, rbx; _Mtx_t
0x180124949  call    cs:__imp__Mtx_unlock
0x18012494f  nop
0x180124950  mov     rcx, [rsp+100h+var_E0]; this
0x180124955  test    rcx, rcx
0x180124958  jz      short loc_180124960
0x18012495a  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18012495f  nop
0x180124960  lea     rcx, [rbp+4Fh+var_50]
0x180124964  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180124969  nop
0x18012496a  mov     rcx, rdi; this
0x18012496d  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x180124972  nop
0x180124973  xor     eax, eax
0x180124975  mov     rcx, [rbp+4Fh+var_38]
0x180124979  xor     rcx, rsp; StackCookie
0x18012497c  call    __security_check_cookie
0x180124981  add     rsp, 0D0h
0x180124988  pop     r15
0x18012498a  pop     r14
0x18012498c  pop     r12
0x18012498e  pop     rdi
0x18012498f  pop     rsi
0x180124990  pop     rbx
0x180124991  pop     rbp
0x180124992  retn
```
