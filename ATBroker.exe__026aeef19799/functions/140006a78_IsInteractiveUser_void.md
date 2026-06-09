# IsInteractiveUser(void)

- ea: `0x140006a78`
- end: `0x140006b33`
- name: `?IsInteractiveUser@@YAHXZ`
- size: `187`
- prototype: `int(void)`
- caller_count: `12`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400048b8`
- `0x14000b250`
- `0x14000c8b4`
- `0x14000e0c0`
- `0x14000ee8c`
- `0x14000fd08`
- `0x140010244`
- `0x140010714`
- `0x140011c60`
- `0x140011f08`
- `0x140012640`
- `0x14001271c`

## callees

- `0x140006a78`
- `0x140015b00`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x140006afc`
- `ADVAPI32!CheckTokenMembership` at `0x140006afc`
- `ADVAPI32!FreeSid` at `0x140006b08`
- `ADVAPI32!FreeSid` at `0x140006b08`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140006adb`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140006adb`

## pseudocode

```c
__int64 IsInteractiveUser(void)
{
  unsigned int v0; // edi
  PSID v1; // rdx
  BOOL v2; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  v0 = 1;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    v1 = SidToCheck;
  }
  else
  {
    v1 = 0;
    SidToCheck = 0;
  }
  if ( !v1 )
    return 0;
  v2 = CheckTokenMembership(0, v1, &IsMember);
  FreeSid(SidToCheck);
  if ( !v2 || !IsMember )
    return 0;
  return v0;
}

```

## disassembly

```asm
0x140006a78  push    rbp
0x140006a7a  push    rbx
0x140006a7b  push    rsi
0x140006a7c  push    rdi
0x140006a7d  lea     rbp, [rsp-3Fh]
0x140006a82  sub     rsp, 88h
0x140006a89  mov     rax, cs:__security_cookie
0x140006a90  xor     rax, rsp
0x140006a93  mov     [rbp+57h+var_28], rax
0x140006a97  xor     esi, esi
0x140006a99  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140006a9f  lea     rax, [rbp+57h+SidToCheck]
0x140006aa3  mov     [rbp+57h+IsMember], esi
0x140006aa6  mov     [rsp+0A0h+pSid], rax; pSid
0x140006aab  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140006aaf  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x140006ab3  xor     r9d, r9d; nSubAuthority1
0x140006ab6  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x140006aba  lea     edi, [rsi+1]
0x140006abd  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x140006ac1  lea     r8d, [rsi+4]; nSubAuthority0
0x140006ac5  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x140006ac9  mov     dl, dil; nSubAuthorityCount
0x140006acc  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x140006ad0  mov     [rsp+0A0h+nSubAuthority2], esi; nSubAuthority2
0x140006ad4  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x140006ad7  mov     [rbp+57h+SidToCheck], rsi
0x140006adb  call    cs:__imp_AllocateAndInitializeSid
0x140006ae1  test    eax, eax
0x140006ae3  jnz     short loc_140006AED
0x140006ae5  mov     edx, esi
0x140006ae7  mov     [rbp+57h+SidToCheck], rdx
0x140006aeb  jmp     short loc_140006AF1
0x140006aed  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140006af1  test    rdx, rdx
0x140006af4  jz      short loc_140006B17
0x140006af6  lea     r8, [rbp+57h+IsMember]; IsMember
0x140006afa  xor     ecx, ecx; TokenHandle
0x140006afc  call    cs:__imp_CheckTokenMembership
0x140006b02  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x140006b06  mov     ebx, eax
0x140006b08  call    cs:__imp_FreeSid
0x140006b0e  test    ebx, ebx
0x140006b10  jz      short loc_140006B17
0x140006b12  cmp     [rbp+57h+IsMember], esi
0x140006b15  jnz     short loc_140006B19
0x140006b17  mov     edi, esi
0x140006b19  mov     eax, edi
0x140006b1b  mov     rcx, [rbp+57h+var_28]
0x140006b1f  xor     rcx, rsp; StackCookie
0x140006b22  call    __security_check_cookie
0x140006b27  add     rsp, 88h
0x140006b2e  pop     rdi
0x140006b2f  pop     rsi
0x140006b30  pop     rbx
0x140006b31  pop     rbp
0x140006b32  retn
```
