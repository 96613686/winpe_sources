# Microsoft::Diagnostics::Utils::Os::GetServiceProcessId(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,ulong &)

- ea: `0x18026eb0c`
- end: `0x18026ed29`
- name: `?GetServiceProcessId@Os@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAK@Z`
- size: `541`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180053ff4`
- `0x1802adb64`
- `0x18032a8e0`

## callees

- `0x18001b510`
- `0x18002b7c0`
- `0x18002df00`
- `0x180064e6c`
- `0x1800f7b34`
- `0x1801ecf60`
- `0x18020aac0`
- `0x18026eb0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026ec22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026ec22`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18026eba3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18026eba3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18026eb41`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18026eb41`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18026ec14`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18026ec5b`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18026ec14`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18026ec5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::GetServiceProcessId(__int64 a1, _DWORD *a2)
{
  SC_HANDLE v4; // rbx
  const char *v5; // r9
  unsigned int v6; // ebx
  __int64 v8; // rax
  SC_HANDLE v9; // rbx
  const char *v10; // r9
  unsigned int v11; // ebx
  const char *v12; // r9
  LPBYTE v13; // rdi
  const struct std::nothrow_t *v14; // rdx
  const char *v15; // r9
  unsigned int v16; // ebx
  const struct std::nothrow_t *v17; // rdx
  unsigned int LastError; // ebx
  DWORD cbBufSize; // [rsp+30h] [rbp-58h] BYREF
  SC_HANDLE v20; // [rsp+38h] [rbp-50h] BYREF
  SC_HANDLE v21; // [rsp+40h] [rbp-48h] BYREF
  LPBYTE lpBuffer; // [rsp+48h] [rbp-40h] BYREF
  _BYTE v23[32]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *a2 = 0;
  v4 = OpenSCManagerW(0, 0, 4u);
  v20 = v4;
  if ( v4 )
  {
    v8 = std::wstring::wstring(v23, a1);
    if ( *(_QWORD *)(v8 + 24) > 7u )
      v8 = *(_QWORD *)v8;
    v9 = OpenServiceW(v4, (LPCWSTR)v8, 4u);
    v21 = v9;
    std::wstring::_Tidy_deallocate(v23);
    if ( v9 )
    {
      cbBufSize = 0;
      if ( QueryServiceStatusEx(v9, SC_STATUS_PROCESS_INFO, 0, 0, &cbBufSize) || GetLastError() != 122 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x5FF,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                      v12);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v21);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v20);
        return LastError;
      }
      else
      {
        std::make_unique<unsigned char [0],0>(&lpBuffer, cbBufSize);
        v13 = lpBuffer;
        if ( QueryServiceStatusEx(v9, SC_STATUS_PROCESS_INFO, lpBuffer, cbBufSize, &cbBufSize) )
        {
          *a2 = *((_DWORD *)v13 + 7);
          std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpBuffer, v14);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v21);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v20);
          return 0;
        }
        else
        {
          v16 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x605,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                  v15);
          std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpBuffer, v17);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v21);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v20);
          return v16;
        }
      }
    }
    else
    {
      v11 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x5F8,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
              v10);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v21);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v20);
      return v11;
    }
  }
  else
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x5F5,
           (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
           v5);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v20);
    return v6;
  }
}

