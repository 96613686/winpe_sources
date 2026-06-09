# BasicUtils::GetMachineSidString(_GUID const &)

- ea: `0x180024820`
- end: `0x1800249e6`
- name: `?GetMachineSidString@BasicUtils@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024370`
- `0x1800244b0`

## callees

- `0x180023ce8`
- `0x1800245f0`
- `0x180024820`
- `0x1800249ec`
- `0x18002a514`
- `0x180031540`
- `0x180043680`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800248a0`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800248a0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024915`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024929`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024940`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024954`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024968`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002497c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024915`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024929`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024940`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024954`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024968`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002497c`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800248f0`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800248f0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180024998`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180024998`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800248b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800248b5`

## string_xrefs

- `0x18002487f`: `onecore\windows\accessibletech\common\basicutils.cpp`
- `0x1800248d4`: `onecore\windows\accessibletech\common\basicutils.cpp`
- `0x1800248fe`: `onecore\windows\accessibletech\common\basicutils.cpp`
- `0x1800249a6`: `onecore\windows\accessibletech\common\basicutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPWSTR *__fastcall BasicUtils::GetMachineSidString(LPWSTR *StringSid, DWORD *a2)
{
  __int64 v4; // rax
  DWORD SidLengthRequired; // eax
  HLOCAL v6; // rax
  const char *v7; // r9
  PSID v8; // rbx
  const char *v9; // r9
  DWORD v10; // edi
  DWORD v11; // edi
  DWORD v12; // edi
  DWORD v13; // edi
  const char *v14; // r9
  PSID Sid[2]; // [rsp+28h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  Sid[1] = StringSid;
  v4 = *(_QWORD *)a2 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)a2 == *(_QWORD *)&GUID_NULL.Data1 )
    v4 = *((_QWORD *)a2 + 1) - *(_QWORD *)GUID_NULL.Data4;
  if ( !v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
      (const char *)0x80070057LL,
      0);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidLengthRequired = GetSidLengthRequired(6u);
  Sid[0] = 0;
  v6 = LocalAlloc(0x40u, SidLengthRequired);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    Sid,
    v6);
  v8 = Sid[0];
  if ( !Sid[0] )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
      v7);
  if ( !InitializeSid(Sid[0], &pIdentifierAuthority, 6u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
      v9);
  *GetSidSubAuthority(v8, 0) = 83;
  *GetSidSubAuthority(v8, 1u) = 1;
  v10 = *a2;
  *GetSidSubAuthority(v8, 2u) = v10;
  v11 = a2[1];
  *GetSidSubAuthority(v8, 3u) = v11;
  v12 = a2[2];
  *GetSidSubAuthority(v8, 4u) = v12;
  v13 = a2[3];
  *GetSidSubAuthority(v8, 5u) = v13;
  *StringSid = 0;
  if ( !ConvertSidToStringSidW(v8, StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xA6,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
      v14);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Sid);
  return StringSid;
}

```

## disassembly

