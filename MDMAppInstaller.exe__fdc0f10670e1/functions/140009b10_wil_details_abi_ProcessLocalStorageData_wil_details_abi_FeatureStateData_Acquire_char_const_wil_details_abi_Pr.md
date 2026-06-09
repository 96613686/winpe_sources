# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140009b10`
- end: `0x140009c76`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000ccec`

## callees

- `0x140003c68`
- `0x140003c84`
- `0x140004888`
- `0x1400056a4`
- `0x140005c3c`
- `0x140005db0`
- `0x1400064e4`
- `0x14000690c`
- `0x140009b10`
- `0x14000ded8`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x140009b8d`
- `KERNEL32!CreateMutexExW` at `0x140009b8d`
- `KERNEL32!GetCurrentProcessId` at `0x140009b48`
- `KERNEL32!GetCurrentProcessId` at `0x140009b48`

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
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x140009b10  mov     [rsp-8+arg_10], rbx
0x140009b15  mov     [rsp-8+arg_18], rdi
0x140009b1a  push    rbp
0x140009b1b  lea     rbp, [rsp-170h]
0x140009b23  sub     rsp, 270h
0x140009b2a  mov     rax, cs:__security_cookie
0x140009b31  xor     rax, rsp
0x140009b34  mov     [rbp+170h+var_10], rax
0x140009b3b  mov     rdi, rdx
0x140009b3e  mov     qword ptr [rdx], 0
0x140009b45  mov     rbx, rcx
0x140009b48  call    cs:__imp_GetCurrentProcessId
0x140009b4e  mov     [rsp+270h+var_248], rbx
0x140009b53  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140009b5a  mov     r9d, eax
0x140009b5d  mov     [rsp+270h+var_250], 130h; int
0x140009b65  mov     edx, 104h; unsigned __int64
0x140009b6a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140009b6f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009b74  mov     r9d, 1F0001h; dwDesiredAccess
0x140009b7a  mov     [rsp+270h+var_240], 0
0x140009b83  xor     r8d, r8d; dwFlags
0x140009b86  lea     rdx, [rsp+270h+Name]; lpName
0x140009b8b  xor     ecx, ecx; lpMutexAttributes
0x140009b8d  call    cs:__imp_CreateMutexExW
0x140009b93  mov     rdx, rax
0x140009b96  lea     rcx, [rsp+270h+var_240]
0x140009b9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140009ba0  cmp     [rsp+270h+var_240], 0
0x140009ba6  jnz     short loc_140009BB1
0x140009ba8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009bad  mov     ebx, eax
0x140009baf  jmp     short loc_140009C24
0x140009bb1  lea     rdx, [rsp+270h+var_238]
0x140009bb6  lea     rcx, [rsp+270h+var_240]
0x140009bbb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140009bc0  lea     rdx, [rsp+270h+var_230]; void **
0x140009bc5  mov     [rsp+270h+var_230], 0
0x140009bce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140009bd3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140009bd8  mov     ebx, eax
0x140009bda  test    eax, eax
0x140009bdc  jns     short loc_140009C05
0x140009bde  mov     edx, 12Eh; void *
0x140009be3  mov     rcx, [rbp+178h]; this
0x140009bea  lea     r8, aWil; "wil"
0x140009bf1  mov     r9d, eax; char *
0x140009bf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009bf9  lea     rcx, [rsp+270h+var_238]
0x140009bfe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009c03  jmp     short loc_140009C24
0x140009c05  mov     rcx, [rsp+270h+var_230]
0x140009c0a  test    rcx, rcx
0x140009c0d  jz      short loc_140009C54
0x140009c0f  mov     [rdi], rcx
0x140009c12  mov     eax, [rcx]
0x140009c14  inc     eax
0x140009c16  mov     [rcx], eax
0x140009c18  lea     rcx, [rsp+270h+var_238]
0x140009c1d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009c22  xor     ebx, ebx
0x140009c24  lea     rcx, [rsp+270h+var_240]
0x140009c29  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009c2e  mov     eax, ebx
0x140009c30  mov     rcx, [rbp+170h+var_10]
0x140009c37  xor     rcx, rsp; StackCookie
0x140009c3a  call    __security_check_cookie
0x140009c3f  lea     r11, [rsp+270h+var_s0]
0x140009c47  mov     rbx, [r11+20h]
0x140009c4b  mov     rdi, [r11+28h]
0x140009c4f  mov     rsp, r11
0x140009c52  pop     rbp
0x140009c53  retn
0x140009c54  mov     r8, rdi
0x140009c57  lea     rdx, [rsp+270h+var_240]
0x140009c5c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140009c61  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140009c66  mov     ebx, eax
0x140009c68  test    eax, eax
0x140009c6a  jns     short loc_140009C18
0x140009c6c  mov     edx, 137h
0x140009c71  jmp     loc_140009BE3
```
