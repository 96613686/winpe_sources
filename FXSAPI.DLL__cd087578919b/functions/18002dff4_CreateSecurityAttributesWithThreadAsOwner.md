# CreateSecurityAttributesWithThreadAsOwner

- ea: `0x18002dff4`
- end: `0x18002e5a6`
- name: `CreateSecurityAttributesWithThreadAsOwner`
- size: `1458`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d9ac`
- `0x180036f80`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002bab8`
- `0x18002bb58`
- `0x18002dff4`
- `0x18002ed50`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18002e571`
- `KERNEL32!LocalFree` at `0x18002e571`
- `KERNEL32!SetLastError` at `0x18002e46b`
- `KERNEL32!SetLastError` at `0x18002e46b`
- `KERNEL32!GetLastError` at `0x18002e176`
- `KERNEL32!GetLastError` at `0x18002e1c4`
- `KERNEL32!GetLastError` at `0x18002e21c`
- `KERNEL32!GetLastError` at `0x18002e276`
- `KERNEL32!GetLastError` at `0x18002e305`
- `KERNEL32!GetLastError` at `0x18002e394`
- `KERNEL32!GetLastError` at `0x18002e4f4`
- `KERNEL32!GetLastError` at `0x18002e176`
- `KERNEL32!GetLastError` at `0x18002e1c4`
- `KERNEL32!GetLastError` at `0x18002e21c`
- `KERNEL32!GetLastError` at `0x18002e276`
- `KERNEL32!GetLastError` at `0x18002e305`
- `KERNEL32!GetLastError` at `0x18002e394`
- `KERNEL32!GetLastError` at `0x18002e4f4`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002e4c1`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002e4c1`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18002e1e1`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18002e1e1`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002e2ca`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002e359`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002e2ca`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002e359`
- `ADVAPI32!SetEntriesInAclW` at `0x18002e420`
- `ADVAPI32!SetEntriesInAclW` at `0x18002e420`
- `ADVAPI32!FreeSid` at `0x18002e486`
- `ADVAPI32!FreeSid` at `0x18002e4a1`
- `ADVAPI32!FreeSid` at `0x18002e541`
- `ADVAPI32!FreeSid` at `0x18002e557`
- `ADVAPI32!FreeSid` at `0x18002e486`
- `ADVAPI32!FreeSid` at `0x18002e4a1`
- `ADVAPI32!FreeSid` at `0x18002e541`
- `ADVAPI32!FreeSid` at `0x18002e557`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002e13b`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002e13b`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18002e23b`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18002e23b`

## pseudocode

```c
_DWORD *__fastcall CreateSecurityAttributesWithThreadAsOwner(DWORD a1, DWORD a2, int a3)
{
  _DWORD *v6; // r12
  void *v8; // rsi
  void *v9; // rax
  void *v10; // r14
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  DWORD LastError; // eax
  void *CurrentThreadSID; // rax
  __int64 v16; // rdx
  PSID v17; // rax
  __int64 v18; // rcx
  DWORD v19; // eax
  DWORD v20; // ebx
  PSID v21; // [rsp+60h] [rbp-A0h] BYREF
  PSID pSid; // [rsp+68h] [rbp-98h] BYREF
  PACL NewAcl; // [rsp+70h] [rbp-90h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp-88h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-80h] BYREF
  int v26; // [rsp+B0h] [rbp-50h]
  __int64 v27; // [rsp+B4h] [rbp-4Ch]
  int v28; // [rsp+CCh] [rbp-34h]
  int v29; // [rsp+D0h] [rbp-30h]
  PSID v30; // [rsp+D8h] [rbp-28h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  v21 = 0;
  pSid = 0;
  NewAcl = 0;
  pListOfExplicitEntries.grfAccessPermissions = 0;
  memset_0(&pListOfExplicitEntries.grfAccessMode, 0, 0x8Cu);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v6 = (_DWORD *)pMemAlloc(0x18u);
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_db036311db36307996a98c23702218b2_Traceguids, 24);
    }
    return 0;
  }
  v8 = 0;
  v9 = (void *)pMemAlloc(0x28u);
  v10 = v9;
  if ( !v9 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    v12 = 58;
    v13 = 40;
LABEL_68:
    WPP_SF_d(v11[2], v12, WPP_db036311db36307996a98c23702218b2_Traceguids, v13);
LABEL_69:
    pMemFree(v6);
    pMemFree(v10);
    pMemFree(v8);
    if ( v21 )
      FreeSid(v21);
    if ( pSid )
      FreeSid(pSid);
    if ( NewAcl )
      LocalFree(NewAcl);
    return 0;
  }
  *v6 = 24;
  v6[4] = 1;
  *((_QWORD *)v6 + 1) = v9;
  if ( !InitializeSecurityDescriptor(v9, 1u) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    LastError = GetLastError();
    v12 = 59;
    goto LABEL_67;
  }
  CurrentThreadSID = (void *)GetCurrentThreadSID();
  v8 = CurrentThreadSID;
  if ( !CurrentThreadSID )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    LastError = GetLastError();
    v12 = 60;
    goto LABEL_67;
  }
  if ( !SetSecurityDescriptorOwner(v10, CurrentThreadSID, 0) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    LastError = GetLastError();
    v12 = 61;
    goto LABEL_67;
  }
  if ( !SetSecurityDescriptorGroup(v10, v8, 0) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    LastError = GetLastError();
    v12 = 62;
    goto LABEL_67;
  }
  if ( a3 && !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    LastError = GetLastError();
    v12 = 63;
    goto LABEL_67;
  }
  if ( a2 && !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &v21) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    LastError = GetLastError();
    v12 = 64;
    goto LABEL_67;
  }
  pListOfExplicitEntries.grfAccessPermissions = a1;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  LODWORD(v16) = 0;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v8;
  if ( a3 )
  {
    LODWORD(v16) = 1;
    v30 = pSid;
    v26 = a3;
    v27 = 2;
    v28 = 0;
    v29 = 2;
  }
  if ( a2 )
  {
    v17 = v21;
    v16 = (unsigned int)(v16 + 1);
    v18 = 6 * v16;
    *(&pListOfExplicitEntries.grfAccessPermissions + 2 * v18) = a2;
    *((_QWORD *)&pListOfExplicitEntries.grfAccessMode + v18) = 2;
    *((_DWORD *)&pListOfExplicitEntries.Trustee.TrusteeForm + 2 * v18) = 0;
    *((_DWORD *)&pListOfExplicitEntries.Trustee.TrusteeType + 2 * v18) = 2;
    *((_QWORD *)&pListOfExplicitEntries.Trustee.ptstrName + v18) = v17;
  }
  v19 = SetEntriesInAclW(v16 + 1, &pListOfExplicitEntries, 0, &NewAcl);
  v20 = v19;
  if ( v19 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_db036311db36307996a98c23702218b2_Traceguids, v19);
    }
    SetLastError(v20);
    goto LABEL_69;
  }
  if ( v21 )
  {
    FreeSid(v21);
    v21 = 0;
  }
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( !SetSecurityDescriptorDacl(v10, 1, NewAcl, 0) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    LastError = GetLastError();
    v12 = 66;
LABEL_67:
    v11 = WPP_GLOBAL_Control;
    v13 = LastError;
    goto LABEL_68;
  }
  return v6;
}

