# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800ba57c`
- end: `0x1800ba6e2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800baaf4`

## callees

- `0x180097b64`
- `0x18009a680`
- `0x18009a7e8`
- `0x18009d670`
- `0x18009fc80`
- `0x18009fc9c`
- `0x1800a15ac`
- `0x1800a1718`
- `0x1800a1b04`
- `0x1800a1bf4`
- `0x1800ba57c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800ba5f9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800ba5f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ba5b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ba5b4`

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
0x1800ba57c  mov     [rsp-8+arg_10], rbx
0x1800ba581  mov     [rsp-8+arg_18], rdi
0x1800ba586  push    rbp
0x1800ba587  lea     rbp, [rsp-170h]
0x1800ba58f  sub     rsp, 270h
0x1800ba596  mov     rax, cs:__security_cookie
0x1800ba59d  xor     rax, rsp
0x1800ba5a0  mov     [rbp+170h+var_10], rax
0x1800ba5a7  mov     rdi, rdx
0x1800ba5aa  mov     qword ptr [rdx], 0
0x1800ba5b1  mov     rbx, rcx
0x1800ba5b4  call    cs:__imp_GetCurrentProcessId
0x1800ba5ba  mov     [rsp+270h+var_248], rbx
0x1800ba5bf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800ba5c6  mov     r9d, eax
0x1800ba5c9  mov     [rsp+270h+var_250], 130h; int
0x1800ba5d1  mov     edx, 104h; unsigned __int64
0x1800ba5d6  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800ba5db  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ba5e0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800ba5e6  mov     [rsp+270h+var_240], 0
0x1800ba5ef  xor     r8d, r8d; dwFlags
0x1800ba5f2  lea     rdx, [rsp+270h+Name]; lpName
0x1800ba5f7  xor     ecx, ecx; lpMutexAttributes
0x1800ba5f9  call    cs:__imp_CreateMutexExW
0x1800ba5ff  mov     rdx, rax
0x1800ba602  lea     rcx, [rsp+270h+var_240]
0x1800ba607  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800ba60c  cmp     [rsp+270h+var_240], 0
0x1800ba612  jnz     short loc_1800BA61D
0x1800ba614  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800ba619  mov     ebx, eax
0x1800ba61b  jmp     short loc_1800BA690
0x1800ba61d  lea     rdx, [rsp+270h+var_238]
0x1800ba622  lea     rcx, [rsp+270h+var_240]
0x1800ba627  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800ba62c  lea     rdx, [rsp+270h+var_230]; void **
0x1800ba631  mov     [rsp+270h+var_230], 0
0x1800ba63a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800ba63f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1800ba644  mov     ebx, eax
0x1800ba646  test    eax, eax
0x1800ba648  jns     short loc_1800BA671
0x1800ba64a  mov     edx, 12Eh; void *
0x1800ba64f  mov     rcx, [rbp+178h]; this
0x1800ba656  lea     r8, aWil; "wil"
0x1800ba65d  mov     r9d, eax; char *
0x1800ba660  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba665  lea     rcx, [rsp+270h+var_238]
0x1800ba66a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ba66f  jmp     short loc_1800BA690
0x1800ba671  mov     rcx, [rsp+270h+var_230]
0x1800ba676  test    rcx, rcx
0x1800ba679  jz      short loc_1800BA6C0
0x1800ba67b  mov     [rdi], rcx
0x1800ba67e  mov     eax, [rcx]
0x1800ba680  inc     eax
0x1800ba682  mov     [rcx], eax
0x1800ba684  lea     rcx, [rsp+270h+var_238]
0x1800ba689  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ba68e  xor     ebx, ebx
0x1800ba690  lea     rcx, [rsp+270h+var_240]
0x1800ba695  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ba69a  mov     eax, ebx
0x1800ba69c  mov     rcx, [rbp+170h+var_10]
0x1800ba6a3  xor     rcx, rsp; StackCookie
0x1800ba6a6  call    __security_check_cookie
0x1800ba6ab  lea     r11, [rsp+270h+var_s0]
0x1800ba6b3  mov     rbx, [r11+20h]
0x1800ba6b7  mov     rdi, [r11+28h]
0x1800ba6bb  mov     rsp, r11
0x1800ba6be  pop     rbp
0x1800ba6bf  retn
0x1800ba6c0  mov     r8, rdi
0x1800ba6c3  lea     rdx, [rsp+270h+var_240]
0x1800ba6c8  lea     rcx, [rsp+270h+Name]
0x1800ba6cd  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800ba6d2  mov     ebx, eax
0x1800ba6d4  test    eax, eax
0x1800ba6d6  jns     short loc_1800BA684
0x1800ba6d8  mov     edx, 137h
0x1800ba6dd  jmp     loc_1800BA64F
```
