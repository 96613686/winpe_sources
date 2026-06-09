# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180048e70`
- end: `0x180048fd6`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1801122b8`

## callees

- `0x180015eec`
- `0x18003de88`
- `0x18003f100`
- `0x18003f184`
- `0x180040658`
- `0x1800407d8`
- `0x180048e70`
- `0x180048fdc`
- `0x1800517e0`
- `0x180053518`
- `0x180059920`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180048eed`
- `KERNEL32!CreateMutexExW` at `0x180048eed`
- `KERNEL32!GetCurrentProcessId` at `0x180048ea8`
- `KERNEL32!GetCurrentProcessId` at `0x180048ea8`

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
0x180048e70  mov     [rsp-8+arg_10], rbx
0x180048e75  mov     [rsp-8+arg_18], rdi
0x180048e7a  push    rbp
0x180048e7b  lea     rbp, [rsp-170h]
0x180048e83  sub     rsp, 270h
0x180048e8a  mov     rax, cs:__security_cookie
0x180048e91  xor     rax, rsp
0x180048e94  mov     [rbp+170h+var_10], rax
0x180048e9b  mov     rdi, rdx
0x180048e9e  mov     qword ptr [rdx], 0
0x180048ea5  mov     rbx, rcx
0x180048ea8  call    cs:__imp_GetCurrentProcessId
0x180048eae  mov     [rsp+270h+var_248], rbx
0x180048eb3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180048eba  mov     r9d, eax
0x180048ebd  mov     [rsp+270h+var_250], 130h; int
0x180048ec5  mov     edx, 104h; unsigned __int64
0x180048eca  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180048ecf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048ed4  mov     r9d, 1F0001h; dwDesiredAccess
0x180048eda  mov     [rsp+270h+var_240], 0
0x180048ee3  xor     r8d, r8d; dwFlags
0x180048ee6  lea     rdx, [rsp+270h+Name]; lpName
0x180048eeb  xor     ecx, ecx; lpMutexAttributes
0x180048eed  call    cs:__imp_CreateMutexExW
0x180048ef3  mov     rdx, rax
0x180048ef6  lea     rcx, [rsp+270h+var_240]
0x180048efb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180048f00  cmp     [rsp+270h+var_240], 0
0x180048f06  jnz     short loc_180048F11
0x180048f08  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180048f0d  mov     ebx, eax
0x180048f0f  jmp     short loc_180048F84
0x180048f11  lea     rdx, [rsp+270h+var_238]
0x180048f16  lea     rcx, [rsp+270h+var_240]
0x180048f1b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180048f20  lea     rdx, [rsp+270h+var_230]; void **
0x180048f25  mov     [rsp+270h+var_230], 0
0x180048f2e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180048f33  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180048f38  mov     ebx, eax
0x180048f3a  test    eax, eax
0x180048f3c  jns     short loc_180048F65
0x180048f3e  mov     edx, 12Eh; void *
0x180048f43  mov     rcx, [rbp+178h]; this
0x180048f4a  lea     r8, aWil; "wil"
0x180048f51  mov     r9d, eax; char *
0x180048f54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048f59  lea     rcx, [rsp+270h+var_238]
0x180048f5e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180048f63  jmp     short loc_180048F84
0x180048f65  mov     rcx, [rsp+270h+var_230]
0x180048f6a  test    rcx, rcx
0x180048f6d  jz      short loc_180048FB4
0x180048f6f  mov     [rdi], rcx
0x180048f72  mov     eax, [rcx]
0x180048f74  inc     eax
0x180048f76  mov     [rcx], eax
0x180048f78  lea     rcx, [rsp+270h+var_238]
0x180048f7d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180048f82  xor     ebx, ebx
0x180048f84  lea     rcx, [rsp+270h+var_240]
0x180048f89  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180048f8e  mov     eax, ebx
0x180048f90  mov     rcx, [rbp+170h+var_10]
0x180048f97  xor     rcx, rsp; StackCookie
0x180048f9a  call    __security_check_cookie
0x180048f9f  lea     r11, [rsp+270h+var_s0]
0x180048fa7  mov     rbx, [r11+20h]
0x180048fab  mov     rdi, [r11+28h]
0x180048faf  mov     rsp, r11
0x180048fb2  pop     rbp
0x180048fb3  retn
0x180048fb4  mov     r8, rdi
0x180048fb7  lea     rdx, [rsp+270h+var_240]
0x180048fbc  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180048fc1  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180048fc6  mov     ebx, eax
0x180048fc8  test    eax, eax
0x180048fca  jns     short loc_180048F78
0x180048fcc  mov     edx, 137h
0x180048fd1  jmp     loc_180048F43
```
