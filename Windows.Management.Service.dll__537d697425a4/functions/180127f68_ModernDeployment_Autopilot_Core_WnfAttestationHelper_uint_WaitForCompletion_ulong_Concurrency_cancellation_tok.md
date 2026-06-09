# ModernDeployment::Autopilot::Core::WnfAttestationHelper<uint>::WaitForCompletion(ulong,Concurrency::cancellation_token,uint &,ModernDeployment::Autopilot::Core::AttestationState &)

- ea: `0x180127f68`
- end: `0x180128292`
- name: `?WaitForCompletion@?$WnfAttestationHelper@I@Core@Autopilot@ModernDeployment@@QEAAJKVcancellation_token@Concurrency@@AEAIAEAW4AttestationState@234@@Z`
- size: `810`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180125484`

## callees

- `0x18000b8f0`
- `0x180067e34`
- `0x180067e54`
- `0x18006e484`
- `0x18006e670`
- `0x18008e088`
- `0x1800966b8`
- `0x1800b34e0`
- `0x1800dab90`
- `0x18011c1e0`
- `0x180127830`
- `0x1801279e4`
- `0x180127f68`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18012805d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18012805d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180128075`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180128075`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180127fb1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180127fb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012812b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012812b`
- `msvcp_win!_Mtx_unlock` at `0x180128241`
- `msvcp_win!_Mtx_unlock` at `0x180128241`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1801280f9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1801280f9`

## string_xrefs

- `0x180128036`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x180128094`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x180128157`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x18012819d`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x1801281e3`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ModernDeployment::Autopilot::Core::WnfAttestationHelper<unsigned int>::WaitForCompletion(
        __int64 a1,
        DWORD a2,
        pplx::cancellation_token_registration *a3,
        _DWORD *a4,
        _DWORD *a5)
{
  __int64 v9; // r8
  int wnf_subscription; // eax
  Concurrency::details::_RefCounter *v11; // rcx
  unsigned int LastError; // ebx
  const char *v14; // r9
  DWORD v15; // eax
  signed int v16; // eax
  Concurrency::details::_RefCounter *v17; // [rsp+20h] [rbp-91h] BYREF
  _QWORD v18[2]; // [rsp+28h] [rbp-89h] BYREF
  _BYTE v19[8]; // [rsp+38h] [rbp-79h] BYREF
  _QWORD v20[14]; // [rsp+40h] [rbp-71h] BYREF
  HANDLE EventW; // [rsp+B0h] [rbp-1h] BYREF
  HANDLE Handles[2]; // [rsp+B8h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v18[1] = a3;
  *(_BYTE *)(a1 + 160) = 0;
  ResetEvent(*(HANDLE *)(a1 + 152));
  v20[0] = wistd::__function::Z::$$A6AXAEBI::Z::__func<`ModernDeployment::Autopilot::Core::WnfAttestationHelper<unsigned int>::WaitForCompletion'::`2'::_lambda_1_,Concurrency::AJKVcancellation_token * const,unsigned int &,enum ModernDeployment::Autopilot::Core::AttestationState &>::`vftable';
  v20[1] = a1;
  v20[13] = v20;
  v17 = 0;
  wnf_subscription = wil::details::make_wnf_subscription_state<unsigned int>(a1, v19, v9, &v17);
  v11 = 0;
  if ( wnf_subscription >= 0 )
    v11 = v17;
  v17 = v11;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    a1 + 144,
    &v17);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v17);
  wistd::function<void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)>::~function<void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)>(v19);
  if ( !*(_QWORD *)(a1 + 144) )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\wnfattestationhelper.cpp",
      (const char *)0x8007000ELL,
      (int)v17);
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
                  v14);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&EventW);
    pplx::cancellation_token_registration::_Clear(a3);
    return LastError;
  }
  v18[0] = &EventW;
  ___register_callback_V_lambda_2___1__WaitForCompletion___WnfAttestationHelper_UMsaTpmKeyState_Autopilot_Windows_Microsoft___Core_Autopilot_ModernDeployment__QEAAJKVcancellation_token_Concurrency__AEAUMsaTpmKeyState_5Windows_Microsoft__AEAW4AttestationState_456__Z__cancellation_token_Concurrency__QEBA_AVcancellation_token_registration_1_AEBV_lambda_2___1__WaitForCompletion___WnfAttestationHelper_UMsaTpmKeyState_Autopilot_Windows_Microsoft___Core_Autopilot_ModernDeployment__QEAAJKV01_AEAUMsaTpmKeyState_7Windows_Microsoft__AEAW4AttestationState_678__Z__Z(
    a3,
    &v17,
    v18);
  Handles[0] = *(HANDLE *)(a1 + 152);
  Handles[1] = EventW;
  v15 = WaitForMultipleObjects(2u, Handles, 0, a2);
  if ( v15 )
  {
    *a4 = 0;
    *a5 = 0;
    if ( v15 == 1 )
    {
      LastError = -2147467260;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\wnfattestationhelper.cpp",
        (const char *)0x80004004LL,
        (int)v17);
      if ( v17 )
        Concurrency::details::_RefCounter::_Release(v17);
    }
    else if ( v15 == 258 )
    {
      LastError = -2147023436;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA2,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\wnfattestationhelper.cpp",
        (const char *)0x800705B4LL,
        (int)v17);
      if ( v17 )
        Concurrency::details::_RefCounter::_Release(v17);
    }
    else
    {
      v16 = GetLastError();
      LastError = v16;
      if ( v16 > 0 )
        LastError = (unsigned __int16)v16 | 0x80070000;
      if ( (LastError & 0x80000000) == 0 )
        LastError = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\wnfattestationhelper.cpp",
        (const char *)LastError,
        (int)v17);
      if ( v17 )
        Concurrency::details::_RefCounter::_Release(v17);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&EventW);
    pplx::cancellation_token_registration::_Clear(a3);
    return LastError;
  }
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 176));
  *a4 = *(_DWORD *)(a1 + 164);
  *a5 = *(_DWORD *)(a1 + 168);
  _Mtx_unlock((_Mtx_t)(a1 + 176));
  if ( v17 )
    Concurrency::details::_RefCounter::_Release(v17);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&EventW);
  pplx::cancellation_token_registration::_Clear(a3);
  return 0;
}

```

