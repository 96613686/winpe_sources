# HNS::Service::Util::details::ServiceMonitor::ServiceMonitor(wil::basic_zstring_view<ushort>,bool)

- ea: `0x18023efe4`
- end: `0x18023f22b`
- name: `??0ServiceMonitor@details@Util@Service@HNS@@QEAA@V?$basic_zstring_view@G@wil@@_N@Z`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18023ef1c`

## callees

- `0x18005f0c0`
- `0x18005f59c`
- `0x180064018`
- `0x1800666d4`
- `0x1800677f0`
- `0x180067c00`
- `0x1800860d0`
- `0x18023efe4`
- `0x18023feb0`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18023f1e4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18023f1e4`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18023f198`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18023f198`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18023f183`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18023f183`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18023f113`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18023f139`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18023f113`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18023f139`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18023f061`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18023f061`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18023f0f9`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18023f0f9`

## string_xrefs

- `0x18023f219`: `onecore\vm\dv\net\hns\service\common\helperlib\src\servicemonitor.cpp`
- `0x18023f212`: `Failed to Query service status : %ws.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
HNS::Service::Util::details::ServiceMonitor *__fastcall HNS::Service::Util::details::ServiceMonitor::ServiceMonitor(
        HNS::Service::Util::details::ServiceMonitor *this,
        _QWORD *a2,
        char a3)
{
  char *v6; // rcx
  HANDLE *v7; // r15
  unsigned int v8; // r8d
  const char *v9; // r9
  BOOL v10; // eax
  unsigned int v11; // r8d
  const char *v12; // r9
  wil::details::in1diag3 *v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // rax
  int v16; // edx
  int v17; // ecx
  const char *v19; // rax
  DWORD pcbBytesNeeded[4]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v21; // [rsp+40h] [rbp-29h]
  _DWORD v22[2]; // [rsp+48h] [rbp-21h] BYREF
  HNS::Service::Util::details::ServiceMonitor *v23; // [rsp+50h] [rbp-19h]
  _QWORD *v24; // [rsp+58h] [rbp-11h]
  BYTE Buffer[16]; // [rsp+60h] [rbp-9h] BYREF
  __int128 v26; // [rsp+70h] [rbp+7h]
  int v27; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v23 = this;
  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_OWORD *)this + 1) = 0;
  v6 = (char *)this + 32;
  *(_OWORD *)v6 = 0;
  *((_QWORD *)v6 + 2) = 0;
  *((_QWORD *)v6 + 3) = 0;
  std::wstring::_Construct<1,unsigned short const *>(v6, *a2);
  v7 = (HANDLE *)((char *)this + 64);
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 88), 0, 0);
  *((_DWORD *)this + 32) = 2000;
  *((_DWORD *)this + 33) = 16000;
  *((_DWORD *)this + 34) = 2000;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_BYTE *)this + 248) = a3;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)this + 72,
    0);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)this + 80,
    0);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)this + 64,
    1);
  HNS::Service::Util::details::ServiceMonitor::OpenServiceHandle(this);
  *(_OWORD *)Buffer = 0;
  v26 = 0;
  v27 = 0;
  pcbBytesNeeded[0] = 0;
  if ( !QueryServiceStatusEx(*((SC_HANDLE *)this + 1), SC_STATUS_PROCESS_INFO, Buffer, 0x24u, pcbBytesNeeded) )
  {
    v19 = (const char *)std::shared_ptr<HNS::Service::Resource::ExternalAdapterResource>::operator-><HNS::Service::Resource::ExternalAdapterResource,0>(a2);
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x11B,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\servicemonitor.cpp",
      "Failed to Query service status : %ws.",
      v19);
  }
  if ( *(_DWORD *)&Buffer[4] == 4 )
  {
    _InterlockedExchange((volatile __int32 *)this, 1);
    if ( !SetEvent(*v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v8, v9);
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this, 0);
    if ( !*((_BYTE *)this + 248) )
    {
      v10 = SetEvent(*v7);
      v13 = retaddr;
      if ( !v10 )
LABEL_12:
        wil::details::in1diag3::_FailFast_GetLastError(v13, (void *)0xA01, v11, v12);
    }
  }
  v14 = operator new(0x10u);
  *v14 = HNS::Service::Util::details::ServiceMonitor::WorkerProc;
  v14[1] = this;
  v24 = v14;
  v15 = _o__beginthreadex(
          0,
          0,
          std::thread::_Invoke<std::tuple<std::_Binder<std::_Unforced,void (HNS::Service::Util::details::ServiceMonitor::*)(void),HNS::Service::Util::details::ServiceMonitor *>>,0>,
          v14,
          0,
          v22);
  v21 = v15;
  if ( !v15 )
  {
    v22[0] = 0;
    std::_Throw_Cpp_error(6);
    goto LABEL_12;
  }
  if ( *((_DWORD *)this + 6) )
  {
    _o_terminate();
    __debugbreak();
  }
  v16 = v22[0];
  v17 = v22[1];
  *((_QWORD *)this + 2) = v15;
  *((_DWORD *)this + 6) = v16;
  *((_DWORD *)this + 7) = v17;
  return this;
}

```

