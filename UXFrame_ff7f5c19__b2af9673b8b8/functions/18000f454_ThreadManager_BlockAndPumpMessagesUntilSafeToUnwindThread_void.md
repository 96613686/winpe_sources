# ThreadManager::BlockAndPumpMessagesUntilSafeToUnwindThread(void)

- ea: `0x18000f454`
- end: `0x18000f525`
- name: `?BlockAndPumpMessagesUntilSafeToUnwindThread@ThreadManager@@AEAAXXZ`
- size: `209`
- prototype: `void __fastcall(ThreadManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016660`

## callees

- `0x180002b20`
- `0x18000e360`
- `0x18000f454`
- `0x180016bac`
- `0x180016eb8`
- `0x180016ee4`
- `0x180017a90`
- `0x18001a878`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000f49e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000f49e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4ac`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000f4ec`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000f4ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ThreadManager::BlockAndPumpMessagesUntilSafeToUnwindThread(ThreadManager *this)
{
  DWORD v1; // ebx
  void *v2; // rdx
  HANDLE Event; // rdi
  unsigned int v4; // r8d
  const char *v5; // r9
  void *v6; // [rsp+30h] [rbp-28h] BYREF
  DWORD dwindex; // [rsp+38h] [rbp-20h] BYREF
  HANDLE pHandles; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  fc::config_property_base::ensure_initialized((fc::config_property_base *)qword_180073810);
  v1 = dwTimeout;
  if ( dwTimeout )
  {
    UXFrameTelemetry::XamlThreadShutdown_WaitingForSafeThreadUnwind_Start();
    v6 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( !Event )
      wil::details::in1diag3::Throw_GetLastError(retaddr, v2, v4, v5);
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v6,
      Event);
    dwindex = 0;
    pHandles = v6;
    CoWaitForMultipleHandles(0x18u, v1, 1u, &pHandles, &dwindex);
    UXFrameTelemetry::XamlThreadShutdown_WaitingForSafeThreadUnwind_Stop();
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v6);
  }
}

```

## disassembly

```asm
0x18000f454  mov     [rsp+arg_0], rbx
0x18000f459  push    rdi
0x18000f45a  sub     rsp, 50h
0x18000f45e  mov     rax, cs:__security_cookie
0x18000f465  xor     rax, rsp
0x18000f468  mov     [rsp+58h+var_10], rax
0x18000f46d  lea     rcx, qword_180073810; this
0x18000f474  call    ?ensure_initialized@config_property_base@fc@@IEAAXXZ; fc::config_property_base::ensure_initialized(void)
0x18000f479  mov     ebx, cs:dwTimeout
0x18000f47f  test    ebx, ebx
0x18000f481  jz      short loc_18000F502
0x18000f483  call    ?XamlThreadShutdown_WaitingForSafeThreadUnwind_Start@UXFrameTelemetry@@SAXXZ; UXFrameTelemetry::XamlThreadShutdown_WaitingForSafeThreadUnwind_Start(void)
0x18000f488  mov     [rsp+58h+var_28], 0
0x18000f491  mov     r9d, 1F0003h; dwDesiredAccess
0x18000f497  xor     r8d, r8d; dwFlags
0x18000f49a  xor     edx, edx; lpName
0x18000f49c  xor     ecx, ecx; lpEventAttributes
0x18000f49e  call    cs:__imp_CreateEventExW
0x18000f4a4  mov     rdi, rax
0x18000f4a7  test    rax, rax
0x18000f4aa  jz      short loc_18000F51A
0x18000f4ac  call    cs:__imp_GetLastError
0x18000f4b2  mov     rdx, rdi
0x18000f4b5  lea     rcx, [rsp+58h+var_28]
0x18000f4ba  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000f4bf  mov     [rsp+58h+dwindex], 0
0x18000f4c7  mov     rax, [rsp+58h+var_28]
0x18000f4cc  mov     [rsp+58h+pHandles], rax
0x18000f4d1  lea     rax, [rsp+58h+dwindex]
0x18000f4d6  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x18000f4db  lea     r9, [rsp+58h+pHandles]; pHandles
0x18000f4e0  mov     r8d, 1; cHandles
0x18000f4e6  mov     edx, ebx; dwTimeout
0x18000f4e8  lea     ecx, [r8+17h]; dwFlags
0x18000f4ec  call    cs:__imp_CoWaitForMultipleHandles
0x18000f4f2  call    ?XamlThreadShutdown_WaitingForSafeThreadUnwind_Stop@UXFrameTelemetry@@SAXXZ; UXFrameTelemetry::XamlThreadShutdown_WaitingForSafeThreadUnwind_Stop(void)
0x18000f4f7  nop
0x18000f4f8  lea     rcx, [rsp+58h+var_28]
0x18000f4fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f502  mov     rcx, [rsp+58h+var_10]
0x18000f507  xor     rcx, rsp; StackCookie
0x18000f50a  call    __security_check_cookie
0x18000f50f  mov     rbx, [rsp+58h+arg_0]
0x18000f514  add     rsp, 50h
0x18000f518  pop     rdi
0x18000f519  retn
0x18000f51a  mov     rcx, [rsp+58h]; this
0x18000f51f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
