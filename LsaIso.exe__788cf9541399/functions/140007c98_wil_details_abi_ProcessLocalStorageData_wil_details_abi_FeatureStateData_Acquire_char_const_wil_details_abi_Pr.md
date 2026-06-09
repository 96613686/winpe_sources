# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140007c98`
- end: `0x140007df7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140009428`

## callees

- `0x1400078d8`
- `0x1400078f4`
- `0x140007c98`
- `0x140009d88`
- `0x14000b058`
- `0x14000bedc`
- `0x14000c6c0`
- `0x14000cb30`
- `0x14000d584`
- `0x14000dc08`
- `0x140038d10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007cd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007cd0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140007d15`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140007d15`

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
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x140007c98  mov     [rsp-8+arg_10], rbx
0x140007c9d  mov     [rsp-8+arg_18], rdi
0x140007ca2  push    rbp
0x140007ca3  lea     rbp, [rsp-170h]
0x140007cab  sub     rsp, 270h
0x140007cb2  mov     rax, cs:__security_cookie
0x140007cb9  xor     rax, rsp
0x140007cbc  mov     [rbp+170h+var_10], rax
0x140007cc3  mov     rdi, rdx
0x140007cc6  mov     qword ptr [rdx], 0
0x140007ccd  mov     rbx, rcx
0x140007cd0  call    cs:__imp_GetCurrentProcessId
0x140007cd6  mov     [rsp+270h+var_248], rbx
0x140007cdb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140007ce2  mov     r9d, eax
0x140007ce5  mov     [rsp+270h+var_250], 130h; int
0x140007ced  mov     edx, 104h; unsigned __int64
0x140007cf2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007cf7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007cfc  mov     r9d, 1F0001h; dwDesiredAccess
0x140007d02  mov     [rsp+270h+var_240], 0
0x140007d0b  xor     r8d, r8d; dwFlags
0x140007d0e  lea     rdx, [rsp+270h+Name]; lpName
0x140007d13  xor     ecx, ecx; lpMutexAttributes
0x140007d15  call    cs:__imp_CreateMutexExW
0x140007d1b  mov     rdx, rax
0x140007d1e  lea     rcx, [rsp+270h+var_240]
0x140007d23  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140007d28  cmp     [rsp+270h+var_240], 0
0x140007d2e  jnz     short loc_140007D39
0x140007d30  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140007d35  mov     ebx, eax
0x140007d37  jmp     short loc_140007DA5
0x140007d39  lea     rdx, [rsp+270h+var_238]
0x140007d3e  lea     rcx, [rsp+270h+var_240]
0x140007d43  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140007d48  lea     rdx, [rsp+270h+var_230]; void **
0x140007d4d  mov     [rsp+270h+var_230], 0
0x140007d56  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007d5b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140007d60  mov     ebx, eax
0x140007d62  test    eax, eax
0x140007d64  jns     short loc_140007D86
0x140007d66  mov     edx, 12Eh; void *
0x140007d6b  mov     rcx, [rbp+178h]; this
0x140007d72  mov     r9d, eax; char *
0x140007d75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007d7a  lea     rcx, [rsp+270h+var_238]
0x140007d7f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007d84  jmp     short loc_140007DA5
0x140007d86  mov     rcx, [rsp+270h+var_230]
0x140007d8b  test    rcx, rcx
0x140007d8e  jz      short loc_140007DD5
0x140007d90  mov     [rdi], rcx
0x140007d93  mov     eax, [rcx]
0x140007d95  inc     eax
0x140007d97  mov     [rcx], eax
0x140007d99  lea     rcx, [rsp+270h+var_238]
0x140007d9e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007da3  xor     ebx, ebx
0x140007da5  lea     rcx, [rsp+270h+var_240]
0x140007daa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007daf  mov     eax, ebx
0x140007db1  mov     rcx, [rbp+170h+var_10]
0x140007db8  xor     rcx, rsp; StackCookie
0x140007dbb  call    __security_check_cookie
0x140007dc0  lea     r11, [rsp+270h+var_s0]
0x140007dc8  mov     rbx, [r11+20h]
0x140007dcc  mov     rdi, [r11+28h]
0x140007dd0  mov     rsp, r11
0x140007dd3  pop     rbp
0x140007dd4  retn
0x140007dd5  mov     r8, rdi
0x140007dd8  lea     rdx, [rsp+270h+var_240]
0x140007ddd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007de2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140007de7  mov     ebx, eax
0x140007de9  test    eax, eax
0x140007deb  jns     short loc_140007D99
0x140007ded  mov     edx, 137h
0x140007df2  jmp     loc_140007D6B
```
