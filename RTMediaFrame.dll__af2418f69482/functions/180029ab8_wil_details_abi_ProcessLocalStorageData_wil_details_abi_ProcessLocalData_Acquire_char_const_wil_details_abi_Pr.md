# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180029ab8`
- end: `0x180029c1e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002c1e0`

## callees

- `0x180020c48`
- `0x180025dac`
- `0x180026920`
- `0x180029488`
- `0x1800294a4`
- `0x180029ab8`
- `0x18002ccfc`
- `0x18002f814`
- `0x18002fcac`
- `0x1800305f4`
- `0x180030920`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029af0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029af0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180029b35`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180029b35`

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
0x180029ab8  mov     [rsp-8+arg_10], rbx
0x180029abd  mov     [rsp-8+arg_18], rdi
0x180029ac2  push    rbp
0x180029ac3  lea     rbp, [rsp-170h]
0x180029acb  sub     rsp, 270h
0x180029ad2  mov     rax, cs:__security_cookie
0x180029ad9  xor     rax, rsp
0x180029adc  mov     [rbp+170h+var_10], rax
0x180029ae3  mov     rdi, rdx
0x180029ae6  mov     qword ptr [rdx], 0
0x180029aed  mov     rbx, rcx
0x180029af0  call    cs:__imp_GetCurrentProcessId
0x180029af6  mov     [rsp+270h+var_248], rbx
0x180029afb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180029b02  mov     r9d, eax
0x180029b05  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180029b0d  mov     edx, 104h; unsigned __int64
0x180029b12  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180029b17  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029b1c  mov     r9d, 1F0001h; dwDesiredAccess
0x180029b22  mov     [rsp+270h+var_240], 0
0x180029b2b  xor     r8d, r8d; dwFlags
0x180029b2e  lea     rdx, [rsp+270h+Name]; lpName
0x180029b33  xor     ecx, ecx; lpMutexAttributes
0x180029b35  call    cs:__imp_CreateMutexExW
0x180029b3b  mov     rdx, rax
0x180029b3e  lea     rcx, [rsp+270h+var_240]
0x180029b43  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180029b48  cmp     [rsp+270h+var_240], 0
0x180029b4e  jnz     short loc_180029B59
0x180029b50  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180029b55  mov     ebx, eax
0x180029b57  jmp     short loc_180029BCC
0x180029b59  lea     rdx, [rsp+270h+var_238]
0x180029b5e  lea     rcx, [rsp+270h+var_240]
0x180029b63  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180029b68  lea     rdx, [rsp+270h+var_230]; void **
0x180029b6d  mov     [rsp+270h+var_230], 0
0x180029b76  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180029b7b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180029b80  mov     ebx, eax
0x180029b82  test    eax, eax
0x180029b84  jns     short loc_180029BAD
0x180029b86  mov     edx, 12Eh; void *
0x180029b8b  mov     rcx, [rbp+178h]; this
0x180029b92  lea     r8, aWil; "wil"
0x180029b99  mov     r9d, eax; char *
0x180029b9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029ba1  lea     rcx, [rsp+270h+var_238]
0x180029ba6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180029bab  jmp     short loc_180029BCC
0x180029bad  mov     rcx, [rsp+270h+var_230]
0x180029bb2  test    rcx, rcx
0x180029bb5  jz      short loc_180029BFC
0x180029bb7  mov     [rdi], rcx
0x180029bba  mov     eax, [rcx]
0x180029bbc  inc     eax
0x180029bbe  mov     [rcx], eax
0x180029bc0  lea     rcx, [rsp+270h+var_238]
0x180029bc5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180029bca  xor     ebx, ebx
0x180029bcc  lea     rcx, [rsp+270h+var_240]
0x180029bd1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180029bd6  mov     eax, ebx
0x180029bd8  mov     rcx, [rbp+170h+var_10]
0x180029bdf  xor     rcx, rsp; StackCookie
0x180029be2  call    __security_check_cookie
0x180029be7  lea     r11, [rsp+270h+var_s0]
0x180029bef  mov     rbx, [r11+20h]
0x180029bf3  mov     rdi, [r11+28h]
0x180029bf7  mov     rsp, r11
0x180029bfa  pop     rbp
0x180029bfb  retn
0x180029bfc  mov     r8, rdi
0x180029bff  lea     rdx, [rsp+270h+var_240]
0x180029c04  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180029c09  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180029c0e  mov     ebx, eax
0x180029c10  test    eax, eax
0x180029c12  jns     short loc_180029BC0
0x180029c14  mov     edx, 137h
0x180029c19  jmp     loc_180029B8B
```
