# IsWellKnownSid

- ea: `0x180031200`
- end: `0x1800314e1`
- name: `IsWellKnownSid`
- size: `737`
- prototype: `BOOL __stdcall(PSID pSid, WELL_KNOWN_SID_TYPE WellKnownSidType)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800314f0`

## callees

- `0x180031200`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18003128e`
- `ntdll!RtlSubAuthoritySid` at `0x180031304`
- `ntdll!RtlSubAuthoritySid` at `0x1800313bc`
- `ntdll!RtlSubAuthoritySid` at `0x18018d5ce`
- `ntdll!RtlSubAuthoritySid` at `0x18018d5e5`
- `ntdll!RtlSubAuthoritySid` at `0x18018d5fc`
- `ntdll!RtlSubAuthoritySid` at `0x18018d613`
- `ntdll!RtlSubAuthoritySid` at `0x18018d62a`
- `ntdll!RtlSubAuthoritySid` at `0x18003128e`
- `ntdll!RtlSubAuthoritySid` at `0x180031304`
- `ntdll!RtlSubAuthoritySid` at `0x1800313bc`
- `ntdll!RtlSubAuthoritySid` at `0x18018d5ce`
- `ntdll!RtlSubAuthoritySid` at `0x18018d5e5`
- `ntdll!RtlSubAuthoritySid` at `0x18018d5fc`
- `ntdll!RtlSubAuthoritySid` at `0x18018d613`
- `ntdll!RtlSubAuthoritySid` at `0x18018d62a`
- `ntdll!RtlSetLastWin32Error` at `0x18003121f`
- `ntdll!RtlSetLastWin32Error` at `0x18003121f`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003124c`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003124c`
- `ntdll!RtlValidSid` at `0x18003120f`
- `ntdll!RtlValidSid` at `0x18003120f`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180031228`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180031228`

## pseudocode

```c
BOOL __stdcall IsWellKnownSid(PSID pSid, WELL_KNOWN_SID_TYPE WellKnownSidType)
{
  PSID_IDENTIFIER_AUTHORITY v4; // rbx
  int v5; // ebp
  int v6; // ecx
  ULONG v7; // ecx
  BOOL v8; // r14d
  __int64 *v10; // rdi
  unsigned int v11; // ebx
  ULONG v12; // r8d
  __int64 j; // rax
  int v14; // eax
  __int64 i; // rdx
  __int64 v16; // r8
  int v17; // ecx
  int v18; // ecx
  ULONG v19; // ecx
  int v20; // ecx
  int v21; // ecx

  if ( RtlValidSid(pSid) )
  {
    RtlSetLastWin32Error(0);
    v4 = RtlIdentifierAuthoritySid(pSid);
    if ( v4 )
    {
      v5 = *RtlSubAuthorityCountSid(pSid);
      if ( !(_BYTE)v5 )
      {
        v21 = *(_DWORD *)v4->Value;
        if ( !*(_DWORD *)v4->Value )
          v21 = *(unsigned __int16 *)&v4->Value[4] - 1280;
        if ( !v21 )
        {
          v14 = 7;
          v8 = 1;
          goto LABEL_24;
        }
        return 0;
      }
      if ( (_BYTE)v5 == 1 )
      {
        for ( i = 0; (unsigned int)i < 0xD; i = (unsigned int)(i + 1) )
        {
          v16 = 3 * i;
          v17 = *(_DWORD *)v4->Value - LODWORD(KnownAuthoritiesAndDomains[3 * i]);
          if ( *(_DWORD *)v4->Value == LODWORD(KnownAuthoritiesAndDomains[3 * i]) )
            v17 = *(unsigned __int16 *)&v4->Value[4] - WORD2(KnownAuthoritiesAndDomains[v16]);
          if ( !v17 )
          {
            _mm_lfence();
            v10 = (__int64 *)KnownAuthoritiesAndDomains[v16 + 1];
            if ( v10 )
            {
              v11 = KnownAuthoritiesAndDomains[v16 + 2];
              goto LABEL_18;
            }
            break;
          }
        }
        v20 = *(_DWORD *)v4->Value;
        if ( !*(_DWORD *)v4->Value )
          v20 = *(unsigned __int16 *)&v4->Value[4] - 4096;
        if ( v20 )
          return 0;
        v10 = SecurityMandatorySids;
        v11 = 6;
        if ( !SecurityMandatorySids )
          return 0;
      }
      else
      {
        v6 = *(_DWORD *)v4->Value;
        if ( !*(_DWORD *)v4->Value )
          v6 = *(unsigned __int16 *)&v4->Value[4] - 1280;
        if ( v6 )
        {
          v18 = *(_DWORD *)v4->Value;
          if ( !*(_DWORD *)v4->Value )
            v18 = *(unsigned __int16 *)&v4->Value[4] - 3840;
          if ( v18 )
            return 0;
          v19 = *RtlSubAuthoritySid(pSid, 0);
          if ( v19 == 2 )
          {
            if ( (_BYTE)v5 != 2 )
              return 0;
            v8 = 1;
            v10 = ApplicationPackageTypeSids;
            v11 = 1;
            goto LABEL_19;
          }
          if ( (_BYTE)v5 != 2 || v19 != 3 )
            return 0;
          v10 = ApplicationCapabilityTypeSids;
          v11 = 12;
        }
        else
        {
          v7 = *RtlSubAuthoritySid(pSid, 0);
          switch ( v7 )
          {
            case 0x20u:
              if ( (_BYTE)v5 != 2 )
                return 0;
              v10 = BuiltinDomainSids;
              v11 = 35;
              break;
            case 0x15u:
              if ( (_BYTE)v5 != 5 )
                return 0;
              v10 = AccountDomainSids;
              v11 = 22;
              break;
            case 5u:
              if ( (_BYTE)v5 == 3 )
              {
                v14 = 21;
                v8 = 1;
                goto LABEL_24;
              }
              return 0;
            case 0x40u:
              if ( (_BYTE)v5 != 2 )
                return 0;
              v10 = SecurityPackageSids;
              v11 = 3;
              break;
            case 0x41u:
              if ( (_BYTE)v5 != 2 )
                return 0;
              v8 = 1;
              v10 = &CredTypeSids;
              v11 = 1;
LABEL_19:
              v12 = *RtlSubAuthoritySid(pSid, v5 - 1);
              for ( j = 0; (unsigned int)j < v11; j = (unsigned int)(j + 1) )
              {
                if ( v12 == LODWORD(v10[j]) )
                {
                  v14 = HIDWORD(v10[j]);
                  goto LABEL_24;
                }
              }
              return 0;
            default:
              if ( v7 == 84 && (_BYTE)v5 == 6 )
              {
                v8 = 1;
                if ( !*RtlSubAuthoritySid(pSid, 1u)
                  && !*RtlSubAuthoritySid(pSid, 2u)
                  && !*RtlSubAuthoritySid(pSid, 3u)
                  && !*RtlSubAuthoritySid(pSid, 4u)
                  && !*RtlSubAuthoritySid(pSid, 5u) )
                {
                  v14 = 98;
LABEL_24:
                  if ( v14 == WellKnownSidType )
                    return v8;
                  return 0;
                }
              }
              return 0;
          }
        }
      }
LABEL_18:
      v8 = 1;
      goto LABEL_19;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180031200  push    rbx
0x180031202  push    rsi
0x180031203  push    r15
0x180031205  sub     rsp, 20h
0x180031209  mov     r15d, edx
0x18003120c  mov     rsi, rcx
0x18003120f  call    cs:__imp_RtlValidSid
0x180031215  test    al, al
0x180031217  jz      loc_1800314BB
0x18003121d  xor     ecx, ecx; LastError
0x18003121f  call    cs:__imp_RtlSetLastWin32Error
0x180031225  mov     rcx, rsi; Sid
0x180031228  call    cs:__imp_RtlIdentifierAuthoritySid
0x18003122e  mov     rbx, rax
0x180031231  test    rax, rax
0x180031234  jz      loc_1800314BB
0x18003123a  mov     [rsp+38h+arg_0], rbp
0x18003123f  mov     rcx, rsi; Sid
0x180031242  mov     [rsp+38h+arg_10], r14
0x180031247  mov     [rsp+38h+arg_8], rdi
0x18003124c  call    cs:__imp_RtlSubAuthorityCountSid
0x180031252  movzx   ebp, byte ptr [rax]
0x180031255  test    bpl, bpl
0x180031258  jz      loc_180031424
0x18003125e  cmp     bpl, 1
0x180031262  jz      loc_180031340
0x180031268  jbe     short loc_1800312C8
0x18003126a  mov     ecx, [rbx]
0x18003126c  sub     ecx, cs:dword_180198970
0x180031272  jnz     short loc_180031281
0x180031274  movzx   ecx, word ptr [rbx+4]
0x180031278  movzx   eax, cs:word_180198974
0x18003127f  sub     ecx, eax
0x180031281  test    ecx, ecx
0x180031283  jnz     loc_180031398
0x180031289  xor     edx, edx; SubAuthority
0x18003128b  mov     rcx, rsi; Sid
0x18003128e  call    cs:__imp_RtlSubAuthoritySid
0x180031294  mov     ecx, [rax]
0x180031296  cmp     ecx, 20h ; ' '
0x180031299  jz      loc_18003132C
0x18003129f  cmp     ecx, 15h
0x1800312a2  jz      short loc_1800312E6
0x1800312a4  cmp     ecx, 5
0x1800312a7  jz      loc_180031477
0x1800312ad  cmp     ecx, 40h ; '@'
0x1800312b0  jz      loc_180031491
0x1800312b6  cmp     ecx, 41h ; 'A'
0x1800312b9  jz      loc_1800314C2
0x1800312bf  cmp     ecx, 54h ; 'T'
0x1800312c2  jz      loc_1800314AC
0x1800312c8  xor     r14d, r14d
0x1800312cb  mov     rdi, [rsp+38h+arg_8]
0x1800312d0  mov     eax, r14d
0x1800312d3  mov     r14, [rsp+38h+arg_10]
0x1800312d8  mov     rbp, [rsp+38h+arg_0]
0x1800312dd  add     rsp, 20h
0x1800312e1  pop     r15
0x1800312e3  pop     rsi
0x1800312e4  pop     rbx
0x1800312e5  retn
0x1800312e6  cmp     bpl, 5
0x1800312ea  jnz     short loc_1800312C8
0x1800312ec  lea     rdi, AccountDomainSids
0x1800312f3  mov     ebx, 16h
0x1800312f8  mov     r14d, 1
0x1800312fe  lea     edx, [rbp-1]; SubAuthority
0x180031301  mov     rcx, rsi; Sid
0x180031304  call    cs:__imp_RtlSubAuthoritySid
0x18003130a  mov     r8d, [rax]
0x18003130d  xor     eax, eax
0x18003130f  nop
0x180031310  cmp     eax, ebx
0x180031312  jnb     short loc_1800312C8
0x180031314  cmp     r8d, [rdi+rax*8]
0x180031318  lea     rdx, [rdi+rax*8]
0x18003131c  jz      short loc_180031322
0x18003131e  inc     eax
0x180031320  jmp     short loc_180031310
0x180031322  mov     eax, [rdx+4]
0x180031325  cmp     eax, r15d
0x180031328  jz      short loc_1800312CB
0x18003132a  jmp     short loc_1800312C8
0x18003132c  cmp     bpl, 2
0x180031330  jnz     short loc_1800312C8
0x180031332  lea     rdi, BuiltinDomainSids
0x180031339  mov     ebx, 23h ; '#'
0x18003133e  jmp     short loc_1800312F8
0x180031340  xor     edx, edx
0x180031342  lea     r9, KnownAuthoritiesAndDomains
0x180031349  nop     dword ptr [rax+00000000h]
0x180031350  cmp     edx, 0Dh
0x180031353  jnb     loc_1800313EB
0x180031359  lea     rcx, [rdx+rdx*2]
0x18003135d  lea     r8, ds:0[rcx*8]
0x180031365  mov     ecx, [rbx]
0x180031367  sub     ecx, [r8+r9]
0x18003136b  jnz     short loc_180031379
0x18003136d  movzx   ecx, word ptr [rbx+4]
0x180031371  movzx   eax, word ptr [r8+r9+4]
0x180031377  sub     ecx, eax
0x180031379  test    ecx, ecx
0x18003137b  jz      short loc_180031381
0x18003137d  inc     edx
0x18003137f  jmp     short loc_180031350
0x180031381  lfence
0x180031384  mov     rdi, [r8+r9+8]
0x180031389  test    rdi, rdi
0x18003138c  jz      short loc_1800313EB
0x18003138e  mov     ebx, [r8+r9+10h]
0x180031393  jmp     loc_1800312F8
0x180031398  mov     ecx, [rbx]
0x18003139a  sub     ecx, cs:dword_180198A00
0x1800313a0  jnz     short loc_1800313AF
0x1800313a2  movzx   ecx, word ptr [rbx+4]
0x1800313a6  movzx   eax, cs:word_180198A04
0x1800313ad  sub     ecx, eax
0x1800313af  test    ecx, ecx
0x1800313b1  jnz     loc_1800312C8
0x1800313b7  xor     edx, edx; SubAuthority
0x1800313b9  mov     rcx, rsi; Sid
0x1800313bc  call    cs:__imp_RtlSubAuthoritySid
0x1800313c2  mov     ecx, [rax]
0x1800313c4  cmp     ecx, 2
0x1800313c7  jnz     loc_180031453
0x1800313cd  cmp     bpl, cl
0x1800313d0  jnz     loc_1800312C8
0x1800313d6  mov     r14d, 1
0x1800313dc  lea     rdi, ApplicationPackageTypeSids
0x1800313e3  mov     ebx, r14d
0x1800313e6  jmp     loc_1800312FE
0x1800313eb  mov     ecx, [rbx]
0x1800313ed  sub     ecx, cs:dword_1801989D0
0x1800313f3  jnz     short loc_180031402
0x1800313f5  movzx   ecx, word ptr [rbx+4]
0x1800313f9  movzx   eax, cs:word_1801989D4
0x180031400  sub     ecx, eax
0x180031402  test    ecx, ecx
0x180031404  jnz     loc_1800312C8
0x18003140a  mov     rdi, cs:off_1801989D8
0x180031411  mov     ebx, 6
0x180031416  test    rdi, rdi
0x180031419  jz      loc_1800312C8
0x18003141f  jmp     loc_1800312F8
0x180031424  mov     ecx, [rbx]
0x180031426  sub     ecx, cs:dword_180198970
0x18003142c  jnz     short loc_18003143B
0x18003142e  movzx   ecx, word ptr [rbx+4]
0x180031432  movzx   eax, cs:word_180198974
0x180031439  sub     ecx, eax
0x18003143b  test    ecx, ecx
0x18003143d  jnz     loc_1800312C8
0x180031443  mov     eax, 7
0x180031448  mov     r14d, 1
0x18003144e  jmp     loc_180031325
0x180031453  cmp     bpl, 2
0x180031457  jnz     loc_1800312C8
0x18003145d  cmp     ecx, 3
0x180031460  jnz     loc_1800312C8
0x180031466  lea     rdi, ApplicationCapabilityTypeSids
0x18003146d  mov     ebx, 0Ch
0x180031472  jmp     loc_1800312F8
0x180031477  cmp     bpl, 3
0x18003147b  jnz     loc_1800312C8
0x180031481  mov     eax, 15h
0x180031486  mov     r14d, 1
0x18003148c  jmp     loc_180031325
0x180031491  cmp     bpl, 2
0x180031495  jnz     loc_1800312C8
0x18003149b  lea     rdi, SecurityPackageSids
0x1800314a2  mov     ebx, 3
0x1800314a7  jmp     loc_1800312F8
0x1800314ac  cmp     bpl, 6
0x1800314b0  jnz     loc_1800312C8
0x1800314b6  jmp     loc_18018D5C2
0x1800314bb  xor     eax, eax
0x1800314bd  jmp     loc_1800312DD
0x1800314c2  cmp     bpl, 2
0x1800314c6  jnz     loc_1800312C8
0x1800314cc  mov     r14d, 1
0x1800314d2  lea     rdi, CredTypeSids
0x1800314d9  mov     ebx, r14d
0x1800314dc  jmp     loc_1800312FE
0x18018d5c2  mov     r14d, 1
0x18018d5c8  mov     rcx, rsi; Sid
0x18018d5cb  mov     edx, r14d; SubAuthority
0x18018d5ce  call    cs:__imp_RtlSubAuthoritySid
0x18018d5d4  cmp     dword ptr [rax], 0
0x18018d5d7  jnz     loc_1800312C8
0x18018d5dd  mov     edx, 2; SubAuthority
0x18018d5e2  mov     rcx, rsi; Sid
0x18018d5e5  call    cs:__imp_RtlSubAuthoritySid
0x18018d5eb  cmp     dword ptr [rax], 0
0x18018d5ee  jnz     loc_1800312C8
0x18018d5f4  mov     edx, 3; SubAuthority
0x18018d5f9  mov     rcx, rsi; Sid
0x18018d5fc  call    cs:__imp_RtlSubAuthoritySid
0x18018d602  cmp     dword ptr [rax], 0
0x18018d605  jnz     loc_1800312C8
0x18018d60b  mov     edx, 4; SubAuthority
0x18018d610  mov     rcx, rsi; Sid
0x18018d613  call    cs:__imp_RtlSubAuthoritySid
0x18018d619  cmp     dword ptr [rax], 0
0x18018d61c  jnz     loc_1800312C8
0x18018d622  mov     edx, 5; SubAuthority
0x18018d627  mov     rcx, rsi; Sid
0x18018d62a  call    cs:__imp_RtlSubAuthoritySid
0x18018d630  cmp     dword ptr [rax], 0
0x18018d633  jnz     loc_1800312C8
0x18018d639  mov     eax, 62h ; 'b'
0x18018d63e  jmp     loc_180031325
```
