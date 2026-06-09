# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180005d50`
- end: `0x180005eaf`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007d2c`

## callees

- `0x180005808`
- `0x180005824`
- `0x180005d50`
- `0x180007c44`
- `0x180008aa8`
- `0x18000a7b8`
- `0x18000acac`
- `0x18000b120`
- `0x18000ba3c`
- `0x18000bd50`
- `0x180043090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005dcd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005dcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005d88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005d88`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180005d50  mov     [rsp-8+arg_10], rbx
0x180005d55  mov     [rsp-8+arg_18], rdi
0x180005d5a  push    rbp
0x180005d5b  lea     rbp, [rsp-170h]
0x180005d63  sub     rsp, 270h
0x180005d6a  mov     rax, cs:__security_cookie
0x180005d71  xor     rax, rsp
0x180005d74  mov     [rbp+170h+var_10], rax
0x180005d7b  mov     rdi, rdx
0x180005d7e  mov     qword ptr [rdx], 0
0x180005d85  mov     rbx, rcx
0x180005d88  call    cs:__imp_GetCurrentProcessId
0x180005d8e  mov     [rsp+270h+var_248], rbx
0x180005d93  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005d9a  mov     r9d, eax
0x180005d9d  mov     [rsp+270h+var_250], 130h; int
0x180005da5  mov     edx, 104h; unsigned __int64
0x180005daa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005daf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005db4  mov     r9d, 1F0001h; dwDesiredAccess
0x180005dba  mov     [rsp+270h+var_240], 0
0x180005dc3  xor     r8d, r8d; dwFlags
0x180005dc6  lea     rdx, [rsp+270h+Name]; lpName
0x180005dcb  xor     ecx, ecx; lpMutexAttributes
0x180005dcd  call    cs:__imp_CreateMutexExW
0x180005dd3  mov     rdx, rax
0x180005dd6  lea     rcx, [rsp+270h+var_240]
0x180005ddb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005de0  cmp     [rsp+270h+var_240], 0
0x180005de6  jnz     short loc_180005DF1
0x180005de8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005ded  mov     ebx, eax
0x180005def  jmp     short loc_180005E5D
0x180005df1  lea     rdx, [rsp+270h+var_238]
0x180005df6  lea     rcx, [rsp+270h+var_240]
0x180005dfb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005e00  lea     rdx, [rsp+270h+var_230]; void **
0x180005e05  mov     [rsp+270h+var_230], 0
0x180005e0e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005e13  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005e18  mov     ebx, eax
0x180005e1a  test    eax, eax
0x180005e1c  jns     short loc_180005E3E
0x180005e1e  mov     edx, 12Eh; void *
0x180005e23  mov     rcx, [rbp+178h]; this
0x180005e2a  mov     r9d, eax; char *
0x180005e2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e32  lea     rcx, [rsp+270h+var_238]
0x180005e37  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005e3c  jmp     short loc_180005E5D
0x180005e3e  mov     rcx, [rsp+270h+var_230]
0x180005e43  test    rcx, rcx
0x180005e46  jz      short loc_180005E8D
0x180005e48  mov     [rdi], rcx
0x180005e4b  mov     eax, [rcx]
0x180005e4d  inc     eax
0x180005e4f  mov     [rcx], eax
0x180005e51  lea     rcx, [rsp+270h+var_238]
0x180005e56  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005e5b  xor     ebx, ebx
0x180005e5d  lea     rcx, [rsp+270h+var_240]
0x180005e62  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005e67  mov     eax, ebx
0x180005e69  mov     rcx, [rbp+170h+var_10]
0x180005e70  xor     rcx, rsp; StackCookie
0x180005e73  call    __security_check_cookie
0x180005e78  lea     r11, [rsp+270h+var_s0]
0x180005e80  mov     rbx, [r11+20h]
0x180005e84  mov     rdi, [r11+28h]
0x180005e88  mov     rsp, r11
0x180005e8b  pop     rbp
0x180005e8c  retn
0x180005e8d  mov     r8, rdi
0x180005e90  lea     rdx, [rsp+270h+var_240]
0x180005e95  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005e9a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005e9f  mov     ebx, eax
0x180005ea1  test    eax, eax
0x180005ea3  jns     short loc_180005E51
0x180005ea5  mov     edx, 137h
0x180005eaa  jmp     loc_180005E23
```
