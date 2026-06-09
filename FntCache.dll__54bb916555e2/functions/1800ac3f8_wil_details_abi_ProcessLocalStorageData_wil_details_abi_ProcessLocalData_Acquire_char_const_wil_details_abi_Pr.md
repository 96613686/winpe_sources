# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800ac3f8`
- end: `0x1800ac55e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800ad270`

## callees

- `0x1800a868c`
- `0x1800aa650`
- `0x1800ac1a4`
- `0x1800ac1c0`
- `0x1800ac3f8`
- `0x1800ad9e8`
- `0x1800ae75c`
- `0x1800aed7c`
- `0x1800af1d8`
- `0x1800af8c4`
- `0x1800afa50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ac430`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ac430`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800ac475`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800ac475`

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
0x1800ac3f8  mov     [rsp-8+arg_10], rbx
0x1800ac3fd  mov     [rsp-8+arg_18], rdi
0x1800ac402  push    rbp
0x1800ac403  lea     rbp, [rsp-170h]
0x1800ac40b  sub     rsp, 270h
0x1800ac412  mov     rax, cs:__security_cookie
0x1800ac419  xor     rax, rsp
0x1800ac41c  mov     [rbp+170h+var_10], rax
0x1800ac423  mov     rdi, rdx
0x1800ac426  mov     qword ptr [rdx], 0
0x1800ac42d  mov     rbx, rcx
0x1800ac430  call    cs:__imp_GetCurrentProcessId
0x1800ac436  mov     [rsp+270h+var_248], rbx
0x1800ac43b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800ac442  mov     r9d, eax
0x1800ac445  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800ac44d  mov     edx, 104h; unsigned __int64
0x1800ac452  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800ac457  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ac45c  mov     r9d, 1F0001h; dwDesiredAccess
0x1800ac462  mov     [rsp+270h+var_240], 0
0x1800ac46b  xor     r8d, r8d; dwFlags
0x1800ac46e  lea     rdx, [rsp+270h+Name]; lpName
0x1800ac473  xor     ecx, ecx; lpMutexAttributes
0x1800ac475  call    cs:__imp_CreateMutexExW
0x1800ac47b  mov     rdx, rax
0x1800ac47e  lea     rcx, [rsp+270h+var_240]
0x1800ac483  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800ac488  cmp     [rsp+270h+var_240], 0
0x1800ac48e  jnz     short loc_1800AC499
0x1800ac490  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800ac495  mov     ebx, eax
0x1800ac497  jmp     short loc_1800AC50C
0x1800ac499  lea     rdx, [rsp+270h+var_238]
0x1800ac49e  lea     rcx, [rsp+270h+var_240]
0x1800ac4a3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800ac4a8  lea     rdx, [rsp+270h+var_230]; void **
0x1800ac4ad  mov     [rsp+270h+var_230], 0
0x1800ac4b6  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800ac4bb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1800ac4c0  mov     ebx, eax
0x1800ac4c2  test    eax, eax
0x1800ac4c4  jns     short loc_1800AC4ED
0x1800ac4c6  mov     edx, 12Eh; void *
0x1800ac4cb  mov     rcx, [rbp+178h]; this
0x1800ac4d2  lea     r8, aWil; "wil"
0x1800ac4d9  mov     r9d, eax; char *
0x1800ac4dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac4e1  lea     rcx, [rsp+270h+var_238]
0x1800ac4e6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ac4eb  jmp     short loc_1800AC50C
0x1800ac4ed  mov     rcx, [rsp+270h+var_230]
0x1800ac4f2  test    rcx, rcx
0x1800ac4f5  jz      short loc_1800AC53C
0x1800ac4f7  mov     [rdi], rcx
0x1800ac4fa  mov     eax, [rcx]
0x1800ac4fc  inc     eax
0x1800ac4fe  mov     [rcx], eax
0x1800ac500  lea     rcx, [rsp+270h+var_238]
0x1800ac505  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ac50a  xor     ebx, ebx
0x1800ac50c  lea     rcx, [rsp+270h+var_240]
0x1800ac511  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ac516  mov     eax, ebx
0x1800ac518  mov     rcx, [rbp+170h+var_10]
0x1800ac51f  xor     rcx, rsp; StackCookie
0x1800ac522  call    __security_check_cookie
0x1800ac527  lea     r11, [rsp+270h+var_s0]
0x1800ac52f  mov     rbx, [r11+20h]
0x1800ac533  mov     rdi, [r11+28h]
0x1800ac537  mov     rsp, r11
0x1800ac53a  pop     rbp
0x1800ac53b  retn
0x1800ac53c  mov     r8, rdi
0x1800ac53f  lea     rdx, [rsp+270h+var_240]
0x1800ac544  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800ac549  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800ac54e  mov     ebx, eax
0x1800ac550  test    eax, eax
0x1800ac552  jns     short loc_1800AC500
0x1800ac554  mov     edx, 137h
0x1800ac559  jmp     loc_1800AC4CB
```
