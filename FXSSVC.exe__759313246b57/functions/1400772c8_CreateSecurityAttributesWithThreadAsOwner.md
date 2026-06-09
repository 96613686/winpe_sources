# CreateSecurityAttributesWithThreadAsOwner

- ea: `0x1400772c8`
- end: `0x14007780c`
- name: `CreateSecurityAttributesWithThreadAsOwner`
- size: `1348`
- prototype: `_DWORD *()`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140076c74`

## callees

- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x1400698ec`
- `0x14006998c`
- `0x1400772c8`
- `0x140077e50`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14007772e`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14007772e`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x14007749b`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x14007749b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14007756e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400775ee`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14007756e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400775ee`
- `ADVAPI32!SetEntriesInAclW` at `0x140077694`
- `ADVAPI32!SetEntriesInAclW` at `0x140077694`
- `ADVAPI32!FreeSid` at `0x1400776f3`
- `ADVAPI32!FreeSid` at `0x14007770e`
- `ADVAPI32!FreeSid` at `0x1400777a7`
- `ADVAPI32!FreeSid` at `0x1400777bd`
- `ADVAPI32!FreeSid` at `0x1400776f3`
- `ADVAPI32!FreeSid` at `0x14007770e`
- `ADVAPI32!FreeSid` at `0x1400777a7`
- `ADVAPI32!FreeSid` at `0x1400777bd`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140077402`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140077402`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1400774ee`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1400774ee`
- `KERNEL32!GetLastError` at `0x140077436`
- `KERNEL32!GetLastError` at `0x140077480`
- `KERNEL32!GetLastError` at `0x1400774cf`
- `KERNEL32!GetLastError` at `0x140077522`
- `KERNEL32!GetLastError` at `0x1400775a2`
- `KERNEL32!GetLastError` at `0x140077622`
- `KERNEL32!GetLastError` at `0x14007775a`
- `KERNEL32!GetLastError` at `0x140077436`
- `KERNEL32!GetLastError` at `0x140077480`
- `KERNEL32!GetLastError` at `0x1400774cf`
- `KERNEL32!GetLastError` at `0x140077522`
- `KERNEL32!GetLastError` at `0x1400775a2`
- `KERNEL32!GetLastError` at `0x140077622`
- `KERNEL32!GetLastError` at `0x14007775a`
- `KERNEL32!SetLastError` at `0x1400776d8`
- `KERNEL32!SetLastError` at `0x1400776d8`
- `KERNEL32!LocalFree` at `0x1400777d7`
- `KERNEL32!LocalFree` at `0x1400777d7`

## pseudocode

```c
_DWORD *CreateSecurityAttributesWithThreadAsOwner()
{
  _DWORD *v0; // rsi
  void *v2; // r14
  void *v3; // rax
  void *v4; // rdi
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  DWORD LastError; // eax
  void *CurrentThreadSID; // rax
  DWORD v10; // eax
  DWORD v11; // ebx
  PSID v12; // [rsp+60h] [rbp-A0h] BYREF
  PSID pSid; // [rsp+68h] [rbp-98h] BYREF
  PACL NewAcl; // [rsp+70h] [rbp-90h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp-88h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-80h] BYREF
  int v17; // [rsp+B0h] [rbp-50h]
  __int64 v18; // [rsp+B4h] [rbp-4Ch]
  int v19; // [rsp+CCh] [rbp-34h]
  int v20; // [rsp+D0h] [rbp-30h]
  PSID v21; // [rsp+D8h] [rbp-28h]
  int v22; // [rsp+E0h] [rbp-20h]
  __int64 v23; // [rsp+E4h] [rbp-1Ch]
  int v24; // [rsp+FCh] [rbp-4h]
  int v25; // [rsp+100h] [rbp+0h]
  PSID v26; // [rsp+108h] [rbp+8h]

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  v12 = 0;
  pSid = 0;
  NewAcl = 0;
  pListOfExplicitEntries.grfAccessPermissions = 0;
  memset_0(&pListOfExplicitEntries.grfAccessMode, 0, 0x8Cu);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v0 = (_DWORD *)pMemAlloc(0x18u);
  if ( !v0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_db036311db36307996a98c23702218b2_Traceguids, 24);
    }
    return 0;
  }
  v2 = 0;
  v3 = (void *)pMemAlloc(0x28u);
  v4 = v3;
  if ( !v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    v6 = 58;
    v7 = 40;
LABEL_62:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_db036311db36307996a98c23702218b2_Traceguids, v7);
LABEL_63:
    pMemFree(v0);
    pMemFree(v4);
    pMemFree(v2);
    if ( v12 )
      FreeSid(v12);
    if ( pSid )
      FreeSid(pSid);
    if ( NewAcl )
      LocalFree(NewAcl);
    return 0;
  }
  *v0 = 24;
  v0[4] = 1;
  *((_QWORD *)v0 + 1) = v3;
  if ( !InitializeSecurityDescriptor(v3, 1u) )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    LastError = GetLastError();
    v6 = 59;
    goto LABEL_61;
  }
  CurrentThreadSID = (void *)GetCurrentThreadSID();
  v2 = CurrentThreadSID;
  if ( !CurrentThreadSID )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    LastError = GetLastError();
    v6 = 60;
    goto LABEL_61;
  }
  if ( !SetSecurityDescriptorOwner(v4, CurrentThreadSID, 0) )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    LastError = GetLastError();
    v6 = 61;
    goto LABEL_61;
  }
  if ( !SetSecurityDescriptorGroup(v4, v2, 0) )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    LastError = GetLastError();
    v6 = 62;
    goto LABEL_61;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    LastError = GetLastError();
    v6 = 63;
    goto LABEL_61;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &v12) )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    LastError = GetLastError();
    v6 = 64;
    goto LABEL_61;
  }
  v21 = pSid;
  pListOfExplicitEntries.grfAccessPermissions = 0x100000;
  v22 = 0x100000;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v2;
  v17 = 2031619;
  v18 = 2;
  v19 = 0;
  v20 = 2;
  v23 = 2;
  v24 = 0;
  v25 = 2;
  v26 = v12;
  v10 = SetEntriesInAclW(3u, &pListOfExplicitEntries, 0, &NewAcl);
  v11 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_db036311db36307996a98c23702218b2_Traceguids, v10);
    }
    SetLastError(v11);
    goto LABEL_63;
  }
  if ( v12 )
  {
    FreeSid(v12);
    v12 = 0;
  }
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( !SetSecurityDescriptorDacl(v4, 1, NewAcl, 0) )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    LastError = GetLastError();
    v6 = 66;
