# Rdp::Security::CreateAdminSid(void)

- ea: `0x18001833c`
- end: `0x1800183f5`
- name: `?CreateAdminSid@Security@Rdp@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018aec`

## callees

- `0x180006580`
- `0x18001833c`
- `0x180019998`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800183a9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800183a9`

## string_xrefs

- `0x1800183dc`: `Failed to allocate admin sid`
- `0x1800183e3`: `onecoreuap\termsrv\rdp_bin\win\common/inc/RdpSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PSID *__fastcall Rdp::Security::CreateAdminSid(PSID *a1)
{
  const char *nSubAuthority2; // [rsp+20h] [rbp-68h]
  struct _SID_IDENTIFIER_AUTHORITY v4; // [rsp+70h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *(_DWORD *)v4.Value = 0;
  *(_WORD *)&v4.Value[4] = 1280;
  *a1 = 0;
  if ( !AllocateAndInitializeSid(&v4, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, a1) )
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RdpSecurity.h",
      "Failed to allocate admin sid",
      nSubAuthority2);
  return a1;
}

```

## disassembly

```asm
0x18001833c  mov     r11, rsp
0x18001833f  mov     [r11+10h], rbx
0x180018343  push    rdi
0x180018344  sub     rsp, 80h
0x18001834b  mov     rax, cs:__security_cookie
0x180018352  xor     rax, rsp
0x180018355  mov     [rsp+88h+var_10], rax
0x18001835a  mov     rbx, rcx
0x18001835d  mov     [r11-20h], rcx
0x180018361  xor     edi, edi
0x180018363  mov     [rsp+88h+var_28], edi
0x180018367  mov     [rsp+88h+var_28], 1
0x18001836f  mov     [rsp+88h+var_18], edi
0x180018373  mov     [rsp+88h+var_14], 500h
0x18001837a  mov     [rcx], rdi
0x18001837d  mov     [r11-38h], rcx
0x180018381  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x180018385  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x180018389  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x18001838d  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x180018391  mov     [rsp+88h+nSubAuthority3], edi; nSubAuthority3
0x180018395  mov     dword ptr [rsp+88h+nSubAuthority2], edi; char *
0x180018399  mov     r9d, 220h; nSubAuthority1
0x18001839f  lea     r8d, [rdi+20h]; nSubAuthority0
0x1800183a3  mov     dl, 2; nSubAuthorityCount
0x1800183a5  lea     rcx, [r11-18h]; pIdentifierAuthority
0x1800183a9  call    cs:__imp_AllocateAndInitializeSid
0x1800183af  test    eax, eax
0x1800183b1  jz      short loc_1800183D4
0x1800183b3  mov     rax, rbx
0x1800183b6  mov     rcx, [rsp+88h+var_10]
0x1800183bb  xor     rcx, rsp; StackCookie
0x1800183be  call    __security_check_cookie
0x1800183c3  mov     rbx, [rsp+88h+arg_8]
0x1800183cb  add     rsp, 80h
0x1800183d2  pop     rdi
0x1800183d3  retn
0x1800183d4  mov     rcx, [rsp+88h]; this
0x1800183dc  lea     r9, aFailedToAlloca_2; "Failed to allocate admin sid"
0x1800183e3  lea     r8, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x1800183ea  mov     edx, 0D9h; void *
0x1800183ef  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
