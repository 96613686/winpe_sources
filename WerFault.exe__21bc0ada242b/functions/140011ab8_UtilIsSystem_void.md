# UtilIsSystem(void)

- ea: `0x140011ab8`
- end: `0x140011bea`
- name: `?UtilIsSystem@@YA_NXZ`
- size: `306`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004812c`
- `0x14005acd0`

## callees

- `0x140002470`
- `0x140011ab8`
- `0x14001444c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140011b28`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140011b28`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140011b7a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140011b7a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011b48`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011bc1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011b48`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011bc1`

## pseudocode

```c
bool UtilIsSystem(void)
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
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+3Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  p_SidToCheck = &SidToCheck;
  IsMember = 0;
  v8 = 0;
  SidToCheck = 0;
  v0 = AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &v8);
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
        v3 = 33;
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
      v3 = 32;
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
0x140011ab8  mov     r11, rsp
0x140011abb  mov     [r11+8], rbx
0x140011abf  mov     [r11+10h], rdi
0x140011ac3  push    rbp
0x140011ac4  lea     rbp, [r11-5Fh]
0x140011ac8  sub     rsp, 0A0h
0x140011acf  mov     rax, cs:__security_cookie
0x140011ad6  xor     rax, rsp
0x140011ad9  mov     [rbp+57h+var_10], rax
0x140011add  xor     edi, edi
0x140011adf  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140011ae5  lea     rax, [rbp+57h+SidToCheck]
0x140011ae9  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x140011aec  mov     [rbp+57h+var_28], rax
0x140011af0  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140011af4  lea     rax, [rbp+57h+var_30]
0x140011af8  mov     [rbp+57h+IsMember], edi
0x140011afb  mov     [r11-58h], rax
0x140011aff  lea     r8d, [rdi+12h]; nSubAuthority0
0x140011b03  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x140011b07  xor     r9d, r9d; nSubAuthority1
0x140011b0a  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x140011b0e  mov     dl, 1; nSubAuthorityCount
0x140011b10  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x140011b14  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x140011b18  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x140011b1c  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x140011b20  mov     [rbp+57h+var_30], rdi
0x140011b24  mov     [rbp+57h+SidToCheck], rdi
0x140011b28  call    cs:__imp_AllocateAndInitializeSid
0x140011b2e  mov     r8, [rbp+57h+var_30]
0x140011b32  mov     ebx, eax
0x140011b34  test    r8, r8
0x140011b37  jz      short loc_140011B4E
0x140011b39  mov     rdx, [rbp+57h+var_28]
0x140011b3d  mov     rcx, [rdx]; pSid
0x140011b40  mov     [rdx], r8
0x140011b43  test    rcx, rcx
0x140011b46  jz      short loc_140011B4E
0x140011b48  call    cs:__imp_FreeSid
0x140011b4e  test    ebx, ebx
0x140011b50  jnz     short loc_140011B70
0x140011b52  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b59  lea     rax, WPP_GLOBAL_Control
0x140011b60  cmp     rcx, rax
0x140011b63  jz      short loc_140011BB2
0x140011b65  test    byte ptr [rcx+1Ch], 1
0x140011b69  jz      short loc_140011BB2
0x140011b6b  lea     edx, [rbx+20h]
0x140011b6e  jmp     short loc_140011BA2
0x140011b70  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140011b74  lea     r8, [rbp+57h+IsMember]; IsMember
0x140011b78  xor     ecx, ecx; TokenHandle
0x140011b7a  call    cs:__imp_CheckTokenMembership
0x140011b80  test    eax, eax
0x140011b82  jnz     short loc_140011BB2
0x140011b84  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b8b  lea     rax, WPP_GLOBAL_Control
0x140011b92  cmp     rcx, rax
0x140011b95  jz      short loc_140011BB2
0x140011b97  test    byte ptr [rcx+1Ch], 1
0x140011b9b  jz      short loc_140011BB2
0x140011b9d  mov     edx, 21h ; '!'
0x140011ba2  mov     rcx, [rcx+10h]
0x140011ba6  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140011bad  call    WPP_SF_
0x140011bb2  cmp     [rbp+57h+IsMember], edi
0x140011bb5  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x140011bb9  setnz   bl
0x140011bbc  test    rcx, rcx
0x140011bbf  jz      short loc_140011BC7
0x140011bc1  call    cs:__imp_FreeSid
0x140011bc7  mov     al, bl
0x140011bc9  mov     rcx, [rbp+57h+var_10]
0x140011bcd  xor     rcx, rsp; StackCookie
0x140011bd0  call    __security_check_cookie
0x140011bd5  lea     r11, [rsp+0A0h+var_s0]
0x140011bdd  mov     rbx, [r11+10h]
0x140011be1  mov     rdi, [r11+18h]
0x140011be5  mov     rsp, r11
0x140011be8  pop     rbp
0x140011be9  retn
```
