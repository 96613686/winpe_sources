# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180011ff8`
- end: `0x180012173`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180012864`

## callees

- `0x180002ab0`
- `0x18000500c`
- `0x180005028`
- `0x180005b78`
- `0x1800069a4`
- `0x180006fa0`
- `0x18000711c`
- `0x180007504`
- `0x180007608`
- `0x180011ff8`
- `0x180012ba4`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180012075`
- `KERNEL32!CreateMutexExW` at `0x180012075`
- `KERNEL32!GetCurrentProcessId` at `0x180012030`
- `KERNEL32!GetCurrentProcessId` at `0x180012030`

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
  unsigned int v8; // r8d
  _DWORD *v9; // rcx
  int v11; // eax
  unsigned int v12; // r8d
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-C8h] BYREF
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
      &v13,
      v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer >= 0 )
    {
      v9 = v15;
      if ( v15 )
      {
        *a2 = v15;
        ++*v9;
      }
      else
      {
        v11 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
        LastErrorFailHr = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v12, (const char *)(unsigned int)v11, 304);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180011ff8  mov     [rsp-8+arg_10], rbx
0x180011ffd  mov     [rsp-8+arg_18], rdi
0x180012002  push    rbp
0x180012003  lea     rbp, [rsp-170h]
0x18001200b  sub     rsp, 270h
0x180012012  mov     rax, cs:__security_cookie
0x180012019  xor     rax, rsp
0x18001201c  mov     [rbp+170h+var_10], rax
0x180012023  mov     rdi, rdx
0x180012026  mov     rbx, rcx
0x180012029  mov     qword ptr [rdx], 0
0x180012030  call    cs:__imp_GetCurrentProcessId
0x180012036  mov     r9d, eax
0x180012039  mov     [rsp+270h+var_248], rbx
0x18001203e  mov     [rsp+270h+var_250], 130h; int
0x180012046  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001204d  mov     edx, 104h; unsigned __int64
0x180012052  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180012057  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001205c  mov     [rsp+270h+var_240], 0
0x180012065  mov     r9d, 1F0001h; dwDesiredAccess
0x18001206b  xor     r8d, r8d; dwFlags
0x18001206e  lea     rdx, [rsp+270h+Name]; lpName
0x180012073  xor     ecx, ecx; lpMutexAttributes
0x180012075  call    cs:__imp_CreateMutexExW
0x18001207b  mov     rdx, rax
0x18001207e  lea     rcx, [rsp+270h+var_240]
0x180012083  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180012088  cmp     [rsp+270h+var_240], 0
0x18001208e  jnz     short loc_180012099
0x180012090  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012095  mov     ebx, eax
0x180012097  jmp     short loc_180012109
0x180012099  lea     rdx, [rsp+270h+var_238]
0x18001209e  lea     rcx, [rsp+270h+var_240]
0x1800120a3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800120a8  nop
0x1800120a9  mov     [rsp+270h+var_230], 0
0x1800120b2  lea     rdx, [rsp+270h+var_230]; void **
0x1800120b7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800120bc  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800120c1  mov     ebx, eax
0x1800120c3  test    eax, eax
0x1800120c5  jns     short loc_1800120E9
0x1800120c7  mov     rcx, [rbp+178h]; this
0x1800120ce  mov     r9d, eax; char *
0x1800120d1  mov     edx, 12Eh; void *
0x1800120d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800120db  nop
0x1800120dc  lea     rcx, [rsp+270h+var_238]
0x1800120e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800120e6  nop
0x1800120e7  jmp     short loc_180012109
0x1800120e9  mov     rcx, [rsp+270h+var_230]
0x1800120ee  test    rcx, rcx
0x1800120f1  jz      short loc_180012139
0x1800120f3  mov     [rdi], rcx
0x1800120f6  mov     eax, [rcx]
0x1800120f8  inc     eax
0x1800120fa  mov     [rcx], eax
0x1800120fc  lea     rcx, [rsp+270h+var_238]
0x180012101  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012106  nop
0x180012107  xor     ebx, ebx
0x180012109  lea     rcx, [rsp+270h+var_240]
0x18001210e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012113  mov     eax, ebx
0x180012115  mov     rcx, [rbp+170h+var_10]
0x18001211c  xor     rcx, rsp; StackCookie
0x18001211f  call    __security_check_cookie
0x180012124  lea     r11, [rsp+270h+var_s0]
0x18001212c  mov     rbx, [r11+20h]
0x180012130  mov     rdi, [r11+28h]
0x180012134  mov     rsp, r11
0x180012137  pop     rbp
0x180012138  retn
0x180012139  mov     r8, rdi
0x18001213c  lea     rdx, [rsp+270h+var_240]
0x180012141  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180012146  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001214b  mov     ebx, eax
0x18001214d  test    eax, eax
0x18001214f  jns     short loc_1800120FC
0x180012151  mov     rcx, [rbp+178h]; this
0x180012158  mov     r9d, eax; char *
0x18001215b  mov     edx, 137h; void *
0x180012160  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012165  nop
0x180012166  lea     rcx, [rsp+270h+var_238]
0x18001216b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012170  nop
0x180012171  jmp     short loc_180012109
```
