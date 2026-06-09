# ServiceHandler::ServiceHandler(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14007037c`
- end: `0x140070433`
- name: `??0ServiceHandler@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `183`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14006f494`

## callees

- `0x140029eb8`
- `0x140055c64`
- `0x140065fa4`
- `0x14007037c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400703b0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400703b0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400703f2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400703f2`

## string_xrefs

- `0x1400703cc`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`
- `0x14007040e`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`

## pseudocode

```c
_QWORD *__fastcall ServiceHandler::ServiceHandler(_QWORD *a1, __int64 a2)
{
  SC_HANDLE *v4; // rbx
  SC_HANDLE v5; // rax
  const char *v6; // r9
  const WCHAR *v7; // rax
  SC_HANDLE v8; // rax
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a1 = 0;
  v4 = (SC_HANDLE *)(a1 + 1);
  a1[1] = 0;
  v5 = OpenSCManagerW(0, 0, 1u);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
    v4,
    v5);
  if ( !*v4 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x15,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
      v6);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v8 = OpenServiceW(*v4, v7, 0xA0000000);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
    a1,
    v8);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1B,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
      v9);
  return a1;
}

```

## disassembly

```asm
0x14007037c  mov     [rsp+arg_8], rbx
0x140070381  mov     [rsp+arg_10], rsi
0x140070386  mov     [rsp+arg_0], rcx
0x14007038b  push    rdi
0x14007038c  sub     rsp, 20h
0x140070390  mov     rsi, rdx
0x140070393  mov     rdi, rcx
0x140070396  mov     qword ptr [rcx], 0
0x14007039d  lea     rbx, [rcx+8]
0x1400703a1  mov     qword ptr [rbx], 0
0x1400703a8  xor     edx, edx; lpDatabaseName
0x1400703aa  xor     ecx, ecx; lpMachineName
0x1400703ac  lea     r8d, [rdx+1]; dwDesiredAccess
0x1400703b0  call    cs:__imp_OpenSCManagerW
0x1400703b6  mov     rdx, rax
0x1400703b9  mov     rcx, rbx
0x1400703bc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x1400703c1  mov     rcx, [rsp+28h]; this
0x1400703c6  cmp     qword ptr [rbx], 0
0x1400703ca  jnz     short loc_1400703DE
0x1400703cc  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400703d3  mov     edx, 15h; void *
0x1400703d8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1400703de  mov     rcx, rsi
0x1400703e1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400703e6  mov     r8d, 0A0000000h; dwDesiredAccess
0x1400703ec  mov     rdx, rax; lpServiceName
0x1400703ef  mov     rcx, [rbx]; hSCManager
0x1400703f2  call    cs:__imp_OpenServiceW
0x1400703f8  mov     rdx, rax
0x1400703fb  mov     rcx, rdi
0x1400703fe  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x140070403  mov     rcx, [rsp+28h]; this
0x140070408  cmp     qword ptr [rdi], 0
0x14007040c  jnz     short loc_140070420
0x14007040e  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x140070415  mov     edx, 1Bh; void *
0x14007041a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140070420  mov     rax, rdi
0x140070423  mov     rbx, [rsp+28h+arg_8]
0x140070428  mov     rsi, [rsp+28h+arg_10]
0x14007042d  add     rsp, 20h
0x140070431  pop     rdi
0x140070432  retn
```
