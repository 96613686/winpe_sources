# UtilIsWindowManagerToken(void *)

- ea: `0x140012658`
- end: `0x14001277e`
- name: `?UtilIsWindowManagerToken@@YAJPEAX@Z`
- size: `294`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005e9f8`

## callees

- `0x140002490`
- `0x14000e698`
- `0x140012658`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012720`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1400126c6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1400126c6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140012706`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140012706`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400126ec`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14001274e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400126ec`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14001274e`

## pseudocode

```c
__int64 __fastcall UtilIsWindowManagerToken(void *a1)
{
  PSID *pSid; // rax
  BOOL v2; // ebx
  void *v3; // rcx
  int v4; // ebx
  signed int LastError; // eax
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
  v2 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x5Au, 0, 0, 0, 0, 0, 0, 0, pSid);
  if ( v9 )
  {
    v3 = *v10;
    *v10 = v9;
    if ( v3 )
      FreeSid(v3);
  }
  if ( v2 && CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v4 = IsMember == 0;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147467259;
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140012658  mov     [rsp-8+arg_0], rbx
0x14001265d  mov     [rsp-8+arg_8], rdi
0x140012662  push    rbp
0x140012663  lea     rbp, [rsp-57h]
0x140012668  sub     rsp, 0A0h
0x14001266f  mov     rax, cs:__security_cookie
0x140012676  xor     rax, rsp
0x140012679  mov     [rbp+57h+var_10], rax
0x14001267d  xor     edi, edi
0x14001267f  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140012685  lea     rdx, [rbp+57h+SidToCheck]
0x140012689  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x14001268c  lea     rcx, [rbp+57h+var_30]
0x140012690  mov     [rbp+57h+SidToCheck], rdi
0x140012694  mov     [rbp+57h+IsMember], edi
0x140012697  call    ??$out_ptr@XV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z
0x14001269c  mov     [rsp+0A0h+pSid], rax; pSid
0x1400126a1  lea     r8d, [rdi+5Ah]; nSubAuthority0
0x1400126a5  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x1400126a9  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1400126ad  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x1400126b1  xor     r9d, r9d; nSubAuthority1
0x1400126b4  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x1400126b8  mov     dl, 2; nSubAuthorityCount
0x1400126ba  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x1400126be  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x1400126c2  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x1400126c6  call    cs:__imp_AllocateAndInitializeSid
0x1400126cd  nop     dword ptr [rax+rax+00h]
0x1400126d2  mov     r8, [rbp+57h+var_30]
0x1400126d6  mov     ebx, eax
0x1400126d8  test    r8, r8
0x1400126db  jz      short loc_1400126F8
0x1400126dd  mov     rdx, [rbp+57h+var_28]
0x1400126e1  mov     rcx, [rdx]; pSid
0x1400126e4  mov     [rdx], r8
0x1400126e7  test    rcx, rcx
0x1400126ea  jz      short loc_1400126F8
0x1400126ec  call    cs:__imp_FreeSid
0x1400126f3  nop     dword ptr [rax+rax+00h]
0x1400126f8  test    ebx, ebx
0x1400126fa  jz      short loc_140012720
0x1400126fc  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140012700  lea     r8, [rbp+57h+IsMember]; IsMember
0x140012704  xor     ecx, ecx; TokenHandle
0x140012706  call    cs:__imp_CheckTokenMembership
0x14001270d  nop     dword ptr [rax+rax+00h]
0x140012712  test    eax, eax
0x140012714  jz      short loc_140012720
0x140012716  cmp     [rbp+57h+IsMember], edi
0x140012719  mov     ebx, edi
0x14001271b  setz    bl
0x14001271e  jmp     short loc_140012745
0x140012720  call    cs:__imp_GetLastError
0x140012727  nop     dword ptr [rax+rax+00h]
0x14001272c  mov     ebx, eax
0x14001272e  test    eax, eax
0x140012730  jle     short loc_14001273B
0x140012732  movzx   ebx, ax
0x140012735  or      ebx, 80070000h
0x14001273b  test    ebx, ebx
0x14001273d  mov     eax, 80004005h
0x140012742  cmovns  ebx, eax
0x140012745  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x140012749  test    rcx, rcx
0x14001274c  jz      short loc_14001275A
0x14001274e  call    cs:__imp_FreeSid
0x140012755  nop     dword ptr [rax+rax+00h]
0x14001275a  mov     eax, ebx
0x14001275c  mov     rcx, [rbp+57h+var_10]
0x140012760  xor     rcx, rsp; StackCookie
0x140012763  call    __security_check_cookie
0x140012768  lea     r11, [rsp+0A0h+var_s0]
0x140012770  mov     rbx, [r11+10h]
0x140012774  mov     rdi, [r11+18h]
0x140012778  mov     rsp, r11
0x14001277b  pop     rbp
0x14001277c  retn
```
