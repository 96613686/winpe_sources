# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800128e0`
- end: `0x180012a3f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800168dc`

## callees

- `0x180004c94`
- `0x180004d74`
- `0x180004d90`
- `0x180005020`
- `0x18000fa58`
- `0x18000fdb0`
- `0x1800128e0`
- `0x180012a48`
- `0x180012a8c`
- `0x180016a08`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001295d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001295d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012918`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012918`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  void *v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800128e0  mov     [rsp-8+arg_10], rbx
0x1800128e5  mov     [rsp-8+arg_18], rdi
0x1800128ea  push    rbp
0x1800128eb  lea     rbp, [rsp-170h]
0x1800128f3  sub     rsp, 270h
0x1800128fa  mov     rax, cs:__security_cookie
0x180012901  xor     rax, rsp
0x180012904  mov     [rbp+170h+var_10], rax
0x18001290b  mov     rdi, rdx
0x18001290e  mov     qword ptr [rdx], 0
0x180012915  mov     rbx, rcx
0x180012918  call    cs:__imp_GetCurrentProcessId
0x18001291e  mov     [rsp+270h+var_248], rbx
0x180012923  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001292a  mov     r9d, eax
0x18001292d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180012935  mov     edx, 104h; unsigned __int64
0x18001293a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001293f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012944  mov     r9d, 1F0001h; dwDesiredAccess
0x18001294a  mov     [rsp+270h+var_240], 0
0x180012953  xor     r8d, r8d; dwFlags
0x180012956  lea     rdx, [rsp+270h+Name]; lpName
0x18001295b  xor     ecx, ecx; lpMutexAttributes
0x18001295d  call    cs:__imp_CreateMutexExW
0x180012963  mov     rdx, rax
0x180012966  lea     rcx, [rsp+270h+var_240]
0x18001296b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180012970  cmp     [rsp+270h+var_240], 0
0x180012976  jnz     short loc_180012981
0x180012978  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001297d  mov     ebx, eax
0x18001297f  jmp     short loc_1800129ED
0x180012981  lea     rdx, [rsp+270h+var_238]
0x180012986  lea     rcx, [rsp+270h+var_240]
0x18001298b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180012990  lea     rdx, [rsp+270h+var_230]; void **
0x180012995  mov     [rsp+270h+var_230], 0
0x18001299e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800129a3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800129a8  mov     ebx, eax
0x1800129aa  test    eax, eax
0x1800129ac  jns     short loc_1800129CE
0x1800129ae  mov     edx, 12Eh; void *
0x1800129b3  mov     rcx, [rbp+178h]; this
0x1800129ba  mov     r9d, eax; char *
0x1800129bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800129c2  lea     rcx, [rsp+270h+var_238]
0x1800129c7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800129cc  jmp     short loc_1800129ED
0x1800129ce  mov     rcx, [rsp+270h+var_230]
0x1800129d3  test    rcx, rcx
0x1800129d6  jz      short loc_180012A1D
0x1800129d8  mov     [rdi], rcx
0x1800129db  mov     eax, [rcx]
0x1800129dd  inc     eax
0x1800129df  mov     [rcx], eax
0x1800129e1  lea     rcx, [rsp+270h+var_238]
0x1800129e6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800129eb  xor     ebx, ebx
0x1800129ed  lea     rcx, [rsp+270h+var_240]
0x1800129f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800129f7  mov     eax, ebx
0x1800129f9  mov     rcx, [rbp+170h+var_10]
0x180012a00  xor     rcx, rsp; StackCookie
0x180012a03  call    __security_check_cookie
0x180012a08  lea     r11, [rsp+270h+var_s0]
0x180012a10  mov     rbx, [r11+20h]
0x180012a14  mov     rdi, [r11+28h]
0x180012a18  mov     rsp, r11
0x180012a1b  pop     rbp
0x180012a1c  retn
0x180012a1d  mov     r8, rdi
0x180012a20  lea     rdx, [rsp+270h+var_240]
0x180012a25  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180012a2a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180012a2f  mov     ebx, eax
0x180012a31  test    eax, eax
0x180012a33  jns     short loc_1800129E1
0x180012a35  mov     edx, 137h
0x180012a3a  jmp     loc_1800129B3
```
