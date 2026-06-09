# ValidateSecurityDescriptor

- ea: `0x180003200`
- end: `0x18000350c`
- name: `ValidateSecurityDescriptor`
- size: `780`
- prototype: `__int64 __fastcall(int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002f80`

## callees

- `0x180003200`
- `0x180008ff0`
- `0x180009130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000348b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000348b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000326c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000326c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800032d0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800032d0`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000330d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000330d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180003335`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180003335`

## pseudocode

```c
__int64 __fastcall ValidateSecurityDescriptor(int a1, void *a2)
{
  unsigned int v3; // ebp
  PVOID *v5; // rcx
  DWORD i; // ebx
  LPVOID v8; // rdi
  int v9; // esi
  __int64 v10; // rdx
  DWORD LastError; // eax
  __int64 v12; // r9
  DWORD v13; // eax
  DWORD v14; // eax
  WINBOOL bOwnerDefaulted; // [rsp+20h] [rbp-48h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-40h] BYREF
  LPVOID pAce; // [rsp+30h] [rbp-38h] BYREF
  PSID pOwner; // [rsp+38h] [rbp-30h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+80h] [rbp+18h] BYREF
  WINBOOL bDaclPresent; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  pAce = 0;
  pOwner = 0;
  bOwnerDefaulted = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
  if ( !GetSecurityDescriptorDacl(a2, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError )
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v3;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_32;
      v10 = 38;
      v12 = LastError;
      goto LABEL_54;
    }
  }
  if ( !bDaclDefaulted && pDacl && bDaclPresent )
  {
    if ( !GetSecurityDescriptorOwner(a2, &pOwner, &bOwnerDefaulted) )
    {
      v13 = GetLastError();
      v3 = v13;
      if ( v13 )
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v3;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_32;
        v10 = 40;
        v12 = v13;
        goto LABEL_54;
      }
    }
    if ( pOwner )
    {
      for ( i = 0; i < pDacl->AceCount; ++i )
      {
        pAce = 0;
        if ( !GetAce(pDacl, i, &pAce) )
        {
          v14 = GetLastError();
          v3 = v14;
          if ( v14 )
          {
            v5 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return v3;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v10 = 42;
              v12 = v14;
              goto LABEL_54;
            }
            goto LABEL_32;
          }
        }
        if ( *(_BYTE *)pAce )
        {
          if ( *(_BYTE *)pAce != 1 )
          {
            v3 = 1336;
            v5 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return v3;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v10 = 43;
              goto LABEL_53;
            }
            goto LABEL_32;
          }
          v8 = 0;
        }
        else
        {
          v8 = pAce;
        }
        v9 = *((_DWORD *)pAce + 1);
        if ( !IsValidSid((char *)pAce + 8) )
        {
          v3 = 1337;
          v5 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return v3;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v10 = 44;
            goto LABEL_53;
          }
          goto LABEL_32;
        }
        if ( v8 && (~a1 & v9) != 0 )
        {
          v3 = 1336;
          v5 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return v3;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v10 = 45;
            goto LABEL_53;
          }
          goto LABEL_32;
        }
      }
      goto LABEL_31;
    }
    v3 = 1338;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_32;
    v10 = 41;
    goto LABEL_53;
  }
  v3 = 1338;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v10 = 39;
LABEL_53:
    v12 = v3;
LABEL_54:
    WPP_SF_L(v5[2], v10, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v12);
LABEL_31:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_32:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_L(v5[2], 46, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180003200  mov     rax, rsp
0x180003203  push    rbx
0x180003204  push    rbp
0x180003205  push    r12
0x180003207  push    r14
0x180003209  push    r15
0x18000320b  sub     rsp, 40h
0x18000320f  xor     r15d, r15d
0x180003212  mov     rbx, rdx
0x180003215  mov     ebp, r15d
0x180003218  mov     [rax+20h], r15d
0x18000321c  mov     [rax+18h], r15d
0x180003220  mov     r14d, ecx
0x180003223  mov     [rax-40h], r15
0x180003227  mov     [rax-38h], r15
0x18000322b  mov     [rax-30h], r15
0x18000322f  mov     [rax-48h], r15d
0x180003233  mov     rcx, cs:WPP_GLOBAL_Control
0x18000323a  lea     r12, WPP_GLOBAL_Control
0x180003241  cmp     rcx, r12
0x180003244  jnz     loc_18000340E
0x18000324a  mov     [rsp+68h+arg_0], rsi
0x18000324f  lea     r9, [rsp+68h+bDaclDefaulted]; lpbDaclDefaulted
0x180003257  lea     r8, [rsp+68h+pDacl]; pDacl
0x18000325c  mov     [rsp+68h+arg_8], rdi
0x180003261  lea     rdx, [rsp+68h+bDaclPresent]; lpbDaclPresent
0x180003269  mov     rcx, rbx; pSecurityDescriptor
0x18000326c  call    cs:__imp_GetSecurityDescriptorDacl
0x180003272  test    eax, eax
0x180003274  jz      loc_1800033A4
0x18000327a  cmp     [rsp+68h+bDaclDefaulted], r15d
0x180003282  jnz     short loc_18000328B
0x180003284  cmp     [rsp+68h+pDacl], r15
0x180003289  jnz     short loc_1800032B9
0x18000328b  mov     ebp, 53Ah
0x180003290  mov     rcx, cs:WPP_GLOBAL_Control
0x180003297  cmp     rcx, r12
0x18000329a  jnz     loc_1800034E5
0x1800032a0  mov     rdi, [rsp+68h+arg_8]
0x1800032a5  mov     eax, ebp
0x1800032a7  mov     rsi, [rsp+68h+arg_0]
0x1800032ac  add     rsp, 40h
0x1800032b0  pop     r15
0x1800032b2  pop     r14
0x1800032b4  pop     r12
0x1800032b6  pop     rbp
0x1800032b7  pop     rbx
0x1800032b8  retn
0x1800032b9  cmp     [rsp+68h+bDaclPresent], r15d
0x1800032c1  jz      short loc_18000328B
0x1800032c3  lea     r8, [rsp+68h+bOwnerDefaulted]; lpbOwnerDefaulted
0x1800032c8  mov     rcx, rbx; pSecurityDescriptor
0x1800032cb  lea     rdx, [rsp+68h+pOwner]; pOwner
0x1800032d0  call    cs:__imp_GetSecurityDescriptorOwner
0x1800032d6  test    eax, eax
0x1800032d8  jz      loc_180003432
0x1800032de  cmp     [rsp+68h+pOwner], r15
0x1800032e3  jz      loc_180003465
0x1800032e9  mov     ebx, r15d
0x1800032ec  nop     dword ptr [rax+00h]
0x1800032f0  mov     rcx, [rsp+68h+pDacl]; pAcl
0x1800032f5  movzx   eax, word ptr [rcx+4]
0x1800032f9  cmp     ebx, eax
0x1800032fb  jnb     loc_1800033D7
0x180003301  lea     r8, [rsp+68h+pAce]; pAce
0x180003306  mov     [rsp+68h+pAce], r15
0x18000330b  mov     edx, ebx; dwAceIndex
0x18000330d  call    cs:__imp_GetAce
0x180003313  test    eax, eax
0x180003315  jz      loc_18000348B
0x18000331b  mov     rcx, [rsp+68h+pAce]
0x180003320  movzx   eax, byte ptr [rcx]
0x180003323  test    al, al
0x180003325  jz      short loc_18000334C
0x180003327  cmp     al, 1
0x180003329  jnz     short loc_18000337F
0x18000332b  mov     rdi, r15
0x18000332e  mov     esi, [rcx+4]
0x180003331  add     rcx, 8; pSid
0x180003335  call    cs:__imp_IsValidSid
0x18000333b  test    eax, eax
0x18000333d  jz      loc_1800034BF
0x180003343  test    rdi, rdi
0x180003346  jnz     short loc_180003351
0x180003348  inc     ebx
0x18000334a  jmp     short loc_1800032F0
0x18000334c  mov     rdi, rcx
0x18000334f  jmp     short loc_18000332E
0x180003351  mov     eax, r14d
0x180003354  not     eax
0x180003356  test    esi, eax
0x180003358  jz      short loc_180003348
0x18000335a  mov     ebp, 538h
0x18000335f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003366  cmp     rcx, r12
0x180003369  jz      loc_1800032A0
0x18000336f  test    byte ptr [rcx+1Ch], 4
0x180003373  jz      short loc_1800033DE
0x180003375  mov     edx, 2Dh ; '-'
0x18000337a  jmp     loc_1800034F4
0x18000337f  mov     ebp, 538h
0x180003384  mov     rcx, cs:WPP_GLOBAL_Control
0x18000338b  cmp     rcx, r12
0x18000338e  jz      loc_1800032A0
0x180003394  test    byte ptr [rcx+1Ch], 4
0x180003398  jz      short loc_1800033DE
0x18000339a  mov     edx, 2Bh ; '+'
0x18000339f  jmp     loc_1800034F4
0x1800033a4  call    cs:__imp_GetLastError
0x1800033aa  mov     ebp, eax
0x1800033ac  test    eax, eax
0x1800033ae  jz      loc_18000327A
0x1800033b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033bb  cmp     rcx, r12
0x1800033be  jz      loc_1800032A0
0x1800033c4  test    byte ptr [rcx+1Ch], 4
0x1800033c8  jz      short loc_1800033DE
0x1800033ca  mov     edx, 26h ; '&'
0x1800033cf  mov     r9d, eax
0x1800033d2  jmp     loc_1800034F7
0x1800033d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033de  cmp     rcx, r12
0x1800033e1  jz      loc_1800032A0
0x1800033e7  test    byte ptr [rcx+1Ch], 8
0x1800033eb  jz      loc_1800032A0
0x1800033f1  mov     rcx, [rcx+10h]
0x1800033f5  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800033fc  mov     edx, 2Eh ; '.'
0x180003401  mov     r9d, ebp
0x180003404  call    WPP_SF_L
0x180003409  jmp     loc_1800032A0
0x18000340e  test    byte ptr [rcx+1Ch], 8
0x180003412  jz      loc_18000324A
0x180003418  mov     rcx, [rcx+10h]
0x18000341c  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180003423  mov     edx, 25h ; '%'
0x180003428  call    WPP_SF_
0x18000342d  jmp     loc_18000324A
0x180003432  call    cs:__imp_GetLastError
0x180003438  mov     ebp, eax
0x18000343a  test    eax, eax
0x18000343c  jz      loc_1800032DE
0x180003442  mov     rcx, cs:WPP_GLOBAL_Control
0x180003449  cmp     rcx, r12
0x18000344c  jz      loc_1800032A0
0x180003452  test    byte ptr [rcx+1Ch], 4
0x180003456  jz      short loc_1800033DE
0x180003458  mov     edx, 28h ; '('
0x18000345d  mov     r9d, eax
0x180003460  jmp     loc_1800034F7
0x180003465  mov     ebp, 53Ah
0x18000346a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003471  cmp     rcx, r12
0x180003474  jz      loc_1800032A0
0x18000347a  test    byte ptr [rcx+1Ch], 4
0x18000347e  jz      loc_1800033DE
0x180003484  mov     edx, 29h ; ')'
0x180003489  jmp     short loc_1800034F4
0x18000348b  call    cs:__imp_GetLastError
0x180003491  mov     ebp, eax
0x180003493  test    eax, eax
0x180003495  jz      loc_18000331B
0x18000349b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034a2  cmp     rcx, r12
0x1800034a5  jz      loc_1800032A0
0x1800034ab  test    byte ptr [rcx+1Ch], 4
0x1800034af  jz      loc_1800033DE
0x1800034b5  mov     edx, 2Ah ; '*'
0x1800034ba  mov     r9d, eax
0x1800034bd  jmp     short loc_1800034F7
0x1800034bf  mov     ebp, 539h
0x1800034c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034cb  cmp     rcx, r12
0x1800034ce  jz      loc_1800032A0
0x1800034d4  test    byte ptr [rcx+1Ch], 4
0x1800034d8  jz      loc_1800033DE
0x1800034de  mov     edx, 2Ch ; ','
0x1800034e3  jmp     short loc_1800034F4
0x1800034e5  test    byte ptr [rcx+1Ch], 4
0x1800034e9  jz      loc_1800033DE
0x1800034ef  mov     edx, 27h ; '''
0x1800034f4  mov     r9d, ebp
0x1800034f7  mov     rcx, [rcx+10h]
0x1800034fb  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180003502  call    WPP_SF_L
0x180003507  jmp     loc_1800033D7
```
