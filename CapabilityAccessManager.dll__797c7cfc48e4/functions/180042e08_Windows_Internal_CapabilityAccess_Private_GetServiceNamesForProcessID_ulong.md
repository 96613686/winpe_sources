# Windows::Internal::CapabilityAccess::Private::GetServiceNamesForProcessID(ulong)

- ea: `0x180042e08`
- end: `0x180042fe0`
- name: `?GetServiceNamesForProcessID@Private@CapabilityAccess@Internal@Windows@@YA?AV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@K@Z`
- size: `472`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180025c90`
- `0x18002fe74`
- `0x180092eec`

## callees

- `0x18001c5fc`
- `0x18002392c`
- `0x1800257ec`
- `0x18002a564`
- `0x180039e9c`
- `0x18003f274`
- `0x18003f43c`
- `0x18003f4c4`
- `0x180042e08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042ed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042ed7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180042e4e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180042e4e`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180042eb1`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180042f4c`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180042eb1`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180042f4c`

## string_xrefs

- `0x180042e45`: `ServicesActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::GetServiceNamesForProcessID(_QWORD *a1, int a2)
{
  __int64 v4; // rcx
  SC_HANDLE v5; // rbx
  const char *v6; // r9
  LPBYTE v7; // rsi
  const char *v8; // r9
  DWORD v9; // ebx
  DWORD i; // ecx
  __int64 v11; // rdi
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  int lpServices; // [rsp+20h] [rbp-50h]
  DWORD ResumeHandle[2]; // [rsp+50h] [rbp-20h] BYREF
  LPBYTE v19; // [rsp+58h] [rbp-18h] BYREF
  SC_HANDLE v20[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  DWORD pcbBytesNeeded; // [rsp+C0h] [rbp+50h] BYREF
  DWORD ServicesReturned; // [rsp+C8h] [rbp+58h] BYREF

  std::wstring::wstring(a1);
  std::wstring::wstring(v4 + 32);
  ResumeHandle[1] = 1;
  v5 = OpenSCManagerW(0, L"ServicesActive", 4u);
  v20[0] = v5;
  pcbBytesNeeded = 0;
  ServicesReturned = 0;
  ResumeHandle[0] = 0;
  if ( EnumServicesStatusExW(
         v5,
         SC_ENUM_PROCESS_INFO,
         0x30u,
         1u,
         0,
         0,
         &pcbBytesNeeded,
         &ServicesReturned,
         ResumeHandle,
         0) )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8AF,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)0x8000FFFFLL,
      lpServices);
  }
  if ( GetLastError() != 234 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8B3,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v6);
  std::make_unique<unsigned char [0],0>(&v19, pcbBytesNeeded);
  v7 = v19;
  if ( !EnumServicesStatusExW(
          v5,
          SC_ENUM_PROCESS_INFO,
          0x30u,
          1u,
          v19,
          pcbBytesNeeded,
          &pcbBytesNeeded,
          &ServicesReturned,
          ResumeHandle,
          0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8BA,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v8);
  v9 = 0;
  for ( i = ServicesReturned; v9 < i; ++v9 )
  {
    v11 = 56LL * v9;
    if ( *(_DWORD *)&v7[v11 + 44] == a2 )
    {
      v12 = std::_WChar_traits<unsigned short>::length(*(_QWORD *)&v7[v11]);
      std::wstring::_Append<unsigned short>(a1 + 4, v13, v12);
      v14 = std::_WChar_traits<unsigned short>::length(*(_QWORD *)&v7[v11 + 8]);
      std::wstring::_Append<unsigned short>(a1, v15, v14);
      i = ServicesReturned;
    }
  }
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v19);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v20);
  return a1;
}

