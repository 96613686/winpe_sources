# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180005d54`
- end: `0x180005ec7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007108`

## callees

- `0x180002a60`
- `0x1800055cc`
- `0x1800055ec`
- `0x180005d54`
- `0x180006ef0`
- `0x180007e90`
- `0x1800096ec`
- `0x180009eac`
- `0x18000a388`
- `0x18000ad34`
- `0x18000b090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005dd7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005dd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005d8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005d8c`

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
0x180005d54  mov     [rsp-8+arg_10], rbx
0x180005d59  mov     [rsp-8+arg_18], rdi
0x180005d5e  push    rbp
0x180005d5f  lea     rbp, [rsp-170h]
0x180005d67  sub     rsp, 270h
0x180005d6e  mov     rax, cs:__security_cookie
0x180005d75  xor     rax, rsp
0x180005d78  mov     [rbp+170h+var_10], rax
0x180005d7f  mov     rdi, rdx
0x180005d82  mov     qword ptr [rdx], 0
0x180005d89  mov     rbx, rcx
0x180005d8c  call    cs:__imp_GetCurrentProcessId
0x180005d93  nop     dword ptr [rax+rax+00h]
0x180005d98  mov     [rsp+270h+var_248], rbx
0x180005d9d  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005da4  mov     r9d, eax
0x180005da7  mov     [rsp+270h+var_250], 130h; int
0x180005daf  mov     edx, 104h; unsigned __int64
0x180005db4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005db9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005dbe  mov     r9d, 1F0001h; dwDesiredAccess
0x180005dc4  mov     [rsp+270h+var_240], 0
0x180005dcd  xor     r8d, r8d; dwFlags
0x180005dd0  lea     rdx, [rsp+270h+Name]; lpName
0x180005dd5  xor     ecx, ecx; lpMutexAttributes
0x180005dd7  call    cs:__imp_CreateMutexExW
0x180005dde  nop     dword ptr [rax+rax+00h]
0x180005de3  mov     rdx, rax
0x180005de6  lea     rcx, [rsp+270h+var_240]
0x180005deb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005df0  cmp     [rsp+270h+var_240], 0
0x180005df6  jnz     short loc_180005E01
0x180005df8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005dfd  mov     ebx, eax
0x180005dff  jmp     short loc_180005E74
0x180005e01  lea     rdx, [rsp+270h+var_238]
0x180005e06  lea     rcx, [rsp+270h+var_240]
0x180005e0b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005e10  lea     rdx, [rsp+270h+var_230]; void **
0x180005e15  mov     [rsp+270h+var_230], 0
0x180005e1e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005e23  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005e28  mov     ebx, eax
0x180005e2a  test    eax, eax
0x180005e2c  jns     short loc_180005E55
0x180005e2e  mov     edx, 12Eh; void *
0x180005e33  mov     rcx, [rbp+178h]; this
0x180005e3a  lea     r8, aWil; "wil"
0x180005e41  mov     r9d, eax; char *
0x180005e44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e49  lea     rcx, [rsp+270h+var_238]
0x180005e4e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005e53  jmp     short loc_180005E74
0x180005e55  mov     rcx, [rsp+270h+var_230]
0x180005e5a  test    rcx, rcx
0x180005e5d  jz      short loc_180005EA5
0x180005e5f  mov     [rdi], rcx
0x180005e62  mov     eax, [rcx]
0x180005e64  inc     eax
0x180005e66  mov     [rcx], eax
0x180005e68  lea     rcx, [rsp+270h+var_238]
0x180005e6d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005e72  xor     ebx, ebx
0x180005e74  lea     rcx, [rsp+270h+var_240]
0x180005e79  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005e7e  mov     eax, ebx
0x180005e80  mov     rcx, [rbp+170h+var_10]
0x180005e87  xor     rcx, rsp; StackCookie
0x180005e8a  call    __security_check_cookie
0x180005e8f  lea     r11, [rsp+270h+var_s0]
0x180005e97  mov     rbx, [r11+20h]
0x180005e9b  mov     rdi, [r11+28h]
0x180005e9f  mov     rsp, r11
0x180005ea2  pop     rbp
0x180005ea3  retn
0x180005ea5  mov     r8, rdi
0x180005ea8  lea     rdx, [rsp+270h+var_240]
0x180005ead  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005eb2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005eb7  mov     ebx, eax
0x180005eb9  test    eax, eax
0x180005ebb  jns     short loc_180005E68
0x180005ebd  mov     edx, 137h
0x180005ec2  jmp     loc_180005E33
```
