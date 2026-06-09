# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180014438`
- end: `0x18001459e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180014eb8`

## callees

- `0x180009bf8`
- `0x180010818`
- `0x18001433c`
- `0x180014358`
- `0x180014438`
- `0x1800150cc`
- `0x18001577c`
- `0x180015dac`
- `0x1800160cc`
- `0x1800161d0`
- `0x1800227c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800144b5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800144b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014470`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014470`

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
0x180014438  mov     [rsp-8+arg_10], rbx
0x18001443d  mov     [rsp-8+arg_18], rdi
0x180014442  push    rbp
0x180014443  lea     rbp, [rsp-170h]
0x18001444b  sub     rsp, 270h
0x180014452  mov     rax, cs:__security_cookie
0x180014459  xor     rax, rsp
0x18001445c  mov     [rbp+170h+var_10], rax
0x180014463  mov     rdi, rdx
0x180014466  mov     qword ptr [rdx], 0
0x18001446d  mov     rbx, rcx
0x180014470  call    cs:__imp_GetCurrentProcessId
0x180014476  mov     [rsp+270h+var_248], rbx
0x18001447b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180014482  mov     r9d, eax
0x180014485  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001448d  mov     edx, 104h; unsigned __int64
0x180014492  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180014497  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001449c  mov     r9d, 1F0001h; dwDesiredAccess
0x1800144a2  mov     [rsp+270h+var_240], 0
0x1800144ab  xor     r8d, r8d; dwFlags
0x1800144ae  lea     rdx, [rsp+270h+Name]; lpName
0x1800144b3  xor     ecx, ecx; lpMutexAttributes
0x1800144b5  call    cs:__imp_CreateMutexExW
0x1800144bb  mov     rdx, rax
0x1800144be  lea     rcx, [rsp+270h+var_240]
0x1800144c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800144c8  cmp     [rsp+270h+var_240], 0
0x1800144ce  jnz     short loc_1800144D9
0x1800144d0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800144d5  mov     ebx, eax
0x1800144d7  jmp     short loc_18001454C
0x1800144d9  lea     rdx, [rsp+270h+var_238]
0x1800144de  lea     rcx, [rsp+270h+var_240]
0x1800144e3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800144e8  lea     rdx, [rsp+270h+var_230]; void **
0x1800144ed  mov     [rsp+270h+var_230], 0
0x1800144f6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800144fb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180014500  mov     ebx, eax
0x180014502  test    eax, eax
0x180014504  jns     short loc_18001452D
0x180014506  mov     edx, 12Eh; void *
0x18001450b  mov     rcx, [rbp+178h]; this
0x180014512  lea     r8, aWil; "wil"
0x180014519  mov     r9d, eax; char *
0x18001451c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014521  lea     rcx, [rsp+270h+var_238]
0x180014526  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001452b  jmp     short loc_18001454C
0x18001452d  mov     rcx, [rsp+270h+var_230]
0x180014532  test    rcx, rcx
0x180014535  jz      short loc_18001457C
0x180014537  mov     [rdi], rcx
0x18001453a  mov     eax, [rcx]
0x18001453c  inc     eax
0x18001453e  mov     [rcx], eax
0x180014540  lea     rcx, [rsp+270h+var_238]
0x180014545  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001454a  xor     ebx, ebx
0x18001454c  lea     rcx, [rsp+270h+var_240]
0x180014551  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180014556  mov     eax, ebx
0x180014558  mov     rcx, [rbp+170h+var_10]
0x18001455f  xor     rcx, rsp; StackCookie
0x180014562  call    __security_check_cookie
0x180014567  lea     r11, [rsp+270h+var_s0]
0x18001456f  mov     rbx, [r11+20h]
0x180014573  mov     rdi, [r11+28h]
0x180014577  mov     rsp, r11
0x18001457a  pop     rbp
0x18001457b  retn
0x18001457c  mov     r8, rdi
0x18001457f  lea     rdx, [rsp+270h+var_240]
0x180014584  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180014589  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001458e  mov     ebx, eax
0x180014590  test    eax, eax
0x180014592  jns     short loc_180014540
0x180014594  mov     edx, 137h
0x180014599  jmp     loc_18001450B
```
