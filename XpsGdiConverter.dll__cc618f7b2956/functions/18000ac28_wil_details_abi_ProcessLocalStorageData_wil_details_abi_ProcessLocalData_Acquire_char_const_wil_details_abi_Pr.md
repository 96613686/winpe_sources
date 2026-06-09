# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000ac28`
- end: `0x18000ad87`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b738`

## callees

- `0x180008830`
- `0x18000aacc`
- `0x18000aae8`
- `0x18000ac28`
- `0x18000b498`
- `0x18000be74`
- `0x18000c264`
- `0x18000c840`
- `0x18000c9ac`
- `0x18000cd9c`
- `0x18000cea0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18000ac60`
- `KERNEL32!GetCurrentProcessId` at `0x18000ac60`
- `KERNEL32!CreateMutexExW` at `0x18000aca5`
- `KERNEL32!CreateMutexExW` at `0x18000aca5`

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
0x18000ac28  mov     [rsp-8+arg_10], rbx
0x18000ac2d  mov     [rsp-8+arg_18], rdi
0x18000ac32  push    rbp
0x18000ac33  lea     rbp, [rsp-170h]
0x18000ac3b  sub     rsp, 270h
0x18000ac42  mov     rax, cs:__security_cookie
0x18000ac49  xor     rax, rsp
0x18000ac4c  mov     [rbp+170h+var_10], rax
0x18000ac53  mov     rdi, rdx
0x18000ac56  mov     qword ptr [rdx], 0
0x18000ac5d  mov     rbx, rcx
0x18000ac60  call    cs:__imp_GetCurrentProcessId
0x18000ac66  mov     [rsp+270h+var_248], rbx
0x18000ac6b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000ac72  mov     r9d, eax
0x18000ac75  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000ac7d  mov     edx, 104h; unsigned __int64
0x18000ac82  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000ac87  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000ac8c  mov     r9d, 1F0001h; dwDesiredAccess
0x18000ac92  mov     [rsp+270h+var_240], 0
0x18000ac9b  xor     r8d, r8d; dwFlags
0x18000ac9e  lea     rdx, [rsp+270h+Name]; lpName
0x18000aca3  xor     ecx, ecx; lpMutexAttributes
0x18000aca5  call    cs:__imp_CreateMutexExW
0x18000acab  mov     rdx, rax
0x18000acae  lea     rcx, [rsp+270h+var_240]
0x18000acb3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000acb8  cmp     [rsp+270h+var_240], 0
0x18000acbe  jnz     short loc_18000ACC9
0x18000acc0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000acc5  mov     ebx, eax
0x18000acc7  jmp     short loc_18000AD35
0x18000acc9  lea     rdx, [rsp+270h+var_238]
0x18000acce  lea     rcx, [rsp+270h+var_240]
0x18000acd3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000acd8  lea     rdx, [rsp+270h+var_230]; void **
0x18000acdd  mov     [rsp+270h+var_230], 0
0x18000ace6  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000aceb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18000acf0  mov     ebx, eax
0x18000acf2  test    eax, eax
0x18000acf4  jns     short loc_18000AD16
0x18000acf6  mov     edx, 12Eh; void *
0x18000acfb  mov     rcx, [rbp+178h]; this
0x18000ad02  mov     r9d, eax; char *
0x18000ad05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad0a  lea     rcx, [rsp+270h+var_238]
0x18000ad0f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ad14  jmp     short loc_18000AD35
0x18000ad16  mov     rcx, [rsp+270h+var_230]
0x18000ad1b  test    rcx, rcx
0x18000ad1e  jz      short loc_18000AD65
0x18000ad20  mov     [rdi], rcx
0x18000ad23  mov     eax, [rcx]
0x18000ad25  inc     eax
0x18000ad27  mov     [rcx], eax
0x18000ad29  lea     rcx, [rsp+270h+var_238]
0x18000ad2e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ad33  xor     ebx, ebx
0x18000ad35  lea     rcx, [rsp+270h+var_240]
0x18000ad3a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ad3f  mov     eax, ebx
0x18000ad41  mov     rcx, [rbp+170h+var_10]
0x18000ad48  xor     rcx, rsp; StackCookie
0x18000ad4b  call    __security_check_cookie
0x18000ad50  lea     r11, [rsp+270h+var_s0]
0x18000ad58  mov     rbx, [r11+20h]
0x18000ad5c  mov     rdi, [r11+28h]
0x18000ad60  mov     rsp, r11
0x18000ad63  pop     rbp
0x18000ad64  retn
0x18000ad65  mov     r8, rdi
0x18000ad68  lea     rdx, [rsp+270h+var_240]
0x18000ad6d  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000ad72  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000ad77  mov     ebx, eax
0x18000ad79  test    eax, eax
0x18000ad7b  jns     short loc_18000AD29
0x18000ad7d  mov     edx, 137h
0x18000ad82  jmp     loc_18000ACFB
```
