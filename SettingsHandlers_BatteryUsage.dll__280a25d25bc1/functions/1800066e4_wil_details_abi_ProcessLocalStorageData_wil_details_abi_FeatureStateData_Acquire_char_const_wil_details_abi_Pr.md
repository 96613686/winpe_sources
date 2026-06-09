# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800066e4`
- end: `0x18000684a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007bac`

## callees

- `0x1800028d0`
- `0x1800060f4`
- `0x180006110`
- `0x1800066e4`
- `0x1800079a8`
- `0x1800088f0`
- `0x18000a13c`
- `0x18000a8fc`
- `0x18000ad6c`
- `0x18000b78c`
- `0x18000bab8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000671c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000671c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006761`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006761`

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
0x1800066e4  mov     [rsp-8+arg_10], rbx
0x1800066e9  mov     [rsp-8+arg_18], rdi
0x1800066ee  push    rbp
0x1800066ef  lea     rbp, [rsp-170h]
0x1800066f7  sub     rsp, 270h
0x1800066fe  mov     rax, cs:__security_cookie
0x180006705  xor     rax, rsp
0x180006708  mov     [rbp+170h+var_10], rax
0x18000670f  mov     rdi, rdx
0x180006712  mov     qword ptr [rdx], 0
0x180006719  mov     rbx, rcx
0x18000671c  call    cs:__imp_GetCurrentProcessId
0x180006722  mov     [rsp+270h+var_248], rbx
0x180006727  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000672e  mov     r9d, eax
0x180006731  mov     [rsp+270h+var_250], 130h; int
0x180006739  mov     edx, 104h; unsigned __int64
0x18000673e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006743  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006748  mov     r9d, 1F0001h; dwDesiredAccess
0x18000674e  mov     [rsp+270h+var_240], 0
0x180006757  xor     r8d, r8d; dwFlags
0x18000675a  lea     rdx, [rsp+270h+Name]; lpName
0x18000675f  xor     ecx, ecx; lpMutexAttributes
0x180006761  call    cs:__imp_CreateMutexExW
0x180006767  mov     rdx, rax
0x18000676a  lea     rcx, [rsp+270h+var_240]
0x18000676f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006774  cmp     [rsp+270h+var_240], 0
0x18000677a  jnz     short loc_180006785
0x18000677c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006781  mov     ebx, eax
0x180006783  jmp     short loc_1800067F8
0x180006785  lea     rdx, [rsp+270h+var_238]
0x18000678a  lea     rcx, [rsp+270h+var_240]
0x18000678f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006794  lea     rdx, [rsp+270h+var_230]; void **
0x180006799  mov     [rsp+270h+var_230], 0
0x1800067a2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800067a7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800067ac  mov     ebx, eax
0x1800067ae  test    eax, eax
0x1800067b0  jns     short loc_1800067D9
0x1800067b2  mov     edx, 12Eh; void *
0x1800067b7  mov     rcx, [rbp+178h]; this
0x1800067be  lea     r8, aWil; "wil"
0x1800067c5  mov     r9d, eax; char *
0x1800067c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067cd  lea     rcx, [rsp+270h+var_238]
0x1800067d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800067d7  jmp     short loc_1800067F8
0x1800067d9  mov     rcx, [rsp+270h+var_230]
0x1800067de  test    rcx, rcx
0x1800067e1  jz      short loc_180006828
0x1800067e3  mov     [rdi], rcx
0x1800067e6  mov     eax, [rcx]
0x1800067e8  inc     eax
0x1800067ea  mov     [rcx], eax
0x1800067ec  lea     rcx, [rsp+270h+var_238]
0x1800067f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800067f6  xor     ebx, ebx
0x1800067f8  lea     rcx, [rsp+270h+var_240]
0x1800067fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006802  mov     eax, ebx
0x180006804  mov     rcx, [rbp+170h+var_10]
0x18000680b  xor     rcx, rsp; StackCookie
0x18000680e  call    __security_check_cookie
0x180006813  lea     r11, [rsp+270h+var_s0]
0x18000681b  mov     rbx, [r11+20h]
0x18000681f  mov     rdi, [r11+28h]
0x180006823  mov     rsp, r11
0x180006826  pop     rbp
0x180006827  retn
0x180006828  mov     r8, rdi
0x18000682b  lea     rdx, [rsp+270h+var_240]
0x180006830  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006835  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000683a  mov     ebx, eax
0x18000683c  test    eax, eax
0x18000683e  jns     short loc_1800067EC
0x180006840  mov     edx, 137h
0x180006845  jmp     loc_1800067B7
```
