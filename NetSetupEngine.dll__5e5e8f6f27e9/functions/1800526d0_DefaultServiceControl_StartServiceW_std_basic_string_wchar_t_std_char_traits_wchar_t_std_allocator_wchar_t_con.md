# DefaultServiceControl::StartServiceW(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800526d0`
- end: `0x1800527f1`
- name: `?StartServiceW@DefaultServiceControl@@UEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task`

## callees

- `0x18001dee8`
- `0x18005097c`
- `0x1800526d0`
- `0x180052944`
- `0x1800530a8`
- `0x180065035`
- `0x180078c64`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005278d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005278d`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18005273b`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18005273b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __fastcall DefaultServiceControl::StartServiceW(__int64 a1, const wchar_t *a2)
{
  const wchar_t *v3; // r8
  signed int LastError; // eax
  _BYTE pExceptionObject[208]; // [rsp+28h] [rbp-F0h] BYREF
  SC_HANDLE hService; // [rsp+F8h] [rbp-20h] BYREF
  SC_HANDLE v8; // [rsp+100h] [rbp-18h] BYREF

  SafeScmHandle::SafeScmHandle((SafeScmHandle *)&v8);
  if ( *((_QWORD *)a2 + 3) < 8u )
    v3 = a2;
  else
    v3 = *(const wchar_t **)a2;
  SafeServiceHandle::SafeServiceHandle((SafeServiceHandle *)&hService, &v8, v3, 0x10u);
  if ( !StartServiceW(hService, 0, 0) && GetLastError() != 1056 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( *((_QWORD *)a2 + 3) >= 8u )
        a2 = *(const wchar_t **)a2;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_eecf0a69fc4a3f7219213d296c76a52c_Traceguids, a2);
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
0x1800526d0  mov     r11, rsp
0x1800526d3  push    rbx
0x1800526d4  sub     rsp, 110h
0x1800526db  mov     [rsp+118h+var_F8], 0FFFFFFFFFFFFFFFEh
0x1800526e4  mov     rax, cs:__security_cookie
0x1800526eb  xor     rax, rsp
0x1800526ee  mov     [rsp+118h+var_10], rax
0x1800526f6  mov     rbx, rdx
0x1800526f9  lea     rcx, [r11-18h]; this
0x1800526fd  call    ??0SafeScmHandle@@QEAA@K@Z; SafeScmHandle::SafeScmHandle(ulong)
0x180052702  nop
0x180052703  cmp     qword ptr [rbx+18h], 8
0x180052708  jb      short loc_18005270F
0x18005270a  mov     r8, [rbx]
0x18005270d  jmp     short loc_180052712
0x18005270f  mov     r8, rbx; wchar_t *
0x180052712  mov     r9d, 10h; unsigned int
0x180052718  lea     rdx, [rsp+118h+var_18]; struct SafeScmHandle *
0x180052720  lea     rcx, [rsp+118h+hService]; this
0x180052728  call    ??0SafeServiceHandle@@QEAA@AEAVSafeScmHandle@@PEB_WK@Z; SafeServiceHandle::SafeServiceHandle(SafeScmHandle &,wchar_t const *,ulong)
0x18005272d  nop
0x18005272e  xor     r8d, r8d; lpServiceArgVectors
0x180052731  xor     edx, edx; dwNumServiceArgs
0x180052733  mov     rcx, [rsp+118h+hService]; hService
0x18005273b  call    cs:__imp_StartServiceW
0x180052741  test    eax, eax
0x180052743  jnz     short loc_1800527BD
0x180052745  call    cs:__imp_GetLastError
0x18005274b  cmp     eax, 420h
0x180052750  jz      short loc_1800527BD
0x180052752  lea     rax, WPP_GLOBAL_Control
0x180052759  mov     rcx, cs:WPP_GLOBAL_Control
0x180052760  cmp     rcx, rax
0x180052763  jz      short loc_18005278D
0x180052765  cmp     byte ptr [rcx+19h], 2
0x180052769  jb      short loc_18005278D
0x18005276b  cmp     qword ptr [rbx+18h], 8
0x180052770  jb      short loc_180052775
0x180052772  mov     rbx, [rbx]
0x180052775  mov     edx, 0Ah
0x18005277a  mov     r9, rbx
0x18005277d  lea     r8, WPP_eecf0a69fc4a3f7219213d296c76a52c_Traceguids
0x180052784  mov     rcx, [rcx+10h]
0x180052788  call    WPP_SF_S
0x18005278d  call    cs:__imp_GetLastError
0x180052793  test    eax, eax
0x180052795  jle     short loc_18005279F
0x180052797  movzx   eax, ax
0x18005279a  or      eax, 80070000h
0x18005279f  mov     edx, eax; int
0x1800527a1  lea     rcx, [rsp+118h+pExceptionObject]; this
0x1800527a6  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800527ab  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800527b2  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x1800527b7  call    _CxxThrowException_0
0x1800527bd  lea     rcx, [rsp+118h+hService]
0x1800527c5  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800527ca  nop
0x1800527cb  lea     rcx, [rsp+118h+var_18]
0x1800527d3  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800527d8  mov     rcx, [rsp+118h+var_10]
0x1800527e0  xor     rcx, rsp; StackCookie
0x1800527e3  call    __security_check_cookie
0x1800527e8  add     rsp, 110h
0x1800527ef  pop     rbx
0x1800527f0  retn
```
