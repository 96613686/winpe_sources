# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000a5a8`
- end: `0x18000a70e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(const char *staticNameWithVersion, wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> **data)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b918`

## callees

- `0x1800060f8`
- `0x1800062c0`
- `0x180007674`
- `0x180007a68`
- `0x18000a28c`
- `0x18000a2a8`
- `0x18000a5a8`
- `0x18000c244`
- `0x18000da84`
- `0x18000e300`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a625`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a625`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a5e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a5e0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        const char *staticNameWithVersion,
        wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> **data)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  unsigned int *v5; // r8
  unsigned int v6; // r9d
  unsigned int LastErrorFailHr; // ebx
  HRESULT v8; // eax
  unsigned int v9; // edx
  _DWORD *v10; // rcx
  wil::unique_any_t<wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > mutex; // [rsp+30h] [rbp-D0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::ReleaseMutex,wistd::integral_constant<unsigned __int64,2>,void *,void *,0,std::nullptr_t> > > lock; // [rsp+38h] [rbp-C8h] BYREF
  void *pointer; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t name[264]; // [rsp+50h] [rbp-B0h] BYREF
  void *retaddr; // [rsp+278h] [rbp+178h]

  *data = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  mutex.m_ptr = 0;
  v4 = CreateMutexExW(0, name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &mutex,
    v4);
  if ( mutex.m_ptr )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &mutex,
      &lock,
      v5,
      v6,
      120);
    pointer = 0;
    v8 = wil::details_abi::SemaphoreValue::TryGetPointer(name, &pointer);
    LastErrorFailHr = v8;
    if ( v8 < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, v9, "wil", v8);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&lock);
      goto LABEL_9;
    }
    v10 = pointer;
    if ( pointer )
    {
      *data = (wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> *)pointer;
      ++*v10;
    }
    else
    {
      v8 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
             name,
             &mutex,
             data);
      LastErrorFailHr = v8;
      if ( v8 < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&lock);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr();
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&mutex);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18000a5a8  mov     [rsp-8+arg_10], rbx
0x18000a5ad  mov     [rsp-8+arg_18], rdi
0x18000a5b2  push    rbp
0x18000a5b3  lea     rbp, [rsp-170h]
0x18000a5bb  sub     rsp, 270h
0x18000a5c2  mov     rax, cs:__security_cookie
0x18000a5c9  xor     rax, rsp
0x18000a5cc  mov     [rbp+170h+var_10], rax
0x18000a5d3  mov     rdi, data
0x18000a5d6  mov     qword ptr [data], 0
0x18000a5dd  mov     rbx, staticNameWithVersion
0x18000a5e0  call    cs:__imp_GetCurrentProcessId
0x18000a5e6  mov     [rsp+270h+var_248], rbx
0x18000a5eb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a5f2  mov     r9d, eax
0x18000a5f5  mov     [rsp+270h+bAlertable], 78h ; 'x'; bAlertable
0x18000a5fd  mov     edx, 104h; cchDest
0x18000a602  lea     staticNameWithVersion, [rsp+270h+name]; pszDest
0x18000a607  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a60c  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a612  mov     [rsp+270h+mutex.m_ptr], 0
0x18000a61b  xor     r8d, r8d; dwFlags
0x18000a61e  lea     data, [rsp+270h+name]; lpName
0x18000a623  xor     ecx, ecx; lpMutexAttributes
0x18000a625  call    cs:__imp_CreateMutexExW
0x18000a62b  mov     data, rax; ptr
0x18000a62e  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x18000a633  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a638  cmp     [rsp+270h+mutex.m_ptr], 0
0x18000a63e  jnz     short loc_18000A649
0x18000a640  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a645  mov     ebx, eax
0x18000a647  jmp     short loc_18000A6BC
0x18000a649  lea     data, [rsp+270h+lock]; result
0x18000a64e  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x18000a653  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000a658  lea     data, [rsp+270h+pointer]; pointer
0x18000a65d  mov     [rsp+270h+pointer], 0
0x18000a666  lea     staticNameWithVersion, [rsp+270h+name]; name
0x18000a66b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000a670  mov     ebx, eax
0x18000a672  test    eax, eax
0x18000a674  jns     short loc_18000A69D
0x18000a676  mov     edx, 12Eh; lineNumber
0x18000a67b  mov     staticNameWithVersion, [rbp+178h]; callerReturnAddress
0x18000a682  lea     r8, aWil; "wil"
0x18000a689  mov     r9d, eax; hr
0x18000a68c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a691  lea     staticNameWithVersion, [rsp+270h+lock]; this
0x18000a696  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a69b  jmp     short loc_18000A6BC
0x18000a69d  mov     staticNameWithVersion, [rsp+270h+pointer]
0x18000a6a2  test    staticNameWithVersion, staticNameWithVersion
0x18000a6a5  jz      short loc_18000A6EC
0x18000a6a7  mov     [rdi], staticNameWithVersion
0x18000a6aa  mov     eax, [staticNameWithVersion]
0x18000a6ac  inc     eax
0x18000a6ae  mov     [staticNameWithVersion], eax
0x18000a6b0  lea     staticNameWithVersion, [rsp+270h+lock]; this
0x18000a6b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a6ba  xor     ebx, ebx
0x18000a6bc  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x18000a6c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a6c6  mov     eax, ebx
0x18000a6c8  mov     staticNameWithVersion, [rbp+170h+var_10]
0x18000a6cf  xor     staticNameWithVersion, rsp; StackCookie
0x18000a6d2  call    __security_check_cookie
0x18000a6d7  lea     r11, [rsp+270h+var_s0]
0x18000a6df  mov     rbx, [r11+20h]
0x18000a6e3  mov     rdi, [r11+28h]
0x18000a6e7  mov     rsp, r11
0x18000a6ea  pop     rbp
0x18000a6eb  retn
0x18000a6ec  mov     r8, rdi; data
0x18000a6ef  lea     data, [rsp+270h+mutex]; mutex
0x18000a6f4  lea     staticNameWithVersion, [rsp+270h+name]; name
0x18000a6f9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000a6fe  mov     ebx, eax
0x18000a700  test    eax, eax
0x18000a702  jns     short loc_18000A6B0
0x18000a704  mov     edx, 137h
0x18000a709  jmp     loc_18000A67B
```
