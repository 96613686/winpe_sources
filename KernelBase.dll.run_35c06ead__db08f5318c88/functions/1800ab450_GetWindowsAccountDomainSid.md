# GetWindowsAccountDomainSid

- ea: `0x1800ab450`
- end: `0x1800ab558`
- name: `GetWindowsAccountDomainSid`
- size: `264`
- prototype: `BOOL __stdcall(PSID pSid, PSID pDomainSid, DWORD *cbDomainSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800ab280`

## callees

- `0x1800134a0`
- `0x1800ab450`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x1800ab4fe`
- `ntdll!RtlInitializeSid` at `0x1800ab4fe`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab4c9`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab50f`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab51d`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab4c9`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab50f`
- `ntdll!RtlSubAuthoritySid` at `0x1800ab51d`
- `ntdll!RtlLengthRequiredSid` at `0x1800ab4d9`
- `ntdll!RtlLengthRequiredSid` at `0x1800ab4d9`
- `ntdll!RtlSetLastWin32Error` at `0x1800ab4ac`
- `ntdll!RtlSetLastWin32Error` at `0x1800ab4ac`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800ab49c`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800ab49c`
- `ntdll!RtlValidSid` at `0x1800ab462`
- `ntdll!RtlValidSid` at `0x1800ab462`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800ab478`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800ab4ef`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800ab478`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800ab4ef`

## pseudocode

```c
BOOL __stdcall GetWindowsAccountDomainSid(PSID pSid, PSID pDomainSid, DWORD *cbDomainSid)
{
  PSID_IDENTIFIER_AUTHORITY v6; // rax
  int v7; // ecx
  ULONG v8; // ecx
  ULONG v10; // eax
  DWORD v11; // ecx
  struct _SID_IDENTIFIER_AUTHORITY *v12; // rax
  NTSTATUS v13; // eax
  ULONG i; // esi
  PULONG v15; // rbx
  PULONG v16; // rax

  if ( !RtlValidSid(pSid) )
  {
    v8 = 1337;
    goto LABEL_8;
  }
  if ( !cbDomainSid )
    goto LABEL_10;
  v6 = RtlIdentifierAuthoritySid(pSid);
  v7 = *(_DWORD *)v6->Value;
  if ( !*(_DWORD *)v6->Value )
    v7 = *(unsigned __int16 *)&v6->Value[4] - 1280;
  if ( v7 || *RtlSubAuthorityCountSid(pSid) <= 3u || *RtlSubAuthoritySid(pSid, 0) != 21 )
  {
    v8 = 1257;
LABEL_8:
    RtlSetLastWin32Error(v8);
    return 0;
  }
  v10 = RtlLengthRequiredSid(4u);
  v11 = *cbDomainSid;
  *cbDomainSid = v10;
  if ( v11 < v10 )
  {
    v8 = 122;
    goto LABEL_8;
  }
  if ( !pDomainSid )
  {
LABEL_10:
    v8 = 87;
    goto LABEL_8;
  }
  v12 = RtlIdentifierAuthoritySid(pSid);
  v13 = RtlInitializeSid(pDomainSid, v12, 4u);
  if ( v13 < 0 )
  {
    BaseSetLastNTError((unsigned int)v13);
    return 0;
  }
  for ( i = 0; i < 4; ++i )
  {
    v15 = RtlSubAuthoritySid(pSid, i);
    v16 = RtlSubAuthoritySid(pDomainSid, i);
    *v16 = *v15;
  }
  return 1;
}

```

## disassembly

