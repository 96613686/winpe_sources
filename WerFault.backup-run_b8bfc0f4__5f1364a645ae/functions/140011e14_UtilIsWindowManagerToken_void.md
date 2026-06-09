# UtilIsWindowManagerToken(void *)

- ea: `0x140011e14`
- end: `0x140011f1d`
- name: `?UtilIsWindowManagerToken@@YAJPEAX@Z`
- size: `265`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005acd0`

## callees

- `0x140002470`
- `0x140011e14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011ecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011ecc`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140011e84`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140011e84`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140011eb8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140011eb8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011ea4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011ef4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011ea4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011ef4`

## pseudocode

```c
__int64 __fastcall UtilIsWindowManagerToken(void *a1)
{
  BOOL v1; // ebx
  PSID v2; // rcx
  int v3; // ebx
  signed int LastError; // eax
  WINBOOL IsMember; // [rsp+68h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp+1Fh] BYREF
  PSID v8; // [rsp+78h] [rbp+27h] BYREF
  PSID *p_SidToCheck; // [rsp+80h] [rbp+2Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+3Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  p_SidToCheck = &SidToCheck;
  IsMember = 0;
  v8 = 0;
  SidToCheck = 0;
  v1 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x5Au, 0, 0, 0, 0, 0, 0, 0, &v8);
  if ( v8 )
  {
    v2 = *p_SidToCheck;
    *p_SidToCheck = v8;
    if ( v2 )
      FreeSid(v2);
  }
  if ( v1 && CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v3 = IsMember == 0;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140011e14  mov     r11, rsp
0x140011e17  mov     [r11+8], rbx
0x140011e1b  mov     [r11+10h], rdi
0x140011e1f  push    rbp
0x140011e20  lea     rbp, [r11-5Fh]
0x140011e24  sub     rsp, 0A0h
0x140011e2b  mov     rax, cs:__security_cookie
0x140011e32  xor     rax, rsp
0x140011e35  mov     [rbp+57h+var_10], rax
0x140011e39  xor     edi, edi
0x140011e3b  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140011e41  lea     rax, [rbp+57h+SidToCheck]
0x140011e45  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x140011e48  mov     [rbp+57h+var_28], rax
0x140011e4c  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140011e50  lea     rax, [rbp+57h+var_30]
0x140011e54  mov     [rbp+57h+IsMember], edi
0x140011e57  mov     [r11-58h], rax
0x140011e5b  lea     r8d, [rdi+5Ah]; nSubAuthority0
0x140011e5f  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x140011e63  xor     r9d, r9d; nSubAuthority1
0x140011e66  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x140011e6a  mov     dl, 2; nSubAuthorityCount
0x140011e6c  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x140011e70  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x140011e74  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x140011e78  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x140011e7c  mov     [rbp+57h+var_30], rdi
0x140011e80  mov     [rbp+57h+SidToCheck], rdi
0x140011e84  call    cs:__imp_AllocateAndInitializeSid
0x140011e8a  mov     r8, [rbp+57h+var_30]
0x140011e8e  mov     ebx, eax
0x140011e90  test    r8, r8
0x140011e93  jz      short loc_140011EAA
0x140011e95  mov     rdx, [rbp+57h+var_28]
0x140011e99  mov     rcx, [rdx]; pSid
0x140011e9c  mov     [rdx], r8
0x140011e9f  test    rcx, rcx
0x140011ea2  jz      short loc_140011EAA
0x140011ea4  call    cs:__imp_FreeSid
0x140011eaa  test    ebx, ebx
0x140011eac  jz      short loc_140011ECC
0x140011eae  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140011eb2  lea     r8, [rbp+57h+IsMember]; IsMember
0x140011eb6  xor     ecx, ecx; TokenHandle
0x140011eb8  call    cs:__imp_CheckTokenMembership
0x140011ebe  test    eax, eax
0x140011ec0  jz      short loc_140011ECC
0x140011ec2  cmp     [rbp+57h+IsMember], edi
0x140011ec5  mov     ebx, edi
0x140011ec7  setz    bl
0x140011eca  jmp     short loc_140011EEB
0x140011ecc  call    cs:__imp_GetLastError
0x140011ed2  mov     ebx, eax
0x140011ed4  test    eax, eax
0x140011ed6  jle     short loc_140011EE1
0x140011ed8  movzx   ebx, ax
0x140011edb  or      ebx, 80070000h
0x140011ee1  test    ebx, ebx
0x140011ee3  mov     eax, 80004005h
0x140011ee8  cmovns  ebx, eax
0x140011eeb  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x140011eef  test    rcx, rcx
0x140011ef2  jz      short loc_140011EFA
0x140011ef4  call    cs:__imp_FreeSid
0x140011efa  mov     eax, ebx
0x140011efc  mov     rcx, [rbp+57h+var_10]
0x140011f00  xor     rcx, rsp; StackCookie
0x140011f03  call    __security_check_cookie
0x140011f08  lea     r11, [rsp+0A0h+var_s0]
0x140011f10  mov     rbx, [r11+10h]
0x140011f14  mov     rdi, [r11+18h]
0x140011f18  mov     rsp, r11
0x140011f1b  pop     rbp
0x140011f1c  retn
```
