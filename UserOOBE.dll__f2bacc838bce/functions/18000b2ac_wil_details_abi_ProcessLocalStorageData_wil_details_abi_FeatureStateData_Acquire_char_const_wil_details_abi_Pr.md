# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000b2ac`
- end: `0x18000b412`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000bb78`

## callees

- `0x1800032b0`
- `0x1800056c8`
- `0x1800056e4`
- `0x1800060e8`
- `0x180007134`
- `0x180007710`
- `0x1800078bc`
- `0x180007d40`
- `0x180007e34`
- `0x18000b2ac`
- `0x18000c3dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b329`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b329`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b2e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b2e4`

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
0x18000b2ac  mov     [rsp-8+arg_10], rbx
0x18000b2b1  mov     [rsp-8+arg_18], rdi
0x18000b2b6  push    rbp
0x18000b2b7  lea     rbp, [rsp-170h]
0x18000b2bf  sub     rsp, 270h
0x18000b2c6  mov     rax, cs:__security_cookie
0x18000b2cd  xor     rax, rsp
0x18000b2d0  mov     [rbp+170h+var_10], rax
0x18000b2d7  mov     rdi, rdx
0x18000b2da  mov     qword ptr [rdx], 0
0x18000b2e1  mov     rbx, rcx
0x18000b2e4  call    cs:__imp_GetCurrentProcessId
0x18000b2ea  mov     [rsp+270h+var_248], rbx
0x18000b2ef  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b2f6  mov     r9d, eax
0x18000b2f9  mov     [rsp+270h+var_250], 130h; int
0x18000b301  mov     edx, 104h; unsigned __int64
0x18000b306  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b30b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b310  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b316  mov     [rsp+270h+var_240], 0
0x18000b31f  xor     r8d, r8d; dwFlags
0x18000b322  lea     rdx, [rsp+270h+Name]; lpName
0x18000b327  xor     ecx, ecx; lpMutexAttributes
0x18000b329  call    cs:__imp_CreateMutexExW
0x18000b32f  mov     rdx, rax
0x18000b332  lea     rcx, [rsp+270h+var_240]
0x18000b337  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000b33c  cmp     [rsp+270h+var_240], 0
0x18000b342  jnz     short loc_18000B34D
0x18000b344  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b349  mov     ebx, eax
0x18000b34b  jmp     short loc_18000B3C0
0x18000b34d  lea     rdx, [rsp+270h+var_238]
0x18000b352  lea     rcx, [rsp+270h+var_240]
0x18000b357  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000b35c  lea     rdx, [rsp+270h+var_230]; void **
0x18000b361  mov     [rsp+270h+var_230], 0
0x18000b36a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b36f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000b374  mov     ebx, eax
0x18000b376  test    eax, eax
0x18000b378  jns     short loc_18000B3A1
0x18000b37a  mov     edx, 12Eh; void *
0x18000b37f  mov     rcx, [rbp+178h]; this
0x18000b386  lea     r8, aWil; "wil"
0x18000b38d  mov     r9d, eax; char *
0x18000b390  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b395  lea     rcx, [rsp+270h+var_238]
0x18000b39a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b39f  jmp     short loc_18000B3C0
0x18000b3a1  mov     rcx, [rsp+270h+var_230]
0x18000b3a6  test    rcx, rcx
0x18000b3a9  jz      short loc_18000B3F0
0x18000b3ab  mov     [rdi], rcx
0x18000b3ae  mov     eax, [rcx]
0x18000b3b0  inc     eax
0x18000b3b2  mov     [rcx], eax
0x18000b3b4  lea     rcx, [rsp+270h+var_238]
0x18000b3b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b3be  xor     ebx, ebx
0x18000b3c0  lea     rcx, [rsp+270h+var_240]
0x18000b3c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b3ca  mov     eax, ebx
0x18000b3cc  mov     rcx, [rbp+170h+var_10]
0x18000b3d3  xor     rcx, rsp; StackCookie
0x18000b3d6  call    __security_check_cookie
0x18000b3db  lea     r11, [rsp+270h+var_s0]
0x18000b3e3  mov     rbx, [r11+20h]
0x18000b3e7  mov     rdi, [r11+28h]
0x18000b3eb  mov     rsp, r11
0x18000b3ee  pop     rbp
0x18000b3ef  retn
0x18000b3f0  mov     r8, rdi
0x18000b3f3  lea     rdx, [rsp+270h+var_240]
0x18000b3f8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b3fd  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000b402  mov     ebx, eax
0x18000b404  test    eax, eax
0x18000b406  jns     short loc_18000B3B4
0x18000b408  mov     edx, 137h
0x18000b40d  jmp     loc_18000B37F
```