## disassembly

```asm
0x18023efe4  mov     [rsp-8+arg_10], rbx
0x18023efe9  push    rbp
0x18023efea  push    rsi
0x18023efeb  push    rdi
0x18023efec  push    r12
0x18023efee  push    r13
0x18023eff0  push    r14
0x18023eff2  push    r15
0x18023eff4  lea     rbp, [rsp-27h]
0x18023eff9  sub     rsp, 90h
0x18023f000  mov     rax, cs:__security_cookie
0x18023f007  xor     rax, rsp
0x18023f00a  mov     [rbp+57h+var_38], rax
0x18023f00e  mov     sil, r8b
0x18023f011  mov     r12, rdx
0x18023f014  mov     r14, rcx
0x18023f017  mov     [rbp+57h+var_70], rcx
0x18023f01b  xor     r13d, r13d
0x18023f01e  xor     eax, eax
0x18023f020  mov     [rcx], eax
0x18023f022  mov     [rcx+8], r13
0x18023f026  xorps   xmm0, xmm0
0x18023f029  movups  xmmword ptr [rcx+10h], xmm0
0x18023f02d  add     rcx, 20h ; ' '
0x18023f031  movups  xmmword ptr [rcx], xmm0
0x18023f034  mov     [rcx+10h], r13
0x18023f038  mov     [rcx+18h], r13
0x18023f03c  mov     r8, [rdx+8]
0x18023f040  mov     rdx, [rdx]
0x18023f043  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18023f048  nop
0x18023f049  lea     r15, [r14+40h]
0x18023f04d  mov     [r15], r13
0x18023f050  mov     [r14+48h], r13
0x18023f054  mov     [r14+50h], r13
0x18023f058  lea     rcx, [r14+58h]; lpCriticalSection
0x18023f05c  xor     r8d, r8d; Flags
0x18023f05f  xor     edx, edx; dwSpinCount
0x18023f061  call    cs:__imp_InitializeCriticalSectionEx
0x18023f067  nop
0x18023f068  mov     eax, 7D0h
0x18023f06d  mov     [r14+80h], eax
0x18023f074  mov     dword ptr [r14+84h], 3E80h
0x18023f07f  mov     [r14+88h], eax
0x18023f086  mov     [r14+90h], r13
0x18023f08d  mov     [r14+98h], r13
0x18023f094  mov     [r14+0A0h], r13
0x18023f09b  mov     [r14+0F8h], sil
0x18023f0a2  xor     edx, edx
0x18023f0a4  lea     rcx, [r14+48h]
0x18023f0a8  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18023f0ad  xor     edx, edx
0x18023f0af  lea     rcx, [r14+50h]
0x18023f0b3  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18023f0b8  lea     ebx, [r13+1]
0x18023f0bc  mov     edx, ebx
0x18023f0be  mov     rcx, r15
0x18023f0c1  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18023f0c6  mov     rcx, r14; this
0x18023f0c9  call    ?OpenServiceHandle@ServiceMonitor@details@Util@Service@HNS@@AEAAXXZ; HNS::Service::Util::details::ServiceMonitor::OpenServiceHandle(void)
0x18023f0ce  xorps   xmm0, xmm0
0x18023f0d1  xor     eax, eax
0x18023f0d3  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x18023f0d7  movups  [rbp+57h+var_50], xmm0
0x18023f0db  mov     [rbp+57h+var_40], eax
0x18023f0de  mov     [rbp+57h+var_90], r13d
0x18023f0e2  lea     rax, [rbp+57h+var_90]
0x18023f0e6  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18023f0eb  lea     r9d, [r13+24h]; cbBufSize
0x18023f0ef  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18023f0f3  xor     edx, edx; InfoLevel
0x18023f0f5  mov     rcx, [r14+8]; hService
0x18023f0f9  call    cs:__imp_QueryServiceStatusEx
0x18023f0ff  test    eax, eax
0x18023f101  jz      loc_18023F201
0x18023f107  cmp     dword ptr [rbp+57h+Buffer+4], 4
0x18023f10b  jnz     short loc_18023F127
0x18023f10d  xchg    ebx, [r14]
0x18023f110  mov     rcx, [r15]; hEvent
0x18023f113  call    cs:__imp_SetEvent
0x18023f119  mov     rcx, [rbp+5Fh]; this
0x18023f11d  test    eax, eax
0x18023f11f  jz      loc_18023F1F6
0x18023f125  jmp     short loc_18023F14B
0x18023f127  mov     eax, r13d
0x18023f12a  xchg    eax, [r14]
0x18023f12d  cmp     [r14+0F8h], r13b
0x18023f134  jnz     short loc_18023F14B
0x18023f136  mov     rcx, [r15]; hEvent
0x18023f139  call    cs:__imp_SetEvent
0x18023f13f  mov     rcx, [rbp+5Fh]
0x18023f143  test    eax, eax
0x18023f145  jz      loc_18023F1EB
0x18023f14b  mov     ecx, 10h; Size
0x18023f150  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18023f155  lea     rcx, ?WorkerProc@ServiceMonitor@details@Util@Service@HNS@@AEAAXXZ; HNS::Service::Util::details::ServiceMonitor::WorkerProc(void)
0x18023f15c  mov     [rax], rcx
0x18023f15f  mov     [rax+8], r14
0x18023f163  mov     [rbp+57h+var_68], rax
0x18023f167  lea     rcx, [rbp+57h+var_78]
0x18023f16b  mov     [rsp+0C0h+var_98], rcx
0x18023f170  mov     dword ptr [rsp+0C0h+pcbBytesNeeded], r13d
0x18023f175  mov     r9, rax
0x18023f178  lea     r8, ??$_Invoke@V?$tuple@V?$_Binder@U_Unforced@std@@P8ServiceMonitor@details@Util@Service@HNS@@EAAXXZPEAV34567@@std@@@std@@$0A@@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<std::_Binder<std::_Unforced,void (HNS::Service::Util::details::ServiceMonitor::*)(void),HNS::Service::Util::details::ServiceMonitor *>>,0>(void *)
0x18023f17f  xor     edx, edx
0x18023f181  xor     ecx, ecx
0x18023f183  call    cs:__imp__o__beginthreadex
0x18023f189  mov     [rbp+57h+var_80], rax
0x18023f18d  test    rax, rax
0x18023f190  jz      short loc_18023F1DB
0x18023f192  cmp     [r14+18h], r13d
0x18023f196  jz      short loc_18023F19F
0x18023f198  call    cs:__imp__o_terminate
0x18023f19e  int     3; Trap to Debugger
0x18023f19f  mov     edx, [rbp+57h+var_78]
0x18023f1a2  mov     ecx, [rbp+57h+var_74]
0x18023f1a5  mov     [r14+10h], rax
0x18023f1a9  mov     [r14+18h], edx
0x18023f1ad  mov     [r14+1Ch], ecx
0x18023f1b1  mov     rax, r14
0x18023f1b4  mov     rcx, [rbp+57h+var_38]
0x18023f1b8  xor     rcx, rsp; StackCookie
0x18023f1bb  call    __security_check_cookie
0x18023f1c0  mov     rbx, [rsp+0C0h+arg_10]
0x18023f1c8  add     rsp, 90h
0x18023f1cf  pop     r15
0x18023f1d1  pop     r14
0x18023f1d3  pop     r13
0x18023f1d5  pop     r12
0x18023f1d7  pop     rdi
0x18023f1d8  pop     rsi
0x18023f1d9  pop     rbp
0x18023f1da  retn
0x18023f1db  mov     [rbp+57h+var_78], r13d
0x18023f1df  mov     ecx, 6
0x18023f1e4  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18023f1ea  nop
0x18023f1eb  mov     edx, 0A01h; void *
0x18023f1f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18023f1f6  mov     edx, 0A01h; void *
0x18023f1fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18023f201  mov     rcx, r12
0x18023f204  call    ??$?CVExternalAdapterResource@Resource@Service@HNS@@$0A@@?$shared_ptr@VExternalAdapterResource@Resource@Service@HNS@@@std@@QEBAPEAVExternalAdapterResource@Resource@Service@HNS@@XZ; std::shared_ptr<HNS::Service::Resource::ExternalAdapterResource>::operator-><HNS::Service::Resource::ExternalAdapterResource,0>(void)
0x18023f209  mov     rcx, [rbp+5Fh]; this
0x18023f20d  mov     [rsp+0C0h+pcbBytesNeeded], rax; char *
0x18023f212  lea     r9, aFailedToQueryS_0; "Failed to Query service status : %ws."
0x18023f219  lea     r8, aOnecoreVmDvNet_47; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x18023f220  mov     edx, 11Bh; void *
0x18023f225  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
