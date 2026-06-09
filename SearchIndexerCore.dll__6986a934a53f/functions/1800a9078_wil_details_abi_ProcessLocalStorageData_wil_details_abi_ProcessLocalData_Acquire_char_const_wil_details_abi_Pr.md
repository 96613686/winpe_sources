# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800a9078`
- end: `0x1800a91da`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800aa92c`

## callees

- `0x1800789c0`
- `0x1800a8d5c`
- `0x1800a8d78`
- `0x1800a9078`
- `0x1800aa658`
- `0x1800ab344`
- `0x1800ac75c`
- `0x1800ace98`
- `0x1800ad318`
- `0x1800adbac`
- `0x1800ade4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a90b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a90b0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800a90f5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800a90f5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x1800a9078  mov     [rsp-8+arg_10], rbx
0x1800a907d  mov     [rsp-8+arg_18], rdi
0x1800a9082  push    rbp
0x1800a9083  lea     rbp, [rsp-170h]
0x1800a908b  sub     rsp, 270h
0x1800a9092  mov     rax, cs:__security_cookie
0x1800a9099  xor     rax, rsp
0x1800a909c  mov     [rbp+170h+var_10], rax
0x1800a90a3  mov     rdi, rdx
0x1800a90a6  mov     rbx, rcx
0x1800a90a9  mov     qword ptr [rdx], 0
0x1800a90b0  call    cs:__imp_GetCurrentProcessId
0x1800a90b6  mov     r9d, eax
0x1800a90b9  mov     [rsp+270h+var_248], rbx
0x1800a90be  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800a90c6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800a90cd  mov     edx, 104h; unsigned __int64
0x1800a90d2  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800a90d7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800a90dc  mov     [rsp+270h+var_240], 0
0x1800a90e5  mov     r9d, 1F0001h; dwDesiredAccess
0x1800a90eb  xor     r8d, r8d; dwFlags
0x1800a90ee  lea     rdx, [rsp+270h+Name]; lpName
0x1800a90f3  xor     ecx, ecx; lpMutexAttributes
0x1800a90f5  call    cs:__imp_CreateMutexExW
0x1800a90fb  mov     rdx, rax
0x1800a90fe  lea     rcx, [rsp+270h+var_240]
0x1800a9103  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800a9108  cmp     [rsp+270h+var_240], 0
0x1800a910e  jnz     short loc_1800A9119
0x1800a9110  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800a9115  mov     ebx, eax
0x1800a9117  jmp     short loc_1800A9187
0x1800a9119  lea     rdx, [rsp+270h+var_238]
0x1800a911e  lea     rcx, [rsp+270h+var_240]
0x1800a9123  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800a9128  nop
0x1800a9129  mov     [rsp+270h+var_230], 0
0x1800a9132  lea     rdx, [rsp+270h+var_230]; void **
0x1800a9137  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800a913c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1800a9141  mov     ebx, eax
0x1800a9143  test    eax, eax
0x1800a9145  jns     short loc_1800A9168
0x1800a9147  mov     edx, 12Eh; void *
0x1800a914c  mov     r9d, eax; char *
0x1800a914f  mov     rcx, [rbp+178h]; this
0x1800a9156  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a915b  nop
0x1800a915c  lea     rcx, [rsp+270h+var_238]
0x1800a9161  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a9166  jmp     short loc_1800A9187
0x1800a9168  mov     rcx, [rsp+270h+var_230]
0x1800a916d  test    rcx, rcx
0x1800a9170  jz      short loc_1800A91B7
0x1800a9172  mov     [rdi], rcx
0x1800a9175  mov     eax, [rcx]
0x1800a9177  inc     eax
0x1800a9179  mov     [rcx], eax
0x1800a917b  lea     rcx, [rsp+270h+var_238]
0x1800a9180  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a9185  xor     ebx, ebx
0x1800a9187  lea     rcx, [rsp+270h+var_240]
0x1800a918c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a9191  mov     eax, ebx
0x1800a9193  mov     rcx, [rbp+170h+var_10]
0x1800a919a  xor     rcx, rsp; StackCookie
0x1800a919d  call    __security_check_cookie
0x1800a91a2  lea     r11, [rsp+270h+var_s0]
0x1800a91aa  mov     rbx, [r11+20h]
0x1800a91ae  mov     rdi, [r11+28h]
0x1800a91b2  mov     rsp, r11
0x1800a91b5  pop     rbp
0x1800a91b6  retn
0x1800a91b7  mov     r8, rdi
0x1800a91ba  lea     rdx, [rsp+270h+var_240]
0x1800a91bf  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800a91c4  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800a91c9  mov     ebx, eax
0x1800a91cb  test    eax, eax
0x1800a91cd  jns     short loc_1800A917B
0x1800a91cf  mov     edx, 137h
0x1800a91d4  jmp     loc_1800A914C
```
