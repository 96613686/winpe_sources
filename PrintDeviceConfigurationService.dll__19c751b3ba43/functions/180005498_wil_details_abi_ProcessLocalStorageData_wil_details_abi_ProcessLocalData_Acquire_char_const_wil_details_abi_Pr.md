# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005498`
- end: `0x1800055fe`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000658c`

## callees

- `0x1800020c0`
- `0x180004f08`
- `0x180004f24`
- `0x180005498`
- `0x1800062b8`
- `0x180006fa8`
- `0x1800087bc`
- `0x180008f4c`
- `0x180009498`
- `0x180009ca4`
- `0x18000a07c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005515`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005515`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800054d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800054d0`

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
0x180005498  mov     [rsp-8+arg_10], rbx
0x18000549d  mov     [rsp-8+arg_18], rdi
0x1800054a2  push    rbp
0x1800054a3  lea     rbp, [rsp-170h]
0x1800054ab  sub     rsp, 270h
0x1800054b2  mov     rax, cs:__security_cookie
0x1800054b9  xor     rax, rsp
0x1800054bc  mov     [rbp+170h+var_10], rax
0x1800054c3  mov     rdi, rdx
0x1800054c6  mov     qword ptr [rdx], 0
0x1800054cd  mov     rbx, rcx
0x1800054d0  call    cs:__imp_GetCurrentProcessId
0x1800054d6  mov     [rsp+270h+var_248], rbx
0x1800054db  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800054e2  mov     r9d, eax
0x1800054e5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800054ed  mov     edx, 104h; unsigned __int64
0x1800054f2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800054f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800054fc  mov     r9d, 1F0001h; dwDesiredAccess
0x180005502  mov     [rsp+270h+var_240], 0
0x18000550b  xor     r8d, r8d; dwFlags
0x18000550e  lea     rdx, [rsp+270h+Name]; lpName
0x180005513  xor     ecx, ecx; lpMutexAttributes
0x180005515  call    cs:__imp_CreateMutexExW
0x18000551b  mov     rdx, rax
0x18000551e  lea     rcx, [rsp+270h+var_240]
0x180005523  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005528  cmp     [rsp+270h+var_240], 0
0x18000552e  jnz     short loc_180005539
0x180005530  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005535  mov     ebx, eax
0x180005537  jmp     short loc_1800055AC
0x180005539  lea     rdx, [rsp+270h+var_238]
0x18000553e  lea     rcx, [rsp+270h+var_240]
0x180005543  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005548  lea     rdx, [rsp+270h+var_230]; void **
0x18000554d  mov     [rsp+270h+var_230], 0
0x180005556  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000555b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005560  mov     ebx, eax
0x180005562  test    eax, eax
0x180005564  jns     short loc_18000558D
0x180005566  mov     edx, 12Eh; void *
0x18000556b  mov     rcx, [rbp+178h]; this
0x180005572  lea     r8, aWil; "wil"
0x180005579  mov     r9d, eax; char *
0x18000557c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005581  lea     rcx, [rsp+270h+var_238]
0x180005586  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000558b  jmp     short loc_1800055AC
0x18000558d  mov     rcx, [rsp+270h+var_230]
0x180005592  test    rcx, rcx
0x180005595  jz      short loc_1800055DC
0x180005597  mov     [rdi], rcx
0x18000559a  mov     eax, [rcx]
0x18000559c  inc     eax
0x18000559e  mov     [rcx], eax
0x1800055a0  lea     rcx, [rsp+270h+var_238]
0x1800055a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800055aa  xor     ebx, ebx
0x1800055ac  lea     rcx, [rsp+270h+var_240]
0x1800055b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800055b6  mov     eax, ebx
0x1800055b8  mov     rcx, [rbp+170h+var_10]
0x1800055bf  xor     rcx, rsp; StackCookie
0x1800055c2  call    __security_check_cookie
0x1800055c7  lea     r11, [rsp+270h+var_s0]
0x1800055cf  mov     rbx, [r11+20h]
0x1800055d3  mov     rdi, [r11+28h]
0x1800055d7  mov     rsp, r11
0x1800055da  pop     rbp
0x1800055db  retn
0x1800055dc  mov     r8, rdi
0x1800055df  lea     rdx, [rsp+270h+var_240]
0x1800055e4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800055e9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800055ee  mov     ebx, eax
0x1800055f0  test    eax, eax
0x1800055f2  jns     short loc_1800055A0
0x1800055f4  mov     edx, 137h
0x1800055f9  jmp     loc_18000556B
```
