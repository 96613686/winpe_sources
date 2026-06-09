# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002086c`
- end: `0x1800209d2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180020eb0`

## callees

- `0x180002520`
- `0x1800067ac`
- `0x18000e768`
- `0x1800207ac`
- `0x1800207c8`
- `0x18002086c`
- `0x180020cac`
- `0x1800210cc`
- `0x180021728`
- `0x180021988`
- `0x180021bf8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800208a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800208a4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800208e9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800208e9`

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
0x18002086c  mov     [rsp-8+arg_10], rbx
0x180020871  mov     [rsp-8+arg_18], rdi
0x180020876  push    rbp
0x180020877  lea     rbp, [rsp-170h]
0x18002087f  sub     rsp, 270h
0x180020886  mov     rax, cs:__security_cookie
0x18002088d  xor     rax, rsp
0x180020890  mov     [rbp+170h+var_10], rax
0x180020897  mov     rdi, rdx
0x18002089a  mov     qword ptr [rdx], 0
0x1800208a1  mov     rbx, rcx
0x1800208a4  call    cs:__imp_GetCurrentProcessId
0x1800208aa  mov     [rsp+270h+var_248], rbx
0x1800208af  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800208b6  mov     r9d, eax
0x1800208b9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800208c1  mov     edx, 104h; unsigned __int64
0x1800208c6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800208cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800208d0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800208d6  mov     [rsp+270h+var_240], 0
0x1800208df  xor     r8d, r8d; dwFlags
0x1800208e2  lea     rdx, [rsp+270h+Name]; lpName
0x1800208e7  xor     ecx, ecx; lpMutexAttributes
0x1800208e9  call    cs:__imp_CreateMutexExW
0x1800208ef  mov     rdx, rax
0x1800208f2  lea     rcx, [rsp+270h+var_240]
0x1800208f7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800208fc  cmp     [rsp+270h+var_240], 0
0x180020902  jnz     short loc_18002090D
0x180020904  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180020909  mov     ebx, eax
0x18002090b  jmp     short loc_180020980
0x18002090d  lea     rdx, [rsp+270h+var_238]
0x180020912  lea     rcx, [rsp+270h+var_240]
0x180020917  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002091c  lea     rdx, [rsp+270h+var_230]; void **
0x180020921  mov     [rsp+270h+var_230], 0
0x18002092a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002092f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180020934  mov     ebx, eax
0x180020936  test    eax, eax
0x180020938  jns     short loc_180020961
0x18002093a  mov     edx, 12Eh; void *
0x18002093f  mov     rcx, [rbp+178h]; this
0x180020946  lea     r8, aWil; "wil"
0x18002094d  mov     r9d, eax; char *
0x180020950  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020955  lea     rcx, [rsp+270h+var_238]
0x18002095a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002095f  jmp     short loc_180020980
0x180020961  mov     rcx, [rsp+270h+var_230]
0x180020966  test    rcx, rcx
0x180020969  jz      short loc_1800209B0
0x18002096b  mov     [rdi], rcx
0x18002096e  mov     eax, [rcx]
0x180020970  inc     eax
0x180020972  mov     [rcx], eax
0x180020974  lea     rcx, [rsp+270h+var_238]
0x180020979  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002097e  xor     ebx, ebx
0x180020980  lea     rcx, [rsp+270h+var_240]
0x180020985  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002098a  mov     eax, ebx
0x18002098c  mov     rcx, [rbp+170h+var_10]
0x180020993  xor     rcx, rsp; StackCookie
0x180020996  call    __security_check_cookie
0x18002099b  lea     r11, [rsp+270h+var_s0]
0x1800209a3  mov     rbx, [r11+20h]
0x1800209a7  mov     rdi, [r11+28h]
0x1800209ab  mov     rsp, r11
0x1800209ae  pop     rbp
0x1800209af  retn
0x1800209b0  mov     r8, rdi
0x1800209b3  lea     rdx, [rsp+270h+var_240]
0x1800209b8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800209bd  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800209c2  mov     ebx, eax
0x1800209c4  test    eax, eax
0x1800209c6  jns     short loc_180020974
0x1800209c8  mov     edx, 137h
0x1800209cd  jmp     loc_18002093F
```
