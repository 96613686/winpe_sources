# UtilIsVirtualServer(void)

- ea: `0x140011bf0`
- end: `0x140011d22`
- name: `?UtilIsVirtualServer@@YA_NXZ`
- size: `306`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005acd0`

## callees

- `0x140002470`
- `0x140011bf0`
- `0x14001444c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140011c60`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140011c60`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140011cb2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140011cb2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011c80`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011cf9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011c80`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011cf9`

## pseudocode

```c
bool UtilIsVirtualServer(void)
{
  BOOL v0; // ebx
  PSID v1; // rcx
  CUserModeHangReport *v2; // rcx
  __int64 v3; // rdx
  bool v4; // bl
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
  v0 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x53u, 0, 0, 0, 0, 0, 0, 0, &v8);
  if ( v8 )
  {
    v1 = *p_SidToCheck;
    *p_SidToCheck = v8;
    if ( v1 )
      FreeSid(v1);
  }
  if ( v0 )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v3 = 31;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = 30;
LABEL_12:
      WPP_SF_(*((_QWORD *)v2 + 2), v3, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    }
  }
  v4 = IsMember != 0;
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v4;
}

```

## disassembly

```asm
0x140011bf0  mov     r11, rsp
0x140011bf3  mov     [r11+8], rbx
0x140011bf7  mov     [r11+10h], rdi
0x140011bfb  push    rbp
0x140011bfc  lea     rbp, [r11-5Fh]
0x140011c00  sub     rsp, 0A0h
0x140011c07  mov     rax, cs:__security_cookie
0x140011c0e  xor     rax, rsp
0x140011c11  mov     [rbp+57h+var_10], rax
0x140011c15  xor     edi, edi
0x140011c17  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140011c1d  lea     rax, [rbp+57h+SidToCheck]
0x140011c21  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x140011c24  mov     [rbp+57h+var_28], rax
0x140011c28  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140011c2c  lea     rax, [rbp+57h+var_30]
0x140011c30  mov     [rbp+57h+IsMember], edi
0x140011c33  mov     [r11-58h], rax
0x140011c37  lea     r8d, [rdi+53h]; nSubAuthority0
0x140011c3b  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x140011c3f  xor     r9d, r9d; nSubAuthority1
0x140011c42  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x140011c46  mov     dl, 2; nSubAuthorityCount
0x140011c48  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x140011c4c  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x140011c50  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x140011c54  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x140011c58  mov     [rbp+57h+var_30], rdi
0x140011c5c  mov     [rbp+57h+SidToCheck], rdi
0x140011c60  call    cs:__imp_AllocateAndInitializeSid
0x140011c66  mov     r8, [rbp+57h+var_30]
0x140011c6a  mov     ebx, eax
0x140011c6c  test    r8, r8
0x140011c6f  jz      short loc_140011C86
0x140011c71  mov     rdx, [rbp+57h+var_28]
0x140011c75  mov     rcx, [rdx]; pSid
0x140011c78  mov     [rdx], r8
0x140011c7b  test    rcx, rcx
0x140011c7e  jz      short loc_140011C86
0x140011c80  call    cs:__imp_FreeSid
0x140011c86  test    ebx, ebx
0x140011c88  jnz     short loc_140011CA8
0x140011c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c91  lea     rax, WPP_GLOBAL_Control
0x140011c98  cmp     rcx, rax
0x140011c9b  jz      short loc_140011CEA
0x140011c9d  test    byte ptr [rcx+1Ch], 1
0x140011ca1  jz      short loc_140011CEA
0x140011ca3  lea     edx, [rbx+1Eh]
0x140011ca6  jmp     short loc_140011CDA
0x140011ca8  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140011cac  lea     r8, [rbp+57h+IsMember]; IsMember
0x140011cb0  xor     ecx, ecx; TokenHandle
0x140011cb2  call    cs:__imp_CheckTokenMembership
0x140011cb8  test    eax, eax
0x140011cba  jnz     short loc_140011CEA
0x140011cbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140011cc3  lea     rax, WPP_GLOBAL_Control
0x140011cca  cmp     rcx, rax
0x140011ccd  jz      short loc_140011CEA
0x140011ccf  test    byte ptr [rcx+1Ch], 1
0x140011cd3  jz      short loc_140011CEA
0x140011cd5  mov     edx, 1Fh
0x140011cda  mov     rcx, [rcx+10h]
0x140011cde  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140011ce5  call    WPP_SF_
0x140011cea  cmp     [rbp+57h+IsMember], edi
0x140011ced  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x140011cf1  setnz   bl
0x140011cf4  test    rcx, rcx
0x140011cf7  jz      short loc_140011CFF
0x140011cf9  call    cs:__imp_FreeSid
0x140011cff  mov     al, bl
0x140011d01  mov     rcx, [rbp+57h+var_10]
0x140011d05  xor     rcx, rsp; StackCookie
0x140011d08  call    __security_check_cookie
0x140011d0d  lea     r11, [rsp+0A0h+var_s0]
0x140011d15  mov     rbx, [r11+10h]
0x140011d19  mov     rdi, [r11+18h]
0x140011d1d  mov     rsp, r11
0x140011d20  pop     rbp
0x140011d21  retn
```
