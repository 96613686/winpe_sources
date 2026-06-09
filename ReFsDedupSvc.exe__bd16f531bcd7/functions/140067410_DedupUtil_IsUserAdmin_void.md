# DedupUtil::IsUserAdmin(void)

- ea: `0x140067410`
- end: `0x1400674d7`
- name: `?IsUserAdmin@DedupUtil@@YA_NXZ`
- size: `199`
- prototype: `bool __fastcall(DedupUtil *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400653fc`
- `0x1400656dc`
- `0x140065c7c`
- `0x140067f64`
- `0x14007a6fc`

## callees

- `0x140004870`
- `0x140067410`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400674a5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400674a5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140067471`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140067471`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14006748e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14006748e`

## pseudocode

```c
bool __fastcall DedupUtil::IsUserAdmin(DedupUtil *this)
{
  bool v1; // zf
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck);
  v1 = IsMember == 0;
  if ( IsMember )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
      IsMember = 0;
    FreeSid(SidToCheck);
    v1 = IsMember == 0;
  }
  return !v1;
}

```

## disassembly

```asm
0x140067410  mov     [rsp-8+arg_0], rbx
0x140067415  push    rbp
0x140067416  mov     rbp, rsp
0x140067419  sub     rsp, 80h
0x140067420  mov     rax, cs:__security_cookie
0x140067427  xor     rax, rsp
0x14006742a  mov     [rbp+var_8], rax
0x14006742e  xor     ebx, ebx
0x140067430  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x140067436  lea     rax, [rbp+SidToCheck]
0x14006743a  mov     [rbp+IsMember], ebx
0x14006743d  mov     [rsp+80h+pSid], rax; pSid
0x140067442  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x140067446  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x14006744a  mov     r9d, 220h; nSubAuthority1
0x140067450  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x140067454  lea     r8d, [rbx+20h]; nSubAuthority0
0x140067458  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x14006745c  mov     dl, 2; nSubAuthorityCount
0x14006745e  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x140067462  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x140067466  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x14006746a  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x14006746d  mov     [rbp+SidToCheck], rbx
0x140067471  call    cs:__imp_AllocateAndInitializeSid
0x140067478  nop     dword ptr [rax+rax+00h]
0x14006747d  mov     [rbp+IsMember], eax
0x140067480  test    eax, eax
0x140067482  jz      short loc_1400674B6
0x140067484  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x140067488  lea     r8, [rbp+IsMember]; IsMember
0x14006748c  xor     ecx, ecx; TokenHandle
0x14006748e  call    cs:__imp_CheckTokenMembership
0x140067495  nop     dword ptr [rax+rax+00h]
0x14006749a  test    eax, eax
0x14006749c  jnz     short loc_1400674A1
0x14006749e  mov     [rbp+IsMember], ebx
0x1400674a1  mov     rcx, [rbp+SidToCheck]; pSid
0x1400674a5  call    cs:__imp_FreeSid
0x1400674ac  nop     dword ptr [rax+rax+00h]
0x1400674b1  mov     eax, [rbp+IsMember]
0x1400674b4  test    eax, eax
0x1400674b6  setnz   al
0x1400674b9  mov     rcx, [rbp+var_8]
0x1400674bd  xor     rcx, rsp; StackCookie
0x1400674c0  call    __security_check_cookie
0x1400674c5  mov     rbx, [rsp+80h+arg_0]
0x1400674cd  add     rsp, 80h
0x1400674d4  pop     rbp
0x1400674d5  retn
```
