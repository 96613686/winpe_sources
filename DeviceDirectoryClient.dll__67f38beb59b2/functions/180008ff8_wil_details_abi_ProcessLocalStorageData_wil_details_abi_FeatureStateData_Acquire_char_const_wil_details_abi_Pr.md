# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180008ff8`
- end: `0x18000915e`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000a064`

## callees

- `0x1800024c0`
- `0x180008a48`
- `0x180008a64`
- `0x180008ff8`
- `0x180009ea8`
- `0x18000af70`
- `0x18000d08c`
- `0x18000d79c`
- `0x18000dc58`
- `0x18000e524`
- `0x18000e85c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009075`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009075`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009030`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009030`

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
0x180008ff8  mov     [rsp-8+arg_10], rbx
0x180008ffd  mov     [rsp-8+arg_18], rdi
0x180009002  push    rbp
0x180009003  lea     rbp, [rsp-170h]
0x18000900b  sub     rsp, 270h
0x180009012  mov     rax, cs:__security_cookie
0x180009019  xor     rax, rsp
0x18000901c  mov     [rbp+170h+var_10], rax
0x180009023  mov     rdi, rdx
0x180009026  mov     qword ptr [rdx], 0
0x18000902d  mov     rbx, rcx
0x180009030  call    cs:__imp_GetCurrentProcessId
0x180009036  mov     [rsp+270h+var_248], rbx
0x18000903b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009042  mov     r9d, eax
0x180009045  mov     [rsp+270h+var_250], 130h; int
0x18000904d  mov     edx, 104h; unsigned __int64
0x180009052  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009057  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000905c  mov     r9d, 1F0001h; dwDesiredAccess
0x180009062  mov     [rsp+270h+var_240], 0
0x18000906b  xor     r8d, r8d; dwFlags
0x18000906e  lea     rdx, [rsp+270h+Name]; lpName
0x180009073  xor     ecx, ecx; lpMutexAttributes
0x180009075  call    cs:__imp_CreateMutexExW
0x18000907b  mov     rdx, rax
0x18000907e  lea     rcx, [rsp+270h+var_240]
0x180009083  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009088  cmp     [rsp+270h+var_240], 0
0x18000908e  jnz     short loc_180009099
0x180009090  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009095  mov     ebx, eax
0x180009097  jmp     short loc_18000910C
0x180009099  lea     rdx, [rsp+270h+var_238]
0x18000909e  lea     rcx, [rsp+270h+var_240]
0x1800090a3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800090a8  lea     rdx, [rsp+270h+var_230]; void **
0x1800090ad  mov     [rsp+270h+var_230], 0
0x1800090b6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800090bb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800090c0  mov     ebx, eax
0x1800090c2  test    eax, eax
0x1800090c4  jns     short loc_1800090ED
0x1800090c6  mov     edx, 12Eh; void *
0x1800090cb  mov     rcx, [rbp+178h]; this
0x1800090d2  lea     r8, aWil; "wil"
0x1800090d9  mov     r9d, eax; char *
0x1800090dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090e1  lea     rcx, [rsp+270h+var_238]
0x1800090e6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800090eb  jmp     short loc_18000910C
0x1800090ed  mov     rcx, [rsp+270h+var_230]
0x1800090f2  test    rcx, rcx
0x1800090f5  jz      short loc_18000913C
0x1800090f7  mov     [rdi], rcx
0x1800090fa  mov     eax, [rcx]
0x1800090fc  inc     eax
0x1800090fe  mov     [rcx], eax
0x180009100  lea     rcx, [rsp+270h+var_238]
0x180009105  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000910a  xor     ebx, ebx
0x18000910c  lea     rcx, [rsp+270h+var_240]
0x180009111  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009116  mov     eax, ebx
0x180009118  mov     rcx, [rbp+170h+var_10]
0x18000911f  xor     rcx, rsp; StackCookie
0x180009122  call    __security_check_cookie
0x180009127  lea     r11, [rsp+270h+var_s0]
0x18000912f  mov     rbx, [r11+20h]
0x180009133  mov     rdi, [r11+28h]
0x180009137  mov     rsp, r11
0x18000913a  pop     rbp
0x18000913b  retn
0x18000913c  mov     r8, rdi
0x18000913f  lea     rdx, [rsp+270h+var_240]
0x180009144  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009149  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000914e  mov     ebx, eax
0x180009150  test    eax, eax
0x180009152  jns     short loc_180009100
0x180009154  mov     edx, 137h
0x180009159  jmp     loc_1800090CB
```
