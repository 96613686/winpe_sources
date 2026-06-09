# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001f5fc`
- end: `0x18001f762`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180022b60`

## callees

- `0x1800037d0`
- `0x18001b3f0`
- `0x18001bbe0`
- `0x18001f1e8`
- `0x18001f204`
- `0x18001f5fc`
- `0x1800236fc`
- `0x180025a34`
- `0x1800278fc`
- `0x180028c04`
- `0x18002a20c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f634`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f634`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001f679`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001f679`

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
0x18001f5fc  mov     [rsp-8+arg_10], rbx
0x18001f601  mov     [rsp-8+arg_18], rdi
0x18001f606  push    rbp
0x18001f607  lea     rbp, [rsp-170h]
0x18001f60f  sub     rsp, 270h
0x18001f616  mov     rax, cs:__security_cookie
0x18001f61d  xor     rax, rsp
0x18001f620  mov     [rbp+170h+var_10], rax
0x18001f627  mov     rdi, rdx
0x18001f62a  mov     qword ptr [rdx], 0
0x18001f631  mov     rbx, rcx
0x18001f634  call    cs:__imp_GetCurrentProcessId
0x18001f63a  mov     [rsp+270h+var_248], rbx
0x18001f63f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001f646  mov     r9d, eax
0x18001f649  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001f651  mov     edx, 104h; unsigned __int64
0x18001f656  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001f65b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f660  mov     r9d, 1F0001h; dwDesiredAccess
0x18001f666  mov     [rsp+270h+var_240], 0
0x18001f66f  xor     r8d, r8d; dwFlags
0x18001f672  lea     rdx, [rsp+270h+Name]; lpName
0x18001f677  xor     ecx, ecx; lpMutexAttributes
0x18001f679  call    cs:__imp_CreateMutexExW
0x18001f67f  mov     rdx, rax
0x18001f682  lea     rcx, [rsp+270h+var_240]
0x18001f687  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001f68c  cmp     [rsp+270h+var_240], 0
0x18001f692  jnz     short loc_18001F69D
0x18001f694  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001f699  mov     ebx, eax
0x18001f69b  jmp     short loc_18001F710
0x18001f69d  lea     rdx, [rsp+270h+var_238]
0x18001f6a2  lea     rcx, [rsp+270h+var_240]
0x18001f6a7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001f6ac  lea     rdx, [rsp+270h+var_230]; void **
0x18001f6b1  mov     [rsp+270h+var_230], 0
0x18001f6ba  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001f6bf  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001f6c4  mov     ebx, eax
0x18001f6c6  test    eax, eax
0x18001f6c8  jns     short loc_18001F6F1
0x18001f6ca  mov     edx, 12Eh; void *
0x18001f6cf  mov     rcx, [rbp+178h]; this
0x18001f6d6  lea     r8, aWil; "wil"
0x18001f6dd  mov     r9d, eax; char *
0x18001f6e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f6e5  lea     rcx, [rsp+270h+var_238]
0x18001f6ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f6ef  jmp     short loc_18001F710
0x18001f6f1  mov     rcx, [rsp+270h+var_230]
0x18001f6f6  test    rcx, rcx
0x18001f6f9  jz      short loc_18001F740
0x18001f6fb  mov     [rdi], rcx
0x18001f6fe  mov     eax, [rcx]
0x18001f700  inc     eax
0x18001f702  mov     [rcx], eax
0x18001f704  lea     rcx, [rsp+270h+var_238]
0x18001f709  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f70e  xor     ebx, ebx
0x18001f710  lea     rcx, [rsp+270h+var_240]
0x18001f715  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f71a  mov     eax, ebx
0x18001f71c  mov     rcx, [rbp+170h+var_10]
0x18001f723  xor     rcx, rsp; StackCookie
0x18001f726  call    __security_check_cookie
0x18001f72b  lea     r11, [rsp+270h+var_s0]
0x18001f733  mov     rbx, [r11+20h]
0x18001f737  mov     rdi, [r11+28h]
0x18001f73b  mov     rsp, r11
0x18001f73e  pop     rbp
0x18001f73f  retn
0x18001f740  mov     r8, rdi
0x18001f743  lea     rdx, [rsp+270h+var_240]
0x18001f748  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001f74d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001f752  mov     ebx, eax
0x18001f754  test    eax, eax
0x18001f756  jns     short loc_18001F704
0x18001f758  mov     edx, 137h
0x18001f75d  jmp     loc_18001F6CF
```
