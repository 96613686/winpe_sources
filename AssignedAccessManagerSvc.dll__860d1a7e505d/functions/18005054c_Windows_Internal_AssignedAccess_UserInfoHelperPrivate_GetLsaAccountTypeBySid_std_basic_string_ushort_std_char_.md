# Windows::Internal::AssignedAccess::UserInfoHelperPrivate::GetLsaAccountTypeBySid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18005054c`
- end: `0x1800505c7`
- name: `?GetLsaAccountTypeBySid@UserInfoHelperPrivate@AssignedAccess@Internal@Windows@@SA?AW4_LSA_USER_ACCOUNT_TYPE@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180050440`
- `0x18005080c`

## callees

- `0x18002001c`
- `0x18004eca0`
- `0x18005054c`
- `0x180051048`
- `0x180051064`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180050570`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180050570`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180050599`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180050599`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AssignedAccess::UserInfoHelperPrivate::GetLsaAccountTypeBySid(__int64 a1)
{
  const WCHAR *v1; // rax
  const char *v2; // r9
  int v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF

  v10 = 0;
  Sid = 0;
  v1 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  if ( !ConvertStringSidToSidW(v1, &Sid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
      v2);
  v3 = LsaLookupUserAccountType(Sid, &v10);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, v4, v5, (const char *)(unsigned int)v3, v8);
  v6 = v10;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
  return v6;
}

```

## disassembly

```asm
0x18005054c  push    rbx; int
0x18005054e  sub     rsp, 20h
0x180050552  mov     [rsp+28h+arg_0], 0
0x18005055a  mov     [rsp+28h+Sid], 0
0x180050563  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180050568  lea     rdx, [rsp+28h+Sid]; Sid
0x18005056d  mov     rcx, rax; StringSid
0x180050570  call    cs:__imp_ConvertStringSidToSidW
0x180050576  mov     rcx, [rsp+28h]; this
0x18005057b  test    eax, eax
0x18005057d  jnz     short loc_18005058F
0x18005057f  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180050586  lea     edx, [rax+1Ch]; void *
0x180050589  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005058f  lea     rdx, [rsp+28h+arg_0]
0x180050594  mov     rcx, [rsp+28h+Sid]
0x180050599  call    cs:__imp_LsaLookupUserAccountType
0x18005059f  mov     rcx, [rsp+28h]; this
0x1800505a4  test    eax, eax
0x1800505a6  jns     short loc_1800505B1
0x1800505a8  mov     r9d, eax; char *
0x1800505ab  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800505b1  mov     ebx, [rsp+28h+arg_0]
0x1800505b5  lea     rcx, [rsp+28h+Sid]
0x1800505ba  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800505bf  mov     eax, ebx
0x1800505c1  add     rsp, 20h
0x1800505c5  pop     rbx
0x1800505c6  retn
```
