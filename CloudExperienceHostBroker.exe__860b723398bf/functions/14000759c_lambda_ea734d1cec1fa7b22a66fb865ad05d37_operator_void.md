# _lambda_ea734d1cec1fa7b22a66fb865ad05d37_::operator()(void)

- ea: `0x14000759c`
- end: `0x140007719`
- name: `??R_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@QEBAJXZ`
- size: `381`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140008950`

## callees

- `0x14000330c`
- `0x140003cc8`
- `0x140004340`
- `0x140004d74`
- `0x140005f54`
- `0x1400074c8`
- `0x14000759c`
- `0x1400089e0`
- `0x140008fac`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140007692`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140007692`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1400075c8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1400075c8`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400076d3`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400076d3`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1400076ac`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1400076ac`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000760e`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000760e`

## string_xrefs

- `0x14000761f`: `onecoreuap\internal\shell\inc\private\createobjectservertaskbase.h`
- `0x14000765e`: `onecoreuap\internal\shell\inc\private\createobjectservertaskbase.h`
- `0x1400076bb`: `onecoreuap\internal\shell\inc\private\createobjectservertaskbase.h`
- `0x1400076e2`: `onecoreuap\internal\shell\inc\private\createobjectservertaskbase.h`

## pseudocode

```c
__int64 __fastcall _lambda_ea734d1cec1fa7b22a66fb865ad05d37_::operator()(__int64 *a1)
{
  __int64 v1; // r8
  HANDLE v3; // rax
  wil::details *v4; // rcx
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int LastErrorFailHr; // eax
  DWORD v9; // ebx
  HRESULT v10; // eax
  HRESULT v11; // eax
  int lpdwRegister; // [rsp+20h] [rbp-18h]
  int lpdwRegistera; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD dwRegister; // [rsp+40h] [rbp+8h] BYREF
  __int64 v16; // [rsp+48h] [rbp+10h] BYREF
  char v17; // [rsp+50h] [rbp+18h] BYREF

  v1 = *a1;
  dwRegister = 0;
  v16 = 0;
  v3 = OpenEventW(0x1F0003u, 0, *(LPCWSTR *)(v1 + 72));
  if ( v3 )
  {
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v16,
      v3);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v4);
    v6 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\createobjectservertaskbase.h",
        (const char *)(unsigned int)LastErrorFailHr,
        lpdwRegister);
      goto LABEL_5;
    }
  }
  _SetEvent_scope_exit___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_XZ(
    &v16,
    &v17);
  v5 = CoRegisterClassObject((const IID *const)(*a1 + 56), (LPUNKNOWN)a1[1], 4u, 1u, &dwRegister);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\createobjectservertaskbase.h",
      (const char *)(unsigned int)v5,
      lpdwRegistera);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
LABEL_5:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v16);
    return v6;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v16);
  v9 = WaitForSingleObject(*(HANDLE *)(*a1 + 88), *(_DWORD *)(*a1 + 96));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(*a1 + 80);
  v10 = CoDisconnectObject((LPUNKNOWN)a1[1], 0);
  if ( v10 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\createobjectservertaskbase.h",
      (const char *)(unsigned int)v10,
      lpdwRegistera);
  v11 = CoRevokeClassObject(dwRegister);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\createobjectservertaskbase.h",
      (const char *)(unsigned int)v11,
      lpdwRegistera);
  if ( v9 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1[2] + 32LL))(a1[2], 0);
  return 0;
}

```

## disassembly

