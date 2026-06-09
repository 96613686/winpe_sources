# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140006844`
- end: `0x1400069aa`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000774c`

## callees

- `0x140002f40`
- `0x140005e90`
- `0x140005eac`
- `0x140006844`
- `0x140007548`
- `0x140008b78`
- `0x14000a4bc`
- `0x14000cc54`
- `0x14000d038`
- `0x14000dfa4`
- `0x14000e68c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400068c1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400068c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000687c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000687c`

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
0x140006844  mov     [rsp-8+arg_10], rbx
0x140006849  mov     [rsp-8+arg_18], rdi
0x14000684e  push    rbp
0x14000684f  lea     rbp, [rsp-170h]
0x140006857  sub     rsp, 270h
0x14000685e  mov     rax, cs:__security_cookie
0x140006865  xor     rax, rsp
0x140006868  mov     [rbp+170h+var_10], rax
0x14000686f  mov     rdi, rdx
0x140006872  mov     qword ptr [rdx], 0
0x140006879  mov     rbx, rcx
0x14000687c  call    cs:__imp_GetCurrentProcessId
0x140006882  mov     [rsp+270h+var_248], rbx
0x140006887  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000688e  mov     r9d, eax
0x140006891  mov     [rsp+270h+var_250], 130h; int
0x140006899  mov     edx, 104h; unsigned __int64
0x14000689e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400068a3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400068a8  mov     r9d, 1F0001h; dwDesiredAccess
0x1400068ae  mov     [rsp+270h+var_240], 0
0x1400068b7  xor     r8d, r8d; dwFlags
0x1400068ba  lea     rdx, [rsp+270h+Name]; lpName
0x1400068bf  xor     ecx, ecx; lpMutexAttributes
0x1400068c1  call    cs:__imp_CreateMutexExW
0x1400068c7  mov     rdx, rax
0x1400068ca  lea     rcx, [rsp+270h+var_240]
0x1400068cf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400068d4  cmp     [rsp+270h+var_240], 0
0x1400068da  jnz     short loc_1400068E5
0x1400068dc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400068e1  mov     ebx, eax
0x1400068e3  jmp     short loc_140006958
0x1400068e5  lea     rdx, [rsp+270h+var_238]
0x1400068ea  lea     rcx, [rsp+270h+var_240]
0x1400068ef  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1400068f4  lea     rdx, [rsp+270h+var_230]; void **
0x1400068f9  mov     [rsp+270h+var_230], 0
0x140006902  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140006907  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x14000690c  mov     ebx, eax
0x14000690e  test    eax, eax
0x140006910  jns     short loc_140006939
0x140006912  mov     edx, 12Eh; void *
0x140006917  mov     rcx, [rbp+178h]; this
0x14000691e  lea     r8, aWil; "wil"
0x140006925  mov     r9d, eax; char *
0x140006928  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000692d  lea     rcx, [rsp+270h+var_238]
0x140006932  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006937  jmp     short loc_140006958
0x140006939  mov     rcx, [rsp+270h+var_230]
0x14000693e  test    rcx, rcx
0x140006941  jz      short loc_140006988
0x140006943  mov     [rdi], rcx
0x140006946  mov     eax, [rcx]
0x140006948  inc     eax
0x14000694a  mov     [rcx], eax
0x14000694c  lea     rcx, [rsp+270h+var_238]
0x140006951  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006956  xor     ebx, ebx
0x140006958  lea     rcx, [rsp+270h+var_240]
0x14000695d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006962  mov     eax, ebx
0x140006964  mov     rcx, [rbp+170h+var_10]
0x14000696b  xor     rcx, rsp; StackCookie
0x14000696e  call    __security_check_cookie
0x140006973  lea     r11, [rsp+270h+var_s0]
0x14000697b  mov     rbx, [r11+20h]
0x14000697f  mov     rdi, [r11+28h]
0x140006983  mov     rsp, r11
0x140006986  pop     rbp
0x140006987  retn
0x140006988  mov     r8, rdi
0x14000698b  lea     rdx, [rsp+270h+var_240]
0x140006990  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140006995  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000699a  mov     ebx, eax
0x14000699c  test    eax, eax
0x14000699e  jns     short loc_14000694C
0x1400069a0  mov     edx, 137h
0x1400069a5  jmp     loc_140006917
```
