# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009e08`
- end: `0x180009f6e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000a980`

## callees

- `0x180006640`
- `0x180009cb8`
- `0x180009cd4`
- `0x180009e08`
- `0x18000a698`
- `0x18000b0b0`
- `0x18000b6b4`
- `0x18000bc4c`
- `0x18000be08`
- `0x18000c290`
- `0x18000c398`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009e85`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009e85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009e40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009e40`

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
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
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
0x180009e08  mov     [rsp-8+arg_10], rbx
0x180009e0d  mov     [rsp-8+arg_18], rdi
0x180009e12  push    rbp
0x180009e13  lea     rbp, [rsp-170h]
0x180009e1b  sub     rsp, 270h
0x180009e22  mov     rax, cs:__security_cookie
0x180009e29  xor     rax, rsp
0x180009e2c  mov     [rbp+170h+var_10], rax
0x180009e33  mov     rdi, rdx
0x180009e36  mov     qword ptr [rdx], 0
0x180009e3d  mov     rbx, rcx
0x180009e40  call    cs:__imp_GetCurrentProcessId
0x180009e46  mov     [rsp+270h+var_248], rbx
0x180009e4b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009e52  mov     r9d, eax
0x180009e55  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180009e5d  mov     edx, 104h; unsigned __int64
0x180009e62  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009e67  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009e6c  mov     r9d, 1F0001h; dwDesiredAccess
0x180009e72  mov     [rsp+270h+var_240], 0
0x180009e7b  xor     r8d, r8d; dwFlags
0x180009e7e  lea     rdx, [rsp+270h+Name]; lpName
0x180009e83  xor     ecx, ecx; lpMutexAttributes
0x180009e85  call    cs:__imp_CreateMutexExW
0x180009e8b  mov     rdx, rax
0x180009e8e  lea     rcx, [rsp+270h+var_240]
0x180009e93  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009e98  cmp     [rsp+270h+var_240], 0
0x180009e9e  jnz     short loc_180009EA9
0x180009ea0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009ea5  mov     ebx, eax
0x180009ea7  jmp     short loc_180009F1C
0x180009ea9  lea     rdx, [rsp+270h+var_238]
0x180009eae  lea     rcx, [rsp+270h+var_240]
0x180009eb3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180009eb8  lea     rdx, [rsp+270h+var_230]; void **
0x180009ebd  mov     [rsp+270h+var_230], 0
0x180009ec6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009ecb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180009ed0  mov     ebx, eax
0x180009ed2  test    eax, eax
0x180009ed4  jns     short loc_180009EFD
0x180009ed6  mov     edx, 12Eh; void *
0x180009edb  mov     rcx, [rbp+178h]; this
0x180009ee2  lea     r8, aWil; "wil"
0x180009ee9  mov     r9d, eax; char *
0x180009eec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ef1  lea     rcx, [rsp+270h+var_238]
0x180009ef6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009efb  jmp     short loc_180009F1C
0x180009efd  mov     rcx, [rsp+270h+var_230]
0x180009f02  test    rcx, rcx
0x180009f05  jz      short loc_180009F4C
0x180009f07  mov     [rdi], rcx
0x180009f0a  mov     eax, [rcx]
0x180009f0c  inc     eax
0x180009f0e  mov     [rcx], eax
0x180009f10  lea     rcx, [rsp+270h+var_238]
0x180009f15  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009f1a  xor     ebx, ebx
0x180009f1c  lea     rcx, [rsp+270h+var_240]
0x180009f21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009f26  mov     eax, ebx
0x180009f28  mov     rcx, [rbp+170h+var_10]
0x180009f2f  xor     rcx, rsp; StackCookie
0x180009f32  call    __security_check_cookie
0x180009f37  lea     r11, [rsp+270h+var_s0]
0x180009f3f  mov     rbx, [r11+20h]
0x180009f43  mov     rdi, [r11+28h]
0x180009f47  mov     rsp, r11
0x180009f4a  pop     rbp
0x180009f4b  retn
0x180009f4c  mov     r8, rdi
0x180009f4f  lea     rdx, [rsp+270h+var_240]
0x180009f54  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009f59  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180009f5e  mov     ebx, eax
0x180009f60  test    eax, eax
0x180009f62  jns     short loc_180009F10
0x180009f64  mov     edx, 137h
0x180009f69  jmp     loc_180009EDB
```
