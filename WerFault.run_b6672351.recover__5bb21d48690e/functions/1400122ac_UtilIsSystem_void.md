# UtilIsSystem(void)

- ea: `0x1400122ac`
- end: `0x1400123f5`
- name: `?UtilIsSystem@@YA_NXZ`
- size: `329`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004b414`
- `0x14005e9f8`

## callees

- `0x140002490`
- `0x14000e698`
- `0x1400122ac`
- `0x140014ee4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14001231a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14001231a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140012378`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140012378`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140012340`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400123c5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140012340`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400123c5`

## pseudocode

```c
bool UtilIsSystem(void)
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
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+3Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  pSid = (PSID *)utl::out_ptr<void,tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>,>(
                   &v9,
                   &SidToCheck);
  v1 = AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, pSid);
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
        v4 = 33;
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
      v4 = 32;
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
0x1400122ac  mov     [rsp-8+arg_0], rbx
0x1400122b1  mov     [rsp-8+arg_8], rdi
0x1400122b6  push    rbp
0x1400122b7  lea     rbp, [rsp-57h]
0x1400122bc  sub     rsp, 0A0h
0x1400122c3  mov     rax, cs:__security_cookie
0x1400122ca  xor     rax, rsp
0x1400122cd  mov     [rbp+57h+var_10], rax
0x1400122d1  xor     edi, edi
0x1400122d3  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1400122d9  lea     rdx, [rbp+57h+SidToCheck]
0x1400122dd  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x1400122e0  lea     rcx, [rbp+57h+var_30]
0x1400122e4  mov     [rbp+57h+SidToCheck], rdi
0x1400122e8  mov     [rbp+57h+IsMember], edi
0x1400122eb  call    ??$out_ptr@XV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z
0x1400122f0  mov     [rsp+0A0h+pSid], rax; pSid
0x1400122f5  lea     r8d, [rdi+12h]; nSubAuthority0
0x1400122f9  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x1400122fd  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140012301  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x140012305  xor     r9d, r9d; nSubAuthority1
0x140012308  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x14001230c  mov     dl, 1; nSubAuthorityCount
0x14001230e  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x140012312  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x140012316  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x14001231a  call    cs:__imp_AllocateAndInitializeSid
0x140012321  nop     dword ptr [rax+rax+00h]
0x140012326  mov     r8, [rbp+57h+var_30]
0x14001232a  mov     ebx, eax
0x14001232c  test    r8, r8
0x14001232f  jz      short loc_14001234C
0x140012331  mov     rdx, [rbp+57h+var_28]
0x140012335  mov     rcx, [rdx]; pSid
0x140012338  mov     [rdx], r8
0x14001233b  test    rcx, rcx
0x14001233e  jz      short loc_14001234C
0x140012340  call    cs:__imp_FreeSid
0x140012347  nop     dword ptr [rax+rax+00h]
0x14001234c  test    ebx, ebx
0x14001234e  jnz     short loc_14001236E
0x140012350  mov     rcx, cs:WPP_GLOBAL_Control
0x140012357  lea     rax, WPP_GLOBAL_Control
0x14001235e  cmp     rcx, rax
0x140012361  jz      short loc_1400123B6
0x140012363  test    byte ptr [rcx+1Ch], 1
0x140012367  jz      short loc_1400123B6
0x140012369  lea     edx, [rbx+20h]
0x14001236c  jmp     short loc_1400123A6
0x14001236e  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140012372  lea     r8, [rbp+57h+IsMember]; IsMember
0x140012376  xor     ecx, ecx; TokenHandle
0x140012378  call    cs:__imp_CheckTokenMembership
0x14001237f  nop     dword ptr [rax+rax+00h]
0x140012384  test    eax, eax
0x140012386  jnz     short loc_1400123B6
0x140012388  mov     rcx, cs:WPP_GLOBAL_Control
0x14001238f  lea     rax, WPP_GLOBAL_Control
0x140012396  cmp     rcx, rax
0x140012399  jz      short loc_1400123B6
0x14001239b  test    byte ptr [rcx+1Ch], 1
0x14001239f  jz      short loc_1400123B6
0x1400123a1  mov     edx, 21h ; '!'
0x1400123a6  mov     rcx, [rcx+10h]
0x1400123aa  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x1400123b1  call    WPP_SF_
0x1400123b6  cmp     [rbp+57h+IsMember], edi
0x1400123b9  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x1400123bd  setnz   bl
0x1400123c0  test    rcx, rcx
0x1400123c3  jz      short loc_1400123D1
0x1400123c5  call    cs:__imp_FreeSid
0x1400123cc  nop     dword ptr [rax+rax+00h]
0x1400123d1  mov     al, bl
0x1400123d3  mov     rcx, [rbp+57h+var_10]
0x1400123d7  xor     rcx, rsp; StackCookie
0x1400123da  call    __security_check_cookie
0x1400123df  lea     r11, [rsp+0A0h+var_s0]
0x1400123e7  mov     rbx, [r11+10h]
0x1400123eb  mov     rdi, [r11+18h]
0x1400123ef  mov     rsp, r11
0x1400123f2  pop     rbp
0x1400123f3  retn
```
