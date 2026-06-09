# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180007514`
- end: `0x18000767a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008640`

## callees

- `0x180003390`
- `0x180006d4c`
- `0x180006d68`
- `0x180007514`
- `0x180008408`
- `0x180009384`
- `0x18000aa7c`
- `0x18000b218`
- `0x18000b77c`
- `0x18000c1e4`
- `0x18000c68c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007591`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007591`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000754c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000754c`

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
0x180007514  mov     [rsp-8+arg_10], rbx
0x180007519  mov     [rsp-8+arg_18], rdi
0x18000751e  push    rbp
0x18000751f  lea     rbp, [rsp-170h]
0x180007527  sub     rsp, 270h
0x18000752e  mov     rax, cs:__security_cookie
0x180007535  xor     rax, rsp
0x180007538  mov     [rbp+170h+var_10], rax
0x18000753f  mov     rdi, rdx
0x180007542  mov     qword ptr [rdx], 0
0x180007549  mov     rbx, rcx
0x18000754c  call    cs:__imp_GetCurrentProcessId
0x180007552  mov     [rsp+270h+var_248], rbx
0x180007557  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000755e  mov     r9d, eax
0x180007561  mov     [rsp+270h+var_250], 130h; int
0x180007569  mov     edx, 104h; unsigned __int64
0x18000756e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007573  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007578  mov     r9d, 1F0001h; dwDesiredAccess
0x18000757e  mov     [rsp+270h+var_240], 0
0x180007587  xor     r8d, r8d; dwFlags
0x18000758a  lea     rdx, [rsp+270h+Name]; lpName
0x18000758f  xor     ecx, ecx; lpMutexAttributes
0x180007591  call    cs:__imp_CreateMutexExW
0x180007597  mov     rdx, rax
0x18000759a  lea     rcx, [rsp+270h+var_240]
0x18000759f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800075a4  cmp     [rsp+270h+var_240], 0
0x1800075aa  jnz     short loc_1800075B5
0x1800075ac  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800075b1  mov     ebx, eax
0x1800075b3  jmp     short loc_180007628
0x1800075b5  lea     rdx, [rsp+270h+var_238]
0x1800075ba  lea     rcx, [rsp+270h+var_240]
0x1800075bf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800075c4  lea     rdx, [rsp+270h+var_230]; void **
0x1800075c9  mov     [rsp+270h+var_230], 0
0x1800075d2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800075d7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800075dc  mov     ebx, eax
0x1800075de  test    eax, eax
0x1800075e0  jns     short loc_180007609
0x1800075e2  mov     edx, 12Eh; void *
0x1800075e7  mov     rcx, [rbp+178h]; this
0x1800075ee  lea     r8, aWil; "wil"
0x1800075f5  mov     r9d, eax; char *
0x1800075f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075fd  lea     rcx, [rsp+270h+var_238]
0x180007602  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007607  jmp     short loc_180007628
0x180007609  mov     rcx, [rsp+270h+var_230]
0x18000760e  test    rcx, rcx
0x180007611  jz      short loc_180007658
0x180007613  mov     [rdi], rcx
0x180007616  mov     eax, [rcx]
0x180007618  inc     eax
0x18000761a  mov     [rcx], eax
0x18000761c  lea     rcx, [rsp+270h+var_238]
0x180007621  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007626  xor     ebx, ebx
0x180007628  lea     rcx, [rsp+270h+var_240]
0x18000762d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007632  mov     eax, ebx
0x180007634  mov     rcx, [rbp+170h+var_10]
0x18000763b  xor     rcx, rsp; StackCookie
0x18000763e  call    __security_check_cookie
0x180007643  lea     r11, [rsp+270h+var_s0]
0x18000764b  mov     rbx, [r11+20h]
0x18000764f  mov     rdi, [r11+28h]
0x180007653  mov     rsp, r11
0x180007656  pop     rbp
0x180007657  retn
0x180007658  mov     r8, rdi
0x18000765b  lea     rdx, [rsp+270h+var_240]
0x180007660  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007665  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000766a  mov     ebx, eax
0x18000766c  test    eax, eax
0x18000766e  jns     short loc_18000761C
0x180007670  mov     edx, 137h
0x180007675  jmp     loc_1800075E7
```
