# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001fd90`
- end: `0x18001fef6`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180028bb4`

## callees

- `0x1800130a0`
- `0x18001fd90`
- `0x180020110`
- `0x18002012c`
- `0x1800202bc`
- `0x180020344`
- `0x180026200`
- `0x180027294`
- `0x180027c1c`
- `0x180027db4`
- `0x1800295d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001fe0d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001fe0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fdc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fdc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
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
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
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
      (HANDLE *)&v12,
      &v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18001fd90  mov     [rsp-8+arg_10], rbx
0x18001fd95  mov     [rsp-8+arg_18], rdi
0x18001fd9a  push    rbp
0x18001fd9b  lea     rbp, [rsp-170h]
0x18001fda3  sub     rsp, 270h
0x18001fdaa  mov     rax, cs:__security_cookie
0x18001fdb1  xor     rax, rsp
0x18001fdb4  mov     [rbp+170h+var_10], rax
0x18001fdbb  mov     rdi, rdx
0x18001fdbe  mov     qword ptr [rdx], 0
0x18001fdc5  mov     rbx, rcx
0x18001fdc8  call    cs:__imp_GetCurrentProcessId
0x18001fdce  mov     [rsp+270h+var_248], rbx
0x18001fdd3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001fdda  mov     r9d, eax
0x18001fddd  mov     [rsp+270h+var_250], 130h; int
0x18001fde5  mov     edx, 104h; unsigned __int64
0x18001fdea  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001fdef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001fdf4  mov     r9d, 1F0001h; dwDesiredAccess
0x18001fdfa  mov     [rsp+270h+var_240], 0
0x18001fe03  xor     r8d, r8d; dwFlags
0x18001fe06  lea     rdx, [rsp+270h+Name]; lpName
0x18001fe0b  xor     ecx, ecx; lpMutexAttributes
0x18001fe0d  call    cs:__imp_CreateMutexExW
0x18001fe13  mov     rdx, rax
0x18001fe16  lea     rcx, [rsp+270h+var_240]
0x18001fe1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001fe20  cmp     [rsp+270h+var_240], 0
0x18001fe26  jnz     short loc_18001FE31
0x18001fe28  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001fe2d  mov     ebx, eax
0x18001fe2f  jmp     short loc_18001FEA4
0x18001fe31  lea     rdx, [rsp+270h+var_238]
0x18001fe36  lea     rcx, [rsp+270h+var_240]
0x18001fe3b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001fe40  lea     rdx, [rsp+270h+var_230]; void **
0x18001fe45  mov     [rsp+270h+var_230], 0
0x18001fe4e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001fe53  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001fe58  mov     ebx, eax
0x18001fe5a  test    eax, eax
0x18001fe5c  jns     short loc_18001FE85
0x18001fe5e  mov     edx, 12Eh; void *
0x18001fe63  mov     rcx, [rbp+178h]; this
0x18001fe6a  lea     r8, aWil; "wil"
0x18001fe71  mov     r9d, eax; char *
0x18001fe74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe79  lea     rcx, [rsp+270h+var_238]
0x18001fe7e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fe83  jmp     short loc_18001FEA4
0x18001fe85  mov     rcx, [rsp+270h+var_230]
0x18001fe8a  test    rcx, rcx
0x18001fe8d  jz      short loc_18001FED4
0x18001fe8f  mov     [rdi], rcx
0x18001fe92  mov     eax, [rcx]
0x18001fe94  inc     eax
0x18001fe96  mov     [rcx], eax
0x18001fe98  lea     rcx, [rsp+270h+var_238]
0x18001fe9d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fea2  xor     ebx, ebx
0x18001fea4  lea     rcx, [rsp+270h+var_240]
0x18001fea9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001feae  mov     eax, ebx
0x18001feb0  mov     rcx, [rbp+170h+var_10]
0x18001feb7  xor     rcx, rsp; StackCookie
0x18001feba  call    __security_check_cookie
0x18001febf  lea     r11, [rsp+270h+var_s0]
0x18001fec7  mov     rbx, [r11+20h]
0x18001fecb  mov     rdi, [r11+28h]
0x18001fecf  mov     rsp, r11
0x18001fed2  pop     rbp
0x18001fed3  retn
0x18001fed4  mov     r8, rdi
0x18001fed7  lea     rdx, [rsp+270h+var_240]
0x18001fedc  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001fee1  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001fee6  mov     ebx, eax
0x18001fee8  test    eax, eax
0x18001feea  jns     short loc_18001FE98
0x18001feec  mov     edx, 137h
0x18001fef1  jmp     loc_18001FE63
```
