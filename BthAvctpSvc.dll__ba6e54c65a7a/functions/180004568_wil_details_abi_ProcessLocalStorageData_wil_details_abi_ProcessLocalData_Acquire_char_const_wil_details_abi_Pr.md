# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004568`
- end: `0x1800046ce`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005634`

## callees

- `0x180001dd0`
- `0x1800040d8`
- `0x1800040f4`
- `0x180004568`
- `0x180005308`
- `0x18000604c`
- `0x18000751c`
- `0x180007ca8`
- `0x180008128`
- `0x1800089d4`
- `0x180008d08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800045e5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800045e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800045a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800045a0`

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
0x180004568  mov     [rsp-8+arg_10], rbx
0x18000456d  mov     [rsp-8+arg_18], rdi
0x180004572  push    rbp
0x180004573  lea     rbp, [rsp-170h]
0x18000457b  sub     rsp, 270h
0x180004582  mov     rax, cs:__security_cookie
0x180004589  xor     rax, rsp
0x18000458c  mov     [rbp+170h+var_10], rax
0x180004593  mov     rdi, rdx
0x180004596  mov     qword ptr [rdx], 0
0x18000459d  mov     rbx, rcx
0x1800045a0  call    cs:__imp_GetCurrentProcessId
0x1800045a6  mov     [rsp+270h+var_248], rbx
0x1800045ab  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800045b2  mov     r9d, eax
0x1800045b5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800045bd  mov     edx, 104h; unsigned __int64
0x1800045c2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800045c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800045cc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800045d2  mov     [rsp+270h+var_240], 0
0x1800045db  xor     r8d, r8d; dwFlags
0x1800045de  lea     rdx, [rsp+270h+Name]; lpName
0x1800045e3  xor     ecx, ecx; lpMutexAttributes
0x1800045e5  call    cs:__imp_CreateMutexExW
0x1800045eb  mov     rdx, rax
0x1800045ee  lea     rcx, [rsp+270h+var_240]
0x1800045f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800045f8  cmp     [rsp+270h+var_240], 0
0x1800045fe  jnz     short loc_180004609
0x180004600  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004605  mov     ebx, eax
0x180004607  jmp     short loc_18000467C
0x180004609  lea     rdx, [rsp+270h+var_238]
0x18000460e  lea     rcx, [rsp+270h+var_240]
0x180004613  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004618  lea     rdx, [rsp+270h+var_230]; void **
0x18000461d  mov     [rsp+270h+var_230], 0
0x180004626  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000462b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180004630  mov     ebx, eax
0x180004632  test    eax, eax
0x180004634  jns     short loc_18000465D
0x180004636  mov     edx, 12Eh; void *
0x18000463b  mov     rcx, [rbp+178h]; this
0x180004642  lea     r8, aWil; "wil"
0x180004649  mov     r9d, eax; char *
0x18000464c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004651  lea     rcx, [rsp+270h+var_238]
0x180004656  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000465b  jmp     short loc_18000467C
0x18000465d  mov     rcx, [rsp+270h+var_230]
0x180004662  test    rcx, rcx
0x180004665  jz      short loc_1800046AC
0x180004667  mov     [rdi], rcx
0x18000466a  mov     eax, [rcx]
0x18000466c  inc     eax
0x18000466e  mov     [rcx], eax
0x180004670  lea     rcx, [rsp+270h+var_238]
0x180004675  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000467a  xor     ebx, ebx
0x18000467c  lea     rcx, [rsp+270h+var_240]
0x180004681  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004686  mov     eax, ebx
0x180004688  mov     rcx, [rbp+170h+var_10]
0x18000468f  xor     rcx, rsp; StackCookie
0x180004692  call    __security_check_cookie
0x180004697  lea     r11, [rsp+270h+var_s0]
0x18000469f  mov     rbx, [r11+20h]
0x1800046a3  mov     rdi, [r11+28h]
0x1800046a7  mov     rsp, r11
0x1800046aa  pop     rbp
0x1800046ab  retn
0x1800046ac  mov     r8, rdi
0x1800046af  lea     rdx, [rsp+270h+var_240]
0x1800046b4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800046b9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800046be  mov     ebx, eax
0x1800046c0  test    eax, eax
0x1800046c2  jns     short loc_180004670
0x1800046c4  mov     edx, 137h
0x1800046c9  jmp     loc_18000463B
```
