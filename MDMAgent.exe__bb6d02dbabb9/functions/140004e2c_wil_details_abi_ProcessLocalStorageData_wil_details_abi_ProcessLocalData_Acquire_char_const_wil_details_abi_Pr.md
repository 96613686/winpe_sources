# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140004e2c`
- end: `0x140004f9f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140005c7c`

## callees

- `0x1400029c0`
- `0x140004bb8`
- `0x140004bd8`
- `0x140004e2c`
- `0x140005870`
- `0x140006510`
- `0x140006bf4`
- `0x140007628`
- `0x14000779c`
- `0x140007d20`
- `0x140007e98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004eaf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004eaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004e64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004e64`

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
0x140004e2c  mov     [rsp-8+arg_10], rbx
0x140004e31  mov     [rsp-8+arg_18], rdi
0x140004e36  push    rbp
0x140004e37  lea     rbp, [rsp-170h]
0x140004e3f  sub     rsp, 270h
0x140004e46  mov     rax, cs:__security_cookie
0x140004e4d  xor     rax, rsp
0x140004e50  mov     [rbp+170h+var_10], rax
0x140004e57  mov     rdi, rdx
0x140004e5a  mov     qword ptr [rdx], 0
0x140004e61  mov     rbx, rcx
0x140004e64  call    cs:__imp_GetCurrentProcessId
0x140004e6b  nop     dword ptr [rax+rax+00h]
0x140004e70  mov     [rsp+270h+var_248], rbx
0x140004e75  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004e7c  mov     r9d, eax
0x140004e7f  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140004e87  mov     edx, 104h; unsigned __int64
0x140004e8c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004e91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004e96  mov     r9d, 1F0001h; dwDesiredAccess
0x140004e9c  mov     [rsp+270h+var_240], 0
0x140004ea5  xor     r8d, r8d; dwFlags
0x140004ea8  lea     rdx, [rsp+270h+Name]; lpName
0x140004ead  xor     ecx, ecx; lpMutexAttributes
0x140004eaf  call    cs:__imp_CreateMutexExW
0x140004eb6  nop     dword ptr [rax+rax+00h]
0x140004ebb  mov     rdx, rax
0x140004ebe  lea     rcx, [rsp+270h+var_240]
0x140004ec3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140004ec8  cmp     [rsp+270h+var_240], 0
0x140004ece  jnz     short loc_140004ED9
0x140004ed0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004ed5  mov     ebx, eax
0x140004ed7  jmp     short loc_140004F4C
0x140004ed9  lea     rdx, [rsp+270h+var_238]
0x140004ede  lea     rcx, [rsp+270h+var_240]
0x140004ee3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140004ee8  lea     rdx, [rsp+270h+var_230]; void **
0x140004eed  mov     [rsp+270h+var_230], 0
0x140004ef6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004efb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140004f00  mov     ebx, eax
0x140004f02  test    eax, eax
0x140004f04  jns     short loc_140004F2D
0x140004f06  mov     edx, 12Eh; void *
0x140004f0b  mov     rcx, [rbp+178h]; this
0x140004f12  lea     r8, aWil; "wil"
0x140004f19  mov     r9d, eax; char *
0x140004f1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004f21  lea     rcx, [rsp+270h+var_238]
0x140004f26  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004f2b  jmp     short loc_140004F4C
0x140004f2d  mov     rcx, [rsp+270h+var_230]
0x140004f32  test    rcx, rcx
0x140004f35  jz      short loc_140004F7D
0x140004f37  mov     [rdi], rcx
0x140004f3a  mov     eax, [rcx]
0x140004f3c  inc     eax
0x140004f3e  mov     [rcx], eax
0x140004f40  lea     rcx, [rsp+270h+var_238]
0x140004f45  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004f4a  xor     ebx, ebx
0x140004f4c  lea     rcx, [rsp+270h+var_240]
0x140004f51  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004f56  mov     eax, ebx
0x140004f58  mov     rcx, [rbp+170h+var_10]
0x140004f5f  xor     rcx, rsp; StackCookie
0x140004f62  call    __security_check_cookie
0x140004f67  lea     r11, [rsp+270h+var_s0]
0x140004f6f  mov     rbx, [r11+20h]
0x140004f73  mov     rdi, [r11+28h]
0x140004f77  mov     rsp, r11
0x140004f7a  pop     rbp
0x140004f7b  retn
0x140004f7d  mov     r8, rdi
0x140004f80  lea     rdx, [rsp+270h+var_240]
0x140004f85  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004f8a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140004f8f  mov     ebx, eax
0x140004f91  test    eax, eax
0x140004f93  jns     short loc_140004F40
0x140004f95  mov     edx, 137h
0x140004f9a  jmp     loc_140004F0B
```
