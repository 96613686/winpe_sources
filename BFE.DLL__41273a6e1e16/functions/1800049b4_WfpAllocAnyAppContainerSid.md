# WfpAllocAnyAppContainerSid

- ea: `0x1800049b4`
- end: `0x180004a5e`
- name: `WfpAllocAnyAppContainerSid`
- size: `170`
- prototype: `__int64 __fastcall(PSID *pSid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800040d0`

## callees

- `0x1800049b4`
- `0x180012d8c`
- `0x1800197d0`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a2a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180004a03`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180004a03`

## string_xrefs

- `0x180004a39`: `AllocateAndInitializeSid`
- `0x180004a4d`: `WfpAllocAnyAppContainerSid`

## pseudocode

```c
__int64 __fastcall WfpAllocAnyAppContainerSid(PSID *pSid)
{
  __int64 v1; // rbx
  DWORD LastError; // eax
  __int64 v4; // rcx
  __int64 v5; // rax
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-18h] BYREF

  v1 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, pSid) )
  {
    LastError = GetLastError();
    v5 = WfpReportSysErrorAsWinError(v4, "AllocateAndInitializeSid", LastError);
    v1 = v5;
    if ( v5 )
      WfpReportError(v5, "WfpAllocAnyAppContainerSid");
  }
  return v1;
}

```

## disassembly

```asm
0x1800049b4  push    rbx
0x1800049b6  sub     rsp, 70h
0x1800049ba  mov     rax, cs:__security_cookie
0x1800049c1  xor     rax, rsp
0x1800049c4  mov     [rsp+78h+var_10], rax
0x1800049c9  xor     ebx, ebx
0x1800049cb  mov     [rsp+78h+pSid], rcx; pSid
0x1800049d0  mov     [rsp+78h+nSubAuthority7], ebx; nSubAuthority7
0x1800049d4  lea     rcx, [rsp+78h+pIdentifierAuthority]; pIdentifierAuthority
0x1800049d9  mov     [rsp+78h+nSubAuthority6], ebx; nSubAuthority6
0x1800049dd  mov     [rsp+78h+nSubAuthority5], ebx; nSubAuthority5
0x1800049e1  lea     r8d, [rbx+2]; nSubAuthority0
0x1800049e5  mov     [rsp+78h+nSubAuthority4], ebx; nSubAuthority4
0x1800049e9  mov     dl, r8b; nSubAuthorityCount
0x1800049ec  mov     [rsp+78h+nSubAuthority3], ebx; nSubAuthority3
0x1800049f0  lea     r9d, [rbx+1]; nSubAuthority1
0x1800049f4  mov     dword ptr [rsp+78h+pIdentifierAuthority.Value], ebx
0x1800049f8  mov     word ptr [rsp+78h+pIdentifierAuthority.Value+4], 0F00h
0x1800049ff  mov     [rsp+78h+nSubAuthority2], ebx; nSubAuthority2
0x180004a03  call    cs:__imp_AllocateAndInitializeSid
0x180004a0a  nop     dword ptr [rax+rax+00h]
0x180004a0f  test    eax, eax
0x180004a11  jz      short loc_180004A2A
0x180004a13  mov     rax, rbx
0x180004a16  mov     rcx, [rsp+78h+var_10]
0x180004a1b  xor     rcx, rsp; StackCookie
0x180004a1e  call    __security_check_cookie
0x180004a23  add     rsp, 70h
0x180004a27  pop     rbx
0x180004a28  retn
0x180004a2a  call    cs:__imp_GetLastError
0x180004a31  nop     dword ptr [rax+rax+00h]
0x180004a36  mov     r8d, eax
0x180004a39  lea     rdx, aAllocateandini; "AllocateAndInitializeSid"
0x180004a40  call    WfpReportSysErrorAsWinError
0x180004a45  mov     rbx, rax
0x180004a48  test    rax, rax
0x180004a4b  jz      short loc_180004A13
0x180004a4d  lea     rdx, aWfpallocanyapp; "WfpAllocAnyAppContainerSid"
0x180004a54  mov     rcx, rax
0x180004a57  call    WfpReportError
0x180004a5c  jmp     short loc_180004A13
```
