# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003e24`
- end: `0x140003f8a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140004948`

## callees

- `0x1400023e0`
- `0x140003da4`
- `0x140003dc0`
- `0x140003e24`
- `0x1400046a8`
- `0x1400050a8`
- `0x1400054b0`
- `0x140005844`
- `0x140005a04`
- `0x140005df4`
- `0x140005ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003ea1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003ea1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003e5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003e5c`

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
0x140003e24  mov     [rsp-8+arg_10], rbx
0x140003e29  mov     [rsp-8+arg_18], rdi
0x140003e2e  push    rbp
0x140003e2f  lea     rbp, [rsp-170h]
0x140003e37  sub     rsp, 270h
0x140003e3e  mov     rax, cs:__security_cookie
0x140003e45  xor     rax, rsp
0x140003e48  mov     [rbp+170h+var_10], rax
0x140003e4f  mov     rdi, rdx
0x140003e52  mov     qword ptr [rdx], 0
0x140003e59  mov     rbx, rcx
0x140003e5c  call    cs:__imp_GetCurrentProcessId
0x140003e62  mov     [rsp+270h+var_248], rbx
0x140003e67  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003e6e  mov     r9d, eax
0x140003e71  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140003e79  mov     edx, 104h; unsigned __int64
0x140003e7e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140003e83  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140003e88  mov     r9d, 1F0001h; dwDesiredAccess
0x140003e8e  mov     [rsp+270h+var_240], 0
0x140003e97  xor     r8d, r8d; dwFlags
0x140003e9a  lea     rdx, [rsp+270h+Name]; lpName
0x140003e9f  xor     ecx, ecx; lpMutexAttributes
0x140003ea1  call    cs:__imp_CreateMutexExW
0x140003ea7  mov     rdx, rax
0x140003eaa  lea     rcx, [rsp+270h+var_240]
0x140003eaf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140003eb4  cmp     [rsp+270h+var_240], 0
0x140003eba  jnz     short loc_140003EC5
0x140003ebc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003ec1  mov     ebx, eax
0x140003ec3  jmp     short loc_140003F38
0x140003ec5  lea     rdx, [rsp+270h+var_238]
0x140003eca  lea     rcx, [rsp+270h+var_240]
0x140003ecf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140003ed4  lea     rdx, [rsp+270h+var_230]; void **
0x140003ed9  mov     [rsp+270h+var_230], 0
0x140003ee2  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140003ee7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x140003eec  mov     ebx, eax
0x140003eee  test    eax, eax
0x140003ef0  jns     short loc_140003F19
0x140003ef2  mov     edx, 12Eh; void *
0x140003ef7  mov     rcx, [rbp+178h]; this
0x140003efe  lea     r8, aWil; "wil"
0x140003f05  mov     r9d, eax; char *
0x140003f08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f0d  lea     rcx, [rsp+270h+var_238]
0x140003f12  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003f17  jmp     short loc_140003F38
0x140003f19  mov     rcx, [rsp+270h+var_230]
0x140003f1e  test    rcx, rcx
0x140003f21  jz      short loc_140003F68
0x140003f23  mov     [rdi], rcx
0x140003f26  mov     eax, [rcx]
0x140003f28  inc     eax
0x140003f2a  mov     [rcx], eax
0x140003f2c  lea     rcx, [rsp+270h+var_238]
0x140003f31  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003f36  xor     ebx, ebx
0x140003f38  lea     rcx, [rsp+270h+var_240]
0x140003f3d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003f42  mov     eax, ebx
0x140003f44  mov     rcx, [rbp+170h+var_10]
0x140003f4b  xor     rcx, rsp; StackCookie
0x140003f4e  call    __security_check_cookie
0x140003f53  lea     r11, [rsp+270h+var_s0]
0x140003f5b  mov     rbx, [r11+20h]
0x140003f5f  mov     rdi, [r11+28h]
0x140003f63  mov     rsp, r11
0x140003f66  pop     rbp
0x140003f67  retn
0x140003f68  mov     r8, rdi
0x140003f6b  lea     rdx, [rsp+270h+var_240]
0x140003f70  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140003f75  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140003f7a  mov     ebx, eax
0x140003f7c  test    eax, eax
0x140003f7e  jns     short loc_140003F2C
0x140003f80  mov     edx, 137h
0x140003f85  jmp     loc_140003EF7
```