```asm
0x180024820  mov     [rsp-18h+arg_8], rbx
0x180024825  mov     [rsp-18h+arg_10], rsi
0x18002482a  push    rbp
0x18002482b  push    rdi
0x18002482c  push    r14
0x18002482e  mov     rbp, rsp
0x180024831  sub     rsp, 50h
0x180024835  mov     rax, cs:__security_cookie
0x18002483c  xor     rax, rsp
0x18002483f  mov     [rbp+var_10], rax
0x180024843  mov     r14, rdx
0x180024846  mov     rsi, rcx
0x180024849  mov     [rbp+var_20], rcx
0x18002484d  mov     [rbp+var_30], 0
0x180024854  mov     rax, [rdx]
0x180024857  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18002485e  jnz     short loc_18002486B
0x180024860  mov     rax, [rdx+8]
0x180024864  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18002486b  test    rax, rax
0x18002486e  setz    al
0x180024871  mov     rcx, [rbp+18h]; this
0x180024875  test    al, al
0x180024877  jz      short loc_180024891
0x180024879  mov     r9d, 80070057h; char *
0x18002487f  lea     r8, aOnecoreWindows_3; "onecore\\windows\\accessibletech\\commo"...
0x180024886  mov     edx, 8Eh; void *
0x18002488b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024891  mov     dword ptr [rbp+pIdentifierAuthority.Value], 0
0x180024898  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18002489e  mov     cl, 6; nSubAuthorityCount
0x1800248a0  call    cs:__imp_GetSidLengthRequired
0x1800248a6  mov     [rbp+Sid], 0
0x1800248ae  mov     edx, eax; uBytes
0x1800248b0  mov     ecx, 40h ; '@'; uFlags
0x1800248b5  call    cs:__imp_LocalAlloc
0x1800248bb  mov     rdx, rax
0x1800248be  lea     rcx, [rbp+Sid]
0x1800248c2  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800248c7  mov     rcx, [rbp+18h]; this
0x1800248cb  mov     rbx, [rbp+Sid]
0x1800248cf  test    rbx, rbx
0x1800248d2  jnz     short loc_1800248E6
0x1800248d4  lea     r8, aOnecoreWindows_3; "onecore\\windows\\accessibletech\\commo"...
0x1800248db  mov     edx, 96h; void *
0x1800248e0  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800248e6  mov     r8b, 6; nSubAuthorityCount
0x1800248e9  lea     rdx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800248ed  mov     rcx, rbx; Sid
0x1800248f0  call    cs:__imp_InitializeSid
0x1800248f6  mov     rcx, [rbp+18h]; this
0x1800248fa  test    eax, eax
0x1800248fc  jnz     short loc_180024910
0x1800248fe  lea     r8, aOnecoreWindows_3; "onecore\\windows\\accessibletech\\commo"...
0x180024905  mov     edx, 9Ah; void *
0x18002490a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180024910  xor     edx, edx; nSubAuthority
0x180024912  mov     rcx, rbx; pSid
0x180024915  call    cs:__imp_GetSidSubAuthority
0x18002491b  mov     dword ptr [rax], 53h ; 'S'
0x180024921  mov     edx, 1; nSubAuthority
0x180024926  mov     rcx, rbx; pSid
0x180024929  call    cs:__imp_GetSidSubAuthority
0x18002492f  mov     dword ptr [rax], 1
0x180024935  mov     edi, [r14]
0x180024938  mov     edx, 2; nSubAuthority
0x18002493d  mov     rcx, rbx; pSid
0x180024940  call    cs:__imp_GetSidSubAuthority
0x180024946  mov     [rax], edi
0x180024948  mov     edi, [r14+4]
0x18002494c  mov     edx, 3; nSubAuthority
0x180024951  mov     rcx, rbx; pSid
0x180024954  call    cs:__imp_GetSidSubAuthority
0x18002495a  mov     [rax], edi
0x18002495c  mov     edi, [r14+8]
0x180024960  mov     edx, 4; nSubAuthority
0x180024965  mov     rcx, rbx; pSid
0x180024968  call    cs:__imp_GetSidSubAuthority
0x18002496e  mov     [rax], edi
0x180024970  mov     edi, [r14+0Ch]
0x180024974  mov     edx, 5; nSubAuthority
0x180024979  mov     rcx, rbx; pSid
0x18002497c  call    cs:__imp_GetSidSubAuthority
0x180024982  mov     [rax], edi
0x180024984  mov     [rbp+var_30], 1
0x18002498b  mov     qword ptr [rsi], 0
0x180024992  mov     rdx, rsi; StringSid
0x180024995  mov     rcx, rbx; Sid
0x180024998  call    cs:__imp_ConvertSidToStringSidW
0x18002499e  mov     rcx, [rbp+18h]; this
0x1800249a2  test    eax, eax
0x1800249a4  jnz     short loc_1800249B8
0x1800249a6  lea     r8, aOnecoreWindows_3; "onecore\\windows\\accessibletech\\commo"...
0x1800249ad  mov     edx, 0A6h; void *
0x1800249b2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800249b8  lea     rcx, [rbp+Sid]
0x1800249bc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800249c1  mov     rax, rsi
0x1800249c4  mov     rcx, [rbp+var_10]
0x1800249c8  xor     rcx, rsp; StackCookie
0x1800249cb  call    __security_check_cookie
0x1800249d0  lea     r11, [rsp+50h+var_s0]
0x1800249d5  mov     rbx, [r11+28h]
0x1800249d9  mov     rsi, [r11+30h]
0x1800249dd  mov     rsp, r11
0x1800249e0  pop     r14
0x1800249e2  pop     rdi
0x1800249e3  pop     rbp
0x1800249e4  retn
```
