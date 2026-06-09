# Vml::VmAccessToken::_GetInformation(_TOKEN_INFORMATION_CLASS)

- ea: `0x1400c419c`
- end: `0x1400c4289`
- name: `?_GetInformation@VmAccessToken@Vml@@AEBAPEAXW4_TOKEN_INFORMATION_CLASS@@@Z`
- size: `237`
- prototype: `void *__fastcall(Vml::VmAccessToken *__hidden this, enum _TOKEN_INFORMATION_CLASS)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400c3a80`

## callees

- `0x14005b628`
- `0x1400c419c`
- `0x140132940`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400c41fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400c41fc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400c41e7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400c4246`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400c41e7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400c4246`

## string_xrefs

- `0x1400c425b`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400c4215`: `onecore\vm\common\vml\VmMemory.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HLOCAL __fastcall Vml::VmAccessToken::_GetInformation(HANDLE *this, enum _TOKEN_INFORMATION_CLASS a2)
{
  HLOCAL v3; // rax
  const char *v4; // r9
  HLOCAL v5; // rbx
  const char *v6; // r9
  SIZE_T uBytes; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  LODWORD(uBytes) = 0;
  GetTokenInformation(*this, TokenUser, 0, 0, (PDWORD)&uBytes);
  v3 = LocalAlloc(0x40u, (unsigned int)uBytes);
  v5 = v3;
  if ( !v3 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x355,
      (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
      v4);
  if ( !GetTokenInformation(*this, TokenUser, v3, uBytes, (PDWORD)&uBytes) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x199C,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v6);
  return v5;
}

```

## disassembly

```asm
0x1400c419c  mov     r11, rsp
0x1400c419f  mov     [r11+10h], rbx
0x1400c41a3  push    rdi
0x1400c41a4  sub     rsp, 50h
0x1400c41a8  mov     rax, cs:__security_cookie
0x1400c41af  xor     rax, rsp
0x1400c41b2  mov     [rsp+58h+var_10], rax
0x1400c41b7  mov     rdi, rcx
0x1400c41ba  xorps   xmm0, xmm0
0x1400c41bd  movups  [rsp+58h+var_28], xmm0
0x1400c41c2  mov     qword ptr [r11-28h], 0
0x1400c41ca  mov     dword ptr [rsp+58h+uBytes], 0
0x1400c41d2  lea     rax, [r11-18h]
0x1400c41d6  mov     [r11-38h], rax
0x1400c41da  xor     r9d, r9d; TokenInformationLength
0x1400c41dd  xor     r8d, r8d; TokenInformation
0x1400c41e0  lea     edx, [r9+1]; TokenInformationClass
0x1400c41e4  mov     rcx, [rcx]; TokenHandle
0x1400c41e7  call    cs:__imp_GetTokenInformation
0x1400c41ee  nop     dword ptr [rax+rax+00h]
0x1400c41f3  mov     edx, dword ptr [rsp+58h+uBytes]; uBytes
0x1400c41f7  mov     ecx, 40h ; '@'; uFlags
0x1400c41fc  call    cs:__imp_LocalAlloc
0x1400c4203  nop     dword ptr [rax+rax+00h]
0x1400c4208  mov     rbx, rax
0x1400c420b  test    rax, rax
0x1400c420e  jnz     short loc_1400C4227
0x1400c4210  mov     rcx, [rsp+58h]; this
0x1400c4215  lea     r8, aOnecoreVmCommo_36; "onecore\\vm\\common\\vml\\VmMemory.h"
0x1400c421c  mov     edx, 355h; void *
0x1400c4221  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c4227  mov     qword ptr [rsp+58h+var_28], rbx
0x1400c422c  lea     rax, [rsp+58h+uBytes]
0x1400c4231  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1400c4236  mov     r9d, dword ptr [rsp+58h+uBytes]; TokenInformationLength
0x1400c423b  mov     r8, rbx; TokenInformation
0x1400c423e  mov     edx, 1; TokenInformationClass
0x1400c4243  mov     rcx, [rdi]; TokenHandle
0x1400c4246  call    cs:__imp_GetTokenInformation
0x1400c424d  nop     dword ptr [rax+rax+00h]
0x1400c4252  mov     rcx, [rsp+58h]; this
0x1400c4257  test    eax, eax
0x1400c4259  jnz     short loc_1400C426D
0x1400c425b  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400c4262  mov     edx, 199Ch; void *
0x1400c4267  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c426d  mov     rax, rbx
0x1400c4270  mov     rcx, [rsp+58h+var_10]
0x1400c4275  xor     rcx, rsp; StackCookie
0x1400c4278  call    __security_check_cookie
0x1400c427d  mov     rbx, [rsp+58h+arg_8]
0x1400c4282  add     rsp, 50h
0x1400c4286  pop     rdi
0x1400c4287  retn
```
