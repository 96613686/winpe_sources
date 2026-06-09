# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180140ab0`
- end: `0x180140c16`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180141878`

## callees

- `0x1801378fc`
- `0x18013bad0`
- `0x1801405c0`
- `0x1801405dc`
- `0x180140ab0`
- `0x1801423ac`
- `0x18014357c`
- `0x180143a74`
- `0x180143f40`
- `0x1801447a4`
- `0x180144a8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180140b2d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180140b2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180140ae8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180140ae8`

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
0x180140ab0  mov     [rsp-8+arg_10], rbx
0x180140ab5  mov     [rsp-8+arg_18], rdi
0x180140aba  push    rbp
0x180140abb  lea     rbp, [rsp-170h]
0x180140ac3  sub     rsp, 270h
0x180140aca  mov     rax, cs:__security_cookie
0x180140ad1  xor     rax, rsp
0x180140ad4  mov     [rbp+170h+var_10], rax
0x180140adb  mov     rdi, rdx
0x180140ade  mov     qword ptr [rdx], 0
0x180140ae5  mov     rbx, rcx
0x180140ae8  call    cs:__imp_GetCurrentProcessId
0x180140aee  mov     [rsp+270h+var_248], rbx
0x180140af3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180140afa  mov     r9d, eax
0x180140afd  mov     [rsp+270h+var_250], 130h; int
0x180140b05  mov     edx, 104h; unsigned __int64
0x180140b0a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180140b0f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180140b14  mov     r9d, 1F0001h; dwDesiredAccess
0x180140b1a  mov     [rsp+270h+var_240], 0
0x180140b23  xor     r8d, r8d; dwFlags
0x180140b26  lea     rdx, [rsp+270h+Name]; lpName
0x180140b2b  xor     ecx, ecx; lpMutexAttributes
0x180140b2d  call    cs:__imp_CreateMutexExW
0x180140b33  mov     rdx, rax
0x180140b36  lea     rcx, [rsp+270h+var_240]
0x180140b3b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180140b40  cmp     [rsp+270h+var_240], 0
0x180140b46  jnz     short loc_180140B51
0x180140b48  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180140b4d  mov     ebx, eax
0x180140b4f  jmp     short loc_180140BC4
0x180140b51  lea     rdx, [rsp+270h+var_238]
0x180140b56  lea     rcx, [rsp+270h+var_240]
0x180140b5b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180140b60  lea     rdx, [rsp+270h+var_230]; void **
0x180140b65  mov     [rsp+270h+var_230], 0
0x180140b6e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180140b73  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180140b78  mov     ebx, eax
0x180140b7a  test    eax, eax
0x180140b7c  jns     short loc_180140BA5
0x180140b7e  mov     edx, 12Eh; void *
0x180140b83  mov     rcx, [rbp+178h]; this
0x180140b8a  lea     r8, aWil; "wil"
0x180140b91  mov     r9d, eax; char *
0x180140b94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180140b99  lea     rcx, [rsp+270h+var_238]
0x180140b9e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180140ba3  jmp     short loc_180140BC4
0x180140ba5  mov     rcx, [rsp+270h+var_230]
0x180140baa  test    rcx, rcx
0x180140bad  jz      short loc_180140BF4
0x180140baf  mov     [rdi], rcx
0x180140bb2  mov     eax, [rcx]
0x180140bb4  inc     eax
0x180140bb6  mov     [rcx], eax
0x180140bb8  lea     rcx, [rsp+270h+var_238]
0x180140bbd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180140bc2  xor     ebx, ebx
0x180140bc4  lea     rcx, [rsp+270h+var_240]
0x180140bc9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180140bce  mov     eax, ebx
0x180140bd0  mov     rcx, [rbp+170h+var_10]
0x180140bd7  xor     rcx, rsp; StackCookie
0x180140bda  call    __security_check_cookie
0x180140bdf  lea     r11, [rsp+270h+var_s0]
0x180140be7  mov     rbx, [r11+20h]
0x180140beb  mov     rdi, [r11+28h]
0x180140bef  mov     rsp, r11
0x180140bf2  pop     rbp
0x180140bf3  retn
0x180140bf4  mov     r8, rdi
0x180140bf7  lea     rdx, [rsp+270h+var_240]
0x180140bfc  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180140c01  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180140c06  mov     ebx, eax
0x180140c08  test    eax, eax
0x180140c0a  jns     short loc_180140BB8
0x180140c0c  mov     edx, 137h
0x180140c11  jmp     loc_180140B83
```
