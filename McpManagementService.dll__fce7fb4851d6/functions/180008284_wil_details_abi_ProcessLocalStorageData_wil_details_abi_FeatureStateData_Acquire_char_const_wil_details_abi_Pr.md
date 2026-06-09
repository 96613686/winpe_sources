# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180008284`
- end: `0x1800083ea`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009880`

## callees

- `0x180003a60`
- `0x180007520`
- `0x18000753c`
- `0x180008284`
- `0x180009638`
- `0x18000aa78`
- `0x18000c4cc`
- `0x18000cd3c`
- `0x18000d348`
- `0x18000e284`
- `0x18000e838`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008301`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008301`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800082bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800082bc`

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
0x180008284  mov     [rsp-8+arg_10], rbx
0x180008289  mov     [rsp-8+arg_18], rdi
0x18000828e  push    rbp
0x18000828f  lea     rbp, [rsp-170h]
0x180008297  sub     rsp, 270h
0x18000829e  mov     rax, cs:__security_cookie
0x1800082a5  xor     rax, rsp
0x1800082a8  mov     [rbp+170h+var_10], rax
0x1800082af  mov     rdi, rdx
0x1800082b2  mov     qword ptr [rdx], 0
0x1800082b9  mov     rbx, rcx
0x1800082bc  call    cs:__imp_GetCurrentProcessId
0x1800082c2  mov     [rsp+270h+var_248], rbx
0x1800082c7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800082ce  mov     r9d, eax
0x1800082d1  mov     [rsp+270h+var_250], 130h; int
0x1800082d9  mov     edx, 104h; unsigned __int64
0x1800082de  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800082e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800082e8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800082ee  mov     [rsp+270h+var_240], 0
0x1800082f7  xor     r8d, r8d; dwFlags
0x1800082fa  lea     rdx, [rsp+270h+Name]; lpName
0x1800082ff  xor     ecx, ecx; lpMutexAttributes
0x180008301  call    cs:__imp_CreateMutexExW
0x180008307  mov     rdx, rax
0x18000830a  lea     rcx, [rsp+270h+var_240]
0x18000830f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008314  cmp     [rsp+270h+var_240], 0
0x18000831a  jnz     short loc_180008325
0x18000831c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008321  mov     ebx, eax
0x180008323  jmp     short loc_180008398
0x180008325  lea     rdx, [rsp+270h+var_238]
0x18000832a  lea     rcx, [rsp+270h+var_240]
0x18000832f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180008334  lea     rdx, [rsp+270h+var_230]; void **
0x180008339  mov     [rsp+270h+var_230], 0
0x180008342  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008347  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000834c  mov     ebx, eax
0x18000834e  test    eax, eax
0x180008350  jns     short loc_180008379
0x180008352  mov     edx, 12Eh; void *
0x180008357  mov     rcx, [rbp+178h]; this
0x18000835e  lea     r8, aWil; "wil"
0x180008365  mov     r9d, eax; char *
0x180008368  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000836d  lea     rcx, [rsp+270h+var_238]
0x180008372  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008377  jmp     short loc_180008398
0x180008379  mov     rcx, [rsp+270h+var_230]
0x18000837e  test    rcx, rcx
0x180008381  jz      short loc_1800083C8
0x180008383  mov     [rdi], rcx
0x180008386  mov     eax, [rcx]
0x180008388  inc     eax
0x18000838a  mov     [rcx], eax
0x18000838c  lea     rcx, [rsp+270h+var_238]
0x180008391  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008396  xor     ebx, ebx
0x180008398  lea     rcx, [rsp+270h+var_240]
0x18000839d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800083a2  mov     eax, ebx
0x1800083a4  mov     rcx, [rbp+170h+var_10]
0x1800083ab  xor     rcx, rsp; StackCookie
0x1800083ae  call    __security_check_cookie
0x1800083b3  lea     r11, [rsp+270h+var_s0]
0x1800083bb  mov     rbx, [r11+20h]
0x1800083bf  mov     rdi, [r11+28h]
0x1800083c3  mov     rsp, r11
0x1800083c6  pop     rbp
0x1800083c7  retn
0x1800083c8  mov     r8, rdi
0x1800083cb  lea     rdx, [rsp+270h+var_240]
0x1800083d0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800083d5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800083da  mov     ebx, eax
0x1800083dc  test    eax, eax
0x1800083de  jns     short loc_18000838C
0x1800083e0  mov     edx, 137h
0x1800083e5  jmp     loc_180008357
```
