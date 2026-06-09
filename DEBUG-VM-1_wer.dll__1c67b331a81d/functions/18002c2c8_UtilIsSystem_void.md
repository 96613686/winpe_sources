# UtilIsSystem(void)

- ea: `0x18002c2c8`
- end: `0x18002c3fa`
- name: `?UtilIsSystem@@YA_NXZ`
- size: `306`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c26c`

## callees

- `0x180004bb4`
- `0x18002c2c8`
- `0x180050db0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002c358`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002c3d1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002c358`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002c3d1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002c338`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002c338`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002c38a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002c38a`

## pseudocode

```c
bool UtilIsSystem(void)
{
  BOOL v0; // ebx
  PSID v1; // rcx
  wchar_t *v2; // rcx
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
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v3 = 33;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
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
0x18002c2c8  mov     r11, rsp
0x18002c2cb  mov     [r11+8], rbx
0x18002c2cf  mov     [r11+10h], rdi
0x18002c2d3  push    rbp
0x18002c2d4  lea     rbp, [r11-5Fh]
0x18002c2d8  sub     rsp, 0A0h
0x18002c2df  mov     rax, cs:__security_cookie
0x18002c2e6  xor     rax, rsp
0x18002c2e9  mov     [rbp+57h+var_10], rax
0x18002c2ed  xor     edi, edi
0x18002c2ef  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18002c2f5  lea     rax, [rbp+57h+SidToCheck]
0x18002c2f9  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x18002c2fc  mov     [rbp+57h+var_28], rax
0x18002c300  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18002c304  lea     rax, [rbp+57h+var_30]
0x18002c308  mov     [rbp+57h+IsMember], edi
0x18002c30b  mov     [r11-58h], rax
0x18002c30f  lea     r8d, [rdi+12h]; nSubAuthority0
0x18002c313  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x18002c317  xor     r9d, r9d; nSubAuthority1
0x18002c31a  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x18002c31e  mov     dl, 1; nSubAuthorityCount
0x18002c320  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x18002c324  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x18002c328  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x18002c32c  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x18002c330  mov     [rbp+57h+var_30], rdi
0x18002c334  mov     [rbp+57h+SidToCheck], rdi
0x18002c338  call    cs:__imp_AllocateAndInitializeSid
0x18002c33e  mov     r8, [rbp+57h+var_30]
0x18002c342  mov     ebx, eax
0x18002c344  test    r8, r8
0x18002c347  jz      short loc_18002C35E
0x18002c349  mov     rdx, [rbp+57h+var_28]
0x18002c34d  mov     rcx, [rdx]; pSid
0x18002c350  mov     [rdx], r8
0x18002c353  test    rcx, rcx
0x18002c356  jz      short loc_18002C35E
0x18002c358  call    cs:__imp_FreeSid
0x18002c35e  test    ebx, ebx
0x18002c360  jnz     short loc_18002C380
0x18002c362  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c369  lea     rax, WPP_GLOBAL_Control
0x18002c370  cmp     rcx, rax
0x18002c373  jz      short loc_18002C3C2
0x18002c375  test    byte ptr [rcx+1Ch], 1
0x18002c379  jz      short loc_18002C3C2
0x18002c37b  lea     edx, [rbx+20h]
0x18002c37e  jmp     short loc_18002C3B2
0x18002c380  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18002c384  lea     r8, [rbp+57h+IsMember]; IsMember
0x18002c388  xor     ecx, ecx; TokenHandle
0x18002c38a  call    cs:__imp_CheckTokenMembership
0x18002c390  test    eax, eax
0x18002c392  jnz     short loc_18002C3C2
0x18002c394  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c39b  lea     rax, WPP_GLOBAL_Control
0x18002c3a2  cmp     rcx, rax
0x18002c3a5  jz      short loc_18002C3C2
0x18002c3a7  test    byte ptr [rcx+1Ch], 1
0x18002c3ab  jz      short loc_18002C3C2
0x18002c3ad  mov     edx, 21h ; '!'
0x18002c3b2  mov     rcx, [rcx+10h]
0x18002c3b6  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18002c3bd  call    WPP_SF_
0x18002c3c2  cmp     [rbp+57h+IsMember], edi
0x18002c3c5  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18002c3c9  setnz   bl
0x18002c3cc  test    rcx, rcx
0x18002c3cf  jz      short loc_18002C3D7
0x18002c3d1  call    cs:__imp_FreeSid
0x18002c3d7  mov     al, bl
0x18002c3d9  mov     rcx, [rbp+57h+var_10]
0x18002c3dd  xor     rcx, rsp; StackCookie
0x18002c3e0  call    __security_check_cookie
0x18002c3e5  lea     r11, [rsp+0A0h+var_s0]
0x18002c3ed  mov     rbx, [r11+10h]
0x18002c3f1  mov     rdi, [r11+18h]
0x18002c3f5  mov     rsp, r11
0x18002c3f8  pop     rbp
0x18002c3f9  retn
```
