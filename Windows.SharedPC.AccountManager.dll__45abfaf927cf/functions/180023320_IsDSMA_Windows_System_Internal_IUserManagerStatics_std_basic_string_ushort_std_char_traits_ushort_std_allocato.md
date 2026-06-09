# IsDSMA(Windows::System::Internal::IUserManagerStatics *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180023320`
- end: `0x180023386`
- name: `?IsDSMA@@YA_NPEAUIUserManagerStatics@Internal@System@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000a548`
- `0x18001138c`
- `0x180013dcc`
- `0x180023320`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180023368`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180023368`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002333f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002333f`

## string_xrefs

- `0x18002334e`: `shellcommon\shell\sharedpc\accountmanager\lib\util\specialaccountsutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool IsDSMA()
{
  const WCHAR *v0; // rax
  const char *v1; // r9
  bool v2; // bl
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF

  Sid = 0;
  v0 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  if ( !ConvertStringSidToSidW(v0, &Sid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x52,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\specialaccountsutils.cpp",
      v1);
  v2 = IsWellKnownSid(Sid, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
  return v2;
}

```

## disassembly

```asm
0x180023320  push    rbx
0x180023322  sub     rsp, 20h
0x180023326  mov     [rsp+28h+Sid], 0
0x18002332f  mov     rcx, rdx
0x180023332  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180023337  lea     rdx, [rsp+28h+Sid]; Sid
0x18002333c  mov     rcx, rax; StringSid
0x18002333f  call    cs:__imp_ConvertStringSidToSidW
0x180023345  mov     rcx, [rsp+28h]; this
0x18002334a  test    eax, eax
0x18002334c  jnz     short loc_18002335E
0x18002334e  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\sharedpc\\accountma"...
0x180023355  lea     edx, [rax+52h]; void *
0x180023358  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002335e  mov     edx, 6Eh ; 'n'; WellKnownSidType
0x180023363  mov     rcx, [rsp+28h+Sid]; pSid
0x180023368  call    cs:__imp_IsWellKnownSid
0x18002336e  nop
0x18002336f  test    eax, eax
0x180023371  setnz   bl
0x180023374  lea     rcx, [rsp+28h+Sid]
0x180023379  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002337e  mov     al, bl
0x180023380  add     rsp, 20h
0x180023384  pop     rbx
0x180023385  retn
```