```

## disassembly

```asm
0x18002dff4  push    rbp
0x18002dff6  push    rbx
0x18002dff7  push    rsi
0x18002dff8  push    rdi
0x18002dff9  push    r12
0x18002dffb  push    r13
0x18002dffd  push    r14
0x18002dfff  push    r15
0x18002e001  lea     rbp, [rsp-28h]
0x18002e006  sub     rsp, 128h
0x18002e00d  mov     rax, cs:__security_cookie
0x18002e014  xor     rax, rsp
0x18002e017  mov     [rbp+60h+var_50], rax
0x18002e01b  mov     ebx, r8d
0x18002e01e  mov     edi, edx
0x18002e020  mov     r15d, ecx
0x18002e023  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e02a  lea     rsi, WPP_GLOBAL_Control
0x18002e031  cmp     rcx, rsi
0x18002e034  jz      short loc_18002E057
0x18002e036  test    byte ptr [rcx+1Ch], 2
0x18002e03a  jz      short loc_18002E057
0x18002e03c  cmp     byte ptr [rcx+19h], 5
0x18002e040  jb      short loc_18002E057
0x18002e042  mov     rcx, [rcx+10h]
0x18002e046  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002e04d  mov     edx, 38h ; '8'
0x18002e052  call    WPP_SF_
0x18002e057  xor     r13d, r13d
0x18002e05a  lea     rcx, [rbp+60h+pListOfExplicitEntries.grfAccessMode]; void *
0x18002e05e  xor     edx, edx; Val
0x18002e060  mov     [rsp+160h+var_100], r13
0x18002e065  mov     r8d, 8Ch; Size
0x18002e06b  mov     [rsp+160h+var_F8], r13
0x18002e070  mov     [rsp+160h+NewAcl], r13
0x18002e075  mov     [rbp+60h+pListOfExplicitEntries.grfAccessPermissions], r13d
0x18002e079  call    memset_0
0x18002e07e  lea     r14d, [r13+18h]
0x18002e082  mov     dword ptr [rsp+160h+pIdentifierAuthority.Value], r13d
0x18002e087  mov     ecx, r14d; dwBytes
0x18002e08a  mov     word ptr [rsp+160h+pIdentifierAuthority.Value+4], 500h
0x18002e091  call    pMemAlloc
0x18002e096  mov     r12, rax
0x18002e099  test    rax, rax
0x18002e09c  jnz     short loc_18002E0D3
0x18002e09e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e0a5  cmp     rcx, rsi
0x18002e0a8  jz      short loc_18002E0CC
0x18002e0aa  test    byte ptr [rcx+1Ch], 2
0x18002e0ae  jz      short loc_18002E0CC
0x18002e0b0  cmp     byte ptr [rcx+19h], 2
0x18002e0b4  jb      short loc_18002E0CC
0x18002e0b6  mov     rcx, [rcx+10h]
0x18002e0ba  lea     edx, [rax+39h]
0x18002e0bd  mov     r9d, r14d
0x18002e0c0  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002e0c7  call    WPP_SF_d
0x18002e0cc  xor     eax, eax
0x18002e0ce  jmp     loc_18002E585
0x18002e0d3  mov     ecx, 28h ; '('; dwBytes
0x18002e0d8  mov     rsi, r13
0x18002e0db  call    pMemAlloc
0x18002e0e0  mov     r14, rax
0x18002e0e3  test    rax, rax
0x18002e0e6  jnz     short loc_18002E11F
0x18002e0e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e0ef  lea     rdx, WPP_GLOBAL_Control
0x18002e0f6  cmp     rcx, rdx
0x18002e0f9  jz      loc_18002E51F
0x18002e0ff  test    byte ptr [rcx+1Ch], 2
0x18002e103  jz      loc_18002E51F
0x18002e109  cmp     byte ptr [rcx+19h], 2
0x18002e10d  jb      loc_18002E51F
0x18002e113  lea     edx, [rax+3Ah]
0x18002e116  lea     r9d, [rax+28h]
0x18002e11a  jmp     loc_18002E50F
0x18002e11f  mov     eax, 1
0x18002e124  mov     dword ptr [r12], 18h
0x18002e12c  mov     edx, eax; dwRevision
0x18002e12e  mov     [r12+10h], eax
0x18002e133  mov     rcx, r14; pSecurityDescriptor
0x18002e136  mov     [r12+8], r14
0x18002e13b  call    cs:__imp_InitializeSecurityDescriptor
0x18002e142  nop     dword ptr [rax+rax+00h]
0x18002e147  test    eax, eax
0x18002e149  jnz     short loc_18002E18C
0x18002e14b  mov     rax, cs:WPP_GLOBAL_Control
0x18002e152  lea     rdx, WPP_GLOBAL_Control
0x18002e159  cmp     rax, rdx
0x18002e15c  jz      loc_18002E51F
0x18002e162  test    byte ptr [rax+1Ch], 2
0x18002e166  jz      loc_18002E51F
0x18002e16c  cmp     byte ptr [rax+19h], 2
0x18002e170  jb      loc_18002E51F
0x18002e176  call    cs:__imp_GetLastError
0x18002e17d  nop     dword ptr [rax+rax+00h]
0x18002e182  mov     edx, 3Bh ; ';'
0x18002e187  jmp     loc_18002E505
0x18002e18c  call    GetCurrentThreadSID
0x18002e191  mov     rsi, rax
0x18002e194  test    rax, rax
0x18002e197  jnz     short loc_18002E1D8
0x18002e199  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e1a0  lea     rdx, WPP_GLOBAL_Control
0x18002e1a7  cmp     rcx, rdx
0x18002e1aa  jz      loc_18002E51F
0x18002e1b0  test    byte ptr [rcx+1Ch], 2
0x18002e1b4  jz      loc_18002E51F
0x18002e1ba  cmp     byte ptr [rcx+19h], 2
0x18002e1be  jb      loc_18002E51F
0x18002e1c4  call    cs:__imp_GetLastError
0x18002e1cb  nop     dword ptr [rax+rax+00h]
0x18002e1d0  lea     edx, [rsi+3Ch]
0x18002e1d3  jmp     loc_18002E505
0x18002e1d8  xor     r8d, r8d; bOwnerDefaulted
0x18002e1db  mov     rdx, rsi; pOwner
0x18002e1de  mov     rcx, r14; pSecurityDescriptor
0x18002e1e1  call    cs:__imp_SetSecurityDescriptorOwner
0x18002e1e8  nop     dword ptr [rax+rax+00h]
0x18002e1ed  test    eax, eax
0x18002e1ef  jnz     short loc_18002E232
0x18002e1f1  mov     rax, cs:WPP_GLOBAL_Control
0x18002e1f8  lea     rdx, WPP_GLOBAL_Control
0x18002e1ff  cmp     rax, rdx
0x18002e202  jz      loc_18002E51F
0x18002e208  test    byte ptr [rax+1Ch], 2
0x18002e20c  jz      loc_18002E51F
0x18002e212  cmp     byte ptr [rax+19h], 2
0x18002e216  jb      loc_18002E51F
0x18002e21c  call    cs:__imp_GetLastError
0x18002e223  nop     dword ptr [rax+rax+00h]
0x18002e228  mov     edx, 3Dh ; '='
0x18002e22d  jmp     loc_18002E505
0x18002e232  xor     r8d, r8d; bGroupDefaulted
0x18002e235  mov     rdx, rsi; pGroup
0x18002e238  mov     rcx, r14; pSecurityDescriptor
0x18002e23b  call    cs:__imp_SetSecurityDescriptorGroup
0x18002e242  nop     dword ptr [rax+rax+00h]
0x18002e247  test    eax, eax
0x18002e249  jnz     short loc_18002E28C
0x18002e24b  mov     rax, cs:WPP_GLOBAL_Control
0x18002e252  lea     rdx, WPP_GLOBAL_Control
0x18002e259  cmp     rax, rdx
0x18002e25c  jz      loc_18002E51F
0x18002e262  test    byte ptr [rax+1Ch], 2
0x18002e266  jz      loc_18002E51F
0x18002e26c  cmp     byte ptr [rax+19h], 2
0x18002e270  jb      loc_18002E51F
0x18002e276  call    cs:__imp_GetLastError
0x18002e27d  nop     dword ptr [rax+rax+00h]
0x18002e282  mov     edx, 3Eh ; '>'
0x18002e287  jmp     loc_18002E505
0x18002e28c  test    ebx, ebx
0x18002e28e  jz      loc_18002E31B
0x18002e294  lea     rax, [rsp+160h+var_F8]
0x18002e299  xor     r9d, r9d; nSubAuthority1
0x18002e29c  mov     [rsp+160h+pSid], rax; pSid
0x18002e2a1  lea     rcx, [rsp+160h+pIdentifierAuthority]; pIdentifierAuthority
0x18002e2a6  mov     [rsp+160h+nSubAuthority7], r13d; nSubAuthority7
0x18002e2ab  mov     dl, 1; nSubAuthorityCount
0x18002e2ad  mov     [rsp+160h+nSubAuthority6], r13d; nSubAuthority6
0x18002e2b2  mov     [rsp+160h+nSubAuthority5], r13d; nSubAuthority5
0x18002e2b7  lea     r8d, [r9+14h]; nSubAuthority0
0x18002e2bb  mov     [rsp+160h+nSubAuthority4], r13d; nSubAuthority4
0x18002e2c0  mov     [rsp+160h+nSubAuthority3], r13d; nSubAuthority3
0x18002e2c5  mov     [rsp+160h+nSubAuthority2], r13d; nSubAuthority2
0x18002e2ca  call    cs:__imp_AllocateAndInitializeSid
0x18002e2d1  nop     dword ptr [rax+rax+00h]
0x18002e2d6  test    eax, eax
0x18002e2d8  jnz     short loc_18002E31B
0x18002e2da  mov     rax, cs:WPP_GLOBAL_Control
0x18002e2e1  lea     rdx, WPP_GLOBAL_Control
0x18002e2e8  cmp     rax, rdx
0x18002e2eb  jz      loc_18002E51F
0x18002e2f1  test    byte ptr [rax+1Ch], 2
0x18002e2f5  jz      loc_18002E51F
0x18002e2fb  cmp     byte ptr [rax+19h], 2
0x18002e2ff  jb      loc_18002E51F
0x18002e305  call    cs:__imp_GetLastError
0x18002e30c  nop     dword ptr [rax+rax+00h]
0x18002e311  mov     edx, 3Fh ; '?'
0x18002e316  jmp     loc_18002E505
0x18002e31b  test    edi, edi
0x18002e31d  jz      loc_18002E3AA
0x18002e323  lea     rax, [rsp+160h+var_100]
0x18002e328  xor     r9d, r9d; nSubAuthority1
0x18002e32b  mov     [rsp+160h+pSid], rax; pSid
0x18002e330  lea     rcx, [rsp+160h+pIdentifierAuthority]; pIdentifierAuthority
0x18002e335  mov     [rsp+160h+nSubAuthority7], r13d; nSubAuthority7
0x18002e33a  mov     dl, 1; nSubAuthorityCount
0x18002e33c  mov     [rsp+160h+nSubAuthority6], r13d; nSubAuthority6
0x18002e341  mov     [rsp+160h+nSubAuthority5], r13d; nSubAuthority5
0x18002e346  lea     r8d, [r9+0Bh]; nSubAuthority0
0x18002e34a  mov     [rsp+160h+nSubAuthority4], r13d; nSubAuthority4
0x18002e34f  mov     [rsp+160h+nSubAuthority3], r13d; nSubAuthority3
0x18002e354  mov     [rsp+160h+nSubAuthority2], r13d; nSubAuthority2
0x18002e359  call    cs:__imp_AllocateAndInitializeSid
0x18002e360  nop     dword ptr [rax+rax+00h]
0x18002e365  test    eax, eax
0x18002e367  jnz     short loc_18002E3AA
0x18002e369  mov     rax, cs:WPP_GLOBAL_Control
0x18002e370  lea     rdx, WPP_GLOBAL_Control
0x18002e377  cmp     rax, rdx
0x18002e37a  jz      loc_18002E51F
0x18002e380  test    byte ptr [rax+1Ch], 2
0x18002e384  jz      loc_18002E51F
0x18002e38a  cmp     byte ptr [rax+19h], 2
0x18002e38e  jb      loc_18002E51F
0x18002e394  call    cs:__imp_GetLastError
0x18002e39b  nop     dword ptr [rax+rax+00h]
0x18002e3a0  mov     edx, 40h ; '@'
0x18002e3a5  jmp     loc_18002E505
0x18002e3aa  mov     [rbp+60h+pListOfExplicitEntries.grfAccessPermissions], r15d
0x18002e3ae  mov     r15d, 2
0x18002e3b4  mov     qword ptr [rbp+60h+pListOfExplicitEntries.grfAccessMode], r15
0x18002e3b8  mov     edx, r13d
0x18002e3bb  mov     [rbp+60h+pListOfExplicitEntries.Trustee.TrusteeType], r15d
0x18002e3bf  mov     [rbp+60h+pListOfExplicitEntries.Trustee.TrusteeForm], r13d
0x18002e3c3  mov     [rbp+60h+pListOfExplicitEntries.Trustee.ptstrName], rsi
0x18002e3c7  test    ebx, ebx
0x18002e3c9  jz      short loc_18002E3E7
0x18002e3cb  mov     rax, [rsp+160h+var_F8]
0x18002e3d0  lea     edx, [r15-1]
0x18002e3d4  mov     [rbp+60h+var_88], rax
0x18002e3d8  mov     [rbp+60h+var_B0], ebx
0x18002e3db  mov     [rbp+60h+var_AC], r15
0x18002e3df  mov     [rbp+60h+var_94], r13d
0x18002e3e3  mov     [rbp+60h+var_90], r15d
0x18002e3e7  test    edi, edi
0x18002e3e9  jz      short loc_18002E411
0x18002e3eb  mov     rax, [rsp+160h+var_100]
0x18002e3f0  inc     edx
0x18002e3f2  lea     rcx, [rdx+rdx*2]
0x18002e3f6  add     rcx, rcx
0x18002e3f9  mov     [rbp+rcx*8+60h+pListOfExplicitEntries.grfAccessPermissions], edi
0x18002e3fd  mov     qword ptr [rbp+rcx*8+60h+pListOfExplicitEntries.grfAccessMode], r15
0x18002e402  mov     [rbp+rcx*8+60h+pListOfExplicitEntries.Trustee.TrusteeForm], r13d
0x18002e407  mov     [rbp+rcx*8+60h+pListOfExplicitEntries.Trustee.TrusteeType], r15d
0x18002e40c  mov     [rbp+rcx*8+60h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18002e411  lea     ecx, [rdx+1]; cCountOfExplicitEntries
0x18002e414  xor     r8d, r8d; OldAcl
0x18002e417  lea     rdx, [rbp+60h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18002e41b  lea     r9, [rsp+160h+NewAcl]; NewAcl
0x18002e420  call    cs:__imp_SetEntriesInAclW
0x18002e427  nop     dword ptr [rax+rax+00h]
0x18002e42c  mov     ebx, eax
0x18002e42e  test    eax, eax
0x18002e430  jz      short loc_18002E47C
0x18002e432  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e439  lea     rdx, WPP_GLOBAL_Control
0x18002e440  cmp     rcx, rdx
0x18002e443  jz      short loc_18002E469
0x18002e445  test    [rcx+1Ch], r15b
0x18002e449  jz      short loc_18002E469
0x18002e44b  cmp     [rcx+19h], r15b
0x18002e44f  jb      short loc_18002E469
0x18002e451  mov     rcx, [rcx+10h]
0x18002e455  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002e45c  mov     edx, 41h ; 'A'
0x18002e461  mov     r9d, eax
0x18002e464  call    WPP_SF_d
0x18002e469  mov     ecx, ebx; dwErrCode
0x18002e46b  call    cs:__imp_SetLastError
0x18002e472  nop     dword ptr [rax+rax+00h]
0x18002e477  jmp     loc_18002E51F
0x18002e47c  mov     rcx, [rsp+160h+var_100]; pSid
0x18002e481  test    rcx, rcx
0x18002e484  jz      short loc_18002E497
0x18002e486  call    cs:__imp_FreeSid
0x18002e48d  nop     dword ptr [rax+rax+00h]
0x18002e492  mov     [rsp+160h+var_100], r13
0x18002e497  mov     rcx, [rsp+160h+var_F8]; pSid
0x18002e49c  test    rcx, rcx
0x18002e49f  jz      short loc_18002E4B2
0x18002e4a1  call    cs:__imp_FreeSid
0x18002e4a8  nop     dword ptr [rax+rax+00h]
0x18002e4ad  mov     [rsp+160h+var_F8], r13
0x18002e4b2  mov     r8, [rsp+160h+NewAcl]; pDacl
0x18002e4b7  xor     r9d, r9d; bDaclDefaulted
0x18002e4ba  mov     rcx, r14; pSecurityDescriptor
0x18002e4bd  lea     edx, [r9+1]; bDaclPresent
0x18002e4c1  call    cs:__imp_SetSecurityDescriptorDacl
0x18002e4c8  nop     dword ptr [rax+rax+00h]
0x18002e4cd  test    eax, eax
0x18002e4cf  jnz     loc_18002E582
0x18002e4d5  mov     rax, cs:WPP_GLOBAL_Control
0x18002e4dc  lea     rdx, WPP_GLOBAL_Control
0x18002e4e3  cmp     rax, rdx
0x18002e4e6  jz      short loc_18002E51F
0x18002e4e8  test    [rax+1Ch], r15b
0x18002e4ec  jz      short loc_18002E51F
0x18002e4ee  cmp     [rax+19h], r15b
0x18002e4f2  jb      short loc_18002E51F
0x18002e4f4  call    cs:__imp_GetLastError
0x18002e4fb  nop     dword ptr [rax+rax+00h]
0x18002e500  mov     edx, 42h ; 'B'
0x18002e505  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e50c  mov     r9d, eax
0x18002e50f  mov     rcx, [rcx+10h]
0x18002e513  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
  ... truncated ...
```
