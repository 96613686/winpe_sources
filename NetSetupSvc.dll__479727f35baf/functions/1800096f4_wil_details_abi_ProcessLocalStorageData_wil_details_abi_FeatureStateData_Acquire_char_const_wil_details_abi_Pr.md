# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800096f4`
- end: `0x18000985a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000a648`

## callees

- `0x1800027c0`
- `0x1800041ec`
- `0x180004208`
- `0x180004bc8`
- `0x180005c34`
- `0x180006214`
- `0x1800063cc`
- `0x18000685c`
- `0x180006964`
- `0x1800096f4`
- `0x18000accc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009771`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009771`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000972c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000972c`

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
0x1800096f4  mov     [rsp-8+arg_10], rbx
0x1800096f9  mov     [rsp-8+arg_18], rdi
0x1800096fe  push    rbp
0x1800096ff  lea     rbp, [rsp-170h]
0x180009707  sub     rsp, 270h
0x18000970e  mov     rax, cs:__security_cookie
0x180009715  xor     rax, rsp
0x180009718  mov     [rbp+170h+var_10], rax
0x18000971f  mov     rdi, rdx
0x180009722  mov     qword ptr [rdx], 0
0x180009729  mov     rbx, rcx
0x18000972c  call    cs:__imp_GetCurrentProcessId
0x180009732  mov     [rsp+270h+var_248], rbx
0x180009737  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000973e  mov     r9d, eax
0x180009741  mov     [rsp+270h+var_250], 130h; int
0x180009749  mov     edx, 104h; unsigned __int64
0x18000974e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180009753  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180009758  mov     r9d, 1F0001h; dwDesiredAccess
0x18000975e  mov     [rsp+270h+var_240], 0
0x180009767  xor     r8d, r8d; dwFlags
0x18000976a  lea     rdx, [rsp+270h+Name]; lpName
0x18000976f  xor     ecx, ecx; lpMutexAttributes
0x180009771  call    cs:__imp_CreateMutexExW
0x180009777  mov     rdx, rax
0x18000977a  lea     rcx, [rsp+270h+var_240]
0x18000977f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009784  cmp     [rsp+270h+var_240], 0
0x18000978a  jnz     short loc_180009795
0x18000978c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009791  mov     ebx, eax
0x180009793  jmp     short loc_180009808
0x180009795  lea     rdx, [rsp+270h+var_238]
0x18000979a  lea     rcx, [rsp+270h+var_240]
0x18000979f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800097a4  lea     rdx, [rsp+270h+var_230]; void **
0x1800097a9  mov     [rsp+270h+var_230], 0
0x1800097b2  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800097b7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1800097bc  mov     ebx, eax
0x1800097be  test    eax, eax
0x1800097c0  jns     short loc_1800097E9
0x1800097c2  mov     edx, 12Eh; void *
0x1800097c7  mov     rcx, [rbp+178h]; this
0x1800097ce  lea     r8, aWil; "wil"
0x1800097d5  mov     r9d, eax; char *
0x1800097d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800097dd  lea     rcx, [rsp+270h+var_238]
0x1800097e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800097e7  jmp     short loc_180009808
0x1800097e9  mov     rcx, [rsp+270h+var_230]
0x1800097ee  test    rcx, rcx
0x1800097f1  jz      short loc_180009838
0x1800097f3  mov     [rdi], rcx
0x1800097f6  mov     eax, [rcx]
0x1800097f8  inc     eax
0x1800097fa  mov     [rcx], eax
0x1800097fc  lea     rcx, [rsp+270h+var_238]
0x180009801  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009806  xor     ebx, ebx
0x180009808  lea     rcx, [rsp+270h+var_240]
0x18000980d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009812  mov     eax, ebx
0x180009814  mov     rcx, [rbp+170h+var_10]
0x18000981b  xor     rcx, rsp; StackCookie
0x18000981e  call    __security_check_cookie
0x180009823  lea     r11, [rsp+270h+var_s0]
0x18000982b  mov     rbx, [r11+20h]
0x18000982f  mov     rdi, [r11+28h]
0x180009833  mov     rsp, r11
0x180009836  pop     rbp
0x180009837  retn
0x180009838  mov     r8, rdi
0x18000983b  lea     rdx, [rsp+270h+var_240]
0x180009840  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180009845  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000984a  mov     ebx, eax
0x18000984c  test    eax, eax
0x18000984e  jns     short loc_1800097FC
0x180009850  mov     edx, 137h
0x180009855  jmp     loc_1800097C7
```
