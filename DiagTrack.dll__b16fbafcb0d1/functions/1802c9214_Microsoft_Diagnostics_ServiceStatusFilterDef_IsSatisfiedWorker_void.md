# Microsoft::Diagnostics::ServiceStatusFilterDef::IsSatisfiedWorker(void)

- ea: `0x1802c9214`
- end: `0x1802c9419`
- name: `?IsSatisfiedWorker@ServiceStatusFilterDef@Diagnostics@Microsoft@@AEBA?AU?$pair@JVResult@Filters@Diagnostics@Microsoft@@@std@@XZ`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802c9b60`

## callees

- `0x18003d318`
- `0x1801a9494`
- `0x1801b2084`
- `0x18020aac0`
- `0x1802c8f84`
- `0x1802c9214`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802c926e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802c92c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802c926e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802c92c3`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1802c937d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1802c937d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1802c92b3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1802c92b3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1802c9260`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1802c9260`

## string_xrefs

- `0x1802c928d`: `onecore\base\telemetry\utc\service\scenarios\filters\servicestatusfilter.cpp`
- `0x1802c932d`: `onecore\base\telemetry\utc\service\scenarios\filters\servicestatusfilter.cpp`
- `0x1802c938c`: `onecore\base\telemetry\utc\service\scenarios\filters\servicestatusfilter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::ServiceStatusFilterDef::IsSatisfiedWorker(__int64 a1, __int64 a2)
{
  SC_HANDLE v5; // rbx
  signed int LastError; // eax
  const WCHAR *v7; // rdx
  SC_HANDLE v8; // rax
  DWORD v9; // eax
  char v10; // al
  const char *v11; // r9
  char v12; // cl
  char v13; // al
  unsigned int v14[2]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v15[2]; // [rsp+28h] [rbp-40h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v15[1] = a2;
  if ( !*(_BYTE *)(a1 + 88) && *(_BYTE *)(a1 + 89) )
  {
    *(_QWORD *)a2 = 0;
    return a2;
  }
  v5 = OpenSCManagerW(0, 0, 4u);
  v15[0] = v5;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( !v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\servicestatusfilter.cpp",
      (const char *)(unsigned int)LastError,
      v14[0]);
  v7 = (const WCHAR *)(a1 + 56);
  if ( *(_QWORD *)(a1 + 80) > 7u )
    v7 = *(const WCHAR **)v7;
  v8 = OpenServiceW(v5, v7, 4u);
  *(_QWORD *)v14 = v8;
  if ( !v8 )
  {
    v9 = GetLastError();
    if ( v9 != 1060 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x84,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\servicestatusfilter.cpp",
        (const char *)v9,
        v14[0]);
    v10 = *(_BYTE *)(a1 + 88);
    *(_DWORD *)a2 = 0;
    if ( v10 )
      *(_DWORD *)(a2 + 4) = 0;
    else
      *(_DWORD *)(a2 + 4) = 1;
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v14);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v15);
    return a2;
  }
  if ( *(_BYTE *)(a1 + 88) )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !QueryServiceStatus(v8, &ServiceStatus) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\servicestatusfilter.cpp",
        v11);
    v12 = ServiceStatus.dwCurrentState == 4;
    v13 = *(_BYTE *)(a1 + 89);
    *(_DWORD *)a2 = 0;
    *(_DWORD *)(a2 + 4) = v13 == v12;
    goto LABEL_14;
  }
  *(_QWORD *)a2 = 0;
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v14);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v15);
  return a2;
}

```

## disassembly

