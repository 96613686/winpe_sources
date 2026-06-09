# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180009064`
- end: `0x1800091c3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000ac3c`

## callees

- `0x180001720`
- `0x180005b78`
- `0x1800087c4`
- `0x1800087e0`
- `0x180009064`
- `0x18000b514`
- `0x18000ceb8`
- `0x18000f0cc`
- `0x180010278`
- `0x180010f14`
- `0x180011280`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800090e1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800090e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000909c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000909c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v9; // r8d
  __int64 v10; // rdx
  _DWORD *v11; // rcx
  wil::details *v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v13 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v13,
    Mutex);
  if ( v13 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v13,
      &v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
      goto LABEL_9;
    }
    v11 = v15;
    if ( v15 )
    {
      *a2 = v15;
      ++*v11;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v10 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v13,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180009064  mov     [rsp-8+arg_10], rbx
0x180009069  mov     [rsp-8+arg_18], rdi
0x18000906e  push    rbp
0x18000906f  lea     rbp, [rsp-170h]
0x180009077  sub     rsp, 270h
0x18000907e  mov     rax, cs:__security_cookie
0x180009085  xor     rax, rsp
0x180009088  mov     [rbp+170h+var_10], rax
0x18000908f  mov     rdi, rdx
0x180009092  mov     qword ptr [rdx], 0
0x180009099  mov     rbx, rcx
0x18000909c  call    cs:__imp_GetCurrentProcessId
0x1800090a2  mov     [rsp+270h+var_248], rbx
0x1800090a7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800090ae  mov     r9d, eax
0x1800090b1  mov     [rsp+270h+var_250], 130h; int
0x1800090b9  mov     edx, 104h; unsigned __int64
0x1800090be  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800090c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800090c8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800090ce  mov     [rsp+270h+var_240], 0
0x1800090d7  xor     r8d, r8d; dwFlags
0x1800090da  lea     rdx, [rsp+270h+Name]; lpName
0x1800090df  xor     ecx, ecx; lpMutexAttributes
0x1800090e1  call    cs:__imp_CreateMutexExW
0x1800090e7  mov     rdx, rax
0x1800090ea  lea     rcx, [rsp+270h+var_240]
0x1800090ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800090f4  cmp     [rsp+270h+var_240], 0
0x1800090fa  jnz     short loc_180009105
0x1800090fc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009101  mov     ebx, eax
0x180009103  jmp     short loc_180009171
0x180009105  lea     rdx, [rsp+270h+var_238]
0x18000910a  lea     rcx, [rsp+270h+var_240]
0x18000910f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180009114  lea     rdx, [rsp+270h+var_230]; void **
0x180009119  mov     [rsp+270h+var_230], 0
0x180009122  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009127  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000912c  mov     ebx, eax
0x18000912e  test    eax, eax
0x180009130  jns     short loc_180009152
0x180009132  mov     edx, 12Eh; void *
0x180009137  mov     rcx, [rbp+178h]; this
0x18000913e  mov     r9d, eax; char *
0x180009141  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009146  lea     rcx, [rsp+270h+var_238]
0x18000914b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009150  jmp     short loc_180009171
0x180009152  mov     rcx, [rsp+270h+var_230]
0x180009157  test    rcx, rcx
0x18000915a  jz      short loc_1800091A1
0x18000915c  mov     [rdi], rcx
0x18000915f  mov     eax, [rcx]
0x180009161  inc     eax
0x180009163  mov     [rcx], eax
0x180009165  lea     rcx, [rsp+270h+var_238]
0x18000916a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000916f  xor     ebx, ebx
0x180009171  lea     rcx, [rsp+270h+var_240]
0x180009176  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000917b  mov     eax, ebx
0x18000917d  mov     rcx, [rbp+170h+var_10]
0x180009184  xor     rcx, rsp; StackCookie
0x180009187  call    __security_check_cookie
0x18000918c  lea     r11, [rsp+270h+var_s0]
0x180009194  mov     rbx, [r11+20h]
0x180009198  mov     rdi, [r11+28h]
0x18000919c  mov     rsp, r11
0x18000919f  pop     rbp
0x1800091a0  retn
0x1800091a1  mov     r8, rdi
0x1800091a4  lea     rdx, [rsp+270h+var_240]
0x1800091a9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800091ae  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800091b3  mov     ebx, eax
0x1800091b5  test    eax, eax
0x1800091b7  jns     short loc_180009165
0x1800091b9  mov     edx, 137h
0x1800091be  jmp     loc_180009137
```
