# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180065e9c`
- end: `0x180066009`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `365`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180066adc`

## callees

- `0x180017858`
- `0x180038248`
- `0x180038270`
- `0x180038294`
- `0x1800382c8`
- `0x180041520`
- `0x18004c09c`
- `0x18004c574`
- `0x18004c894`
- `0x180065e9c`
- `0x1800671bc`
- `0x18009e300`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180065edd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180065edd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180065f24`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180065f24`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C8h] BYREF
  void *v14[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  v14[1] = (void *)-2LL;
  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  __0__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v12);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      &v13);
    v14[0] = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v13);
      goto LABEL_9;
    }
    v10 = v14[0];
    if ( v14[0] )
    {
      *a2 = v14[0];
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
    __1__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180065e9c  mov     rax, rsp
0x180065e9f  push    rbp
0x180065ea0  lea     rbp, [rax-178h]
0x180065ea7  sub     rsp, 270h
0x180065eae  mov     qword ptr [rsp+270h+var_228], 0FFFFFFFFFFFFFFFEh
0x180065eb7  mov     [rax+18h], rbx
0x180065ebb  mov     [rax+20h], rdi
0x180065ebf  mov     rax, cs:__security_cookie
0x180065ec6  xor     rax, rsp
0x180065ec9  mov     [rbp+170h+var_10], rax
0x180065ed0  mov     rdi, rdx
0x180065ed3  mov     rbx, rcx
0x180065ed6  mov     qword ptr [rdx], 0
0x180065edd  call    cs:__imp_GetCurrentProcessId
0x180065ee3  mov     r9d, eax
0x180065ee6  mov     [rsp+270h+var_248], rbx
0x180065eeb  mov     [rsp+270h+var_250], 130h; int
0x180065ef3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180065efa  mov     edx, 104h; unsigned __int64
0x180065eff  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180065f04  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180065f09  lea     rcx, [rsp+270h+var_240]
0x180065f0e  call    ??0?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x180065f13  nop
0x180065f14  mov     r9d, 1F0001h; dwDesiredAccess
0x180065f1a  xor     r8d, r8d; dwFlags
0x180065f1d  lea     rdx, [rsp+270h+Name]; lpName
0x180065f22  xor     ecx, ecx; lpMutexAttributes
0x180065f24  call    cs:__imp_CreateMutexExW
0x180065f2a  mov     rdx, rax
0x180065f2d  lea     rcx, [rsp+270h+var_240]
0x180065f32  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180065f37  cmp     [rsp+270h+var_240], 0
0x180065f3d  jnz     short loc_180065F48
0x180065f3f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180065f44  mov     ebx, eax
0x180065f46  jmp     short loc_180065FB6
0x180065f48  lea     rdx, [rsp+270h+var_238]
0x180065f4d  lea     rcx, [rsp+270h+var_240]
0x180065f52  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180065f57  nop
0x180065f58  mov     [rsp+270h+var_230], 0
0x180065f61  lea     rdx, [rsp+270h+var_230]; void **
0x180065f66  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180065f6b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180065f70  mov     ebx, eax
0x180065f72  test    eax, eax
0x180065f74  jns     short loc_180065F97
0x180065f76  mov     edx, 12Eh; void *
0x180065f7b  mov     r9d, eax; char *
0x180065f7e  mov     rcx, [rbp+178h]; this
0x180065f85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065f8a  nop
0x180065f8b  lea     rcx, [rsp+270h+var_238]
0x180065f90  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x180065f95  jmp     short loc_180065FB6
0x180065f97  mov     rcx, [rsp+270h+var_230]
0x180065f9c  test    rcx, rcx
0x180065f9f  jz      short loc_180065FE6
0x180065fa1  mov     [rdi], rcx
0x180065fa4  mov     eax, [rcx]
0x180065fa6  inc     eax
0x180065fa8  mov     [rcx], eax
0x180065faa  lea     rcx, [rsp+270h+var_238]
0x180065faf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x180065fb4  xor     ebx, ebx
0x180065fb6  lea     rcx, [rsp+270h+var_240]
0x180065fbb  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x180065fc0  mov     eax, ebx
0x180065fc2  mov     rcx, [rbp+170h+var_10]
0x180065fc9  xor     rcx, rsp; StackCookie
0x180065fcc  call    __security_check_cookie
0x180065fd1  lea     r11, [rsp+270h+var_s0]
0x180065fd9  mov     rbx, [r11+20h]
0x180065fdd  mov     rdi, [r11+28h]
0x180065fe1  mov     rsp, r11
0x180065fe4  pop     rbp
0x180065fe5  retn
0x180065fe6  mov     r8, rdi
0x180065fe9  lea     rdx, [rsp+270h+var_240]
0x180065fee  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180065ff3  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180065ff8  mov     ebx, eax
0x180065ffa  test    eax, eax
0x180065ffc  jns     short loc_180065FAA
0x180065ffe  mov     edx, 137h
0x180066003  jmp     loc_180065F7B
```
