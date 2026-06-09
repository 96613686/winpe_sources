# SimpleCheckMembership(ulong,int *)

- ea: `0x1800194dc`
- end: `0x1800195fe`
- name: `?SimpleCheckMembership@@YAKKPEAH@Z`
- size: `290`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800178a4`

## callees

- `0x1800144b4`
- `0x1800194dc`
- `0x180019750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195a6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001954a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001954a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001959c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001959c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800195de`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800195de`

## pseudocode

```c
__int64 __fastcall SimpleCheckMembership(__int64 a1, int *a2)
{
  DWORD LastError; // ebx
  CIdentityProfileHandler *v4; // rcx
  __int64 v5; // rdx
  WINBOOL IsMember; // [rsp+60h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+1Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !a2 )
    return 87;
  *a2 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    IsMember = 0;
    if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      LastError = 0;
      *a2 = IsMember;
    }
    else
    {
      LastError = GetLastError();
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v5 = 16;
        goto LABEL_7;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v5 = 15;
LABEL_7:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_a8931f2c81c1305f250c9a1b52db8649_Traceguids, LastError);
    }
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return LastError;
}

```

## disassembly

```asm
0x1800194dc  push    rbp
0x1800194de  push    rbx
0x1800194df  push    rsi
0x1800194e0  push    rdi
0x1800194e1  lea     rbp, [rsp-3Fh]
0x1800194e6  sub     rsp, 88h
0x1800194ed  mov     rax, cs:__security_cookie
0x1800194f4  xor     rax, rsp
0x1800194f7  mov     [rbp+57h+var_28], rax
0x1800194fb  xor     esi, esi
0x1800194fd  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180019503  mov     [rbp+57h+SidToCheck], rsi
0x180019507  mov     rdi, rdx
0x18001950a  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18001950d  test    rdx, rdx
0x180019510  jnz     short loc_18001951A
0x180019512  lea     ebx, [rdx+57h]
0x180019515  jmp     loc_1800195E4
0x18001951a  lea     rax, [rbp+57h+SidToCheck]
0x18001951e  mov     [rdx], esi
0x180019520  mov     [rsp+0A0h+pSid], rax; pSid
0x180019525  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180019529  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x18001952d  xor     r9d, r9d; nSubAuthority1
0x180019530  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x180019534  mov     dl, 1; nSubAuthorityCount
0x180019536  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x18001953a  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x18001953e  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x180019542  lea     r8d, [r9+12h]; nSubAuthority0
0x180019546  mov     [rsp+0A0h+nSubAuthority2], esi; nSubAuthority2
0x18001954a  call    cs:__imp_AllocateAndInitializeSid
0x180019550  test    eax, eax
0x180019552  jnz     short loc_18001958F
0x180019554  call    cs:__imp_GetLastError
0x18001955a  mov     ebx, eax
0x18001955c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019563  lea     rax, WPP_GLOBAL_Control
0x18001956a  cmp     rcx, rax
0x18001956d  jz      short loc_1800195D5
0x18001956f  test    byte ptr [rcx+1Ch], 4
0x180019573  jz      short loc_1800195D5
0x180019575  mov     edx, 0Fh
0x18001957a  mov     rcx, [rcx+10h]
0x18001957e  lea     r8, WPP_a8931f2c81c1305f250c9a1b52db8649_Traceguids
0x180019585  mov     r9d, ebx
0x180019588  call    WPP_SF_d
0x18001958d  jmp     short loc_1800195D5
0x18001958f  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180019593  lea     r8, [rbp+57h+IsMember]; IsMember
0x180019597  xor     ecx, ecx; TokenHandle
0x180019599  mov     [rbp+57h+IsMember], esi
0x18001959c  call    cs:__imp_CheckTokenMembership
0x1800195a2  test    eax, eax
0x1800195a4  jnz     short loc_1800195CE
0x1800195a6  call    cs:__imp_GetLastError
0x1800195ac  mov     ebx, eax
0x1800195ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195b5  lea     rax, WPP_GLOBAL_Control
0x1800195bc  cmp     rcx, rax
0x1800195bf  jz      short loc_1800195D5
0x1800195c1  test    byte ptr [rcx+1Ch], 4
0x1800195c5  jz      short loc_1800195D5
0x1800195c7  mov     edx, 10h
0x1800195cc  jmp     short loc_18001957A
0x1800195ce  mov     eax, [rbp+57h+IsMember]
0x1800195d1  mov     ebx, esi
0x1800195d3  mov     [rdi], eax
0x1800195d5  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x1800195d9  test    rcx, rcx
0x1800195dc  jz      short loc_1800195E4
0x1800195de  call    cs:__imp_FreeSid
0x1800195e4  mov     eax, ebx
0x1800195e6  mov     rcx, [rbp+57h+var_28]
0x1800195ea  xor     rcx, rsp; StackCookie
0x1800195ed  call    __security_check_cookie
0x1800195f2  add     rsp, 88h
0x1800195f9  pop     rdi
0x1800195fa  pop     rsi
0x1800195fb  pop     rbx
0x1800195fc  pop     rbp
0x1800195fd  retn
```
