# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180017810`
- end: `0x18001796f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001871c`

## callees

- `0x180016580`
- `0x18001754c`
- `0x180017568`
- `0x180017810`
- `0x180018548`
- `0x1800191a8`
- `0x18001a354`
- `0x18001ab94`
- `0x18001b264`
- `0x18001b54c`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001788d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001788d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017848`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017848`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v9; // r8d
  __int64 v10; // rdx
  _DWORD *v11; // rcx
  wil::details *v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
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
      (HANDLE *)&v13,
      &v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
      goto LABEL_9;
    }
    v11 = v15;
    if ( v15 )
    {
      *a2 = v15;
      ++*v11;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v10 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v13,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180017810  mov     [rsp-8+arg_10], rbx
0x180017815  mov     [rsp-8+arg_18], rdi
0x18001781a  push    rbp
0x18001781b  lea     rbp, [rsp-170h]
0x180017823  sub     rsp, 270h
0x18001782a  mov     rax, cs:__security_cookie
0x180017831  xor     rax, rsp
0x180017834  mov     [rbp+170h+var_10], rax
0x18001783b  mov     rdi, rdx
0x18001783e  mov     qword ptr [rdx], 0
0x180017845  mov     rbx, rcx
0x180017848  call    cs:__imp_GetCurrentProcessId
0x18001784e  mov     [rsp+270h+var_248], rbx
0x180017853  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001785a  mov     r9d, eax
0x18001785d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180017865  mov     edx, 104h; unsigned __int64
0x18001786a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001786f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017874  mov     r9d, 1F0001h; dwDesiredAccess
0x18001787a  mov     [rsp+270h+var_240], 0
0x180017883  xor     r8d, r8d; dwFlags
0x180017886  lea     rdx, [rsp+270h+Name]; lpName
0x18001788b  xor     ecx, ecx; lpMutexAttributes
0x18001788d  call    cs:__imp_CreateMutexExW
0x180017893  mov     rdx, rax
0x180017896  lea     rcx, [rsp+270h+var_240]
0x18001789b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800178a0  cmp     [rsp+270h+var_240], 0
0x1800178a6  jnz     short loc_1800178B1
0x1800178a8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800178ad  mov     ebx, eax
0x1800178af  jmp     short loc_18001791D
0x1800178b1  lea     rdx, [rsp+270h+var_238]
0x1800178b6  lea     rcx, [rsp+270h+var_240]
0x1800178bb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800178c0  lea     rdx, [rsp+270h+var_230]; void **
0x1800178c5  mov     [rsp+270h+var_230], 0
0x1800178ce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800178d3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800178d8  mov     ebx, eax
0x1800178da  test    eax, eax
0x1800178dc  jns     short loc_1800178FE
0x1800178de  mov     edx, 12Eh; void *
0x1800178e3  mov     rcx, [rbp+178h]; this
0x1800178ea  mov     r9d, eax; char *
0x1800178ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800178f2  lea     rcx, [rsp+270h+var_238]
0x1800178f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800178fc  jmp     short loc_18001791D
0x1800178fe  mov     rcx, [rsp+270h+var_230]
0x180017903  test    rcx, rcx
0x180017906  jz      short loc_18001794D
0x180017908  mov     [rdi], rcx
0x18001790b  mov     eax, [rcx]
0x18001790d  inc     eax
0x18001790f  mov     [rcx], eax
0x180017911  lea     rcx, [rsp+270h+var_238]
0x180017916  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001791b  xor     ebx, ebx
0x18001791d  lea     rcx, [rsp+270h+var_240]
0x180017922  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017927  mov     eax, ebx
0x180017929  mov     rcx, [rbp+170h+var_10]
0x180017930  xor     rcx, rsp; StackCookie
0x180017933  call    __security_check_cookie
0x180017938  lea     r11, [rsp+270h+var_s0]
0x180017940  mov     rbx, [r11+20h]
0x180017944  mov     rdi, [r11+28h]
0x180017948  mov     rsp, r11
0x18001794b  pop     rbp
0x18001794c  retn
0x18001794d  mov     r8, rdi
0x180017950  lea     rdx, [rsp+270h+var_240]
0x180017955  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001795a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001795f  mov     ebx, eax
0x180017961  test    eax, eax
0x180017963  jns     short loc_180017911
0x180017965  mov     edx, 137h
0x18001796a  jmp     loc_1800178E3
```
