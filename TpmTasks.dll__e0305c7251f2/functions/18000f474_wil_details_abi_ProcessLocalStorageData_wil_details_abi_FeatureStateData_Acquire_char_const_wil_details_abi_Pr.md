# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000f474`
- end: `0x18000f5da`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800144a0`

## callees

- `0x1800078b0`
- `0x18000e570`
- `0x18000e58c`
- `0x18000f474`
- `0x18001413c`
- `0x18001618c`
- `0x18001a42c`
- `0x18001be20`
- `0x18001d93c`
- `0x180023d5c`
- `0x1800249b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000f4f1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000f4f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f4ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f4ac`

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
0x18000f474  mov     [rsp-8+arg_10], rbx
0x18000f479  mov     [rsp-8+arg_18], rdi
0x18000f47e  push    rbp
0x18000f47f  lea     rbp, [rsp-170h]
0x18000f487  sub     rsp, 270h
0x18000f48e  mov     rax, cs:__security_cookie
0x18000f495  xor     rax, rsp
0x18000f498  mov     [rbp+170h+var_10], rax
0x18000f49f  mov     rdi, rdx
0x18000f4a2  mov     qword ptr [rdx], 0
0x18000f4a9  mov     rbx, rcx
0x18000f4ac  call    cs:__imp_GetCurrentProcessId
0x18000f4b2  mov     [rsp+270h+var_248], rbx
0x18000f4b7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000f4be  mov     r9d, eax
0x18000f4c1  mov     [rsp+270h+var_250], 130h; int
0x18000f4c9  mov     edx, 104h; unsigned __int64
0x18000f4ce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f4d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f4d8  mov     r9d, 1F0001h; dwDesiredAccess
0x18000f4de  mov     [rsp+270h+var_240], 0
0x18000f4e7  xor     r8d, r8d; dwFlags
0x18000f4ea  lea     rdx, [rsp+270h+Name]; lpName
0x18000f4ef  xor     ecx, ecx; lpMutexAttributes
0x18000f4f1  call    cs:__imp_CreateMutexExW
0x18000f4f7  mov     rdx, rax
0x18000f4fa  lea     rcx, [rsp+270h+var_240]
0x18000f4ff  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000f504  cmp     [rsp+270h+var_240], 0
0x18000f50a  jnz     short loc_18000F515
0x18000f50c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000f511  mov     ebx, eax
0x18000f513  jmp     short loc_18000F588
0x18000f515  lea     rdx, [rsp+270h+var_238]
0x18000f51a  lea     rcx, [rsp+270h+var_240]
0x18000f51f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000f524  lea     rdx, [rsp+270h+var_230]; void **
0x18000f529  mov     [rsp+270h+var_230], 0
0x18000f532  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f537  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000f53c  mov     ebx, eax
0x18000f53e  test    eax, eax
0x18000f540  jns     short loc_18000F569
0x18000f542  mov     edx, 12Eh; void *
0x18000f547  mov     rcx, [rbp+178h]; this
0x18000f54e  lea     r8, aWil; "wil"
0x18000f555  mov     r9d, eax; char *
0x18000f558  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f55d  lea     rcx, [rsp+270h+var_238]
0x18000f562  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f567  jmp     short loc_18000F588
0x18000f569  mov     rcx, [rsp+270h+var_230]
0x18000f56e  test    rcx, rcx
0x18000f571  jz      short loc_18000F5B8
0x18000f573  mov     [rdi], rcx
0x18000f576  mov     eax, [rcx]
0x18000f578  inc     eax
0x18000f57a  mov     [rcx], eax
0x18000f57c  lea     rcx, [rsp+270h+var_238]
0x18000f581  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f586  xor     ebx, ebx
0x18000f588  lea     rcx, [rsp+270h+var_240]
0x18000f58d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f592  mov     eax, ebx
0x18000f594  mov     rcx, [rbp+170h+var_10]
0x18000f59b  xor     rcx, rsp; StackCookie
0x18000f59e  call    __security_check_cookie
0x18000f5a3  lea     r11, [rsp+270h+var_s0]
0x18000f5ab  mov     rbx, [r11+20h]
0x18000f5af  mov     rdi, [r11+28h]
0x18000f5b3  mov     rsp, r11
0x18000f5b6  pop     rbp
0x18000f5b7  retn
0x18000f5b8  mov     r8, rdi
0x18000f5bb  lea     rdx, [rsp+270h+var_240]
0x18000f5c0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f5c5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000f5ca  mov     ebx, eax
0x18000f5cc  test    eax, eax
0x18000f5ce  jns     short loc_18000F57C
0x18000f5d0  mov     edx, 137h
0x18000f5d5  jmp     loc_18000F547
```
