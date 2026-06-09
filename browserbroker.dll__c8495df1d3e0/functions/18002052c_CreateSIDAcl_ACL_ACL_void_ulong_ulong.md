# CreateSIDAcl(_ACL *,_ACL * *,void *,ulong,ulong)

- ea: `0x18002052c`
- end: `0x180020651`
- name: `?CreateSIDAcl@@YAKPEAU_ACL@@PEAPEAU1@PEAXKK@Z`
- size: `293`
- prototype: `__int64 __fastcall(PACL pAcl, struct _ACL **, void *, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020730`

## callees

- `0x18002052c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020617`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020573`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020573`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002062b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002062b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180020551`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180020551`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800205ae`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800205ae`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180020590`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180020590`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180020608`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180020608`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800205e4`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800205e4`

## pseudocode

```c
__int64 __fastcall CreateSIDAcl(PACL pAcl, struct _ACL **a2, void *a3, DWORD a4)
{
  DWORD LengthSid; // eax
  int AclSize; // ecx
  DWORD v10; // ebx
  struct _ACL *v11; // rax
  struct _ACL *v12; // rsi
  DWORD LastError; // ebx
  WORD i; // bp
  LPVOID pAce; // [rsp+60h] [rbp+8h] BYREF

  LengthSid = GetLengthSid(a3);
  if ( pAcl )
    AclSize = pAcl->AclSize;
  else
    AclSize = 8;
  v10 = AclSize + LengthSid + 12;
  v11 = (struct _ACL *)LocalAlloc(0, v10);
  v12 = v11;
  if ( !v11 )
    return 14;
  if ( InitializeAcl(v11, v10, 4u) && AddAccessAllowedAceEx(v12, 4u, 3u, a4, a3) )
  {
    LastError = 0;
    if ( pAcl && pAcl->AceCount )
    {
      for ( i = 0; i < pAcl->AceCount; ++i )
      {
        pAce = 0;
        if ( !GetAce(pAcl, i, &pAce) || !AddAce(v12, 4u, i + 1, pAce, *((unsigned __int16 *)pAce + 1)) )
          goto LABEL_14;
      }
    }
  }
  else
  {
LABEL_14:
    LastError = GetLastError();
    if ( LastError )
    {
      LocalFree(v12);
      return LastError;
    }
  }
  *a2 = v12;
  return LastError;
}

```

## disassembly

```asm
0x18002052c  mov     [rsp+arg_8], rbx
0x180020531  mov     [rsp+arg_10], rbp
0x180020536  push    rsi
0x180020537  push    rdi
0x180020538  push    r12
0x18002053a  push    r14
0x18002053c  push    r15
0x18002053e  sub     rsp, 30h
0x180020542  mov     rdi, rcx
0x180020545  mov     r14d, r9d
0x180020548  mov     rcx, r8; pSid
0x18002054b  mov     rbp, r8
0x18002054e  mov     r15, rdx
0x180020551  call    cs:__imp_GetLengthSid
0x180020557  xor     r12d, r12d
0x18002055a  test    rdi, rdi
0x18002055d  jz      short loc_180020565
0x18002055f  movzx   ecx, word ptr [rdi+2]
0x180020563  jmp     short loc_18002056A
0x180020565  mov     ecx, 8
0x18002056a  lea     ebx, [rax+0Ch]
0x18002056d  add     ebx, ecx
0x18002056f  xor     ecx, ecx; uFlags
0x180020571  mov     edx, ebx; uBytes
0x180020573  call    cs:__imp_LocalAlloc
0x180020579  mov     rsi, rax
0x18002057c  test    rax, rax
0x18002057f  jz      loc_180020633
0x180020585  mov     r8d, 4; dwAclRevision
0x18002058b  mov     edx, ebx; nAclLength
0x18002058d  mov     rcx, rax; pAcl
0x180020590  call    cs:__imp_InitializeAcl
0x180020596  test    eax, eax
0x180020598  jz      short loc_180020617
0x18002059a  mov     edx, 4; dwAceRevision
0x18002059f  mov     [rsp+58h+pSid], rbp; pSid
0x1800205a4  mov     r9d, r14d; AccessMask
0x1800205a7  mov     rcx, rsi; pAcl
0x1800205aa  lea     r8d, [rdx-1]; AceFlags
0x1800205ae  call    cs:__imp_AddAccessAllowedAceEx
0x1800205b4  test    eax, eax
0x1800205b6  jz      short loc_180020617
0x1800205b8  mov     ebx, r12d
0x1800205bb  test    rdi, rdi
0x1800205be  jz      short loc_180020623
0x1800205c0  cmp     [rdi+4], r12w
0x1800205c5  jz      short loc_180020623
0x1800205c7  mov     ebp, r12d
0x1800205ca  cmp     bp, [rdi+4]
0x1800205ce  jnb     short loc_180020623
0x1800205d0  movzx   r14d, bp
0x1800205d4  lea     r8, [rsp+58h+pAce]; pAce
0x1800205d9  mov     edx, r14d; dwAceIndex
0x1800205dc  mov     [rsp+58h+pAce], r12
0x1800205e1  mov     rcx, rdi; pAcl
0x1800205e4  call    cs:__imp_GetAce
0x1800205ea  test    eax, eax
0x1800205ec  jz      short loc_180020617
0x1800205ee  mov     r9, [rsp+58h+pAce]; pAceList
0x1800205f3  lea     r8d, [r14+1]; dwStartingAceIndex
0x1800205f7  mov     edx, 4; dwAceRevision
0x1800205fc  mov     rcx, rsi; pAcl
0x1800205ff  movzx   eax, word ptr [r9+2]
0x180020604  mov     dword ptr [rsp+58h+pSid], eax; nAceListLength
0x180020608  call    cs:__imp_AddAce
0x18002060e  test    eax, eax
0x180020610  jz      short loc_180020617
0x180020612  inc     bp
0x180020615  jmp     short loc_1800205CA
0x180020617  call    cs:__imp_GetLastError
0x18002061d  mov     ebx, eax
0x18002061f  test    eax, eax
0x180020621  jnz     short loc_180020628
0x180020623  mov     [r15], rsi
0x180020626  jmp     short loc_180020638
0x180020628  mov     rcx, rsi; hMem
0x18002062b  call    cs:__imp_LocalFree
0x180020631  jmp     short loc_180020638
0x180020633  mov     ebx, 0Eh
0x180020638  mov     rbp, [rsp+58h+arg_10]
0x18002063d  mov     eax, ebx
0x18002063f  mov     rbx, [rsp+58h+arg_8]
0x180020644  add     rsp, 30h
0x180020648  pop     r15
0x18002064a  pop     r14
0x18002064c  pop     r12
0x18002064e  pop     rdi
0x18002064f  pop     rsi
0x180020650  retn
```
