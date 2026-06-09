# VfsAccessCheck

- ea: `0x14000e438`
- end: `0x14000e593`
- name: `VfsAccessCheck`
- size: `347`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400046bc`
- `0x1400049b4`
- `0x140004d1c`
- `0x14000502c`

## callees

- `0x14000e438`

## import_xrefs

- `ntoskrnl!SeAppendPrivileges` at `0x14000e527`
- `ntoskrnl!SeAppendPrivileges` at `0x14000e527`
- `ntoskrnl!SeFreePrivileges` at `0x14000e539`
- `ntoskrnl!SeFreePrivileges` at `0x14000e539`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14000e54c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14000e54c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000e48c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000e4c8`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000e48c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000e4c8`
- `ntoskrnl!SeLockSubjectContext` at `0x14000e4bc`
- `ntoskrnl!SeLockSubjectContext` at `0x14000e4bc`
- `ntoskrnl!SeAccessCheck` at `0x14000e50d`
- `ntoskrnl!SeAccessCheck` at `0x14000e50d`

## pseudocode

```c
__int64 __fastcall VfsAccessCheck(PSECURITY_DESCRIPTOR SecurityDescriptor, __int64 a2, int a3, char a4)
{
  __int64 v4; // r10
  unsigned int appended; // esi
  struct _ACCESS_STATE *v8; // rdi
  ACCESS_MASK v9; // ebx
  KPROCESSOR_MODE AccessMode; // r14
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v12; // bl
  PPRIVILEGE_SET Privileges; // [rsp+50h] [rbp-10h] BYREF
  int AccessStatus; // [rsp+A8h] [rbp+48h] BYREF
  DWORD GrantedAccess; // [rsp+B0h] [rbp+50h] BYREF

  v4 = *(_QWORD *)(a2 + 16);
  AccessStatus = 0;
  appended = 0;
  v8 = *(struct _ACCESS_STATE **)(*(_QWORD *)(v4 + 24) + 8LL);
  Privileges = 0;
  GrantedAccess = 0;
  v9 = a3 & ~v8->PreviouslyGrantedAccess;
  if ( v9 )
  {
    if ( SecurityDescriptor )
    {
      AccessMode = 1;
      if ( (*(_BYTE *)(v4 + 6) & 1) == 0 )
        AccessMode = *(_BYTE *)(a2 + 80);
      SeLockSubjectContext(&v8->SubjectSecurityContext);
      GenericMapping = IoGetFileObjectGenericMapping();
      v12 = SeAccessCheck(
              SecurityDescriptor,
              &v8->SubjectSecurityContext,
              1u,
              v9,
              0,
              &Privileges,
              GenericMapping,
              AccessMode,
              &GrantedAccess,
              &AccessStatus);
      if ( Privileges )
      {
        appended = SeAppendPrivileges(v8, Privileges);
        SeFreePrivileges(Privileges);
        Privileges = 0;
      }
      SeUnlockSubjectContext(&v8->SubjectSecurityContext);
      if ( !v12 )
        return (unsigned int)AccessStatus;
      v9 = GrantedAccess;
    }
    else
    {
      if ( (v9 & 0x2000000) != 0 )
        v9 = IoGetFileObjectGenericMapping()->GenericAll | v9 & 0xFDFFFFFF;
      GrantedAccess = v9;
    }
    if ( !a4 )
    {
      v8->PreviouslyGrantedAccess |= v9;
      v8->RemainingDesiredAccess &= ~(GrantedAccess | 0x2000000);
    }
  }
  return appended;
}

