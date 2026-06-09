# BasicUtils::GetMediumILSidString(void)

- ea: `0x180024610`
- end: `0x180024708`
- name: `?GetMediumILSidString@BasicUtils@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `248`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024080`

## callees

- `0x1800245f0`
- `0x180024610`
- `0x1800249ec`
- `0x18002a514`
- `0x180043680`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180024689`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180024689`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800246ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800246ba`

## string_xrefs

- `0x180024697`: `onecore\windows\accessibletech\common\basicutils.cpp`
- `0x1800246c8`: `onecore\windows\accessibletech\common\basicutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPWSTR *__fastcall BasicUtils::GetMediumILSidString(LPWSTR *StringSid)
{
  const char *v2; // r9
  const char *v3; // r9
  PSID Sid; // [rsp+60h] [rbp+27h] BYREF
  int v6; // [rsp+68h] [rbp+2Fh]
  LPWSTR *v7; // [rsp+70h] [rbp+37h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v7 = StringSid;
  v6 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  Sid = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &Sid,
    0);
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x2000u, 0, 0, 0, 0, 0, 0, 0, &Sid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
      v2);
  v6 = 1;
  *StringSid = 0;
  if ( !ConvertSidToStringSidW(Sid, StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
      v3);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
  return StringSid;
}

```

## disassembly

```asm
0x180024610  mov     [rsp-8+arg_8], rbx
0x180024615  mov     [rsp-8+arg_10], rdi
0x18002461a  push    rbp
0x18002461b  lea     rbp, [rsp-57h]
0x180024620  sub     rsp, 90h
0x180024627  mov     rax, cs:__security_cookie
0x18002462e  xor     rax, rsp
0x180024631  mov     [rbp+57h+var_10], rax
0x180024635  mov     rbx, rcx
0x180024638  mov     [rbp+57h+var_20], rcx
0x18002463c  xor     edi, edi
0x18002463e  mov     [rbp+57h+var_28], edi
0x180024641  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x180024644  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 1000h
0x18002464a  mov     [rbp+57h+Sid], rdi
0x18002464e  xor     edx, edx
0x180024650  lea     rcx, [rbp+57h+Sid]
0x180024654  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180024659  lea     rax, [rbp+57h+Sid]
0x18002465d  mov     [rsp+90h+pSid], rax; pSid
0x180024662  mov     [rsp+90h+nSubAuthority7], edi; nSubAuthority7
0x180024666  mov     [rsp+90h+nSubAuthority6], edi; nSubAuthority6
0x18002466a  mov     [rsp+90h+nSubAuthority5], edi; nSubAuthority5
0x18002466e  mov     [rsp+90h+nSubAuthority4], edi; nSubAuthority4
0x180024672  mov     [rsp+90h+nSubAuthority3], edi; nSubAuthority3
0x180024676  mov     [rsp+90h+nSubAuthority2], edi; nSubAuthority2
0x18002467a  xor     r9d, r9d; nSubAuthority1
0x18002467d  mov     r8d, 2000h; nSubAuthority0
0x180024683  mov     dl, 1; nSubAuthorityCount
0x180024685  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180024689  call    cs:__imp_AllocateAndInitializeSid
0x18002468f  mov     rcx, [rbp+5Fh]; this
0x180024693  test    eax, eax
0x180024695  jnz     short loc_1800246A9
0x180024697  lea     r8, aOnecoreWindows_3; "onecore\\windows\\accessibletech\\commo"...
0x18002469e  mov     edx, 84h; void *
0x1800246a3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800246a9  mov     [rbp+57h+var_28], 1
0x1800246b0  mov     [rbx], rdi
0x1800246b3  mov     rdx, rbx; StringSid
0x1800246b6  mov     rcx, [rbp+57h+Sid]; Sid
0x1800246ba  call    cs:__imp_ConvertSidToStringSidW
0x1800246c0  mov     rcx, [rbp+5Fh]; this
0x1800246c4  test    eax, eax
0x1800246c6  jnz     short loc_1800246DA
0x1800246c8  lea     r8, aOnecoreWindows_3; "onecore\\windows\\accessibletech\\commo"...
0x1800246cf  mov     edx, 87h; void *
0x1800246d4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800246da  lea     rcx, [rbp+57h+Sid]
0x1800246de  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800246e3  mov     rax, rbx
0x1800246e6  mov     rcx, [rbp+57h+var_10]
0x1800246ea  xor     rcx, rsp; StackCookie
0x1800246ed  call    __security_check_cookie
0x1800246f2  lea     r11, [rsp+90h+var_s0]
0x1800246fa  mov     rbx, [r11+18h]
0x1800246fe  mov     rdi, [r11+20h]
0x180024702  mov     rsp, r11
0x180024705  pop     rbp
0x180024706  retn
```
