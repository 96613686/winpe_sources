# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180047224`
- end: `0x180047397`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180047648`

## callees

- `0x18001e3c8`
- `0x18001e51c`
- `0x1800293a0`
- `0x1800406c4`
- `0x1800406e4`
- `0x180041568`
- `0x1800415d0`
- `0x180041848`
- `0x180041908`
- `0x180047224`
- `0x180047bf8`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x1800472a7`
- `KERNEL32!CreateMutexExW` at `0x1800472a7`
- `KERNEL32!GetCurrentProcessId` at `0x18004725c`
- `KERNEL32!GetCurrentProcessId` at `0x18004725c`

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
0x180047224  mov     [rsp-8+arg_10], rbx
0x180047229  mov     [rsp-8+arg_18], rdi
0x18004722e  push    rbp
0x18004722f  lea     rbp, [rsp-170h]
0x180047237  sub     rsp, 270h
0x18004723e  mov     rax, cs:__security_cookie
0x180047245  xor     rax, rsp
0x180047248  mov     [rbp+170h+var_10], rax
0x18004724f  mov     rdi, rdx
0x180047252  mov     qword ptr [rdx], 0
0x180047259  mov     rbx, rcx
0x18004725c  call    cs:__imp_GetCurrentProcessId
0x180047263  nop     dword ptr [rax+rax+00h]
0x180047268  mov     [rsp+270h+var_248], rbx
0x18004726d  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180047274  mov     r9d, eax
0x180047277  mov     [rsp+270h+var_250], 130h; int
0x18004727f  mov     edx, 104h; unsigned __int64
0x180047284  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180047289  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18004728e  mov     r9d, 1F0001h; dwDesiredAccess
0x180047294  mov     [rsp+270h+var_240], 0
0x18004729d  xor     r8d, r8d; dwFlags
0x1800472a0  lea     rdx, [rsp+270h+Name]; lpName
0x1800472a5  xor     ecx, ecx; lpMutexAttributes
0x1800472a7  call    cs:__imp_CreateMutexExW
0x1800472ae  nop     dword ptr [rax+rax+00h]
0x1800472b3  mov     rdx, rax
0x1800472b6  lea     rcx, [rsp+270h+var_240]
0x1800472bb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800472c0  cmp     [rsp+270h+var_240], 0
0x1800472c6  jnz     short loc_1800472D1
0x1800472c8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800472cd  mov     ebx, eax
0x1800472cf  jmp     short loc_180047344
0x1800472d1  lea     rdx, [rsp+270h+var_238]
0x1800472d6  lea     rcx, [rsp+270h+var_240]
0x1800472db  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800472e0  lea     rdx, [rsp+270h+var_230]; void **
0x1800472e5  mov     [rsp+270h+var_230], 0
0x1800472ee  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800472f3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1800472f8  mov     ebx, eax
0x1800472fa  test    eax, eax
0x1800472fc  jns     short loc_180047325
0x1800472fe  mov     edx, 12Eh; void *
0x180047303  mov     rcx, [rbp+178h]; this
0x18004730a  lea     r8, aWil; "wil"
0x180047311  mov     r9d, eax; char *
0x180047314  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047319  lea     rcx, [rsp+270h+var_238]
0x18004731e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180047323  jmp     short loc_180047344
0x180047325  mov     rcx, [rsp+270h+var_230]
0x18004732a  test    rcx, rcx
0x18004732d  jz      short loc_180047375
0x18004732f  mov     [rdi], rcx
0x180047332  mov     eax, [rcx]
0x180047334  inc     eax
0x180047336  mov     [rcx], eax
0x180047338  lea     rcx, [rsp+270h+var_238]
0x18004733d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180047342  xor     ebx, ebx
0x180047344  lea     rcx, [rsp+270h+var_240]
0x180047349  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004734e  mov     eax, ebx
0x180047350  mov     rcx, [rbp+170h+var_10]
0x180047357  xor     rcx, rsp; StackCookie
0x18004735a  call    __security_check_cookie
0x18004735f  lea     r11, [rsp+270h+var_s0]
0x180047367  mov     rbx, [r11+20h]
0x18004736b  mov     rdi, [r11+28h]
0x18004736f  mov     rsp, r11
0x180047372  pop     rbp
0x180047373  retn
0x180047375  mov     r8, rdi
0x180047378  lea     rdx, [rsp+270h+var_240]
0x18004737d  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180047382  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180047387  mov     ebx, eax
0x180047389  test    eax, eax
0x18004738b  jns     short loc_180047338
0x18004738d  mov     edx, 137h
0x180047392  jmp     loc_180047303
```
