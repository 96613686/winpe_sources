# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800764dc`
- end: `0x18007663b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18007775c`

## callees

- `0x180075ff8`
- `0x180076014`
- `0x1800764dc`
- `0x180077528`
- `0x1800784d0`
- `0x180079cec`
- `0x18007a308`
- `0x18007a724`
- `0x18007af40`
- `0x18007b218`
- `0x180091140`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180076514`
- `KERNEL32!GetCurrentProcessId` at `0x180076514`
- `KERNEL32!CreateMutexExW` at `0x180076559`
- `KERNEL32!CreateMutexExW` at `0x180076559`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800764dc  mov     [rsp-8+arg_10], rbx
0x1800764e1  mov     [rsp-8+arg_18], rdi
0x1800764e6  push    rbp
0x1800764e7  lea     rbp, [rsp-170h]
0x1800764ef  sub     rsp, 270h
0x1800764f6  mov     rax, cs:__security_cookie
0x1800764fd  xor     rax, rsp
0x180076500  mov     [rbp+170h+var_10], rax
0x180076507  mov     rdi, rdx
0x18007650a  mov     qword ptr [rdx], 0
0x180076511  mov     rbx, rcx
0x180076514  call    cs:__imp_GetCurrentProcessId
0x18007651a  mov     [rsp+270h+var_248], rbx
0x18007651f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180076526  mov     r9d, eax
0x180076529  mov     [rsp+270h+var_250], 130h; int
0x180076531  mov     edx, 104h; unsigned __int64
0x180076536  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007653b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180076540  mov     r9d, 1F0001h; dwDesiredAccess
0x180076546  mov     [rsp+270h+var_240], 0
0x18007654f  xor     r8d, r8d; dwFlags
0x180076552  lea     rdx, [rsp+270h+Name]; lpName
0x180076557  xor     ecx, ecx; lpMutexAttributes
0x180076559  call    cs:__imp_CreateMutexExW
0x18007655f  mov     rdx, rax
0x180076562  lea     rcx, [rsp+270h+var_240]
0x180076567  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18007656c  cmp     [rsp+270h+var_240], 0
0x180076572  jnz     short loc_18007657D
0x180076574  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180076579  mov     ebx, eax
0x18007657b  jmp     short loc_1800765E9
0x18007657d  lea     rdx, [rsp+270h+var_238]
0x180076582  lea     rcx, [rsp+270h+var_240]
0x180076587  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18007658c  lea     rdx, [rsp+270h+var_230]; void **
0x180076591  mov     [rsp+270h+var_230], 0
0x18007659a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007659f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800765a4  mov     ebx, eax
0x1800765a6  test    eax, eax
0x1800765a8  jns     short loc_1800765CA
0x1800765aa  mov     edx, 12Eh; void *
0x1800765af  mov     rcx, [rbp+178h]; this
0x1800765b6  mov     r9d, eax; char *
0x1800765b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800765be  lea     rcx, [rsp+270h+var_238]
0x1800765c3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800765c8  jmp     short loc_1800765E9
0x1800765ca  mov     rcx, [rsp+270h+var_230]
0x1800765cf  test    rcx, rcx
0x1800765d2  jz      short loc_180076619
0x1800765d4  mov     [rdi], rcx
0x1800765d7  mov     eax, [rcx]
0x1800765d9  inc     eax
0x1800765db  mov     [rcx], eax
0x1800765dd  lea     rcx, [rsp+270h+var_238]
0x1800765e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800765e7  xor     ebx, ebx
0x1800765e9  lea     rcx, [rsp+270h+var_240]
0x1800765ee  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800765f3  mov     eax, ebx
0x1800765f5  mov     rcx, [rbp+170h+var_10]
0x1800765fc  xor     rcx, rsp; StackCookie
0x1800765ff  call    __security_check_cookie
0x180076604  lea     r11, [rsp+270h+var_s0]
0x18007660c  mov     rbx, [r11+20h]
0x180076610  mov     rdi, [r11+28h]
0x180076614  mov     rsp, r11
0x180076617  pop     rbp
0x180076618  retn
0x180076619  mov     r8, rdi
0x18007661c  lea     rdx, [rsp+270h+var_240]
0x180076621  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180076626  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18007662b  mov     ebx, eax
0x18007662d  test    eax, eax
0x18007662f  jns     short loc_1800765DD
0x180076631  mov     edx, 137h
0x180076636  jmp     loc_1800765AF
```
