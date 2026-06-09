# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180008d30`
- end: `0x180008e8f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009ab4`

## callees

- `0x1800015f0`
- `0x1800087a4`
- `0x1800087c0`
- `0x180008d30`
- `0x1800098f8`
- `0x18000a69c`
- `0x18000b8bc`
- `0x18000bffc`
- `0x18000c428`
- `0x18000cb54`
- `0x18000ce8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008dad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008dad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008d68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008d68`

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
0x180008d30  mov     [rsp-8+arg_10], rbx
0x180008d35  mov     [rsp-8+arg_18], rdi
0x180008d3a  push    rbp
0x180008d3b  lea     rbp, [rsp-170h]
0x180008d43  sub     rsp, 270h
0x180008d4a  mov     rax, cs:__security_cookie
0x180008d51  xor     rax, rsp
0x180008d54  mov     [rbp+170h+var_10], rax
0x180008d5b  mov     rdi, rdx
0x180008d5e  mov     qword ptr [rdx], 0
0x180008d65  mov     rbx, rcx
0x180008d68  call    cs:__imp_GetCurrentProcessId
0x180008d6e  mov     [rsp+270h+var_248], rbx
0x180008d73  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008d7a  mov     r9d, eax
0x180008d7d  mov     [rsp+270h+var_250], 130h; int
0x180008d85  mov     edx, 104h; unsigned __int64
0x180008d8a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008d8f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008d94  mov     r9d, 1F0001h; dwDesiredAccess
0x180008d9a  mov     [rsp+270h+var_240], 0
0x180008da3  xor     r8d, r8d; dwFlags
0x180008da6  lea     rdx, [rsp+270h+Name]; lpName
0x180008dab  xor     ecx, ecx; lpMutexAttributes
0x180008dad  call    cs:__imp_CreateMutexExW
0x180008db3  mov     rdx, rax
0x180008db6  lea     rcx, [rsp+270h+var_240]
0x180008dbb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008dc0  cmp     [rsp+270h+var_240], 0
0x180008dc6  jnz     short loc_180008DD1
0x180008dc8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008dcd  mov     ebx, eax
0x180008dcf  jmp     short loc_180008E3D
0x180008dd1  lea     rdx, [rsp+270h+var_238]
0x180008dd6  lea     rcx, [rsp+270h+var_240]
0x180008ddb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180008de0  lea     rdx, [rsp+270h+var_230]; void **
0x180008de5  mov     [rsp+270h+var_230], 0
0x180008dee  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008df3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180008df8  mov     ebx, eax
0x180008dfa  test    eax, eax
0x180008dfc  jns     short loc_180008E1E
0x180008dfe  mov     edx, 12Eh; void *
0x180008e03  mov     rcx, [rbp+178h]; this
0x180008e0a  mov     r9d, eax; char *
0x180008e0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e12  lea     rcx, [rsp+270h+var_238]
0x180008e17  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008e1c  jmp     short loc_180008E3D
0x180008e1e  mov     rcx, [rsp+270h+var_230]
0x180008e23  test    rcx, rcx
0x180008e26  jz      short loc_180008E6D
0x180008e28  mov     [rdi], rcx
0x180008e2b  mov     eax, [rcx]
0x180008e2d  inc     eax
0x180008e2f  mov     [rcx], eax
0x180008e31  lea     rcx, [rsp+270h+var_238]
0x180008e36  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008e3b  xor     ebx, ebx
0x180008e3d  lea     rcx, [rsp+270h+var_240]
0x180008e42  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008e47  mov     eax, ebx
0x180008e49  mov     rcx, [rbp+170h+var_10]
0x180008e50  xor     rcx, rsp; StackCookie
0x180008e53  call    __security_check_cookie
0x180008e58  lea     r11, [rsp+270h+var_s0]
0x180008e60  mov     rbx, [r11+20h]
0x180008e64  mov     rdi, [r11+28h]
0x180008e68  mov     rsp, r11
0x180008e6b  pop     rbp
0x180008e6c  retn
0x180008e6d  mov     r8, rdi
0x180008e70  lea     rdx, [rsp+270h+var_240]
0x180008e75  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008e7a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180008e7f  mov     ebx, eax
0x180008e81  test    eax, eax
0x180008e83  jns     short loc_180008E31
0x180008e85  mov     edx, 137h
0x180008e8a  jmp     loc_180008E03
```
