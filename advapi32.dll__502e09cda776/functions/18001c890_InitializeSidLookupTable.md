# InitializeSidLookupTable

- ea: `0x18001c890`
- end: `0x18001ce38`
- name: `InitializeSidLookupTable`
- size: `1448`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b744`
- `0x18001c000`
- `0x18001cfb8`

## callees

- `0x18001c890`
- `0x18001ce40`
- `0x18001d8c4`
- `0x180072042`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18001cb74`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001cc40`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001cb74`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001cc40`
- `ntdll!RtlLengthSid` at `0x18001cb49`
- `ntdll!RtlLengthSid` at `0x18001cc15`
- `ntdll!RtlLengthSid` at `0x18001cb49`
- `ntdll!RtlLengthSid` at `0x18001cc15`
- `ntdll!RtlInitializeSid` at `0x18001ca30`
- `ntdll!RtlInitializeSid` at `0x18001ca73`
- `ntdll!RtlInitializeSid` at `0x18001cb9b`
- `ntdll!RtlInitializeSid` at `0x18001cbc5`
- `ntdll!RtlInitializeSid` at `0x18001cc5f`
- `ntdll!RtlInitializeSid` at `0x18001ccb7`
- `ntdll!RtlInitializeSid` at `0x18001ccfd`
- `ntdll!RtlInitializeSid` at `0x18001cd32`
- `ntdll!RtlInitializeSid` at `0x18001cdd0`
- `ntdll!RtlInitializeSid` at `0x18001ca30`
- `ntdll!RtlInitializeSid` at `0x18001ca73`
- `ntdll!RtlInitializeSid` at `0x18001cb9b`
- `ntdll!RtlInitializeSid` at `0x18001cbc5`
- `ntdll!RtlInitializeSid` at `0x18001cc5f`
- `ntdll!RtlInitializeSid` at `0x18001ccb7`
- `ntdll!RtlInitializeSid` at `0x18001ccfd`
- `ntdll!RtlInitializeSid` at `0x18001cd32`
- `ntdll!RtlInitializeSid` at `0x18001cdd0`
- `ntdll!RtlSubAuthoritySid` at `0x18001ca41`
- `ntdll!RtlSubAuthoritySid` at `0x18001ca84`
- `ntdll!RtlSubAuthoritySid` at `0x18001ca9c`
- `ntdll!RtlSubAuthoritySid` at `0x18001cbd6`
- `ntdll!RtlSubAuthoritySid` at `0x18001cc70`
- `ntdll!RtlSubAuthoritySid` at `0x18001ccc8`
- `ntdll!RtlSubAuthoritySid` at `0x18001cd0e`
- `ntdll!RtlSubAuthoritySid` at `0x18001cd43`
- `ntdll!RtlSubAuthoritySid` at `0x18001cd5b`
- `ntdll!RtlSubAuthoritySid` at `0x18001cde1`
- `ntdll!RtlSubAuthoritySid` at `0x18001ca41`
- `ntdll!RtlSubAuthoritySid` at `0x18001ca84`
- `ntdll!RtlSubAuthoritySid` at `0x18001ca9c`
- `ntdll!RtlSubAuthoritySid` at `0x18001cbd6`
- `ntdll!RtlSubAuthoritySid` at `0x18001cc70`
- `ntdll!RtlSubAuthoritySid` at `0x18001ccc8`
- `ntdll!RtlSubAuthoritySid` at `0x18001cd0e`
- `ntdll!RtlSubAuthoritySid` at `0x18001cd43`
- `ntdll!RtlSubAuthoritySid` at `0x18001cd5b`
- `ntdll!RtlSubAuthoritySid` at `0x18001cde1`
- `KERNELBASE!Sleep` at `0x18001cd99`
- `KERNELBASE!Sleep` at `0x18001cd99`
- `KERNEL32!EnterCriticalSection` at `0x18001c922`
- `KERNEL32!EnterCriticalSection` at `0x18001c922`
- `KERNEL32!LeaveCriticalSection` at `0x18001cb05`
- `KERNEL32!LeaveCriticalSection` at `0x18001cb05`

## pseudocode

```c
char __fastcall InitializeSidLookupTable(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // ebx
  int v5; // eax
  __int64 i; // rdi
  __int64 v7; // rsi
  PSID *v8; // r14
  int v9; // eax
  ULONG v10; // edx
  PULONG v11; // rax
  ULONG v12; // edx
  ULONG v14; // eax
  ULONG v15; // eax
  PULONG v16; // rax
  PULONG v17; // rax
  __int64 v18; // [rsp+20h] [rbp-50h] BYREF
  __int64 v19; // [rsp+28h] [rbp-48h] BYREF
  __int64 v20; // [rsp+30h] [rbp-40h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v21; // [rsp+38h] [rbp-38h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v22; // [rsp+40h] [rbp-30h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v23; // [rsp+48h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+50h] [rbp-20h] BYREF

  v4 = (unsigned __int8)a1;
  LODWORD(v19) = 0;
  WORD2(v19) = 256;
  LODWORD(v20) = 0;
  WORD2(v20) = 512;
  *(_DWORD *)v21.Value = 0;
  *(_WORD *)&v21.Value[4] = 768;
  LODWORD(v18) = 0;
  WORD2(v18) = 1280;
  *(_DWORD *)v22.Value = 0;
  *(_WORD *)&v22.Value[4] = 4096;
  *(_DWORD *)v23.Value = 0;
  *(_WORD *)&v23.Value[4] = 3840;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 4608;
  if ( fCSInitialized )
  {
    EnterCriticalSection(&SddlSidLookupCritical);
  }
  else
  {
    while ( _InterlockedCompareExchange(&fWaitSddlLookup, 1, 0) )
      Sleep(0xAu);
  }
  if ( v4 == 1 )
  {
    if ( (unsigned int)++dword_1800B21C8 > 1 || gbLookupTableInitialized == 1 )
    {
      LeaveWaitSddlSidLookup(a1, a2, a3, a4, v18, v19, v20);
      return 1;
    }
  }
  else if ( v4 == 2 )
  {
    if ( (unsigned int)dword_1800B21C8 <= 1 )
      v5 = 0;
    else
      v5 = dword_1800B21C8 - 1;
    dword_1800B21C8 = v5;
    goto LABEL_25;
  }
  CacheDomainAndDnsDomainSids(a1, a2, a3, a4, v18, v19, v20);
  for ( i = 0; i != 68; ++i )
  {
    v7 = 13 * i;
    if ( (_BYTE)v4 == 1 )
      LOBYTE(qword_1800AEDD0[v7]) = 0;
    v8 = (PSID *)&qword_1800AEDE0[v7];
    if ( LOBYTE(qword_1800AEDD0[v7]) != 1 || !*v8 )
    {
      v9 = HIDWORD(qword_1800AEDE8[v7]);
      *v8 = &qword_1800AEDF0[v7];
      if ( v9 )
      {
        if ( v9 == 6 )
        {
          RtlInitializeSid(&qword_1800AEDF0[v7], (PSID_IDENTIFIER_AUTHORITY)&v18, 2u);
          v11 = RtlSubAuthoritySid(*v8, 0);
          v12 = 1;
          *v11 = 32;
LABEL_21:
          *RtlSubAuthoritySid(*v8, v12) = qword_1800AEDE8[v7];
          LOBYTE(qword_1800AEDD0[v7]) = 1;
          continue;
        }
        if ( v9 == 5 )
        {
          RtlInitializeSid(&qword_1800AEDF0[v7], (PSID_IDENTIFIER_AUTHORITY)&v18, 1u);
          v12 = 0;
          goto LABEL_21;
        }
        switch ( v9 )
        {
          case 1:
            RtlInitializeSid(&qword_1800AEDF0[v7], (PSID_IDENTIFIER_AUTHORITY)&v19, 1u);
            *RtlSubAuthoritySid(*v8, 0) = qword_1800AEDE8[13 * i];
            LOBYTE(qword_1800AEDD0[13 * i]) = 1;
            break;
          case 2:
            RtlInitializeSid(&qword_1800AEDF0[v7], (PSID_IDENTIFIER_AUTHORITY)&v20, 1u);
            *RtlSubAuthoritySid(*v8, 0) = qword_1800AEDE8[13 * i];
            LOBYTE(qword_1800AEDD0[13 * i]) = 1;
            break;
          case 3:
            if ( gbDomainSidCached )
            {
              v15 = RtlLengthSid(Sid);
              memcpy_0(*v8, Sid, v15);
              ++*((_BYTE *)*v8 + 1);
              v10 = *RtlSubAuthorityCountSid(Sid);
              goto LABEL_19;
            }
            break;
          case 4:
            RtlInitializeSid(&qword_1800AEDF0[v7], &v21, 1u);
            *RtlSubAuthoritySid(*v8, 0) = qword_1800AEDE8[13 * i];
            LOBYTE(qword_1800AEDD0[13 * i]) = 1;
            break;
          case 8:
            RtlInitializeSid(&qword_1800AEDF0[v7], &v22, 1u);
            *RtlSubAuthoritySid(*v8, 0) = qword_1800AEDE8[13 * i];
            LOBYTE(qword_1800AEDD0[13 * i]) = 1;
            break;
          case 9:
            RtlInitializeSid(&qword_1800AEDF0[v7], &v23, 2u);
            v16 = RtlSubAuthoritySid(*v8, 0);
            v10 = 1;
            *v16 = 2;
            goto LABEL_19;
          case 10:
            RtlInitializeSid(&qword_1800AEDF0[v7], (PSID_IDENTIFIER_AUTHORITY)&v18, 6u);
            *RtlSubAuthoritySid(*v8, 0) = 84;
            v17 = RtlSubAuthoritySid(*v8, 1u);
            *(_OWORD *)v17 = 0;
            v17[4] = 0;
            LOBYTE(qword_1800AEDD0[13 * i]) = 1;
            break;
          case 11:
            RtlInitializeSid(&qword_1800AEDF0[v7], &IdentifierAuthority, 1u);
            v10 = 0;
LABEL_19:
            *RtlSubAuthoritySid(*v8, v10) = qword_1800AEDE8[13 * i];
            LOBYTE(qword_1800AEDD0[13 * i]) = 1;
            break;
          default:
            continue;
        }
      }
      else if ( gbDnsDomainSidCached )
      {
        v14 = RtlLengthSid(Src);
        memcpy_0(*v8, Src, v14);
        ++*((_BYTE *)*v8 + 1);
        v12 = *RtlSubAuthorityCountSid(Src);
        goto LABEL_21;
      }
    }
  }
  if ( gbLsaLookupSucceeded )
    gbLookupTableInitialized = 1;
LABEL_25:
  if ( fCSInitialized )
    LeaveCriticalSection(&SddlSidLookupCritical);
  else
    _InterlockedCompareExchange(&fWaitSddlLookup, 0, 1);
  return 1;
}

