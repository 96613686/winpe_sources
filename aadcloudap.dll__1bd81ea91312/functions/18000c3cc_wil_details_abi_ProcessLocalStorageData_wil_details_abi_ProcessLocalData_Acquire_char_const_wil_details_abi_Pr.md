# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000c3cc`
- end: `0x18000c52e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180015f18`

## callees

- `0x180003c20`
- `0x18000a200`
- `0x18000a21c`
- `0x18000c3cc`
- `0x180015ba8`
- `0x180016a6c`
- `0x18001901c`
- `0x180019868`
- `0x180019e04`
- `0x18001a91c`
- `0x18001bb28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c449`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c449`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c404`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c404`

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
0x18000c3cc  mov     [rsp-8+arg_10], rbx
0x18000c3d1  mov     [rsp-8+arg_18], rdi
0x18000c3d6  push    rbp
0x18000c3d7  lea     rbp, [rsp-170h]
0x18000c3df  sub     rsp, 270h
0x18000c3e6  mov     rax, cs:__security_cookie
0x18000c3ed  xor     rax, rsp
0x18000c3f0  mov     [rbp+170h+var_10], rax
0x18000c3f7  mov     rdi, rdx
0x18000c3fa  mov     rbx, rcx
0x18000c3fd  mov     qword ptr [rdx], 0
0x18000c404  call    cs:__imp_GetCurrentProcessId
0x18000c40a  mov     r9d, eax
0x18000c40d  mov     [rsp+270h+var_248], rbx
0x18000c412  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000c41a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000c421  mov     edx, 104h; unsigned __int64
0x18000c426  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c42b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c430  mov     [rsp+270h+var_240], 0
0x18000c439  mov     r9d, 1F0001h; dwDesiredAccess
0x18000c43f  xor     r8d, r8d; dwFlags
0x18000c442  lea     rdx, [rsp+270h+Name]; lpName
0x18000c447  xor     ecx, ecx; lpMutexAttributes
0x18000c449  call    cs:__imp_CreateMutexExW
0x18000c44f  mov     rdx, rax
0x18000c452  lea     rcx, [rsp+270h+var_240]
0x18000c457  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000c45c  cmp     [rsp+270h+var_240], 0
0x18000c462  jnz     short loc_18000C46D
0x18000c464  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c469  mov     ebx, eax
0x18000c46b  jmp     short loc_18000C4DB
0x18000c46d  lea     rdx, [rsp+270h+var_238]
0x18000c472  lea     rcx, [rsp+270h+var_240]
0x18000c477  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000c47c  nop
0x18000c47d  mov     [rsp+270h+var_230], 0
0x18000c486  lea     rdx, [rsp+270h+var_230]; void **
0x18000c48b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c490  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000c495  mov     ebx, eax
0x18000c497  test    eax, eax
0x18000c499  jns     short loc_18000C4BC
0x18000c49b  mov     edx, 12Eh; void *
0x18000c4a0  mov     r9d, eax; char *
0x18000c4a3  mov     rcx, [rbp+178h]; this
0x18000c4aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c4af  nop
0x18000c4b0  lea     rcx, [rsp+270h+var_238]
0x18000c4b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c4ba  jmp     short loc_18000C4DB
0x18000c4bc  mov     rcx, [rsp+270h+var_230]
0x18000c4c1  test    rcx, rcx
0x18000c4c4  jz      short loc_18000C50B
0x18000c4c6  mov     [rdi], rcx
0x18000c4c9  mov     eax, [rcx]
0x18000c4cb  inc     eax
0x18000c4cd  mov     [rcx], eax
0x18000c4cf  lea     rcx, [rsp+270h+var_238]
0x18000c4d4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c4d9  xor     ebx, ebx
0x18000c4db  lea     rcx, [rsp+270h+var_240]
0x18000c4e0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c4e5  mov     eax, ebx
0x18000c4e7  mov     rcx, [rbp+170h+var_10]
0x18000c4ee  xor     rcx, rsp; StackCookie
0x18000c4f1  call    __security_check_cookie
0x18000c4f6  lea     r11, [rsp+270h+var_s0]
0x18000c4fe  mov     rbx, [r11+20h]
0x18000c502  mov     rdi, [r11+28h]
0x18000c506  mov     rsp, r11
0x18000c509  pop     rbp
0x18000c50a  retn
0x18000c50b  mov     r8, rdi
0x18000c50e  lea     rdx, [rsp+270h+var_240]
0x18000c513  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c518  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000c51d  mov     ebx, eax
0x18000c51f  test    eax, eax
0x18000c521  jns     short loc_18000C4CF
0x18000c523  mov     edx, 137h
0x18000c528  jmp     loc_18000C4A0
```
