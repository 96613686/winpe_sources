# ModernDeployment::Autopilot::Core::WnfAttestationHelper<uint>::WaitForCompletion(ulong,Concurrency::cancellation_token,uint &,ModernDeployment::Autopilot::Core::AttestationState &)

- ea: `0x180124398`
- end: `0x18012469d`
- name: `?WaitForCompletion@?$WnfAttestationHelper@I@Core@Autopilot@ModernDeployment@@QEAAJKVcancellation_token@Concurrency@@AEAIAEAW4AttestationState@234@@Z`
- size: `773`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801219bc`

## callees

- `0x18000b820`
- `0x180067a34`
- `0x180067a54`
- `0x18006df3c`
- `0x18006e104`
- `0x18008cfa4`
- `0x1800953b4`
- `0x1800b1998`
- `0x1800d8480`
- `0x180118938`
- `0x180123ca8`
- `0x180123e4c`
- `0x180124398`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180124487`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180124487`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180124499`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180124499`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801243e1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801243e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180124543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180124543`
- `msvcp_win!_Mtx_unlock` at `0x180124653`
- `msvcp_win!_Mtx_unlock` at `0x180124653`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180124517`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180124517`

## string_xrefs

- `0x180124460`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x1801244b2`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x180124569`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x1801245af`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`
- `0x1801245f5`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\wnfattestationhelper.cpp`

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
0x180124398  push    rbp
0x18012439a  push    rbx
0x18012439b  push    rsi
0x18012439c  push    rdi
0x18012439d  push    r12
0x18012439f  push    r14
0x1801243a1  push    r15
0x1801243a3  lea     rbp, [rsp-1Fh]
0x1801243a8  sub     rsp, 0D0h
0x1801243af  mov     rax, cs:__security_cookie
0x1801243b6  xor     rax, rsp
0x1801243b9  mov     [rbp+4Fh+var_38], rax
0x1801243bd  mov     r14, r9
0x1801243c0  mov     rdi, r8
0x1801243c3  mov     r12d, edx
0x1801243c6  mov     rsi, rcx
0x1801243c9  mov     [rsp+100h+var_D0], r8
0x1801243ce  mov     r15, [rbp+4Fh+arg_20]
0x1801243d2  xor     eax, eax
0x1801243d4  xchg    al, [rcx+0A0h]
0x1801243da  mov     rcx, [rcx+98h]; hEvent
0x1801243e1  call    cs:__imp_ResetEvent
0x1801243e7  lea     rax, ??_7?$__func@V_lambda_1_@?1??WaitForCompletion@?$WnfAttestationHelper@I@Core@Autopilot@ModernDeployment@@QEAAJKVcancellation_token@Concurrency@@AEAIAEAW4AttestationState@456@@Z@$$A6AXAEBI@Z@__function@wistd@@6B@; const wistd::__function::__func<`ModernDeployment::Autopilot::Core::WnfAttestationHelper<uint>::WaitForCompletion(ulong,Concurrency::cancellation_token,uint &,ModernDeployment::Autopilot::Core::AttestationState &)'::`2'::_lambda_1_,void (uint const &)>::`vftable'
0x1801243ee  mov     [rbp+4Fh+var_C0], rax
0x1801243f2  mov     [rbp+4Fh+var_B8], rsi
0x1801243f6  lea     rax, [rbp+4Fh+var_C0]
0x1801243fa  mov     [rbp+4Fh+var_58], rax
0x1801243fe  mov     [rsp+100h+var_E0], 0
0x180124407  lea     r9, [rsp+100h+var_E0]
0x18012440c  lea     rdx, [rbp+4Fh+var_C8]
0x180124410  mov     rcx, rsi
0x180124413  call    ??$make_wnf_subscription_state@I@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBI@Z@wistd@@KPEAPEAU?$wnf_subscription_state@I@01@@Z; wil::details::make_wnf_subscription_state<uint>(_WNF_STATE_NAME const &,wistd::function<void (uint const &)> &&,ulong,wil::details::wnf_subscription_state<uint> * *)
0x180124418  xor     ecx, ecx
0x18012441a  test    eax, eax
0x18012441c  cmovns  rcx, [rsp+100h+var_E0]
0x180124422  mov     [rsp+100h+var_E0], rcx; int
0x180124427  lea     rbx, [rsi+90h]
0x18012442e  lea     rdx, [rsp+100h+var_E0]
0x180124433  mov     rcx, rbx
0x180124436  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18012443b  lea     rcx, [rsp+100h+var_E0]
0x180124440  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180124445  lea     rcx, [rbp+4Fh+var_C8]
0x180124449  call    ??1?$function@$$A6AXAEBUMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Z@wistd@@QEAA@XZ; wistd::function<void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)>::~function<void (Microsoft::Windows::Autopilot::MsaTpmKeyState const &)>(void)
0x18012444e  cmp     qword ptr [rbx], 0
0x180124452  jnz     short loc_180124482
0x180124454  mov     rcx, [rbp+57h]; this
0x180124458  mov     ebx, 8007000Eh
0x18012445d  mov     r9d, ebx; char *
0x180124460  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x180124467  mov     edx, 7Ch ; '|'; void *
0x18012446c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124471  nop
0x180124472  mov     rcx, rdi; this
0x180124475  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x18012447a  nop
0x18012447b  mov     eax, ebx
0x18012447d  jmp     loc_18012467F
0x180124482  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180124487  call    cs:__imp_Sleep
0x18012448d  xor     r9d, r9d; lpName
0x180124490  xor     r8d, r8d; bInitialState
0x180124493  lea     edx, [r9+1]; bManualReset
0x180124497  xor     ecx, ecx; lpEventAttributes
0x180124499  call    cs:__imp_CreateEventW
0x18012449f  mov     [rbp+4Fh+var_50], rax
0x1801244a3  inc     rax
0x1801244a6  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801244ac  jnz     short loc_1801244DA
0x1801244ae  mov     rcx, [rbp+57h]; this
0x1801244b2  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801244b9  mov     edx, 83h; void *
0x1801244be  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801244c3  mov     ebx, eax
0x1801244c5  lea     rcx, [rbp+4Fh+var_50]
0x1801244c9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801244ce  nop
0x1801244cf  mov     rcx, rdi; this
0x1801244d2  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x1801244d7  nop
0x1801244d8  jmp     short loc_18012447B
0x1801244da  lea     rax, [rbp+4Fh+var_50]
0x1801244de  mov     [rsp+100h+var_D8], rax
0x1801244e3  lea     r8, [rsp+100h+var_D8]
0x1801244e8  lea     rdx, [rsp+100h+var_E0]
0x1801244ed  mov     rcx, rdi
0x1801244f0  call    ??$register_callback@V_lambda_2_@?1??WaitForCompletion@?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAAJKVcancellation_token@Concurrency@@AEAUMsaTpmKeyState@5Windows@Microsoft@@AEAW4AttestationState@456@@Z@@cancellation_token@Concurrency@@QEBA?AVcancellation_token_registration@1@AEBV_lambda_2_@?1??WaitForCompletion@?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAAJKV01@AEAUMsaTpmKeyState@7Windows@Microsoft@@AEAW4AttestationState@678@@Z@@Z; Concurrency::cancellation_token::register_callback<`ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(ulong,Concurrency::cancellation_token,Microsoft::Windows::Autopilot::MsaTpmKeyState &,ModernDeployment::Autopilot::Core::AttestationState &)'::`2'::_lambda_2_>(`ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(ulong,Concurrency::cancellation_token,Microsoft::Windows::Autopilot::MsaTpmKeyState &,ModernDeployment::Autopilot::Core::AttestationState &)'::`2'::_lambda_2_ const &)
0x1801244f5  nop
0x1801244f6  mov     rax, [rsi+98h]
0x1801244fd  mov     [rbp+4Fh+Handles], rax
0x180124501  mov     rax, [rbp+4Fh+var_50]
0x180124505  mov     [rbp+4Fh+var_40], rax
0x180124509  mov     r9d, r12d; dwMilliseconds
0x18012450c  xor     r8d, r8d; bWaitAll
0x18012450f  lea     rdx, [rbp+4Fh+Handles]; lpHandles
0x180124513  lea     ecx, [r8+2]; nCount
0x180124517  call    cs:__imp_WaitForMultipleObjects
0x18012451d  test    eax, eax
0x18012451f  jz      loc_18012462F
0x180124525  mov     dword ptr [r14], 0
0x18012452c  mov     dword ptr [r15], 0
0x180124533  cmp     eax, 1
0x180124536  jz      loc_1801245E9
0x18012453c  cmp     eax, 102h
0x180124541  jz      short loc_1801245A3
0x180124543  call    cs:__imp_GetLastError
0x180124549  mov     ebx, eax
0x18012454b  test    eax, eax
0x18012454d  jle     short loc_180124558
0x18012454f  movzx   ebx, ax
0x180124552  or      ebx, 80070000h
0x180124558  mov     eax, 8000FFFFh
0x18012455d  test    ebx, ebx
0x18012455f  cmovns  ebx, eax
0x180124562  mov     rcx, [rbp+57h]; this
0x180124566  mov     r9d, ebx; char *
0x180124569  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x180124570  mov     edx, 0A9h; void *
0x180124575  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012457a  nop
0x18012457b  mov     rcx, [rsp+100h+var_E0]; this
0x180124580  test    rcx, rcx
0x180124583  jz      short loc_18012458B
0x180124585  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18012458a  nop
0x18012458b  lea     rcx, [rbp+4Fh+var_50]
0x18012458f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180124594  nop
0x180124595  mov     rcx, rdi; this
0x180124598  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x18012459d  nop
0x18012459e  jmp     loc_18012447B
0x1801245a3  mov     rcx, [rbp+57h]; this
0x1801245a7  mov     ebx, 800705B4h
0x1801245ac  mov     r9d, ebx; char *
0x1801245af  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801245b6  mov     edx, 0A2h; void *
0x1801245bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801245c0  nop
0x1801245c1  mov     rcx, [rsp+100h+var_E0]; this
0x1801245c6  test    rcx, rcx
0x1801245c9  jz      short loc_1801245D1
0x1801245cb  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x1801245d0  nop
0x1801245d1  lea     rcx, [rbp+4Fh+var_50]
0x1801245d5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801245da  nop
0x1801245db  mov     rcx, rdi; this
0x1801245de  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x1801245e3  nop
0x1801245e4  jmp     loc_18012447B
0x1801245e9  mov     rcx, [rbp+57h]; this
0x1801245ed  mov     ebx, 80004004h
0x1801245f2  mov     r9d, ebx; char *
0x1801245f5  lea     r8, aOnecoreuapAdmi_157; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801245fc  mov     edx, 9Dh; void *
0x180124601  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124606  nop
0x180124607  mov     rcx, [rsp+100h+var_E0]; this
0x18012460c  test    rcx, rcx
0x18012460f  jz      short loc_180124617
0x180124611  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x180124616  nop
0x180124617  lea     rcx, [rbp+4Fh+var_50]
0x18012461b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180124620  nop
0x180124621  mov     rcx, rdi; this
0x180124624  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x180124629  nop
0x18012462a  jmp     loc_18012447B
0x18012462f  lea     rbx, [rsi+0B0h]
0x180124636  mov     rcx, rbx; this
0x180124639  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18012463e  mov     eax, [rsi+0A4h]
0x180124644  mov     [r14], eax
0x180124647  mov     eax, [rsi+0A8h]
0x18012464d  mov     [r15], eax
0x180124650  mov     rcx, rbx; _Mtx_t
0x180124653  call    cs:__imp__Mtx_unlock
0x180124659  nop
0x18012465a  mov     rcx, [rsp+100h+var_E0]; this
0x18012465f  test    rcx, rcx
0x180124662  jz      short loc_18012466A
0x180124664  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x180124669  nop
0x18012466a  lea     rcx, [rbp+4Fh+var_50]
0x18012466e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180124673  nop
0x180124674  mov     rcx, rdi; this
0x180124677  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x18012467c  nop
0x18012467d  xor     eax, eax
0x18012467f  mov     rcx, [rbp+4Fh+var_38]
0x180124683  xor     rcx, rsp; StackCookie
0x180124686  call    __security_check_cookie
0x18012468b  add     rsp, 0D0h
0x180124692  pop     r15
0x180124694  pop     r14
0x180124696  pop     r12
0x180124698  pop     rdi
0x180124699  pop     rsi
0x18012469a  pop     rbx
0x18012469b  pop     rbp
0x18012469c  retn
```