```asm
0x1802c9214  mov     [rsp+arg_10], rbx
0x1802c9219  mov     [rsp+arg_18], rsi
0x1802c921e  push    rdi
0x1802c921f  sub     rsp, 60h
0x1802c9223  mov     rax, cs:__security_cookie
0x1802c922a  xor     rax, rsp
0x1802c922d  mov     [rsp+68h+var_10], rax
0x1802c9232  mov     rdi, rdx
0x1802c9235  mov     rsi, rcx
0x1802c9238  mov     [rsp+68h+var_38], rdx
0x1802c923d  cmp     byte ptr [rcx+58h], 0
0x1802c9241  jnz     short loc_1802C9258
0x1802c9243  cmp     byte ptr [rcx+59h], 0
0x1802c9247  jz      short loc_1802C9258
0x1802c9249  mov     qword ptr [rdx], 0
0x1802c9250  mov     rax, rdx
0x1802c9253  jmp     loc_1802C93F9
0x1802c9258  xor     edx, edx; lpDatabaseName
0x1802c925a  xor     ecx, ecx; lpMachineName
0x1802c925c  lea     r8d, [rdx+4]; dwDesiredAccess
0x1802c9260  call    cs:__imp_OpenSCManagerW
0x1802c9266  mov     rbx, rax
0x1802c9269  mov     [rsp+68h+var_40], rax
0x1802c926e  call    cs:__imp_GetLastError
0x1802c9274  test    eax, eax
0x1802c9276  jle     short loc_1802C9280
0x1802c9278  movzx   eax, ax
0x1802c927b  or      eax, 80070000h
0x1802c9280  mov     rcx, [rsp+68h]; this
0x1802c9285  test    rbx, rbx
0x1802c9288  jnz     short loc_1802C929C
0x1802c928a  mov     r9d, eax; char *
0x1802c928d  lea     r8, aOnecoreBaseTel_128; "onecore\\base\\telemetry\\utc\\service"...
0x1802c9294  lea     edx, [rbx+6Eh]; void *
0x1802c9297  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802c929c  lea     rdx, [rsi+38h]
0x1802c92a0  cmp     qword ptr [rdx+18h], 7
0x1802c92a5  jbe     short loc_1802C92AA
0x1802c92a7  mov     rdx, [rdx]; lpServiceName
0x1802c92aa  mov     r8d, 4; dwDesiredAccess
0x1802c92b0  mov     rcx, rbx; hSCManager
0x1802c92b3  call    cs:__imp_OpenServiceW
0x1802c92b9  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x1802c92be  test    rax, rax
0x1802c92c1  jnz     short loc_1802C933E
0x1802c92c3  call    cs:__imp_GetLastError
0x1802c92c9  cmp     eax, 424h
0x1802c92ce  jnz     short loc_1802C9325
0x1802c92d0  mov     al, [rsi+58h]
0x1802c92d3  mov     dword ptr [rdi], 0
0x1802c92d9  test    al, al
0x1802c92db  jz      short loc_1802C9301
0x1802c92dd  mov     dword ptr [rdi+4], 0
0x1802c92e4  lea     rcx, [rsp+68h+var_48]
0x1802c92e9  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802c92ee  nop
0x1802c92ef  lea     rcx, [rsp+68h+var_40]
0x1802c92f4  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802c92f9  mov     rax, rdi
0x1802c92fc  jmp     loc_1802C93F9
0x1802c9301  mov     dword ptr [rdi+4], 1
0x1802c9308  lea     rcx, [rsp+68h+var_48]
0x1802c930d  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802c9312  nop
0x1802c9313  lea     rcx, [rsp+68h+var_40]
0x1802c9318  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802c931d  mov     rax, rdi
0x1802c9320  jmp     loc_1802C93F9
0x1802c9325  mov     rcx, [rsp+68h]; this
0x1802c932a  mov     r9d, eax; char *
0x1802c932d  lea     r8, aOnecoreBaseTel_128; "onecore\\base\\telemetry\\utc\\service"...
0x1802c9334  mov     edx, 84h; void *
0x1802c9339  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1802c933e  cmp     byte ptr [rsi+58h], 0
0x1802c9342  jnz     short loc_1802C9368
0x1802c9344  mov     qword ptr [rdi], 0
0x1802c934b  lea     rcx, [rsp+68h+var_48]
0x1802c9350  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802c9355  nop
0x1802c9356  lea     rcx, [rsp+68h+var_40]
0x1802c935b  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802c9360  mov     rax, rdi
0x1802c9363  jmp     loc_1802C93F9
0x1802c9368  xorps   xmm0, xmm0
0x1802c936b  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x1802c9370  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x1802c9375  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x1802c937a  mov     rcx, rax; hService
0x1802c937d  call    cs:__imp_QueryServiceStatus
0x1802c9383  test    eax, eax
0x1802c9385  jnz     short loc_1802C939D
0x1802c9387  mov     rcx, [rsp+68h]; this
0x1802c938c  lea     r8, aOnecoreBaseTel_128; "onecore\\base\\telemetry\\utc\\service"...
0x1802c9393  mov     edx, 91h; void *
0x1802c9398  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1802c939d  cmp     [rsp+68h+ServiceStatus.dwCurrentState], 4
0x1802c93a2  setz    cl
0x1802c93a5  mov     al, [rsi+59h]
0x1802c93a8  mov     dword ptr [rdi], 0
0x1802c93ae  cmp     al, cl
0x1802c93b0  jnz     short loc_1802C93D3
0x1802c93b2  mov     dword ptr [rdi+4], 1
0x1802c93b9  lea     rcx, [rsp+68h+var_48]
0x1802c93be  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802c93c3  nop
0x1802c93c4  lea     rcx, [rsp+68h+var_40]
0x1802c93c9  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802c93ce  mov     rax, rdi
0x1802c93d1  jmp     short loc_1802C93F9
0x1802c93d3  mov     dword ptr [rdi+4], 0
0x1802c93da  lea     rcx, [rsp+68h+var_48]
0x1802c93df  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802c93e4  nop
0x1802c93e5  lea     rcx, [rsp+68h+var_40]
0x1802c93ea  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802c93ef  mov     rax, rdi
0x1802c93f2  jmp     short loc_1802C93F9
0x1802c93f4  mov     rax, [rsp+68h+var_38]
0x1802c93f9  mov     rcx, [rsp+68h+var_10]
0x1802c93fe  xor     rcx, rsp; StackCookie
0x1802c9401  call    __security_check_cookie
0x1802c9406  lea     r11, [rsp+68h+var_8]
0x1802c940b  mov     rbx, [r11+20h]
0x1802c940f  mov     rsi, [r11+28h]
0x1802c9413  mov     rsp, r11
0x1802c9416  pop     rdi
0x1802c9417  retn
```
