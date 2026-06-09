# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008d8c`
- end: `0x180008ef2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800098ac`

## callees

- `0x180003980`
- `0x180008d0c`
- `0x180008d28`
- `0x180008d8c`
- `0x180009608`
- `0x180009fdc`
- `0x18000a3c0`
- `0x18000a7c0`
- `0x18000a918`
- `0x18000ada0`
- `0x18000ae58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008e09`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008e09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008dc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008dc4`

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
0x180008d8c  mov     [rsp-8+arg_10], rbx
0x180008d91  mov     [rsp-8+arg_18], rdi
0x180008d96  push    rbp
0x180008d97  lea     rbp, [rsp-170h]
0x180008d9f  sub     rsp, 270h
0x180008da6  mov     rax, cs:__security_cookie
0x180008dad  xor     rax, rsp
0x180008db0  mov     [rbp+170h+var_10], rax
0x180008db7  mov     rdi, rdx
0x180008dba  mov     qword ptr [rdx], 0
0x180008dc1  mov     rbx, rcx
0x180008dc4  call    cs:__imp_GetCurrentProcessId
0x180008dca  mov     [rsp+270h+var_248], rbx
0x180008dcf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008dd6  mov     r9d, eax
0x180008dd9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180008de1  mov     edx, 104h; unsigned __int64
0x180008de6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008deb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008df0  mov     r9d, 1F0001h; dwDesiredAccess
0x180008df6  mov     [rsp+270h+var_240], 0
0x180008dff  xor     r8d, r8d; dwFlags
0x180008e02  lea     rdx, [rsp+270h+Name]; lpName
0x180008e07  xor     ecx, ecx; lpMutexAttributes
0x180008e09  call    cs:__imp_CreateMutexExW
0x180008e0f  mov     rdx, rax
0x180008e12  lea     rcx, [rsp+270h+var_240]
0x180008e17  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008e1c  cmp     [rsp+270h+var_240], 0
0x180008e22  jnz     short loc_180008E2D
0x180008e24  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008e29  mov     ebx, eax
0x180008e2b  jmp     short loc_180008EA0
0x180008e2d  lea     rdx, [rsp+270h+var_238]
0x180008e32  lea     rcx, [rsp+270h+var_240]
0x180008e37  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180008e3c  lea     rdx, [rsp+270h+var_230]; void **
0x180008e41  mov     [rsp+270h+var_230], 0
0x180008e4a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008e4f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180008e54  mov     ebx, eax
0x180008e56  test    eax, eax
0x180008e58  jns     short loc_180008E81
0x180008e5a  mov     edx, 12Eh; void *
0x180008e5f  mov     rcx, [rbp+178h]; this
0x180008e66  lea     r8, aWil; "wil"
0x180008e6d  mov     r9d, eax; char *
0x180008e70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e75  lea     rcx, [rsp+270h+var_238]
0x180008e7a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008e7f  jmp     short loc_180008EA0
0x180008e81  mov     rcx, [rsp+270h+var_230]
0x180008e86  test    rcx, rcx
0x180008e89  jz      short loc_180008ED0
0x180008e8b  mov     [rdi], rcx
0x180008e8e  mov     eax, [rcx]
0x180008e90  inc     eax
0x180008e92  mov     [rcx], eax
0x180008e94  lea     rcx, [rsp+270h+var_238]
0x180008e99  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008e9e  xor     ebx, ebx
0x180008ea0  lea     rcx, [rsp+270h+var_240]
0x180008ea5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008eaa  mov     eax, ebx
0x180008eac  mov     rcx, [rbp+170h+var_10]
0x180008eb3  xor     rcx, rsp; StackCookie
0x180008eb6  call    __security_check_cookie
0x180008ebb  lea     r11, [rsp+270h+var_s0]
0x180008ec3  mov     rbx, [r11+20h]
0x180008ec7  mov     rdi, [r11+28h]
0x180008ecb  mov     rsp, r11
0x180008ece  pop     rbp
0x180008ecf  retn
0x180008ed0  mov     r8, rdi
0x180008ed3  lea     rdx, [rsp+270h+var_240]
0x180008ed8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008edd  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180008ee2  mov     ebx, eax
0x180008ee4  test    eax, eax
0x180008ee6  jns     short loc_180008E94
0x180008ee8  mov     edx, 137h
0x180008eed  jmp     loc_180008E5F
```
