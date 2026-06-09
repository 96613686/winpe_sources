# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180011c24`
- end: `0x180011d83`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001288c`

## callees

- `0x180002020`
- `0x1800051e0`
- `0x18000a740`
- `0x18000a75c`
- `0x18000c4a4`
- `0x18000e784`
- `0x18000eccc`
- `0x18000f2dc`
- `0x18000fe84`
- `0x180011c24`
- `0x18001323c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180011ca1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180011ca1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011c5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011c5c`

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
0x180011c24  mov     [rsp-8+arg_10], rbx
0x180011c29  mov     [rsp-8+arg_18], rdi
0x180011c2e  push    rbp
0x180011c2f  lea     rbp, [rsp-170h]
0x180011c37  sub     rsp, 270h
0x180011c3e  mov     rax, cs:__security_cookie
0x180011c45  xor     rax, rsp
0x180011c48  mov     [rbp+170h+var_10], rax
0x180011c4f  mov     rdi, rdx
0x180011c52  mov     qword ptr [rdx], 0
0x180011c59  mov     rbx, rcx
0x180011c5c  call    cs:__imp_GetCurrentProcessId
0x180011c62  mov     [rsp+270h+var_248], rbx
0x180011c67  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180011c6e  mov     r9d, eax
0x180011c71  mov     [rsp+270h+var_250], 130h; int
0x180011c79  mov     edx, 104h; unsigned __int64
0x180011c7e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011c83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011c88  mov     r9d, 1F0001h; dwDesiredAccess
0x180011c8e  mov     [rsp+270h+var_240], 0
0x180011c97  xor     r8d, r8d; dwFlags
0x180011c9a  lea     rdx, [rsp+270h+Name]; lpName
0x180011c9f  xor     ecx, ecx; lpMutexAttributes
0x180011ca1  call    cs:__imp_CreateMutexExW
0x180011ca7  mov     rdx, rax
0x180011caa  lea     rcx, [rsp+270h+var_240]
0x180011caf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180011cb4  cmp     [rsp+270h+var_240], 0
0x180011cba  jnz     short loc_180011CC5
0x180011cbc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180011cc1  mov     ebx, eax
0x180011cc3  jmp     short loc_180011D31
0x180011cc5  lea     rdx, [rsp+270h+var_238]
0x180011cca  lea     rcx, [rsp+270h+var_240]
0x180011ccf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180011cd4  lea     rdx, [rsp+270h+var_230]; void **
0x180011cd9  mov     [rsp+270h+var_230], 0
0x180011ce2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011ce7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180011cec  mov     ebx, eax
0x180011cee  test    eax, eax
0x180011cf0  jns     short loc_180011D12
0x180011cf2  mov     edx, 12Eh; void *
0x180011cf7  mov     rcx, [rbp+178h]; this
0x180011cfe  mov     r9d, eax; char *
0x180011d01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011d06  lea     rcx, [rsp+270h+var_238]
0x180011d0b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011d10  jmp     short loc_180011D31
0x180011d12  mov     rcx, [rsp+270h+var_230]
0x180011d17  test    rcx, rcx
0x180011d1a  jz      short loc_180011D61
0x180011d1c  mov     [rdi], rcx
0x180011d1f  mov     eax, [rcx]
0x180011d21  inc     eax
0x180011d23  mov     [rcx], eax
0x180011d25  lea     rcx, [rsp+270h+var_238]
0x180011d2a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011d2f  xor     ebx, ebx
0x180011d31  lea     rcx, [rsp+270h+var_240]
0x180011d36  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011d3b  mov     eax, ebx
0x180011d3d  mov     rcx, [rbp+170h+var_10]
0x180011d44  xor     rcx, rsp; StackCookie
0x180011d47  call    __security_check_cookie
0x180011d4c  lea     r11, [rsp+270h+var_s0]
0x180011d54  mov     rbx, [r11+20h]
0x180011d58  mov     rdi, [r11+28h]
0x180011d5c  mov     rsp, r11
0x180011d5f  pop     rbp
0x180011d60  retn
0x180011d61  mov     r8, rdi
0x180011d64  lea     rdx, [rsp+270h+var_240]
0x180011d69  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011d6e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180011d73  mov     ebx, eax
0x180011d75  test    eax, eax
0x180011d77  jns     short loc_180011D25
0x180011d79  mov     edx, 137h
0x180011d7e  jmp     loc_180011CF7
```
