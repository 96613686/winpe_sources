# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180009084`
- end: `0x1800091ea`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000ab58`

## callees

- `0x180002d40`
- `0x1800082c8`
- `0x1800082e4`
- `0x180009084`
- `0x18000a738`
- `0x18000bdc8`
- `0x18000ddac`
- `0x18000e5f4`
- `0x18000eca0`
- `0x18000f924`
- `0x180010df0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009101`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009101`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800090bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800090bc`

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
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v11,
    Mutex);
  if ( v11 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      v12);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      goto LABEL_9;
    }
    v9 = v13;
    if ( v13 )
    {
      *a2 = v13;
      ++*v9;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180009084  mov     [rsp-8+arg_10], rbx
0x180009089  mov     [rsp-8+arg_18], rdi
0x18000908e  push    rbp
0x18000908f  lea     rbp, [rsp-170h]
0x180009097  sub     rsp, 270h
0x18000909e  mov     rax, cs:__security_cookie
0x1800090a5  xor     rax, rsp
0x1800090a8  mov     [rbp+170h+var_10], rax
0x1800090af  mov     rdi, rdx
0x1800090b2  mov     qword ptr [rdx], 0
0x1800090b9  mov     rbx, rcx
0x1800090bc  call    cs:__imp_GetCurrentProcessId
0x1800090c2  mov     [rsp+270h+var_248], rbx
0x1800090c7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800090ce  mov     r9d, eax
0x1800090d1  mov     [rsp+270h+var_250], 130h; int
0x1800090d9  mov     edx, 104h; unsigned __int64
0x1800090de  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800090e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800090e8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800090ee  mov     [rsp+270h+var_240], 0
0x1800090f7  xor     r8d, r8d; dwFlags
0x1800090fa  lea     rdx, [rsp+270h+Name]; lpName
0x1800090ff  xor     ecx, ecx; lpMutexAttributes
0x180009101  call    cs:__imp_CreateMutexExW
0x180009107  mov     rdx, rax
0x18000910a  lea     rcx, [rsp+270h+var_240]
0x18000910f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009114  cmp     [rsp+270h+var_240], 0
0x18000911a  jnz     short loc_180009125
0x18000911c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009121  mov     ebx, eax
0x180009123  jmp     short loc_180009198
0x180009125  lea     rdx, [rsp+270h+var_238]
0x18000912a  lea     rcx, [rsp+270h+var_240]
0x18000912f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180009134  lea     rdx, [rsp+270h+var_230]; void **
0x180009139  mov     [rsp+270h+var_230], 0
0x180009142  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009147  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000914c  mov     ebx, eax
0x18000914e  test    eax, eax
0x180009150  jns     short loc_180009179
0x180009152  mov     edx, 12Eh; void *
0x180009157  mov     rcx, [rbp+178h]; this
0x18000915e  lea     r8, aWil; "wil"
0x180009165  mov     r9d, eax; char *
0x180009168  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000916d  lea     rcx, [rsp+270h+var_238]
0x180009172  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009177  jmp     short loc_180009198
0x180009179  mov     rcx, [rsp+270h+var_230]
0x18000917e  test    rcx, rcx
0x180009181  jz      short loc_1800091C8
0x180009183  mov     [rdi], rcx
0x180009186  mov     eax, [rcx]
0x180009188  inc     eax
0x18000918a  mov     [rcx], eax
0x18000918c  lea     rcx, [rsp+270h+var_238]
0x180009191  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009196  xor     ebx, ebx
0x180009198  lea     rcx, [rsp+270h+var_240]
0x18000919d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800091a2  mov     eax, ebx
0x1800091a4  mov     rcx, [rbp+170h+var_10]
0x1800091ab  xor     rcx, rsp; StackCookie
0x1800091ae  call    __security_check_cookie
0x1800091b3  lea     r11, [rsp+270h+var_s0]
0x1800091bb  mov     rbx, [r11+20h]
0x1800091bf  mov     rdi, [r11+28h]
0x1800091c3  mov     rsp, r11
0x1800091c6  pop     rbp
0x1800091c7  retn
0x1800091c8  mov     r8, rdi
0x1800091cb  lea     rdx, [rsp+270h+var_240]
0x1800091d0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800091d5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800091da  mov     ebx, eax
0x1800091dc  test    eax, eax
0x1800091de  jns     short loc_18000918C
0x1800091e0  mov     edx, 137h
0x1800091e5  jmp     loc_180009157
```
