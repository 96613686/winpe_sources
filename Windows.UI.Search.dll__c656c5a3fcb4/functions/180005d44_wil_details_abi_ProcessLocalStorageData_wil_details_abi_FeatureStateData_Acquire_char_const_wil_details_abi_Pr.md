# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180005d44`
- end: `0x180005eaa`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000759c`

## callees

- `0x1800055d8`
- `0x1800055f4`
- `0x180005d44`
- `0x1800072d8`
- `0x180008384`
- `0x180009d6c`
- `0x18000a4a8`
- `0x18000aa90`
- `0x18000b994`
- `0x18000c1d0`
- `0x180076c50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005dc1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005dc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005d7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005d7c`

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
0x180005d44  mov     [rsp-8+arg_10], rbx
0x180005d49  mov     [rsp-8+arg_18], rdi
0x180005d4e  push    rbp
0x180005d4f  lea     rbp, [rsp-170h]
0x180005d57  sub     rsp, 270h
0x180005d5e  mov     rax, cs:__security_cookie
0x180005d65  xor     rax, rsp
0x180005d68  mov     [rbp+170h+var_10], rax
0x180005d6f  mov     rdi, rdx
0x180005d72  mov     qword ptr [rdx], 0
0x180005d79  mov     rbx, rcx
0x180005d7c  call    cs:__imp_GetCurrentProcessId
0x180005d82  mov     [rsp+270h+var_248], rbx
0x180005d87  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005d8e  mov     r9d, eax
0x180005d91  mov     [rsp+270h+var_250], 130h; int
0x180005d99  mov     edx, 104h; unsigned __int64
0x180005d9e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180005da3  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180005da8  mov     r9d, 1F0001h; dwDesiredAccess
0x180005dae  mov     [rsp+270h+var_240], 0
0x180005db7  xor     r8d, r8d; dwFlags
0x180005dba  lea     rdx, [rsp+270h+Name]; lpName
0x180005dbf  xor     ecx, ecx; lpMutexAttributes
0x180005dc1  call    cs:__imp_CreateMutexExW
0x180005dc7  mov     rdx, rax
0x180005dca  lea     rcx, [rsp+270h+var_240]
0x180005dcf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005dd4  cmp     [rsp+270h+var_240], 0
0x180005dda  jnz     short loc_180005DE5
0x180005ddc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005de1  mov     ebx, eax
0x180005de3  jmp     short loc_180005E58
0x180005de5  lea     rdx, [rsp+270h+var_238]
0x180005dea  lea     rcx, [rsp+270h+var_240]
0x180005def  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005df4  lea     rdx, [rsp+270h+var_230]; void **
0x180005df9  mov     [rsp+270h+var_230], 0
0x180005e02  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180005e07  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180005e0c  mov     ebx, eax
0x180005e0e  test    eax, eax
0x180005e10  jns     short loc_180005E39
0x180005e12  mov     edx, 12Eh; void *
0x180005e17  mov     rcx, [rbp+178h]; this
0x180005e1e  lea     r8, aWil; "wil"
0x180005e25  mov     r9d, eax; char *
0x180005e28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e2d  lea     rcx, [rsp+270h+var_238]
0x180005e32  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005e37  jmp     short loc_180005E58
0x180005e39  mov     rcx, [rsp+270h+var_230]
0x180005e3e  test    rcx, rcx
0x180005e41  jz      short loc_180005E88
0x180005e43  mov     [rdi], rcx
0x180005e46  mov     eax, [rcx]
0x180005e48  inc     eax
0x180005e4a  mov     [rcx], eax
0x180005e4c  lea     rcx, [rsp+270h+var_238]
0x180005e51  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005e56  xor     ebx, ebx
0x180005e58  lea     rcx, [rsp+270h+var_240]
0x180005e5d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005e62  mov     eax, ebx
0x180005e64  mov     rcx, [rbp+170h+var_10]
0x180005e6b  xor     rcx, rsp; StackCookie
0x180005e6e  call    __security_check_cookie
0x180005e73  lea     r11, [rsp+270h+var_s0]
0x180005e7b  mov     rbx, [r11+20h]
0x180005e7f  mov     rdi, [r11+28h]
0x180005e83  mov     rsp, r11
0x180005e86  pop     rbp
0x180005e87  retn
0x180005e88  mov     r8, rdi
0x180005e8b  lea     rdx, [rsp+270h+var_240]
0x180005e90  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180005e95  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005e9a  mov     ebx, eax
0x180005e9c  test    eax, eax
0x180005e9e  jns     short loc_180005E4C
0x180005ea0  mov     edx, 137h
0x180005ea5  jmp     loc_180005E17
```
