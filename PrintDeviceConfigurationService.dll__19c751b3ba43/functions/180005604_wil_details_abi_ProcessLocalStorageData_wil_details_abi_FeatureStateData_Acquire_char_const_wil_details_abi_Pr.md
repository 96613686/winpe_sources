# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180005604`
- end: `0x18000576a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800059b8`

## callees

- `0x1800020c0`
- `0x180004f08`
- `0x180004f24`
- `0x180005604`
- `0x1800062b8`
- `0x1800070d8`
- `0x1800087bc`
- `0x180008f4c`
- `0x180009498`
- `0x180009ca4`
- `0x18000a07c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005681`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005681`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000563c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000563c`

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
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x180005604  mov     [rsp-8+arg_10], rbx
0x180005609  mov     [rsp-8+arg_18], rdi
0x18000560e  push    rbp
0x18000560f  lea     rbp, [rsp-170h]
0x180005617  sub     rsp, 270h
0x18000561e  mov     rax, cs:__security_cookie
0x180005625  xor     rax, rsp
0x180005628  mov     [rbp+170h+var_10], rax
0x18000562f  mov     rdi, rdx
0x180005632  mov     qword ptr [rdx], 0
0x180005639  mov     rbx, rcx
0x18000563c  call    cs:__imp_GetCurrentProcessId
0x180005642  mov     [rsp+270h+var_248], rbx
0x180005647  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000564e  mov     r9d, eax
0x180005651  mov     [rsp+270h+var_250], 130h; int
0x180005659  mov     edx, 104h; unsigned __int64
0x18000565e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005663  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005668  mov     r9d, 1F0001h; dwDesiredAccess
0x18000566e  mov     [rsp+270h+var_240], 0
0x180005677  xor     r8d, r8d; dwFlags
0x18000567a  lea     rdx, [rsp+270h+Name]; lpName
0x18000567f  xor     ecx, ecx; lpMutexAttributes
0x180005681  call    cs:__imp_CreateMutexExW
0x180005687  mov     rdx, rax
0x18000568a  lea     rcx, [rsp+270h+var_240]
0x18000568f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005694  cmp     [rsp+270h+var_240], 0
0x18000569a  jnz     short loc_1800056A5
0x18000569c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800056a1  mov     ebx, eax
0x1800056a3  jmp     short loc_180005718
0x1800056a5  lea     rdx, [rsp+270h+var_238]
0x1800056aa  lea     rcx, [rsp+270h+var_240]
0x1800056af  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800056b4  lea     rdx, [rsp+270h+var_230]; void **
0x1800056b9  mov     [rsp+270h+var_230], 0
0x1800056c2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800056c7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800056cc  mov     ebx, eax
0x1800056ce  test    eax, eax
0x1800056d0  jns     short loc_1800056F9
0x1800056d2  mov     edx, 12Eh; void *
0x1800056d7  mov     rcx, [rbp+178h]; this
0x1800056de  lea     r8, aWil; "wil"
0x1800056e5  mov     r9d, eax; char *
0x1800056e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800056ed  lea     rcx, [rsp+270h+var_238]
0x1800056f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800056f7  jmp     short loc_180005718
0x1800056f9  mov     rcx, [rsp+270h+var_230]
0x1800056fe  test    rcx, rcx
0x180005701  jz      short loc_180005748
0x180005703  mov     [rdi], rcx
0x180005706  mov     eax, [rcx]
0x180005708  inc     eax
0x18000570a  mov     [rcx], eax
0x18000570c  lea     rcx, [rsp+270h+var_238]
0x180005711  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005716  xor     ebx, ebx
0x180005718  lea     rcx, [rsp+270h+var_240]
0x18000571d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005722  mov     eax, ebx
0x180005724  mov     rcx, [rbp+170h+var_10]
0x18000572b  xor     rcx, rsp; StackCookie
0x18000572e  call    __security_check_cookie
0x180005733  lea     r11, [rsp+270h+var_s0]
0x18000573b  mov     rbx, [r11+20h]
0x18000573f  mov     rdi, [r11+28h]
0x180005743  mov     rsp, r11
0x180005746  pop     rbp
0x180005747  retn
0x180005748  mov     r8, rdi
0x18000574b  lea     rdx, [rsp+270h+var_240]
0x180005750  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005755  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000575a  mov     ebx, eax
0x18000575c  test    eax, eax
0x18000575e  jns     short loc_18000570C
0x180005760  mov     edx, 137h
0x180005765  jmp     loc_1800056D7
```
