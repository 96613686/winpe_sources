# Windows::System::ShutdownManagerImpl::EnterPowerStateInternal(Windows::System::PowerState,Windows::Foundation::TimeSpan *)

- ea: `0x18000db70`
- end: `0x18000de46`
- name: `?EnterPowerStateInternal@ShutdownManagerImpl@System@Windows@@AEAAJW4PowerState@23@PEAUTimeSpan@Foundation@3@@Z`
- size: `726`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18000dab0`
- `0x18000de50`

## callees

- `0x180002dc0`
- `0x18000d5a4`
- `0x18000db70`
- `0x18000fa18`
- `0x18000fa70`
- `0x18001c6a8`
- `0x18002b010`

## import_xrefs

- `ntdll!NtInitiatePowerAction` at `0x18000dde8`
- `ntdll!NtInitiatePowerAction` at `0x18000dde8`
- `ntdll!NtPowerInformation` at `0x18000ddb2`
- `ntdll!NtPowerInformation` at `0x18000ddb2`
- `ntdll!RtlAcquirePrivilege` at `0x18000ddcd`
- `ntdll!RtlAcquirePrivilege` at `0x18000ddcd`
- `ntdll!RtlReleasePrivilege` at `0x18000de17`
- `ntdll!RtlReleasePrivilege` at `0x18000de17`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18000dd1b`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18000dd1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dbee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dbee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de06`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18000dc6d`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18000dc6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000dd2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000dd2f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000dce0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000dce0`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18000dc98`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18000dc98`
- `UMPDC!PdcNotificationClientRegister` at `0x18000dd77`
- `UMPDC!PdcNotificationClientRegister` at `0x18000dd77`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::System::ShutdownManagerImpl::EnterPowerStateInternal(
        __int64 a1,
        unsigned int a2,
        __int64 *a3)
{
  int HasSystemManagementCapability; // ebx
  HANDLE *v7; // rdi
  void *v8; // rcx
  HANDLE WaitableTimerW; // rax
  signed int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rax
  NTSTATUS v12; // eax
  unsigned __int8 v14; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v15[3]; // [rsp+31h] [rbp-38h] BYREF
  int v16; // [rsp+34h] [rbp-35h] BYREF
  ULONG Privilege; // [rsp+38h] [rbp-31h] BYREF
  LARGE_INTEGER DueTime; // [rsp+40h] [rbp-29h] BYREF
  PVOID ReturnedState; // [rsp+48h] [rbp-21h] BYREF
  __int64 v20; // [rsp+50h] [rbp-19h] BYREF
  PVOID *p_ReturnedState; // [rsp+58h] [rbp-11h]
  __int64 v22; // [rsp+60h] [rbp-9h]
  __int64 (__fastcall *v23)(); // [rsp+68h] [rbp-1h]
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+70h] [rbp+7h]
  __int64 InputBuffer; // [rsp+78h] [rbp+Fh] BYREF
  int v26; // [rsp+80h] [rbp+17h]

  v14 = 0;
  v15[0] = 0;
  InputBuffer = 0;
  v26 = 0;
  DueTime.QuadPart = 0;
  ReturnedState = 0;
  v16 = -1073741727;
  Privilege = 19;
  v20 = (__int64)&v16;
  p_ReturnedState = &ReturnedState;
  LOBYTE(v22) = 1;
  EnterCriticalSection(&Windows::System::ShutdownManagerImpl::s_lock);
  v24 = &Windows::System::ShutdownManagerImpl::s_lock;
  HasSystemManagementCapability = Windows::System::SystemManagementUtil::HasSystemManagementCapability(&v14);
  if ( HasSystemManagementCapability >= 0 )
  {
    if ( !v14 )
    {
      HasSystemManagementCapability = -2147024891;
      goto LABEL_29;
    }
    if ( a2 >= 2 )
      goto LABEL_5;
    HasSystemManagementCapability = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)(a1 + 56) + 48LL))(
                                      a1 + 56,
                                      a2,
                                      v15);
    if ( HasSystemManagementCapability >= 0 )
    {
      if ( !v15[0] )
      {
        HasSystemManagementCapability = -2147024846;
        goto LABEL_29;
      }
      v7 = (HANDLE *)(a1 + 136);
      v8 = *(void **)(a1 + 136);
      if ( v8 )
      {
        CancelWaitableTimer(v8);
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(a1 + 136);
      }
      if ( !a3 )
        goto LABEL_22;
      if ( *a3 < 0 )
      {
LABEL_5:
        HasSystemManagementCapability = -2147024809;
        goto LABEL_29;
      }
      *(_DWORD *)(a1 + 152) = a2;
      WaitableTimerW = CreateWaitableTimerW(0, 1, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        a1 + 136,
        WaitableTimerW);
      if ( !*v7
        || (ThreadpoolWait = CreateThreadpoolWait(
                               Windows::System::ShutdownManagerImpl::s_PowerStateTimerCallback,
                               (PVOID)a1,
                               0),
            wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
              a1 + 144,
              ThreadpoolWait),
            !*(_QWORD *)(a1 + 144))
        || (DueTime.QuadPart = -*a3, !SetWaitableTimer(*v7, &DueTime, 0, 0, 0, 1)) )
      {
        LastError = GetLastError();
        HasSystemManagementCapability = LastError;
        if ( LastError > 0 )
          HasSystemManagementCapability = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_29;
      }
      SetThreadpoolWait(*(PTP_WAIT *)(a1 + 144), *v7, 0);
      if ( !Windows::System::ShutdownManagerImpl::s_pdcClientRegistered )
      {
        v20 = 1;
        v22 = 0;
        p_ReturnedState = (PVOID *)Windows::System::ShutdownManagerImpl::s_PdcStateCallback;
        v23 = winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::System::Update::SystemUpdateItem,std::vector<winrt::Windows::System::Update::SystemUpdateItem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::System::Update::SystemUpdateItem,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::System::Update::SystemUpdateItem>>::GetTrustLevel;
        HasSystemManagementCapability = PdcNotificationClientRegister(1, &v20, a1, a1 + 160);
        if ( HasSystemManagementCapability < 0 )
          goto LABEL_29;
        Windows::System::ShutdownManagerImpl::s_pdcClientRegistered = 1;
      }
      if ( *a3 > 0 )
      {
LABEL_22:
        if ( a2 )
        {
          v12 = RtlAcquirePrivilege(&Privilege, 1u, 0, &ReturnedState);
          v16 = v12;
          if ( v12 < 0 )
          {
LABEL_28:
            HasSystemManagementCapability = v12 | 0x10000000;
            goto LABEL_29;
          }
          v12 = NtInitiatePowerAction(PowerActionSleep, PowerSystemSleeping3, 3u, 0);
        }
        else
        {
          InputBuffer = 25;
          LOBYTE(v26) = 0;
          v12 = NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 0xCu, 0, 0);
        }
        if ( v12 && v12 != 259 )
          goto LABEL_28;
      }
    }
  }
LABEL_29:
  LeaveCriticalSection(&Windows::System::ShutdownManagerImpl::s_lock);
  if ( v16 >= 0 )
    RtlReleasePrivilege(ReturnedState);
  return (unsigned int)HasSystemManagementCapability;
}

```

