# InitializeSidLookupTable

- ea: `0x18001dbb0`
- end: `0x18001e0b4`
- name: `InitializeSidLookupTable`
- size: `1284`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001cbbc`
- `0x18001d3d0`
- `0x18001e218`

## callees

- `0x18001dbb0`
- `0x18001e0bc`
- `0x18001ea50`
- `0x180065042`
- `0x180065090`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18001de5b`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001df09`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001de5b`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001df09`
- `ntdll!RtlLengthSid` at `0x18001de36`
- `ntdll!RtlLengthSid` at `0x18001dee4`
- `ntdll!RtlLengthSid` at `0x18001de36`
- `ntdll!RtlLengthSid` at `0x18001dee4`
- `ntdll!RtlInitializeSid` at `0x18001dd46`
- `ntdll!RtlInitializeSid` at `0x18001dd7d`
- `ntdll!RtlInitializeSid` at `0x18001de7c`
- `ntdll!RtlInitializeSid` at `0x18001dea0`
- `ntdll!RtlInitializeSid` at `0x18001df22`
- `ntdll!RtlInitializeSid` at `0x18001df6e`
- `ntdll!RtlInitializeSid` at `0x18001dfa8`
- `ntdll!RtlInitializeSid` at `0x18001dfd1`
- `ntdll!RtlInitializeSid` at `0x18001e057`
- `ntdll!RtlInitializeSid` at `0x18001dd46`
- `ntdll!RtlInitializeSid` at `0x18001dd7d`
- `ntdll!RtlInitializeSid` at `0x18001de7c`
- `ntdll!RtlInitializeSid` at `0x18001dea0`
- `ntdll!RtlInitializeSid` at `0x18001df22`
- `ntdll!RtlInitializeSid` at `0x18001df6e`
- `ntdll!RtlInitializeSid` at `0x18001dfa8`
- `ntdll!RtlInitializeSid` at `0x18001dfd1`
- `ntdll!RtlInitializeSid` at `0x18001e057`
- `ntdll!RtlSubAuthoritySid` at `0x18001dd51`
- `ntdll!RtlSubAuthoritySid` at `0x18001dd88`
- `ntdll!RtlSubAuthoritySid` at `0x18001dd9a`
- `ntdll!RtlSubAuthoritySid` at `0x18001deab`
- `ntdll!RtlSubAuthoritySid` at `0x18001df2d`
- `ntdll!RtlSubAuthoritySid` at `0x18001df79`
- `ntdll!RtlSubAuthoritySid` at `0x18001dfb3`
- `ntdll!RtlSubAuthoritySid` at `0x18001dfdc`
- `ntdll!RtlSubAuthoritySid` at `0x18001dfee`
- `ntdll!RtlSubAuthoritySid` at `0x18001e062`
- `ntdll!RtlSubAuthoritySid` at `0x18001dd51`
- `ntdll!RtlSubAuthoritySid` at `0x18001dd88`
- `ntdll!RtlSubAuthoritySid` at `0x18001dd9a`
- `ntdll!RtlSubAuthoritySid` at `0x18001deab`
- `ntdll!RtlSubAuthoritySid` at `0x18001df2d`
- `ntdll!RtlSubAuthoritySid` at `0x18001df79`
- `ntdll!RtlSubAuthoritySid` at `0x18001dfb3`
- `ntdll!RtlSubAuthoritySid` at `0x18001dfdc`
- `ntdll!RtlSubAuthoritySid` at `0x18001dfee`
- `ntdll!RtlSubAuthoritySid` at `0x18001e062`
- `KERNELBASE!Sleep` at `0x18001e026`
- `KERNELBASE!Sleep` at `0x18001e026`
- `KERNEL32!EnterCriticalSection` at `0x18001dc42`
- `KERNEL32!EnterCriticalSection` at `0x18001dc42`
- `KERNEL32!LeaveCriticalSection` at `0x18001ddfd`
- `KERNEL32!LeaveCriticalSection` at `0x18001ddfd`

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
    if ( (unsigned int)++dword_1800A3080 > 1 || gbLookupTableInitialized == 1 )
    {
      LeaveWaitSddlSidLookup(a1, a2, a3, a4, v18, v19, v20);
      return 1;
    }
  }
  else if ( v4 == 2 )
  {
    if ( (unsigned int)dword_1800A3080 <= 1 )
      v5 = 0;
    else
      v5 = dword_1800A3080 - 1;
    dword_1800A3080 = v5;
    goto LABEL_25;
  }
  CacheDomainAndDnsDomainSids(a1, a2, a3, a4, v18, v19, v20);
  for ( i = 0; i != 68; ++i )
  {
    v7 = 13 * i;
    if ( (_BYTE)v4 == 1 )
      LOBYTE(qword_18009FDE0[v7]) = 0;
    v8 = (PSID *)&qword_18009FDF0[v7];
    if ( LOBYTE(qword_18009FDE0[v7]) != 1 || !*v8 )
    {
      v9 = HIDWORD(qword_18009FDF8[v7]);
      *v8 = &qword_18009FE00[v7];
      if ( v9 )
      {
        if ( v9 == 6 )
        {
          RtlInitializeSid(&qword_18009FE00[v7], (PSID_IDENTIFIER_AUTHORITY)&v18, 2u);
          v11 = RtlSubAuthoritySid(*v8, 0);
          v12 = 1;
          *v11 = 32;
LABEL_21:
          *RtlSubAuthoritySid(*v8, v12) = qword_18009FDF8[v7];
          LOBYTE(qword_18009FDE0[v7]) = 1;
          continue;
        }
        if ( v9 == 5 )
        {
          RtlInitializeSid(&qword_18009FE00[v7], (PSID_IDENTIFIER_AUTHORITY)&v18, 1u);
          v12 = 0;
          goto LABEL_21;
        }
        switch ( v9 )
        {
          case 1:
            RtlInitializeSid(&qword_18009FE00[v7], (PSID_IDENTIFIER_AUTHORITY)&v19, 1u);
            *RtlSubAuthoritySid(*v8, 0) = qword_18009FDF8[13 * i];
            LOBYTE(qword_18009FDE0[13 * i]) = 1;
            break;
          case 2:
            RtlInitializeSid(&qword_18009FE00[v7], (PSID_IDENTIFIER_AUTHORITY)&v20, 1u);
            *RtlSubAuthoritySid(*v8, 0) = qword_18009FDF8[13 * i];
            LOBYTE(qword_18009FDE0[13 * i]) = 1;
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
            RtlInitializeSid(&qword_18009FE00[v7], &v21, 1u);
            *RtlSubAuthoritySid(*v8, 0) = qword_18009FDF8[13 * i];
            LOBYTE(qword_18009FDE0[13 * i]) = 1;
            break;
          case 8:
            RtlInitializeSid(&qword_18009FE00[v7], &v22, 1u);
            *RtlSubAuthoritySid(*v8, 0) = qword_18009FDF8[13 * i];
            LOBYTE(qword_18009FDE0[13 * i]) = 1;
            break;
          case 9:
            RtlInitializeSid(&qword_18009FE00[v7], &v23, 2u);
            v16 = RtlSubAuthoritySid(*v8, 0);
            v10 = 1;
            *v16 = 2;
            goto LABEL_19;
          case 10:
            RtlInitializeSid(&qword_18009FE00[v7], (PSID_IDENTIFIER_AUTHORITY)&v18, 6u);
            *RtlSubAuthoritySid(*v8, 0) = 84;
            v17 = RtlSubAuthoritySid(*v8, 1u);
            *(_OWORD *)v17 = 0;
            v17[4] = 0;
            LOBYTE(qword_18009FDE0[13 * i]) = 1;
            break;
          case 11:
            RtlInitializeSid(&qword_18009FE00[v7], &IdentifierAuthority, 1u);
            v10 = 0;
LABEL_19:
            *RtlSubAuthoritySid(*v8, v10) = qword_18009FDF8[13 * i];
            LOBYTE(qword_18009FDE0[13 * i]) = 1;
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
0x18001dbb0  push    rbp
0x18001dbb2  push    rbx
0x18001dbb3  push    r13
0x18001dbb5  mov     rbp, rsp
0x18001dbb8  sub     rsp, 70h
0x18001dbbc  mov     rax, cs:__security_cookie
0x18001dbc3  xor     rax, rsp
0x18001dbc6  mov     [rbp+var_18], rax
0x18001dbca  cmp     cs:fCSInitialized, 0
0x18001dbd1  mov     r13d, 1
0x18001dbd7  movzx   ebx, cl
0x18001dbda  mov     dword ptr [rbp+var_48], 0
0x18001dbe1  mov     word ptr [rbp+var_48+4], 100h
0x18001dbe7  mov     dword ptr [rbp+var_40], 0
0x18001dbee  mov     word ptr [rbp+var_40+4], 200h
0x18001dbf4  mov     dword ptr [rbp+var_38.Value], 0
0x18001dbfb  mov     word ptr [rbp+var_38.Value+4], 300h
0x18001dc01  mov     dword ptr [rbp+var_50], 0
0x18001dc08  mov     word ptr [rbp+var_50+4], 500h
0x18001dc0e  mov     dword ptr [rbp+var_30.Value], 0
0x18001dc15  mov     word ptr [rbp+var_30.Value+4], 1000h
0x18001dc1b  mov     dword ptr [rbp+var_28.Value], 0
0x18001dc22  mov     word ptr [rbp+var_28.Value+4], 0F00h
0x18001dc28  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x18001dc2f  mov     word ptr [rbp+IdentifierAuthority.Value+4], 1200h
0x18001dc35  jz      loc_18001E010
0x18001dc3b  lea     rcx, SddlSidLookupCritical; lpCriticalSection
0x18001dc42  call    cs:__imp_EnterCriticalSection
0x18001dc48  mov     eax, ebx
0x18001dc4a  mov     [rsp+70h+var_10], r15
0x18001dc4f  sub     eax, r13d
0x18001dc52  jz      short loc_18001DC78
0x18001dc54  cmp     eax, r13d
0x18001dc57  jnz     short loc_18001DC9C
0x18001dc59  mov     eax, cs:dword_1800A3080
0x18001dc5f  xor     r15d, r15d
0x18001dc62  cmp     eax, r13d
0x18001dc65  jbe     loc_18001DE69
0x18001dc6b  dec     eax
0x18001dc6d  mov     cs:dword_1800A3080, eax
0x18001dc73  jmp     loc_18001DDE9
0x18001dc78  mov     eax, cs:dword_1800A3080
0x18001dc7e  inc     eax
0x18001dc80  mov     cs:dword_1800A3080, eax
0x18001dc86  cmp     eax, r13d
0x18001dc89  ja      loc_18001DE1F
0x18001dc8f  cmp     cs:gbLookupTableInitialized, r13d
0x18001dc96  jz      loc_18001DE1F
0x18001dc9c  mov     [rsp+70h+arg_0], rsi
0x18001dca4  mov     [rsp+70h+arg_8], rdi
0x18001dcac  mov     [rsp+70h+arg_10], r12
0x18001dcb4  mov     [rsp+70h+var_8], r14
0x18001dcb9  call    CacheDomainAndDnsDomainSids
0x18001dcbe  xor     r15d, r15d
0x18001dcc1  lea     r12, __ImageBase
0x18001dcc8  mov     edi, r15d
0x18001dccb  imul    rsi, rdi, 68h ; 'h'
0x18001dccf  cmp     bl, r13b
0x18001dcd2  jnz     short loc_18001DCDC
0x18001dcd4  mov     [rsi+r12+9FDE0h], r15b
0x18001dcdc  lea     r14, rva qword_18009FDF0[r12]
0x18001dce4  add     r14, rsi
0x18001dce7  cmp     [rsi+r12+9FDE0h], r13b
0x18001dcef  jz      loc_18001E03E
0x18001dcf5  mov     eax, [rsi+r12+9FDFCh]
0x18001dcfd  lea     r9, rva qword_18009FE00[r12]
0x18001dd05  add     r9, rsi
0x18001dd08  mov     [r14], r9
0x18001dd0b  test    eax, eax
0x18001dd0d  jz      loc_18001DE26
0x18001dd13  cmp     eax, 6
0x18001dd16  jz      short loc_18001DD73
0x18001dd18  cmp     eax, 5
0x18001dd1b  jz      loc_18001DE71
0x18001dd21  dec     eax; switch 11 cases
0x18001dd23  cmp     eax, 0Ah
0x18001dd26  ja      def_18001DD39; jumptable 000000018001DD39 default case, cases 5-7
0x18001dd2c  cdqe
0x18001dd2e  mov     ecx, ds:(jpt_18001DD39 - 180000000h)[r12+rax*4]
0x18001dd36  add     rcx, r12
0x18001dd39  jmp     rcx; switch jump
0x18001dd3b  movzx   r8d, r13b; jumptable 000000018001DD39 case 11
0x18001dd3f  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x18001dd43  mov     rcx, r9; Sid
0x18001dd46  call    cs:__imp_RtlInitializeSid
0x18001dd4c  xor     edx, edx; SubAuthority
0x18001dd4e  mov     rcx, [r14]; Sid
0x18001dd51  call    cs:__imp_RtlSubAuthoritySid
0x18001dd57  imul    rcx, rdi, 68h ; 'h'
0x18001dd5b  mov     ecx, [rcx+r12+9FDF8h]
0x18001dd63  mov     [rax], ecx
0x18001dd65  imul    rax, rdi, 68h ; 'h'
0x18001dd69  mov     [rax+r12+9FDE0h], r13b
0x18001dd71  jmp     short def_18001DD39; jumptable 000000018001DD39 default case, cases 5-7
0x18001dd73  mov     r8b, 2; SubAuthorityCount
0x18001dd76  lea     rdx, [rbp+var_50]; IdentifierAuthority
0x18001dd7a  mov     rcx, r9; Sid
0x18001dd7d  call    cs:__imp_RtlInitializeSid
0x18001dd83  mov     rcx, [r14]; Sid
0x18001dd86  xor     edx, edx; SubAuthority
0x18001dd88  call    cs:__imp_RtlSubAuthoritySid
0x18001dd8e  mov     edx, r13d; SubAuthority
0x18001dd91  mov     dword ptr [rax], 20h ; ' '
0x18001dd97  mov     rcx, [r14]; Sid
0x18001dd9a  call    cs:__imp_RtlSubAuthoritySid
0x18001dda0  mov     ecx, [rsi+r12+9FDF8h]
0x18001dda8  mov     [rax], ecx
0x18001ddaa  mov     [rsi+r12+9FDE0h], r13b
0x18001ddb2  inc     rdi; jumptable 000000018001DD39 default case, cases 5-7
0x18001ddb5  cmp     rdi, 44h ; 'D'
0x18001ddb9  jnz     loc_18001DCCB
0x18001ddbf  cmp     cs:gbLsaLookupSucceeded, r15d
0x18001ddc6  mov     r14, [rsp+70h+var_8]
0x18001ddcb  mov     r12, [rsp+70h+arg_10]
0x18001ddd3  mov     rdi, [rsp+70h+arg_8]
0x18001dddb  mov     rsi, [rsp+70h+arg_0]
0x18001dde3  jnz     loc_18001DE89
0x18001dde9  cmp     cs:fCSInitialized, r15d
0x18001ddf0  jz      loc_18001DF52
0x18001ddf6  lea     rcx, SddlSidLookupCritical; lpCriticalSection
0x18001ddfd  call    cs:__imp_LeaveCriticalSection
0x18001de03  mov     r15, [rsp+70h+var_10]
0x18001de08  mov     al, 1
0x18001de0a  mov     rcx, [rbp+var_18]
0x18001de0e  xor     rcx, rsp; StackCookie
0x18001de11  call    __security_check_cookie
0x18001de16  add     rsp, 70h
0x18001de1a  pop     r13
0x18001de1c  pop     rbx
0x18001de1d  pop     rbp
0x18001de1e  retn
0x18001de1f  call    LeaveWaitSddlSidLookup
0x18001de24  jmp     short loc_18001DE03
0x18001de26  cmp     cs:gbDnsDomainSidCached, r15d
0x18001de2d  jz      short def_18001DD39; jumptable 000000018001DD39 default case, cases 5-7
0x18001de2f  mov     rcx, cs:Src; Sid
0x18001de36  call    cs:__imp_RtlLengthSid
0x18001de3c  mov     rdx, cs:Src; Src
0x18001de43  mov     rcx, [r14]; void *
0x18001de46  mov     r8d, eax; Size
0x18001de49  call    memcpy_0
0x18001de4e  mov     rax, [r14]
0x18001de51  inc     byte ptr [rax+1]
0x18001de54  mov     rcx, cs:Src; Sid
0x18001de5b  call    cs:__imp_RtlSubAuthorityCountSid
0x18001de61  movzx   edx, byte ptr [rax]
0x18001de64  jmp     loc_18001DD97
0x18001de69  mov     eax, r15d
0x18001de6c  jmp     loc_18001DC6D
0x18001de71  movzx   r8d, r13b; SubAuthorityCount
0x18001de75  lea     rdx, [rbp+var_50]; IdentifierAuthority
0x18001de79  mov     rcx, r9; Sid
0x18001de7c  call    cs:__imp_RtlInitializeSid
0x18001de82  xor     edx, edx
0x18001de84  jmp     loc_18001DD97
0x18001de89  mov     cs:gbLookupTableInitialized, r13d
0x18001de90  jmp     loc_18001DDE9
0x18001de95  movzx   r8d, r13b; jumptable 000000018001DD39 case 8
0x18001de99  lea     rdx, [rbp+var_30]; IdentifierAuthority
0x18001de9d  mov     rcx, r9; Sid
0x18001dea0  call    cs:__imp_RtlInitializeSid
0x18001dea6  mov     rcx, [r14]; Sid
0x18001dea9  xor     edx, edx; SubAuthority
0x18001deab  call    cs:__imp_RtlSubAuthoritySid
0x18001deb1  imul    rcx, rdi, 68h ; 'h'
0x18001deb5  mov     ecx, [rcx+r12+9FDF8h]
0x18001debd  mov     [rax], ecx
0x18001debf  imul    rax, rdi, 68h ; 'h'
0x18001dec3  mov     [rax+r12+9FDE0h], r13b
0x18001decb  jmp     def_18001DD39; jumptable 000000018001DD39 default case, cases 5-7
0x18001ded0  cmp     cs:gbDomainSidCached, r15d; jumptable 000000018001DD39 case 3
0x18001ded7  jz      def_18001DD39; jumptable 000000018001DD39 default case, cases 5-7
0x18001dedd  mov     rcx, cs:Sid; Sid
0x18001dee4  call    cs:__imp_RtlLengthSid
0x18001deea  mov     rdx, cs:Sid; Src
0x18001def1  mov     rcx, [r14]; void *
0x18001def4  mov     r8d, eax; Size
0x18001def7  call    memcpy_0
0x18001defc  mov     rax, [r14]
0x18001deff  inc     byte ptr [rax+1]
0x18001df02  mov     rcx, cs:Sid; Sid
0x18001df09  call    cs:__imp_RtlSubAuthorityCountSid
0x18001df0f  movzx   edx, byte ptr [rax]
0x18001df12  jmp     loc_18001DD4E
0x18001df17  movzx   r8d, r13b; jumptable 000000018001DD39 case 4
0x18001df1b  lea     rdx, [rbp+var_38]; IdentifierAuthority
0x18001df1f  mov     rcx, r9; Sid
0x18001df22  call    cs:__imp_RtlInitializeSid
0x18001df28  mov     rcx, [r14]; Sid
0x18001df2b  xor     edx, edx; SubAuthority
0x18001df2d  call    cs:__imp_RtlSubAuthoritySid
0x18001df33  imul    rcx, rdi, 68h ; 'h'
0x18001df37  mov     ecx, [rcx+r12+9FDF8h]
0x18001df3f  mov     [rax], ecx
0x18001df41  imul    rax, rdi, 68h ; 'h'
0x18001df45  mov     [rax+r12+9FDE0h], r13b
0x18001df4d  jmp     def_18001DD39; jumptable 000000018001DD39 default case, cases 5-7
0x18001df52  mov     eax, r13d
0x18001df55  lock cmpxchg cs:fWaitSddlLookup, r15d
0x18001df5e  jmp     loc_18001DE03
0x18001df63  movzx   r8d, r13b; jumptable 000000018001DD39 case 1
0x18001df67  lea     rdx, [rbp+var_48]; IdentifierAuthority
0x18001df6b  mov     rcx, r9; Sid
0x18001df6e  call    cs:__imp_RtlInitializeSid
0x18001df74  mov     rcx, [r14]; Sid
0x18001df77  xor     edx, edx; SubAuthority
0x18001df79  call    cs:__imp_RtlSubAuthoritySid
0x18001df7f  imul    rcx, rdi, 68h ; 'h'
0x18001df83  mov     ecx, [rcx+r12+9FDF8h]
0x18001df8b  mov     [rax], ecx
0x18001df8d  imul    rax, rdi, 68h ; 'h'
0x18001df91  mov     [rax+r12+9FDE0h], r13b
0x18001df99  jmp     def_18001DD39; jumptable 000000018001DD39 default case, cases 5-7
0x18001df9e  mov     r8b, 2; jumptable 000000018001DD39 case 9
0x18001dfa1  lea     rdx, [rbp+var_28]; IdentifierAuthority
0x18001dfa5  mov     rcx, r9; Sid
0x18001dfa8  call    cs:__imp_RtlInitializeSid
0x18001dfae  mov     rcx, [r14]; Sid
0x18001dfb1  xor     edx, edx; SubAuthority
0x18001dfb3  call    cs:__imp_RtlSubAuthoritySid
0x18001dfb9  mov     edx, r13d
0x18001dfbc  mov     dword ptr [rax], 2
0x18001dfc2  jmp     loc_18001DD4E
0x18001dfc7  mov     r8b, 6; jumptable 000000018001DD39 case 10
0x18001dfca  lea     rdx, [rbp+var_50]; IdentifierAuthority
0x18001dfce  mov     rcx, r9; Sid
0x18001dfd1  call    cs:__imp_RtlInitializeSid
0x18001dfd7  mov     rcx, [r14]; Sid
0x18001dfda  xor     edx, edx; SubAuthority
0x18001dfdc  call    cs:__imp_RtlSubAuthoritySid
0x18001dfe2  mov     edx, r13d; SubAuthority
0x18001dfe5  mov     dword ptr [rax], 54h ; 'T'
0x18001dfeb  mov     rcx, [r14]; Sid
0x18001dfee  call    cs:__imp_RtlSubAuthoritySid
0x18001dff4  xor     ecx, ecx
0x18001dff6  xorps   xmm0, xmm0
0x18001dff9  movups  xmmword ptr [rax], xmm0
0x18001dffc  mov     [rax+10h], ecx
0x18001dfff  imul    rax, rdi, 68h ; 'h'
0x18001e003  mov     [rax+r12+9FDE0h], r13b
0x18001e00b  jmp     def_18001DD39; jumptable 000000018001DD39 default case, cases 5-7
0x18001e010  xor     eax, eax
0x18001e012  lock cmpxchg cs:fWaitSddlLookup, r13d
0x18001e01b  jz      loc_18001DC48
0x18001e021  mov     ecx, 0Ah; dwMilliseconds
0x18001e026  call    cs:__imp_Sleep
0x18001e02c  xor     eax, eax
0x18001e02e  lock cmpxchg cs:fWaitSddlLookup, r13d
0x18001e037  jnz     short loc_18001E021
0x18001e039  jmp     loc_18001DC48
0x18001e03e  cmp     [r14], r15
0x18001e041  jnz     def_18001DD39; jumptable 000000018001DD39 default case, cases 5-7
0x18001e047  jmp     loc_18001DCF5
0x18001e04c  movzx   r8d, r13b; jumptable 000000018001DD39 case 2
0x18001e050  lea     rdx, [rbp+var_40]; IdentifierAuthority
0x18001e054  mov     rcx, r9; Sid
0x18001e057  call    cs:__imp_RtlInitializeSid
0x18001e05d  mov     rcx, [r14]; Sid
0x18001e060  xor     edx, edx; SubAuthority
0x18001e062  call    cs:__imp_RtlSubAuthoritySid
0x18001e068  imul    rcx, rdi, 68h ; 'h'
0x18001e06c  mov     ecx, [rcx+r12+9FDF8h]
0x18001e074  mov     [rax], ecx
0x18001e076  imul    rax, rdi, 68h ; 'h'
0x18001e07a  mov     [rax+r12+9FDE0h], r13b
0x18001e082  jmp     def_18001DD39; jumptable 000000018001DD39 default case, cases 5-7
```
