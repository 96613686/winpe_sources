# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140009804`
- end: `0x1400099c2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000bf20`

## callees

- `0x1400029c0`
- `0x140004bb8`
- `0x140004bd8`
- `0x140005870`
- `0x140006bf4`
- `0x140007628`
- `0x14000779c`
- `0x140007d20`
- `0x140007e98`
- `0x140009804`
- `0x14000c1a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140009888`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140009888`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000983c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000983c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  _DWORD *v9; // rcx
  int v10; // eax
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
  if ( !v11 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
    return LastErrorFailHr;
  }
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v11,
    v12);
  v13 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
  LastErrorFailHr = Pointer;
  if ( Pointer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      304);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
    return LastErrorFailHr;
  }
  v9 = v13;
  if ( v13 )
  {
    *a2 = v13;
    ++*v9;
  }
  else
  {
    v10 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    LastErrorFailHr = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v10,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
      return LastErrorFailHr;
    }
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return 0;
}

```

## disassembly

```asm
0x140009804  mov     [rsp-8+arg_10], rbx
0x140009809  mov     [rsp-8+arg_18], rdi
0x14000980e  push    rbp
0x14000980f  lea     rbp, [rsp-170h]
0x140009817  sub     rsp, 270h
0x14000981e  mov     rax, cs:__security_cookie
0x140009825  xor     rax, rsp
0x140009828  mov     [rbp+170h+var_10], rax
0x14000982f  mov     rdi, rdx
0x140009832  mov     rbx, rcx
0x140009835  mov     qword ptr [rdx], 0
0x14000983c  call    cs:__imp_GetCurrentProcessId
0x140009843  nop     dword ptr [rax+rax+00h]
0x140009848  mov     r9d, eax
0x14000984b  mov     [rsp+270h+var_248], rbx
0x140009850  mov     [rsp+270h+var_250], 130h; int
0x140009858  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000985f  mov     edx, 104h; unsigned __int64
0x140009864  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140009869  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000986e  nop
0x14000986f  mov     [rsp+270h+var_240], 0
0x140009878  mov     r9d, 1F0001h; dwDesiredAccess
0x14000987e  xor     r8d, r8d; dwFlags
0x140009881  lea     rdx, [rsp+270h+Name]; lpName
0x140009886  xor     ecx, ecx; lpMutexAttributes
0x140009888  call    cs:__imp_CreateMutexExW
0x14000988f  nop     dword ptr [rax+rax+00h]
0x140009894  mov     rdx, rax
0x140009897  lea     rcx, [rsp+270h+var_240]
0x14000989c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400098a1  cmp     [rsp+270h+var_240], 0
0x1400098a7  jnz     short loc_1400098C2
0x1400098a9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400098ae  mov     ebx, eax
0x1400098b0  lea     rcx, [rsp+270h+var_240]
0x1400098b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400098ba  nop
0x1400098bb  mov     eax, ebx
0x1400098bd  jmp     loc_14000994E
0x1400098c2  lea     rdx, [rsp+270h+var_238]
0x1400098c7  lea     rcx, [rsp+270h+var_240]
0x1400098cc  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1400098d1  mov     [rsp+270h+var_230], 0
0x1400098da  lea     rdx, [rsp+270h+var_230]; void **
0x1400098df  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400098e4  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1400098e9  mov     ebx, eax
0x1400098eb  test    eax, eax
0x1400098ed  jns     short loc_140009923
0x1400098ef  mov     rcx, [rbp+178h]; this
0x1400098f6  mov     r9d, eax; char *
0x1400098f9  lea     r8, aWil; "wil"
0x140009900  mov     edx, 12Eh; void *
0x140009905  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000990a  nop
0x14000990b  lea     rcx, [rsp+270h+var_238]
0x140009910  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009915  nop
0x140009916  lea     rcx, [rsp+270h+var_240]
0x14000991b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009920  nop
0x140009921  jmp     short loc_1400098BB
0x140009923  mov     rcx, [rsp+270h+var_230]
0x140009928  test    rcx, rcx
0x14000992b  jz      short loc_140009973
0x14000992d  mov     [rdi], rcx
0x140009930  mov     eax, [rcx]
0x140009932  inc     eax
0x140009934  mov     [rcx], eax
0x140009936  lea     rcx, [rsp+270h+var_238]
0x14000993b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009940  nop
0x140009941  lea     rcx, [rsp+270h+var_240]
0x140009946  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000994b  nop
0x14000994c  xor     eax, eax
0x14000994e  mov     rcx, [rbp+170h+var_10]
0x140009955  xor     rcx, rsp; StackCookie
0x140009958  call    __security_check_cookie
0x14000995d  lea     r11, [rsp+270h+var_s0]
0x140009965  mov     rbx, [r11+20h]
0x140009969  mov     rdi, [r11+28h]
0x14000996d  mov     rsp, r11
0x140009970  pop     rbp
0x140009971  retn
0x140009973  mov     r8, rdi
0x140009976  lea     rdx, [rsp+270h+var_240]
0x14000997b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140009980  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140009985  mov     ebx, eax
0x140009987  test    eax, eax
0x140009989  jns     short loc_140009936
0x14000998b  mov     rcx, [rbp+178h]; this
0x140009992  mov     r9d, eax; char *
0x140009995  lea     r8, aWil; "wil"
0x14000999c  mov     edx, 137h; void *
0x1400099a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400099a6  nop
0x1400099a7  lea     rcx, [rsp+270h+var_238]
0x1400099ac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400099b1  nop
0x1400099b2  lea     rcx, [rsp+270h+var_240]
0x1400099b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400099bc  nop
0x1400099bd  jmp     loc_1400098BB
```