```

## disassembly

```asm
0x18001c890  push    rbp
0x18001c892  push    rbx
0x18001c893  push    r13
0x18001c895  mov     rbp, rsp
0x18001c898  sub     rsp, 70h
0x18001c89c  mov     rax, cs:__security_cookie
0x18001c8a3  xor     rax, rsp
0x18001c8a6  mov     [rbp+var_18], rax
0x18001c8aa  cmp     cs:fCSInitialized, 0
0x18001c8b1  mov     r13d, 1
0x18001c8b7  movzx   ebx, cl
0x18001c8ba  mov     dword ptr [rbp+var_48], 0
0x18001c8c1  mov     word ptr [rbp+var_48+4], 100h
0x18001c8c7  mov     dword ptr [rbp+var_40], 0
0x18001c8ce  mov     word ptr [rbp+var_40+4], 200h
0x18001c8d4  mov     dword ptr [rbp+var_38.Value], 0
0x18001c8db  mov     word ptr [rbp+var_38.Value+4], 300h
0x18001c8e1  mov     dword ptr [rbp+var_50], 0
0x18001c8e8  mov     word ptr [rbp+var_50+4], 500h
0x18001c8ee  mov     dword ptr [rbp+var_30.Value], 0
0x18001c8f5  mov     word ptr [rbp+var_30.Value+4], 1000h
0x18001c8fb  mov     dword ptr [rbp+var_28.Value], 0
0x18001c902  mov     word ptr [rbp+var_28.Value+4], 0F00h
0x18001c908  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x18001c90f  mov     word ptr [rbp+IdentifierAuthority.Value+4], 1200h
0x18001c915  jz      loc_18001CD83
0x18001c91b  lea     rcx, SddlSidLookupCritical; lpCriticalSection
0x18001c922  call    cs:__imp_EnterCriticalSection
0x18001c929  nop     dword ptr [rax+rax+00h]
0x18001c92e  mov     eax, ebx
0x18001c930  mov     [rsp+70h+var_10], r15
0x18001c935  sub     eax, r13d
0x18001c938  jz      short loc_18001C95E
0x18001c93a  cmp     eax, r13d
0x18001c93d  jnz     short loc_18001C982
0x18001c93f  mov     eax, cs:dword_1800B21C8
0x18001c945  xor     r15d, r15d
0x18001c948  cmp     eax, r13d
0x18001c94b  jbe     loc_18001CB88
0x18001c951  dec     eax
0x18001c953  mov     cs:dword_1800B21C8, eax
0x18001c959  jmp     loc_18001CAF1
0x18001c95e  mov     eax, cs:dword_1800B21C8
0x18001c964  inc     eax
0x18001c966  mov     cs:dword_1800B21C8, eax
0x18001c96c  cmp     eax, r13d
0x18001c96f  ja      loc_18001CB2E
0x18001c975  cmp     cs:gbLookupTableInitialized, r13d
0x18001c97c  jz      loc_18001CB2E
0x18001c982  mov     [rsp+70h+arg_0], rsi
0x18001c98a  mov     [rsp+70h+arg_8], rdi
0x18001c992  mov     [rsp+70h+arg_10], r12
0x18001c99a  mov     [rsp+70h+var_8], r14
0x18001c99f  call    CacheDomainAndDnsDomainSids
0x18001c9a4  xor     r15d, r15d
0x18001c9a7  lea     r12, __ImageBase
0x18001c9ae  mov     edi, r15d
0x18001c9b1  imul    rsi, rdi, 68h ; 'h'
0x18001c9b5  cmp     bl, r13b
0x18001c9b8  jnz     short loc_18001C9C2
0x18001c9ba  mov     [rsi+r12+0AEDD0h], r15b
0x18001c9c2  lea     r14, rva qword_1800AEDE0[r12]
0x18001c9ca  add     r14, rsi
0x18001c9cd  cmp     [rsi+r12+0AEDD0h], r13b
0x18001c9d5  jz      loc_18001CDB7
0x18001c9db  mov     eax, [rsi+r12+0AEDECh]
0x18001c9e3  lea     r9, rva qword_1800AEDF0[r12]
0x18001c9eb  add     r9, rsi
0x18001c9ee  mov     [r14], r9
0x18001c9f1  test    eax, eax
0x18001c9f3  jz      loc_18001CB35
0x18001c9f9  cmp     eax, 6
0x18001c9fc  jz      short loc_18001CA69
0x18001c9fe  cmp     eax, 5
0x18001ca01  jz      loc_18001CB90
0x18001ca07  dec     eax; switch 11 cases
0x18001ca09  cmp     eax, 0Ah
0x18001ca0c  ja      def_18001CA1F; jumptable 000000018001CA1F default case, cases 5-7
0x18001ca12  cdqe
0x18001ca14  mov     ecx, ds:(jpt_18001CA1F - 180000000h)[r12+rax*4]
0x18001ca1c  add     rcx, r12
0x18001ca1f  jmp     rcx; switch jump
0x18001ca25  movzx   r8d, r13b; jumptable 000000018001CA1F case 11
0x18001ca29  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x18001ca2d  mov     rcx, r9; Sid
0x18001ca30  call    cs:__imp_RtlInitializeSid
0x18001ca37  nop     dword ptr [rax+rax+00h]
0x18001ca3c  xor     edx, edx; SubAuthority
0x18001ca3e  mov     rcx, [r14]; Sid
0x18001ca41  call    cs:__imp_RtlSubAuthoritySid
0x18001ca48  nop     dword ptr [rax+rax+00h]
0x18001ca4d  imul    rcx, rdi, 68h ; 'h'
0x18001ca51  mov     ecx, [rcx+r12+0AEDE8h]
0x18001ca59  mov     [rax], ecx
0x18001ca5b  imul    rax, rdi, 68h ; 'h'
0x18001ca5f  mov     [rax+r12+0AEDD0h], r13b
0x18001ca67  jmp     short def_18001CA1F; jumptable 000000018001CA1F default case, cases 5-7
0x18001ca69  mov     r8b, 2; SubAuthorityCount
0x18001ca6c  lea     rdx, [rbp+var_50]; IdentifierAuthority
0x18001ca70  mov     rcx, r9; Sid
0x18001ca73  call    cs:__imp_RtlInitializeSid
0x18001ca7a  nop     dword ptr [rax+rax+00h]
0x18001ca7f  mov     rcx, [r14]; Sid
0x18001ca82  xor     edx, edx; SubAuthority
0x18001ca84  call    cs:__imp_RtlSubAuthoritySid
0x18001ca8b  nop     dword ptr [rax+rax+00h]
0x18001ca90  mov     edx, r13d; SubAuthority
0x18001ca93  mov     dword ptr [rax], 20h ; ' '
0x18001ca99  mov     rcx, [r14]; Sid
0x18001ca9c  call    cs:__imp_RtlSubAuthoritySid
0x18001caa3  nop     dword ptr [rax+rax+00h]
0x18001caa8  mov     ecx, [rsi+r12+0AEDE8h]
0x18001cab0  mov     [rax], ecx
0x18001cab2  mov     [rsi+r12+0AEDD0h], r13b
0x18001caba  inc     rdi; jumptable 000000018001CA1F default case, cases 5-7
0x18001cabd  cmp     rdi, 44h ; 'D'
0x18001cac1  jnz     loc_18001C9B1
0x18001cac7  cmp     cs:gbLsaLookupSucceeded, r15d
0x18001cace  mov     r14, [rsp+70h+var_8]
0x18001cad3  mov     r12, [rsp+70h+arg_10]
0x18001cadb  mov     rdi, [rsp+70h+arg_8]
0x18001cae3  mov     rsi, [rsp+70h+arg_0]
0x18001caeb  jnz     loc_18001CBAE
0x18001caf1  cmp     cs:fCSInitialized, r15d
0x18001caf8  jz      loc_18001CC9B
0x18001cafe  lea     rcx, SddlSidLookupCritical; lpCriticalSection
0x18001cb05  call    cs:__imp_LeaveCriticalSection
0x18001cb0c  nop     dword ptr [rax+rax+00h]
0x18001cb11  mov     r15, [rsp+70h+var_10]
0x18001cb16  mov     al, 1
0x18001cb18  mov     rcx, [rbp+var_18]
0x18001cb1c  xor     rcx, rsp; StackCookie
0x18001cb1f  call    __security_check_cookie
0x18001cb24  add     rsp, 70h
0x18001cb28  pop     r13
0x18001cb2a  pop     rbx
0x18001cb2b  pop     rbp
0x18001cb2c  retn
0x18001cb2e  call    LeaveWaitSddlSidLookup
0x18001cb33  jmp     short loc_18001CB11
0x18001cb35  cmp     cs:gbDnsDomainSidCached, r15d
0x18001cb3c  jz      def_18001CA1F; jumptable 000000018001CA1F default case, cases 5-7
0x18001cb42  mov     rcx, cs:Src; Sid
0x18001cb49  call    cs:__imp_RtlLengthSid
0x18001cb50  nop     dword ptr [rax+rax+00h]
0x18001cb55  mov     rdx, cs:Src; Src
0x18001cb5c  mov     rcx, [r14]; void *
0x18001cb5f  mov     r8d, eax; Size
0x18001cb62  call    memcpy_0
0x18001cb67  mov     rax, [r14]
0x18001cb6a  inc     byte ptr [rax+1]
0x18001cb6d  mov     rcx, cs:Src; Sid
0x18001cb74  call    cs:__imp_RtlSubAuthorityCountSid
0x18001cb7b  nop     dword ptr [rax+rax+00h]
0x18001cb80  movzx   edx, byte ptr [rax]
0x18001cb83  jmp     loc_18001CA99
0x18001cb88  mov     eax, r15d
0x18001cb8b  jmp     loc_18001C953
0x18001cb90  movzx   r8d, r13b; SubAuthorityCount
0x18001cb94  lea     rdx, [rbp+var_50]; IdentifierAuthority
0x18001cb98  mov     rcx, r9; Sid
0x18001cb9b  call    cs:__imp_RtlInitializeSid
0x18001cba2  nop     dword ptr [rax+rax+00h]
0x18001cba7  xor     edx, edx
0x18001cba9  jmp     loc_18001CA99
0x18001cbae  mov     cs:gbLookupTableInitialized, r13d
0x18001cbb5  jmp     loc_18001CAF1
0x18001cbba  movzx   r8d, r13b; jumptable 000000018001CA1F case 8
0x18001cbbe  lea     rdx, [rbp+var_30]; IdentifierAuthority
0x18001cbc2  mov     rcx, r9; Sid
0x18001cbc5  call    cs:__imp_RtlInitializeSid
0x18001cbcc  nop     dword ptr [rax+rax+00h]
0x18001cbd1  mov     rcx, [r14]; Sid
0x18001cbd4  xor     edx, edx; SubAuthority
0x18001cbd6  call    cs:__imp_RtlSubAuthoritySid
0x18001cbdd  nop     dword ptr [rax+rax+00h]
0x18001cbe2  imul    rcx, rdi, 68h ; 'h'
0x18001cbe6  mov     ecx, [rcx+r12+0AEDE8h]
0x18001cbee  mov     [rax], ecx
0x18001cbf0  imul    rax, rdi, 68h ; 'h'
0x18001cbf4  mov     [rax+r12+0AEDD0h], r13b
0x18001cbfc  jmp     def_18001CA1F; jumptable 000000018001CA1F default case, cases 5-7
0x18001cc01  cmp     cs:gbDomainSidCached, r15d; jumptable 000000018001CA1F case 3
0x18001cc08  jz      def_18001CA1F; jumptable 000000018001CA1F default case, cases 5-7
0x18001cc0e  mov     rcx, cs:Sid; Sid
0x18001cc15  call    cs:__imp_RtlLengthSid
0x18001cc1c  nop     dword ptr [rax+rax+00h]
0x18001cc21  mov     rdx, cs:Sid; Src
0x18001cc28  mov     rcx, [r14]; void *
0x18001cc2b  mov     r8d, eax; Size
0x18001cc2e  call    memcpy_0
0x18001cc33  mov     rax, [r14]
0x18001cc36  inc     byte ptr [rax+1]
0x18001cc39  mov     rcx, cs:Sid; Sid
0x18001cc40  call    cs:__imp_RtlSubAuthorityCountSid
0x18001cc47  nop     dword ptr [rax+rax+00h]
0x18001cc4c  movzx   edx, byte ptr [rax]
0x18001cc4f  jmp     loc_18001CA3E
0x18001cc54  movzx   r8d, r13b; jumptable 000000018001CA1F case 4
0x18001cc58  lea     rdx, [rbp+var_38]; IdentifierAuthority
0x18001cc5c  mov     rcx, r9; Sid
0x18001cc5f  call    cs:__imp_RtlInitializeSid
0x18001cc66  nop     dword ptr [rax+rax+00h]
0x18001cc6b  mov     rcx, [r14]; Sid
0x18001cc6e  xor     edx, edx; SubAuthority
0x18001cc70  call    cs:__imp_RtlSubAuthoritySid
0x18001cc77  nop     dword ptr [rax+rax+00h]
0x18001cc7c  imul    rcx, rdi, 68h ; 'h'
0x18001cc80  mov     ecx, [rcx+r12+0AEDE8h]
0x18001cc88  mov     [rax], ecx
0x18001cc8a  imul    rax, rdi, 68h ; 'h'
0x18001cc8e  mov     [rax+r12+0AEDD0h], r13b
0x18001cc96  jmp     def_18001CA1F; jumptable 000000018001CA1F default case, cases 5-7
0x18001cc9b  mov     eax, r13d
0x18001cc9e  lock cmpxchg cs:fWaitSddlLookup, r15d
0x18001cca7  jmp     loc_18001CB11
0x18001ccac  movzx   r8d, r13b; jumptable 000000018001CA1F case 1
0x18001ccb0  lea     rdx, [rbp+var_48]; IdentifierAuthority
0x18001ccb4  mov     rcx, r9; Sid
0x18001ccb7  call    cs:__imp_RtlInitializeSid
0x18001ccbe  nop     dword ptr [rax+rax+00h]
0x18001ccc3  mov     rcx, [r14]; Sid
0x18001ccc6  xor     edx, edx; SubAuthority
0x18001ccc8  call    cs:__imp_RtlSubAuthoritySid
0x18001cccf  nop     dword ptr [rax+rax+00h]
0x18001ccd4  imul    rcx, rdi, 68h ; 'h'
0x18001ccd8  mov     ecx, [rcx+r12+0AEDE8h]
0x18001cce0  mov     [rax], ecx
0x18001cce2  imul    rax, rdi, 68h ; 'h'
0x18001cce6  mov     [rax+r12+0AEDD0h], r13b
0x18001ccee  jmp     def_18001CA1F; jumptable 000000018001CA1F default case, cases 5-7
0x18001ccf3  mov     r8b, 2; jumptable 000000018001CA1F case 9
0x18001ccf6  lea     rdx, [rbp+var_28]; IdentifierAuthority
0x18001ccfa  mov     rcx, r9; Sid
0x18001ccfd  call    cs:__imp_RtlInitializeSid
0x18001cd04  nop     dword ptr [rax+rax+00h]
0x18001cd09  mov     rcx, [r14]; Sid
0x18001cd0c  xor     edx, edx; SubAuthority
0x18001cd0e  call    cs:__imp_RtlSubAuthoritySid
0x18001cd15  nop     dword ptr [rax+rax+00h]
0x18001cd1a  mov     edx, r13d
0x18001cd1d  mov     dword ptr [rax], 2
0x18001cd23  jmp     loc_18001CA3E
0x18001cd28  mov     r8b, 6; jumptable 000000018001CA1F case 10
0x18001cd2b  lea     rdx, [rbp+var_50]; IdentifierAuthority
0x18001cd2f  mov     rcx, r9; Sid
0x18001cd32  call    cs:__imp_RtlInitializeSid
0x18001cd39  nop     dword ptr [rax+rax+00h]
0x18001cd3e  mov     rcx, [r14]; Sid
0x18001cd41  xor     edx, edx; SubAuthority
0x18001cd43  call    cs:__imp_RtlSubAuthoritySid
0x18001cd4a  nop     dword ptr [rax+rax+00h]
0x18001cd4f  mov     edx, r13d; SubAuthority
0x18001cd52  mov     dword ptr [rax], 54h ; 'T'
0x18001cd58  mov     rcx, [r14]; Sid
0x18001cd5b  call    cs:__imp_RtlSubAuthoritySid
0x18001cd62  nop     dword ptr [rax+rax+00h]
0x18001cd67  xor     ecx, ecx
0x18001cd69  xorps   xmm0, xmm0
0x18001cd6c  movups  xmmword ptr [rax], xmm0
0x18001cd6f  mov     [rax+10h], ecx
0x18001cd72  imul    rax, rdi, 68h ; 'h'
0x18001cd76  mov     [rax+r12+0AEDD0h], r13b
0x18001cd7e  jmp     def_18001CA1F; jumptable 000000018001CA1F default case, cases 5-7
0x18001cd83  xor     eax, eax
0x18001cd85  lock cmpxchg cs:fWaitSddlLookup, r13d
0x18001cd8e  jz      loc_18001C92E
0x18001cd94  mov     ecx, 0Ah; dwMilliseconds
0x18001cd99  call    cs:__imp_Sleep
0x18001cda0  nop     dword ptr [rax+rax+00h]
0x18001cda5  xor     eax, eax
0x18001cda7  lock cmpxchg cs:fWaitSddlLookup, r13d
0x18001cdb0  jnz     short loc_18001CD94
0x18001cdb2  jmp     loc_18001C92E
0x18001cdb7  cmp     [r14], r15
0x18001cdba  jnz     def_18001CA1F; jumptable 000000018001CA1F default case, cases 5-7
0x18001cdc0  jmp     loc_18001C9DB
0x18001cdc5  movzx   r8d, r13b; jumptable 000000018001CA1F case 2
0x18001cdc9  lea     rdx, [rbp+var_40]; IdentifierAuthority
0x18001cdcd  mov     rcx, r9; Sid
0x18001cdd0  call    cs:__imp_RtlInitializeSid
0x18001cdd7  nop     dword ptr [rax+rax+00h]
0x18001cddc  mov     rcx, [r14]; Sid
0x18001cddf  xor     edx, edx; SubAuthority
0x18001cde1  call    cs:__imp_RtlSubAuthoritySid
0x18001cde8  nop     dword ptr [rax+rax+00h]
0x18001cded  imul    rcx, rdi, 68h ; 'h'
0x18001cdf1  mov     ecx, [rcx+r12+0AEDE8h]
0x18001cdf9  mov     [rax], ecx
0x18001cdfb  imul    rax, rdi, 68h ; 'h'
0x18001cdff  mov     [rax+r12+0AEDD0h], r13b
0x18001ce07  jmp     def_18001CA1F; jumptable 000000018001CA1F default case, cases 5-7
```
