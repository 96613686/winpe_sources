# IsAdminWithHighIL(void)

- ea: `0x4027bb`
- end: `0x402858`
- name: `?IsAdminWithHighIL@@YGHXZ`
- size: `157`
- prototype: `BOOL __stdcall()`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x402ae4`
- `0x4081a5`

## callees

- `0x4027bb`
- `0x40cb60`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x40280b`
- `ADVAPI32!CheckTokenMembership` at `0x40280b`
- `ADVAPI32!FreeSid` at `0x402842`
- `ADVAPI32!FreeSid` at `0x402842`
- `ADVAPI32!AllocateAndInitializeSid` at `0x4027f9`
- `ADVAPI32!AllocateAndInitializeSid` at `0x4027f9`
- `iertutil!__imp_?GetProcessIntegrityLevel@@YGJPAXPAK@Z` at `0x402826`
- `iertutil!__imp_?GetProcessIntegrityLevel@@YGJPAXPAK@Z` at `0x402826`

## pseudocode

```c
BOOL __stdcall IsAdminWithHighIL()
{
  BOOL v0; // esi
  unsigned int v2; // [esp+8h] [ebp-18h] BYREF
  BOOL IsMember; // [esp+Ch] [ebp-14h] BYREF
  PSID pSid; // [esp+10h] [ebp-10h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [esp+14h] [ebp-Ch] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v0 = 0;
  pSid = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    if ( CheckTokenMembership(0, pSid, &IsMember) )
    {
      if ( IsMember )
      {
        v2 = 4096;
        if ( !GetProcessIntegrityLevel(0, &v2) )
          v0 = v2 >= 0x3000;
      }
    }
  }
  if ( pSid )
    FreeSid(pSid);
  return v0;
}

```

## disassembly

```asm
0x4027bb  mov     edi, edi
0x4027bd  push    ebp
0x4027be  mov     ebp, esp
0x4027c0  sub     esp, 18h
0x4027c3  mov     eax, ___security_cookie
0x4027c8  xor     eax, ebp
0x4027ca  mov     [ebp+var_4], eax
0x4027cd  push    ebx
0x4027ce  push    esi
0x4027cf  xor     ebx, ebx
0x4027d1  mov     word ptr [ebp+pIdentifierAuthority.Value+4], 500h
0x4027d7  lea     eax, [ebp+pSid]
0x4027da  mov     [ebp+IsMember], ebx
0x4027dd  push    eax; pSid
0x4027de  push    ebx; nSubAuthority7
0x4027df  push    ebx; nSubAuthority6
0x4027e0  push    ebx; nSubAuthority5
0x4027e1  push    ebx; nSubAuthority4
0x4027e2  push    ebx; nSubAuthority3
0x4027e3  push    ebx; nSubAuthority2
0x4027e4  push    220h; nSubAuthority1
0x4027e9  push    20h ; ' '; nSubAuthority0
0x4027eb  push    2; nSubAuthorityCount
0x4027ed  lea     eax, [ebp+pIdentifierAuthority]
0x4027f0  mov     dword ptr [ebp+pIdentifierAuthority.Value], ebx
0x4027f3  push    eax; pIdentifierAuthority
0x4027f4  mov     esi, ebx
0x4027f6  mov     [ebp+pSid], ebx
0x4027f9  call    ds:__imp__AllocateAndInitializeSid@44; AllocateAndInitializeSid(x,x,x,x,x,x,x,x,x,x,x)
0x4027ff  test    eax, eax
0x402801  jz      short loc_40283A
0x402803  lea     eax, [ebp+IsMember]
0x402806  push    eax; IsMember
0x402807  push    [ebp+pSid]; SidToCheck
0x40280a  push    ebx; TokenHandle
0x40280b  call    ds:__imp__CheckTokenMembership@12; CheckTokenMembership(x,x,x)
0x402811  test    eax, eax
0x402813  jz      short loc_40283A
0x402815  cmp     [ebp+IsMember], ebx
0x402818  jz      short loc_40283A
0x40281a  lea     eax, [ebp+var_18]
0x40281d  mov     [ebp+var_18], 1000h
0x402824  push    eax
0x402825  push    ebx
0x402826  call    ds:__imp_?GetProcessIntegrityLevel@@YGJPAXPAK@Z; GetProcessIntegrityLevel(void *,ulong *)
0x40282c  test    eax, eax
0x40282e  jnz     short loc_40283A
0x402830  cmp     [ebp+var_18], 3000h
0x402837  sbb     esi, esi
0x402839  inc     esi
0x40283a  cmp     [ebp+pSid], ebx
0x40283d  jz      short loc_402848
0x40283f  push    [ebp+pSid]; pSid
0x402842  call    ds:__imp__FreeSid@4; FreeSid(x)
0x402848  mov     ecx, [ebp+var_4]
0x40284b  mov     eax, esi
0x40284d  pop     esi
0x40284e  xor     ecx, ebp; StackCookie
0x402850  pop     ebx
0x402851  call    @__security_check_cookie@4; __security_check_cookie(x)
0x402856  leave
0x402857  retn
```
