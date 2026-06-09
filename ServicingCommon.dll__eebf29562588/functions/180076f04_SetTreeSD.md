# SetTreeSD

- ea: `0x180076f04`
- end: `0x18007704f`
- name: `SetTreeSD`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180076cfc`

## callees

- `0x180076f04`
- `0x1800a0020`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180076fd5`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180076fd5`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180076fad`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180076fad`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180076f5e`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180076f5e`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180076f85`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180076f85`

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
  v4 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, PSID, PSID, PACL, PACL, _DWORD, _QWORD, int, _QWORD))qword_1800D4D90;
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
0x180076f04  mov     rax, rsp
0x180076f07  mov     [rax+8], rbx
0x180076f0b  mov     [rax+18h], rsi
0x180076f0f  mov     [rax+20h], r9
0x180076f13  mov     [rax+10h], edx
0x180076f16  push    rbp
0x180076f17  push    rdi
0x180076f18  push    r12
0x180076f1a  push    r14
0x180076f1c  push    r15
0x180076f1e  mov     rbp, rsp
0x180076f21  sub     rsp, 80h
0x180076f28  mov     r14, cs:qword_1800D4D90
0x180076f2f  lea     rdx, [rbp+pOwner]; pOwner
0x180076f33  xor     r15d, r15d
0x180076f36  mov     rdi, r8
0x180076f39  mov     rsi, rcx
0x180076f3c  mov     [rbp+pOwner], r15
0x180076f40  mov     rcx, rdi; pSecurityDescriptor
0x180076f43  mov     [rbp+pGroup], r15
0x180076f47  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x180076f4b  mov     [rbp+pDacl], r15
0x180076f4f  mov     [rbp+pSacl], r15
0x180076f53  mov     ebx, r15d
0x180076f56  mov     [rbp+bDaclPresent], r15d
0x180076f5a  mov     [rbp+bOwnerDefaulted], r15d
0x180076f5e  call    cs:__imp_GetSecurityDescriptorOwner
0x180076f65  nop     dword ptr [rax+rax+00h]
0x180076f6a  lea     r12d, [r15+1]
0x180076f6e  test    eax, eax
0x180076f70  jz      short loc_180076F7A
0x180076f72  cmp     [rbp+pOwner], r15
0x180076f76  cmovnz  ebx, r12d
0x180076f7a  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x180076f7e  mov     rcx, rdi; pSecurityDescriptor
0x180076f81  lea     rdx, [rbp+pGroup]; pGroup
0x180076f85  call    cs:__imp_GetSecurityDescriptorGroup
0x180076f8c  nop     dword ptr [rax+rax+00h]
0x180076f91  test    eax, eax
0x180076f93  jz      short loc_180076F9E
0x180076f95  cmp     [rbp+pGroup], r15
0x180076f99  jz      short loc_180076F9E
0x180076f9b  or      ebx, 2
0x180076f9e  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x180076fa2  mov     rcx, rdi; pSecurityDescriptor
0x180076fa5  lea     r8, [rbp+pDacl]; pDacl
0x180076fa9  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180076fad  call    cs:__imp_GetSecurityDescriptorDacl
0x180076fb4  nop     dword ptr [rax+rax+00h]
0x180076fb9  test    eax, eax
0x180076fbb  jz      short loc_180076FC6
0x180076fbd  cmp     [rbp+bDaclPresent], r15d
0x180076fc1  jz      short loc_180076FC6
0x180076fc3  or      ebx, 4
0x180076fc6  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x180076fca  mov     rcx, rdi; pSecurityDescriptor
0x180076fcd  lea     r8, [rbp+pSacl]; pSacl
0x180076fd1  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x180076fd5  call    cs:__imp_GetSecurityDescriptorSacl
0x180076fdc  nop     dword ptr [rax+rax+00h]
0x180076fe1  test    eax, eax
0x180076fe3  jz      short loc_180076FEE
0x180076fe5  cmp     [rbp+bDaclPresent], r15d
0x180076fe9  jz      short loc_180076FEE
0x180076feb  or      ebx, 8
0x180076fee  mov     rcx, [rbp+pSacl]
0x180076ff2  mov     r8d, ebx
0x180076ff5  mov     r9, [rbp+pOwner]
0x180076ff9  mov     edx, r12d
0x180076ffc  mov     [rsp+80h+var_30], r15
0x180077001  mov     rax, r14
0x180077004  mov     [rsp+80h+var_38], r12d
0x180077009  mov     [rsp+80h+var_40], r15
0x18007700e  mov     [rsp+80h+var_48], r15d
0x180077013  mov     [rsp+80h+var_50], rcx
0x180077018  mov     rcx, [rbp+pDacl]
0x18007701c  mov     [rsp+80h+var_58], rcx
0x180077021  mov     rcx, [rbp+pGroup]
0x180077025  mov     [rsp+80h+var_60], rcx
0x18007702a  mov     rcx, rsi
0x18007702d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077032  lea     r11, [rsp+80h+var_s0]
0x18007703a  mov     rbx, [r11+30h]
0x18007703e  mov     rsi, [r11+40h]
0x180077042  mov     rsp, r11
0x180077045  pop     r15
0x180077047  pop     r14
0x180077049  pop     r12
0x18007704b  pop     rdi
0x18007704c  pop     rbp
0x18007704d  retn
```
