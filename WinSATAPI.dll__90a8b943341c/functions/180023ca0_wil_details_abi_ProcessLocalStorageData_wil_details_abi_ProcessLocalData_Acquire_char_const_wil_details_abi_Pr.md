# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180023ca0`
- end: `0x180023e06`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002544c`

## callees

- `0x180010690`
- `0x180023414`
- `0x180023434`
- `0x180023ca0`
- `0x180024f50`
- `0x180025ee8`
- `0x180027218`
- `0x180027cf8`
- `0x1800297f4`
- `0x18002b26c`
- `0x18002fb50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023cd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023cd5`
- `KERNEL32!CreateMutexExW` at `0x180023d1d`
- `KERNEL32!CreateMutexExW` at `0x180023d1d`

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
      v9 = 299;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      *(_DWORD *)*a2 = *v10 + 1;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 308;
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
0x180023ca0  mov     [rsp-8+arg_10], rbx
0x180023ca5  mov     [rsp-8+arg_18], rdi
0x180023caa  push    rbp
0x180023cab  lea     rbp, [rsp-170h]
0x180023cb3  sub     rsp, 270h
0x180023cba  mov     rax, cs:__security_cookie
0x180023cc1  xor     rax, rsp
0x180023cc4  mov     [rbp+170h+var_10], rax
0x180023ccb  and     qword ptr [rdx], 0
0x180023ccf  mov     rdi, rdx
0x180023cd2  mov     rbx, rcx
0x180023cd5  call    cs:__imp_GetCurrentProcessId
0x180023cdc  nop     dword ptr [rax+rax+00h]
0x180023ce1  mov     [rsp+270h+var_248], rbx
0x180023ce6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180023ced  mov     r9d, eax
0x180023cf0  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180023cf8  mov     edx, 104h; unsigned __int64
0x180023cfd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023d02  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023d07  and     [rsp+270h+var_240], 0
0x180023d0d  lea     rdx, [rsp+270h+Name]; lpName
0x180023d12  mov     r9d, 1F0001h; dwDesiredAccess
0x180023d18  xor     r8d, r8d; dwFlags
0x180023d1b  xor     ecx, ecx; lpMutexAttributes
0x180023d1d  call    cs:__imp_CreateMutexExW
0x180023d24  nop     dword ptr [rax+rax+00h]
0x180023d29  mov     rdx, rax
0x180023d2c  lea     rcx, [rsp+270h+var_240]
0x180023d31  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180023d36  cmp     [rsp+270h+var_240], 0
0x180023d3c  jnz     short loc_180023D47
0x180023d3e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180023d43  mov     ebx, eax
0x180023d45  jmp     short loc_180023DB3
0x180023d47  lea     rdx, [rsp+270h+var_238]
0x180023d4c  lea     rcx, [rsp+270h+var_240]
0x180023d51  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180023d56  and     [rsp+270h+var_230], 0
0x180023d5c  lea     rdx, [rsp+270h+var_230]; void **
0x180023d61  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023d66  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180023d6b  mov     ebx, eax
0x180023d6d  test    eax, eax
0x180023d6f  jns     short loc_180023D91
0x180023d71  mov     edx, 12Bh; void *
0x180023d76  mov     rcx, [rbp+178h]; this
0x180023d7d  mov     r9d, eax; char *
0x180023d80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023d85  lea     rcx, [rsp+270h+var_238]
0x180023d8a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023d8f  jmp     short loc_180023DB3
0x180023d91  mov     rcx, [rsp+270h+var_230]
0x180023d96  test    rcx, rcx
0x180023d99  jz      short loc_180023DE4
0x180023d9b  mov     [rdi], rcx
0x180023d9e  mov     ecx, [rcx]
0x180023da0  mov     rax, [rdi]
0x180023da3  inc     ecx
0x180023da5  mov     [rax], ecx
0x180023da7  lea     rcx, [rsp+270h+var_238]
0x180023dac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023db1  xor     ebx, ebx
0x180023db3  lea     rcx, [rsp+270h+var_240]
0x180023db8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023dbd  mov     eax, ebx
0x180023dbf  mov     rcx, [rbp+170h+var_10]
0x180023dc6  xor     rcx, rsp; StackCookie
0x180023dc9  call    __security_check_cookie
0x180023dce  lea     r11, [rsp+270h+var_s0]
0x180023dd6  mov     rbx, [r11+20h]
0x180023dda  mov     rdi, [r11+28h]
0x180023dde  mov     rsp, r11
0x180023de1  pop     rbp
0x180023de2  retn
0x180023de4  mov     r8, rdi
0x180023de7  lea     rdx, [rsp+270h+var_240]
0x180023dec  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023df1  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180023df6  mov     ebx, eax
0x180023df8  test    eax, eax
0x180023dfa  jns     short loc_180023DA7
0x180023dfc  mov     edx, 134h
0x180023e01  jmp     loc_180023D76
```