## disassembly

```asm
0x18000db70  mov     [rsp-8+arg_18], rbx
0x18000db75  push    rbp
0x18000db76  push    rsi
0x18000db77  push    rdi
0x18000db78  push    r12
0x18000db7a  push    r13
0x18000db7c  push    r14
0x18000db7e  push    r15
0x18000db80  lea     rbp, [rsp-27h]
0x18000db85  sub     rsp, 90h
0x18000db8c  mov     rax, cs:__security_cookie
0x18000db93  xor     rax, rsp
0x18000db96  mov     [rbp+57h+var_38], rax
0x18000db9a  mov     r15, r8
0x18000db9d  mov     esi, edx
0x18000db9f  mov     r14, rcx
0x18000dba2  xor     r13d, r13d
0x18000dba5  mov     [rbp+57h+var_90], r13b
0x18000dba9  mov     [rbp+57h+var_8F], r13b
0x18000dbad  xor     eax, eax
0x18000dbaf  mov     [rbp+57h+InputBuffer], rax
0x18000dbb3  mov     [rbp+57h+var_40], eax
0x18000dbb6  mov     qword ptr [rbp+57h+DueTime], r13
0x18000dbba  mov     [rbp+57h+ReturnedState], r13
0x18000dbbe  mov     [rbp+57h+var_8C], 0C0000061h
0x18000dbc5  mov     [rbp+57h+Privilege], 13h
0x18000dbcc  lea     rax, [rbp+57h+var_8C]
0x18000dbd0  mov     [rbp+57h+var_70], rax
0x18000dbd4  lea     rax, [rbp+57h+ReturnedState]
0x18000dbd8  mov     [rbp+57h+var_68], rax
0x18000dbdc  lea     r12d, [r13+1]
0x18000dbe0  mov     byte ptr [rbp+57h+var_60], r12b
0x18000dbe4  lea     rbx, ?s_lock@ShutdownManagerImpl@System@Windows@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection Windows::System::ShutdownManagerImpl::s_lock
0x18000dbeb  mov     rcx, rbx; lpCriticalSection
0x18000dbee  call    cs:__imp_EnterCriticalSection
0x18000dbf4  mov     [rbp+57h+var_50], rbx
0x18000dbf8  lea     rcx, [rbp+57h+var_90]; unsigned __int8 *
0x18000dbfc  call    ?HasSystemManagementCapability@SystemManagementUtil@System@Windows@@SAJPEAE@Z; Windows::System::SystemManagementUtil::HasSystemManagementCapability(uchar *)
0x18000dc01  mov     ebx, eax
0x18000dc03  test    eax, eax
0x18000dc05  js      loc_18000DDFF
0x18000dc0b  cmp     [rbp+57h+var_90], r13b
0x18000dc0f  jnz     short loc_18000DC1B
0x18000dc11  mov     ebx, 80070005h
0x18000dc16  jmp     loc_18000DDFF
0x18000dc1b  test    esi, esi
0x18000dc1d  jz      short loc_18000DC2E
0x18000dc1f  cmp     esi, 1
0x18000dc22  jz      short loc_18000DC2E
0x18000dc24  mov     ebx, 80070057h
0x18000dc29  jmp     loc_18000DDFF
0x18000dc2e  lea     rcx, [r14+38h]
0x18000dc32  mov     rax, [rcx]
0x18000dc35  lea     r8, [rbp+57h+var_8F]
0x18000dc39  mov     edx, esi
0x18000dc3b  mov     rax, [rax+30h]
0x18000dc3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc44  mov     ebx, eax
0x18000dc46  test    eax, eax
0x18000dc48  js      loc_18000DDFF
0x18000dc4e  cmp     [rbp+57h+var_8F], r13b
0x18000dc52  jnz     short loc_18000DC5E
0x18000dc54  mov     ebx, 80070032h
0x18000dc59  jmp     loc_18000DDFF
0x18000dc5e  lea     rdi, [r14+88h]
0x18000dc65  mov     rcx, [rdi]; hTimer
0x18000dc68  test    rcx, rcx
0x18000dc6b  jz      short loc_18000DC7B
0x18000dc6d  call    cs:__imp_CancelWaitableTimer
0x18000dc73  mov     rcx, rdi
0x18000dc76  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(std::nullptr_t)
0x18000dc7b  test    r15, r15
0x18000dc7e  jz      loc_18000DD8F
0x18000dc84  cmp     [r15], r13
0x18000dc87  jl      short loc_18000DC24
0x18000dc89  mov     [r14+98h], esi
0x18000dc90  xor     r8d, r8d; lpTimerName
0x18000dc93  mov     edx, r12d; bManualReset
0x18000dc96  xor     ecx, ecx; lpTimerAttributes
0x18000dc98  call    cs:__imp_CreateWaitableTimerW
0x18000dc9e  mov     rdx, rax
0x18000dca1  mov     rcx, rdi
0x18000dca4  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000dca9  cmp     [rdi], r13
0x18000dcac  jnz     short loc_18000DCCC
0x18000dcae  call    cs:__imp_GetLastError
0x18000dcb4  mov     ebx, eax
0x18000dcb6  test    eax, eax
0x18000dcb8  jle     loc_18000DDFF
0x18000dcbe  movzx   ebx, ax
0x18000dcc1  or      ebx, 80070000h
0x18000dcc7  jmp     loc_18000DDFF
0x18000dccc  lea     r12, [r14+90h]
0x18000dcd3  xor     r8d, r8d; pcbe
0x18000dcd6  mov     rdx, r14; pv
0x18000dcd9  lea     rcx, ?s_PowerStateTimerCallback@ShutdownManagerImpl@System@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18000dce0  call    cs:__imp_CreateThreadpoolWait
0x18000dce6  mov     rdx, rax
0x18000dce9  mov     rcx, r12
0x18000dcec  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18000dcf1  cmp     [r12], r13
0x18000dcf5  jz      short loc_18000DCAE
0x18000dcf7  mov     rax, [r15]
0x18000dcfa  neg     rax
0x18000dcfd  mov     qword ptr [rbp+57h+DueTime], rax
0x18000dd01  mov     [rsp+0C0h+fResume], 1; fResume
0x18000dd09  mov     [rsp+0C0h+lpArgToCompletionRoutine], r13; lpArgToCompletionRoutine
0x18000dd0e  xor     r9d, r9d; pfnCompletionRoutine
0x18000dd11  xor     r8d, r8d; lPeriod
0x18000dd14  lea     rdx, [rbp+57h+DueTime]; lpDueTime
0x18000dd18  mov     rcx, [rdi]; hTimer
0x18000dd1b  call    cs:__imp_SetWaitableTimer
0x18000dd21  test    eax, eax
0x18000dd23  jz      short loc_18000DCAE
0x18000dd25  xor     r8d, r8d; pftTimeout
0x18000dd28  mov     rdx, [rdi]; h
0x18000dd2b  mov     rcx, [r12]; pwa
0x18000dd2f  call    cs:__imp_SetThreadpoolWait
0x18000dd35  mov     r12d, 1
0x18000dd3b  cmp     cs:?s_pdcClientRegistered@ShutdownManagerImpl@System@Windows@@0HA, r13d; int Windows::System::ShutdownManagerImpl::s_pdcClientRegistered
0x18000dd42  jnz     short loc_18000DD8A
0x18000dd44  mov     [rbp+57h+var_70], 1
0x18000dd4c  mov     [rbp+57h+var_60], r13
0x18000dd50  lea     rax, ?s_PdcStateCallback@ShutdownManagerImpl@System@Windows@@CAJPEAXK@Z; Windows::System::ShutdownManagerImpl::s_PdcStateCallback(void *,ulong)
0x18000dd57  mov     [rbp+57h+var_68], rax
0x18000dd5b  lea     rax, ?GetTrustLevel@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@USystemUpdateItem@Update@System@Windows@winrt@@V?$vector@USystemUpdateItem@Update@System@Windows@winrt@@V?$allocator@USystemUpdateItem@Update@System@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@USystemUpdateItem@Update@System@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@USystemUpdateItem@Update@System@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@MEBA?AW4TrustLevel@Foundation@Windows@3@XZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::System::Update::SystemUpdateItem,std::vector<winrt::Windows::System::Update::SystemUpdateItem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::System::Update::SystemUpdateItem,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::System::Update::SystemUpdateItem>>::GetTrustLevel(void)
0x18000dd62  mov     [rbp+57h+var_58], rax
0x18000dd66  lea     r9, [r14+0A0h]
0x18000dd6d  mov     r8, r14
0x18000dd70  lea     rdx, [rbp+57h+var_70]
0x18000dd74  mov     ecx, r12d
0x18000dd77  call    cs:__imp_PdcNotificationClientRegister
0x18000dd7d  mov     ebx, eax
0x18000dd7f  test    eax, eax
0x18000dd81  js      short loc_18000DDFF
0x18000dd83  mov     cs:?s_pdcClientRegistered@ShutdownManagerImpl@System@Windows@@0HA, r12d; int Windows::System::ShutdownManagerImpl::s_pdcClientRegistered
0x18000dd8a  cmp     [r15], r13
0x18000dd8d  jle     short loc_18000DDFF
0x18000dd8f  test    esi, esi
0x18000dd91  jnz     short loc_18000DDBA
0x18000dd93  mov     [rbp+57h+InputBuffer], 19h
0x18000dd9b  mov     byte ptr [rbp+57h+var_40], r13b
0x18000dd9f  mov     dword ptr [rsp+0C0h+lpArgToCompletionRoutine], r13d; OutputBufferLength
0x18000dda4  xor     r9d, r9d; OutputBuffer
0x18000dda7  lea     r8d, [rsi+0Ch]; InputBufferLength
0x18000ddab  lea     rdx, [rbp+57h+InputBuffer]; InputBuffer
0x18000ddaf  lea     ecx, [rsi+57h]; PowerInformationLevel
0x18000ddb2  call    cs:__imp_NtPowerInformation
0x18000ddb8  jmp     short loc_18000DDEE
0x18000ddba  cmp     esi, r12d
0x18000ddbd  jnz     short loc_18000DDFF
0x18000ddbf  lea     r9, [rbp+57h+ReturnedState]; ReturnedState
0x18000ddc3  xor     r8d, r8d; Flags
0x18000ddc6  mov     edx, r12d; NumPriv
0x18000ddc9  lea     rcx, [rbp+57h+Privilege]; Privilege
0x18000ddcd  call    cs:__imp_RtlAcquirePrivilege
0x18000ddd3  mov     [rbp+57h+var_8C], eax
0x18000ddd6  test    eax, eax
0x18000ddd8  js      short loc_18000DDF9
0x18000ddda  xor     r9d, r9d; Asynchronous
0x18000dddd  lea     edx, [r9+4]; MinSystemState
0x18000dde1  lea     ecx, [rdx-2]; SystemAction
0x18000dde4  lea     r8d, [r9+3]; Flags
0x18000dde8  call    cs:__imp_NtInitiatePowerAction
0x18000ddee  test    eax, eax
0x18000ddf0  jz      short loc_18000DDFF
0x18000ddf2  cmp     eax, 103h
0x18000ddf7  jz      short loc_18000DDFF
0x18000ddf9  mov     ebx, eax
0x18000ddfb  bts     ebx, 1Ch
0x18000ddff  lea     rcx, ?s_lock@ShutdownManagerImpl@System@Windows@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x18000de06  call    cs:__imp_LeaveCriticalSection
0x18000de0c  nop
0x18000de0d  cmp     [rbp+57h+var_8C], r13d
0x18000de11  jl      short loc_18000DE1D
0x18000de13  mov     rcx, [rbp+57h+ReturnedState]; ReturnedState
0x18000de17  call    cs:__imp_RtlReleasePrivilege
0x18000de1d  mov     eax, ebx
0x18000de1f  mov     rcx, [rbp+57h+var_38]
0x18000de23  xor     rcx, rsp; StackCookie
0x18000de26  call    __security_check_cookie
0x18000de2b  mov     rbx, [rsp+0C0h+arg_18]
0x18000de33  add     rsp, 90h
0x18000de3a  pop     r15
0x18000de3c  pop     r14
0x18000de3e  pop     r13
0x18000de40  pop     r12
0x18000de42  pop     rdi
0x18000de43  pop     rsi
0x18000de44  pop     rbp
0x18000de45  retn
```
