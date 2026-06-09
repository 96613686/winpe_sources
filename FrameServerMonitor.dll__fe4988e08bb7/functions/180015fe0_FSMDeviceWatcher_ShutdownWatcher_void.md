# FSMDeviceWatcher::ShutdownWatcher(void)

- ea: `0x180015fe0`
- end: `0x1800160ab`
- name: `?ShutdownWatcher@FSMDeviceWatcher@@UEAAJXZ`
- size: `203`
- prototype: `__int64 __fastcall(FSMDeviceWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e6dc`

## callees

- `0x180003730`
- `0x1800056a8`
- `0x180006a68`
- `0x18000e100`
- `0x180015fe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015ff1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015ff1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016075`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016075`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180016030`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180016030`
- `MFPlat!MFUnlockWorkQueue` at `0x180016064`
- `MFPlat!MFUnlockWorkQueue` at `0x180016064`

## string_xrefs

- `0x180016099`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall FSMDeviceWatcher::ShutdownWatcher(FSMDeviceWatcher *this)
{
  int v2; // eax
  char *v3; // rdi
  void *v4; // rcx
  DWORD v5; // eax
  const char *v6; // r9
  DWORD v7; // ecx
  __int64 v8; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v2 = *((_DWORD *)this + 26);
  v3 = (char *)*((_QWORD *)this + 21);
  *((_QWORD *)this + 21) = 0;
  if ( !v2 )
    v2 = -1072873851;
  v4 = (void *)*((_QWORD *)this + 23);
  *((_DWORD *)this + 26) = v2;
  if ( v4 )
  {
    v5 = WaitForSingleObjectEx(v4, 0xFA0u, 0);
    if ( v5 != 258 && v5 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xB0F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v6);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 184,
      0);
  }
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((__int64 *)this + 11);
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((__int64 *)this + 14);
  v7 = *((_DWORD *)this + 20);
  if ( v7 )
  {
    MFUnlockWorkQueue(v7);
    *((_DWORD *)this + 20) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( v3 )
    wistd::default_delete<FSMDeviceWatcherCMRegisterInfo [0]>::operator()<FSMDeviceWatcherCMRegisterInfo>(v8, v3);
  return 0;
}

```

## disassembly

```asm
0x180015fe0  push    rbx
0x180015fe2  push    rsi
0x180015fe3  push    rdi
0x180015fe4  push    r14
0x180015fe6  sub     rsp, 28h
0x180015fea  mov     rbx, rcx
0x180015fed  add     rcx, 28h ; '('; lpCriticalSection
0x180015ff1  call    cs:__imp_EnterCriticalSection
0x180015ff7  mov     eax, [rbx+68h]
0x180015ffa  lea     r14, [rbx+0B8h]
0x180016001  mov     rdi, [rbx+0A8h]
0x180016008  test    eax, eax
0x18001600a  mov     ecx, 0C00D3E85h
0x18001600f  mov     qword ptr [rbx+0A8h], 0
0x18001601a  cmovz   eax, ecx
0x18001601d  mov     rcx, [r14]; hHandle
0x180016020  mov     [rbx+68h], eax
0x180016023  test    rcx, rcx
0x180016026  jz      short loc_18001604B
0x180016028  xor     r8d, r8d; bAlertable
0x18001602b  mov     edx, 0FA0h; dwMilliseconds
0x180016030  call    cs:__imp_WaitForSingleObjectEx
0x180016036  cmp     eax, 102h
0x18001603b  jz      short loc_180016041
0x18001603d  test    eax, eax
0x18001603f  jnz     short loc_180016094
0x180016041  xor     edx, edx
0x180016043  mov     rcx, r14
0x180016046  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001604b  lea     rcx, [rbx+58h]
0x18001604f  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180016054  lea     rcx, [rbx+70h]
0x180016058  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18001605d  mov     ecx, [rbx+50h]; dwWorkQueue
0x180016060  test    ecx, ecx
0x180016062  jz      short loc_180016071
0x180016064  call    cs:__imp_MFUnlockWorkQueue
0x18001606a  mov     dword ptr [rbx+50h], 0
0x180016071  lea     rcx, [rbx+28h]; lpCriticalSection
0x180016075  call    cs:__imp_LeaveCriticalSection
0x18001607b  test    rdi, rdi
0x18001607e  jz      short loc_180016088
0x180016080  mov     rdx, rdi
0x180016083  call    ??$?RUFSMDeviceWatcherCMRegisterInfo@@@?$default_delete@$$BY0A@UFSMDeviceWatcherCMRegisterInfo@@@wistd@@QEBAXPEAUFSMDeviceWatcherCMRegisterInfo@@@Z; wistd::default_delete<FSMDeviceWatcherCMRegisterInfo [0]>::operator()<FSMDeviceWatcherCMRegisterInfo>(FSMDeviceWatcherCMRegisterInfo *)
0x180016088  xor     eax, eax
0x18001608a  add     rsp, 28h
0x18001608e  pop     r14
0x180016090  pop     rdi
0x180016091  pop     rsi
0x180016092  pop     rbx
0x180016093  retn
0x180016094  mov     rcx, [rsp+48h]; this
0x180016099  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800160a0  mov     edx, 0B0Fh; void *
0x1800160a5  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
