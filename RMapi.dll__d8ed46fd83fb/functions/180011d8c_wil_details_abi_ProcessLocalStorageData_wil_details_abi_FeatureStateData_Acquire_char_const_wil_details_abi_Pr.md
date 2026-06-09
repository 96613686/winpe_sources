# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180011d8c`
- end: `0x180011efb`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180013550`

## callees

- `0x180005050`
- `0x18000aac0`
- `0x18000b798`
- `0x18000bc3c`
- `0x18000d2a0`
- `0x18000f930`
- `0x180010468`
- `0x1800106a4`
- `0x180010754`
- `0x180011d8c`
- `0x180013abc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011dc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011dc4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180011e09`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180011e09`

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
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
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
    v12 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      &v12);
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
0x180011d8c  mov     [rsp-8+arg_10], rbx
0x180011d91  mov     [rsp-8+arg_18], rdi
0x180011d96  push    rbp
0x180011d97  lea     rbp, [rsp-170h]
0x180011d9f  sub     rsp, 270h
0x180011da6  mov     rax, cs:__security_cookie
0x180011dad  xor     rax, rsp
0x180011db0  mov     [rbp+170h+var_10], rax
0x180011db7  mov     rdi, rdx
0x180011dba  mov     qword ptr [rdx], 0
0x180011dc1  mov     rbx, rcx
0x180011dc4  call    cs:__imp_GetCurrentProcessId
0x180011dca  mov     [rsp+270h+var_248], rbx
0x180011dcf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180011dd6  mov     r9d, eax
0x180011dd9  mov     [rsp+270h+var_250], 130h; int
0x180011de1  mov     edx, 104h; unsigned __int64
0x180011de6  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180011deb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180011df0  mov     r9d, 1F0001h; dwDesiredAccess
0x180011df6  mov     [rsp+270h+var_240], 0
0x180011dff  xor     r8d, r8d; dwFlags
0x180011e02  lea     rdx, [rsp+270h+Name]; lpName
0x180011e07  xor     ecx, ecx; lpMutexAttributes
0x180011e09  call    cs:__imp_CreateMutexExW
0x180011e0f  mov     rdx, rax
0x180011e12  lea     rcx, [rsp+270h+var_240]
0x180011e17  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180011e1c  cmp     [rsp+270h+var_240], 0
0x180011e22  jnz     short loc_180011E2D
0x180011e24  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180011e29  mov     ebx, eax
0x180011e2b  jmp     short loc_180011EA9
0x180011e2d  lea     rdx, [rsp+270h+var_238]
0x180011e32  mov     [rsp+270h+var_238], 0
0x180011e3b  lea     rcx, [rsp+270h+var_240]
0x180011e40  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180011e45  lea     rdx, [rsp+270h+var_230]; void **
0x180011e4a  mov     [rsp+270h+var_230], 0
0x180011e53  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180011e58  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180011e5d  mov     ebx, eax
0x180011e5f  test    eax, eax
0x180011e61  jns     short loc_180011E8A
0x180011e63  mov     edx, 12Eh; void *
0x180011e68  mov     rcx, [rbp+178h]; this
0x180011e6f  lea     r8, aWil; "wil"
0x180011e76  mov     r9d, eax; char *
0x180011e79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011e7e  lea     rcx, [rsp+270h+var_238]
0x180011e83  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011e88  jmp     short loc_180011EA9
0x180011e8a  mov     rcx, [rsp+270h+var_230]
0x180011e8f  test    rcx, rcx
0x180011e92  jz      short loc_180011ED9
0x180011e94  mov     [rdi], rcx
0x180011e97  mov     eax, [rcx]
0x180011e99  inc     eax
0x180011e9b  mov     [rcx], eax
0x180011e9d  lea     rcx, [rsp+270h+var_238]
0x180011ea2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011ea7  xor     ebx, ebx
0x180011ea9  lea     rcx, [rsp+270h+var_240]
0x180011eae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011eb3  mov     eax, ebx
0x180011eb5  mov     rcx, [rbp+170h+var_10]
0x180011ebc  xor     rcx, rsp; StackCookie
0x180011ebf  call    __security_check_cookie
0x180011ec4  lea     r11, [rsp+270h+var_s0]
0x180011ecc  mov     rbx, [r11+20h]
0x180011ed0  mov     rdi, [r11+28h]
0x180011ed4  mov     rsp, r11
0x180011ed7  pop     rbp
0x180011ed8  retn
0x180011ed9  mov     r8, rdi
0x180011edc  lea     rdx, [rsp+270h+var_240]
0x180011ee1  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180011ee6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180011eeb  mov     ebx, eax
0x180011eed  test    eax, eax
0x180011eef  jns     short loc_180011E9D
0x180011ef1  mov     edx, 137h
0x180011ef6  jmp     loc_180011E68
```
