# Utils::SetTokenIntegrityLevel(void *,ulong)

- ea: `0x180005934`
- end: `0x180005a20`
- name: `?SetTokenIntegrityLevel@Utils@@SAJPEAXK@Z`
- size: `236`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006ea0`

## callees

- `0x180001720`
- `0x180005644`
- `0x180005934`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059e2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800059a9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800059a9`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800059d8`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800059d8`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800059c4`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800059c4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180005a00`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180005a00`

## pseudocode

```c
__int64 __fastcall Utils::SetTokenIntegrityLevel(HANDLE TokenHandle)
{
  unsigned int v1; // ebx
  DWORD SidLengthRequired; // eax
  signed int LastError; // eax
  PSID pSid; // [rsp+60h] [rbp+7h] BYREF
  __int128 TokenInformation; // [rsp+68h] [rbp+Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v1 = 0;
  pSid = 0;
  TokenInformation = 0;
  if ( Utils::GetTokenIL(TokenHandle) < 0x3000 )
  {
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x3000u, 0, 0, 0, 0, 0, 0, 0, &pSid)
      || (*(_QWORD *)&TokenInformation = pSid,
          DWORD2(TokenInformation) = 96,
          SidLengthRequired = GetSidLengthRequired(1u),
          !SetTokenInformation(TokenHandle, TokenIntegrityLevel, &TokenInformation, SidLengthRequired + 16)) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( pSid )
    FreeSid(pSid);
  return v1;
}

```

## disassembly

```asm
0x180005934  push    rbp
0x180005936  push    rbx
0x180005937  push    rsi
0x180005938  push    rdi
0x180005939  lea     rbp, [rsp-3Fh]
0x18000593e  sub     rsp, 98h
0x180005945  mov     rax, cs:__security_cookie
0x18000594c  xor     rax, rsp
0x18000594f  mov     [rbp+57h+var_30], rax
0x180005953  xor     esi, esi
0x180005955  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 1000h
0x18000595b  xorps   xmm0, xmm0
0x18000595e  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180005961  mov     ebx, esi
0x180005963  mov     [rbp+57h+var_50], rsi
0x180005967  movdqu  [rbp+57h+TokenInformation], xmm0
0x18000596c  mov     rdi, rcx
0x18000596f  call    ?GetTokenIL@Utils@@SAKPEAX@Z; Utils::GetTokenIL(void *)
0x180005974  mov     r8d, 3000h; nSubAuthority0
0x18000597a  cmp     eax, r8d
0x18000597d  jnb     short loc_1800059F7
0x18000597f  lea     rax, [rbp+57h+var_50]
0x180005983  xor     r9d, r9d; nSubAuthority1
0x180005986  mov     [rsp+0B0h+pSid], rax; pSid
0x18000598b  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000598f  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x180005993  mov     dl, 1; nSubAuthorityCount
0x180005995  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x180005999  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x18000599d  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x1800059a1  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x1800059a5  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x1800059a9  call    cs:__imp_AllocateAndInitializeSid
0x1800059af  test    eax, eax
0x1800059b1  jz      short loc_1800059E2
0x1800059b3  mov     rax, [rbp+57h+var_50]
0x1800059b7  mov     cl, 1; nSubAuthorityCount
0x1800059b9  mov     qword ptr [rbp+57h+TokenInformation], rax
0x1800059bd  mov     dword ptr [rbp+57h+TokenInformation+8], 60h ; '`'
0x1800059c4  call    cs:__imp_GetSidLengthRequired
0x1800059ca  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800059ce  mov     rcx, rdi; TokenHandle
0x1800059d1  lea     edx, [rsi+19h]; TokenInformationClass
0x1800059d4  lea     r9d, [rax+10h]; TokenInformationLength
0x1800059d8  call    cs:__imp_SetTokenInformation
0x1800059de  test    eax, eax
0x1800059e0  jnz     short loc_1800059F7
0x1800059e2  call    cs:__imp_GetLastError
0x1800059e8  mov     ebx, eax
0x1800059ea  test    eax, eax
0x1800059ec  jle     short loc_1800059F7
0x1800059ee  movzx   ebx, ax
0x1800059f1  or      ebx, 80070000h
0x1800059f7  mov     rcx, [rbp+57h+var_50]; pSid
0x1800059fb  test    rcx, rcx
0x1800059fe  jz      short loc_180005A06
0x180005a00  call    cs:__imp_FreeSid
0x180005a06  mov     eax, ebx
0x180005a08  mov     rcx, [rbp+57h+var_30]
0x180005a0c  xor     rcx, rsp; StackCookie
0x180005a0f  call    __security_check_cookie
0x180005a14  add     rsp, 98h
0x180005a1b  pop     rdi
0x180005a1c  pop     rsi
0x180005a1d  pop     rbx
0x180005a1e  pop     rbp
0x180005a1f  retn
```
