# UtilIsVirtualServer(void)

- ea: `0x1400123fc`
- end: `0x140012545`
- name: `?UtilIsVirtualServer@@YA_NXZ`
- size: `329`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005e9f8`

## callees

- `0x140002490`
- `0x14000e698`
- `0x1400123fc`
- `0x140014ee4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14001246a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14001246a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400124c8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400124c8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140012490`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140012515`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140012490`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140012515`

## pseudocode

```c
bool UtilIsVirtualServer(void)
{
  PSID *pSid; // rax
  BOOL v1; // ebx
  void *v2; // rcx
  CUserModeHangReport *v3; // rcx
  __int64 v4; // rdx
  bool v5; // bl
  WINBOOL IsMember; // [rsp+60h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+1Fh] BYREF
  void *v9; // [rsp+70h] [rbp+27h] BYREF
  void **v10; // [rsp+78h] [rbp+2Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+3Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  pSid = (PSID *)utl::out_ptr<void,tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>,>(
                   &v9,
                   &SidToCheck);
  v1 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x53u, 0, 0, 0, 0, 0, 0, 0, pSid);
  if ( v9 )
  {
    v2 = *v10;
    *v10 = v9;
    if ( v2 )
      FreeSid(v2);
  }
  if ( v1 )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 31;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 30;
LABEL_12:
      WPP_SF_(*((_QWORD *)v3 + 2), v4, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
    }
  }
  v5 = IsMember != 0;
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v5;
}

```

## disassembly

```asm
0x1400123fc  mov     [rsp-8+arg_0], rbx
0x140012401  mov     [rsp-8+arg_8], rdi
0x140012406  push    rbp
0x140012407  lea     rbp, [rsp-57h]
0x14001240c  sub     rsp, 0A0h
0x140012413  mov     rax, cs:__security_cookie
0x14001241a  xor     rax, rsp
0x14001241d  mov     [rbp+57h+var_10], rax
0x140012421  xor     edi, edi
0x140012423  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140012429  lea     rdx, [rbp+57h+SidToCheck]
0x14001242d  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x140012430  lea     rcx, [rbp+57h+var_30]
0x140012434  mov     [rbp+57h+SidToCheck], rdi
0x140012438  mov     [rbp+57h+IsMember], edi
0x14001243b  call    ??$out_ptr@XV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z
0x140012440  mov     [rsp+0A0h+pSid], rax; pSid
0x140012445  lea     r8d, [rdi+53h]; nSubAuthority0
0x140012449  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x14001244d  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140012451  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x140012455  xor     r9d, r9d; nSubAuthority1
0x140012458  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x14001245c  mov     dl, 2; nSubAuthorityCount
0x14001245e  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x140012462  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x140012466  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x14001246a  call    cs:__imp_AllocateAndInitializeSid
0x140012471  nop     dword ptr [rax+rax+00h]
0x140012476  mov     r8, [rbp+57h+var_30]
0x14001247a  mov     ebx, eax
0x14001247c  test    r8, r8
0x14001247f  jz      short loc_14001249C
0x140012481  mov     rdx, [rbp+57h+var_28]
0x140012485  mov     rcx, [rdx]; pSid
0x140012488  mov     [rdx], r8
0x14001248b  test    rcx, rcx
0x14001248e  jz      short loc_14001249C
0x140012490  call    cs:__imp_FreeSid
0x140012497  nop     dword ptr [rax+rax+00h]
0x14001249c  test    ebx, ebx
0x14001249e  jnz     short loc_1400124BE
0x1400124a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400124a7  lea     rax, WPP_GLOBAL_Control
0x1400124ae  cmp     rcx, rax
0x1400124b1  jz      short loc_140012506
0x1400124b3  test    byte ptr [rcx+1Ch], 1
0x1400124b7  jz      short loc_140012506
0x1400124b9  lea     edx, [rbx+1Eh]
0x1400124bc  jmp     short loc_1400124F6
0x1400124be  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1400124c2  lea     r8, [rbp+57h+IsMember]; IsMember
0x1400124c6  xor     ecx, ecx; TokenHandle
0x1400124c8  call    cs:__imp_CheckTokenMembership
0x1400124cf  nop     dword ptr [rax+rax+00h]
0x1400124d4  test    eax, eax
0x1400124d6  jnz     short loc_140012506
0x1400124d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400124df  lea     rax, WPP_GLOBAL_Control
0x1400124e6  cmp     rcx, rax
0x1400124e9  jz      short loc_140012506
0x1400124eb  test    byte ptr [rcx+1Ch], 1
0x1400124ef  jz      short loc_140012506
0x1400124f1  mov     edx, 1Fh
0x1400124f6  mov     rcx, [rcx+10h]
0x1400124fa  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x140012501  call    WPP_SF_
0x140012506  cmp     [rbp+57h+IsMember], edi
0x140012509  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x14001250d  setnz   bl
0x140012510  test    rcx, rcx
0x140012513  jz      short loc_140012521
0x140012515  call    cs:__imp_FreeSid
0x14001251c  nop     dword ptr [rax+rax+00h]
0x140012521  mov     al, bl
0x140012523  mov     rcx, [rbp+57h+var_10]
0x140012527  xor     rcx, rsp; StackCookie
0x14001252a  call    __security_check_cookie
0x14001252f  lea     r11, [rsp+0A0h+var_s0]
0x140012537  mov     rbx, [r11+10h]
0x14001253b  mov     rdi, [r11+18h]
0x14001253f  mov     rsp, r11
0x140012542  pop     rbp
0x140012543  retn
```
