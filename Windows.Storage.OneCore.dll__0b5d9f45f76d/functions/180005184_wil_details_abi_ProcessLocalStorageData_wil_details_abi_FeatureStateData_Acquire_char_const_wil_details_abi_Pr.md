# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180005184`
- end: `0x1800052ea`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005f8c`

## callees

- `0x180002be0`
- `0x180004b90`
- `0x180004bac`
- `0x180005184`
- `0x180005db8`
- `0x180006c78`
- `0x180007fac`
- `0x180008704`
- `0x180008c18`
- `0x180009584`
- `0x1800098a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005201`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005201`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800051bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800051bc`

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
0x180005184  mov     [rsp-8+arg_10], rbx
0x180005189  mov     [rsp-8+arg_18], rdi
0x18000518e  push    rbp
0x18000518f  lea     rbp, [rsp-170h]
0x180005197  sub     rsp, 270h
0x18000519e  mov     rax, cs:__security_cookie
0x1800051a5  xor     rax, rsp
0x1800051a8  mov     [rbp+170h+var_10], rax
0x1800051af  mov     rdi, rdx
0x1800051b2  mov     qword ptr [rdx], 0
0x1800051b9  mov     rbx, rcx
0x1800051bc  call    cs:__imp_GetCurrentProcessId
0x1800051c2  mov     [rsp+270h+var_248], rbx
0x1800051c7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800051ce  mov     r9d, eax
0x1800051d1  mov     [rsp+270h+var_250], 130h; int
0x1800051d9  mov     edx, 104h; unsigned __int64
0x1800051de  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800051e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800051e8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800051ee  mov     [rsp+270h+var_240], 0
0x1800051f7  xor     r8d, r8d; dwFlags
0x1800051fa  lea     rdx, [rsp+270h+Name]; lpName
0x1800051ff  xor     ecx, ecx; lpMutexAttributes
0x180005201  call    cs:__imp_CreateMutexExW
0x180005207  mov     rdx, rax
0x18000520a  lea     rcx, [rsp+270h+var_240]
0x18000520f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005214  cmp     [rsp+270h+var_240], 0
0x18000521a  jnz     short loc_180005225
0x18000521c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005221  mov     ebx, eax
0x180005223  jmp     short loc_180005298
0x180005225  lea     rdx, [rsp+270h+var_238]
0x18000522a  lea     rcx, [rsp+270h+var_240]
0x18000522f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005234  lea     rdx, [rsp+270h+var_230]; void **
0x180005239  mov     [rsp+270h+var_230], 0
0x180005242  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005247  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000524c  mov     ebx, eax
0x18000524e  test    eax, eax
0x180005250  jns     short loc_180005279
0x180005252  mov     edx, 12Eh; void *
0x180005257  mov     rcx, [rbp+178h]; this
0x18000525e  lea     r8, aWil; "wil"
0x180005265  mov     r9d, eax; char *
0x180005268  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000526d  lea     rcx, [rsp+270h+var_238]
0x180005272  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005277  jmp     short loc_180005298
0x180005279  mov     rcx, [rsp+270h+var_230]
0x18000527e  test    rcx, rcx
0x180005281  jz      short loc_1800052C8
0x180005283  mov     [rdi], rcx
0x180005286  mov     eax, [rcx]
0x180005288  inc     eax
0x18000528a  mov     [rcx], eax
0x18000528c  lea     rcx, [rsp+270h+var_238]
0x180005291  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005296  xor     ebx, ebx
0x180005298  lea     rcx, [rsp+270h+var_240]
0x18000529d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800052a2  mov     eax, ebx
0x1800052a4  mov     rcx, [rbp+170h+var_10]
0x1800052ab  xor     rcx, rsp; StackCookie
0x1800052ae  call    __security_check_cookie
0x1800052b3  lea     r11, [rsp+270h+var_s0]
0x1800052bb  mov     rbx, [r11+20h]
0x1800052bf  mov     rdi, [r11+28h]
0x1800052c3  mov     rsp, r11
0x1800052c6  pop     rbp
0x1800052c7  retn
0x1800052c8  mov     r8, rdi
0x1800052cb  lea     rdx, [rsp+270h+var_240]
0x1800052d0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800052d5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800052da  mov     ebx, eax
0x1800052dc  test    eax, eax
0x1800052de  jns     short loc_18000528C
0x1800052e0  mov     edx, 137h
0x1800052e5  jmp     loc_180005257
```
