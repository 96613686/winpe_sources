# CMiscHelpersT<CEmptyType>::IsAdmin(void *,int *)

- ea: `0x140011be4`
- end: `0x140011d10`
- name: `?IsAdmin@?$CMiscHelpersT@VCEmptyType@@@@SAJPEAXPEAH@Z`
- size: `300`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140012124`

## callees

- `0x1400076c8`
- `0x140011be4`
- `0x1400135b8`
- `0x140080d70`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x140011cb8`
- `ADVAPI32!CheckTokenMembership` at `0x140011cb8`
- `ADVAPI32!FreeSid` at `0x140011cdd`
- `ADVAPI32!FreeSid` at `0x140011cdd`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140011c77`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140011c77`
- `KERNEL32!GetLastError` at `0x140011c87`
- `KERNEL32!GetLastError` at `0x140011c87`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::IsAdmin(HANDLE TokenHandle, WINBOOL *a2)
{
  unsigned int v4; // ebx
  signed int LastError; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  IsMember = 0;
  SidToCheck = 0;
  v4 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_11;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck)
    || !CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    goto LABEL_3;
  }
  *a2 = IsMember;
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v4;
}

```

## disassembly

```asm
0x140011be4  mov     [rsp-18h+arg_10], rbx
0x140011be9  mov     [rsp-18h+arg_18], rsi
0x140011bee  push    rbp
0x140011bef  push    rdi
0x140011bf0  push    r14
0x140011bf2  mov     rbp, rsp
0x140011bf5  sub     rsp, 80h
0x140011bfc  mov     rax, cs:__security_cookie
0x140011c03  xor     rax, rsp
0x140011c06  mov     [rbp+var_8], rax
0x140011c0a  xor     r14d, r14d
0x140011c0d  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x140011c13  mov     dword ptr [rbp+pIdentifierAuthority.Value], r14d
0x140011c17  mov     rdi, rdx
0x140011c1a  mov     [rbp+IsMember], r14d
0x140011c1e  mov     rsi, rcx
0x140011c21  mov     [rbp+SidToCheck], r14
0x140011c25  mov     ebx, r14d
0x140011c28  test    rdx, rdx
0x140011c2b  jnz     short loc_140011C3E
0x140011c2d  mov     ebx, 80070057h
0x140011c32  mov     ecx, ebx
0x140011c34  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140011c39  jmp     loc_140011CCD
0x140011c3e  lea     rax, [rbp+SidToCheck]
0x140011c42  mov     r9d, 220h; nSubAuthority1
0x140011c48  mov     [rsp+80h+pSid], rax; pSid
0x140011c4d  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x140011c51  mov     [rsp+80h+nSubAuthority7], r14d; nSubAuthority7
0x140011c56  mov     r8d, 20h ; ' '; nSubAuthority0
0x140011c5c  mov     [rsp+80h+nSubAuthority6], r14d; nSubAuthority6
0x140011c61  mov     dl, 2; nSubAuthorityCount
0x140011c63  mov     [rsp+80h+nSubAuthority5], r14d; nSubAuthority5
0x140011c68  mov     [rsp+80h+nSubAuthority4], r14d; nSubAuthority4
0x140011c6d  mov     [rsp+80h+nSubAuthority3], r14d; nSubAuthority3
0x140011c72  mov     [rsp+80h+nSubAuthority2], r14d; nSubAuthority2
0x140011c77  call    cs:__imp_AllocateAndInitializeSid
0x140011c7e  nop     dword ptr [rax+rax+00h]
0x140011c83  test    eax, eax
0x140011c85  jnz     short loc_140011CAD
0x140011c87  call    cs:__imp_GetLastError
0x140011c8e  nop     dword ptr [rax+rax+00h]
0x140011c93  mov     ebx, eax
0x140011c95  test    eax, eax
0x140011c97  jnz     short loc_140011CA0
0x140011c99  mov     ebx, 80004005h
0x140011c9e  jmp     short loc_140011C32
0x140011ca0  jle     short loc_140011C32
0x140011ca2  movzx   ebx, ax
0x140011ca5  or      ebx, 80070000h
0x140011cab  jmp     short loc_140011C32
0x140011cad  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x140011cb1  lea     r8, [rbp+IsMember]; IsMember
0x140011cb5  mov     rcx, rsi; TokenHandle
0x140011cb8  call    cs:__imp_CheckTokenMembership
0x140011cbf  nop     dword ptr [rax+rax+00h]
0x140011cc4  test    eax, eax
0x140011cc6  jz      short loc_140011C87
0x140011cc8  mov     ecx, [rbp+IsMember]
0x140011ccb  mov     [rdi], ecx
0x140011ccd  mov     ecx, ebx
0x140011ccf  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140011cd4  mov     rcx, [rbp+SidToCheck]; pSid
0x140011cd8  test    rcx, rcx
0x140011cdb  jz      short loc_140011CE9
0x140011cdd  call    cs:__imp_FreeSid
0x140011ce4  nop     dword ptr [rax+rax+00h]
0x140011ce9  mov     eax, ebx
0x140011ceb  mov     rcx, [rbp+var_8]
0x140011cef  xor     rcx, rsp; StackCookie
0x140011cf2  call    __security_check_cookie
0x140011cf7  lea     r11, [rsp+80h+var_s0]
0x140011cff  mov     rbx, [r11+30h]
0x140011d03  mov     rsi, [r11+38h]
0x140011d07  mov     rsp, r11
0x140011d0a  pop     r14
0x140011d0c  pop     rdi
0x140011d0d  pop     rbp
0x140011d0e  retn
```
