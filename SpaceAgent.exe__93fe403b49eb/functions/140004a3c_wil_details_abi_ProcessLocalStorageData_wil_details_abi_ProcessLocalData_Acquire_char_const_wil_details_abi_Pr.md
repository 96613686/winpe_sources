# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140004a3c`
- end: `0x140004b9b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140005d2c`

## callees

- `0x1400046a8`
- `0x1400046c4`
- `0x140004a3c`
- `0x140005a58`
- `0x140006748`
- `0x1400079cc`
- `0x1400081d4`
- `0x140008b30`
- `0x140009314`
- `0x1400095fc`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x140004ab9`
- `KERNEL32!CreateMutexExW` at `0x140004ab9`
- `KERNEL32!GetCurrentProcessId` at `0x140004a74`
- `KERNEL32!GetCurrentProcessId` at `0x140004a74`

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
  _BYTE v14[8]; // [rsp+38h] [rbp-C8h] BYREF
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
      &v13,
      v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
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
0x140004a3c  mov     [rsp-8+arg_10], rbx
0x140004a41  mov     [rsp-8+arg_18], rdi
0x140004a46  push    rbp
0x140004a47  lea     rbp, [rsp-170h]
0x140004a4f  sub     rsp, 270h
0x140004a56  mov     rax, cs:__security_cookie
0x140004a5d  xor     rax, rsp
0x140004a60  mov     [rbp+170h+var_10], rax
0x140004a67  mov     rdi, rdx
0x140004a6a  mov     qword ptr [rdx], 0
0x140004a71  mov     rbx, rcx
0x140004a74  call    cs:__imp_GetCurrentProcessId
0x140004a7a  mov     [rsp+270h+var_248], rbx
0x140004a7f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004a86  mov     r9d, eax
0x140004a89  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140004a91  mov     edx, 104h; unsigned __int64
0x140004a96  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004a9b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004aa0  mov     r9d, 1F0001h; dwDesiredAccess
0x140004aa6  mov     [rsp+270h+var_240], 0
0x140004aaf  xor     r8d, r8d; dwFlags
0x140004ab2  lea     rdx, [rsp+270h+Name]; lpName
0x140004ab7  xor     ecx, ecx; lpMutexAttributes
0x140004ab9  call    cs:__imp_CreateMutexExW
0x140004abf  mov     rdx, rax
0x140004ac2  lea     rcx, [rsp+270h+var_240]
0x140004ac7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140004acc  cmp     [rsp+270h+var_240], 0
0x140004ad2  jnz     short loc_140004ADD
0x140004ad4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004ad9  mov     ebx, eax
0x140004adb  jmp     short loc_140004B49
0x140004add  lea     rdx, [rsp+270h+var_238]
0x140004ae2  lea     rcx, [rsp+270h+var_240]
0x140004ae7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140004aec  lea     rdx, [rsp+270h+var_230]; void **
0x140004af1  mov     [rsp+270h+var_230], 0
0x140004afa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004aff  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140004b04  mov     ebx, eax
0x140004b06  test    eax, eax
0x140004b08  jns     short loc_140004B2A
0x140004b0a  mov     edx, 12Eh; void *
0x140004b0f  mov     rcx, [rbp+178h]; this
0x140004b16  mov     r9d, eax; char *
0x140004b19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004b1e  lea     rcx, [rsp+270h+var_238]
0x140004b23  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004b28  jmp     short loc_140004B49
0x140004b2a  mov     rcx, [rsp+270h+var_230]
0x140004b2f  test    rcx, rcx
0x140004b32  jz      short loc_140004B79
0x140004b34  mov     [rdi], rcx
0x140004b37  mov     eax, [rcx]
0x140004b39  inc     eax
0x140004b3b  mov     [rcx], eax
0x140004b3d  lea     rcx, [rsp+270h+var_238]
0x140004b42  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004b47  xor     ebx, ebx
0x140004b49  lea     rcx, [rsp+270h+var_240]
0x140004b4e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004b53  mov     eax, ebx
0x140004b55  mov     rcx, [rbp+170h+var_10]
0x140004b5c  xor     rcx, rsp; StackCookie
0x140004b5f  call    __security_check_cookie
0x140004b64  lea     r11, [rsp+270h+var_s0]
0x140004b6c  mov     rbx, [r11+20h]
0x140004b70  mov     rdi, [r11+28h]
0x140004b74  mov     rsp, r11
0x140004b77  pop     rbp
0x140004b78  retn
0x140004b79  mov     r8, rdi
0x140004b7c  lea     rdx, [rsp+270h+var_240]
0x140004b81  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004b86  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140004b8b  mov     ebx, eax
0x140004b8d  test    eax, eax
0x140004b8f  jns     short loc_140004B3D
0x140004b91  mov     edx, 137h
0x140004b96  jmp     loc_140004B0F
```
