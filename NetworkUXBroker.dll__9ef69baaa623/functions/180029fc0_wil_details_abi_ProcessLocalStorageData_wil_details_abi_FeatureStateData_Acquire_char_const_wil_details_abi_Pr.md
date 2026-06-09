# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180029fc0`
- end: `0x18002a126`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002d2a4`

## callees

- `0x180002520`
- `0x1800067ac`
- `0x18000e768`
- `0x1800207ac`
- `0x1800207c8`
- `0x180020cac`
- `0x180021728`
- `0x180021988`
- `0x180021bf8`
- `0x180029fc0`
- `0x18002da64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029ff8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029ff8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002a03d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002a03d`

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
0x180029fc0  mov     [rsp-8+arg_10], rbx
0x180029fc5  mov     [rsp-8+arg_18], rdi
0x180029fca  push    rbp
0x180029fcb  lea     rbp, [rsp-170h]
0x180029fd3  sub     rsp, 270h
0x180029fda  mov     rax, cs:__security_cookie
0x180029fe1  xor     rax, rsp
0x180029fe4  mov     [rbp+170h+var_10], rax
0x180029feb  mov     rdi, rdx
0x180029fee  mov     qword ptr [rdx], 0
0x180029ff5  mov     rbx, rcx
0x180029ff8  call    cs:__imp_GetCurrentProcessId
0x180029ffe  mov     [rsp+270h+var_248], rbx
0x18002a003  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002a00a  mov     r9d, eax
0x18002a00d  mov     [rsp+270h+var_250], 130h; int
0x18002a015  mov     edx, 104h; unsigned __int64
0x18002a01a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002a01f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a024  mov     r9d, 1F0001h; dwDesiredAccess
0x18002a02a  mov     [rsp+270h+var_240], 0
0x18002a033  xor     r8d, r8d; dwFlags
0x18002a036  lea     rdx, [rsp+270h+Name]; lpName
0x18002a03b  xor     ecx, ecx; lpMutexAttributes
0x18002a03d  call    cs:__imp_CreateMutexExW
0x18002a043  mov     rdx, rax
0x18002a046  lea     rcx, [rsp+270h+var_240]
0x18002a04b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002a050  cmp     [rsp+270h+var_240], 0
0x18002a056  jnz     short loc_18002A061
0x18002a058  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002a05d  mov     ebx, eax
0x18002a05f  jmp     short loc_18002A0D4
0x18002a061  lea     rdx, [rsp+270h+var_238]
0x18002a066  lea     rcx, [rsp+270h+var_240]
0x18002a06b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002a070  lea     rdx, [rsp+270h+var_230]; void **
0x18002a075  mov     [rsp+270h+var_230], 0
0x18002a07e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002a083  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18002a088  mov     ebx, eax
0x18002a08a  test    eax, eax
0x18002a08c  jns     short loc_18002A0B5
0x18002a08e  mov     edx, 12Eh; void *
0x18002a093  mov     rcx, [rbp+178h]; this
0x18002a09a  lea     r8, aWil; "wil"
0x18002a0a1  mov     r9d, eax; char *
0x18002a0a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a0a9  lea     rcx, [rsp+270h+var_238]
0x18002a0ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a0b3  jmp     short loc_18002A0D4
0x18002a0b5  mov     rcx, [rsp+270h+var_230]
0x18002a0ba  test    rcx, rcx
0x18002a0bd  jz      short loc_18002A104
0x18002a0bf  mov     [rdi], rcx
0x18002a0c2  mov     eax, [rcx]
0x18002a0c4  inc     eax
0x18002a0c6  mov     [rcx], eax
0x18002a0c8  lea     rcx, [rsp+270h+var_238]
0x18002a0cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a0d2  xor     ebx, ebx
0x18002a0d4  lea     rcx, [rsp+270h+var_240]
0x18002a0d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a0de  mov     eax, ebx
0x18002a0e0  mov     rcx, [rbp+170h+var_10]
0x18002a0e7  xor     rcx, rsp; StackCookie
0x18002a0ea  call    __security_check_cookie
0x18002a0ef  lea     r11, [rsp+270h+var_s0]
0x18002a0f7  mov     rbx, [r11+20h]
0x18002a0fb  mov     rdi, [r11+28h]
0x18002a0ff  mov     rsp, r11
0x18002a102  pop     rbp
0x18002a103  retn
0x18002a104  mov     r8, rdi
0x18002a107  lea     rdx, [rsp+270h+var_240]
0x18002a10c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002a111  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002a116  mov     ebx, eax
0x18002a118  test    eax, eax
0x18002a11a  jns     short loc_18002A0C8
0x18002a11c  mov     edx, 137h
0x18002a121  jmp     loc_18002A093
```
