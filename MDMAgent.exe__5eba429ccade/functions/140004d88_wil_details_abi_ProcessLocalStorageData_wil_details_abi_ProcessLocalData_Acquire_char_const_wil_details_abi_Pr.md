# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140004d88`
- end: `0x140004eee`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140005ab4`

## callees

- `0x140002930`
- `0x140004b2c`
- `0x140004b48`
- `0x140004d88`
- `0x1400056c8`
- `0x1400062e8`
- `0x140006984`
- `0x140007368`
- `0x1400074dc`
- `0x140007a30`
- `0x140007b88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004e05`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004e05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004dc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004dc0`

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
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x140004d88  mov     [rsp-8+arg_10], rbx
0x140004d8d  mov     [rsp-8+arg_18], rdi
0x140004d92  push    rbp
0x140004d93  lea     rbp, [rsp-170h]
0x140004d9b  sub     rsp, 270h
0x140004da2  mov     rax, cs:__security_cookie
0x140004da9  xor     rax, rsp
0x140004dac  mov     [rbp+170h+var_10], rax
0x140004db3  mov     rdi, rdx
0x140004db6  mov     qword ptr [rdx], 0
0x140004dbd  mov     rbx, rcx
0x140004dc0  call    cs:__imp_GetCurrentProcessId
0x140004dc6  mov     [rsp+270h+var_248], rbx
0x140004dcb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004dd2  mov     r9d, eax
0x140004dd5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140004ddd  mov     edx, 104h; unsigned __int64
0x140004de2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004de7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004dec  mov     r9d, 1F0001h; dwDesiredAccess
0x140004df2  mov     [rsp+270h+var_240], 0
0x140004dfb  xor     r8d, r8d; dwFlags
0x140004dfe  lea     rdx, [rsp+270h+Name]; lpName
0x140004e03  xor     ecx, ecx; lpMutexAttributes
0x140004e05  call    cs:__imp_CreateMutexExW
0x140004e0b  mov     rdx, rax
0x140004e0e  lea     rcx, [rsp+270h+var_240]
0x140004e13  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140004e18  cmp     [rsp+270h+var_240], 0
0x140004e1e  jnz     short loc_140004E29
0x140004e20  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004e25  mov     ebx, eax
0x140004e27  jmp     short loc_140004E9C
0x140004e29  lea     rdx, [rsp+270h+var_238]
0x140004e2e  lea     rcx, [rsp+270h+var_240]
0x140004e33  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140004e38  lea     rdx, [rsp+270h+var_230]; void **
0x140004e3d  mov     [rsp+270h+var_230], 0
0x140004e46  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004e4b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140004e50  mov     ebx, eax
0x140004e52  test    eax, eax
0x140004e54  jns     short loc_140004E7D
0x140004e56  mov     edx, 12Eh; void *
0x140004e5b  mov     rcx, [rbp+178h]; this
0x140004e62  lea     r8, aWil; "wil"
0x140004e69  mov     r9d, eax; char *
0x140004e6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004e71  lea     rcx, [rsp+270h+var_238]
0x140004e76  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004e7b  jmp     short loc_140004E9C
0x140004e7d  mov     rcx, [rsp+270h+var_230]
0x140004e82  test    rcx, rcx
0x140004e85  jz      short loc_140004ECC
0x140004e87  mov     [rdi], rcx
0x140004e8a  mov     eax, [rcx]
0x140004e8c  inc     eax
0x140004e8e  mov     [rcx], eax
0x140004e90  lea     rcx, [rsp+270h+var_238]
0x140004e95  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004e9a  xor     ebx, ebx
0x140004e9c  lea     rcx, [rsp+270h+var_240]
0x140004ea1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004ea6  mov     eax, ebx
0x140004ea8  mov     rcx, [rbp+170h+var_10]
0x140004eaf  xor     rcx, rsp; StackCookie
0x140004eb2  call    __security_check_cookie
0x140004eb7  lea     r11, [rsp+270h+var_s0]
0x140004ebf  mov     rbx, [r11+20h]
0x140004ec3  mov     rdi, [r11+28h]
0x140004ec7  mov     rsp, r11
0x140004eca  pop     rbp
0x140004ecb  retn
0x140004ecc  mov     r8, rdi
0x140004ecf  lea     rdx, [rsp+270h+var_240]
0x140004ed4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004ed9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140004ede  mov     ebx, eax
0x140004ee0  test    eax, eax
0x140004ee2  jns     short loc_140004E90
0x140004ee4  mov     edx, 137h
0x140004ee9  jmp     loc_140004E5B
```
