# BdeCfgIsElevated(void)

- ea: `0x180007730`
- end: `0x18000781c`
- name: `?BdeCfgIsElevated@@YAJXZ`
- size: `236`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180007730`
- `0x1800135c0`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x1800077f3`
- `ADVAPI32!FreeSid` at `0x1800077f3`
- `ADVAPI32!CheckTokenMembership` at `0x1800077c1`
- `ADVAPI32!CheckTokenMembership` at `0x1800077c1`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180007796`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180007796`
- `KERNEL32!GetLastError` at `0x1800077a0`
- `KERNEL32!GetLastError` at `0x1800077cb`
- `KERNEL32!GetLastError` at `0x1800077a0`
- `KERNEL32!GetLastError` at `0x1800077cb`

## pseudocode

```c
__int64 BdeCfgIsElevated(void)
{
  signed int v0; // eax
  unsigned int v1; // ebx
  signed int LastError; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  SidToCheck = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      v1 = 0;
      if ( !IsMember )
        v1 = -1063256063;
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
    }
    FreeSid(SidToCheck);
  }
  else
  {
    v0 = GetLastError();
    v1 = v0;
    if ( v0 > 0 )
      return (unsigned __int16)v0 | 0x80070000;
  }
  return v1;
}

```

## disassembly

```asm
0x180007730  mov     [rsp-8+arg_0], rbx
0x180007735  mov     [rsp-8+arg_8], rdi
0x18000773a  push    rbp
0x18000773b  mov     rbp, rsp
0x18000773e  sub     rsp, 80h
0x180007745  mov     rax, cs:__security_cookie
0x18000774c  xor     rax, rsp
0x18000774f  mov     [rbp+var_8], rax
0x180007753  xor     edi, edi
0x180007755  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18000775b  lea     rax, [rbp+SidToCheck]
0x18000775f  mov     [rbp+IsMember], edi
0x180007762  mov     [rsp+80h+pSid], rax; pSid
0x180007767  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18000776b  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x18000776f  mov     r9d, 220h; nSubAuthority1
0x180007775  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180007779  lea     r8d, [rdi+20h]; nSubAuthority0
0x18000777d  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x180007781  mov     dl, 2; nSubAuthorityCount
0x180007783  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180007787  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x18000778b  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x18000778f  mov     [rbp+SidToCheck], rdi
0x180007793  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x180007796  call    cs:__imp_AllocateAndInitializeSid
0x18000779c  test    eax, eax
0x18000779e  jnz     short loc_1800077B7
0x1800077a0  call    cs:__imp_GetLastError
0x1800077a6  mov     ebx, eax
0x1800077a8  test    eax, eax
0x1800077aa  jle     short loc_1800077F9
0x1800077ac  movzx   ebx, ax
0x1800077af  or      ebx, 80070000h
0x1800077b5  jmp     short loc_1800077F9
0x1800077b7  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1800077bb  lea     r8, [rbp+IsMember]; IsMember
0x1800077bf  xor     ecx, ecx; TokenHandle
0x1800077c1  call    cs:__imp_CheckTokenMembership
0x1800077c7  test    eax, eax
0x1800077c9  jnz     short loc_1800077E2
0x1800077cb  call    cs:__imp_GetLastError
0x1800077d1  mov     ebx, eax
0x1800077d3  test    eax, eax
0x1800077d5  jle     short loc_1800077EF
0x1800077d7  movzx   ebx, ax
0x1800077da  or      ebx, 80070000h
0x1800077e0  jmp     short loc_1800077EF
0x1800077e2  cmp     [rbp+IsMember], edi
0x1800077e5  mov     ebx, edi
0x1800077e7  mov     eax, 0C0A00001h
0x1800077ec  cmovz   ebx, eax
0x1800077ef  mov     rcx, [rbp+SidToCheck]; pSid
0x1800077f3  call    cs:__imp_FreeSid
0x1800077f9  mov     eax, ebx
0x1800077fb  mov     rcx, [rbp+var_8]
0x1800077ff  xor     rcx, rsp; StackCookie
0x180007802  call    __security_check_cookie
0x180007807  lea     r11, [rsp+80h+var_s0]
0x18000780f  mov     rbx, [r11+10h]
0x180007813  mov     rdi, [r11+18h]
0x180007817  mov     rsp, r11
0x18000781a  pop     rbp
0x18000781b  retn
```
