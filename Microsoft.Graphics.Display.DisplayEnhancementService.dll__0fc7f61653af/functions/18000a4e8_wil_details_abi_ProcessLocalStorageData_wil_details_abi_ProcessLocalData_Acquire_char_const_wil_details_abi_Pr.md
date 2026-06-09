# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000a4e8`
- end: `0x18000a64e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b78c`

## callees

- `0x180005860`
- `0x180009b3c`
- `0x180009b58`
- `0x18000a4e8`
- `0x18000b418`
- `0x18000c8c0`
- `0x18000decc`
- `0x18000e7e4`
- `0x18000ecec`
- `0x18000fbb4`
- `0x18000ffe0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a520`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a520`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a565`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a565`

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
0x18000a4e8  mov     [rsp-8+arg_10], rbx
0x18000a4ed  mov     [rsp-8+arg_18], rdi
0x18000a4f2  push    rbp
0x18000a4f3  lea     rbp, [rsp-170h]
0x18000a4fb  sub     rsp, 270h
0x18000a502  mov     rax, cs:__security_cookie
0x18000a509  xor     rax, rsp
0x18000a50c  mov     [rbp+170h+var_10], rax
0x18000a513  mov     rdi, rdx
0x18000a516  mov     qword ptr [rdx], 0
0x18000a51d  mov     rbx, rcx
0x18000a520  call    cs:__imp_GetCurrentProcessId
0x18000a526  mov     [rsp+270h+var_248], rbx
0x18000a52b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a532  mov     r9d, eax
0x18000a535  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000a53d  mov     edx, 104h; unsigned __int64
0x18000a542  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a547  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a54c  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a552  mov     [rsp+270h+var_240], 0
0x18000a55b  xor     r8d, r8d; dwFlags
0x18000a55e  lea     rdx, [rsp+270h+Name]; lpName
0x18000a563  xor     ecx, ecx; lpMutexAttributes
0x18000a565  call    cs:__imp_CreateMutexExW
0x18000a56b  mov     rdx, rax
0x18000a56e  lea     rcx, [rsp+270h+var_240]
0x18000a573  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a578  cmp     [rsp+270h+var_240], 0
0x18000a57e  jnz     short loc_18000A589
0x18000a580  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a585  mov     ebx, eax
0x18000a587  jmp     short loc_18000A5FC
0x18000a589  lea     rdx, [rsp+270h+var_238]
0x18000a58e  lea     rcx, [rsp+270h+var_240]
0x18000a593  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000a598  lea     rdx, [rsp+270h+var_230]; void **
0x18000a59d  mov     [rsp+270h+var_230], 0
0x18000a5a6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a5ab  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000a5b0  mov     ebx, eax
0x18000a5b2  test    eax, eax
0x18000a5b4  jns     short loc_18000A5DD
0x18000a5b6  mov     edx, 12Eh; void *
0x18000a5bb  mov     rcx, [rbp+178h]; this
0x18000a5c2  lea     r8, aWil; "wil"
0x18000a5c9  mov     r9d, eax; char *
0x18000a5cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5d1  lea     rcx, [rsp+270h+var_238]
0x18000a5d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a5db  jmp     short loc_18000A5FC
0x18000a5dd  mov     rcx, [rsp+270h+var_230]
0x18000a5e2  test    rcx, rcx
0x18000a5e5  jz      short loc_18000A62C
0x18000a5e7  mov     [rdi], rcx
0x18000a5ea  mov     eax, [rcx]
0x18000a5ec  inc     eax
0x18000a5ee  mov     [rcx], eax
0x18000a5f0  lea     rcx, [rsp+270h+var_238]
0x18000a5f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a5fa  xor     ebx, ebx
0x18000a5fc  lea     rcx, [rsp+270h+var_240]
0x18000a601  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a606  mov     eax, ebx
0x18000a608  mov     rcx, [rbp+170h+var_10]
0x18000a60f  xor     rcx, rsp; StackCookie
0x18000a612  call    __security_check_cookie
0x18000a617  lea     r11, [rsp+270h+var_s0]
0x18000a61f  mov     rbx, [r11+20h]
0x18000a623  mov     rdi, [r11+28h]
0x18000a627  mov     rsp, r11
0x18000a62a  pop     rbp
0x18000a62b  retn
0x18000a62c  mov     r8, rdi
0x18000a62f  lea     rdx, [rsp+270h+var_240]
0x18000a634  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a639  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000a63e  mov     ebx, eax
0x18000a640  test    eax, eax
0x18000a642  jns     short loc_18000A5F0
0x18000a644  mov     edx, 137h
0x18000a649  jmp     loc_18000A5BB
```
