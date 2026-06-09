# Microsoft::Diagnostics::FilterFunction::CallServiceFunctionHelper(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,bool)

- ea: `0x1802cbf0c`
- end: `0x1802cc187`
- name: `?CallServiceFunctionHelper@FilterFunction@Diagnostics@Microsoft@@SA?AU?$pair@JV?$variant@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_J_KN@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@_N1@Z`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802cdc90`

## callees

- `0x18002b7c0`
- `0x18002df00`
- `0x18003d318`
- `0x1801a9494`
- `0x1801b2084`
- `0x18020aac0`
- `0x1802c8f84`
- `0x1802cab40`
- `0x1802cbf0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802cbf83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802cbffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802cbf83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802cbffa`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1802cc0d0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1802cc0d0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1802cbfd9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1802cbfd9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1802cbf75`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1802cbf75`

## string_xrefs

- `0x1802cbfa5`: `onecore\base\telemetry\utc\service\scenarios\filters\scriptfilternodes.cpp`
- `0x1802cc071`: `onecore\base\telemetry\utc\service\scenarios\filters\scriptfilternodes.cpp`
- `0x1802cc0e2`: `onecore\base\telemetry\utc\service\scenarios\filters\scriptfilternodes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
_DWORD *__fastcall Microsoft::Diagnostics::FilterFunction::CallServiceFunctionHelper(
        _DWORD *a1,
        __int64 a2,
        char a3,
        char a4)
{
  SC_HANDLE v9; // rbx
  signed int LastError; // eax
  __int64 v11; // rax
  SC_HANDLE v12; // rbx
  DWORD v13; // eax
  _DWORD *v14; // rcx
  const char *v15; // r9
  char v16; // al
  _DWORD *v17; // rcx
  unsigned int v18[2]; // [rsp+20h] [rbp-88h] BYREF
  _QWORD v19[3]; // [rsp+28h] [rbp-80h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v19[1] = a1;
  if ( !a3 && a4 )
  {
    *a1 = 0;
    std::variant<std::wstring,__int64,unsigned __int64,double>::variant<std::wstring,__int64,unsigned __int64,double>(
      a1 + 2,
      qword_1803A06E0);
    return a1;
  }
  v9 = OpenSCManagerW(0, 0, 4u);
  v19[0] = v9;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( !v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5DF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\scriptfilternodes.cpp",
      (const char *)(unsigned int)LastError,
      v18[0]);
  v11 = std::wstring::wstring(v21, a2);
  if ( *(_QWORD *)(v11 + 24) > 7u )
    v11 = *(_QWORD *)v11;
  v12 = OpenServiceW(v9, (LPCWSTR)v11, 4u);
  *(_QWORD *)v18 = v12;
  std::wstring::_Tidy_deallocate(v21);
  if ( !v12 )
  {
    v13 = GetLastError();
    if ( v13 != 1060 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5F5,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\scriptfilternodes.cpp",
        (const char *)v13,
        v18[0]);
    *a1 = 0;
    v14 = a1 + 2;
    if ( a3 )
      std::variant<std::wstring,__int64,unsigned __int64,double>::variant<std::wstring,__int64,unsigned __int64,double>(
        v14,
        qword_1803A06E0);
    else
      std::variant<std::wstring,__int64,unsigned __int64,double>::variant<std::wstring,__int64,unsigned __int64,double>(
        v14,
        &qword_1803A06D8);
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v18);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v19);
    return a1;
  }
  if ( a3 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !QueryServiceStatus(v12, &ServiceStatus) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x602,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\scriptfilternodes.cpp",
        v15);
    v16 = ServiceStatus.dwCurrentState == 4;
    *a1 = 0;
    v17 = a1 + 2;
    if ( a4 == v16 )
      std::variant<std::wstring,__int64,unsigned __int64,double>::variant<std::wstring,__int64,unsigned __int64,double>(
        v17,
        &qword_1803A06D8);
    else
      std::variant<std::wstring,__int64,unsigned __int64,double>::variant<std::wstring,__int64,unsigned __int64,double>(
        v17,
        qword_1803A06E0);
    goto LABEL_14;
  }
  *a1 = 0;
  std::variant<std::wstring,__int64,unsigned __int64,double>::variant<std::wstring,__int64,unsigned __int64,double>(
    a1 + 2,
    qword_1803A06E0);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v18);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v19);
  return a1;
}

