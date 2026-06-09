# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18002c2e4`
- end: `0x18002c44a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002c870`

## callees

- `0x180003ed0`
- `0x180007c70`
- `0x180007c8c`
- `0x180008768`
- `0x1800097b4`
- `0x180009d90`
- `0x180009f3c`
- `0x18000a3c0`
- `0x18000a4d0`
- `0x18002c2e4`
- `0x18002cbe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002c361`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002c361`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002c31c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002c31c`

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
0x18002c2e4  mov     [rsp-8+arg_10], rbx
0x18002c2e9  mov     [rsp-8+arg_18], rdi
0x18002c2ee  push    rbp
0x18002c2ef  lea     rbp, [rsp-170h]
0x18002c2f7  sub     rsp, 270h
0x18002c2fe  mov     rax, cs:__security_cookie
0x18002c305  xor     rax, rsp
0x18002c308  mov     [rbp+170h+var_10], rax
0x18002c30f  mov     rdi, rdx
0x18002c312  mov     qword ptr [rdx], 0
0x18002c319  mov     rbx, rcx
0x18002c31c  call    cs:__imp_GetCurrentProcessId
0x18002c322  mov     [rsp+270h+var_248], rbx
0x18002c327  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002c32e  mov     r9d, eax
0x18002c331  mov     [rsp+270h+var_250], 130h; int
0x18002c339  mov     edx, 104h; unsigned __int64
0x18002c33e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002c343  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c348  mov     r9d, 1F0001h; dwDesiredAccess
0x18002c34e  mov     [rsp+270h+var_240], 0
0x18002c357  xor     r8d, r8d; dwFlags
0x18002c35a  lea     rdx, [rsp+270h+Name]; lpName
0x18002c35f  xor     ecx, ecx; lpMutexAttributes
0x18002c361  call    cs:__imp_CreateMutexExW
0x18002c367  mov     rdx, rax
0x18002c36a  lea     rcx, [rsp+270h+var_240]
0x18002c36f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002c374  cmp     [rsp+270h+var_240], 0
0x18002c37a  jnz     short loc_18002C385
0x18002c37c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002c381  mov     ebx, eax
0x18002c383  jmp     short loc_18002C3F8
0x18002c385  lea     rdx, [rsp+270h+var_238]
0x18002c38a  lea     rcx, [rsp+270h+var_240]
0x18002c38f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002c394  lea     rdx, [rsp+270h+var_230]; void **
0x18002c399  mov     [rsp+270h+var_230], 0
0x18002c3a2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002c3a7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18002c3ac  mov     ebx, eax
0x18002c3ae  test    eax, eax
0x18002c3b0  jns     short loc_18002C3D9
0x18002c3b2  mov     edx, 12Eh; void *
0x18002c3b7  mov     rcx, [rbp+178h]; this
0x18002c3be  lea     r8, aWil; "wil"
0x18002c3c5  mov     r9d, eax; char *
0x18002c3c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c3cd  lea     rcx, [rsp+270h+var_238]
0x18002c3d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002c3d7  jmp     short loc_18002C3F8
0x18002c3d9  mov     rcx, [rsp+270h+var_230]
0x18002c3de  test    rcx, rcx
0x18002c3e1  jz      short loc_18002C428
0x18002c3e3  mov     [rdi], rcx
0x18002c3e6  mov     eax, [rcx]
0x18002c3e8  inc     eax
0x18002c3ea  mov     [rcx], eax
0x18002c3ec  lea     rcx, [rsp+270h+var_238]
0x18002c3f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002c3f6  xor     ebx, ebx
0x18002c3f8  lea     rcx, [rsp+270h+var_240]
0x18002c3fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002c402  mov     eax, ebx
0x18002c404  mov     rcx, [rbp+170h+var_10]
0x18002c40b  xor     rcx, rsp; StackCookie
0x18002c40e  call    __security_check_cookie
0x18002c413  lea     r11, [rsp+270h+var_s0]
0x18002c41b  mov     rbx, [r11+20h]
0x18002c41f  mov     rdi, [r11+28h]
0x18002c423  mov     rsp, r11
0x18002c426  pop     rbp
0x18002c427  retn
0x18002c428  mov     r8, rdi
0x18002c42b  lea     rdx, [rsp+270h+var_240]
0x18002c430  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002c435  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002c43a  mov     ebx, eax
0x18002c43c  test    eax, eax
0x18002c43e  jns     short loc_18002C3EC
0x18002c440  mov     edx, 137h
0x18002c445  jmp     loc_18002C3B7
```
