# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000ad4c`
- end: `0x18000aeab`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000cef0`

## callees

- `0x180002020`
- `0x1800051e0`
- `0x18000a740`
- `0x18000a75c`
- `0x18000ad4c`
- `0x18000c4a4`
- `0x18000dba0`
- `0x18000e784`
- `0x18000eccc`
- `0x18000f2dc`
- `0x18000fe84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000adc9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000adc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ad84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ad84`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x18000ad4c  mov     [rsp-8+arg_10], rbx
0x18000ad51  mov     [rsp-8+arg_18], rdi
0x18000ad56  push    rbp
0x18000ad57  lea     rbp, [rsp-170h]
0x18000ad5f  sub     rsp, 270h
0x18000ad66  mov     rax, cs:__security_cookie
0x18000ad6d  xor     rax, rsp
0x18000ad70  mov     [rbp+170h+var_10], rax
0x18000ad77  mov     rdi, rdx
0x18000ad7a  mov     qword ptr [rdx], 0
0x18000ad81  mov     rbx, rcx
0x18000ad84  call    cs:__imp_GetCurrentProcessId
0x18000ad8a  mov     [rsp+270h+var_248], rbx
0x18000ad8f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000ad96  mov     r9d, eax
0x18000ad99  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000ada1  mov     edx, 104h; unsigned __int64
0x18000ada6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000adab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000adb0  mov     r9d, 1F0001h; dwDesiredAccess
0x18000adb6  mov     [rsp+270h+var_240], 0
0x18000adbf  xor     r8d, r8d; dwFlags
0x18000adc2  lea     rdx, [rsp+270h+Name]; lpName
0x18000adc7  xor     ecx, ecx; lpMutexAttributes
0x18000adc9  call    cs:__imp_CreateMutexExW
0x18000adcf  mov     rdx, rax
0x18000add2  lea     rcx, [rsp+270h+var_240]
0x18000add7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000addc  cmp     [rsp+270h+var_240], 0
0x18000ade2  jnz     short loc_18000ADED
0x18000ade4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ade9  mov     ebx, eax
0x18000adeb  jmp     short loc_18000AE59
0x18000aded  lea     rdx, [rsp+270h+var_238]
0x18000adf2  lea     rcx, [rsp+270h+var_240]
0x18000adf7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000adfc  lea     rdx, [rsp+270h+var_230]; void **
0x18000ae01  mov     [rsp+270h+var_230], 0
0x18000ae0a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000ae0f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000ae14  mov     ebx, eax
0x18000ae16  test    eax, eax
0x18000ae18  jns     short loc_18000AE3A
0x18000ae1a  mov     edx, 12Eh; void *
0x18000ae1f  mov     rcx, [rbp+178h]; this
0x18000ae26  mov     r9d, eax; char *
0x18000ae29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae2e  lea     rcx, [rsp+270h+var_238]
0x18000ae33  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ae38  jmp     short loc_18000AE59
0x18000ae3a  mov     rcx, [rsp+270h+var_230]
0x18000ae3f  test    rcx, rcx
0x18000ae42  jz      short loc_18000AE89
0x18000ae44  mov     [rdi], rcx
0x18000ae47  mov     eax, [rcx]
0x18000ae49  inc     eax
0x18000ae4b  mov     [rcx], eax
0x18000ae4d  lea     rcx, [rsp+270h+var_238]
0x18000ae52  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ae57  xor     ebx, ebx
0x18000ae59  lea     rcx, [rsp+270h+var_240]
0x18000ae5e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ae63  mov     eax, ebx
0x18000ae65  mov     rcx, [rbp+170h+var_10]
0x18000ae6c  xor     rcx, rsp; StackCookie
0x18000ae6f  call    __security_check_cookie
0x18000ae74  lea     r11, [rsp+270h+var_s0]
0x18000ae7c  mov     rbx, [r11+20h]
0x18000ae80  mov     rdi, [r11+28h]
0x18000ae84  mov     rsp, r11
0x18000ae87  pop     rbp
0x18000ae88  retn
0x18000ae89  mov     r8, rdi
0x18000ae8c  lea     rdx, [rsp+270h+var_240]
0x18000ae91  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000ae96  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000ae9b  mov     ebx, eax
0x18000ae9d  test    eax, eax
0x18000ae9f  jns     short loc_18000AE4D
0x18000aea1  mov     edx, 137h
0x18000aea6  jmp     loc_18000AE1F
```
