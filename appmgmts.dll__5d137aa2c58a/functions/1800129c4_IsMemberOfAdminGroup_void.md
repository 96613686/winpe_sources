# IsMemberOfAdminGroup(void *)

- ea: `0x1800129c4`
- end: `0x180012a76`
- name: `?IsMemberOfAdminGroup@@YAHPEAX@Z`
- size: `178`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002b90`
- `0x180007410`

## callees

- `0x1800016d0`
- `0x1800129c4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180012a42`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180012a42`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180012a4c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180012a4c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012a2d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012a2d`

## pseudocode

```c
__int64 __fastcall IsMemberOfAdminGroup(HANDLE TokenHandle)
{
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  IsMember = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    CheckTokenMembership(TokenHandle, SidToCheck, &IsMember);
  FreeSid(SidToCheck);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x1800129c4  mov     [rsp-8+arg_8], rbx
0x1800129c9  mov     [rsp-8+arg_10], rdi
0x1800129ce  push    rbp
0x1800129cf  mov     rbp, rsp
0x1800129d2  sub     rsp, 80h
0x1800129d9  mov     rax, cs:__security_cookie
0x1800129e0  xor     rax, rsp
0x1800129e3  mov     [rbp+var_8], rax
0x1800129e7  xor     edi, edi
0x1800129e9  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800129ef  lea     rax, [rbp+SidToCheck]
0x1800129f3  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x1800129f6  mov     [rsp+80h+pSid], rax; pSid
0x1800129fb  mov     rbx, rcx
0x1800129fe  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x180012a02  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180012a06  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180012a0a  lea     r8d, [rdi+20h]; nSubAuthority0
0x180012a0e  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x180012a12  mov     r9d, 220h; nSubAuthority1
0x180012a18  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180012a1c  mov     dl, 2; nSubAuthorityCount
0x180012a1e  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x180012a22  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x180012a26  mov     [rbp+IsMember], edi
0x180012a29  mov     [rbp+SidToCheck], rdi
0x180012a2d  call    cs:__imp_AllocateAndInitializeSid
0x180012a33  test    eax, eax
0x180012a35  jz      short loc_180012A48
0x180012a37  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180012a3b  lea     r8, [rbp+IsMember]; IsMember
0x180012a3f  mov     rcx, rbx; TokenHandle
0x180012a42  call    cs:__imp_CheckTokenMembership
0x180012a48  mov     rcx, [rbp+SidToCheck]; pSid
0x180012a4c  call    cs:__imp_FreeSid
0x180012a52  mov     eax, [rbp+IsMember]
0x180012a55  mov     rcx, [rbp+var_8]
0x180012a59  xor     rcx, rsp; StackCookie
0x180012a5c  call    __security_check_cookie
0x180012a61  lea     r11, [rsp+80h+var_s0]
0x180012a69  mov     rbx, [r11+18h]
0x180012a6d  mov     rdi, [r11+20h]
0x180012a71  mov     rsp, r11
0x180012a74  pop     rbp
0x180012a75  retn
```