```

## disassembly

```asm
0x1802cbf0c  mov     [rsp+arg_10], rbx
0x1802cbf11  mov     [rsp+arg_18], rsi
0x1802cbf16  push    rdi
0x1802cbf17  push    r14
0x1802cbf19  push    r15
0x1802cbf1b  sub     rsp, 90h
0x1802cbf22  mov     rax, cs:__security_cookie
0x1802cbf29  xor     rax, rsp
0x1802cbf2c  mov     [rsp+0A8h+var_28], rax
0x1802cbf34  mov     r14b, r9b
0x1802cbf37  mov     sil, r8b
0x1802cbf3a  mov     r15, rdx
0x1802cbf3d  mov     rdi, rcx
0x1802cbf40  mov     [rsp+0A8h+var_78], rcx
0x1802cbf45  test    r8b, r8b
0x1802cbf48  jnz     short loc_1802CBF6D
0x1802cbf4a  test    r9b, r9b
0x1802cbf4d  jz      short loc_1802CBF6D
0x1802cbf4f  mov     dword ptr [rcx], 0
0x1802cbf55  add     rcx, 8
0x1802cbf59  lea     rdx, qword_1803A06E0
0x1802cbf60  call    ??$?0AEB_K$0A@$0A@@?$variant@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_J_KN@std@@QEAA@AEB_K@Z; std::variant<std::wstring,__int64,unsigned __int64,double>::variant<std::wstring,__int64,unsigned __int64,double>(unsigned __int64 const &)
0x1802cbf65  mov     rax, rdi
0x1802cbf68  jmp     loc_1802CC15D
0x1802cbf6d  xor     edx, edx; lpDatabaseName
0x1802cbf6f  xor     ecx, ecx; lpMachineName
0x1802cbf71  lea     r8d, [rdx+4]; dwDesiredAccess
0x1802cbf75  call    cs:__imp_OpenSCManagerW
0x1802cbf7b  mov     rbx, rax
0x1802cbf7e  mov     [rsp+0A8h+var_80], rax
0x1802cbf83  call    cs:__imp_GetLastError
0x1802cbf89  test    eax, eax
0x1802cbf8b  jle     short loc_1802CBF95
0x1802cbf8d  movzx   eax, ax
0x1802cbf90  or      eax, 80070000h
0x1802cbf95  mov     rcx, [rsp+0A8h]; this
0x1802cbf9d  test    rbx, rbx
0x1802cbfa0  jnz     short loc_1802CBFB6
0x1802cbfa2  mov     r9d, eax; char *
0x1802cbfa5  lea     r8, aOnecoreBaseTel_34; "onecore\\base\\telemetry\\utc\\service"...
0x1802cbfac  mov     edx, 5DFh; void *
0x1802cbfb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802cbfb6  mov     rdx, r15
0x1802cbfb9  lea     rcx, [rsp+0A8h+var_48]
0x1802cbfbe  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1802cbfc3  cmp     qword ptr [rax+18h], 7
0x1802cbfc8  jbe     short loc_1802CBFCD
0x1802cbfca  mov     rax, [rax]
0x1802cbfcd  mov     r8d, 4; dwDesiredAccess
0x1802cbfd3  mov     rdx, rax; lpServiceName
0x1802cbfd6  mov     rcx, rbx; hSCManager
0x1802cbfd9  call    cs:__imp_OpenServiceW
0x1802cbfdf  mov     rbx, rax
0x1802cbfe2  mov     qword ptr [rsp+0A8h+var_88], rax; unsigned int
0x1802cbfe7  lea     rcx, [rsp+0A8h+var_48]
0x1802cbfec  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802cbff1  test    rbx, rbx
0x1802cbff4  jnz     loc_1802CC082
0x1802cbffa  call    cs:__imp_GetLastError
0x1802cc000  cmp     eax, 424h
0x1802cc005  jnz     short loc_1802CC066
0x1802cc007  mov     [rdi], ebx
0x1802cc009  lea     rcx, [rdi+8]
0x1802cc00d  test    sil, sil
0x1802cc010  jz      short loc_1802CC03C
0x1802cc012  lea     rdx, qword_1803A06E0
0x1802cc019  call    ??$?0AEB_K$0A@$0A@@?$variant@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_J_KN@std@@QEAA@AEB_K@Z; std::variant<std::wstring,__int64,unsigned __int64,double>::variant<std::wstring,__int64,unsigned __int64,double>(unsigned __int64 const &)
0x1802cc01e  nop
0x1802cc01f  lea     rcx, [rsp+0A8h+var_88]
0x1802cc024  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802cc029  nop
0x1802cc02a  lea     rcx, [rsp+0A8h+var_80]
0x1802cc02f  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802cc034  mov     rax, rdi
0x1802cc037  jmp     loc_1802CC15D
0x1802cc03c  lea     rdx, qword_1803A06D8
0x1802cc043  call    ??$?0AEB_K$0A@$0A@@?$variant@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_J_KN@std@@QEAA@AEB_K@Z; std::variant<std::wstring,__int64,unsigned __int64,double>::variant<std::wstring,__int64,unsigned __int64,double>(unsigned __int64 const &)
0x1802cc048  nop
0x1802cc049  lea     rcx, [rsp+0A8h+var_88]
0x1802cc04e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802cc053  nop
0x1802cc054  lea     rcx, [rsp+0A8h+var_80]
0x1802cc059  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802cc05e  mov     rax, rdi
0x1802cc061  jmp     loc_1802CC15D
0x1802cc066  mov     rcx, [rsp+0A8h]; this
0x1802cc06e  mov     r9d, eax; char *
0x1802cc071  lea     r8, aOnecoreBaseTel_34; "onecore\\base\\telemetry\\utc\\service"...
0x1802cc078  mov     edx, 5F5h; void *
0x1802cc07d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1802cc082  test    sil, sil
0x1802cc085  jnz     short loc_1802CC0BB
0x1802cc087  mov     dword ptr [rdi], 0
0x1802cc08d  lea     rcx, [rdi+8]
0x1802cc091  lea     rdx, qword_1803A06E0
0x1802cc098  call    ??$?0AEB_K$0A@$0A@@?$variant@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_J_KN@std@@QEAA@AEB_K@Z; std::variant<std::wstring,__int64,unsigned __int64,double>::variant<std::wstring,__int64,unsigned __int64,double>(unsigned __int64 const &)
0x1802cc09d  nop
0x1802cc09e  lea     rcx, [rsp+0A8h+var_88]
0x1802cc0a3  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802cc0a8  nop
0x1802cc0a9  lea     rcx, [rsp+0A8h+var_80]
0x1802cc0ae  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802cc0b3  mov     rax, rdi
0x1802cc0b6  jmp     loc_1802CC15D
0x1802cc0bb  xorps   xmm0, xmm0
0x1802cc0be  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwServiceType], xmm0
0x1802cc0c3  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwWin32ExitCode], xmm0
0x1802cc0c8  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x1802cc0cd  mov     rcx, rbx; hService
0x1802cc0d0  call    cs:__imp_QueryServiceStatus
0x1802cc0d6  test    eax, eax
0x1802cc0d8  jnz     short loc_1802CC0F3
0x1802cc0da  mov     rcx, [rsp+0A8h]; this
0x1802cc0e2  lea     r8, aOnecoreBaseTel_34; "onecore\\base\\telemetry\\utc\\service"...
0x1802cc0e9  mov     edx, 602h; void *
0x1802cc0ee  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1802cc0f3  cmp     [rsp+0A8h+ServiceStatus.dwCurrentState], 4
0x1802cc0f8  setz    al
0x1802cc0fb  mov     dword ptr [rdi], 0
0x1802cc101  lea     rcx, [rdi+8]
0x1802cc105  cmp     r14b, al
0x1802cc108  jnz     short loc_1802CC131
0x1802cc10a  lea     rdx, qword_1803A06D8
0x1802cc111  call    ??$?0AEB_K$0A@$0A@@?$variant@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_J_KN@std@@QEAA@AEB_K@Z; std::variant<std::wstring,__int64,unsigned __int64,double>::variant<std::wstring,__int64,unsigned __int64,double>(unsigned __int64 const &)
0x1802cc116  nop
0x1802cc117  lea     rcx, [rsp+0A8h+var_88]
0x1802cc11c  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802cc121  nop
0x1802cc122  lea     rcx, [rsp+0A8h+var_80]
0x1802cc127  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802cc12c  mov     rax, rdi
0x1802cc12f  jmp     short loc_1802CC15D
0x1802cc131  lea     rdx, qword_1803A06E0
0x1802cc138  call    ??$?0AEB_K$0A@$0A@@?$variant@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_J_KN@std@@QEAA@AEB_K@Z; std::variant<std::wstring,__int64,unsigned __int64,double>::variant<std::wstring,__int64,unsigned __int64,double>(unsigned __int64 const &)
0x1802cc13d  nop
0x1802cc13e  lea     rcx, [rsp+0A8h+var_88]
0x1802cc143  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802cc148  nop
0x1802cc149  lea     rcx, [rsp+0A8h+var_80]
0x1802cc14e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802cc153  mov     rax, rdi
0x1802cc156  jmp     short loc_1802CC15D
0x1802cc158  mov     rax, [rsp+0A8h+var_78]
0x1802cc15d  mov     rcx, [rsp+0A8h+var_28]
0x1802cc165  xor     rcx, rsp; StackCookie
0x1802cc168  call    __security_check_cookie
0x1802cc16d  lea     r11, [rsp+0A8h+var_18]
0x1802cc175  mov     rbx, [r11+30h]
0x1802cc179  mov     rsi, [r11+38h]
0x1802cc17d  mov     rsp, r11
0x1802cc180  pop     r15
0x1802cc182  pop     r14
0x1802cc184  pop     rdi
0x1802cc185  retn
```
