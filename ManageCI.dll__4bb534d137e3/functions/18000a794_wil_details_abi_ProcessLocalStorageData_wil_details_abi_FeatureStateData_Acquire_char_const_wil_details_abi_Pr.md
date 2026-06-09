# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000a794`
- end: `0x18000a8fa`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b374`

## callees

- `0x180002a90`
- `0x18000538c`
- `0x1800053a8`
- `0x180006248`
- `0x180007654`
- `0x180007c2c`
- `0x180007d98`
- `0x1800084cc`
- `0x180008710`
- `0x18000a794`
- `0x18000bae0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a811`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a811`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a7cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a7cc`

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
0x18000a794  mov     [rsp-8+arg_10], rbx
0x18000a799  mov     [rsp-8+arg_18], rdi
0x18000a79e  push    rbp
0x18000a79f  lea     rbp, [rsp-170h]
0x18000a7a7  sub     rsp, 270h
0x18000a7ae  mov     rax, cs:__security_cookie
0x18000a7b5  xor     rax, rsp
0x18000a7b8  mov     [rbp+170h+var_10], rax
0x18000a7bf  mov     rdi, rdx
0x18000a7c2  mov     qword ptr [rdx], 0
0x18000a7c9  mov     rbx, rcx
0x18000a7cc  call    cs:__imp_GetCurrentProcessId
0x18000a7d2  mov     [rsp+270h+var_248], rbx
0x18000a7d7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a7de  mov     r9d, eax
0x18000a7e1  mov     [rsp+270h+var_250], 130h; int
0x18000a7e9  mov     edx, 104h; unsigned __int64
0x18000a7ee  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a7f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a7f8  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a7fe  mov     [rsp+270h+var_240], 0
0x18000a807  xor     r8d, r8d; dwFlags
0x18000a80a  lea     rdx, [rsp+270h+Name]; lpName
0x18000a80f  xor     ecx, ecx; lpMutexAttributes
0x18000a811  call    cs:__imp_CreateMutexExW
0x18000a817  mov     rdx, rax
0x18000a81a  lea     rcx, [rsp+270h+var_240]
0x18000a81f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a824  cmp     [rsp+270h+var_240], 0
0x18000a82a  jnz     short loc_18000A835
0x18000a82c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a831  mov     ebx, eax
0x18000a833  jmp     short loc_18000A8A8
0x18000a835  lea     rdx, [rsp+270h+var_238]
0x18000a83a  lea     rcx, [rsp+270h+var_240]
0x18000a83f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000a844  lea     rdx, [rsp+270h+var_230]; void **
0x18000a849  mov     [rsp+270h+var_230], 0
0x18000a852  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a857  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000a85c  mov     ebx, eax
0x18000a85e  test    eax, eax
0x18000a860  jns     short loc_18000A889
0x18000a862  mov     edx, 12Eh; void *
0x18000a867  mov     rcx, [rbp+178h]; this
0x18000a86e  lea     r8, aWil; "wil"
0x18000a875  mov     r9d, eax; char *
0x18000a878  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a87d  lea     rcx, [rsp+270h+var_238]
0x18000a882  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a887  jmp     short loc_18000A8A8
0x18000a889  mov     rcx, [rsp+270h+var_230]
0x18000a88e  test    rcx, rcx
0x18000a891  jz      short loc_18000A8D8
0x18000a893  mov     [rdi], rcx
0x18000a896  mov     eax, [rcx]
0x18000a898  inc     eax
0x18000a89a  mov     [rcx], eax
0x18000a89c  lea     rcx, [rsp+270h+var_238]
0x18000a8a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a8a6  xor     ebx, ebx
0x18000a8a8  lea     rcx, [rsp+270h+var_240]
0x18000a8ad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a8b2  mov     eax, ebx
0x18000a8b4  mov     rcx, [rbp+170h+var_10]
0x18000a8bb  xor     rcx, rsp; StackCookie
0x18000a8be  call    __security_check_cookie
0x18000a8c3  lea     r11, [rsp+270h+var_s0]
0x18000a8cb  mov     rbx, [r11+20h]
0x18000a8cf  mov     rdi, [r11+28h]
0x18000a8d3  mov     rsp, r11
0x18000a8d6  pop     rbp
0x18000a8d7  retn
0x18000a8d8  mov     r8, rdi
0x18000a8db  lea     rdx, [rsp+270h+var_240]
0x18000a8e0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a8e5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000a8ea  mov     ebx, eax
0x18000a8ec  test    eax, eax
0x18000a8ee  jns     short loc_18000A89C
0x18000a8f0  mov     edx, 137h
0x18000a8f5  jmp     loc_18000A867
```
