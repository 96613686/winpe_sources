# EqualDomainSid

- ea: `0x1800ab280`
- end: `0x1800ab441`
- name: `EqualDomainSid`
- size: `449`
- prototype: `BOOL __stdcall(PSID pSid1, PSID pSid2, BOOL *pfEqual)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800ab280`
- `0x1800ab450`
- `0x1800ab560`
- `0x1800ab840`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x1800ab386`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab3ff`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab386`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab3ff`
- `ntdll!RtlSetLastWin32Error` at `0x1800ab419`
- `ntdll!RtlSetLastWin32Error` at `0x1800ab419`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800ab372`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800ab3ef`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800ab372`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800ab3ef`
- `ntdll!RtlValidSid` at `0x1800ab2ab`
- `ntdll!RtlValidSid` at `0x1800ab2bc`
- `ntdll!RtlValidSid` at `0x1800ab2ab`
- `ntdll!RtlValidSid` at `0x1800ab2bc`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800ab34a`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800ab3cb`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800ab34a`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800ab3cb`

## pseudocode

```c
BOOL __stdcall EqualDomainSid(PSID pSid1, PSID pSid2, BOOL *pfEqual)
{
  _BYTE *v6; // rdi
  PSID_IDENTIFIER_AUTHORITY v7; // rax
  int v8; // ecx
  _BYTE *v9; // rdx
  PSID_IDENTIFIER_AUTHORITY v11; // rax
  int v12; // ecx
  ULONG v13; // ecx
  DWORD cbSid[4]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE pDomainSid[80]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v17[80]; // [rsp+D0h] [rbp-30h] BYREF

  if ( !RtlValidSid(pSid1) || !RtlValidSid(pSid2) )
  {
    v13 = 1337;
LABEL_23:
    RtlSetLastWin32Error(v13);
    return 0;
  }
  if ( !pfEqual )
  {
    v13 = 87;
    goto LABEL_23;
  }
  if ( *(_BYTE *)pSid1 != *(_BYTE *)pSid2 )
  {
    v13 = 1306;
    goto LABEL_23;
  }
  cbSid[0] = 68;
  if ( CreateWellKnownSid(WinBuiltinDomainSid, 0, pSid, cbSid) )
  {
    cbSid[0] = 68;
    if ( GetWindowsAccountDomainSid(pSid1, pDomainSid, cbSid) )
    {
      v6 = pDomainSid;
    }
    else
    {
      v11 = RtlIdentifierAuthoritySid(pSid1);
      v12 = *(_DWORD *)v11->Value;
      if ( !*(_DWORD *)v11->Value )
        v12 = *(unsigned __int16 *)&v11->Value[4] - 1280;
      if ( v12 || !*RtlSubAuthorityCountSid(pSid1) || *RtlSubAuthoritySid(pSid1, 0) != 32 )
      {
LABEL_25:
        v13 = 1258;
        goto LABEL_23;
      }
      v6 = pSid;
    }
    cbSid[0] = 68;
    if ( GetWindowsAccountDomainSid(pSid2, v17, cbSid) )
    {
      v9 = v17;
      goto LABEL_15;
    }
    v7 = RtlIdentifierAuthoritySid(pSid2);
    v8 = *(_DWORD *)v7->Value;
    if ( !*(_DWORD *)v7->Value )
      v8 = *(unsigned __int16 *)&v7->Value[4] - 1280;
    if ( !v8 && *RtlSubAuthorityCountSid(pSid2) && *RtlSubAuthoritySid(pSid2, 0) == 32 )
    {
      v9 = pSid;
LABEL_15:
      *pfEqual = EqualSid(v6, v9);
      return 1;
    }
    goto LABEL_25;
  }
  return 0;
}

```

## disassembly

