# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008118`
- end: `0x18000827e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009af0`

## callees

- `0x180003a60`
- `0x180007520`
- `0x18000753c`
- `0x180008118`
- `0x180009638`
- `0x18000a914`
- `0x18000c4cc`
- `0x18000cd3c`
- `0x18000d348`
- `0x18000e284`
- `0x18000e838`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008195`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008195`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008150`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008150`

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
0x180008118  mov     [rsp-8+arg_10], rbx
0x18000811d  mov     [rsp-8+arg_18], rdi
0x180008122  push    rbp
0x180008123  lea     rbp, [rsp-170h]
0x18000812b  sub     rsp, 270h
0x180008132  mov     rax, cs:__security_cookie
0x180008139  xor     rax, rsp
0x18000813c  mov     [rbp+170h+var_10], rax
0x180008143  mov     rdi, rdx
0x180008146  mov     qword ptr [rdx], 0
0x18000814d  mov     rbx, rcx
0x180008150  call    cs:__imp_GetCurrentProcessId
0x180008156  mov     [rsp+270h+var_248], rbx
0x18000815b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008162  mov     r9d, eax
0x180008165  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000816d  mov     edx, 104h; unsigned __int64
0x180008172  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008177  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000817c  mov     r9d, 1F0001h; dwDesiredAccess
0x180008182  mov     [rsp+270h+var_240], 0
0x18000818b  xor     r8d, r8d; dwFlags
0x18000818e  lea     rdx, [rsp+270h+Name]; lpName
0x180008193  xor     ecx, ecx; lpMutexAttributes
0x180008195  call    cs:__imp_CreateMutexExW
0x18000819b  mov     rdx, rax
0x18000819e  lea     rcx, [rsp+270h+var_240]
0x1800081a3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800081a8  cmp     [rsp+270h+var_240], 0
0x1800081ae  jnz     short loc_1800081B9
0x1800081b0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800081b5  mov     ebx, eax
0x1800081b7  jmp     short loc_18000822C
0x1800081b9  lea     rdx, [rsp+270h+var_238]
0x1800081be  lea     rcx, [rsp+270h+var_240]
0x1800081c3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800081c8  lea     rdx, [rsp+270h+var_230]; void **
0x1800081cd  mov     [rsp+270h+var_230], 0
0x1800081d6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800081db  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800081e0  mov     ebx, eax
0x1800081e2  test    eax, eax
0x1800081e4  jns     short loc_18000820D
0x1800081e6  mov     edx, 12Eh; void *
0x1800081eb  mov     rcx, [rbp+178h]; this
0x1800081f2  lea     r8, aWil; "wil"
0x1800081f9  mov     r9d, eax; char *
0x1800081fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008201  lea     rcx, [rsp+270h+var_238]
0x180008206  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000820b  jmp     short loc_18000822C
0x18000820d  mov     rcx, [rsp+270h+var_230]
0x180008212  test    rcx, rcx
0x180008215  jz      short loc_18000825C
0x180008217  mov     [rdi], rcx
0x18000821a  mov     eax, [rcx]
0x18000821c  inc     eax
0x18000821e  mov     [rcx], eax
0x180008220  lea     rcx, [rsp+270h+var_238]
0x180008225  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000822a  xor     ebx, ebx
0x18000822c  lea     rcx, [rsp+270h+var_240]
0x180008231  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008236  mov     eax, ebx
0x180008238  mov     rcx, [rbp+170h+var_10]
0x18000823f  xor     rcx, rsp; StackCookie
0x180008242  call    __security_check_cookie
0x180008247  lea     r11, [rsp+270h+var_s0]
0x18000824f  mov     rbx, [r11+20h]
0x180008253  mov     rdi, [r11+28h]
0x180008257  mov     rsp, r11
0x18000825a  pop     rbp
0x18000825b  retn
0x18000825c  mov     r8, rdi
0x18000825f  lea     rdx, [rsp+270h+var_240]
0x180008264  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008269  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000826e  mov     ebx, eax
0x180008270  test    eax, eax
0x180008272  jns     short loc_180008220
0x180008274  mov     edx, 137h
0x180008279  jmp     loc_1800081EB
```
