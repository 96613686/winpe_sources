# IsSystem(void)

- ea: `0x402737`
- end: `0x4027b5`
- name: `?IsSystem@@YGHXZ`
- size: `126`
- prototype: `BOOL __stdcall()`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x402ae4`
- `0x4081a5`

## callees

- `0x402737`
- `0x40cb60`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x402786`
- `ADVAPI32!CheckTokenMembership` at `0x402786`
- `ADVAPI32!FreeSid` at `0x40279e`
- `ADVAPI32!FreeSid` at `0x40279e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x402774`
- `ADVAPI32!AllocateAndInitializeSid` at `0x402774`

## pseudocode

```c
BOOL __stdcall IsSystem()
{
  BOOL v0; // esi
  BOOL IsMember; // [esp+Ch] [ebp-14h] BYREF
  PSID pSid; // [esp+10h] [ebp-10h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [esp+14h] [ebp-Ch] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  v0 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid)
    && CheckTokenMembership(0, pSid, &IsMember) )
  {
    v0 = IsMember;
  }
  if ( pSid )
    FreeSid(pSid);
  return v0;
}

```

## disassembly

```asm
0x402737  mov     edi, edi
0x402739  push    ebp
0x40273a  mov     ebp, esp
0x40273c  sub     esp, 14h
0x40273f  mov     eax, ___security_cookie
0x402744  xor     eax, ebp
0x402746  mov     [ebp+var_4], eax
0x402749  push    ebx
0x40274a  push    esi
0x40274b  push    edi
0x40274c  xor     ebx, ebx
0x40274e  mov     word ptr [ebp+pIdentifierAuthority.Value+4], 500h
0x402754  lea     eax, [ebp+pSid]
0x402757  mov     [ebp+IsMember], ebx
0x40275a  push    eax; pSid
0x40275b  push    ebx; nSubAuthority7
0x40275c  push    ebx; nSubAuthority6
0x40275d  push    ebx; nSubAuthority5
0x40275e  push    ebx; nSubAuthority4
0x40275f  push    ebx; nSubAuthority3
0x402760  push    ebx; nSubAuthority2
0x402761  push    ebx; nSubAuthority1
0x402762  push    12h; nSubAuthority0
0x402764  xor     edi, edi
0x402766  mov     dword ptr [ebp+pIdentifierAuthority.Value], ebx
0x402769  inc     edi
0x40276a  mov     [ebp+pSid], ebx
0x40276d  push    edi; nSubAuthorityCount
0x40276e  lea     eax, [ebp+pIdentifierAuthority]
0x402771  mov     esi, ebx
0x402773  push    eax; pIdentifierAuthority
0x402774  call    ds:__imp__AllocateAndInitializeSid@44; AllocateAndInitializeSid(x,x,x,x,x,x,x,x,x,x,x)
0x40277a  test    eax, eax
0x40277c  jz      short loc_402796
0x40277e  lea     eax, [ebp+IsMember]
0x402781  push    eax; IsMember
0x402782  push    [ebp+pSid]; SidToCheck
0x402785  push    ebx; TokenHandle
0x402786  call    ds:__imp__CheckTokenMembership@12; CheckTokenMembership(x,x,x)
0x40278c  test    eax, eax
0x40278e  jz      short loc_402796
0x402790  cmp     [ebp+IsMember], ebx
0x402793  cmovnz  esi, edi
0x402796  cmp     [ebp+pSid], ebx
0x402799  jz      short loc_4027A4
0x40279b  push    [ebp+pSid]; pSid
0x40279e  call    ds:__imp__FreeSid@4; FreeSid(x)
0x4027a4  mov     ecx, [ebp+var_4]
0x4027a7  mov     eax, esi
0x4027a9  pop     edi
0x4027aa  pop     esi
0x4027ab  xor     ecx, ebp; StackCookie
0x4027ad  pop     ebx
0x4027ae  call    @__security_check_cookie@4; __security_check_cookie(x)
0x4027b3  leave
0x4027b4  retn
```
