# InitializeEveryoneSecurityDescriptor(ulong,void *,_ACL * *,void * *)

- ea: `0x14000266c`
- end: `0x1400027f4`
- name: `?InitializeEveryoneSecurityDescriptor@@YAKKPEAXPEAPEAU_ACL@@PEAPEAX@Z`
- size: `392`
- prototype: `__int64 __fastcall(__int64, void *, struct _ACL **, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400020b8`

## callees

- `0x14000266c`
- `0x14001edc0`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x1400026da`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400026da`
- `ADVAPI32!GetLengthSid` at `0x140002730`
- `ADVAPI32!GetLengthSid` at `0x140002730`
- `ADVAPI32!InitializeAcl` at `0x140002759`
- `ADVAPI32!InitializeAcl` at `0x140002759`
- `ADVAPI32!AddAccessAllowedAce` at `0x140002773`
- `ADVAPI32!AddAccessAllowedAce` at `0x140002773`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140002789`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140002789`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1400027a4`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1400027a4`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1400027bc`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1400027bc`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1400027d4`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1400027d4`
- `ADVAPI32!FreeSid` at `0x1400026f8`
- `ADVAPI32!FreeSid` at `0x1400026f8`
- `KERNEL32!GetLastError` at `0x1400026e7`
- `KERNEL32!GetLastError` at `0x1400026e7`
- `msvcrt!free` at `0x140002706`
- `msvcrt!free` at `0x140002706`
- `msvcrt!malloc` at `0x14000273b`
- `msvcrt!malloc` at `0x14000273b`

## pseudocode

```c
__int64 __fastcall InitializeEveryoneSecurityDescriptor(__int64 a1, void *a2, struct _ACL **a3, void **a4)
{
  struct _ACL *v7; // rbx
  DWORD LastError; // edi
  DWORD v10; // esi
  struct _ACL *v11; // rax
  PSID pSid; // [rsp+60h] [rbp-20h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-18h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v10 = GetLengthSid(pSid) + 16;
    v11 = (struct _ACL *)malloc(v10);
    v7 = v11;
    if ( !v11 )
    {
      LastError = 8;
      goto LABEL_4;
    }
    if ( InitializeAcl(v11, v10, 2u)
      && AddAccessAllowedAce(v7, 2u, 3u, pSid)
      && InitializeSecurityDescriptor(a2, 1u)
      && SetSecurityDescriptorDacl(a2, 1, v7, 0)
      && SetSecurityDescriptorOwner(a2, pSid, 0)
      && SetSecurityDescriptorGroup(a2, pSid, 0) )
    {
      LastError = 0;
      *a4 = pSid;
      *a3 = v7;
      return LastError;
    }
  }
  else
  {
    v7 = 0;
  }
  LastError = GetLastError();
LABEL_4:
  if ( pSid )
    FreeSid(pSid);
  if ( v7 )
    free(v7);
  return LastError;
}

```

## disassembly

