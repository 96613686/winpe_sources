# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180005e14`
- end: `0x180005f7a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007080`

## callees

- `0x180002e60`
- `0x18000560c`
- `0x180005628`
- `0x180005e14`
- `0x180006e38`
- `0x180007e58`
- `0x18000907c`
- `0x18000980c`
- `0x180009e58`
- `0x18000a974`
- `0x18000acac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005e91`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005e91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005e4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005e4c`

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
0x180005e14  mov     [rsp-8+arg_10], rbx
0x180005e19  mov     [rsp-8+arg_18], rdi
0x180005e1e  push    rbp
0x180005e1f  lea     rbp, [rsp-170h]
0x180005e27  sub     rsp, 270h
0x180005e2e  mov     rax, cs:__security_cookie
0x180005e35  xor     rax, rsp
0x180005e38  mov     [rbp+170h+var_10], rax
0x180005e3f  mov     rdi, rdx
0x180005e42  mov     qword ptr [rdx], 0
0x180005e49  mov     rbx, rcx
0x180005e4c  call    cs:__imp_GetCurrentProcessId
0x180005e52  mov     [rsp+270h+var_248], rbx
0x180005e57  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005e5e  mov     r9d, eax
0x180005e61  mov     [rsp+270h+var_250], 130h; int
0x180005e69  mov     edx, 104h; unsigned __int64
0x180005e6e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005e73  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005e78  mov     r9d, 1F0001h; dwDesiredAccess
0x180005e7e  mov     [rsp+270h+var_240], 0
0x180005e87  xor     r8d, r8d; dwFlags
0x180005e8a  lea     rdx, [rsp+270h+Name]; lpName
0x180005e8f  xor     ecx, ecx; lpMutexAttributes
0x180005e91  call    cs:__imp_CreateMutexExW
0x180005e97  mov     rdx, rax
0x180005e9a  lea     rcx, [rsp+270h+var_240]
0x180005e9f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005ea4  cmp     [rsp+270h+var_240], 0
0x180005eaa  jnz     short loc_180005EB5
0x180005eac  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005eb1  mov     ebx, eax
0x180005eb3  jmp     short loc_180005F28
0x180005eb5  lea     rdx, [rsp+270h+var_238]
0x180005eba  lea     rcx, [rsp+270h+var_240]
0x180005ebf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005ec4  lea     rdx, [rsp+270h+var_230]; void **
0x180005ec9  mov     [rsp+270h+var_230], 0
0x180005ed2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005ed7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005edc  mov     ebx, eax
0x180005ede  test    eax, eax
0x180005ee0  jns     short loc_180005F09
0x180005ee2  mov     edx, 12Eh; void *
0x180005ee7  mov     rcx, [rbp+178h]; this
0x180005eee  lea     r8, aWil; "wil"
0x180005ef5  mov     r9d, eax; char *
0x180005ef8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005efd  lea     rcx, [rsp+270h+var_238]
0x180005f02  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005f07  jmp     short loc_180005F28
0x180005f09  mov     rcx, [rsp+270h+var_230]
0x180005f0e  test    rcx, rcx
0x180005f11  jz      short loc_180005F58
0x180005f13  mov     [rdi], rcx
0x180005f16  mov     eax, [rcx]
0x180005f18  inc     eax
0x180005f1a  mov     [rcx], eax
0x180005f1c  lea     rcx, [rsp+270h+var_238]
0x180005f21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005f26  xor     ebx, ebx
0x180005f28  lea     rcx, [rsp+270h+var_240]
0x180005f2d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005f32  mov     eax, ebx
0x180005f34  mov     rcx, [rbp+170h+var_10]
0x180005f3b  xor     rcx, rsp; StackCookie
0x180005f3e  call    __security_check_cookie
0x180005f43  lea     r11, [rsp+270h+var_s0]
0x180005f4b  mov     rbx, [r11+20h]
0x180005f4f  mov     rdi, [r11+28h]
0x180005f53  mov     rsp, r11
0x180005f56  pop     rbp
0x180005f57  retn
0x180005f58  mov     r8, rdi
0x180005f5b  lea     rdx, [rsp+270h+var_240]
0x180005f60  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005f65  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005f6a  mov     ebx, eax
0x180005f6c  test    eax, eax
0x180005f6e  jns     short loc_180005F1C
0x180005f70  mov     edx, 137h
0x180005f75  jmp     loc_180005EE7
```