```asm
0x1800ab450  push    rbx
0x1800ab452  push    rbp
0x1800ab453  push    rsi
0x1800ab454  push    rdi
0x1800ab455  sub     rsp, 28h
0x1800ab459  mov     rbx, r8
0x1800ab45c  mov     rbp, rdx
0x1800ab45f  mov     rdi, rcx
0x1800ab462  call    cs:__imp_RtlValidSid
0x1800ab468  test    al, al
0x1800ab46a  jz      loc_1800AB538
0x1800ab470  test    rbx, rbx
0x1800ab473  jz      short loc_1800AB4BD
0x1800ab475  mov     rcx, rdi; Sid
0x1800ab478  call    cs:__imp_RtlIdentifierAuthoritySid
0x1800ab47e  mov     ecx, [rax]
0x1800ab480  sub     ecx, cs:dword_180198970
0x1800ab486  jnz     short loc_1800AB495
0x1800ab488  movzx   ecx, word ptr [rax+4]
0x1800ab48c  movzx   eax, cs:word_180198974
0x1800ab493  sub     ecx, eax
0x1800ab495  test    ecx, ecx
0x1800ab497  jnz     short loc_1800AB4A7
0x1800ab499  mov     rcx, rdi; Sid
0x1800ab49c  call    cs:__imp_RtlSubAuthorityCountSid
0x1800ab4a2  cmp     byte ptr [rax], 3
0x1800ab4a5  ja      short loc_1800AB4C4
0x1800ab4a7  mov     ecx, 4E9h; LastError
0x1800ab4ac  call    cs:__imp_RtlSetLastWin32Error
0x1800ab4b2  xor     eax, eax
0x1800ab4b4  add     rsp, 28h
0x1800ab4b8  pop     rdi
0x1800ab4b9  pop     rsi
0x1800ab4ba  pop     rbp
0x1800ab4bb  pop     rbx
0x1800ab4bc  retn
0x1800ab4bd  mov     ecx, 57h ; 'W'
0x1800ab4c2  jmp     short loc_1800AB4AC
0x1800ab4c4  xor     edx, edx; SubAuthority
0x1800ab4c6  mov     rcx, rdi; Sid
0x1800ab4c9  call    cs:__imp_RtlSubAuthoritySid
0x1800ab4cf  cmp     dword ptr [rax], 15h
0x1800ab4d2  jnz     short loc_1800AB4A7
0x1800ab4d4  mov     ecx, 4; SubAuthorityCount
0x1800ab4d9  call    cs:__imp_RtlLengthRequiredSid
0x1800ab4df  mov     ecx, [rbx]
0x1800ab4e1  mov     [rbx], eax
0x1800ab4e3  cmp     ecx, eax
0x1800ab4e5  jb      short loc_1800AB542
0x1800ab4e7  test    rbp, rbp
0x1800ab4ea  jz      short loc_1800AB4BD
0x1800ab4ec  mov     rcx, rdi; Sid
0x1800ab4ef  call    cs:__imp_RtlIdentifierAuthoritySid
0x1800ab4f5  mov     r8b, 4; SubAuthorityCount
0x1800ab4f8  mov     rcx, rbp; Sid
0x1800ab4fb  mov     rdx, rax; IdentifierAuthority
0x1800ab4fe  call    cs:__imp_RtlInitializeSid
0x1800ab504  test    eax, eax
0x1800ab506  js      short loc_1800AB54C
0x1800ab508  xor     esi, esi
0x1800ab50a  mov     edx, esi; SubAuthority
0x1800ab50c  mov     rcx, rdi; Sid
0x1800ab50f  call    cs:__imp_RtlSubAuthoritySid
0x1800ab515  mov     edx, esi; SubAuthority
0x1800ab517  mov     rcx, rbp; Sid
0x1800ab51a  mov     rbx, rax
0x1800ab51d  call    cs:__imp_RtlSubAuthoritySid
0x1800ab523  mov     ecx, [rbx]
0x1800ab525  inc     esi
0x1800ab527  mov     [rax], ecx
0x1800ab529  cmp     esi, 4
0x1800ab52c  jb      short loc_1800AB50A
0x1800ab52e  mov     eax, 1
0x1800ab533  jmp     loc_1800AB4B4
0x1800ab538  mov     ecx, 539h
0x1800ab53d  jmp     loc_1800AB4AC
0x1800ab542  mov     ecx, 7Ah ; 'z'
0x1800ab547  jmp     loc_1800AB4AC
0x1800ab54c  mov     ecx, eax
0x1800ab54e  call    BaseSetLastNTError
0x1800ab553  jmp     loc_1800AB4B2
```
