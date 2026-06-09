# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180007cb0`
- end: `0x180007e23`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000a9b0`

## callees

- `0x180001c60`
- `0x1800051d8`
- `0x1800076b8`
- `0x1800076d8`
- `0x180007cb0`
- `0x18000a680`
- `0x18000b4d0`
- `0x18000c938`
- `0x180010ad8`
- `0x1800114f4`
- `0x1800118d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007d33`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007d33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007ce8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007ce8`

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
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x180007cb0  mov     [rsp-8+arg_10], rbx
0x180007cb5  mov     [rsp-8+arg_18], rdi
0x180007cba  push    rbp
0x180007cbb  lea     rbp, [rsp-170h]
0x180007cc3  sub     rsp, 270h
0x180007cca  mov     rax, cs:__security_cookie
0x180007cd1  xor     rax, rsp
0x180007cd4  mov     [rbp+170h+var_10], rax
0x180007cdb  mov     rdi, rdx
0x180007cde  mov     qword ptr [rdx], 0
0x180007ce5  mov     rbx, rcx
0x180007ce8  call    cs:__imp_GetCurrentProcessId
0x180007cef  nop     dword ptr [rax+rax+00h]
0x180007cf4  mov     [rsp+270h+var_248], rbx
0x180007cf9  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007d00  mov     r9d, eax
0x180007d03  mov     [rsp+270h+var_250], 130h; int
0x180007d0b  mov     edx, 104h; unsigned __int64
0x180007d10  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007d15  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007d1a  mov     r9d, 1F0001h; dwDesiredAccess
0x180007d20  mov     [rsp+270h+var_240], 0
0x180007d29  xor     r8d, r8d; dwFlags
0x180007d2c  lea     rdx, [rsp+270h+Name]; lpName
0x180007d31  xor     ecx, ecx; lpMutexAttributes
0x180007d33  call    cs:__imp_CreateMutexExW
0x180007d3a  nop     dword ptr [rax+rax+00h]
0x180007d3f  mov     rdx, rax
0x180007d42  lea     rcx, [rsp+270h+var_240]
0x180007d47  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180007d4c  cmp     [rsp+270h+var_240], 0
0x180007d52  jnz     short loc_180007D5D
0x180007d54  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007d59  mov     ebx, eax
0x180007d5b  jmp     short loc_180007DD0
0x180007d5d  lea     rdx, [rsp+270h+var_238]
0x180007d62  lea     rcx, [rsp+270h+var_240]
0x180007d67  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180007d6c  lea     rdx, [rsp+270h+var_230]; void **
0x180007d71  mov     [rsp+270h+var_230], 0
0x180007d7a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007d7f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180007d84  mov     ebx, eax
0x180007d86  test    eax, eax
0x180007d88  jns     short loc_180007DB1
0x180007d8a  mov     edx, 12Eh; void *
0x180007d8f  mov     rcx, [rbp+178h]; this
0x180007d96  lea     r8, aWil; "wil"
0x180007d9d  mov     r9d, eax; char *
0x180007da0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007da5  lea     rcx, [rsp+270h+var_238]
0x180007daa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007daf  jmp     short loc_180007DD0
0x180007db1  mov     rcx, [rsp+270h+var_230]
0x180007db6  test    rcx, rcx
0x180007db9  jz      short loc_180007E01
0x180007dbb  mov     [rdi], rcx
0x180007dbe  mov     eax, [rcx]
0x180007dc0  inc     eax
0x180007dc2  mov     [rcx], eax
0x180007dc4  lea     rcx, [rsp+270h+var_238]
0x180007dc9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007dce  xor     ebx, ebx
0x180007dd0  lea     rcx, [rsp+270h+var_240]
0x180007dd5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007dda  mov     eax, ebx
0x180007ddc  mov     rcx, [rbp+170h+var_10]
0x180007de3  xor     rcx, rsp; StackCookie
0x180007de6  call    __security_check_cookie
0x180007deb  lea     r11, [rsp+270h+var_s0]
0x180007df3  mov     rbx, [r11+20h]
0x180007df7  mov     rdi, [r11+28h]
0x180007dfb  mov     rsp, r11
0x180007dfe  pop     rbp
0x180007dff  retn
0x180007e01  mov     r8, rdi
0x180007e04  lea     rdx, [rsp+270h+var_240]
0x180007e09  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007e0e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180007e13  mov     ebx, eax
0x180007e15  test    eax, eax
0x180007e17  jns     short loc_180007DC4
0x180007e19  mov     edx, 137h
0x180007e1e  jmp     loc_180007D8F
```
