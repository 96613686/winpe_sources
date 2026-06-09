# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000a654`
- end: `0x18000a7ba`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b61c`

## callees

- `0x180005860`
- `0x180009b3c`
- `0x180009b58`
- `0x18000a654`
- `0x18000b418`
- `0x18000ca24`
- `0x18000decc`
- `0x18000e7e4`
- `0x18000ecec`
- `0x18000fbb4`
- `0x18000ffe0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a68c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a68c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a6d1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a6d1`

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
0x18000a654  mov     [rsp-8+arg_10], rbx
0x18000a659  mov     [rsp-8+arg_18], rdi
0x18000a65e  push    rbp
0x18000a65f  lea     rbp, [rsp-170h]
0x18000a667  sub     rsp, 270h
0x18000a66e  mov     rax, cs:__security_cookie
0x18000a675  xor     rax, rsp
0x18000a678  mov     [rbp+170h+var_10], rax
0x18000a67f  mov     rdi, rdx
0x18000a682  mov     qword ptr [rdx], 0
0x18000a689  mov     rbx, rcx
0x18000a68c  call    cs:__imp_GetCurrentProcessId
0x18000a692  mov     [rsp+270h+var_248], rbx
0x18000a697  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a69e  mov     r9d, eax
0x18000a6a1  mov     [rsp+270h+var_250], 130h; int
0x18000a6a9  mov     edx, 104h; unsigned __int64
0x18000a6ae  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a6b3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a6b8  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a6be  mov     [rsp+270h+var_240], 0
0x18000a6c7  xor     r8d, r8d; dwFlags
0x18000a6ca  lea     rdx, [rsp+270h+Name]; lpName
0x18000a6cf  xor     ecx, ecx; lpMutexAttributes
0x18000a6d1  call    cs:__imp_CreateMutexExW
0x18000a6d7  mov     rdx, rax
0x18000a6da  lea     rcx, [rsp+270h+var_240]
0x18000a6df  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a6e4  cmp     [rsp+270h+var_240], 0
0x18000a6ea  jnz     short loc_18000A6F5
0x18000a6ec  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a6f1  mov     ebx, eax
0x18000a6f3  jmp     short loc_18000A768
0x18000a6f5  lea     rdx, [rsp+270h+var_238]
0x18000a6fa  lea     rcx, [rsp+270h+var_240]
0x18000a6ff  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000a704  lea     rdx, [rsp+270h+var_230]; void **
0x18000a709  mov     [rsp+270h+var_230], 0
0x18000a712  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a717  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000a71c  mov     ebx, eax
0x18000a71e  test    eax, eax
0x18000a720  jns     short loc_18000A749
0x18000a722  mov     edx, 12Eh; void *
0x18000a727  mov     rcx, [rbp+178h]; this
0x18000a72e  lea     r8, aWil; "wil"
0x18000a735  mov     r9d, eax; char *
0x18000a738  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a73d  lea     rcx, [rsp+270h+var_238]
0x18000a742  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a747  jmp     short loc_18000A768
0x18000a749  mov     rcx, [rsp+270h+var_230]
0x18000a74e  test    rcx, rcx
0x18000a751  jz      short loc_18000A798
0x18000a753  mov     [rdi], rcx
0x18000a756  mov     eax, [rcx]
0x18000a758  inc     eax
0x18000a75a  mov     [rcx], eax
0x18000a75c  lea     rcx, [rsp+270h+var_238]
0x18000a761  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a766  xor     ebx, ebx
0x18000a768  lea     rcx, [rsp+270h+var_240]
0x18000a76d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a772  mov     eax, ebx
0x18000a774  mov     rcx, [rbp+170h+var_10]
0x18000a77b  xor     rcx, rsp; StackCookie
0x18000a77e  call    __security_check_cookie
0x18000a783  lea     r11, [rsp+270h+var_s0]
0x18000a78b  mov     rbx, [r11+20h]
0x18000a78f  mov     rdi, [r11+28h]
0x18000a793  mov     rsp, r11
0x18000a796  pop     rbp
0x18000a797  retn
0x18000a798  mov     r8, rdi
0x18000a79b  lea     rdx, [rsp+270h+var_240]
0x18000a7a0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a7a5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000a7aa  mov     ebx, eax
0x18000a7ac  test    eax, eax
0x18000a7ae  jns     short loc_18000A75C
0x18000a7b0  mov     edx, 137h
0x18000a7b5  jmp     loc_18000A727
```
