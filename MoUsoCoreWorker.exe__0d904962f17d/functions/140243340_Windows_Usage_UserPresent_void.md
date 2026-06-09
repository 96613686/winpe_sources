# Windows::Usage::UserPresent(void)

- ea: `0x140243340`
- end: `0x1402434cb`
- name: `?UserPresent@Usage@Windows@@UEBA_NXZ`
- size: `395`
- prototype: `bool __fastcall(Windows::Usage *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14003c578`
- `0x140040364`
- `0x14004045c`
- `0x1400413a8`
- `0x14018b170`
- `0x140243340`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14024342b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14024342b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140243370`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140243370`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1402433db`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1402433db`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x140243401`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x140243401`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1402433c0`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1402433c0`

## string_xrefs

- `0x140243452`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140243468`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x14024347a`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x14024348f`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x1402434a7`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x1402434b9`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Windows::Usage::UserPresent(Windows::Usage *this)
{
  HANDLE EventW; // rax
  const char *v2; // r9
  DWORD v3; // eax
  DWORD v4; // eax
  const char *v5; // r9
  DWORD v6; // eax
  bool v7; // bl
  const char *v8; // r9
  HPOWERNOTIFY RegistrationHandle; // [rsp+20h] [rbp-30h] BYREF
  _QWORD Recipient[2]; // [rsp+28h] [rbp-28h] BYREF
  HANDLE hHandle; // [rsp+38h] [rbp-18h] BYREF
  __int64 v13; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  hHandle = 0;
  v13 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    EventW);
  if ( !hHandle )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xC1,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
      v2);
  RegistrationHandle = 0;
  Recipient[0] = Windows::Usage::UserPresent_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
  Recipient[1] = &hHandle;
  v3 = PowerSettingRegisterNotification(&GUID_GLOBAL_USER_PRESENCE, 2u, Recipient, &RegistrationHandle);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xE3,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
      (const char *)v3,
      (unsigned int)RegistrationHandle);
  v4 = WaitForSingleObject(hHandle, 0x7530u);
  if ( v4 == 258 )
  {
    if ( !(_DWORD)v13 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
        (const char *)0x800705B4LL,
        (int)RegistrationHandle);
  }
  else if ( v4 == -1 )
  {
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xED,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
      v5);
  }
  v6 = PowerSettingUnregisterNotification(RegistrationHandle);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xF2,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
      (const char *)(v6 != 0),
      (unsigned int)RegistrationHandle);
  v7 = HIDWORD(v13) == 0;
  if ( hHandle && !CloseHandle(hHandle) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9D1,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      v8);
  return v7;
}

```

## disassembly

```asm
0x140243340  mov     [rsp-8+arg_0], rbx
0x140243345  push    rbp
0x140243346  mov     rbp, rsp
0x140243349  sub     rsp, 50h
0x14024334d  mov     rax, cs:__security_cookie
0x140243354  xor     rax, rsp
0x140243357  mov     [rbp+var_8], rax
0x14024335b  xor     eax, eax
0x14024335d  mov     [rbp+hHandle], rax
0x140243361  mov     [rbp+var_10], rax
0x140243365  xor     r9d, r9d; lpName
0x140243368  xor     r8d, r8d; bInitialState
0x14024336b  lea     edx, [rax+1]; bManualReset
0x14024336e  xor     ecx, ecx; lpEventAttributes
0x140243370  call    cs:__imp_CreateEventW
0x140243376  mov     rdx, rax
0x140243379  lea     rcx, [rbp+hHandle]
0x14024337d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140243382  mov     rcx, [rbp+8]; this
0x140243386  cmp     [rbp+hHandle], 0
0x14024338b  jz      loc_14024347A
0x140243391  mov     [rbp+RegistrationHandle], 0
0x140243399  lea     rax, _Windows__Usage__UserPresent____2____lambda_1____lambda_invoker_cdecl_
0x1402433a0  mov     [rbp+Recipient], rax
0x1402433a4  lea     rax, [rbp+hHandle]
0x1402433a8  mov     [rbp+var_20], rax
0x1402433ac  lea     r9, [rbp+RegistrationHandle]; RegistrationHandle
0x1402433b0  lea     r8, [rbp+Recipient]; Recipient
0x1402433b4  mov     edx, 2; Flags
0x1402433b9  lea     rcx, GUID_GLOBAL_USER_PRESENCE; SettingGuid
0x1402433c0  call    cs:__imp_PowerSettingRegisterNotification
0x1402433c6  mov     rcx, [rbp+8]; this
0x1402433ca  test    eax, eax
0x1402433cc  jnz     loc_14024348C
0x1402433d2  mov     edx, 7530h; dwMilliseconds
0x1402433d7  mov     rcx, [rbp+hHandle]; hHandle
0x1402433db  call    cs:__imp_WaitForSingleObject
0x1402433e1  cmp     eax, 102h
0x1402433e6  jz      short loc_1402433EF
0x1402433e8  cmp     eax, 0FFFFFFFFh
0x1402433eb  jz      short loc_140243464
0x1402433ed  jmp     short loc_1402433FD
0x1402433ef  mov     rcx, [rbp+8]; this
0x1402433f3  cmp     dword ptr [rbp+var_10], 0
0x1402433f7  jz      loc_1402434A1
0x1402433fd  mov     rcx, [rbp+RegistrationHandle]; RegistrationHandle
0x140243401  call    cs:__imp_PowerSettingUnregisterNotification
0x140243407  xor     r9d, r9d
0x14024340a  test    eax, eax
0x14024340c  setnz   r9b; char *
0x140243410  mov     rcx, [rbp+8]; this
0x140243414  test    eax, eax
0x140243416  jnz     loc_1402434B9
0x14024341c  cmp     dword ptr [rbp+var_10+4], eax
0x14024341f  setz    bl
0x140243422  mov     rcx, [rbp+hHandle]; hObject
0x140243426  test    rcx, rcx
0x140243429  jz      short loc_140243435
0x14024342b  call    cs:__imp_CloseHandle
0x140243431  test    eax, eax
0x140243433  jz      short loc_14024344E
0x140243435  mov     al, bl
0x140243437  mov     rcx, [rbp+var_8]
0x14024343b  xor     rcx, rsp; StackCookie
0x14024343e  call    __security_check_cookie
0x140243443  mov     rbx, [rsp+50h+arg_0]
0x140243448  add     rsp, 50h
0x14024344c  pop     rbp
0x14024344d  retn
0x14024344e  mov     rcx, [rbp+8]; this
0x140243452  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140243459  mov     edx, 9D1h; void *
0x14024345e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140243464  mov     rcx, [rbp+8]; this
0x140243468  lea     r8, aCW1SSrcOrchest_10; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14024346f  mov     edx, 0EDh; void *
0x140243474  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14024347a  lea     r8, aCW1SSrcOrchest_10; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140243481  mov     edx, 0C1h; void *
0x140243486  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14024348c  mov     r9d, eax; char *
0x14024348f  lea     r8, aCW1SSrcOrchest_10; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140243496  mov     edx, 0E3h; void *
0x14024349b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1402434a1  mov     r9d, 800705B4h; char *
0x1402434a7  lea     r8, aCW1SSrcOrchest_10; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402434ae  mov     edx, 0EAh; void *
0x1402434b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402434b9  lea     r8, aCW1SSrcOrchest_10; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402434c0  mov     edx, 0F2h; void *
0x1402434c5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
