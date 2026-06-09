# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140007b30`
- end: `0x140007c8f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000a05c`

## callees

- `0x1400078d8`
- `0x1400078f4`
- `0x140007b30`
- `0x140009d88`
- `0x14000af14`
- `0x14000bedc`
- `0x14000c6c0`
- `0x14000cb30`
- `0x14000d584`
- `0x14000dc08`
- `0x140038d10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007b68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007b68`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140007bad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140007bad`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x140007b30  mov     [rsp-8+arg_10], rbx
0x140007b35  mov     [rsp-8+arg_18], rdi
0x140007b3a  push    rbp
0x140007b3b  lea     rbp, [rsp-170h]
0x140007b43  sub     rsp, 270h
0x140007b4a  mov     rax, cs:__security_cookie
0x140007b51  xor     rax, rsp
0x140007b54  mov     [rbp+170h+var_10], rax
0x140007b5b  mov     rdi, rdx
0x140007b5e  mov     qword ptr [rdx], 0
0x140007b65  mov     rbx, rcx
0x140007b68  call    cs:__imp_GetCurrentProcessId
0x140007b6e  mov     [rsp+270h+var_248], rbx
0x140007b73  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140007b7a  mov     r9d, eax
0x140007b7d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140007b85  mov     edx, 104h; unsigned __int64
0x140007b8a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007b8f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007b94  mov     r9d, 1F0001h; dwDesiredAccess
0x140007b9a  mov     [rsp+270h+var_240], 0
0x140007ba3  xor     r8d, r8d; dwFlags
0x140007ba6  lea     rdx, [rsp+270h+Name]; lpName
0x140007bab  xor     ecx, ecx; lpMutexAttributes
0x140007bad  call    cs:__imp_CreateMutexExW
0x140007bb3  mov     rdx, rax
0x140007bb6  lea     rcx, [rsp+270h+var_240]
0x140007bbb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140007bc0  cmp     [rsp+270h+var_240], 0
0x140007bc6  jnz     short loc_140007BD1
0x140007bc8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140007bcd  mov     ebx, eax
0x140007bcf  jmp     short loc_140007C3D
0x140007bd1  lea     rdx, [rsp+270h+var_238]
0x140007bd6  lea     rcx, [rsp+270h+var_240]
0x140007bdb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140007be0  lea     rdx, [rsp+270h+var_230]; void **
0x140007be5  mov     [rsp+270h+var_230], 0
0x140007bee  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007bf3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140007bf8  mov     ebx, eax
0x140007bfa  test    eax, eax
0x140007bfc  jns     short loc_140007C1E
0x140007bfe  mov     edx, 12Eh; void *
0x140007c03  mov     rcx, [rbp+178h]; this
0x140007c0a  mov     r9d, eax; char *
0x140007c0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007c12  lea     rcx, [rsp+270h+var_238]
0x140007c17  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007c1c  jmp     short loc_140007C3D
0x140007c1e  mov     rcx, [rsp+270h+var_230]
0x140007c23  test    rcx, rcx
0x140007c26  jz      short loc_140007C6D
0x140007c28  mov     [rdi], rcx
0x140007c2b  mov     eax, [rcx]
0x140007c2d  inc     eax
0x140007c2f  mov     [rcx], eax
0x140007c31  lea     rcx, [rsp+270h+var_238]
0x140007c36  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007c3b  xor     ebx, ebx
0x140007c3d  lea     rcx, [rsp+270h+var_240]
0x140007c42  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007c47  mov     eax, ebx
0x140007c49  mov     rcx, [rbp+170h+var_10]
0x140007c50  xor     rcx, rsp; StackCookie
0x140007c53  call    __security_check_cookie
0x140007c58  lea     r11, [rsp+270h+var_s0]
0x140007c60  mov     rbx, [r11+20h]
0x140007c64  mov     rdi, [r11+28h]
0x140007c68  mov     rsp, r11
0x140007c6b  pop     rbp
0x140007c6c  retn
0x140007c6d  mov     r8, rdi
0x140007c70  lea     rdx, [rsp+270h+var_240]
0x140007c75  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007c7a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140007c7f  mov     ebx, eax
0x140007c81  test    eax, eax
0x140007c83  jns     short loc_140007C31
0x140007c85  mov     edx, 137h
0x140007c8a  jmp     loc_140007C03
```
