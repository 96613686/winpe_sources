# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006650`
- end: `0x1800067b6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007cd0`

## callees

- `0x1800030e0`
- `0x180005f64`
- `0x180005f80`
- `0x180006650`
- `0x180007808`
- `0x18000880c`
- `0x18000a2bc`
- `0x18000ac78`
- `0x18000b1fc`
- `0x18000bb94`
- `0x18000bec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800066cd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800066cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006688`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006688`

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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x180006650  mov     [rsp-8+arg_10], rbx
0x180006655  mov     [rsp-8+arg_18], rdi
0x18000665a  push    rbp
0x18000665b  lea     rbp, [rsp-170h]
0x180006663  sub     rsp, 270h
0x18000666a  mov     rax, cs:__security_cookie
0x180006671  xor     rax, rsp
0x180006674  mov     [rbp+170h+var_10], rax
0x18000667b  mov     rdi, rdx
0x18000667e  mov     qword ptr [rdx], 0
0x180006685  mov     rbx, rcx
0x180006688  call    cs:__imp_GetCurrentProcessId
0x18000668e  mov     [rsp+270h+var_248], rbx
0x180006693  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000669a  mov     r9d, eax
0x18000669d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800066a5  mov     edx, 104h; unsigned __int64
0x1800066aa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800066af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800066b4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800066ba  mov     [rsp+270h+var_240], 0
0x1800066c3  xor     r8d, r8d; dwFlags
0x1800066c6  lea     rdx, [rsp+270h+Name]; lpName
0x1800066cb  xor     ecx, ecx; lpMutexAttributes
0x1800066cd  call    cs:__imp_CreateMutexExW
0x1800066d3  mov     rdx, rax
0x1800066d6  lea     rcx, [rsp+270h+var_240]
0x1800066db  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800066e0  cmp     [rsp+270h+var_240], 0
0x1800066e6  jnz     short loc_1800066F1
0x1800066e8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800066ed  mov     ebx, eax
0x1800066ef  jmp     short loc_180006764
0x1800066f1  lea     rdx, [rsp+270h+var_238]
0x1800066f6  lea     rcx, [rsp+270h+var_240]
0x1800066fb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006700  lea     rdx, [rsp+270h+var_230]; void **
0x180006705  mov     [rsp+270h+var_230], 0
0x18000670e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006713  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180006718  mov     ebx, eax
0x18000671a  test    eax, eax
0x18000671c  jns     short loc_180006745
0x18000671e  mov     edx, 12Eh; void *
0x180006723  mov     rcx, [rbp+178h]; this
0x18000672a  lea     r8, aWil; "wil"
0x180006731  mov     r9d, eax; char *
0x180006734  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006739  lea     rcx, [rsp+270h+var_238]
0x18000673e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006743  jmp     short loc_180006764
0x180006745  mov     rcx, [rsp+270h+var_230]
0x18000674a  test    rcx, rcx
0x18000674d  jz      short loc_180006794
0x18000674f  mov     [rdi], rcx
0x180006752  mov     eax, [rcx]
0x180006754  inc     eax
0x180006756  mov     [rcx], eax
0x180006758  lea     rcx, [rsp+270h+var_238]
0x18000675d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006762  xor     ebx, ebx
0x180006764  lea     rcx, [rsp+270h+var_240]
0x180006769  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000676e  mov     eax, ebx
0x180006770  mov     rcx, [rbp+170h+var_10]
0x180006777  xor     rcx, rsp; StackCookie
0x18000677a  call    __security_check_cookie
0x18000677f  lea     r11, [rsp+270h+var_s0]
0x180006787  mov     rbx, [r11+20h]
0x18000678b  mov     rdi, [r11+28h]
0x18000678f  mov     rsp, r11
0x180006792  pop     rbp
0x180006793  retn
0x180006794  mov     r8, rdi
0x180006797  lea     rdx, [rsp+270h+var_240]
0x18000679c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800067a1  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800067a6  mov     ebx, eax
0x1800067a8  test    eax, eax
0x1800067aa  jns     short loc_180006758
0x1800067ac  mov     edx, 137h
0x1800067b1  jmp     loc_180006723
```
