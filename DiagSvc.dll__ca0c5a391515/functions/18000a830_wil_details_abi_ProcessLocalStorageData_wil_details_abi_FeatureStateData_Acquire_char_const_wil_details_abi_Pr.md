# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000a830`
- end: `0x18000a98f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d258`

## callees

- `0x180003fc0`
- `0x180009f80`
- `0x180009f9c`
- `0x18000a830`
- `0x18000d060`
- `0x18000e0cc`
- `0x18001025c`
- `0x180011390`
- `0x180011808`
- `0x1800129dc`
- `0x180012d08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a8ad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a8ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a868`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a868`

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
0x18000a830  mov     [rsp-8+arg_10], rbx
0x18000a835  mov     [rsp-8+arg_18], rdi
0x18000a83a  push    rbp
0x18000a83b  lea     rbp, [rsp-170h]
0x18000a843  sub     rsp, 270h
0x18000a84a  mov     rax, cs:__security_cookie
0x18000a851  xor     rax, rsp
0x18000a854  mov     [rbp+170h+var_10], rax
0x18000a85b  mov     rdi, rdx
0x18000a85e  mov     qword ptr [rdx], 0
0x18000a865  mov     rbx, rcx
0x18000a868  call    cs:__imp_GetCurrentProcessId
0x18000a86e  mov     [rsp+270h+var_248], rbx
0x18000a873  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a87a  mov     r9d, eax
0x18000a87d  mov     [rsp+270h+var_250], 130h; int
0x18000a885  mov     edx, 104h; unsigned __int64
0x18000a88a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a88f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a894  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a89a  mov     [rsp+270h+var_240], 0
0x18000a8a3  xor     r8d, r8d; dwFlags
0x18000a8a6  lea     rdx, [rsp+270h+Name]; lpName
0x18000a8ab  xor     ecx, ecx; lpMutexAttributes
0x18000a8ad  call    cs:__imp_CreateMutexExW
0x18000a8b3  mov     rdx, rax
0x18000a8b6  lea     rcx, [rsp+270h+var_240]
0x18000a8bb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a8c0  cmp     [rsp+270h+var_240], 0
0x18000a8c6  jnz     short loc_18000A8D1
0x18000a8c8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a8cd  mov     ebx, eax
0x18000a8cf  jmp     short loc_18000A93D
0x18000a8d1  lea     rdx, [rsp+270h+var_238]
0x18000a8d6  lea     rcx, [rsp+270h+var_240]
0x18000a8db  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000a8e0  lea     rdx, [rsp+270h+var_230]; void **
0x18000a8e5  mov     [rsp+270h+var_230], 0
0x18000a8ee  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a8f3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000a8f8  mov     ebx, eax
0x18000a8fa  test    eax, eax
0x18000a8fc  jns     short loc_18000A91E
0x18000a8fe  mov     edx, 12Eh; void *
0x18000a903  mov     rcx, [rbp+178h]; this
0x18000a90a  mov     r9d, eax; char *
0x18000a90d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a912  lea     rcx, [rsp+270h+var_238]
0x18000a917  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a91c  jmp     short loc_18000A93D
0x18000a91e  mov     rcx, [rsp+270h+var_230]
0x18000a923  test    rcx, rcx
0x18000a926  jz      short loc_18000A96D
0x18000a928  mov     [rdi], rcx
0x18000a92b  mov     eax, [rcx]
0x18000a92d  inc     eax
0x18000a92f  mov     [rcx], eax
0x18000a931  lea     rcx, [rsp+270h+var_238]
0x18000a936  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a93b  xor     ebx, ebx
0x18000a93d  lea     rcx, [rsp+270h+var_240]
0x18000a942  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a947  mov     eax, ebx
0x18000a949  mov     rcx, [rbp+170h+var_10]
0x18000a950  xor     rcx, rsp; StackCookie
0x18000a953  call    __security_check_cookie
0x18000a958  lea     r11, [rsp+270h+var_s0]
0x18000a960  mov     rbx, [r11+20h]
0x18000a964  mov     rdi, [r11+28h]
0x18000a968  mov     rsp, r11
0x18000a96b  pop     rbp
0x18000a96c  retn
0x18000a96d  mov     r8, rdi
0x18000a970  lea     rdx, [rsp+270h+var_240]
0x18000a975  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a97a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000a97f  mov     ebx, eax
0x18000a981  test    eax, eax
0x18000a983  jns     short loc_18000A931
0x18000a985  mov     edx, 137h
0x18000a98a  jmp     loc_18000A903
```
