# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180022b14`
- end: `0x180022c72`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180023a14`

## callees

- `0x1800076b0`
- `0x180014f50`
- `0x180015200`
- `0x180015374`
- `0x180016020`
- `0x180016cec`
- `0x180022944`
- `0x180022960`
- `0x180022b14`
- `0x1800253c8`
- `0x180025b74`
- `0x180025d58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180022b90`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180022b90`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId_0; // eax
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
  CurrentProcessId_0 = GetCurrentProcessId_0();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId_0);
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
0x180022b14  mov     [rsp-8+arg_10], rbx
0x180022b19  mov     [rsp-8+arg_18], rdi
0x180022b1e  push    rbp
0x180022b1f  lea     rbp, [rsp-170h]
0x180022b27  sub     rsp, 270h
0x180022b2e  mov     rax, cs:__security_cookie
0x180022b35  xor     rax, rsp
0x180022b38  mov     [rbp+170h+var_10], rax
0x180022b3f  mov     rdi, rdx
0x180022b42  mov     qword ptr [rdx], 0
0x180022b49  mov     rbx, rcx
0x180022b4c  call    GetCurrentProcessId_0
0x180022b51  mov     r9d, eax
0x180022b54  mov     [rsp+270h+var_248], rbx
0x180022b59  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180022b60  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180022b68  mov     edx, 104h; unsigned __int64
0x180022b6d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180022b72  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022b77  mov     r9d, 1F0001h; dwDesiredAccess
0x180022b7d  mov     [rsp+270h+var_240], 0
0x180022b86  xor     r8d, r8d; dwFlags
0x180022b89  lea     rdx, [rsp+270h+Name]; lpName
0x180022b8e  xor     ecx, ecx; lpMutexAttributes
0x180022b90  call    cs:__imp_CreateMutexExW
0x180022b96  mov     rdx, rax
0x180022b99  lea     rcx, [rsp+270h+var_240]
0x180022b9e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180022ba3  cmp     [rsp+270h+var_240], 0
0x180022ba9  jnz     short loc_180022BB4
0x180022bab  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180022bb0  mov     ebx, eax
0x180022bb2  jmp     short loc_180022C20
0x180022bb4  lea     rdx, [rsp+270h+var_238]
0x180022bb9  lea     rcx, [rsp+270h+var_240]
0x180022bbe  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180022bc3  lea     rdx, [rsp+270h+var_230]; void **
0x180022bc8  mov     [rsp+270h+var_230], 0
0x180022bd1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180022bd6  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180022bdb  mov     ebx, eax
0x180022bdd  test    eax, eax
0x180022bdf  jns     short loc_180022C01
0x180022be1  mov     edx, 12Eh; void *
0x180022be6  mov     rcx, [rbp+178h]; this
0x180022bed  mov     r9d, eax; char *
0x180022bf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022bf5  lea     rcx, [rsp+270h+var_238]
0x180022bfa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022bff  jmp     short loc_180022C20
0x180022c01  mov     rcx, [rsp+270h+var_230]
0x180022c06  test    rcx, rcx
0x180022c09  jz      short loc_180022C50
0x180022c0b  mov     [rdi], rcx
0x180022c0e  mov     eax, [rcx]
0x180022c10  inc     eax
0x180022c12  mov     [rcx], eax
0x180022c14  lea     rcx, [rsp+270h+var_238]
0x180022c19  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022c1e  xor     ebx, ebx
0x180022c20  lea     rcx, [rsp+270h+var_240]
0x180022c25  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022c2a  mov     eax, ebx
0x180022c2c  mov     rcx, [rbp+170h+var_10]
0x180022c33  xor     rcx, rsp; StackCookie
0x180022c36  call    __security_check_cookie
0x180022c3b  lea     r11, [rsp+270h+var_s0]
0x180022c43  mov     rbx, [r11+20h]
0x180022c47  mov     rdi, [r11+28h]
0x180022c4b  mov     rsp, r11
0x180022c4e  pop     rbp
0x180022c4f  retn
0x180022c50  mov     r8, rdi
0x180022c53  lea     rdx, [rsp+270h+var_240]
0x180022c58  lea     rcx, [rsp+270h+Name]
0x180022c5d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180022c62  mov     ebx, eax
0x180022c64  test    eax, eax
0x180022c66  jns     short loc_180022C14
0x180022c68  mov     edx, 137h
0x180022c6d  jmp     loc_180022BE6
```
