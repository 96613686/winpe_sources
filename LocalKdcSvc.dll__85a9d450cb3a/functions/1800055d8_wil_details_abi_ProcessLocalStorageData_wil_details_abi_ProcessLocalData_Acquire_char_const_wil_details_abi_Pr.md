# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800055d8`
- end: `0x180005737`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800066f4`

## callees

- `0x180002ad0`
- `0x180005124`
- `0x180005140`
- `0x1800055d8`
- `0x1800063f8`
- `0x180007120`
- `0x1800082ec`
- `0x180008a30`
- `0x180008ee8`
- `0x180009794`
- `0x180009ac8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005655`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005655`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005610`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005610`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x1800055d8  mov     [rsp-8+arg_10], rbx
0x1800055dd  mov     [rsp-8+arg_18], rdi
0x1800055e2  push    rbp
0x1800055e3  lea     rbp, [rsp-170h]
0x1800055eb  sub     rsp, 270h
0x1800055f2  mov     rax, cs:__security_cookie
0x1800055f9  xor     rax, rsp
0x1800055fc  mov     [rbp+170h+var_10], rax
0x180005603  mov     rdi, rdx
0x180005606  mov     qword ptr [rdx], 0
0x18000560d  mov     rbx, rcx
0x180005610  call    cs:__imp_GetCurrentProcessId
0x180005616  mov     [rsp+270h+var_248], rbx
0x18000561b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005622  mov     r9d, eax
0x180005625  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000562d  mov     edx, 104h; unsigned __int64
0x180005632  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005637  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000563c  mov     r9d, 1F0001h; dwDesiredAccess
0x180005642  mov     [rsp+270h+var_240], 0
0x18000564b  xor     r8d, r8d; dwFlags
0x18000564e  lea     rdx, [rsp+270h+Name]; lpName
0x180005653  xor     ecx, ecx; lpMutexAttributes
0x180005655  call    cs:__imp_CreateMutexExW
0x18000565b  mov     rdx, rax
0x18000565e  lea     rcx, [rsp+270h+var_240]
0x180005663  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005668  cmp     [rsp+270h+var_240], 0
0x18000566e  jnz     short loc_180005679
0x180005670  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005675  mov     ebx, eax
0x180005677  jmp     short loc_1800056E5
0x180005679  lea     rdx, [rsp+270h+var_238]
0x18000567e  lea     rcx, [rsp+270h+var_240]
0x180005683  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005688  lea     rdx, [rsp+270h+var_230]; void **
0x18000568d  mov     [rsp+270h+var_230], 0
0x180005696  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000569b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800056a0  mov     ebx, eax
0x1800056a2  test    eax, eax
0x1800056a4  jns     short loc_1800056C6
0x1800056a6  mov     edx, 12Eh; void *
0x1800056ab  mov     rcx, [rbp+178h]; this
0x1800056b2  mov     r9d, eax; char *
0x1800056b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800056ba  lea     rcx, [rsp+270h+var_238]
0x1800056bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800056c4  jmp     short loc_1800056E5
0x1800056c6  mov     rcx, [rsp+270h+var_230]
0x1800056cb  test    rcx, rcx
0x1800056ce  jz      short loc_180005715
0x1800056d0  mov     [rdi], rcx
0x1800056d3  mov     eax, [rcx]
0x1800056d5  inc     eax
0x1800056d7  mov     [rcx], eax
0x1800056d9  lea     rcx, [rsp+270h+var_238]
0x1800056de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800056e3  xor     ebx, ebx
0x1800056e5  lea     rcx, [rsp+270h+var_240]
0x1800056ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800056ef  mov     eax, ebx
0x1800056f1  mov     rcx, [rbp+170h+var_10]
0x1800056f8  xor     rcx, rsp; StackCookie
0x1800056fb  call    __security_check_cookie
0x180005700  lea     r11, [rsp+270h+var_s0]
0x180005708  mov     rbx, [r11+20h]
0x18000570c  mov     rdi, [r11+28h]
0x180005710  mov     rsp, r11
0x180005713  pop     rbp
0x180005714  retn
0x180005715  mov     r8, rdi
0x180005718  lea     rdx, [rsp+270h+var_240]
0x18000571d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005722  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005727  mov     ebx, eax
0x180005729  test    eax, eax
0x18000572b  jns     short loc_1800056D9
0x18000572d  mov     edx, 137h
0x180005732  jmp     loc_1800056AB
```
