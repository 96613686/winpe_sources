# CreateWellKnownSid

- ea: `0x1800ab560`
- end: `0x1800ab833`
- name: `CreateWellKnownSid`
- size: `723`
- prototype: `BOOL __stdcall(WELL_KNOWN_SID_TYPE WellKnownSidType, PSID DomainSid, PSID pSid, DWORD *cbSid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800aaaac`
- `0x1800ab280`

## callees

- `0x1800134a0`
- `0x1800ab560`
- `0x18012d119`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x1800ab5fd`
- `ntdll!RtlInitializeSid` at `0x1800ab5fd`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab648`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab6bf`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab6e7`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab6fd`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab713`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab732`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab74e`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab822`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab648`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab6bf`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab6e7`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab6fd`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab713`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab732`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab74e`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab822`
- `ntdll!RtlLengthRequiredSid` at `0x1800ab5b8`
- `ntdll!RtlLengthRequiredSid` at `0x1800ab5b8`
- `ntdll!RtlSetLastWin32Error` at `0x1800ab688`
- `ntdll!RtlSetLastWin32Error` at `0x1800ab6d5`
- `ntdll!RtlSetLastWin32Error` at `0x1800ab688`
- `ntdll!RtlSetLastWin32Error` at `0x1800ab6d5`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800ab6b0`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800ab7d9`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800ab6b0`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800ab7d9`
- `ntdll!RtlValidSid` at `0x1800ab675`
- `ntdll!RtlValidSid` at `0x1800ab675`
- `ntdll!RtlCopySid` at `0x1800ab6a3`
- `ntdll!RtlCopySid` at `0x1800ab6a3`

## pseudocode

```c
BOOL __stdcall CreateWellKnownSid(WELL_KNOWN_SID_TYPE WellKnownSidType, PSID DomainSid, PSID pSid, DWORD *cbSid)
{
  ULONG v8; // r14d
  UCHAR v9; // di
  unsigned int v10; // ebp
  ULONG v11; // eax
  DWORD v12; // ecx
  NTSTATUS v13; // eax
  PUCHAR v15; // rax
  PULONG v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  unsigned int v19; // eax
  UCHAR v20; // di
  __int64 v21; // r9

  if ( DomainSid && !RtlValidSid(DomainSid) || !cbSid || WellKnownSidType == WinLogonIdsSid )
    goto LABEL_21;
  v8 = 0;
  if ( WellKnownSidType == WinUserModeDriversSid )
  {
    v9 = 6;
    v10 = 4;
    goto LABEL_6;
  }
  v10 = 0;
LABEL_50:
  v19 = 0;
  v21 = 3LL * v10;
  while ( 1 )
  {
    if ( v19 >= LODWORD(qword_180198920[v21]) )
    {
      if ( ++v10 < 0xD )
        goto LABEL_50;
      if ( WellKnownSidType != WinNtAuthoritySid )
        goto LABEL_21;
      v10 = 4;
LABEL_38:
      v9 = 0;
      goto LABEL_6;
    }
    v17 = v19;
    v18 = (&off_180198918)[v21];
    if ( WellKnownSidType == HIDWORD(v18[v17]) )
      break;
    ++v19;
  }
  v8 = v18[v17];
  if ( v10 != 8 )
  {
    if ( v10 == 7 )
    {
LABEL_42:
      v9 = 2;
      goto LABEL_6;
    }
    if ( v10 != 6 )
    {
      v9 = 0;
      switch ( v10 )
      {
        case 0u:
        case 1u:
        case 2u:
        case 3u:
        case 4u:
          goto LABEL_40;
        case 5u:
        case 0xAu:
        case 0xBu:
          goto LABEL_42;
        case 9u:
          v9 = (WellKnownSidType == WinThisOrganizationCertificateSid) + 1;
          break;
        case 0xCu:
          goto LABEL_48;
        default:
          goto LABEL_6;
      }
      goto LABEL_6;
    }
    if ( DomainSid )
    {
      v20 = *RtlSubAuthorityCountSid(DomainSid);
      if ( v20 != 15 )
      {
        v9 = v20 + 1;
        goto LABEL_6;
      }
    }
    goto LABEL_21;
  }
LABEL_40:
  if ( WellKnownSidType == WinNtAuthoritySid )
    goto LABEL_38;
  if ( WellKnownSidType == WinThisOrganizationCertificateSid )
    goto LABEL_42;
LABEL_48:
  v9 = 1;
LABEL_6:
  v11 = RtlLengthRequiredSid(v9);
  v12 = *cbSid;
  *cbSid = v11;
  if ( v12 < v11 )
  {
    RtlSetLastWin32Error(0x7Au);
    return 0;
  }
  if ( !pSid )
  {
LABEL_21:
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  if ( v10 != 12 )
  {
    if ( v10 != 6 )
    {
      switch ( v10 )
      {
        case 0u:
        case 1u:
        case 2u:
        case 3u:
        case 4u:
        case 5u:
        case 7u:
        case 8u:
        case 9u:
        case 0xAu:
        case 0xBu:
          goto LABEL_9;
        default:
          goto LABEL_16;
      }
    }
    v13 = RtlCopySid(v11, pSid, DomainSid);
    if ( v13 >= 0 )
    {
      v15 = RtlSubAuthorityCountSid(pSid);
      ++*v15;
      goto LABEL_16;
    }
    goto LABEL_19;
  }
LABEL_9:
  v13 = RtlInitializeSid(pSid, (PSID_IDENTIFIER_AUTHORITY)&KnownAuthoritiesAndDomains[3 * v10], v9);
  if ( v13 < 0 )
  {
LABEL_19:
    BaseSetLastNTError((unsigned int)v13);
    return 0;
  }
  switch ( v10 )
  {
    case 5u:
      *RtlSubAuthoritySid(pSid, 0) = 32;
      break;
    case 7u:
      *RtlSubAuthoritySid(pSid, 0) = 64;
      break;
    case 9u:
      *RtlSubAuthoritySid(pSid, 0) = 65;
      break;
    case 0xAu:
      *RtlSubAuthoritySid(pSid, 0) = 2;
      break;
    case 0xBu:
      *RtlSubAuthoritySid(pSid, 0) = 3;
      break;
    default:
      if ( WellKnownSidType == WinUserModeDriversSid && v10 == 4 )
      {
        *RtlSubAuthoritySid(pSid, 0) = 84;
        v16 = RtlSubAuthoritySid(pSid, 1u);
        memset_0(v16, 0, 4LL * v9 - 4);
      }
      break;
  }
LABEL_16:
  if ( v9 )
    *RtlSubAuthoritySid(pSid, (unsigned int)v9 - 1) = v8;
  return 1;
}

```

## disassembly

```asm
0x1800ab560  push    rbx
0x1800ab562  push    rbp
0x1800ab563  push    rsi
0x1800ab564  push    rdi
0x1800ab565  push    r12
0x1800ab567  push    r13
0x1800ab569  push    r14
0x1800ab56b  push    r15
0x1800ab56d  sub     rsp, 28h
0x1800ab571  mov     r15, r9
0x1800ab574  mov     r12, r8
0x1800ab577  mov     r13, rdx
0x1800ab57a  mov     ebx, ecx
0x1800ab57c  test    rdx, rdx
0x1800ab57f  jnz     loc_1800AB672
0x1800ab585  test    r15, r15
0x1800ab588  jz      loc_1800AB683
0x1800ab58e  cmp     ebx, 15h
0x1800ab591  jz      loc_1800AB683
0x1800ab597  xor     r14d, r14d
0x1800ab59a  lea     r10, __ImageBase
0x1800ab5a1  cmp     ebx, 62h ; 'b'
0x1800ab5a4  jnz     loc_1800AB7FC
0x1800ab5aa  mov     dil, 6
0x1800ab5ad  mov     ebp, 4
0x1800ab5b2  movzx   esi, dil; jumptable 000000018019291B default case, cases 6-8
0x1800ab5b6  mov     ecx, esi; SubAuthorityCount
0x1800ab5b8  call    cs:__imp_RtlLengthRequiredSid
0x1800ab5be  mov     ecx, [r15]
0x1800ab5c1  mov     [r15], eax
0x1800ab5c4  cmp     ecx, eax
0x1800ab5c6  jb      loc_1800AB6D0
0x1800ab5cc  test    r12, r12
0x1800ab5cf  jz      loc_1800AB683
0x1800ab5d5  cmp     ebp, 0Ch
0x1800ab5d8  jnz     loc_1800AB692
0x1800ab5de  lea     rdx, __ImageBase
0x1800ab5e5  mov     eax, ebp; jumptable 0000000180192946 cases 0-5,7-11
0x1800ab5e7  movzx   r8d, dil; SubAuthorityCount
0x1800ab5eb  lea     rcx, [rax+rax*2]
0x1800ab5ef  lea     rdx, [rdx+rcx*8]
0x1800ab5f3  mov     rcx, r12; Sid
0x1800ab5f6  lea     rdx, [rdx+198910h]; IdentifierAuthority
0x1800ab5fd  call    cs:__imp_RtlInitializeSid
0x1800ab603  test    eax, eax
0x1800ab605  js      short loc_1800AB667
0x1800ab607  cmp     ebp, 5
0x1800ab60a  jz      loc_1800AB6BA
0x1800ab610  cmp     ebp, 7
0x1800ab613  jz      loc_1800AB81D
0x1800ab619  cmp     ebp, 9
0x1800ab61c  jz      loc_1800AB70E
0x1800ab622  cmp     ebp, 0Ah
0x1800ab625  jz      loc_1800AB6E2
0x1800ab62b  cmp     ebp, 0Bh
0x1800ab62e  jz      loc_1800AB6F8
0x1800ab634  cmp     ebx, 62h ; 'b'
0x1800ab637  jz      loc_1800AB724
0x1800ab63d  test    dil, dil; jumptable 0000000180192946 default case, case 6
0x1800ab640  jz      short loc_1800AB651
0x1800ab642  lea     edx, [rsi-1]; SubAuthority
0x1800ab645  mov     rcx, r12; Sid
0x1800ab648  call    cs:__imp_RtlSubAuthoritySid
0x1800ab64e  mov     [rax], r14d
0x1800ab651  mov     eax, 1
0x1800ab656  add     rsp, 28h
0x1800ab65a  pop     r15
0x1800ab65c  pop     r14
0x1800ab65e  pop     r13
0x1800ab660  pop     r12
0x1800ab662  pop     rdi
0x1800ab663  pop     rsi
0x1800ab664  pop     rbp
0x1800ab665  pop     rbx
0x1800ab666  retn
0x1800ab667  mov     ecx, eax
0x1800ab669  call    BaseSetLastNTError
0x1800ab66e  xor     eax, eax
0x1800ab670  jmp     short loc_1800AB656
0x1800ab672  mov     rcx, r13; Sid
0x1800ab675  call    cs:__imp_RtlValidSid
0x1800ab67b  test    al, al
0x1800ab67d  jnz     loc_1800AB585
0x1800ab683  mov     ecx, 57h ; 'W'; LastError
0x1800ab688  call    cs:__imp_RtlSetLastWin32Error
0x1800ab68e  xor     eax, eax
0x1800ab690  jmp     short loc_1800AB656
0x1800ab692  cmp     ebp, 6
0x1800ab695  jnz     loc_18019292C
0x1800ab69b  mov     r8, r13; SourceSid
0x1800ab69e  mov     rdx, r12; DestinationSid
0x1800ab6a1  mov     ecx, eax; DestinationSidLength
0x1800ab6a3  call    cs:__imp_RtlCopySid
0x1800ab6a9  test    eax, eax
0x1800ab6ab  js      short loc_1800AB667
0x1800ab6ad  mov     rcx, r12; Sid
0x1800ab6b0  call    cs:__imp_RtlSubAuthorityCountSid
0x1800ab6b6  inc     byte ptr [rax]
0x1800ab6b8  jmp     short def_180192946; jumptable 0000000180192946 default case, case 6
0x1800ab6ba  xor     edx, edx; SubAuthority
0x1800ab6bc  mov     rcx, r12; Sid
0x1800ab6bf  call    cs:__imp_RtlSubAuthoritySid
0x1800ab6c5  mov     dword ptr [rax], 20h ; ' '
0x1800ab6cb  jmp     def_180192946; jumptable 0000000180192946 default case, case 6
0x1800ab6d0  mov     ecx, 7Ah ; 'z'; LastError
0x1800ab6d5  call    cs:__imp_RtlSetLastWin32Error
0x1800ab6db  xor     eax, eax
0x1800ab6dd  jmp     loc_1800AB656
0x1800ab6e2  xor     edx, edx; SubAuthority
0x1800ab6e4  mov     rcx, r12; Sid
0x1800ab6e7  call    cs:__imp_RtlSubAuthoritySid
0x1800ab6ed  mov     dword ptr [rax], 2
0x1800ab6f3  jmp     def_180192946; jumptable 0000000180192946 default case, case 6
0x1800ab6f8  xor     edx, edx; SubAuthority
0x1800ab6fa  mov     rcx, r12; Sid
0x1800ab6fd  call    cs:__imp_RtlSubAuthoritySid
0x1800ab703  mov     dword ptr [rax], 3
0x1800ab709  jmp     def_180192946; jumptable 0000000180192946 default case, case 6
0x1800ab70e  xor     edx, edx; SubAuthority
0x1800ab710  mov     rcx, r12; Sid
0x1800ab713  call    cs:__imp_RtlSubAuthoritySid
0x1800ab719  mov     dword ptr [rax], 41h ; 'A'
0x1800ab71f  jmp     def_180192946; jumptable 0000000180192946 default case, case 6
0x1800ab724  cmp     ebp, 4
0x1800ab727  jnz     def_180192946; jumptable 0000000180192946 default case, case 6
0x1800ab72d  xor     edx, edx; SubAuthority
0x1800ab72f  mov     rcx, r12; Sid
0x1800ab732  call    cs:__imp_RtlSubAuthoritySid
0x1800ab738  mov     edx, 1; SubAuthority
0x1800ab73d  lea     rbx, ds:0FFFFFFFFFFFFFFFCh[rsi*4]
0x1800ab745  mov     rcx, r12; Sid
0x1800ab748  mov     dword ptr [rax], 54h ; 'T'
0x1800ab74e  call    cs:__imp_RtlSubAuthoritySid
0x1800ab754  mov     r8, rbx; Size
0x1800ab757  xor     edx, edx; Val
0x1800ab759  mov     rcx, rax; void *
0x1800ab75c  call    memset_0
0x1800ab761  jmp     def_180192946; jumptable 0000000180192946 default case, case 6
0x1800ab766  cmp     eax, r8d
0x1800ab769  jnb     short loc_1800AB787
0x1800ab76b  mov     ecx, eax
0x1800ab76d  lea     rdx, ds:0[rcx*8]
0x1800ab775  mov     rcx, [r9+r10+198918h]
0x1800ab77d  cmp     ebx, [rdx+rcx+4]
0x1800ab781  jz      short loc_1800AB7A4
0x1800ab783  inc     eax
0x1800ab785  jmp     short loc_1800AB766
0x1800ab787  inc     ebp
0x1800ab789  cmp     ebp, 0Dh
0x1800ab78c  jb      short loc_1800AB7FF
0x1800ab78e  cmp     ebx, 7
0x1800ab791  jnz     loc_1800AB683
0x1800ab797  mov     ebp, 4
0x1800ab79c  xor     dil, dil
0x1800ab79f  jmp     def_18019291B; jumptable 000000018019291B default case, cases 6-8
0x1800ab7a4  mov     r14d, [rdx+rcx]
0x1800ab7a8  cmp     ebp, 8
0x1800ab7ab  jnz     short loc_1800AB7BF
0x1800ab7ad  cmp     ebx, 7; jumptable 000000018019291B cases 0-4
0x1800ab7b0  jz      short loc_1800AB79C
0x1800ab7b2  cmp     ebx, 52h ; 'R'
0x1800ab7b5  jnz     short loc_1800AB7F4; jumptable 000000018019291B case 12
0x1800ab7b7  mov     dil, 2; jumptable 000000018019291B cases 5,10,11
0x1800ab7ba  jmp     def_18019291B; jumptable 000000018019291B default case, cases 6-8
0x1800ab7bf  cmp     ebp, 7
0x1800ab7c2  jz      short loc_1800AB7B7; jumptable 000000018019291B cases 5,10,11
0x1800ab7c4  cmp     ebp, 6
0x1800ab7c7  jnz     loc_180192904
0x1800ab7cd  test    r13, r13
0x1800ab7d0  jz      loc_1800AB683
0x1800ab7d6  mov     rcx, r13; Sid
0x1800ab7d9  call    cs:__imp_RtlSubAuthorityCountSid
0x1800ab7df  movzx   edi, byte ptr [rax]
0x1800ab7e2  cmp     dil, 0Fh
0x1800ab7e6  jz      loc_1800AB683
0x1800ab7ec  inc     dil
0x1800ab7ef  jmp     def_18019291B; jumptable 000000018019291B default case, cases 6-8
0x1800ab7f4  mov     dil, 1; jumptable 000000018019291B case 12
0x1800ab7f7  jmp     def_18019291B; jumptable 000000018019291B default case, cases 6-8
0x1800ab7fc  mov     ebp, r14d
0x1800ab7ff  mov     ecx, ebp
0x1800ab801  mov     eax, r14d
0x1800ab804  lea     rdx, [rcx+rcx*2]
0x1800ab808  lea     r9, ds:0[rdx*8]
0x1800ab810  mov     r8d, [r9+r10+198920h]
0x1800ab818  jmp     loc_1800AB766
0x1800ab81d  xor     edx, edx; SubAuthority
0x1800ab81f  mov     rcx, r12; Sid
0x1800ab822  call    cs:__imp_RtlSubAuthoritySid
0x1800ab828  mov     dword ptr [rax], 40h ; '@'
0x1800ab82e  jmp     def_180192946; jumptable 0000000180192946 default case, case 6
0x180192904  xor     dil, dil
0x180192907  cmp     ebp, 0Ch; switch 13 cases
0x18019290a  ja      def_18019291B; jumptable 000000018019291B default case, cases 6-8
0x180192910  mov     eax, ds:(jpt_18019291B - 180000000h)[r10+rbp*4]
0x180192918  add     rax, r10
0x18019291b  jmp     rax; switch jump
0x18019291d  cmp     ebx, 52h ; 'R'; jumptable 000000018019291B case 9
0x180192920  setz    dil
0x180192924  inc     dil
0x180192927  jmp     def_18019291B; jumptable 000000018019291B default case, cases 6-8
0x18019292c  cmp     ebp, 0Bh; switch 12 cases
0x18019292f  ja      def_180192946; jumptable 0000000180192946 default case, case 6
0x180192935  lea     rdx, __ImageBase
0x18019293c  mov     eax, ds:(jpt_180192946 - 180000000h)[rdx+rbp*4]
0x180192943  add     rax, rdx
0x180192946  jmp     rax; switch jump
```