```asm
0x14000266c  mov     r11, rsp
0x14000266f  push    rbp
0x140002670  push    rbx
0x140002671  push    rsi
0x140002672  push    rdi
0x140002673  push    r12
0x140002675  push    r14
0x140002677  push    r15
0x140002679  mov     rbp, rsp
0x14000267c  sub     rsp, 80h
0x140002683  mov     rax, cs:__security_cookie
0x14000268a  xor     rax, rsp
0x14000268d  mov     [rbp+var_10], rax
0x140002691  xor     r12d, r12d
0x140002694  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 100h
0x14000269a  lea     rax, [rbp+pSid]
0x14000269e  mov     dword ptr [rbp+pIdentifierAuthority.Value], r12d
0x1400026a2  mov     [r11-68h], rax
0x1400026a6  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1400026aa  mov     [r11-70h], r12d
0x1400026ae  mov     r15, r9
0x1400026b1  mov     [r11-78h], r12d
0x1400026b5  mov     r14, r8
0x1400026b8  mov     [r11-80h], r12d
0x1400026bc  mov     rdi, rdx
0x1400026bf  mov     [rsp+80h+nSubAuthority4], r12d; nSubAuthority4
0x1400026c4  xor     r9d, r9d; nSubAuthority1
0x1400026c7  mov     [rsp+80h+nSubAuthority3], r12d; nSubAuthority3
0x1400026cc  xor     r8d, r8d; nSubAuthority0
0x1400026cf  mov     dl, 1; nSubAuthorityCount
0x1400026d1  mov     [rsp+80h+nSubAuthority2], r12d; nSubAuthority2
0x1400026d6  mov     [rbp+pSid], r12
0x1400026da  call    cs:__imp_AllocateAndInitializeSid
0x1400026e0  test    eax, eax
0x1400026e2  jnz     short loc_14000272C
0x1400026e4  mov     ebx, r12d
0x1400026e7  call    cs:__imp_GetLastError
0x1400026ed  mov     edi, eax
0x1400026ef  mov     rcx, [rbp+pSid]; pSid
0x1400026f3  test    rcx, rcx
0x1400026f6  jz      short loc_1400026FE
0x1400026f8  call    cs:__imp_FreeSid
0x1400026fe  test    rbx, rbx
0x140002701  jz      short loc_14000270C
0x140002703  mov     rcx, rbx; Block
0x140002706  call    cs:__imp_free
0x14000270c  mov     eax, edi
0x14000270e  mov     rcx, [rbp+var_10]
0x140002712  xor     rcx, rsp; StackCookie
0x140002715  call    __security_check_cookie
0x14000271a  add     rsp, 80h
0x140002721  pop     r15
0x140002723  pop     r14
0x140002725  pop     r12
0x140002727  pop     rdi
0x140002728  pop     rsi
0x140002729  pop     rbx
0x14000272a  pop     rbp
0x14000272b  retn
0x14000272c  mov     rcx, [rbp+pSid]; pSid
0x140002730  call    cs:__imp_GetLengthSid
0x140002736  lea     esi, [rax+10h]
0x140002739  mov     ecx, esi; Size
0x14000273b  call    cs:__imp_malloc
0x140002741  mov     rbx, rax
0x140002744  test    rax, rax
0x140002747  jnz     short loc_14000274E
0x140002749  lea     edi, [rax+8]
0x14000274c  jmp     short loc_1400026EF
0x14000274e  mov     r8d, 2; dwAclRevision
0x140002754  mov     edx, esi; nAclLength
0x140002756  mov     rcx, rbx; pAcl
0x140002759  call    cs:__imp_InitializeAcl
0x14000275f  test    eax, eax
0x140002761  jz      short loc_1400026E7
0x140002763  mov     r9, [rbp+pSid]; pSid
0x140002767  mov     edx, 2; dwAceRevision
0x14000276c  mov     rcx, rbx; pAcl
0x14000276f  lea     r8d, [rdx+1]; AccessMask
0x140002773  call    cs:__imp_AddAccessAllowedAce
0x140002779  test    eax, eax
0x14000277b  jz      loc_1400026E7
0x140002781  mov     edx, 1; dwRevision
0x140002786  mov     rcx, rdi; pSecurityDescriptor
0x140002789  call    cs:__imp_InitializeSecurityDescriptor
0x14000278f  test    eax, eax
0x140002791  jz      loc_1400026E7
0x140002797  xor     r9d, r9d; bDaclDefaulted
0x14000279a  mov     r8, rbx; pDacl
0x14000279d  mov     rcx, rdi; pSecurityDescriptor
0x1400027a0  lea     edx, [r9+1]; bDaclPresent
0x1400027a4  call    cs:__imp_SetSecurityDescriptorDacl
0x1400027aa  test    eax, eax
0x1400027ac  jz      loc_1400026E7
0x1400027b2  mov     rdx, [rbp+pSid]; pOwner
0x1400027b6  xor     r8d, r8d; bOwnerDefaulted
0x1400027b9  mov     rcx, rdi; pSecurityDescriptor
0x1400027bc  call    cs:__imp_SetSecurityDescriptorOwner
0x1400027c2  test    eax, eax
0x1400027c4  jz      loc_1400026E7
0x1400027ca  mov     rdx, [rbp+pSid]; pGroup
0x1400027ce  xor     r8d, r8d; bGroupDefaulted
0x1400027d1  mov     rcx, rdi; pSecurityDescriptor
0x1400027d4  call    cs:__imp_SetSecurityDescriptorGroup
0x1400027da  test    eax, eax
0x1400027dc  jz      loc_1400026E7
0x1400027e2  mov     rax, [rbp+pSid]
0x1400027e6  mov     edi, r12d
0x1400027e9  mov     [r15], rax
0x1400027ec  mov     [r14], rbx
0x1400027ef  jmp     loc_14000270C
```
