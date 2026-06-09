# CATUtils::IsInteractiveUser(void)

- ea: `0x1800295f4`
- end: `0x1800296af`
- name: `?IsInteractiveUser@CATUtils@@SAHXZ`
- size: `187`
- prototype: `static int(void)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800225c4`
- `0x180023090`
- `0x180023de8`
- `0x1800241b0`
- `0x1800245c8`
- `0x1800288dc`
- `0x180028b64`
- `0x180029144`

## callees

- `0x1800295f4`
- `0x18002d220`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x180029684`
- `ADVAPI32!FreeSid` at `0x180029684`
- `ADVAPI32!CheckTokenMembership` at `0x180029678`
- `ADVAPI32!CheckTokenMembership` at `0x180029678`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180029657`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180029657`

## pseudocode

```c
__int64 CATUtils::IsInteractiveUser(void)
{
  unsigned int v0; // edi
  PSID v1; // rdx
  BOOL v2; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+1Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  v0 = 1;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    v1 = SidToCheck;
  }
  else
  {
    v1 = 0;
    SidToCheck = 0;
  }
  if ( !v1 )
    return 0;
  v2 = CheckTokenMembership(0, v1, &IsMember);
  FreeSid(SidToCheck);
  if ( !v2 || !IsMember )
    return 0;
  return v0;
}

```

## disassembly

```asm
0x1800295f4  push    rbp
0x1800295f6  push    rbx
0x1800295f7  push    rsi
0x1800295f8  push    rdi
0x1800295f9  lea     rbp, [rsp-3Fh]
0x1800295fe  sub     rsp, 88h
0x180029605  mov     rax, cs:__security_cookie
0x18002960c  xor     rax, rsp
0x18002960f  mov     [rbp+57h+var_28], rax
0x180029613  xor     esi, esi
0x180029615  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18002961b  lea     rax, [rbp+57h+SidToCheck]
0x18002961f  mov     [rbp+57h+IsMember], esi
0x180029622  mov     [rsp+0A0h+pSid], rax; pSid
0x180029627  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18002962b  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x18002962f  xor     r9d, r9d; nSubAuthority1
0x180029632  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x180029636  lea     edi, [rsi+1]
0x180029639  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x18002963d  lea     r8d, [rsi+4]; nSubAuthority0
0x180029641  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x180029645  mov     dl, dil; nSubAuthorityCount
0x180029648  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x18002964c  mov     [rsp+0A0h+nSubAuthority2], esi; nSubAuthority2
0x180029650  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180029653  mov     [rbp+57h+SidToCheck], rsi
0x180029657  call    cs:__imp_AllocateAndInitializeSid
0x18002965d  test    eax, eax
0x18002965f  jnz     short loc_180029669
0x180029661  mov     edx, esi
0x180029663  mov     [rbp+57h+SidToCheck], rdx
0x180029667  jmp     short loc_18002966D
0x180029669  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18002966d  test    rdx, rdx
0x180029670  jz      short loc_180029693
0x180029672  lea     r8, [rbp+57h+IsMember]; IsMember
0x180029676  xor     ecx, ecx; TokenHandle
0x180029678  call    cs:__imp_CheckTokenMembership
0x18002967e  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x180029682  mov     ebx, eax
0x180029684  call    cs:__imp_FreeSid
0x18002968a  test    ebx, ebx
0x18002968c  jz      short loc_180029693
0x18002968e  cmp     [rbp+57h+IsMember], esi
0x180029691  jnz     short loc_180029695
0x180029693  mov     edi, esi
0x180029695  mov     eax, edi
0x180029697  mov     rcx, [rbp+57h+var_28]
0x18002969b  xor     rcx, rsp; StackCookie
0x18002969e  call    __security_check_cookie
0x1800296a3  add     rsp, 88h
0x1800296aa  pop     rdi
0x1800296ab  pop     rsi
0x1800296ac  pop     rbx
0x1800296ad  pop     rbp
0x1800296ae  retn
```