```

## disassembly

```asm
0x14000e438  mov     [rsp-38h+arg_0], rbx
0x14000e43d  push    rbp
0x14000e43e  push    rsi
0x14000e43f  push    rdi
0x14000e440  push    r12
0x14000e442  push    r13
0x14000e444  push    r14
0x14000e446  push    r15
0x14000e448  mov     rbp, rsp
0x14000e44b  sub     rsp, 60h
0x14000e44f  mov     r10, [rdx+10h]
0x14000e453  xor     r14d, r14d
0x14000e456  mov     [rbp+arg_8], r14d
0x14000e45a  mov     r13b, r9b
0x14000e45d  mov     r12, rcx
0x14000e460  mov     esi, r14d
0x14000e463  mov     rax, [r10+18h]
0x14000e467  mov     rdi, [rax+8]
0x14000e46b  mov     [rbp+var_10], r14
0x14000e46f  mov     [rbp+arg_10], r14d
0x14000e473  mov     ebx, [rdi+14h]
0x14000e476  not     ebx
0x14000e478  and     ebx, r8d
0x14000e47b  jz      loc_14000E578
0x14000e481  test    rcx, rcx
0x14000e484  jnz     short loc_14000E4A7
0x14000e486  bt      ebx, 19h
0x14000e48a  jnb     short loc_14000E49F
0x14000e48c  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000e493  nop     dword ptr [rax+rax+00h]
0x14000e498  btr     ebx, 19h
0x14000e49c  or      ebx, [rax+0Ch]
0x14000e49f  mov     [rbp+arg_10], ebx
0x14000e4a2  jmp     loc_14000E55F
0x14000e4a7  test    byte ptr [r10+6], 1
0x14000e4ac  mov     r14b, 1
0x14000e4af  jnz     short loc_14000E4B5
0x14000e4b1  mov     r14b, [rdx+50h]
0x14000e4b5  lea     r15, [rdi+20h]
0x14000e4b9  mov     rcx, r15; SubjectContext
0x14000e4bc  call    cs:__imp_SeLockSubjectContext
0x14000e4c3  nop     dword ptr [rax+rax+00h]
0x14000e4c8  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000e4cf  nop     dword ptr [rax+rax+00h]
0x14000e4d4  lea     rcx, [rbp+arg_8]
0x14000e4d8  mov     r9d, ebx; DesiredAccess
0x14000e4db  mov     [rsp+60h+AccessStatus], rcx; AccessStatus
0x14000e4e0  mov     r8b, 1; SubjectContextLocked
0x14000e4e3  lea     rcx, [rbp+arg_10]
0x14000e4e7  mov     rdx, r15; SubjectSecurityContext
0x14000e4ea  mov     [rsp+60h+GrantedAccess], rcx; GrantedAccess
0x14000e4ef  mov     rcx, r12; SecurityDescriptor
0x14000e4f2  mov     [rsp+60h+AccessMode], r14b; AccessMode
0x14000e4f7  xor     r14d, r14d
0x14000e4fa  mov     [rsp+60h+GenericMapping], rax; GenericMapping
0x14000e4ff  lea     rax, [rbp+var_10]
0x14000e503  mov     [rsp+60h+Privileges], rax; Privileges
0x14000e508  mov     [rsp+60h+PreviouslyGrantedAccess], r14d; PreviouslyGrantedAccess
0x14000e50d  call    cs:__imp_SeAccessCheck
0x14000e514  nop     dword ptr [rax+rax+00h]
0x14000e519  mov     rdx, [rbp+var_10]; Privileges
0x14000e51d  mov     bl, al
0x14000e51f  test    rdx, rdx
0x14000e522  jz      short loc_14000E549
0x14000e524  mov     rcx, rdi; AccessState
0x14000e527  call    cs:__imp_SeAppendPrivileges
0x14000e52e  nop     dword ptr [rax+rax+00h]
0x14000e533  mov     rcx, [rbp+var_10]; Privileges
0x14000e537  mov     esi, eax
0x14000e539  call    cs:__imp_SeFreePrivileges
0x14000e540  nop     dword ptr [rax+rax+00h]
0x14000e545  mov     [rbp+var_10], r14
0x14000e549  mov     rcx, r15; SubjectContext
0x14000e54c  call    cs:__imp_SeUnlockSubjectContext
0x14000e553  nop     dword ptr [rax+rax+00h]
0x14000e558  test    bl, bl
0x14000e55a  jz      short loc_14000E575
0x14000e55c  mov     ebx, [rbp+arg_10]
0x14000e55f  test    r13b, r13b
0x14000e562  jnz     short loc_14000E578
0x14000e564  or      [rdi+14h], ebx
0x14000e567  mov     eax, [rbp+arg_10]
0x14000e56a  bts     eax, 19h
0x14000e56e  not     eax
0x14000e570  and     [rdi+10h], eax
0x14000e573  jmp     short loc_14000E578
0x14000e575  mov     esi, [rbp+arg_8]
0x14000e578  mov     rbx, [rsp+60h+arg_0]
0x14000e580  mov     eax, esi
0x14000e582  add     rsp, 60h
0x14000e586  pop     r15
0x14000e588  pop     r14
0x14000e58a  pop     r13
0x14000e58c  pop     r12
0x14000e58e  pop     rdi
0x14000e58f  pop     rsi
0x14000e590  pop     rbp
0x14000e591  retn
```
