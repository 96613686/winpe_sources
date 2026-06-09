# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000a7e8`
- end: `0x14000a94e`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000dda0`

## callees

- `0x140003620`
- `0x1400091f0`
- `0x14000920c`
- `0x14000a7e8`
- `0x14000d9e8`
- `0x14000f4d4`
- `0x1400136fc`
- `0x1400163c8`
- `0x140016dbc`
- `0x140018fe0`
- `0x14001af84`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x14000a865`
- `KERNEL32!CreateMutexExW` at `0x14000a865`
- `KERNEL32!GetCurrentProcessId` at `0x14000a820`
- `KERNEL32!GetCurrentProcessId` at `0x14000a820`

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
0x14000a7e8  mov     [rsp-8+arg_10], rbx
0x14000a7ed  mov     [rsp-8+arg_18], rdi
0x14000a7f2  push    rbp
0x14000a7f3  lea     rbp, [rsp-170h]
0x14000a7fb  sub     rsp, 270h
0x14000a802  mov     rax, cs:__security_cookie
0x14000a809  xor     rax, rsp
0x14000a80c  mov     [rbp+170h+var_10], rax
0x14000a813  mov     rdi, rdx
0x14000a816  mov     qword ptr [rdx], 0
0x14000a81d  mov     rbx, rcx
0x14000a820  call    cs:__imp_GetCurrentProcessId
0x14000a826  mov     [rsp+270h+var_248], rbx
0x14000a82b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000a832  mov     r9d, eax
0x14000a835  mov     [rsp+270h+var_250], 130h; int
0x14000a83d  mov     edx, 104h; unsigned __int64
0x14000a842  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000a847  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a84c  mov     r9d, 1F0001h; dwDesiredAccess
0x14000a852  mov     [rsp+270h+var_240], 0
0x14000a85b  xor     r8d, r8d; dwFlags
0x14000a85e  lea     rdx, [rsp+270h+Name]; lpName
0x14000a863  xor     ecx, ecx; lpMutexAttributes
0x14000a865  call    cs:__imp_CreateMutexExW
0x14000a86b  mov     rdx, rax
0x14000a86e  lea     rcx, [rsp+270h+var_240]
0x14000a873  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000a878  cmp     [rsp+270h+var_240], 0
0x14000a87e  jnz     short loc_14000A889
0x14000a880  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000a885  mov     ebx, eax
0x14000a887  jmp     short loc_14000A8FC
0x14000a889  lea     rdx, [rsp+270h+var_238]
0x14000a88e  lea     rcx, [rsp+270h+var_240]
0x14000a893  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x14000a898  lea     rdx, [rsp+270h+var_230]; void **
0x14000a89d  mov     [rsp+270h+var_230], 0
0x14000a8a6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000a8ab  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x14000a8b0  mov     ebx, eax
0x14000a8b2  test    eax, eax
0x14000a8b4  jns     short loc_14000A8DD
0x14000a8b6  mov     edx, 12Eh; void *
0x14000a8bb  mov     rcx, [rbp+178h]; this
0x14000a8c2  lea     r8, aWil; "wil"
0x14000a8c9  mov     r9d, eax; char *
0x14000a8cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a8d1  lea     rcx, [rsp+270h+var_238]
0x14000a8d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000a8db  jmp     short loc_14000A8FC
0x14000a8dd  mov     rcx, [rsp+270h+var_230]
0x14000a8e2  test    rcx, rcx
0x14000a8e5  jz      short loc_14000A92C
0x14000a8e7  mov     [rdi], rcx
0x14000a8ea  mov     eax, [rcx]
0x14000a8ec  inc     eax
0x14000a8ee  mov     [rcx], eax
0x14000a8f0  lea     rcx, [rsp+270h+var_238]
0x14000a8f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000a8fa  xor     ebx, ebx
0x14000a8fc  lea     rcx, [rsp+270h+var_240]
0x14000a901  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000a906  mov     eax, ebx
0x14000a908  mov     rcx, [rbp+170h+var_10]
0x14000a90f  xor     rcx, rsp; StackCookie
0x14000a912  call    __security_check_cookie
0x14000a917  lea     r11, [rsp+270h+var_s0]
0x14000a91f  mov     rbx, [r11+20h]
0x14000a923  mov     rdi, [r11+28h]
0x14000a927  mov     rsp, r11
0x14000a92a  pop     rbp
0x14000a92b  retn
0x14000a92c  mov     r8, rdi
0x14000a92f  lea     rdx, [rsp+270h+var_240]
0x14000a934  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000a939  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000a93e  mov     ebx, eax
0x14000a940  test    eax, eax
0x14000a942  jns     short loc_14000A8F0
0x14000a944  mov     edx, 137h
0x14000a949  jmp     loc_14000A8BB
```
