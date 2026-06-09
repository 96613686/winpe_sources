# DefaultServiceControl::StopService(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180052800`
- end: `0x18005293c`
- name: `?StopService@DefaultServiceControl@@UEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `316`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task`

## callees

- `0x18001dee8`
- `0x18005097c`
- `0x180052800`
- `0x180052944`
- `0x1800530a8`
- `0x180065035`
- `0x180078c64`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800528d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800528d8`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180052886`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180052886`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __fastcall DefaultServiceControl::StopService(__int64 a1, const wchar_t *a2)
{
  const wchar_t *v3; // r8
  signed int LastError; // eax
  _BYTE pExceptionObject[208]; // [rsp+28h] [rbp-110h] BYREF
  SC_HANDLE hService; // [rsp+F8h] [rbp-40h] BYREF
  SC_HANDLE v8; // [rsp+100h] [rbp-38h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+108h] [rbp-30h] BYREF

  SafeScmHandle::SafeScmHandle((SafeScmHandle *)&v8);
  if ( *((_QWORD *)a2 + 3) < 8u )
    v3 = a2;
  else
    v3 = *(const wchar_t **)a2;
  SafeServiceHandle::SafeServiceHandle((SafeServiceHandle *)&hService, &v8, v3, 0x20u);
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( !ControlService(hService, 1u, &ServiceStatus) && GetLastError() != 1062 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( *((_QWORD *)a2 + 3) >= 8u )
        a2 = *(const wchar_t **)a2;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_eecf0a69fc4a3f7219213d296c76a52c_Traceguids, a2);
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, LastError);
    throw (HResultException *)pExceptionObject;
  }
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&hService);
  return wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v8);
}

```

## disassembly

```asm
0x180052800  mov     r11, rsp
0x180052803  push    rbx
0x180052804  sub     rsp, 130h
0x18005280b  mov     [rsp+138h+var_118], 0FFFFFFFFFFFFFFFEh
0x180052814  mov     rax, cs:__security_cookie
0x18005281b  xor     rax, rsp
0x18005281e  mov     [rsp+138h+var_10], rax
0x180052826  mov     rbx, rdx
0x180052829  lea     rcx, [r11-38h]; this
0x18005282d  call    ??0SafeScmHandle@@QEAA@K@Z; SafeScmHandle::SafeScmHandle(ulong)
0x180052832  nop
0x180052833  cmp     qword ptr [rbx+18h], 8
0x180052838  jb      short loc_18005283F
0x18005283a  mov     r8, [rbx]
0x18005283d  jmp     short loc_180052842
0x18005283f  mov     r8, rbx; wchar_t *
0x180052842  mov     r9d, 20h ; ' '; unsigned int
0x180052848  lea     rdx, [rsp+138h+var_38]; struct SafeScmHandle *
0x180052850  lea     rcx, [rsp+138h+hService]; this
0x180052858  call    ??0SafeServiceHandle@@QEAA@AEAVSafeScmHandle@@PEB_WK@Z; SafeServiceHandle::SafeServiceHandle(SafeScmHandle &,wchar_t const *,ulong)
0x18005285d  nop
0x18005285e  xorps   xmm0, xmm0
0x180052861  movups  xmmword ptr [rsp+138h+ServiceStatus.dwServiceType], xmm0
0x180052869  movups  xmmword ptr [rsp+138h+ServiceStatus.dwWin32ExitCode], xmm0
0x180052871  lea     r8, [rsp+138h+ServiceStatus]; lpServiceStatus
0x180052879  mov     edx, 1; dwControl
0x18005287e  mov     rcx, [rsp+138h+hService]; hService
0x180052886  call    cs:__imp_ControlService
0x18005288c  test    eax, eax
0x18005288e  jnz     short loc_180052908
0x180052890  call    cs:__imp_GetLastError
0x180052896  cmp     eax, 426h
0x18005289b  jz      short loc_180052908
0x18005289d  lea     rax, WPP_GLOBAL_Control
0x1800528a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800528ab  cmp     rcx, rax
0x1800528ae  jz      short loc_1800528D8
0x1800528b0  cmp     byte ptr [rcx+19h], 2
0x1800528b4  jb      short loc_1800528D8
0x1800528b6  cmp     qword ptr [rbx+18h], 8
0x1800528bb  jb      short loc_1800528C0
0x1800528bd  mov     rbx, [rbx]
0x1800528c0  mov     edx, 0Bh
0x1800528c5  mov     r9, rbx
0x1800528c8  lea     r8, WPP_eecf0a69fc4a3f7219213d296c76a52c_Traceguids
0x1800528cf  mov     rcx, [rcx+10h]
0x1800528d3  call    WPP_SF_S
0x1800528d8  call    cs:__imp_GetLastError
0x1800528de  test    eax, eax
0x1800528e0  jle     short loc_1800528EA
0x1800528e2  movzx   eax, ax
0x1800528e5  or      eax, 80070000h
0x1800528ea  mov     edx, eax; int
0x1800528ec  lea     rcx, [rsp+138h+pExceptionObject]; this
0x1800528f1  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800528f6  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800528fd  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x180052902  call    _CxxThrowException_0
0x180052908  lea     rcx, [rsp+138h+hService]
0x180052910  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180052915  nop
0x180052916  lea     rcx, [rsp+138h+var_38]
0x18005291e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180052923  mov     rcx, [rsp+138h+var_10]
0x18005292b  xor     rcx, rsp; StackCookie
0x18005292e  call    __security_check_cookie
0x180052933  add     rsp, 130h
0x18005293a  pop     rbx
0x18005293b  retn
```
