# _CreateACL(ACLResource *)

- ea: `0x180032120`
- end: `0x180032330`
- name: `?_CreateACL@@YAJPEAVACLResource@@@Z`
- size: `528`
- prototype: `__int64 __fastcall(struct ACLResource *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180031a04`

## callees

- `0x18001ba48`
- `0x180032120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322fd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800321a4`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003220c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800321a4`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003220c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800322c5`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800322c5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800322f3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800322f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003216b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032179`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032297`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003216b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032179`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032297`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18003226b`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18003226b`

## pseudocode

```c
__int64 __fastcall _CreateACL(struct ACLResource *a1)
{
  HLOCAL v2; // rax
  void *v3; // r8
  signed int LastError; // eax
  signed int v5; // ebx
  WCHAR *v6; // rax
  void *v7; // r8
  signed int v8; // eax
  signed int v9; // eax
  HLOCAL v10; // rax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+20h] [rbp-60h] BYREF
  int v16; // [rsp+50h] [rbp-30h]
  int v17; // [rsp+54h] [rbp-2Ch]
  int v18; // [rsp+58h] [rbp-28h]
  int v19; // [rsp+6Ch] [rbp-14h]
  int v20; // [rsp+70h] [rbp-10h]
  __int64 v21; // [rsp+78h] [rbp-8h]
  DWORD cbSid; // [rsp+A0h] [rbp+20h] BYREF

  memset_0(&pListOfExplicitEntries, 0, 0x60u);
  *((_QWORD *)a1 + 3) = 0;
  *((_QWORD *)a1 + 2) = 0;
  *(_QWORD *)a1 = LocalAlloc(0x40u, 0x44u);
  v2 = LocalAlloc(0x40u, 0x44u);
  v3 = *(void **)a1;
  *((_QWORD *)a1 + 1) = v2;
  if ( !v3 || !v2 )
    return (unsigned int)-2147024882;
  cbSid = 68;
  if ( CreateWellKnownSid(WinAuthenticatedUserSid, 0, v3, &cbSid) )
  {
    v6 = *(WCHAR **)a1;
    v5 = 0;
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    pListOfExplicitEntries.Trustee.ptstrName = v6;
    pListOfExplicitEntries.grfAccessPermissions = 270467072;
    pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
    pListOfExplicitEntries.grfInheritance = 3;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
      return (unsigned int)v5;
  }
  v7 = (void *)*((_QWORD *)a1 + 1);
  cbSid = 68;
  if ( CreateWellKnownSid(WinLocalSystemSid, 0, v7, &cbSid) )
  {
    v21 = *((_QWORD *)a1 + 1);
    v16 = 270467072;
    v17 = 2;
    v18 = 3;
    v19 = 0;
    v20 = 2;
LABEL_15:
    if ( !SetEntriesInAclW(2u, &pListOfExplicitEntries, 0, (PACL *)a1 + 2) )
      goto LABEL_19;
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    if ( v5 >= 0 )
    {
LABEL_19:
      v10 = LocalAlloc(0x40u, 0x28u);
      *((_QWORD *)a1 + 3) = v10;
      if ( v10 )
        goto LABEL_26;
      v11 = GetLastError();
      v5 = v11;
      if ( v11 > 0 )
        v5 = (unsigned __int16)v11 | 0x80070000;
      if ( v5 >= 0 )
      {
LABEL_26:
        if ( InitializeSecurityDescriptor(*((PSECURITY_DESCRIPTOR *)a1 + 3), 1u) )
          goto LABEL_34;
        v12 = GetLastError();
        v5 = v12;
        if ( v12 > 0 )
          v5 = (unsigned __int16)v12 | 0x80070000;
        if ( v5 >= 0 )
        {
LABEL_34:
          if ( !SetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)a1 + 3), 1, *((PACL *)a1 + 2), 0) )
          {
            v13 = GetLastError();
            v5 = v13;
            if ( v13 > 0 )
              return (unsigned __int16)v13 | 0x80070000;
          }
        }
      }
    }
    return (unsigned int)v5;
  }
  v8 = GetLastError();
  v5 = v8;
  if ( v8 > 0 )
    v5 = (unsigned __int16)v8 | 0x80070000;
  if ( v5 >= 0 )
    goto LABEL_15;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180032120  mov     [rsp-18h+arg_8], rbx
0x180032125  mov     [rsp-18h+arg_10], rsi
0x18003212a  push    rbp
0x18003212b  push    rdi
0x18003212c  push    r15
0x18003212e  mov     rbp, rsp
0x180032131  sub     rsp, 80h
0x180032138  xor     edx, edx; Val
0x18003213a  mov     rdi, rcx
0x18003213d  lea     rcx, [rbp+pListOfExplicitEntries]; void *
0x180032141  lea     r8d, [rdx+60h]; Size
0x180032145  call    memset_0
0x18003214a  mov     ebx, 44h ; 'D'
0x18003214f  mov     qword ptr [rdi+18h], 0
0x180032157  lea     rsi, [rdi+10h]
0x18003215b  mov     edx, ebx; uBytes
0x18003215d  mov     qword ptr [rsi], 0
0x180032164  lea     r15d, [rbx-4]
0x180032168  mov     ecx, r15d; uFlags
0x18003216b  call    cs:__imp_LocalAlloc
0x180032171  mov     edx, ebx; uBytes
0x180032173  mov     ecx, r15d; uFlags
0x180032176  mov     [rdi], rax
0x180032179  call    cs:__imp_LocalAlloc
0x18003217f  mov     r8, [rdi]; pSid
0x180032182  mov     [rdi+8], rax
0x180032186  test    r8, r8
0x180032189  jz      loc_180032311
0x18003218f  test    rax, rax
0x180032192  jz      loc_180032311
0x180032198  lea     r9, [rbp+cbSid]; cbSid
0x18003219c  mov     [rbp+cbSid], ebx
0x18003219f  xor     edx, edx; DomainSid
0x1800321a1  lea     ecx, [rbx-33h]; WellKnownSidType
0x1800321a4  call    cs:__imp_CreateWellKnownSid
0x1800321aa  mov     r15d, 80070000h
0x1800321b0  test    eax, eax
0x1800321b2  jnz     short loc_1800321D0
0x1800321b4  call    cs:__imp_GetLastError
0x1800321ba  mov     ebx, eax
0x1800321bc  test    eax, eax
0x1800321be  jle     short loc_1800321C6
0x1800321c0  movzx   ebx, ax
0x1800321c3  or      ebx, r15d
0x1800321c6  test    ebx, ebx
0x1800321c8  js      loc_180032316
0x1800321ce  jmp     short loc_1800321F8
0x1800321d0  mov     rax, [rdi]
0x1800321d3  xor     ebx, ebx
0x1800321d5  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeForm], ebx
0x1800321d8  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800321dc  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], 101F0000h
0x1800321e3  mov     [rbp+pListOfExplicitEntries.grfAccessMode], 2
0x1800321ea  mov     [rbp+pListOfExplicitEntries.grfInheritance], 3
0x1800321f1  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x1800321f8  mov     r8, [rdi+8]; pSid
0x1800321fc  lea     r9, [rbp+cbSid]; cbSid
0x180032200  xor     edx, edx; DomainSid
0x180032202  mov     [rbp+cbSid], 44h ; 'D'
0x180032209  lea     ecx, [rdx+16h]; WellKnownSidType
0x18003220c  call    cs:__imp_CreateWellKnownSid
0x180032212  test    eax, eax
0x180032214  jnz     short loc_180032232
0x180032216  call    cs:__imp_GetLastError
0x18003221c  mov     ebx, eax
0x18003221e  test    eax, eax
0x180032220  jle     short loc_180032228
0x180032222  movzx   ebx, ax
0x180032225  or      ebx, r15d
0x180032228  test    ebx, ebx
0x18003222a  js      loc_180032316
0x180032230  jmp     short loc_18003225D
0x180032232  mov     rax, [rdi+8]
0x180032236  mov     [rbp+var_8], rax
0x18003223a  mov     [rbp+var_30], 101F0000h
0x180032241  mov     [rbp+var_2C], 2
0x180032248  mov     [rbp+var_28], 3
0x18003224f  mov     [rbp+var_14], 0
0x180032256  mov     [rbp+var_10], 2
0x18003225d  xor     r8d, r8d; OldAcl
0x180032260  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x180032264  mov     r9, rsi; NewAcl
0x180032267  lea     ecx, [r8+2]; cCountOfExplicitEntries
0x18003226b  call    cs:__imp_SetEntriesInAclW
0x180032271  test    eax, eax
0x180032273  jz      short loc_18003228F
0x180032275  call    cs:__imp_GetLastError
0x18003227b  mov     ebx, eax
0x18003227d  test    eax, eax
0x18003227f  jle     short loc_180032287
0x180032281  movzx   ebx, ax
0x180032284  or      ebx, r15d
0x180032287  test    ebx, ebx
0x180032289  js      loc_180032316
0x18003228f  mov     edx, 28h ; '('; uBytes
0x180032294  lea     ecx, [rdx+18h]; uFlags
0x180032297  call    cs:__imp_LocalAlloc
0x18003229d  mov     [rdi+18h], rax
0x1800322a1  test    rax, rax
0x1800322a4  jnz     short loc_1800322BC
0x1800322a6  call    cs:__imp_GetLastError
0x1800322ac  mov     ebx, eax
0x1800322ae  test    eax, eax
0x1800322b0  jle     short loc_1800322B8
0x1800322b2  movzx   ebx, ax
0x1800322b5  or      ebx, r15d
0x1800322b8  test    ebx, ebx
0x1800322ba  js      short loc_180032316
0x1800322bc  mov     rcx, [rdi+18h]; pSecurityDescriptor
0x1800322c0  mov     edx, 1; dwRevision
0x1800322c5  call    cs:__imp_InitializeSecurityDescriptor
0x1800322cb  test    eax, eax
0x1800322cd  jnz     short loc_1800322E5
0x1800322cf  call    cs:__imp_GetLastError
0x1800322d5  mov     ebx, eax
0x1800322d7  test    eax, eax
0x1800322d9  jle     short loc_1800322E1
0x1800322db  movzx   ebx, ax
0x1800322de  or      ebx, r15d
0x1800322e1  test    ebx, ebx
0x1800322e3  js      short loc_180032316
0x1800322e5  mov     r8, [rsi]; pDacl
0x1800322e8  xor     r9d, r9d; bDaclDefaulted
0x1800322eb  mov     rcx, [rdi+18h]; pSecurityDescriptor
0x1800322ef  lea     edx, [r9+1]; bDaclPresent
0x1800322f3  call    cs:__imp_SetSecurityDescriptorDacl
0x1800322f9  test    eax, eax
0x1800322fb  jnz     short loc_180032316
0x1800322fd  call    cs:__imp_GetLastError
0x180032303  mov     ebx, eax
0x180032305  test    eax, eax
0x180032307  jle     short loc_180032316
0x180032309  movzx   ebx, ax
0x18003230c  or      ebx, r15d
0x18003230f  jmp     short loc_180032316
0x180032311  mov     ebx, 8007000Eh
0x180032316  lea     r11, [rsp+80h+var_s0]
0x18003231e  mov     eax, ebx
0x180032320  mov     rbx, [r11+28h]
0x180032324  mov     rsi, [r11+30h]
0x180032328  mov     rsp, r11
0x18003232b  pop     r15
0x18003232d  pop     rdi
0x18003232e  pop     rbp
0x18003232f  retn
```
