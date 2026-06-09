# NTUserService::ServiceMain(ulong,ushort * * const)

- ea: `0x18001c3a8`
- end: `0x18001c631`
- name: `?ServiceMain@NTUserService@@QEAAXKQEAPEAG@Z`
- size: `649`
- prototype: `void __fastcall(NTUserService *__hidden this, unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180019250`

## callees

- `0x180001008`
- `0x180001064`
- `0x18000c810`
- `0x180018bb0`
- `0x18001b1f0`
- `0x18001b92c`
- `0x18001c284`
- `0x18001c3a8`
- `0x18001c638`
- `0x18001fb30`
- `0x18001ffd4`
- `0x180025a14`
- `0x180027618`
- `0x18002c570`
- `0x18004117c`
- `0x1800545a4`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c46b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c46b`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001c551`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001c551`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18001c576`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18001c576`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001c45c`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001c45c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NTUserService::ServiceMain(HANDLE *this, __int64 a2, LPCWSTR *a3)
{
  __int64 v5; // r8
  SERVICE_STATUS_HANDLE v6; // rax
  signed int LastError; // eax
  unsigned __int8 v8; // dl
  signed int updated; // r12d
  _QWORD *v10; // r15
  __int64 (__fastcall *v11)(HANDLE *, LPCWSTR, HANDLE, HANDLE, HANDLE *, int); // r15
  HANDLE v12; // rbx
  HANDLE v13; // rdi
  LPCWSTR v14; // rsi
  int v15; // eax
  char *v16; // rdi
  std::thread *v17; // rax
  __int64 v18; // r8
  HANDLE *v19; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v20[16]; // [rsp+48h] [rbp-21h] BYREF
  int v21; // [rsp+58h] [rbp-11h] BYREF
  char v22; // [rsp+5Ch] [rbp-Dh]

  v21 = 0;
  v22 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v21);
  if ( (unsigned int)dword_180094048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180094048, 0x400000000000LL, v5) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180094048,
      (__int64)&word_180083CC6);
  v6 = RegisterServiceCtrlHandlerExW(*a3, NTUserService::ServiceHandlerThunk, this);
  this[3] = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    updated = LastError;
    if ( LastError > 0 )
      updated = (unsigned __int16)LastError | 0x80070000;
    if ( updated < 0 )
      goto LABEL_21;
  }
  updated = NTUserService::UpdateServiceStatus((NTUserService *)this, 2u, 0, 0x2710u);
  if ( updated < 0 )
    goto LABEL_21;
  updated = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this + 2);
  if ( updated < 0 )
    goto LABEL_21;
  v10 = this[6];
  if ( !v10 || !this[7] )
  {
    updated = -2147418113;
LABEL_21:
    NTUserService::ServiceStopCallback((NTUserService *)this, v8);
    goto LABEL_22;
  }
  v11 = (__int64 (__fastcall *)(HANDLE *, LPCWSTR, HANDLE, HANDLE, HANDLE *, int))v10[24];
  v12 = this[7];
  v13 = this[2];
  v14 = *a3;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int UnregisterWait(void *)>>::reset(
    this + 5,
    0);
  v15 = v11(this + 5, v14, v13, v12, this, 24);
  if ( v15 )
  {
    if ( v15 > 0 )
      updated = (unsigned __int16)v15 | 0x80070000;
    else
      updated = v15;
    goto LABEL_21;
  }
  v16 = (char *)this[4];
  if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v19);
    PowerSettingUnregisterNotification(v16);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v19);
  }
  this[4] = 0;
  PowerSettingRegisterNotification(&GUID_LOW_POWER_EPOCH, 1u, this[3], this + 4);
  v19 = this;
  v17 = (std::thread *)std::thread::thread__lambda_f3d8809f5612c984a5365a493d0aaa66__0_(v20, &v19);
  std::thread::detach(v17);
  std::thread::~thread((std::thread *)v20);
LABEL_22:
  v21 = 2;
  if ( (unsigned int)dword_180094048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180094048, 0x400000000000LL, v18) )
  {
    LODWORD(v19) = updated;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180094048,
      (__int64)byte_180083CDB);
  }
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v21);
}

