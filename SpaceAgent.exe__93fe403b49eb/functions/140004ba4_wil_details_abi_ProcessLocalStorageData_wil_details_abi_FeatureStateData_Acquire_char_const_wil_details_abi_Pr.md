# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140004ba4`
- end: `0x140004d03`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400051a8`

## callees

- `0x1400046a8`
- `0x1400046c4`
- `0x140004ba4`
- `0x140005a58`
- `0x14000686c`
- `0x1400079cc`
- `0x1400081d4`
- `0x140008b30`
- `0x140009314`
- `0x1400095fc`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x140004c21`
- `KERNEL32!CreateMutexExW` at `0x140004c21`
- `KERNEL32!GetCurrentProcessId` at `0x140004bdc`
- `KERNEL32!GetCurrentProcessId` at `0x140004bdc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v9; // r8d
  __int64 v10; // rdx
  _DWORD *v11; // rcx
  wil::details *v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v13 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v13,
    Mutex);
  if ( v13 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v13,
      v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
      goto LABEL_9;
    }
    v11 = v15;
    if ( v15 )
    {
      *a2 = v15;
      ++*v11;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v10 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v13,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x140004ba4  mov     [rsp-8+arg_10], rbx
0x140004ba9  mov     [rsp-8+arg_18], rdi
0x140004bae  push    rbp
0x140004baf  lea     rbp, [rsp-170h]
0x140004bb7  sub     rsp, 270h
0x140004bbe  mov     rax, cs:__security_cookie
0x140004bc5  xor     rax, rsp
0x140004bc8  mov     [rbp+170h+var_10], rax
0x140004bcf  mov     rdi, rdx
0x140004bd2  mov     qword ptr [rdx], 0
0x140004bd9  mov     rbx, rcx
0x140004bdc  call    cs:__imp_GetCurrentProcessId
0x140004be2  mov     [rsp+270h+var_248], rbx
0x140004be7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004bee  mov     r9d, eax
0x140004bf1  mov     [rsp+270h+var_250], 130h; int
0x140004bf9  mov     edx, 104h; unsigned __int64
0x140004bfe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004c03  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004c08  mov     r9d, 1F0001h; dwDesiredAccess
0x140004c0e  mov     [rsp+270h+var_240], 0
0x140004c17  xor     r8d, r8d; dwFlags
0x140004c1a  lea     rdx, [rsp+270h+Name]; lpName
0x140004c1f  xor     ecx, ecx; lpMutexAttributes
0x140004c21  call    cs:__imp_CreateMutexExW
0x140004c27  mov     rdx, rax
0x140004c2a  lea     rcx, [rsp+270h+var_240]
0x140004c2f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140004c34  cmp     [rsp+270h+var_240], 0
0x140004c3a  jnz     short loc_140004C45
0x140004c3c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004c41  mov     ebx, eax
0x140004c43  jmp     short loc_140004CB1
0x140004c45  lea     rdx, [rsp+270h+var_238]
0x140004c4a  lea     rcx, [rsp+270h+var_240]
0x140004c4f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140004c54  lea     rdx, [rsp+270h+var_230]; void **
0x140004c59  mov     [rsp+270h+var_230], 0
0x140004c62  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004c67  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140004c6c  mov     ebx, eax
0x140004c6e  test    eax, eax
0x140004c70  jns     short loc_140004C92
0x140004c72  mov     edx, 12Eh; void *
0x140004c77  mov     rcx, [rbp+178h]; this
0x140004c7e  mov     r9d, eax; char *
0x140004c81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004c86  lea     rcx, [rsp+270h+var_238]
0x140004c8b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004c90  jmp     short loc_140004CB1
0x140004c92  mov     rcx, [rsp+270h+var_230]
0x140004c97  test    rcx, rcx
0x140004c9a  jz      short loc_140004CE1
0x140004c9c  mov     [rdi], rcx
0x140004c9f  mov     eax, [rcx]
0x140004ca1  inc     eax
0x140004ca3  mov     [rcx], eax
0x140004ca5  lea     rcx, [rsp+270h+var_238]
0x140004caa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004caf  xor     ebx, ebx
0x140004cb1  lea     rcx, [rsp+270h+var_240]
0x140004cb6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004cbb  mov     eax, ebx
0x140004cbd  mov     rcx, [rbp+170h+var_10]
0x140004cc4  xor     rcx, rsp; StackCookie
0x140004cc7  call    __security_check_cookie
0x140004ccc  lea     r11, [rsp+270h+var_s0]
0x140004cd4  mov     rbx, [r11+20h]
0x140004cd8  mov     rdi, [r11+28h]
0x140004cdc  mov     rsp, r11
0x140004cdf  pop     rbp
0x140004ce0  retn
0x140004ce1  mov     r8, rdi
0x140004ce4  lea     rdx, [rsp+270h+var_240]
0x140004ce9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004cee  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140004cf3  mov     ebx, eax
0x140004cf5  test    eax, eax
0x140004cf7  jns     short loc_140004CA5
0x140004cf9  mov     edx, 137h
0x140004cfe  jmp     loc_140004C77
```
