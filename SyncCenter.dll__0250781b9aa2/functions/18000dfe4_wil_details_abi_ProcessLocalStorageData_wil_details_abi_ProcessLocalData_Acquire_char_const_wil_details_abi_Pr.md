# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000dfe4`
- end: `0x18000e14a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000eac4`

## callees

- `0x180008584`
- `0x18000b60c`
- `0x18000b8d8`
- `0x18000df0c`
- `0x18000df28`
- `0x18000dfe4`
- `0x18000e868`
- `0x18000f878`
- `0x18000fc74`
- `0x18000fd20`
- `0x180052950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000e061`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000e061`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e01c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e01c`

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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x18000dfe4  mov     [rsp-8+arg_10], rbx
0x18000dfe9  mov     [rsp-8+arg_18], rdi
0x18000dfee  push    rbp
0x18000dfef  lea     rbp, [rsp-170h]
0x18000dff7  sub     rsp, 270h
0x18000dffe  mov     rax, cs:__security_cookie
0x18000e005  xor     rax, rsp
0x18000e008  mov     [rbp+170h+var_10], rax
0x18000e00f  mov     rdi, rdx
0x18000e012  mov     qword ptr [rdx], 0
0x18000e019  mov     rbx, rcx
0x18000e01c  call    cs:__imp_GetCurrentProcessId
0x18000e022  mov     [rsp+270h+var_248], rbx
0x18000e027  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000e02e  mov     r9d, eax
0x18000e031  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000e039  mov     edx, 104h; unsigned __int64
0x18000e03e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e043  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e048  mov     r9d, 1F0001h; dwDesiredAccess
0x18000e04e  mov     [rsp+270h+var_240], 0
0x18000e057  xor     r8d, r8d; dwFlags
0x18000e05a  lea     rdx, [rsp+270h+Name]; lpName
0x18000e05f  xor     ecx, ecx; lpMutexAttributes
0x18000e061  call    cs:__imp_CreateMutexExW
0x18000e067  mov     rdx, rax
0x18000e06a  lea     rcx, [rsp+270h+var_240]
0x18000e06f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000e074  cmp     [rsp+270h+var_240], 0
0x18000e07a  jnz     short loc_18000E085
0x18000e07c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000e081  mov     ebx, eax
0x18000e083  jmp     short loc_18000E0F8
0x18000e085  lea     rdx, [rsp+270h+var_238]
0x18000e08a  lea     rcx, [rsp+270h+var_240]
0x18000e08f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000e094  lea     rdx, [rsp+270h+var_230]; void **
0x18000e099  mov     [rsp+270h+var_230], 0
0x18000e0a2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e0a7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000e0ac  mov     ebx, eax
0x18000e0ae  test    eax, eax
0x18000e0b0  jns     short loc_18000E0D9
0x18000e0b2  mov     edx, 12Eh; void *
0x18000e0b7  mov     rcx, [rbp+178h]; this
0x18000e0be  lea     r8, aWil; "wil"
0x18000e0c5  mov     r9d, eax; char *
0x18000e0c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e0cd  lea     rcx, [rsp+270h+var_238]
0x18000e0d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e0d7  jmp     short loc_18000E0F8
0x18000e0d9  mov     rcx, [rsp+270h+var_230]
0x18000e0de  test    rcx, rcx
0x18000e0e1  jz      short loc_18000E128
0x18000e0e3  mov     [rdi], rcx
0x18000e0e6  mov     eax, [rcx]
0x18000e0e8  inc     eax
0x18000e0ea  mov     [rcx], eax
0x18000e0ec  lea     rcx, [rsp+270h+var_238]
0x18000e0f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e0f6  xor     ebx, ebx
0x18000e0f8  lea     rcx, [rsp+270h+var_240]
0x18000e0fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e102  mov     eax, ebx
0x18000e104  mov     rcx, [rbp+170h+var_10]
0x18000e10b  xor     rcx, rsp; StackCookie
0x18000e10e  call    __security_check_cookie
0x18000e113  lea     r11, [rsp+270h+var_s0]
0x18000e11b  mov     rbx, [r11+20h]
0x18000e11f  mov     rdi, [r11+28h]
0x18000e123  mov     rsp, r11
0x18000e126  pop     rbp
0x18000e127  retn
0x18000e128  mov     r8, rdi
0x18000e12b  lea     rdx, [rsp+270h+var_240]
0x18000e130  lea     rcx, [rsp+270h+Name]
0x18000e135  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000e13a  mov     ebx, eax
0x18000e13c  test    eax, eax
0x18000e13e  jns     short loc_18000E0EC
0x18000e140  mov     edx, 137h
0x18000e145  jmp     loc_18000E0B7
```