```asm
0x1800ab280  mov     [rsp-8+arg_18], rbx
0x1800ab285  push    rbp
0x1800ab286  push    rsi
0x1800ab287  push    rdi
0x1800ab288  lea     rbp, [rsp-30h]
0x1800ab28d  sub     rsp, 130h
0x1800ab294  mov     rax, cs:__security_cookie
0x1800ab29b  xor     rax, rsp
0x1800ab29e  mov     [rbp+40h+var_20], rax
0x1800ab2a2  mov     rsi, r8
0x1800ab2a5  mov     rbx, rdx
0x1800ab2a8  mov     rdi, rcx
0x1800ab2ab  call    cs:__imp_RtlValidSid
0x1800ab2b1  test    al, al
0x1800ab2b3  jz      loc_1800AB414
0x1800ab2b9  mov     rcx, rbx; Sid
0x1800ab2bc  call    cs:__imp_RtlValidSid
0x1800ab2c2  test    al, al
0x1800ab2c4  jz      loc_1800AB414
0x1800ab2ca  test    rsi, rsi
0x1800ab2cd  jz      loc_1800AB433
0x1800ab2d3  mov     al, [rbx]
0x1800ab2d5  cmp     [rdi], al
0x1800ab2d7  jnz     loc_1800AB43A
0x1800ab2dd  xor     edx, edx; DomainSid
0x1800ab2df  mov     [rsp+140h+cbSid], 44h ; 'D'
0x1800ab2e7  lea     r9, [rsp+140h+cbSid]; cbSid
0x1800ab2ec  lea     r8, [rsp+140h+pSid]; pSid
0x1800ab2f1  lea     ecx, [rdx+19h]; WellKnownSidType
0x1800ab2f4  call    CreateWellKnownSid
0x1800ab2f9  test    eax, eax
0x1800ab2fb  jz      loc_1800AB41F
0x1800ab301  lea     r8, [rsp+140h+cbSid]; cbDomainSid
0x1800ab306  mov     [rsp+140h+cbSid], 44h ; 'D'
0x1800ab30e  lea     rdx, [rbp+40h+pDomainSid]; pDomainSid
0x1800ab312  mov     rcx, rdi; pSid
0x1800ab315  call    GetWindowsAccountDomainSid
0x1800ab31a  test    eax, eax
0x1800ab31c  jz      loc_1800AB3C8
0x1800ab322  lea     rdi, [rbp+40h+pDomainSid]
0x1800ab326  lea     r8, [rsp+140h+cbSid]; cbDomainSid
0x1800ab32b  mov     [rsp+140h+cbSid], 44h ; 'D'
0x1800ab333  lea     rdx, [rbp+40h+var_70]; pDomainSid
0x1800ab337  mov     rcx, rbx; pSid
0x1800ab33a  call    GetWindowsAccountDomainSid
0x1800ab33f  test    eax, eax
0x1800ab341  jnz     loc_1800AB42A
0x1800ab347  mov     rcx, rbx; Sid
0x1800ab34a  call    cs:__imp_RtlIdentifierAuthoritySid
0x1800ab350  mov     ecx, [rax]
0x1800ab352  sub     ecx, cs:dword_180198970
0x1800ab358  jnz     short loc_1800AB367
0x1800ab35a  movzx   ecx, word ptr [rax+4]
0x1800ab35e  movzx   eax, cs:word_180198974
0x1800ab365  sub     ecx, eax
0x1800ab367  test    ecx, ecx
0x1800ab369  jnz     loc_1800AB423
0x1800ab36f  mov     rcx, rbx; Sid
0x1800ab372  call    cs:__imp_RtlSubAuthorityCountSid
0x1800ab378  cmp     byte ptr [rax], 0
0x1800ab37b  jbe     loc_1800AB423
0x1800ab381  xor     edx, edx; SubAuthority
0x1800ab383  mov     rcx, rbx; Sid
0x1800ab386  call    cs:__imp_RtlSubAuthoritySid
0x1800ab38c  cmp     dword ptr [rax], 20h ; ' '
0x1800ab38f  jnz     loc_1800AB423
0x1800ab395  lea     rdx, [rsp+140h+pSid]; pSid2
0x1800ab39a  mov     rcx, rdi; pSid1
0x1800ab39d  call    EqualSid
0x1800ab3a2  mov     [rsi], eax
0x1800ab3a4  mov     eax, 1
0x1800ab3a9  mov     rcx, [rbp+40h+var_20]
0x1800ab3ad  xor     rcx, rsp; StackCookie
0x1800ab3b0  call    __security_check_cookie
0x1800ab3b5  mov     rbx, [rsp+140h+arg_18]
0x1800ab3bd  add     rsp, 130h
0x1800ab3c4  pop     rdi
0x1800ab3c5  pop     rsi
0x1800ab3c6  pop     rbp
0x1800ab3c7  retn
0x1800ab3c8  mov     rcx, rdi; Sid
0x1800ab3cb  call    cs:__imp_RtlIdentifierAuthoritySid
0x1800ab3d1  mov     ecx, [rax]
0x1800ab3d3  sub     ecx, cs:dword_180198970
0x1800ab3d9  jnz     short loc_1800AB3E8
0x1800ab3db  movzx   ecx, word ptr [rax+4]
0x1800ab3df  movzx   eax, cs:word_180198974
0x1800ab3e6  sub     ecx, eax
0x1800ab3e8  test    ecx, ecx
0x1800ab3ea  jnz     short loc_1800AB423
0x1800ab3ec  mov     rcx, rdi; Sid
0x1800ab3ef  call    cs:__imp_RtlSubAuthorityCountSid
0x1800ab3f5  cmp     byte ptr [rax], 0
0x1800ab3f8  jbe     short loc_1800AB423
0x1800ab3fa  xor     edx, edx; SubAuthority
0x1800ab3fc  mov     rcx, rdi; Sid
0x1800ab3ff  call    cs:__imp_RtlSubAuthoritySid
0x1800ab405  cmp     dword ptr [rax], 20h ; ' '
0x1800ab408  jnz     short loc_1800AB423
0x1800ab40a  lea     rdi, [rsp+140h+pSid]
0x1800ab40f  jmp     loc_1800AB326
0x1800ab414  mov     ecx, 539h; LastError
0x1800ab419  call    cs:__imp_RtlSetLastWin32Error
0x1800ab41f  xor     eax, eax
0x1800ab421  jmp     short loc_1800AB3A9
0x1800ab423  mov     ecx, 4EAh
0x1800ab428  jmp     short loc_1800AB419
0x1800ab42a  lea     rdx, [rbp+40h+var_70]
0x1800ab42e  jmp     loc_1800AB39A
0x1800ab433  mov     ecx, 57h ; 'W'
0x1800ab438  jmp     short loc_1800AB419
0x1800ab43a  mov     ecx, 51Ah
0x1800ab43f  jmp     short loc_1800AB419
```
