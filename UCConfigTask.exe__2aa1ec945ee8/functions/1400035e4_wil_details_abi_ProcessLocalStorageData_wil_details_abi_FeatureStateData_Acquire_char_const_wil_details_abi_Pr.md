# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1400035e4`
- end: `0x14000374a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140004384`

## callees

- `0x1400014c0`
- `0x140003078`
- `0x140003094`
- `0x1400035e4`
- `0x1400041c8`
- `0x140004f68`
- `0x140005fcc`
- `0x14000670c`
- `0x140006af8`
- `0x1400071e4`
- `0x140007508`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003661`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003661`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000361c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000361c`

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
  void *v9; // rdx
  __int64 v10; // rdx
  void *v11; // rdx
  _DWORD *v12; // rcx
  wil::details *v14; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v15; // [rsp+38h] [rbp-C8h] BYREF
  void *v16; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v14 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v14,
    Mutex);
  if ( v14 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v14,
      &v15);
    v16 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v16);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v15,
        v11);
      goto LABEL_9;
    }
    v12 = v16;
    if ( v16 )
    {
      *a2 = v16;
      ++*v12;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v10 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v15,
      v9);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v14,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1400035e4  mov     [rsp-8+arg_10], rbx
0x1400035e9  mov     [rsp-8+arg_18], rdi
0x1400035ee  push    rbp
0x1400035ef  lea     rbp, [rsp-170h]
0x1400035f7  sub     rsp, 270h
0x1400035fe  mov     rax, cs:__security_cookie
0x140003605  xor     rax, rsp
0x140003608  mov     [rbp+170h+var_10], rax
0x14000360f  mov     rdi, rdx
0x140003612  mov     qword ptr [rdx], 0
0x140003619  mov     rbx, rcx
0x14000361c  call    cs:__imp_GetCurrentProcessId
0x140003622  mov     [rsp+270h+var_248], rbx
0x140003627  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000362e  mov     r9d, eax
0x140003631  mov     [rsp+270h+var_250], 130h; int
0x140003639  mov     edx, 104h; unsigned __int64
0x14000363e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140003643  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003648  mov     r9d, 1F0001h; dwDesiredAccess
0x14000364e  mov     [rsp+270h+var_240], 0
0x140003657  xor     r8d, r8d; dwFlags
0x14000365a  lea     rdx, [rsp+270h+Name]; lpName
0x14000365f  xor     ecx, ecx; lpMutexAttributes
0x140003661  call    cs:__imp_CreateMutexExW
0x140003667  mov     rdx, rax
0x14000366a  lea     rcx, [rsp+270h+var_240]
0x14000366f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140003674  cmp     [rsp+270h+var_240], 0
0x14000367a  jnz     short loc_140003685
0x14000367c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003681  mov     ebx, eax
0x140003683  jmp     short loc_1400036F8
0x140003685  lea     rdx, [rsp+270h+var_238]
0x14000368a  lea     rcx, [rsp+270h+var_240]
0x14000368f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140003694  lea     rdx, [rsp+270h+var_230]; void **
0x140003699  mov     [rsp+270h+var_230], 0
0x1400036a2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400036a7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1400036ac  mov     ebx, eax
0x1400036ae  test    eax, eax
0x1400036b0  jns     short loc_1400036D9
0x1400036b2  mov     edx, 12Eh; void *
0x1400036b7  mov     rcx, [rbp+178h]; this
0x1400036be  lea     r8, aWil; "wil"
0x1400036c5  mov     r9d, eax; char *
0x1400036c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400036cd  lea     rcx, [rsp+270h+var_238]
0x1400036d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400036d7  jmp     short loc_1400036F8
0x1400036d9  mov     rcx, [rsp+270h+var_230]
0x1400036de  test    rcx, rcx
0x1400036e1  jz      short loc_140003728
0x1400036e3  mov     [rdi], rcx
0x1400036e6  mov     eax, [rcx]
0x1400036e8  inc     eax
0x1400036ea  mov     [rcx], eax
0x1400036ec  lea     rcx, [rsp+270h+var_238]
0x1400036f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400036f6  xor     ebx, ebx
0x1400036f8  lea     rcx, [rsp+270h+var_240]
0x1400036fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003702  mov     eax, ebx
0x140003704  mov     rcx, [rbp+170h+var_10]
0x14000370b  xor     rcx, rsp; StackCookie
0x14000370e  call    __security_check_cookie
0x140003713  lea     r11, [rsp+270h+var_s0]
0x14000371b  mov     rbx, [r11+20h]
0x14000371f  mov     rdi, [r11+28h]
0x140003723  mov     rsp, r11
0x140003726  pop     rbp
0x140003727  retn
0x140003728  mov     r8, rdi
0x14000372b  lea     rdx, [rsp+270h+var_240]
0x140003730  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140003735  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000373a  mov     ebx, eax
0x14000373c  test    eax, eax
0x14000373e  jns     short loc_1400036EC
0x140003740  mov     edx, 137h
0x140003745  jmp     loc_1400036B7
```
