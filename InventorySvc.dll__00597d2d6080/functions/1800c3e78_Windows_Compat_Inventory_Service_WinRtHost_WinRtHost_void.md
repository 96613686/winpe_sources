# Windows::Compat::Inventory::Service::WinRtHost::WinRtHost(void)

- ea: `0x1800c3e78`
- end: `0x1800c407e`
- name: `??0WinRtHost@Service@Inventory@Compat@Windows@@QEAA@XZ`
- size: `518`
- prototype: `Windows::Compat::Inventory::Service::WinRtHost *__fastcall(Windows::Compat::Inventory::Service::WinRtHost *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011720`

## callees

- `0x180002c40`
- `0x180003c64`
- `0x180006e54`
- `0x18000fc68`
- `0x1800108d4`
- `0x1800110f8`
- `0x1800152d0`
- `0x18002d068`
- `0x1800c3e78`
- `0x1800c53d4`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800c3fd6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800c3fd6`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800c3fa0`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800c3fa0`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800c3f87`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800c3f87`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c3fdd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c3fdd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3f2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3f2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3f39`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c3f0b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c3f0b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800c3ee6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800c3ee6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c3f22`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c3f22`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c3f19`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c3f19`

## string_xrefs

- `0x1800c4027`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800c4001`: `Windows::Compat::Inventory::Service::WinRtHost::WinRtHost`
- `0x1800c4051`: `Windows::Compat::Inventory::Service::WinRtHost::WinRtHost`
- `0x1800c4018`: `onecore\base\appcompat\inventory\service\winrt\lib\winrthost.cpp`
- `0x1800c406f`: `onecore\base\appcompat\inventory\service\winrt\lib\winrthost.cpp`

## pseudocode

```c
Windows::Compat::Inventory::Service::WinRtHost *__fastcall Windows::Compat::Inventory::Service::WinRtHost::WinRtHost(
        Windows::Compat::Inventory::Service::WinRtHost *this,
        __int64 a2,
        __int64 a3)
{
  PVOID *v4; // rbx
  char AppInventoryPresent; // al
  PVOID v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rsi
  struct _TP_TIMER *v8; // rbp
  DWORD LastError; // ebx
  DWORD v10; // eax
  DWORD v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // ecx
  int v15; // eax
  const char *v17; // r9
  unsigned int v18; // eax
  unsigned int v19; // [rsp+20h] [rbp-38h]
  unsigned int v20; // [rsp+20h] [rbp-38h]
  _DWORD v21[8]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void *v23; // [rsp+68h] [rbp+10h]

  *(_QWORD *)this = &Windows::Compat::Inventory::Service::WinRtHost::`vftable';
  v4 = (PVOID *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  *((_OWORD *)this + 1) = 0;
  *((_QWORD *)this + 4) = 0;
  if ( Windows::Compat::Inventory::Service::WinRtHost::singleInstance )
  {
    AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::WinRtHost::WinRtHost", 15, "failed [%#x]", -2147418113);
    v18 = wil::verify_hresult<long>(2147549183LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\winrt\\lib\\winrthost.cpp",
      (const char *)v18,
      v20);
  }
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)this + 8,
    a2,
    a3,
    0);
  AppInventoryPresent = IsGetAppInventoryPresent();
  v6 = *v4;
  if ( AppInventoryPresent )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(TimerExpirationCallback, *v4, 0);
    v8 = (struct _TP_TIMER *)*((_QWORD *)this + 4);
    if ( v8 )
    {
      LastError = GetLastError();
      SetThreadpoolTimer(v8, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v8, 1);
      CloseThreadpoolTimer(v8);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 4) = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
    {
      v10 = GetLastError();
      v11 = v10;
      if ( v10 )
      {
        AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::WinRtHost::WinRtHost", 25, "failed [%d]", v10);
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x19,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\winrt\\lib\\winrthost.cpp",
          (const char *)v11,
          v19);
      }
    }
    Windows::Compat::Inventory::Service::WinRtHost::SetTimer(this);
    Windows::Compat::Inventory::Service::WinRtHost::singleInstance = this;
    v23 = operator new(1u);
    v12 = _o__beginthreadex(
            0,
            0,
            std::thread::_Invoke_std::tuple__lambda_4036d5917722b406f87de37c90732adc____0_,
            v23,
            0,
            v21);
    if ( v12 )
    {
      if ( *((_DWORD *)this + 6) )
      {
        _o_terminate(v13, v12);
        __debugbreak();
      }
      v14 = v21[0];
      v15 = v21[1];
      *((_QWORD *)this + 2) = v12;
      *((_DWORD *)this + 6) = v14;
      *((_DWORD *)this + 7) = v15;
      return this;
    }
    v21[0] = 0;
    std::_Throw_Cpp_error(6);
  }
  if ( !SetEvent(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v17);
  return this;
}

```

## disassembly

```asm
0x1800c3e78  mov     [rsp+arg_10], rbx
0x1800c3e7d  mov     [rsp+arg_0], rcx
0x1800c3e82  push    rbp
0x1800c3e83  push    rsi
0x1800c3e84  push    rdi
0x1800c3e85  sub     rsp, 40h
0x1800c3e89  mov     rdi, rcx
0x1800c3e8c  lea     rax, ??_7WinRtHost@Service@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::Service::WinRtHost::`vftable'
0x1800c3e93  mov     [rcx], rax
0x1800c3e96  lea     rbx, [rcx+8]
0x1800c3e9a  mov     qword ptr [rbx], 0
0x1800c3ea1  xorps   xmm0, xmm0
0x1800c3ea4  movups  xmmword ptr [rcx+10h], xmm0
0x1800c3ea8  mov     qword ptr [rcx+20h], 0
0x1800c3eb0  cmp     cs:?singleInstance@WinRtHost@Service@Inventory@Compat@Windows@@0PEAV12345@EA, 0; Windows::Compat::Inventory::Service::WinRtHost * Windows::Compat::Inventory::Service::WinRtHost::singleInstance
0x1800c3eb8  jnz     loc_1800C4039
0x1800c3ebe  xor     r9d, r9d
0x1800c3ec1  mov     rcx, rbx
0x1800c3ec4  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800c3ec9  call    IsGetAppInventoryPresent
0x1800c3ece  mov     rcx, [rbx]
0x1800c3ed1  test    al, al
0x1800c3ed3  jz      loc_1800C3FDD
0x1800c3ed9  xor     r8d, r8d; pcbe
0x1800c3edc  mov     rdx, rcx; pv
0x1800c3edf  lea     rcx, ?TimerExpirationCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800c3ee6  call    cs:__imp_CreateThreadpoolTimer
0x1800c3eec  mov     rsi, rax
0x1800c3eef  mov     rbp, [rdi+20h]
0x1800c3ef3  test    rbp, rbp
0x1800c3ef6  jz      short loc_1800C3F30
0x1800c3ef8  call    cs:__imp_GetLastError
0x1800c3efe  mov     ebx, eax
0x1800c3f00  xor     r9d, r9d; msWindowLength
0x1800c3f03  xor     r8d, r8d; msPeriod
0x1800c3f06  xor     edx, edx; pftDueTime
0x1800c3f08  mov     rcx, rbp; pti
0x1800c3f0b  call    cs:__imp_SetThreadpoolTimer
0x1800c3f11  mov     edx, 1; fCancelPendingCallbacks
0x1800c3f16  mov     rcx, rbp; pti
0x1800c3f19  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800c3f1f  mov     rcx, rbp; pti
0x1800c3f22  call    cs:__imp_CloseThreadpoolTimer
0x1800c3f28  mov     ecx, ebx; dwErrCode
0x1800c3f2a  call    cs:__imp_SetLastError
0x1800c3f30  mov     [rdi+20h], rsi
0x1800c3f34  test    rsi, rsi
0x1800c3f37  jnz     short loc_1800C3F49
0x1800c3f39  call    cs:__imp_GetLastError
0x1800c3f3f  mov     ebx, eax
0x1800c3f41  test    eax, eax
0x1800c3f43  jnz     loc_1800C3FEE
0x1800c3f49  mov     rcx, rdi; this
0x1800c3f4c  call    ?SetTimer@WinRtHost@Service@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::Service::WinRtHost::SetTimer(void)
0x1800c3f51  mov     cs:?singleInstance@WinRtHost@Service@Inventory@Compat@Windows@@0PEAV12345@EA, rdi; Windows::Compat::Inventory::Service::WinRtHost * Windows::Compat::Inventory::Service::WinRtHost::singleInstance
0x1800c3f58  mov     ecx, 1; Size
0x1800c3f5d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c3f62  mov     [rsp+58h+arg_8], rax
0x1800c3f67  lea     rcx, [rsp+58h+var_20]
0x1800c3f6c  mov     [rsp+58h+var_30], rcx
0x1800c3f71  mov     [rsp+58h+var_38], 0
0x1800c3f79  mov     r9, rax
0x1800c3f7c  lea     r8, std__thread___Invoke_std__tuple__lambda_4036d5917722b406f87de37c90732adc____0_
0x1800c3f83  xor     edx, edx
0x1800c3f85  xor     ecx, ecx
0x1800c3f87  call    cs:__imp__o__beginthreadex
0x1800c3f8d  mov     rdx, rax
0x1800c3f90  mov     [rsp+58h+var_28], rax
0x1800c3f95  test    rax, rax
0x1800c3f98  jz      short loc_1800C3FC9
0x1800c3f9a  cmp     dword ptr [rdi+18h], 0
0x1800c3f9e  jz      short loc_1800C3FA7
0x1800c3fa0  call    cs:__imp__o_terminate
0x1800c3fa6  int     3; Trap to Debugger
0x1800c3fa7  mov     ecx, [rsp+58h+var_20]
0x1800c3fab  mov     eax, [rsp+58h+var_1C]
0x1800c3faf  mov     [rdi+10h], rdx
0x1800c3fb3  mov     [rdi+18h], ecx
0x1800c3fb6  mov     [rdi+1Ch], eax
0x1800c3fb9  mov     rax, rdi
0x1800c3fbc  mov     rbx, [rsp+58h+arg_10]
0x1800c3fc1  add     rsp, 40h
0x1800c3fc5  pop     rdi
0x1800c3fc6  pop     rsi
0x1800c3fc7  pop     rbp
0x1800c3fc8  retn
0x1800c3fc9  mov     [rsp+58h+var_20], 0
0x1800c3fd1  mov     ecx, 6
0x1800c3fd6  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800c3fdc  nop
0x1800c3fdd  call    cs:__imp_SetEvent
0x1800c3fe3  mov     rcx, [rsp+58h]; this
0x1800c3fe8  test    eax, eax
0x1800c3fea  jz      short loc_1800C4027
0x1800c3fec  jmp     short loc_1800C3FB9
0x1800c3fee  mov     [rsp+58h+var_38], ebx; unsigned int
0x1800c3ff2  lea     r9, aFailedD; "failed [%d]"
0x1800c3ff9  mov     edi, 19h
0x1800c3ffe  mov     r8d, edi
0x1800c4001  lea     rdx, aWindowsCompatI_23; "Windows::Compat::Inventory::Service::Wi"...
0x1800c4008  lea     ecx, [rdi-18h]
0x1800c400b  call    AslLogCallPrintf
0x1800c4010  mov     rcx, [rsp+58h]; this
0x1800c4015  mov     r9d, ebx; char *
0x1800c4018  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\se"...
0x1800c401f  mov     edx, edi; void *
0x1800c4021  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800c4027  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c402e  mov     edx, 0A01h; void *
0x1800c4033  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800c4039  mov     ebx, 8000FFFFh
0x1800c403e  mov     [rsp+58h+var_38], ebx; int
0x1800c4042  lea     r9, aFailedX; "failed [%#x]"
0x1800c4049  mov     edi, 0Fh
0x1800c404e  mov     r8d, edi
0x1800c4051  lea     rdx, aWindowsCompatI_23; "Windows::Compat::Inventory::Service::Wi"...
0x1800c4058  lea     ecx, [rdi-0Eh]
0x1800c405b  call    AslLogCallPrintf
0x1800c4060  mov     ecx, ebx
0x1800c4062  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800c4067  mov     r9d, eax; char *
0x1800c406a  mov     rcx, [rsp+58h]; this
0x1800c406f  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\se"...
0x1800c4076  mov     edx, edi; void *
0x1800c4078  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
