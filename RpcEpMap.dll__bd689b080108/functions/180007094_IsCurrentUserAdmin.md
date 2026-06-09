# IsCurrentUserAdmin

- ea: `0x180007094`
- end: `0x18000715d`
- name: `IsCurrentUserAdmin`
- size: `201`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800071e0`

## callees

- `0x180007094`
- `0x18000a980`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180007134`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180007134`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800070fa`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800070fa`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000710e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000710e`

## pseudocode

```c
__int64 IsCurrentUserAdmin()
{
  unsigned int v0; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) || (v0 = 0, !IsMember) )
      v0 = 5;
  }
  else
  {
    v0 = 14;
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v0;
}

```

## disassembly

```asm
0x180007094  mov     [rsp-8+arg_0], rbx
0x180007099  mov     [rsp-8+arg_8], rdi
0x18000709e  push    rbp
0x18000709f  mov     rbp, rsp
0x1800070a2  sub     rsp, 80h
0x1800070a9  mov     rax, cs:__security_cookie
0x1800070b0  xor     rax, rsp
0x1800070b3  mov     [rbp+var_8], rax
0x1800070b7  xor     edi, edi
0x1800070b9  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800070bf  lea     rax, [rbp+SidToCheck]
0x1800070c3  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x1800070c6  mov     [rsp+80h+pSid], rax; pSid
0x1800070cb  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800070cf  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x1800070d3  mov     r9d, 220h; nSubAuthority1
0x1800070d9  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x1800070dd  lea     r8d, [rdi+20h]; nSubAuthority0
0x1800070e1  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x1800070e5  mov     dl, 2; nSubAuthorityCount
0x1800070e7  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x1800070eb  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x1800070ef  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x1800070f3  mov     [rbp+SidToCheck], rdi
0x1800070f7  mov     [rbp+IsMember], edi
0x1800070fa  call    cs:__imp_AllocateAndInitializeSid
0x180007100  test    eax, eax
0x180007102  jz      short loc_180007126
0x180007104  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180007108  lea     r8, [rbp+IsMember]; IsMember
0x18000710c  xor     ecx, ecx; TokenHandle
0x18000710e  call    cs:__imp_CheckTokenMembership
0x180007114  test    eax, eax
0x180007116  jz      short loc_18000711F
0x180007118  mov     ebx, edi
0x18000711a  cmp     [rbp+IsMember], edi
0x18000711d  jnz     short loc_18000712B
0x18000711f  mov     ebx, 5
0x180007124  jmp     short loc_18000712B
0x180007126  mov     ebx, 0Eh
0x18000712b  mov     rcx, [rbp+SidToCheck]; pSid
0x18000712f  test    rcx, rcx
0x180007132  jz      short loc_18000713A
0x180007134  call    cs:__imp_FreeSid
0x18000713a  mov     eax, ebx
0x18000713c  mov     rcx, [rbp+var_8]
0x180007140  xor     rcx, rsp; StackCookie
0x180007143  call    __security_check_cookie
0x180007148  lea     r11, [rsp+80h+var_s0]
0x180007150  mov     rbx, [r11+10h]
0x180007154  mov     rdi, [r11+18h]
0x180007158  mov     rsp, r11
0x18000715b  pop     rbp
0x18000715c  retn
```
