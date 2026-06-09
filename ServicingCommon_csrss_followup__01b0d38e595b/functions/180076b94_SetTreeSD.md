# SetTreeSD

- ea: `0x180076b94`
- end: `0x180076cdf`
- name: `SetTreeSD`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007698c`

## callees

- `0x180076b94`
- `0x18009e020`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180076c65`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180076c65`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180076c3d`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180076c3d`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180076bee`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180076bee`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180076c15`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180076c15`

## pseudocode

```c
__int64 __fastcall SetTreeSD(__int64 a1, __int64 a2, void *a3, __int64 a4)
{
  __int64 (__fastcall *v4)(__int64, __int64, _QWORD, PSID, PSID, PACL, PACL, _DWORD, _QWORD, int, _QWORD); // r14
  unsigned int v7; // ebx
  PSID pGroup; // [rsp+60h] [rbp-20h] BYREF
  PSID pOwner; // [rsp+68h] [rbp-18h] BYREF
  PACL pSacl; // [rsp+70h] [rbp-10h] BYREF
  PACL pDacl; // [rsp+78h] [rbp-8h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+B8h] [rbp+38h] BYREF
  WINBOOL bDaclPresent; // [rsp+C8h] [rbp+48h] BYREF
  int v15; // [rsp+CCh] [rbp+4Ch]

  v15 = HIDWORD(a4);
  v4 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, PSID, PSID, PACL, PACL, _DWORD, _QWORD, int, _QWORD))qword_1800D2DA0;
  pOwner = 0;
  pGroup = 0;
  pDacl = 0;
  pSacl = 0;
  v7 = 0;
  bDaclPresent = 0;
  bOwnerDefaulted = 0;
  if ( GetSecurityDescriptorOwner(a3, &pOwner, &bOwnerDefaulted) )
    v7 = pOwner != 0;
  if ( GetSecurityDescriptorGroup(a3, &pGroup, &bOwnerDefaulted) && pGroup )
    v7 |= 2u;
  if ( GetSecurityDescriptorDacl(a3, &bDaclPresent, &pDacl, &bOwnerDefaulted) && bDaclPresent )
    v7 |= 4u;
  if ( GetSecurityDescriptorSacl(a3, &bDaclPresent, &pSacl, &bOwnerDefaulted) && bDaclPresent )
    v7 |= 8u;
  return v4(a1, 1, v7, pOwner, pGroup, pDacl, pSacl, 0, 0, 1, 0);
}

```

## disassembly

```asm
0x180076b94  mov     rax, rsp
0x180076b97  mov     [rax+8], rbx
0x180076b9b  mov     [rax+18h], rsi
0x180076b9f  mov     [rax+20h], r9
0x180076ba3  mov     [rax+10h], edx
0x180076ba6  push    rbp
0x180076ba7  push    rdi
0x180076ba8  push    r12
0x180076baa  push    r14
0x180076bac  push    r15
0x180076bae  mov     rbp, rsp
0x180076bb1  sub     rsp, 80h
0x180076bb8  mov     r14, cs:qword_1800D2DA0
0x180076bbf  lea     rdx, [rbp+pOwner]; pOwner
0x180076bc3  xor     r15d, r15d
0x180076bc6  mov     rdi, r8
0x180076bc9  mov     rsi, rcx
0x180076bcc  mov     [rbp+pOwner], r15
0x180076bd0  mov     rcx, rdi; pSecurityDescriptor
0x180076bd3  mov     [rbp+pGroup], r15
0x180076bd7  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x180076bdb  mov     [rbp+pDacl], r15
0x180076bdf  mov     [rbp+pSacl], r15
0x180076be3  mov     ebx, r15d
0x180076be6  mov     [rbp+bDaclPresent], r15d
0x180076bea  mov     [rbp+bOwnerDefaulted], r15d
0x180076bee  call    cs:__imp_GetSecurityDescriptorOwner
0x180076bf5  nop     dword ptr [rax+rax+00h]
0x180076bfa  lea     r12d, [r15+1]
0x180076bfe  test    eax, eax
0x180076c00  jz      short loc_180076C0A
0x180076c02  cmp     [rbp+pOwner], r15
0x180076c06  cmovnz  ebx, r12d
0x180076c0a  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x180076c0e  mov     rcx, rdi; pSecurityDescriptor
0x180076c11  lea     rdx, [rbp+pGroup]; pGroup
0x180076c15  call    cs:__imp_GetSecurityDescriptorGroup
0x180076c1c  nop     dword ptr [rax+rax+00h]
0x180076c21  test    eax, eax
0x180076c23  jz      short loc_180076C2E
0x180076c25  cmp     [rbp+pGroup], r15
0x180076c29  jz      short loc_180076C2E
0x180076c2b  or      ebx, 2
0x180076c2e  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x180076c32  mov     rcx, rdi; pSecurityDescriptor
0x180076c35  lea     r8, [rbp+pDacl]; pDacl
0x180076c39  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180076c3d  call    cs:__imp_GetSecurityDescriptorDacl
0x180076c44  nop     dword ptr [rax+rax+00h]
0x180076c49  test    eax, eax
0x180076c4b  jz      short loc_180076C56
0x180076c4d  cmp     [rbp+bDaclPresent], r15d
0x180076c51  jz      short loc_180076C56
0x180076c53  or      ebx, 4
0x180076c56  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x180076c5a  mov     rcx, rdi; pSecurityDescriptor
0x180076c5d  lea     r8, [rbp+pSacl]; pSacl
0x180076c61  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x180076c65  call    cs:__imp_GetSecurityDescriptorSacl
0x180076c6c  nop     dword ptr [rax+rax+00h]
0x180076c71  test    eax, eax
0x180076c73  jz      short loc_180076C7E
0x180076c75  cmp     [rbp+bDaclPresent], r15d
0x180076c79  jz      short loc_180076C7E
0x180076c7b  or      ebx, 8
0x180076c7e  mov     rcx, [rbp+pSacl]
0x180076c82  mov     r8d, ebx
0x180076c85  mov     r9, [rbp+pOwner]
0x180076c89  mov     edx, r12d
0x180076c8c  mov     [rsp+80h+var_30], r15
0x180076c91  mov     rax, r14
0x180076c94  mov     [rsp+80h+var_38], r12d
0x180076c99  mov     [rsp+80h+var_40], r15
0x180076c9e  mov     [rsp+80h+var_48], r15d
0x180076ca3  mov     [rsp+80h+var_50], rcx
0x180076ca8  mov     rcx, [rbp+pDacl]
0x180076cac  mov     [rsp+80h+var_58], rcx
0x180076cb1  mov     rcx, [rbp+pGroup]
0x180076cb5  mov     [rsp+80h+var_60], rcx
0x180076cba  mov     rcx, rsi
0x180076cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076cc2  lea     r11, [rsp+80h+var_s0]
0x180076cca  mov     rbx, [r11+30h]
0x180076cce  mov     rsi, [r11+40h]
0x180076cd2  mov     rsp, r11
0x180076cd5  pop     r15
0x180076cd7  pop     r14
0x180076cd9  pop     r12
0x180076cdb  pop     rdi
0x180076cdc  pop     rbp
0x180076cdd  retn
```