```asm
0x14000759c  mov     [rsp+arg_18], rbx
0x1400075a1  push    rdi
0x1400075a2  sub     rsp, 30h
0x1400075a6  mov     r8, [rcx]
0x1400075a9  mov     rdi, rcx
0x1400075ac  mov     [rsp+38h+dwRegister], 0
0x1400075b4  xor     edx, edx; bInheritHandle
0x1400075b6  mov     ecx, 1F0003h; dwDesiredAccess
0x1400075bb  mov     [rsp+38h+arg_8], 0
0x1400075c4  mov     r8, [r8+48h]; lpName
0x1400075c8  call    cs:__imp_OpenEventW
0x1400075ce  test    rax, rax
0x1400075d1  jz      short loc_14000764E
0x1400075d3  mov     rdx, rax
0x1400075d6  lea     rcx, [rsp+38h+arg_8]
0x1400075db  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400075e0  lea     rdx, [rsp+38h+arg_10]
0x1400075e5  lea     rcx, [rsp+38h+arg_8]
0x1400075ea  call    ?SetEvent_scope_exit@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x1400075ef  mov     rcx, [rdi]
0x1400075f2  lea     rax, [rsp+38h+dwRegister]
0x1400075f7  mov     rdx, [rdi+8]; pUnk
0x1400075fb  mov     r9d, 1; flags
0x140007601  add     rcx, 38h ; '8'; rclsid
0x140007605  mov     qword ptr [rsp+38h+lpdwRegister], rax; int
0x14000760a  lea     r8d, [r9+3]; dwClsContext
0x14000760e  call    cs:__imp_CoRegisterClassObject
0x140007614  mov     ebx, eax
0x140007616  test    eax, eax
0x140007618  jns     short loc_140007674
0x14000761a  mov     rcx, [rsp+38h]; this
0x14000761f  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x140007626  mov     r9d, eax; char *
0x140007629  mov     edx, 2Bh ; '+'; void *
0x14000762e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007633  lea     rcx, [rsp+38h+arg_10]
0x140007638  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000763d  lea     rcx, [rsp+38h+arg_8]
0x140007642  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007647  mov     eax, ebx
0x140007649  jmp     loc_14000770E
0x14000764e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140007653  mov     ebx, eax
0x140007655  test    eax, eax
0x140007657  jns     short loc_1400075E0
0x140007659  mov     rcx, [rsp+38h]; this
0x14000765e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x140007665  mov     r9d, eax; char *
0x140007668  mov     edx, 26h ; '&'; void *
0x14000766d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007672  jmp     short loc_14000763D
0x140007674  lea     rcx, [rsp+38h+arg_10]
0x140007679  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000767e  lea     rcx, [rsp+38h+arg_8]
0x140007683  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007688  mov     rcx, [rdi]
0x14000768b  mov     edx, [rcx+60h]; dwMilliseconds
0x14000768e  mov     rcx, [rcx+58h]; hHandle
0x140007692  call    cs:__imp_WaitForSingleObject
0x140007698  mov     rcx, [rdi]
0x14000769b  mov     ebx, eax
0x14000769d  add     rcx, 50h ; 'P'
0x1400076a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400076a6  mov     rcx, [rdi+8]; pUnk
0x1400076aa  xor     edx, edx; dwReserved
0x1400076ac  call    cs:__imp_CoDisconnectObject
0x1400076b2  test    eax, eax
0x1400076b4  jns     short loc_1400076CF
0x1400076b6  mov     rcx, [rsp+38h]; this
0x1400076bb  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1400076c2  mov     r9d, eax; char *
0x1400076c5  mov     edx, 34h ; '4'; void *
0x1400076ca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400076cf  mov     ecx, [rsp+38h+dwRegister]; dwRegister
0x1400076d3  call    cs:__imp_CoRevokeClassObject
0x1400076d9  test    eax, eax
0x1400076db  jns     short loc_1400076F6
0x1400076dd  mov     rcx, [rsp+38h]; this
0x1400076e2  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1400076e9  mov     r9d, eax; char *
0x1400076ec  mov     edx, 35h ; '5'; void *
0x1400076f1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400076f6  test    ebx, ebx
0x1400076f8  jz      short loc_14000770C
0x1400076fa  mov     rcx, [rdi+10h]
0x1400076fe  xor     edx, edx
0x140007700  mov     rax, [rcx]
0x140007703  mov     rax, [rax+20h]
0x140007707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000770c  xor     eax, eax
0x14000770e  mov     rbx, [rsp+38h+arg_18]
0x140007713  add     rsp, 30h
0x140007717  pop     rdi
0x140007718  retn
```
