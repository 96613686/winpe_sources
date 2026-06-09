# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140009414`
- end: `0x1400095c5`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `433`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000b9d4`

## callees

- `0x140002930`
- `0x140004b2c`
- `0x140004b48`
- `0x1400056c8`
- `0x140006984`
- `0x140007368`
- `0x1400074dc`
- `0x140007a30`
- `0x140007b88`
- `0x140009414`
- `0x14000bc54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140009492`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140009492`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000944c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000944c`

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
  void *v7; // rdx
  int Pointer; // eax
  void *v10; // rdx
  _DWORD *v11; // rcx
  void *v12; // rdx
  int v13; // eax
  void *v14; // rdx
  wil::details *v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v17; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v15 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v15,
    Mutex);
  if ( !v15 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v15,
      v7);
    return LastErrorFailHr;
  }
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v15,
    v16);
  v17 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v17);
  LastErrorFailHr = Pointer;
  if ( Pointer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      304);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v15,
      v10);
    return LastErrorFailHr;
  }
  v11 = v17;
  if ( v17 )
  {
    *a2 = v17;
    ++*v11;
  }
  else
  {
    v13 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    LastErrorFailHr = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v15,
        v14);
      return LastErrorFailHr;
    }
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v15,
    v12);
  return 0;
}

```

## disassembly

```asm
0x140009414  mov     [rsp-8+arg_10], rbx
0x140009419  mov     [rsp-8+arg_18], rdi
0x14000941e  push    rbp
0x14000941f  lea     rbp, [rsp-170h]
0x140009427  sub     rsp, 270h
0x14000942e  mov     rax, cs:__security_cookie
0x140009435  xor     rax, rsp
0x140009438  mov     [rbp+170h+var_10], rax
0x14000943f  mov     rdi, rdx
0x140009442  mov     rbx, rcx
0x140009445  mov     qword ptr [rdx], 0
0x14000944c  call    cs:__imp_GetCurrentProcessId
0x140009452  mov     r9d, eax
0x140009455  mov     [rsp+270h+var_248], rbx
0x14000945a  mov     [rsp+270h+var_250], 130h; int
0x140009462  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140009469  mov     edx, 104h; unsigned __int64
0x14000946e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140009473  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009478  nop
0x140009479  mov     [rsp+270h+var_240], 0
0x140009482  mov     r9d, 1F0001h; dwDesiredAccess
0x140009488  xor     r8d, r8d; dwFlags
0x14000948b  lea     rdx, [rsp+270h+Name]; lpName
0x140009490  xor     ecx, ecx; lpMutexAttributes
0x140009492  call    cs:__imp_CreateMutexExW
0x140009498  mov     rdx, rax
0x14000949b  lea     rcx, [rsp+270h+var_240]
0x1400094a0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400094a5  cmp     [rsp+270h+var_240], 0
0x1400094ab  jnz     short loc_1400094C6
0x1400094ad  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400094b2  mov     ebx, eax
0x1400094b4  lea     rcx, [rsp+270h+var_240]
0x1400094b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400094be  nop
0x1400094bf  mov     eax, ebx
0x1400094c1  jmp     loc_140009552
0x1400094c6  lea     rdx, [rsp+270h+var_238]
0x1400094cb  lea     rcx, [rsp+270h+var_240]
0x1400094d0  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1400094d5  mov     [rsp+270h+var_230], 0
0x1400094de  lea     rdx, [rsp+270h+var_230]; void **
0x1400094e3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400094e8  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1400094ed  mov     ebx, eax
0x1400094ef  test    eax, eax
0x1400094f1  jns     short loc_140009527
0x1400094f3  mov     rcx, [rbp+178h]; this
0x1400094fa  mov     r9d, eax; char *
0x1400094fd  lea     r8, aWil; "wil"
0x140009504  mov     edx, 12Eh; void *
0x140009509  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000950e  nop
0x14000950f  lea     rcx, [rsp+270h+var_238]
0x140009514  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009519  nop
0x14000951a  lea     rcx, [rsp+270h+var_240]
0x14000951f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009524  nop
0x140009525  jmp     short loc_1400094BF
0x140009527  mov     rcx, [rsp+270h+var_230]
0x14000952c  test    rcx, rcx
0x14000952f  jz      short loc_140009576
0x140009531  mov     [rdi], rcx
0x140009534  mov     eax, [rcx]
0x140009536  inc     eax
0x140009538  mov     [rcx], eax
0x14000953a  lea     rcx, [rsp+270h+var_238]
0x14000953f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009544  nop
0x140009545  lea     rcx, [rsp+270h+var_240]
0x14000954a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000954f  nop
0x140009550  xor     eax, eax
0x140009552  mov     rcx, [rbp+170h+var_10]
0x140009559  xor     rcx, rsp; StackCookie
0x14000955c  call    __security_check_cookie
0x140009561  lea     r11, [rsp+270h+var_s0]
0x140009569  mov     rbx, [r11+20h]
0x14000956d  mov     rdi, [r11+28h]
0x140009571  mov     rsp, r11
0x140009574  pop     rbp
0x140009575  retn
0x140009576  mov     r8, rdi
0x140009579  lea     rdx, [rsp+270h+var_240]
0x14000957e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140009583  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140009588  mov     ebx, eax
0x14000958a  test    eax, eax
0x14000958c  jns     short loc_14000953A
0x14000958e  mov     rcx, [rbp+178h]; this
0x140009595  mov     r9d, eax; char *
0x140009598  lea     r8, aWil; "wil"
0x14000959f  mov     edx, 137h; void *
0x1400095a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400095a9  nop
0x1400095aa  lea     rcx, [rsp+270h+var_238]
0x1400095af  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400095b4  nop
0x1400095b5  lea     rcx, [rsp+270h+var_240]
0x1400095ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400095bf  nop
0x1400095c0  jmp     loc_1400094BF
```
