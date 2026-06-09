# WfpAllocAnyAppContainerSid

- ea: `0x180004954`
- end: `0x1800049f1`
- name: `WfpAllocAnyAppContainerSid`
- size: `157`
- prototype: `__int64 __fastcall(PSID *pSid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800040f0`

## callees

- `0x180004954`
- `0x18001236c`
- `0x180018b74`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049c3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800049a3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800049a3`

## string_xrefs

- `0x1800049cc`: `AllocateAndInitializeSid`
- `0x1800049e0`: `WfpAllocAnyAppContainerSid`

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
0x180004954  push    rbx
0x180004956  sub     rsp, 70h
0x18000495a  mov     rax, cs:__security_cookie
0x180004961  xor     rax, rsp
0x180004964  mov     [rsp+78h+var_10], rax
0x180004969  xor     ebx, ebx
0x18000496b  mov     [rsp+78h+pSid], rcx; pSid
0x180004970  mov     [rsp+78h+nSubAuthority7], ebx; nSubAuthority7
0x180004974  lea     rcx, [rsp+78h+pIdentifierAuthority]; pIdentifierAuthority
0x180004979  mov     [rsp+78h+nSubAuthority6], ebx; nSubAuthority6
0x18000497d  mov     [rsp+78h+nSubAuthority5], ebx; nSubAuthority5
0x180004981  lea     r8d, [rbx+2]; nSubAuthority0
0x180004985  mov     [rsp+78h+nSubAuthority4], ebx; nSubAuthority4
0x180004989  mov     dl, r8b; nSubAuthorityCount
0x18000498c  mov     [rsp+78h+nSubAuthority3], ebx; nSubAuthority3
0x180004990  lea     r9d, [rbx+1]; nSubAuthority1
0x180004994  mov     dword ptr [rsp+78h+pIdentifierAuthority.Value], ebx
0x180004998  mov     word ptr [rsp+78h+pIdentifierAuthority.Value+4], 0F00h
0x18000499f  mov     [rsp+78h+nSubAuthority2], ebx; nSubAuthority2
0x1800049a3  call    cs:__imp_AllocateAndInitializeSid
0x1800049a9  test    eax, eax
0x1800049ab  jz      short loc_1800049C3
0x1800049ad  mov     rax, rbx
0x1800049b0  mov     rcx, [rsp+78h+var_10]
0x1800049b5  xor     rcx, rsp; StackCookie
0x1800049b8  call    __security_check_cookie
0x1800049bd  add     rsp, 70h
0x1800049c1  pop     rbx
0x1800049c2  retn
0x1800049c3  call    cs:__imp_GetLastError
0x1800049c9  mov     r8d, eax
0x1800049cc  lea     rdx, aAllocateandini; "AllocateAndInitializeSid"
0x1800049d3  call    WfpReportSysErrorAsWinError
0x1800049d8  mov     rbx, rax
0x1800049db  test    rax, rax
0x1800049de  jz      short loc_1800049AD
0x1800049e0  lea     rdx, aWfpallocanyapp; "WfpAllocAnyAppContainerSid"
0x1800049e7  mov     rcx, rax
0x1800049ea  call    WfpReportError
0x1800049ef  jmp     short loc_1800049AD
```