```

## disassembly

```asm
0x18001c3a8  mov     [rsp-8+arg_8], rbx
0x18001c3ad  push    rbp
0x18001c3ae  push    rsi
0x18001c3af  push    rdi
0x18001c3b0  push    r12
0x18001c3b2  push    r13
0x18001c3b4  push    r14
0x18001c3b6  push    r15
0x18001c3b8  lea     rbp, [rsp-27h]
0x18001c3bd  sub     rsp, 90h
0x18001c3c4  mov     rax, cs:__security_cookie
0x18001c3cb  xor     rax, rsp
0x18001c3ce  mov     [rbp+57h+var_40], rax
0x18001c3d2  mov     rsi, r8
0x18001c3d5  mov     r13, rcx
0x18001c3d8  xor     r14d, r14d
0x18001c3db  mov     [rbp+57h+var_68], r14d
0x18001c3df  mov     [rbp+57h+var_64], r14b
0x18001c3e3  lea     rcx, [rbp+57h+var_68]
0x18001c3e7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18001c3ec  mov     eax, cs:dword_180094048
0x18001c3f2  cmp     eax, 5
0x18001c3f5  jbe     short loc_18001C44F
0x18001c3f7  mov     rdx, 400000000000h
0x18001c401  lea     rcx, dword_180094048
0x18001c408  call    _tlgKeywordOn
0x18001c40d  test    al, al
0x18001c40f  jz      short loc_18001C44F
0x18001c411  cmp     [rbp+57h+var_64], r14b
0x18001c415  jz      short loc_18001C435
0x18001c417  cmp     [rbp+57h+var_50], r14d
0x18001c41b  jnz     short loc_18001C42F
0x18001c41d  cmp     [rbp+57h+var_4C], r14d
0x18001c421  jnz     short loc_18001C42F
0x18001c423  cmp     [rbp+57h+var_48], r14d
0x18001c427  jnz     short loc_18001C42F
0x18001c429  cmp     [rbp+57h+var_44], r14d
0x18001c42d  jz      short loc_18001C435
0x18001c42f  lea     r9, [rbp+57h+var_50]
0x18001c433  jmp     short loc_18001C438
0x18001c435  mov     r9, r14
0x18001c438  lea     r8, [rbp+57h+var_60]
0x18001c43c  lea     rdx, word_180083CC6
0x18001c443  lea     rcx, dword_180094048
0x18001c44a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001c44f  mov     r8, r13; lpContext
0x18001c452  lea     rdx, ?ServiceHandlerThunk@NTUserService@@CAKKKPEAX0@Z; lpHandlerProc
0x18001c459  mov     rcx, [rsi]; lpServiceName
0x18001c45c  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18001c462  mov     [r13+18h], rax
0x18001c466  test    rax, rax
0x18001c469  jnz     short loc_18001C48C
0x18001c46b  call    cs:__imp_GetLastError
0x18001c471  mov     r12d, eax
0x18001c474  test    eax, eax
0x18001c476  jle     short loc_18001C483
0x18001c478  movzx   r12d, ax
0x18001c47c  or      r12d, 80070000h
0x18001c483  test    r12d, r12d
0x18001c486  js      loc_18001C5A8
0x18001c48c  mov     r9d, 2710h; unsigned int
0x18001c492  xor     r8d, r8d; unsigned int
0x18001c495  lea     edx, [r8+2]; unsigned int
0x18001c499  mov     rcx, r13; this
0x18001c49c  call    ?UpdateServiceStatus@NTUserService@@IEAAJKKK@Z; NTUserService::UpdateServiceStatus(ulong,ulong,ulong)
0x18001c4a1  mov     r12d, eax
0x18001c4a4  test    eax, eax
0x18001c4a6  js      loc_18001C5A8
0x18001c4ac  lea     rcx, [r13+10h]
0x18001c4b0  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001c4b5  mov     r12d, eax
0x18001c4b8  test    eax, eax
0x18001c4ba  js      loc_18001C5A8
0x18001c4c0  mov     r15, [r13+30h]
0x18001c4c4  test    r15, r15
0x18001c4c7  jz      loc_18001C5A2
0x18001c4cd  cmp     [r13+38h], r14
0x18001c4d1  jz      loc_18001C5A2
0x18001c4d7  mov     r15, [r15+0C0h]
0x18001c4de  mov     rbx, [r13+38h]
0x18001c4e2  mov     rdi, [r13+10h]
0x18001c4e6  mov     rsi, [rsi]
0x18001c4e9  xor     edx, edx
0x18001c4eb  lea     rcx, [r13+28h]
0x18001c4ef  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?UnregisterWait@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&UnregisterWait(void *)>>::reset(void *)
0x18001c4f4  mov     [rsp+0C0h+var_98], 18h
0x18001c4fc  mov     [rsp+0C0h+var_A0], r13
0x18001c501  mov     r9, rbx
0x18001c504  mov     r8, rdi
0x18001c507  mov     rdx, rsi
0x18001c50a  lea     rcx, [r13+28h]
0x18001c50e  mov     rax, r15
0x18001c511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c516  xor     r14d, r14d
0x18001c519  test    eax, eax
0x18001c51b  jz      short loc_18001C534
0x18001c51d  jg      short loc_18001C524
0x18001c51f  mov     r12d, eax
0x18001c522  jmp     short loc_18001C52F
0x18001c524  movzx   r12d, ax
0x18001c528  or      r12d, 80070000h
0x18001c52f  test    r12d, r12d
0x18001c532  js      short loc_18001C5A8
0x18001c534  lea     rbx, [r13+20h]
0x18001c538  mov     rdi, [rbx]
0x18001c53b  lea     rax, [rdi-1]
0x18001c53f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c543  ja      short loc_18001C560
0x18001c545  lea     rcx, [rbp+57h+var_80]; this
0x18001c549  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001c54e  mov     rcx, rdi; RegistrationHandle
0x18001c551  call    cs:__imp_PowerSettingUnregisterNotification
0x18001c557  lea     rcx, [rbp+57h+var_80]; this
0x18001c55b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001c560  mov     [rbx], r14
0x18001c563  mov     r9, rbx; RegistrationHandle
0x18001c566  mov     r8, [r13+18h]; Recipient
0x18001c56a  mov     edx, 1; Flags
0x18001c56f  lea     rcx, GUID_LOW_POWER_EPOCH; SettingGuid
0x18001c576  call    cs:__imp_PowerSettingRegisterNotification
0x18001c57c  mov     [rbp+57h+var_80], r13
0x18001c580  lea     rdx, [rbp+57h+var_80]
0x18001c584  lea     rcx, [rbp+57h+var_78]
0x18001c588  call    std__thread__thread__lambda_f3d8809f5612c984a5365a493d0aaa66__0_
0x18001c58d  nop
0x18001c58e  mov     rcx, rax; this
0x18001c591  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x18001c596  nop
0x18001c597  lea     rcx, [rbp+57h+var_78]; this
0x18001c59b  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18001c5a0  jmp     short loc_18001C5B0
0x18001c5a2  mov     r12d, 8000FFFFh
0x18001c5a8  mov     rcx, r13; this
0x18001c5ab  call    ?ServiceStopCallback@NTUserService@@QEAAXE@Z; NTUserService::ServiceStopCallback(uchar)
0x18001c5b0  mov     [rbp+57h+var_68], 2
0x18001c5b7  mov     eax, cs:dword_180094048
0x18001c5bd  cmp     eax, 5
0x18001c5c0  jbe     short loc_18001C601
0x18001c5c2  mov     rdx, 400000000000h
0x18001c5cc  lea     rcx, dword_180094048
0x18001c5d3  call    _tlgKeywordOn
0x18001c5d8  test    al, al
0x18001c5da  jz      short loc_18001C601
0x18001c5dc  mov     dword ptr [rbp+57h+var_80], r12d
0x18001c5e0  lea     rax, [rbp+57h+var_80]
0x18001c5e4  mov     [rsp+0C0h+var_A0], rax
0x18001c5e9  lea     r8, [rbp+57h+var_60]
0x18001c5ed  lea     rdx, byte_180083CDB
0x18001c5f4  lea     rcx, dword_180094048
0x18001c5fb  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001c600  nop
0x18001c601  lea     rcx, [rbp+57h+var_68]
0x18001c605  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18001c60a  mov     rcx, [rbp+57h+var_40]
0x18001c60e  xor     rcx, rsp; StackCookie
0x18001c611  call    __security_check_cookie
0x18001c616  mov     rbx, [rsp+0C0h+arg_8]
0x18001c61e  add     rsp, 90h
0x18001c625  pop     r15
0x18001c627  pop     r14
0x18001c629  pop     r13
0x18001c62b  pop     r12
0x18001c62d  pop     rdi
0x18001c62e  pop     rsi
0x18001c62f  pop     rbp
0x18001c630  retn
```
