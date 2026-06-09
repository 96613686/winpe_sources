# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180007418`
- end: `0x18000757e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000a0c0`

## callees

- `0x180002ce0`
- `0x180007034`
- `0x180007050`
- `0x180007418`
- `0x180009c78`
- `0x18000aed0`
- `0x18000c164`
- `0x18000d1c0`
- `0x18000d5b8`
- `0x18000deec`
- `0x18000e01c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007495`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007495`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007450`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007450`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x180007418  mov     [rsp-8+arg_10], rbx
0x18000741d  mov     [rsp-8+arg_18], rdi
0x180007422  push    rbp
0x180007423  lea     rbp, [rsp-170h]
0x18000742b  sub     rsp, 270h
0x180007432  mov     rax, cs:__security_cookie
0x180007439  xor     rax, rsp
0x18000743c  mov     [rbp+170h+var_10], rax
0x180007443  mov     rdi, rdx
0x180007446  mov     qword ptr [rdx], 0
0x18000744d  mov     rbx, rcx
0x180007450  call    cs:__imp_GetCurrentProcessId
0x180007456  mov     [rsp+270h+var_248], rbx
0x18000745b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007462  mov     r9d, eax
0x180007465  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000746d  mov     edx, 104h; unsigned __int64
0x180007472  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007477  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000747c  mov     r9d, 1F0001h; dwDesiredAccess
0x180007482  mov     [rsp+270h+var_240], 0
0x18000748b  xor     r8d, r8d; dwFlags
0x18000748e  lea     rdx, [rsp+270h+Name]; lpName
0x180007493  xor     ecx, ecx; lpMutexAttributes
0x180007495  call    cs:__imp_CreateMutexExW
0x18000749b  mov     rdx, rax
0x18000749e  lea     rcx, [rsp+270h+var_240]
0x1800074a3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800074a8  cmp     [rsp+270h+var_240], 0
0x1800074ae  jnz     short loc_1800074B9
0x1800074b0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800074b5  mov     ebx, eax
0x1800074b7  jmp     short loc_18000752C
0x1800074b9  lea     rdx, [rsp+270h+var_238]
0x1800074be  lea     rcx, [rsp+270h+var_240]
0x1800074c3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800074c8  lea     rdx, [rsp+270h+var_230]; void **
0x1800074cd  mov     [rsp+270h+var_230], 0
0x1800074d6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800074db  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800074e0  mov     ebx, eax
0x1800074e2  test    eax, eax
0x1800074e4  jns     short loc_18000750D
0x1800074e6  mov     edx, 12Eh; void *
0x1800074eb  mov     rcx, [rbp+178h]; this
0x1800074f2  lea     r8, aWil; "wil"
0x1800074f9  mov     r9d, eax; char *
0x1800074fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007501  lea     rcx, [rsp+270h+var_238]
0x180007506  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000750b  jmp     short loc_18000752C
0x18000750d  mov     rcx, [rsp+270h+var_230]
0x180007512  test    rcx, rcx
0x180007515  jz      short loc_18000755C
0x180007517  mov     [rdi], rcx
0x18000751a  mov     eax, [rcx]
0x18000751c  inc     eax
0x18000751e  mov     [rcx], eax
0x180007520  lea     rcx, [rsp+270h+var_238]
0x180007525  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000752a  xor     ebx, ebx
0x18000752c  lea     rcx, [rsp+270h+var_240]
0x180007531  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007536  mov     eax, ebx
0x180007538  mov     rcx, [rbp+170h+var_10]
0x18000753f  xor     rcx, rsp; StackCookie
0x180007542  call    __security_check_cookie
0x180007547  lea     r11, [rsp+270h+var_s0]
0x18000754f  mov     rbx, [r11+20h]
0x180007553  mov     rdi, [r11+28h]
0x180007557  mov     rsp, r11
0x18000755a  pop     rbp
0x18000755b  retn
0x18000755c  mov     r8, rdi
0x18000755f  lea     rdx, [rsp+270h+var_240]
0x180007564  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007569  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000756e  mov     ebx, eax
0x180007570  test    eax, eax
0x180007572  jns     short loc_180007520
0x180007574  mov     edx, 137h
0x180007579  jmp     loc_1800074EB
```