```

## disassembly

```asm
0x180042e08  mov     [rsp-38h+arg_0], rcx
0x180042e0d  push    rbp
0x180042e0e  push    rbx
0x180042e0f  push    rsi
0x180042e10  push    rdi
0x180042e11  push    r12
0x180042e13  push    r14
0x180042e15  push    r15
0x180042e17  mov     rbp, rsp
0x180042e1a  sub     rsp, 70h
0x180042e1e  mov     r15d, edx
0x180042e21  mov     r14, rcx
0x180042e24  mov     [rbp+var_1C], 0
0x180042e2b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180042e30  add     rcx, 20h ; ' '
0x180042e34  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180042e39  mov     edi, 1
0x180042e3e  mov     [rbp+var_1C], edi
0x180042e41  lea     r8d, [rdi+3]; dwDesiredAccess
0x180042e45  lea     rdx, DatabaseName; "ServicesActive"
0x180042e4c  xor     ecx, ecx; lpMachineName
0x180042e4e  call    cs:__imp_OpenSCManagerW
0x180042e54  mov     rbx, rax
0x180042e57  mov     [rbp+var_10], rax
0x180042e5b  mov     [rbp+arg_10], 0
0x180042e62  mov     [rbp+ServicesReturned], 0
0x180042e69  mov     [rbp+ResumeHandle], 0
0x180042e70  mov     [rsp+70h+pszGroupName], 0; pszGroupName
0x180042e79  lea     rax, [rbp+ResumeHandle]
0x180042e7d  mov     [rsp+70h+lpResumeHandle], rax; lpResumeHandle
0x180042e82  lea     rax, [rbp+ServicesReturned]
0x180042e86  mov     [rsp+70h+lpServicesReturned], rax; lpServicesReturned
0x180042e8b  lea     rax, [rbp+arg_10]
0x180042e8f  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180042e94  mov     [rsp+70h+cbBufSize], 0; cbBufSize
0x180042e9c  mov     [rsp+70h+lpServices], 0; int
0x180042ea5  mov     r9d, edi; dwServiceState
0x180042ea8  xor     edx, edx; InfoLevel
0x180042eaa  lea     r8d, [rdi+2Fh]; dwServiceType
0x180042eae  mov     rcx, rbx; hSCManager
0x180042eb1  call    cs:__imp_EnumServicesStatusExW
0x180042eb7  test    eax, eax
0x180042eb9  jz      short loc_180042ED7
0x180042ebb  mov     rcx, [rbp+38h]; this
0x180042ebf  mov     r9d, 8000FFFFh; char *
0x180042ec5  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180042ecc  mov     edx, 8AFh; void *
0x180042ed1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042ed7  call    cs:__imp_GetLastError
0x180042edd  cmp     eax, 0EAh
0x180042ee2  jz      short loc_180042EFA
0x180042ee4  mov     rcx, [rbp+38h]; this
0x180042ee8  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180042eef  mov     edx, 8B3h; void *
0x180042ef4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180042efa  mov     edx, [rbp+arg_10]
0x180042efd  lea     rcx, [rbp+var_18]
0x180042f01  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180042f06  nop
0x180042f07  mov     eax, [rbp+arg_10]
0x180042f0a  mov     rdi, [rbp+38h]
0x180042f0e  mov     [rsp+70h+pszGroupName], 0; pszGroupName
0x180042f17  lea     rcx, [rbp+ResumeHandle]
0x180042f1b  mov     [rsp+70h+lpResumeHandle], rcx; lpResumeHandle
0x180042f20  lea     rcx, [rbp+ServicesReturned]
0x180042f24  mov     [rsp+70h+lpServicesReturned], rcx; lpServicesReturned
0x180042f29  lea     rcx, [rbp+arg_10]
0x180042f2d  mov     [rsp+70h+pcbBytesNeeded], rcx; pcbBytesNeeded
0x180042f32  mov     [rsp+70h+cbBufSize], eax; cbBufSize
0x180042f36  mov     rsi, [rbp+var_18]
0x180042f3a  mov     [rsp+70h+lpServices], rsi; lpServices
0x180042f3f  xor     edx, edx; InfoLevel
0x180042f41  lea     r9d, [rdx+1]; dwServiceState
0x180042f45  lea     r8d, [rdx+30h]; dwServiceType
0x180042f49  mov     rcx, rbx; hSCManager
0x180042f4c  call    cs:__imp_EnumServicesStatusExW
0x180042f52  test    eax, eax
0x180042f54  jnz     short loc_180042F6B
0x180042f56  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180042f5d  mov     edx, 8BAh; void *
0x180042f62  mov     rcx, rdi; this
0x180042f65  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180042f6b  xor     ebx, ebx
0x180042f6d  mov     ecx, [rbp+ServicesReturned]
0x180042f70  test    ecx, ecx
0x180042f72  jz      short loc_180042FBA
0x180042f74  mov     eax, ebx
0x180042f76  imul    rdi, rax, 38h ; '8'
0x180042f7a  cmp     [rdi+rsi+2Ch], r15d
0x180042f7f  jnz     short loc_180042FB4
0x180042f81  mov     rcx, [rdi+rsi]
0x180042f85  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180042f8a  mov     r8, rax
0x180042f8d  mov     rdx, rcx
0x180042f90  lea     rcx, [r14+20h]
0x180042f94  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180042f99  mov     rcx, [rdi+rsi+8]
0x180042f9e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180042fa3  mov     r8, rax
0x180042fa6  mov     rdx, rcx
0x180042fa9  mov     rcx, r14
0x180042fac  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180042fb1  mov     ecx, [rbp+ServicesReturned]
0x180042fb4  inc     ebx
0x180042fb6  cmp     ebx, ecx
0x180042fb8  jb      short loc_180042F74
0x180042fba  lea     rcx, [rbp+var_18]
0x180042fbe  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180042fc3  nop
0x180042fc4  lea     rcx, [rbp+var_10]
0x180042fc8  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180042fcd  mov     rax, r14
0x180042fd0  add     rsp, 70h
0x180042fd4  pop     r15
0x180042fd6  pop     r14
0x180042fd8  pop     r12
0x180042fda  pop     rdi
0x180042fdb  pop     rsi
0x180042fdc  pop     rbx
0x180042fdd  pop     rbp
0x180042fde  retn
```
