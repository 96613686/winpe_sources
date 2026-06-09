# Rdp::Security::CreateTermsrvSid(void)

- ea: `0x1800183fc`
- end: `0x1800184d5`
- name: `?CreateTermsrvSid@Security@Rdp@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `217`
- prototype: `__int64 __fastcall(PSID *pSid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180018d44`
- `0x18005c350`

## callees

- `0x180006580`
- `0x1800183fc`
- `0x180019998`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180018491`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180018491`

## string_xrefs

- `0x1800184bc`: `Failed to allocate termsservice sid`
- `0x1800184c3`: `onecoreuap\termsrv\rdp_bin\win\common/inc/RdpSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PSID *__fastcall Rdp::Security::CreateTermsrvSid(PSID *pSid)
{
  const char *nSubAuthority2; // [rsp+20h] [rbp-68h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *pSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *pSid = 0;
  if ( !AllocateAndInitializeSid(
          &pIdentifierAuthority,
          6u,
          0x50u,
          0x1A963466u,
          0x5CF1AAB9u,
          0xF8123019,
          0x7448CE95u,
          0x304EFDA0u,
          0,
          0,
          pSid) )
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0xC2,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RdpSecurity.h",
      "Failed to allocate termsservice sid",
      nSubAuthority2);
  return pSid;
}

```

## disassembly

```asm
0x1800183fc  push    rbx
0x1800183fe  sub     rsp, 80h
0x180018405  mov     rax, cs:__security_cookie
0x18001840c  xor     rax, rsp
0x18001840f  mov     [rsp+88h+var_10], rax
0x180018414  mov     rbx, rcx
0x180018417  mov     [rsp+88h+var_20], rcx
0x18001841c  mov     [rsp+88h+var_28], 0
0x180018424  mov     qword ptr [rcx], 0
0x18001842b  mov     [rsp+88h+var_28], 1
0x180018433  mov     dword ptr [rsp+88h+pIdentifierAuthority.Value], 0
0x18001843b  mov     word ptr [rsp+88h+pIdentifierAuthority.Value+4], 500h
0x180018442  mov     qword ptr [rcx], 0
0x180018449  mov     [rsp+88h+pSid], rcx; pSid
0x18001844e  mov     [rsp+88h+nSubAuthority7], 0; nSubAuthority7
0x180018456  mov     [rsp+88h+nSubAuthority6], 0; nSubAuthority6
0x18001845e  mov     [rsp+88h+nSubAuthority5], 304EFDA0h; nSubAuthority5
0x180018466  mov     [rsp+88h+nSubAuthority4], 7448CE95h; nSubAuthority4
0x18001846e  mov     [rsp+88h+nSubAuthority3], 0F8123019h; nSubAuthority3
0x180018476  mov     dword ptr [rsp+88h+nSubAuthority2], 5CF1AAB9h; char *
0x18001847e  mov     r9d, 1A963466h; nSubAuthority1
0x180018484  mov     r8d, 50h ; 'P'; nSubAuthority0
0x18001848a  mov     dl, 6; nSubAuthorityCount
0x18001848c  lea     rcx, [rsp+88h+pIdentifierAuthority]; pIdentifierAuthority
0x180018491  call    cs:__imp_AllocateAndInitializeSid
0x180018497  test    eax, eax
0x180018499  jz      short loc_1800184B4
0x18001849b  mov     rax, rbx
0x18001849e  mov     rcx, [rsp+88h+var_10]
0x1800184a3  xor     rcx, rsp; StackCookie
0x1800184a6  call    __security_check_cookie
0x1800184ab  add     rsp, 80h
0x1800184b2  pop     rbx
0x1800184b3  retn
0x1800184b4  mov     rcx, [rsp+88h]; this
0x1800184bc  lea     r9, aFailedToAlloca_5; "Failed to allocate termsservice sid"
0x1800184c3  lea     r8, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x1800184ca  mov     edx, 0C2h; void *
0x1800184cf  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
