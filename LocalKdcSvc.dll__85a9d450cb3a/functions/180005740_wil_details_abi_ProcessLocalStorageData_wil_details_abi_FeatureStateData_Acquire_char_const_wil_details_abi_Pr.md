# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180005740`
- end: `0x18000589f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006584`

## callees

- `0x180002ad0`
- `0x180005124`
- `0x180005140`
- `0x180005740`
- `0x1800063f8`
- `0x180007244`
- `0x1800082ec`
- `0x180008a30`
- `0x180008ee8`
- `0x180009794`
- `0x180009ac8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800057bd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800057bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005778`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005778`

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
  HANDLE v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
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
      &v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
0x180005740  mov     [rsp-8+arg_10], rbx
0x180005745  mov     [rsp-8+arg_18], rdi
0x18000574a  push    rbp
0x18000574b  lea     rbp, [rsp-170h]
0x180005753  sub     rsp, 270h
0x18000575a  mov     rax, cs:__security_cookie
0x180005761  xor     rax, rsp
0x180005764  mov     [rbp+170h+var_10], rax
0x18000576b  mov     rdi, rdx
0x18000576e  mov     qword ptr [rdx], 0
0x180005775  mov     rbx, rcx
0x180005778  call    cs:__imp_GetCurrentProcessId
0x18000577e  mov     [rsp+270h+var_248], rbx
0x180005783  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000578a  mov     r9d, eax
0x18000578d  mov     [rsp+270h+var_250], 130h; int
0x180005795  mov     edx, 104h; unsigned __int64
0x18000579a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000579f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800057a4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800057aa  mov     [rsp+270h+var_240], 0
0x1800057b3  xor     r8d, r8d; dwFlags
0x1800057b6  lea     rdx, [rsp+270h+Name]; lpName
0x1800057bb  xor     ecx, ecx; lpMutexAttributes
0x1800057bd  call    cs:__imp_CreateMutexExW
0x1800057c3  mov     rdx, rax
0x1800057c6  lea     rcx, [rsp+270h+var_240]
0x1800057cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800057d0  cmp     [rsp+270h+var_240], 0
0x1800057d6  jnz     short loc_1800057E1
0x1800057d8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800057dd  mov     ebx, eax
0x1800057df  jmp     short loc_18000584D
0x1800057e1  lea     rdx, [rsp+270h+var_238]
0x1800057e6  lea     rcx, [rsp+270h+var_240]
0x1800057eb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800057f0  lea     rdx, [rsp+270h+var_230]; void **
0x1800057f5  mov     [rsp+270h+var_230], 0
0x1800057fe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005803  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005808  mov     ebx, eax
0x18000580a  test    eax, eax
0x18000580c  jns     short loc_18000582E
0x18000580e  mov     edx, 12Eh; void *
0x180005813  mov     rcx, [rbp+178h]; this
0x18000581a  mov     r9d, eax; char *
0x18000581d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005822  lea     rcx, [rsp+270h+var_238]
0x180005827  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000582c  jmp     short loc_18000584D
0x18000582e  mov     rcx, [rsp+270h+var_230]
0x180005833  test    rcx, rcx
0x180005836  jz      short loc_18000587D
0x180005838  mov     [rdi], rcx
0x18000583b  mov     eax, [rcx]
0x18000583d  inc     eax
0x18000583f  mov     [rcx], eax
0x180005841  lea     rcx, [rsp+270h+var_238]
0x180005846  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000584b  xor     ebx, ebx
0x18000584d  lea     rcx, [rsp+270h+var_240]
0x180005852  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005857  mov     eax, ebx
0x180005859  mov     rcx, [rbp+170h+var_10]
0x180005860  xor     rcx, rsp; StackCookie
0x180005863  call    __security_check_cookie
0x180005868  lea     r11, [rsp+270h+var_s0]
0x180005870  mov     rbx, [r11+20h]
0x180005874  mov     rdi, [r11+28h]
0x180005878  mov     rsp, r11
0x18000587b  pop     rbp
0x18000587c  retn
0x18000587d  mov     r8, rdi
0x180005880  lea     rdx, [rsp+270h+var_240]
0x180005885  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000588a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000588f  mov     ebx, eax
0x180005891  test    eax, eax
0x180005893  jns     short loc_180005841
0x180005895  mov     edx, 137h
0x18000589a  jmp     loc_180005813
```
