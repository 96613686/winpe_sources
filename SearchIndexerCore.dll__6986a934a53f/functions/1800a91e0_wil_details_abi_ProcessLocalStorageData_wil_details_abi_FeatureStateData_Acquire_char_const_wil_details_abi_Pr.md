# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800a91e0`
- end: `0x1800a9342`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800a9534`

## callees

- `0x1800789c0`
- `0x1800a8d5c`
- `0x1800a8d78`
- `0x1800a91e0`
- `0x1800aa658`
- `0x1800ab470`
- `0x1800ac75c`
- `0x1800ace98`
- `0x1800ad318`
- `0x1800adbac`
- `0x1800ade4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a9218`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a9218`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800a925d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800a925d`

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
0x1800a91e0  mov     [rsp-8+arg_10], rbx
0x1800a91e5  mov     [rsp-8+arg_18], rdi
0x1800a91ea  push    rbp
0x1800a91eb  lea     rbp, [rsp-170h]
0x1800a91f3  sub     rsp, 270h
0x1800a91fa  mov     rax, cs:__security_cookie
0x1800a9201  xor     rax, rsp
0x1800a9204  mov     [rbp+170h+var_10], rax
0x1800a920b  mov     rdi, rdx
0x1800a920e  mov     rbx, rcx
0x1800a9211  mov     qword ptr [rdx], 0
0x1800a9218  call    cs:__imp_GetCurrentProcessId
0x1800a921e  mov     r9d, eax
0x1800a9221  mov     [rsp+270h+var_248], rbx
0x1800a9226  mov     [rsp+270h+var_250], 130h; int
0x1800a922e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800a9235  mov     edx, 104h; unsigned __int64
0x1800a923a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800a923f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800a9244  mov     [rsp+270h+var_240], 0
0x1800a924d  mov     r9d, 1F0001h; dwDesiredAccess
0x1800a9253  xor     r8d, r8d; dwFlags
0x1800a9256  lea     rdx, [rsp+270h+Name]; lpName
0x1800a925b  xor     ecx, ecx; lpMutexAttributes
0x1800a925d  call    cs:__imp_CreateMutexExW
0x1800a9263  mov     rdx, rax
0x1800a9266  lea     rcx, [rsp+270h+var_240]
0x1800a926b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800a9270  cmp     [rsp+270h+var_240], 0
0x1800a9276  jnz     short loc_1800A9281
0x1800a9278  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800a927d  mov     ebx, eax
0x1800a927f  jmp     short loc_1800A92EF
0x1800a9281  lea     rdx, [rsp+270h+var_238]
0x1800a9286  lea     rcx, [rsp+270h+var_240]
0x1800a928b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800a9290  nop
0x1800a9291  mov     [rsp+270h+var_230], 0
0x1800a929a  lea     rdx, [rsp+270h+var_230]; void **
0x1800a929f  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800a92a4  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1800a92a9  mov     ebx, eax
0x1800a92ab  test    eax, eax
0x1800a92ad  jns     short loc_1800A92D0
0x1800a92af  mov     edx, 12Eh; void *
0x1800a92b4  mov     r9d, eax; char *
0x1800a92b7  mov     rcx, [rbp+178h]; this
0x1800a92be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a92c3  nop
0x1800a92c4  lea     rcx, [rsp+270h+var_238]
0x1800a92c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a92ce  jmp     short loc_1800A92EF
0x1800a92d0  mov     rcx, [rsp+270h+var_230]
0x1800a92d5  test    rcx, rcx
0x1800a92d8  jz      short loc_1800A931F
0x1800a92da  mov     [rdi], rcx
0x1800a92dd  mov     eax, [rcx]
0x1800a92df  inc     eax
0x1800a92e1  mov     [rcx], eax
0x1800a92e3  lea     rcx, [rsp+270h+var_238]
0x1800a92e8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a92ed  xor     ebx, ebx
0x1800a92ef  lea     rcx, [rsp+270h+var_240]
0x1800a92f4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a92f9  mov     eax, ebx
0x1800a92fb  mov     rcx, [rbp+170h+var_10]
0x1800a9302  xor     rcx, rsp; StackCookie
0x1800a9305  call    __security_check_cookie
0x1800a930a  lea     r11, [rsp+270h+var_s0]
0x1800a9312  mov     rbx, [r11+20h]
0x1800a9316  mov     rdi, [r11+28h]
0x1800a931a  mov     rsp, r11
0x1800a931d  pop     rbp
0x1800a931e  retn
0x1800a931f  mov     r8, rdi
0x1800a9322  lea     rdx, [rsp+270h+var_240]
0x1800a9327  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800a932c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800a9331  mov     ebx, eax
0x1800a9333  test    eax, eax
0x1800a9335  jns     short loc_1800A92E3
0x1800a9337  mov     edx, 137h
0x1800a933c  jmp     loc_1800A92B4
```