## disassembly

```asm
0x180127f68  push    rbp
0x180127f6a  push    rbx
0x180127f6b  push    rsi
0x180127f6c  push    rdi
0x180127f6d  push    r12
0x180127f6f  push    r14
0x180127f71  push    r15
0x180127f73  lea     rbp, [rsp-1Fh]
0x180127f78  sub     rsp, 0D0h
0x180127f7f  mov     rax, cs:__security_cookie
0x180127f86  xor     rax, rsp
0x180127f89  mov     [rbp+4Fh+var_38], rax
0x180127f8d  mov     r14, r9
0x180127f90  mov     rdi, r8
0x180127f93  mov     r12d, edx
0x180127f96  mov     rsi, rcx
0x180127f99  mov     [rsp+100h+var_D0], r8
0x180127f9e  mov     r15, [rbp+4Fh+arg_20]
0x180127fa2  xor     eax, eax
0x180127fa4  xchg    al, [rcx+0A0h]
0x180127faa  mov     rcx, [rcx+98h]; hEvent
0x180127fb1  call    cs:__imp_ResetEvent
0x180127fb8  nop     dword ptr [rax+rax+00h]
0x180127fbd  lea     rax, ??_7?$__func@V_lambda_1_@?1??WaitForCompletion@?$WnfAttestationHelper@I@Core@Autopilot@ModernDeployment@@QEAAJKVcancellation_token@Concurrency@@AEAIAEAW4AttestationState@456@@Z@$$A6AXAEBI@Z@__function@wistd@@6B@; const wistd::__function::__func<`ModernDeployment::Autopilot::Core::WnfAttestationHelper<uint>::WaitForCompletion(ulong,Concurrency::cancellation_token,uint &,ModernDeployment::Autopilot::Core::AttestationState &)'::`2'::_lambda_1_,void (uint const &)>::`vftable'
0x180127fc4  mov     [rbp+4Fh+var_C0], rax
0x180127fc8  mov     [rbp+4Fh+var_B8], rsi
0x180127fcc  lea     rax, [rbp+4Fh+var_C0]
0x180127fd0  mov     [rbp+4Fh+var_58], rax
0x180127fd4  mov     [rsp+100h+var_E0], 0
0x180127fdd  lea     r9, [rsp+100h+var_E0]
0x180127fe2  lea     rdx, [rbp+4Fh+var_C8]
0x180127fe6  mov     rcx, rsi
0x180127fe9  call    ??$make_wnf_subscription_state@I@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBI@Z@wistd@@KPEAPEAU?$wnf_subscription_state@I@01@@Z; wil::details::make_wnf_subscription_state<uint>(_WNF_STATE_NAME const &,wistd::function<void (uint const &)> &&,ulong,wil::details::wnf_subscription_state<uint> * *)
0x180127fee  xor     ecx, ecx
0x180127ff0  test    eax, eax
0x180127ff2  cmovns  rcx, [rsp+100h+var_E0]
0x180127ff8  mov     [rsp+100h+var_E0], rcx; int
0x180127ffd  lea     rbx, [rsi+90h]
0x180128004  lea     rdx, [rsp+100h+var_E0]
0x180128009  mov     rcx, rbx
0x18012800c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x180128011  lea     rcx, [rsp+100h+var_E0]
0x180128016  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18012801b  lea     rcx, [rbp+4Fh+var_C8]
0x18012801f  call    ??1?$function@$$A6AXAEBUMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Z@wistd@@QEAA@XZ; wistd::function<void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)>::~function<void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)>(void)
0x180128024  cmp     qword ptr [rbx], 0
0x180128028  jnz     short loc_180128058
0x18012802a  mov     rcx, [rbp+57h]; this
0x18012802e  mov     ebx, 8007000Eh
0x180128033  mov     r9d, ebx; char *
0x180128036  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012803d  mov     edx, 7Ch ; '|'; void *
0x180128042  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180128047  nop
0x180128048  mov     rcx, rdi; this
0x18012804b  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x180128050  nop
0x180128051  mov     eax, ebx
0x180128053  jmp     loc_180128273
0x180128058  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18012805d  call    cs:__imp_Sleep
0x180128064  nop     dword ptr [rax+rax+00h]
0x180128069  xor     r9d, r9d; lpName
0x18012806c  xor     r8d, r8d; bInitialState
0x18012806f  lea     edx, [r9+1]; bManualReset
0x180128073  xor     ecx, ecx; lpEventAttributes
0x180128075  call    cs:__imp_CreateEventW
0x18012807c  nop     dword ptr [rax+rax+00h]
0x180128081  mov     [rbp+4Fh+var_50], rax
0x180128085  inc     rax
0x180128088  test    rax, 0FFFFFFFFFFFFFFFEh
0x18012808e  jnz     short loc_1801280BC
0x180128090  mov     rcx, [rbp+57h]; this
0x180128094  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012809b  mov     edx, 83h; void *
0x1801280a0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801280a5  mov     ebx, eax
0x1801280a7  lea     rcx, [rbp+4Fh+var_50]
0x1801280ab  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801280b0  nop
0x1801280b1  mov     rcx, rdi; this
0x1801280b4  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x1801280b9  nop
0x1801280ba  jmp     short loc_180128051
0x1801280bc  lea     rax, [rbp+4Fh+var_50]
0x1801280c0  mov     [rsp+100h+var_D8], rax
0x1801280c5  lea     r8, [rsp+100h+var_D8]
0x1801280ca  lea     rdx, [rsp+100h+var_E0]
0x1801280cf  mov     rcx, rdi
0x1801280d2  call    ??$register_callback@V_lambda_2_@?1??WaitForCompletion@?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAAJKVcancellation_token@Concurrency@@AEAUMsaTpmKeyState@5Windows@Microsoft@@AEAW4AttestationState@456@@Z@@cancellation_token@Concurrency@@QEBA?AVcancellation_token_registration@1@AEBV_lambda_2_@?1??WaitForCompletion@?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAAJKV01@AEAUMsaTpmKeyState@7Windows@Microsoft@@AEAW4AttestationState@678@@Z@@Z; Concurrency::cancellation_token::register_callback<`ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(ulong,Concurrency::cancellation_token,Microsoft::Windows::Autopilot::MsaTpmKeyState &,ModernDeployment::Autopilot::Core::AttestationState &)'::`2'::_lambda_2_>(`ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(ulong,Concurrency::cancellation_token,Microsoft::Windows::Autopilot::MsaTpmKeyState &,ModernDeployment::Autopilot::Core::AttestationState &)'::`2'::_lambda_2_ const &)
0x1801280d7  nop
0x1801280d8  mov     rax, [rsi+98h]
0x1801280df  mov     [rbp+4Fh+Handles], rax
0x1801280e3  mov     rax, [rbp+4Fh+var_50]
0x1801280e7  mov     [rbp+4Fh+var_40], rax
0x1801280eb  mov     r9d, r12d; dwMilliseconds
0x1801280ee  xor     r8d, r8d; bWaitAll
0x1801280f1  lea     rdx, [rbp+4Fh+Handles]; lpHandles
0x1801280f5  lea     ecx, [r8+2]; nCount
0x1801280f9  call    cs:__imp_WaitForMultipleObjects
0x180128100  nop     dword ptr [rax+rax+00h]
0x180128105  test    eax, eax
0x180128107  jz      loc_18012821D
0x18012810d  mov     dword ptr [r14], 0
0x180128114  mov     dword ptr [r15], 0
0x18012811b  cmp     eax, 1
0x18012811e  jz      loc_1801281D7
0x180128124  cmp     eax, 102h
0x180128129  jz      short loc_180128191
0x18012812b  call    cs:__imp_GetLastError
0x180128132  nop     dword ptr [rax+rax+00h]
0x180128137  mov     ebx, eax
0x180128139  test    eax, eax
0x18012813b  jle     short loc_180128146
0x18012813d  movzx   ebx, ax
0x180128140  or      ebx, 80070000h
0x180128146  mov     eax, 8000FFFFh
0x18012814b  test    ebx, ebx
0x18012814d  cmovns  ebx, eax
0x180128150  mov     rcx, [rbp+57h]; this
0x180128154  mov     r9d, ebx; char *
0x180128157  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012815e  mov     edx, 0A9h; void *
0x180128163  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180128168  nop
0x180128169  mov     rcx, [rsp+100h+var_E0]; this
0x18012816e  test    rcx, rcx
0x180128171  jz      short loc_180128179
0x180128173  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x180128178  nop
0x180128179  lea     rcx, [rbp+4Fh+var_50]
0x18012817d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180128182  nop
0x180128183  mov     rcx, rdi; this
0x180128186  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x18012818b  nop
0x18012818c  jmp     loc_180128051
0x180128191  mov     rcx, [rbp+57h]; this
0x180128195  mov     ebx, 800705B4h
0x18012819a  mov     r9d, ebx; char *
0x18012819d  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801281a4  mov     edx, 0A2h; void *
0x1801281a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801281ae  nop
0x1801281af  mov     rcx, [rsp+100h+var_E0]; this
0x1801281b4  test    rcx, rcx
0x1801281b7  jz      short loc_1801281BF
0x1801281b9  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x1801281be  nop
0x1801281bf  lea     rcx, [rbp+4Fh+var_50]
0x1801281c3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801281c8  nop
0x1801281c9  mov     rcx, rdi; this
0x1801281cc  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x1801281d1  nop
0x1801281d2  jmp     loc_180128051
0x1801281d7  mov     rcx, [rbp+57h]; this
0x1801281db  mov     ebx, 80004004h
0x1801281e0  mov     r9d, ebx; char *
0x1801281e3  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801281ea  mov     edx, 9Dh; void *
0x1801281ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801281f4  nop
0x1801281f5  mov     rcx, [rsp+100h+var_E0]; this
0x1801281fa  test    rcx, rcx
0x1801281fd  jz      short loc_180128205
0x1801281ff  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x180128204  nop
0x180128205  lea     rcx, [rbp+4Fh+var_50]
0x180128209  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18012820e  nop
0x18012820f  mov     rcx, rdi; this
0x180128212  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x180128217  nop
0x180128218  jmp     loc_180128051
0x18012821d  lea     rbx, [rsi+0B0h]
0x180128224  mov     rcx, rbx; this
0x180128227  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18012822c  mov     eax, [rsi+0A4h]
0x180128232  mov     [r14], eax
0x180128235  mov     eax, [rsi+0A8h]
0x18012823b  mov     [r15], eax
0x18012823e  mov     rcx, rbx; _Mtx_t
0x180128241  call    cs:__imp__Mtx_unlock
0x180128248  nop     dword ptr [rax+rax+00h]
0x18012824d  nop
0x18012824e  mov     rcx, [rsp+100h+var_E0]; this
0x180128253  test    rcx, rcx
0x180128256  jz      short loc_18012825E
0x180128258  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18012825d  nop
0x18012825e  lea     rcx, [rbp+4Fh+var_50]
0x180128262  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180128267  nop
0x180128268  mov     rcx, rdi; this
0x18012826b  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x180128270  nop
0x180128271  xor     eax, eax
0x180128273  mov     rcx, [rbp+4Fh+var_38]
0x180128277  xor     rcx, rsp; StackCookie
0x18012827a  call    __security_check_cookie
0x18012827f  add     rsp, 0D0h
0x180128286  pop     r15
0x180128288  pop     r14
0x18012828a  pop     r12
0x18012828c  pop     rdi
0x18012828d  pop     rsi
0x18012828e  pop     rbx
0x18012828f  pop     rbp
0x180128290  retn
```
