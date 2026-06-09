# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140006d78`
- end: `0x140006ede`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140007ecc`

## callees

- `0x1400030a0`
- `0x140006890`
- `0x1400068ac`
- `0x140006d78`
- `0x140007bb0`
- `0x1400088ec`
- `0x140009f14`
- `0x14000a684`
- `0x14000abcc`
- `0x14000b644`
- `0x14000bc5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140006df5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140006df5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140006db0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140006db0`

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
0x140006d78  mov     [rsp-8+arg_10], rbx
0x140006d7d  mov     [rsp-8+arg_18], rdi
0x140006d82  push    rbp
0x140006d83  lea     rbp, [rsp-170h]
0x140006d8b  sub     rsp, 270h
0x140006d92  mov     rax, cs:__security_cookie
0x140006d99  xor     rax, rsp
0x140006d9c  mov     [rbp+170h+var_10], rax
0x140006da3  mov     rdi, rdx
0x140006da6  mov     qword ptr [rdx], 0
0x140006dad  mov     rbx, rcx
0x140006db0  call    cs:__imp_GetCurrentProcessId
0x140006db6  mov     [rsp+270h+var_248], rbx
0x140006dbb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140006dc2  mov     r9d, eax
0x140006dc5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140006dcd  mov     edx, 104h; unsigned __int64
0x140006dd2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140006dd7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140006ddc  mov     r9d, 1F0001h; dwDesiredAccess
0x140006de2  mov     [rsp+270h+var_240], 0
0x140006deb  xor     r8d, r8d; dwFlags
0x140006dee  lea     rdx, [rsp+270h+Name]; lpName
0x140006df3  xor     ecx, ecx; lpMutexAttributes
0x140006df5  call    cs:__imp_CreateMutexExW
0x140006dfb  mov     rdx, rax
0x140006dfe  lea     rcx, [rsp+270h+var_240]
0x140006e03  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140006e08  cmp     [rsp+270h+var_240], 0
0x140006e0e  jnz     short loc_140006E19
0x140006e10  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140006e15  mov     ebx, eax
0x140006e17  jmp     short loc_140006E8C
0x140006e19  lea     rdx, [rsp+270h+var_238]
0x140006e1e  lea     rcx, [rsp+270h+var_240]
0x140006e23  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140006e28  lea     rdx, [rsp+270h+var_230]; void **
0x140006e2d  mov     [rsp+270h+var_230], 0
0x140006e36  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140006e3b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x140006e40  mov     ebx, eax
0x140006e42  test    eax, eax
0x140006e44  jns     short loc_140006E6D
0x140006e46  mov     edx, 12Eh; void *
0x140006e4b  mov     rcx, [rbp+178h]; this
0x140006e52  lea     r8, aWil; "wil"
0x140006e59  mov     r9d, eax; char *
0x140006e5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006e61  lea     rcx, [rsp+270h+var_238]
0x140006e66  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006e6b  jmp     short loc_140006E8C
0x140006e6d  mov     rcx, [rsp+270h+var_230]
0x140006e72  test    rcx, rcx
0x140006e75  jz      short loc_140006EBC
0x140006e77  mov     [rdi], rcx
0x140006e7a  mov     eax, [rcx]
0x140006e7c  inc     eax
0x140006e7e  mov     [rcx], eax
0x140006e80  lea     rcx, [rsp+270h+var_238]
0x140006e85  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006e8a  xor     ebx, ebx
0x140006e8c  lea     rcx, [rsp+270h+var_240]
0x140006e91  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006e96  mov     eax, ebx
0x140006e98  mov     rcx, [rbp+170h+var_10]
0x140006e9f  xor     rcx, rsp; StackCookie
0x140006ea2  call    __security_check_cookie
0x140006ea7  lea     r11, [rsp+270h+var_s0]
0x140006eaf  mov     rbx, [r11+20h]
0x140006eb3  mov     rdi, [r11+28h]
0x140006eb7  mov     rsp, r11
0x140006eba  pop     rbp
0x140006ebb  retn
0x140006ebc  mov     r8, rdi
0x140006ebf  lea     rdx, [rsp+270h+var_240]
0x140006ec4  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140006ec9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140006ece  mov     ebx, eax
0x140006ed0  test    eax, eax
0x140006ed2  jns     short loc_140006E80
0x140006ed4  mov     edx, 137h
0x140006ed9  jmp     loc_140006E4B
```
