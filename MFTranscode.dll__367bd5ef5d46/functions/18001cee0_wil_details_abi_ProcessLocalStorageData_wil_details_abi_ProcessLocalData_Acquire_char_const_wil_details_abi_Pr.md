# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001cee0`
- end: `0x18001d075`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001e834`

## callees

- `0x1800159c8`
- `0x180015b60`
- `0x180015b98`
- `0x1800174c0`
- `0x18001ccc0`
- `0x18001ccdc`
- `0x18001cee0`
- `0x1800220a8`
- `0x1800221b8`
- `0x18002b9fc`
- `0x18002baa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001cf18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001cf18`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001cf5d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001cf5d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  _DWORD *v15; // rcx
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v18 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v20 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v20,
    Mutex);
  if ( v20 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v20,
      v21);
    v22 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v22, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v10, (const char *)(unsigned int)ValueInternal, 120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v11, (const char *)LastErrorFailHr, v19);
      v13 = LastErrorFailHr;
      v14 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v14, v12, (const char *)v13, v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
      goto LABEL_9;
    }
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v17;
      if ( v17 < 0 )
      {
        v13 = (unsigned int)v17;
        v14 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18001cee0  mov     [rsp-8+arg_10], rbx
0x18001cee5  mov     [rsp-8+arg_18], rdi
0x18001ceea  push    rbp
0x18001ceeb  lea     rbp, [rsp-170h]
0x18001cef3  sub     rsp, 270h
0x18001cefa  mov     rax, cs:__security_cookie
0x18001cf01  xor     rax, rsp
0x18001cf04  mov     [rbp+170h+var_10], rax
0x18001cf0b  mov     rdi, rdx
0x18001cf0e  mov     qword ptr [rdx], 0
0x18001cf15  mov     rbx, rcx
0x18001cf18  call    cs:__imp_GetCurrentProcessId
0x18001cf1e  mov     [rsp+270h+var_248], rbx
0x18001cf23  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001cf2a  mov     r9d, eax
0x18001cf2d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001cf35  mov     edx, 104h; unsigned __int64
0x18001cf3a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001cf3f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cf44  mov     r9d, 1F0001h; dwDesiredAccess
0x18001cf4a  mov     [rsp+270h+var_240], 0
0x18001cf53  xor     r8d, r8d; dwFlags
0x18001cf56  lea     rdx, [rsp+270h+Name]; lpName
0x18001cf5b  xor     ecx, ecx; lpMutexAttributes
0x18001cf5d  call    cs:__imp_CreateMutexExW
0x18001cf63  mov     rdx, rax
0x18001cf66  lea     rcx, [rsp+270h+var_240]
0x18001cf6b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001cf70  cmp     [rsp+270h+var_240], 0
0x18001cf76  jnz     short loc_18001CF84
0x18001cf78  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001cf7d  mov     ebx, eax
0x18001cf7f  jmp     loc_18001D020
0x18001cf84  lea     rdx, [rsp+270h+var_238]
0x18001cf89  lea     rcx, [rsp+270h+var_240]
0x18001cf8e  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001cf93  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18001cf98  mov     [rsp+270h+var_230], 0
0x18001cfa1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001cfa6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001cfab  mov     ebx, eax
0x18001cfad  test    eax, eax
0x18001cfaf  jns     short loc_18001CFF9
0x18001cfb1  mov     rcx, [rbp+178h]; this
0x18001cfb8  mov     r9d, eax; char *
0x18001cfbb  mov     edx, 66h ; 'f'; void *
0x18001cfc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cfc5  mov     rcx, [rbp+178h]; this
0x18001cfcc  mov     r9d, ebx; char *
0x18001cfcf  mov     edx, 6Fh ; 'o'; void *
0x18001cfd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cfd9  mov     r9d, ebx; char *
0x18001cfdc  mov     edx, 12Eh; void *
0x18001cfe1  mov     rcx, [rbp+178h]; this
0x18001cfe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cfed  lea     rcx, [rsp+270h+var_238]
0x18001cff2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001cff7  jmp     short loc_18001D020
0x18001cff9  mov     rax, [rsp+270h+var_230]
0x18001cffe  lea     rcx, ds:0[rax*4]
0x18001d006  test    rcx, rcx
0x18001d009  jz      short loc_18001D050
0x18001d00b  mov     [rdi], rcx
0x18001d00e  mov     eax, [rcx]
0x18001d010  inc     eax
0x18001d012  mov     [rcx], eax
0x18001d014  lea     rcx, [rsp+270h+var_238]
0x18001d019  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d01e  xor     ebx, ebx
0x18001d020  lea     rcx, [rsp+270h+var_240]
0x18001d025  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d02a  mov     eax, ebx
0x18001d02c  mov     rcx, [rbp+170h+var_10]
0x18001d033  xor     rcx, rsp; StackCookie
0x18001d036  call    __security_check_cookie
0x18001d03b  lea     r11, [rsp+270h+var_s0]
0x18001d043  mov     rbx, [r11+20h]
0x18001d047  mov     rdi, [r11+28h]
0x18001d04b  mov     rsp, r11
0x18001d04e  pop     rbp
0x18001d04f  retn
0x18001d050  mov     r8, rdi
0x18001d053  lea     rdx, [rsp+270h+var_240]
0x18001d058  lea     rcx, [rsp+270h+Name]
0x18001d05d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001d062  mov     ebx, eax
0x18001d064  test    eax, eax
0x18001d066  jns     short loc_18001D014
0x18001d068  mov     r9d, eax
0x18001d06b  mov     edx, 137h
0x18001d070  jmp     loc_18001CFE1
```