LABEL_61:
    v5 = WPP_GLOBAL_Control;
    v7 = LastError;
    goto LABEL_62;
  }
  return v0;
}

```

## disassembly

```asm
0x1400772c8  push    rbp
0x1400772ca  push    rbx
0x1400772cb  push    rsi
0x1400772cc  push    rdi
0x1400772cd  push    r12
0x1400772cf  push    r13
0x1400772d1  push    r14
0x1400772d3  push    r15
0x1400772d5  lea     rbp, [rsp-28h]
0x1400772da  sub     rsp, 128h
0x1400772e1  mov     rax, cs:__security_cookie
0x1400772e8  xor     rax, rsp
0x1400772eb  mov     [rbp+60h+var_50], rax
0x1400772ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400772f6  lea     r13, WPP_GLOBAL_Control
0x1400772fd  lea     rbx, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140077304  mov     r12d, 2
0x14007730a  cmp     rcx, r13
0x14007730d  jz      short loc_14007732C
0x14007730f  test    [rcx+1Ch], r12b
0x140077313  jz      short loc_14007732C
0x140077315  cmp     byte ptr [rcx+19h], 5
0x140077319  jb      short loc_14007732C
0x14007731b  mov     rcx, [rcx+10h]
0x14007731f  lea     edx, [r12+36h]
0x140077324  mov     r8, rbx
0x140077327  call    WPP_SF_
0x14007732c  xor     r15d, r15d
0x14007732f  lea     rcx, [rbp+60h+pListOfExplicitEntries.grfAccessMode]; void *
0x140077333  xor     edx, edx; Val
0x140077335  mov     [rsp+160h+var_100], r15
0x14007733a  mov     r8d, 8Ch; Size
0x140077340  mov     [rsp+160h+var_F8], r15
0x140077345  mov     [rsp+160h+NewAcl], r15
0x14007734a  mov     [rbp+60h+pListOfExplicitEntries.grfAccessPermissions], r15d
0x14007734e  call    memset_0
0x140077353  lea     edi, [r15+18h]
0x140077357  mov     dword ptr [rsp+160h+pIdentifierAuthority.Value], r15d
0x14007735c  mov     ecx, edi; dwBytes
0x14007735e  mov     word ptr [rsp+160h+pIdentifierAuthority.Value+4], 500h
0x140077365  call    pMemAlloc
0x14007736a  mov     rsi, rax
0x14007736d  test    rax, rax
0x140077370  jnz     short loc_1400773A3
0x140077372  mov     rcx, cs:WPP_GLOBAL_Control
0x140077379  cmp     rcx, r13
0x14007737c  jz      short loc_14007739C
0x14007737e  test    [rcx+1Ch], r12b
0x140077382  jz      short loc_14007739C
0x140077384  cmp     [rcx+19h], r12b
0x140077388  jb      short loc_14007739C
0x14007738a  mov     rcx, [rcx+10h]
0x14007738e  lea     edx, [rdi+21h]
0x140077391  mov     r9d, edi
0x140077394  mov     r8, rbx
0x140077397  call    WPP_SF_d
0x14007739c  xor     eax, eax
0x14007739e  jmp     loc_1400777EB
0x1400773a3  mov     ecx, 28h ; '('; dwBytes
0x1400773a8  mov     r14, r15
0x1400773ab  call    pMemAlloc
0x1400773b0  mov     rdi, rax
0x1400773b3  test    rax, rax
0x1400773b6  jnz     short loc_1400773EB
0x1400773b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400773bf  cmp     rcx, r13
0x1400773c2  jz      loc_140077785
0x1400773c8  test    [rcx+1Ch], r12b
0x1400773cc  jz      loc_140077785
0x1400773d2  cmp     [rcx+19h], r12b
0x1400773d6  jb      loc_140077785
0x1400773dc  lea     edx, [rax+3Ah]
0x1400773df  mov     r8, rbx
0x1400773e2  lea     r9d, [rax+28h]
0x1400773e6  jmp     loc_14007777C
0x1400773eb  mov     eax, 1
0x1400773f0  mov     dword ptr [rsi], 18h
0x1400773f6  mov     edx, eax; dwRevision
0x1400773f8  mov     [rsi+10h], eax
0x1400773fb  mov     rcx, rdi; pSecurityDescriptor
0x1400773fe  mov     [rsi+8], rdi
0x140077402  call    cs:__imp_InitializeSecurityDescriptor
0x140077409  nop     dword ptr [rax+rax+00h]
0x14007740e  test    eax, eax
0x140077410  jnz     short loc_14007744F
0x140077412  mov     rax, cs:WPP_GLOBAL_Control
0x140077419  cmp     rax, r13
0x14007741c  jz      loc_140077785
0x140077422  test    [rax+1Ch], r12b
0x140077426  jz      loc_140077785
0x14007742c  cmp     [rax+19h], r12b
0x140077430  jb      loc_140077785
0x140077436  call    cs:__imp_GetLastError
0x14007743d  nop     dword ptr [rax+rax+00h]
0x140077442  mov     edx, 3Bh ; ';'
0x140077447  mov     r8, rbx
0x14007744a  jmp     loc_140077772
0x14007744f  call    GetCurrentThreadSID
0x140077454  mov     r14, rax
0x140077457  test    rax, rax
0x14007745a  jnz     short loc_140077492
0x14007745c  mov     rcx, cs:WPP_GLOBAL_Control
0x140077463  cmp     rcx, r13
0x140077466  jz      loc_140077785
0x14007746c  test    [rcx+1Ch], r12b
0x140077470  jz      loc_140077785
0x140077476  cmp     [rcx+19h], r12b
0x14007747a  jb      loc_140077785
0x140077480  call    cs:__imp_GetLastError
0x140077487  nop     dword ptr [rax+rax+00h]
0x14007748c  lea     edx, [r14+3Ch]
0x140077490  jmp     short loc_140077447
0x140077492  xor     r8d, r8d; bOwnerDefaulted
0x140077495  mov     rdx, r14; pOwner
0x140077498  mov     rcx, rdi; pSecurityDescriptor
0x14007749b  call    cs:__imp_SetSecurityDescriptorOwner
0x1400774a2  nop     dword ptr [rax+rax+00h]
0x1400774a7  test    eax, eax
0x1400774a9  jnz     short loc_1400774E5
0x1400774ab  mov     rax, cs:WPP_GLOBAL_Control
0x1400774b2  cmp     rax, r13
0x1400774b5  jz      loc_140077785
0x1400774bb  test    [rax+1Ch], r12b
0x1400774bf  jz      loc_140077785
0x1400774c5  cmp     [rax+19h], r12b
0x1400774c9  jb      loc_140077785
0x1400774cf  call    cs:__imp_GetLastError
0x1400774d6  nop     dword ptr [rax+rax+00h]
0x1400774db  mov     edx, 3Dh ; '='
0x1400774e0  jmp     loc_140077447
0x1400774e5  xor     r8d, r8d; bGroupDefaulted
0x1400774e8  mov     rdx, r14; pGroup
0x1400774eb  mov     rcx, rdi; pSecurityDescriptor
0x1400774ee  call    cs:__imp_SetSecurityDescriptorGroup
0x1400774f5  nop     dword ptr [rax+rax+00h]
0x1400774fa  test    eax, eax
0x1400774fc  jnz     short loc_140077538
0x1400774fe  mov     rax, cs:WPP_GLOBAL_Control
0x140077505  cmp     rax, r13
0x140077508  jz      loc_140077785
0x14007750e  test    [rax+1Ch], r12b
0x140077512  jz      loc_140077785
0x140077518  cmp     [rax+19h], r12b
0x14007751c  jb      loc_140077785
0x140077522  call    cs:__imp_GetLastError
0x140077529  nop     dword ptr [rax+rax+00h]
0x14007752e  mov     edx, 3Eh ; '>'
0x140077533  jmp     loc_140077447
0x140077538  lea     rax, [rsp+160h+var_F8]
0x14007753d  xor     r9d, r9d; nSubAuthority1
0x140077540  mov     [rsp+160h+pSid], rax; pSid
0x140077545  lea     rcx, [rsp+160h+pIdentifierAuthority]; pIdentifierAuthority
0x14007754a  mov     [rsp+160h+nSubAuthority7], r15d; nSubAuthority7
0x14007754f  mov     dl, 1; nSubAuthorityCount
0x140077551  mov     [rsp+160h+nSubAuthority6], r15d; nSubAuthority6
0x140077556  mov     [rsp+160h+nSubAuthority5], r15d; nSubAuthority5
0x14007755b  lea     r8d, [r9+14h]; nSubAuthority0
0x14007755f  mov     [rsp+160h+nSubAuthority4], r15d; nSubAuthority4
0x140077564  mov     [rsp+160h+nSubAuthority3], r15d; nSubAuthority3
0x140077569  mov     [rsp+160h+nSubAuthority2], r15d; nSubAuthority2
0x14007756e  call    cs:__imp_AllocateAndInitializeSid
0x140077575  nop     dword ptr [rax+rax+00h]
0x14007757a  test    eax, eax
0x14007757c  jnz     short loc_1400775B8
0x14007757e  mov     rax, cs:WPP_GLOBAL_Control
0x140077585  cmp     rax, r13
0x140077588  jz      loc_140077785
0x14007758e  test    [rax+1Ch], r12b
0x140077592  jz      loc_140077785
0x140077598  cmp     [rax+19h], r12b
0x14007759c  jb      loc_140077785
0x1400775a2  call    cs:__imp_GetLastError
0x1400775a9  nop     dword ptr [rax+rax+00h]
0x1400775ae  mov     edx, 3Fh ; '?'
0x1400775b3  jmp     loc_140077447
0x1400775b8  lea     rax, [rsp+160h+var_100]
0x1400775bd  xor     r9d, r9d; nSubAuthority1
0x1400775c0  mov     [rsp+160h+pSid], rax; pSid
0x1400775c5  lea     rcx, [rsp+160h+pIdentifierAuthority]; pIdentifierAuthority
0x1400775ca  mov     [rsp+160h+nSubAuthority7], r15d; nSubAuthority7
0x1400775cf  mov     dl, 1; nSubAuthorityCount
0x1400775d1  mov     [rsp+160h+nSubAuthority6], r15d; nSubAuthority6
0x1400775d6  mov     [rsp+160h+nSubAuthority5], r15d; nSubAuthority5
0x1400775db  lea     r8d, [r9+0Bh]; nSubAuthority0
0x1400775df  mov     [rsp+160h+nSubAuthority4], r15d; nSubAuthority4
0x1400775e4  mov     [rsp+160h+nSubAuthority3], r15d; nSubAuthority3
0x1400775e9  mov     [rsp+160h+nSubAuthority2], r15d; nSubAuthority2
0x1400775ee  call    cs:__imp_AllocateAndInitializeSid
0x1400775f5  nop     dword ptr [rax+rax+00h]
0x1400775fa  test    eax, eax
0x1400775fc  jnz     short loc_140077638
0x1400775fe  mov     rax, cs:WPP_GLOBAL_Control
0x140077605  cmp     rax, r13
0x140077608  jz      loc_140077785
0x14007760e  test    [rax+1Ch], r12b
0x140077612  jz      loc_140077785
0x140077618  cmp     [rax+19h], r12b
0x14007761c  jb      loc_140077785
0x140077622  call    cs:__imp_GetLastError
0x140077629  nop     dword ptr [rax+rax+00h]
0x14007762e  mov     edx, 40h ; '@'
0x140077633  jmp     loc_140077447
0x140077638  mov     rax, [rsp+160h+var_F8]
0x14007763d  lea     r9, [rsp+160h+NewAcl]; NewAcl
0x140077642  mov     ecx, 100000h
0x140077647  mov     [rbp+60h+var_88], rax
0x14007764b  mov     rax, [rsp+160h+var_100]
0x140077650  lea     rdx, [rbp+60h+pListOfExplicitEntries]; pListOfExplicitEntries
0x140077654  xor     r8d, r8d; OldAcl
0x140077657  mov     [rbp+60h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x14007765a  mov     [rbp+60h+var_80], ecx
0x14007765d  mov     qword ptr [rbp+60h+pListOfExplicitEntries.grfAccessMode], r12
0x140077661  mov     [rbp+60h+pListOfExplicitEntries.Trustee.TrusteeForm], r15d
0x140077665  lea     ecx, [r8+3]; cCountOfExplicitEntries
0x140077669  mov     [rbp+60h+pListOfExplicitEntries.Trustee.TrusteeType], r12d
0x14007766d  mov     [rbp+60h+pListOfExplicitEntries.Trustee.ptstrName], r14
0x140077671  mov     [rbp+60h+var_B0], 1F0003h
0x140077678  mov     [rbp+60h+var_AC], r12
0x14007767c  mov     [rbp+60h+var_94], r15d
0x140077680  mov     [rbp+60h+var_90], r12d
0x140077684  mov     [rbp+60h+var_7C], r12
0x140077688  mov     [rbp+60h+var_64], r15d
0x14007768c  mov     [rbp+60h+var_60], r12d
0x140077690  mov     [rbp+60h+var_58], rax
0x140077694  call    cs:__imp_SetEntriesInAclW
0x14007769b  nop     dword ptr [rax+rax+00h]
0x1400776a0  mov     ebx, eax
0x1400776a2  test    eax, eax
0x1400776a4  jz      short loc_1400776E9
0x1400776a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400776ad  cmp     rcx, r13
0x1400776b0  jz      short loc_1400776D6
0x1400776b2  test    [rcx+1Ch], r12b
0x1400776b6  jz      short loc_1400776D6
0x1400776b8  cmp     [rcx+19h], r12b
0x1400776bc  jb      short loc_1400776D6
0x1400776be  mov     rcx, [rcx+10h]
0x1400776c2  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1400776c9  mov     edx, 41h ; 'A'
0x1400776ce  mov     r9d, eax
0x1400776d1  call    WPP_SF_d
0x1400776d6  mov     ecx, ebx; dwErrCode
0x1400776d8  call    cs:__imp_SetLastError
0x1400776df  nop     dword ptr [rax+rax+00h]
0x1400776e4  jmp     loc_140077785
0x1400776e9  mov     rcx, [rsp+160h+var_100]; pSid
0x1400776ee  test    rcx, rcx
0x1400776f1  jz      short loc_140077704
0x1400776f3  call    cs:__imp_FreeSid
0x1400776fa  nop     dword ptr [rax+rax+00h]
0x1400776ff  mov     [rsp+160h+var_100], r15
0x140077704  mov     rcx, [rsp+160h+var_F8]; pSid
0x140077709  test    rcx, rcx
0x14007770c  jz      short loc_14007771F
0x14007770e  call    cs:__imp_FreeSid
0x140077715  nop     dword ptr [rax+rax+00h]
0x14007771a  mov     [rsp+160h+var_F8], r15
0x14007771f  mov     r8, [rsp+160h+NewAcl]; pDacl
0x140077724  xor     r9d, r9d; bDaclDefaulted
0x140077727  mov     rcx, rdi; pSecurityDescriptor
0x14007772a  lea     edx, [r9+1]; bDaclPresent
0x14007772e  call    cs:__imp_SetSecurityDescriptorDacl
0x140077735  nop     dword ptr [rax+rax+00h]
0x14007773a  test    eax, eax
0x14007773c  jnz     loc_1400777E8
0x140077742  mov     rax, cs:WPP_GLOBAL_Control
0x140077749  cmp     rax, r13
0x14007774c  jz      short loc_140077785
0x14007774e  test    [rax+1Ch], r12b
0x140077752  jz      short loc_140077785
0x140077754  cmp     [rax+19h], r12b
0x140077758  jb      short loc_140077785
0x14007775a  call    cs:__imp_GetLastError
0x140077761  nop     dword ptr [rax+rax+00h]
0x140077766  mov     edx, 42h ; 'B'
0x14007776b  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140077772  mov     rcx, cs:WPP_GLOBAL_Control
0x140077779  mov     r9d, eax
0x14007777c  mov     rcx, [rcx+10h]
0x140077780  call    WPP_SF_d
0x140077785  mov     rcx, rsi; lpMem
0x140077788  call    pMemFree
0x14007778d  mov     rcx, rdi; lpMem
0x140077790  call    pMemFree
0x140077795  mov     rcx, r14; lpMem
0x140077798  call    pMemFree
0x14007779d  mov     rcx, [rsp+160h+var_100]; pSid
0x1400777a2  test    rcx, rcx
0x1400777a5  jz      short loc_1400777B3
0x1400777a7  call    cs:__imp_FreeSid
0x1400777ae  nop     dword ptr [rax+rax+00h]
0x1400777b3  mov     rcx, [rsp+160h+var_F8]; pSid
0x1400777b8  test    rcx, rcx
0x1400777bb  jz      short loc_1400777C9
0x1400777bd  call    cs:__imp_FreeSid
0x1400777c4  nop     dword ptr [rax+rax+00h]
0x1400777c9  mov     rcx, [rsp+160h+NewAcl]; hMem
0x1400777ce  test    rcx, rcx
0x1400777d1  jz      loc_14007739C
0x1400777d7  call    cs:__imp_LocalFree
  ... truncated ...
```