```

## disassembly

```asm
0x18026eb0c  mov     [rsp+arg_10], rbx
0x18026eb11  mov     [rsp+arg_18], rsi
0x18026eb16  push    rdi
0x18026eb17  sub     rsp, 80h
0x18026eb1e  mov     rax, cs:__security_cookie
0x18026eb25  xor     rax, rsp
0x18026eb28  mov     [rsp+88h+var_18], rax
0x18026eb2d  mov     rsi, rdx
0x18026eb30  mov     rdi, rcx
0x18026eb33  mov     dword ptr [rdx], 0
0x18026eb39  xor     edx, edx; lpDatabaseName
0x18026eb3b  xor     ecx, ecx; lpMachineName
0x18026eb3d  lea     r8d, [rdx+4]; dwDesiredAccess
0x18026eb41  call    cs:__imp_OpenSCManagerW
0x18026eb47  mov     rbx, rax
0x18026eb4a  mov     [rsp+88h+var_50], rax
0x18026eb4f  test    rax, rax
0x18026eb52  jnz     short loc_18026EB80
0x18026eb54  mov     rcx, [rsp+88h]; this
0x18026eb5c  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026eb63  mov     edx, 5F5h; void *
0x18026eb68  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18026eb6d  mov     ebx, eax
0x18026eb6f  lea     rcx, [rsp+88h+var_50]
0x18026eb74  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18026eb79  mov     eax, ebx
0x18026eb7b  jmp     loc_18026ED06
0x18026eb80  mov     rdx, rdi
0x18026eb83  lea     rcx, [rsp+88h+var_38]
0x18026eb88  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18026eb8d  cmp     qword ptr [rax+18h], 7
0x18026eb92  jbe     short loc_18026EB97
0x18026eb94  mov     rax, [rax]
0x18026eb97  mov     r8d, 4; dwDesiredAccess
0x18026eb9d  mov     rdx, rax; lpServiceName
0x18026eba0  mov     rcx, rbx; hSCManager
0x18026eba3  call    cs:__imp_OpenServiceW
0x18026eba9  mov     rbx, rax
0x18026ebac  mov     [rsp+88h+var_48], rax
0x18026ebb1  lea     rcx, [rsp+88h+var_38]
0x18026ebb6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026ebbb  test    rbx, rbx
0x18026ebbe  jnz     short loc_18026EBF7
0x18026ebc0  mov     rcx, [rsp+88h]; this
0x18026ebc8  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026ebcf  mov     edx, 5F8h; void *
0x18026ebd4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18026ebd9  mov     ebx, eax
0x18026ebdb  lea     rcx, [rsp+88h+var_48]
0x18026ebe0  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18026ebe5  nop
0x18026ebe6  lea     rcx, [rsp+88h+var_50]
0x18026ebeb  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18026ebf0  mov     eax, ebx
0x18026ebf2  jmp     loc_18026ED06
0x18026ebf7  mov     [rsp+88h+cbBufSize], 0
0x18026ebff  lea     rax, [rsp+88h+cbBufSize]
0x18026ec04  mov     [rsp+88h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18026ec09  xor     r9d, r9d; cbBufSize
0x18026ec0c  xor     r8d, r8d; lpBuffer
0x18026ec0f  xor     edx, edx; InfoLevel
0x18026ec11  mov     rcx, rbx; hService
0x18026ec14  call    cs:__imp_QueryServiceStatusEx
0x18026ec1a  test    eax, eax
0x18026ec1c  jnz     loc_18026ECCE
0x18026ec22  call    cs:__imp_GetLastError
0x18026ec28  cmp     eax, 7Ah ; 'z'
0x18026ec2b  jnz     loc_18026ECCE
0x18026ec31  mov     edx, [rsp+88h+cbBufSize]
0x18026ec35  lea     rcx, [rsp+88h+lpBuffer]
0x18026ec3a  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x18026ec3f  lea     rax, [rsp+88h+cbBufSize]
0x18026ec44  mov     [rsp+88h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18026ec49  mov     r9d, [rsp+88h+cbBufSize]; cbBufSize
0x18026ec4e  mov     rdi, [rsp+88h+lpBuffer]
0x18026ec53  mov     r8, rdi; lpBuffer
0x18026ec56  xor     edx, edx; InfoLevel
0x18026ec58  mov     rcx, rbx; hService
0x18026ec5b  call    cs:__imp_QueryServiceStatusEx
0x18026ec61  test    eax, eax
0x18026ec63  jnz     short loc_18026ECA4
0x18026ec65  mov     rcx, [rsp+88h]; this
0x18026ec6d  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026ec74  mov     edx, 605h; void *
0x18026ec79  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18026ec7e  mov     ebx, eax
0x18026ec80  lea     rcx, [rsp+88h+lpBuffer]
0x18026ec85  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x18026ec8a  nop
0x18026ec8b  lea     rcx, [rsp+88h+var_48]
0x18026ec90  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18026ec95  nop
0x18026ec96  lea     rcx, [rsp+88h+var_50]
0x18026ec9b  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18026eca0  mov     eax, ebx
0x18026eca2  jmp     short loc_18026ED06
0x18026eca4  mov     eax, [rdi+1Ch]
0x18026eca7  mov     [rsi], eax
0x18026eca9  lea     rcx, [rsp+88h+lpBuffer]
0x18026ecae  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x18026ecb3  nop
0x18026ecb4  lea     rcx, [rsp+88h+var_48]
0x18026ecb9  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18026ecbe  nop
0x18026ecbf  lea     rcx, [rsp+88h+var_50]
0x18026ecc4  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18026ecc9  nop
0x18026ecca  xor     eax, eax
0x18026eccc  jmp     short loc_18026ED06
0x18026ecce  mov     rcx, [rsp+88h]; this
0x18026ecd6  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026ecdd  mov     edx, 5FFh; void *
0x18026ece2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18026ece7  mov     ebx, eax
0x18026ece9  lea     rcx, [rsp+88h+var_48]
0x18026ecee  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18026ecf3  nop
0x18026ecf4  lea     rcx, [rsp+88h+var_50]
0x18026ecf9  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18026ecfe  mov     eax, ebx
0x18026ed00  jmp     short loc_18026ED06
0x18026ed02  mov     eax, [rsp+88h+cbBufSize]
0x18026ed06  mov     rcx, [rsp+88h+var_18]
0x18026ed0b  xor     rcx, rsp; StackCookie
0x18026ed0e  call    __security_check_cookie
0x18026ed13  lea     r11, [rsp+88h+var_8]
0x18026ed1b  mov     rbx, [r11+20h]
0x18026ed1f  mov     rsi, [r11+28h]
0x18026ed23  mov     rsp, r11
0x18026ed26  pop     rdi
0x18026ed27  retn
```
