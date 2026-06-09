# ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(ulong,Concurrency::cancellation_token,Microsoft::Windows::Autopilot::MsaTpmKeyState &,ModernDeployment::Autopilot::Core::AttestationState &)

- ea: `0x180128298`
- end: `0x1801285ac`
- name: `?WaitForCompletion@?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAAJKVcancellation_token@Concurrency@@AEAUMsaTpmKeyState@3Windows@Microsoft@@AEAW4AttestationState@234@@Z`
- size: `788`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180126cd0`

## callees

- `0x18000b8f0`
- `0x180067e34`
- `0x180067e54`
- `0x18006e484`
- `0x18006e670`
- `0x18008e088`
- `0x1800966b8`
- `0x1800b34e0`
- `0x1800d1304`
- `0x1800dab90`
- `0x18011c1e0`
- `0x1801279e4`
- `0x180128298`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180128376`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180128376`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012838e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012838e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801282e1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801282e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180128444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180128444`
- `msvcp_win!_Mtx_unlock` at `0x18012855b`
- `msvcp_win!_Mtx_unlock` at `0x18012855b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180128412`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180128412`

## string_xrefs

- `0x18012834f`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x1801283ad`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x180128470`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x1801284b6`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x1801284fc`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`

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
0x180128298  push    rbp
0x18012829a  push    rbx
0x18012829b  push    rsi
0x18012829c  push    rdi
0x18012829d  push    r12
0x18012829f  push    r14
0x1801282a1  push    r15
0x1801282a3  lea     rbp, [rsp-1Fh]
0x1801282a8  sub     rsp, 0D0h
0x1801282af  mov     rax, cs:__security_cookie
0x1801282b6  xor     rax, rsp
0x1801282b9  mov     [rbp+4Fh+var_38], rax
0x1801282bd  mov     r14, r9
0x1801282c0  mov     rdi, r8
0x1801282c3  mov     r12d, edx
0x1801282c6  mov     rsi, rcx
0x1801282c9  mov     [rsp+100h+var_D0], r8
0x1801282ce  mov     r15, [rbp+4Fh+arg_20]
0x1801282d2  xor     eax, eax
0x1801282d4  xchg    al, [rcx+0A0h]
0x1801282da  mov     rcx, [rcx+98h]; hEvent
0x1801282e1  call    cs:__imp_ResetEvent
0x1801282e8  nop     dword ptr [rax+rax+00h]
0x1801282ed  lea     rax, ??_7?$__func@V_lambda_1_@?1??WaitForCompletion@?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAAJKVcancellation_token@Concurrency@@AEAUMsaTpmKeyState@5Windows@Microsoft@@AEAW4AttestationState@456@@Z@$$A6AXAEBU95Windows@Microsoft@@@Z@__function@wistd@@6B@; const wistd::__function::__func<`ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(ulong,Concurrency::cancellation_token,Microsoft::Windows::Autopilot::MsaTpmKeyState &,ModernDeployment::Autopilot::Core::AttestationState &)'::`2'::_lambda_1_,void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)>::`vftable'
0x1801282f4  mov     [rbp+4Fh+var_C0], rax
0x1801282f8  mov     [rbp+4Fh+var_B8], rsi
0x1801282fc  lea     rax, [rbp+4Fh+var_C0]
0x180128300  mov     [rbp+4Fh+var_58], rax
0x180128304  xor     r9d, r9d
0x180128307  lea     r8, [rbp+4Fh+var_C8]
0x18012830b  mov     rdx, rsi
0x18012830e  lea     rcx, [rsp+100h+var_E0]
0x180128313  call    ??$make_wnf_subscription_nothrow@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBUMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Z@wistd@@K@Z; wil::make_wnf_subscription_nothrow<Microsoft::Windows::Autopilot::MsaTpmKeyState>(_WNF_STATE_NAME const &,wistd::function<void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)> &&,ulong)
0x180128318  lea     rbx, [rsi+90h]
0x18012831f  mov     rdx, rax
0x180128322  mov     rcx, rbx
0x180128325  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18012832a  lea     rcx, [rsp+100h+var_E0]
0x18012832f  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180128334  lea     rcx, [rbp+4Fh+var_C8]
0x180128338  call    ??1?$function@$$A6AXAEBUMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Z@wistd@@QEAA@XZ; wistd::function<void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)>::~function<void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)>(void)
0x18012833d  cmp     qword ptr [rbx], 0
0x180128341  jnz     short loc_180128371
0x180128343  mov     rcx, [rbp+57h]; this
0x180128347  mov     ebx, 8007000Eh
0x18012834c  mov     r9d, ebx; char *
0x18012834f  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x180128356  mov     edx, 7Ch ; '|'; void *
0x18012835b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180128360  nop
0x180128361  mov     rcx, rdi; this
0x180128364  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x180128369  nop
0x18012836a  mov     eax, ebx
0x18012836c  jmp     loc_18012858D
0x180128371  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180128376  call    cs:__imp_Sleep
0x18012837d  nop     dword ptr [rax+rax+00h]
0x180128382  xor     r9d, r9d; lpName
0x180128385  xor     r8d, r8d; bInitialState
0x180128388  lea     edx, [r9+1]; bManualReset
0x18012838c  xor     ecx, ecx; lpEventAttributes
0x18012838e  call    cs:__imp_CreateEventW
0x180128395  nop     dword ptr [rax+rax+00h]
0x18012839a  mov     [rbp+4Fh+var_50], rax
0x18012839e  inc     rax
0x1801283a1  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801283a7  jnz     short loc_1801283D5
0x1801283a9  mov     rcx, [rbp+57h]; this
0x1801283ad  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801283b4  mov     edx, 83h; void *
0x1801283b9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801283be  mov     ebx, eax
0x1801283c0  lea     rcx, [rbp+4Fh+var_50]
0x1801283c4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801283c9  nop
0x1801283ca  mov     rcx, rdi; this
0x1801283cd  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x1801283d2  nop
0x1801283d3  jmp     short loc_18012836A
0x1801283d5  lea     rax, [rbp+4Fh+var_50]
0x1801283d9  mov     [rsp+100h+var_D8], rax
0x1801283de  lea     r8, [rsp+100h+var_D8]
0x1801283e3  lea     rdx, [rsp+100h+var_E0]
0x1801283e8  mov     rcx, rdi
0x1801283eb  call    ??$register_callback@V_lambda_2_@?1??WaitForCompletion@?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAAJKVcancellation_token@Concurrency@@AEAUMsaTpmKeyState@5Windows@Microsoft@@AEAW4AttestationState@456@@Z@@cancellation_token@Concurrency@@QEBA?AVcancellation_token_registration@1@AEBV_lambda_2_@?1??WaitForCompletion@?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAAJKV01@AEAUMsaTpmKeyState@7Windows@Microsoft@@AEAW4AttestationState@678@@Z@@Z; Concurrency::cancellation_token::register_callback<`ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(ulong,Concurrency::cancellation_token,Microsoft::Windows::Autopilot::MsaTpmKeyState &,ModernDeployment::Autopilot::Core::AttestationState &)'::`2'::_lambda_2_>(`ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(ulong,Concurrency::cancellation_token,Microsoft::Windows::Autopilot::MsaTpmKeyState &,ModernDeployment::Autopilot::Core::AttestationState &)'::`2'::_lambda_2_ const &)
0x1801283f0  nop
0x1801283f1  mov     rax, [rsi+98h]
0x1801283f8  mov     [rbp+4Fh+Handles], rax
0x1801283fc  mov     rax, [rbp+4Fh+var_50]
0x180128400  mov     [rbp+4Fh+var_40], rax
0x180128404  mov     r9d, r12d; dwMilliseconds
0x180128407  xor     r8d, r8d; bWaitAll
0x18012840a  lea     rdx, [rbp+4Fh+Handles]; lpHandles
0x18012840e  lea     ecx, [r8+2]; nCount
0x180128412  call    cs:__imp_WaitForMultipleObjects
0x180128419  nop     dword ptr [rax+rax+00h]
0x18012841e  test    eax, eax
0x180128420  jz      loc_180128536
0x180128426  mov     qword ptr [r14], 0
0x18012842d  mov     dword ptr [r15], 0
0x180128434  cmp     eax, 1
0x180128437  jz      loc_1801284F0
0x18012843d  cmp     eax, 102h
0x180128442  jz      short loc_1801284AA
0x180128444  call    cs:__imp_GetLastError
0x18012844b  nop     dword ptr [rax+rax+00h]
0x180128450  mov     ebx, eax
0x180128452  test    eax, eax
0x180128454  jle     short loc_18012845F
0x180128456  movzx   ebx, ax
0x180128459  or      ebx, 80070000h
0x18012845f  mov     eax, 8000FFFFh
0x180128464  test    ebx, ebx
0x180128466  cmovns  ebx, eax
0x180128469  mov     rcx, [rbp+57h]; this
0x18012846d  mov     r9d, ebx; char *
0x180128470  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x180128477  mov     edx, 0A9h; void *
0x18012847c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180128481  nop
0x180128482  mov     rcx, [rsp+100h+var_E0]; this
0x180128487  test    rcx, rcx
0x18012848a  jz      short loc_180128492
0x18012848c  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x180128491  nop
0x180128492  lea     rcx, [rbp+4Fh+var_50]
0x180128496  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18012849b  nop
0x18012849c  mov     rcx, rdi; this
0x18012849f  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x1801284a4  nop
0x1801284a5  jmp     loc_18012836A
0x1801284aa  mov     rcx, [rbp+57h]; this
0x1801284ae  mov     ebx, 800705B4h
0x1801284b3  mov     r9d, ebx; char *
0x1801284b6  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801284bd  mov     edx, 0A2h; void *
0x1801284c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801284c7  nop
0x1801284c8  mov     rcx, [rsp+100h+var_E0]; this
0x1801284cd  test    rcx, rcx
0x1801284d0  jz      short loc_1801284D8
0x1801284d2  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x1801284d7  nop
0x1801284d8  lea     rcx, [rbp+4Fh+var_50]
0x1801284dc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801284e1  nop
0x1801284e2  mov     rcx, rdi; this
0x1801284e5  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x1801284ea  nop
0x1801284eb  jmp     loc_18012836A
0x1801284f0  mov     rcx, [rbp+57h]; this
0x1801284f4  mov     ebx, 80004004h
0x1801284f9  mov     r9d, ebx; char *
0x1801284fc  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x180128503  mov     edx, 9Dh; void *
0x180128508  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012850d  nop
0x18012850e  mov     rcx, [rsp+100h+var_E0]; this
0x180128513  test    rcx, rcx
0x180128516  jz      short loc_18012851E
0x180128518  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18012851d  nop
0x18012851e  lea     rcx, [rbp+4Fh+var_50]
0x180128522  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180128527  nop
0x180128528  mov     rcx, rdi; this
0x18012852b  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x180128530  nop
0x180128531  jmp     loc_18012836A
0x180128536  lea     rbx, [rsi+0B0h]
0x18012853d  mov     rcx, rbx; this
0x180128540  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180128545  mov     rax, [rsi+0A4h]
0x18012854c  mov     [r14], rax
0x18012854f  mov     eax, [rsi+0ACh]
0x180128555  mov     [r15], eax
0x180128558  mov     rcx, rbx; _Mtx_t
0x18012855b  call    cs:__imp__Mtx_unlock
0x180128562  nop     dword ptr [rax+rax+00h]
0x180128567  nop
0x180128568  mov     rcx, [rsp+100h+var_E0]; this
0x18012856d  test    rcx, rcx
0x180128570  jz      short loc_180128578
0x180128572  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x180128577  nop
0x180128578  lea     rcx, [rbp+4Fh+var_50]
0x18012857c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180128581  nop
0x180128582  mov     rcx, rdi; this
0x180128585  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x18012858a  nop
0x18012858b  xor     eax, eax
0x18012858d  mov     rcx, [rbp+4Fh+var_38]
0x180128591  xor     rcx, rsp; StackCookie
0x180128594  call    __security_check_cookie
0x180128599  add     rsp, 0D0h
0x1801285a0  pop     r15
0x1801285a2  pop     r14
0x1801285a4  pop     r12
0x1801285a6  pop     rdi
0x1801285a7  pop     rsi
0x1801285a8  pop     rbx
0x1801285a9  pop     rbp
0x1801285aa  retn
```
