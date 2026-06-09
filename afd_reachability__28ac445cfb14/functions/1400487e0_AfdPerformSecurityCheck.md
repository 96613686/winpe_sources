# AfdPerformSecurityCheck

- ea: `0x1400487e0`
- end: `0x140048926`
- name: `AfdPerformSecurityCheck`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400218d4`

## callees

- `0x1400487e0`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140048812`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14004885b`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140048812`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14004885b`
- `ntoskrnl!RtlMapGenericMask` at `0x140048829`
- `ntoskrnl!RtlMapGenericMask` at `0x140048829`
- `ntoskrnl!SeLockSubjectContext` at `0x140048844`
- `ntoskrnl!SeLockSubjectContext` at `0x140048844`
- `ntoskrnl!SeAccessCheck` at `0x1400488a9`
- `ntoskrnl!SeAccessCheck` at `0x1400488a9`
- `ntoskrnl!SeAppendPrivileges` at `0x1400488c4`
- `ntoskrnl!SeAppendPrivileges` at `0x1400488c4`
- `ntoskrnl!SeFreePrivileges` at `0x1400488d5`
- `ntoskrnl!SeFreePrivileges` at `0x1400488d5`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140048902`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140048902`

## pseudocode

```c
BOOLEAN __fastcall AfdPerformSecurityCheck(__int64 a1, __int64 a2, int *a3)
{
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  struct _ACCESS_STATE *v7; // rdi
  bool v8; // zf
  KPROCESSOR_MODE AccessMode; // bl
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v11; // bl
  PPRIVILEGE_SET Privileges; // [rsp+50h] [rbp-28h] BYREF
  DWORD GrantedAccess; // [rsp+88h] [rbp+10h] BYREF
  DWORD AccessMask; // [rsp+98h] [rbp+20h] BYREF

  Privileges = 0;
  GrantedAccess = 0;
  AccessMask = 0x10000000;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
  v7 = *(struct _ACCESS_STATE **)(*(_QWORD *)(a2 + 8) + 8LL);
  SeLockSubjectContext(&v7->SubjectSecurityContext);
  v8 = (*(_BYTE *)(a2 + 2) & 1) == 0;
  AccessMode = 1;
  if ( v8 )
    AccessMode = *(_BYTE *)(a1 + 64);
  GenericMapping = IoGetFileObjectGenericMapping();
  v11 = SeAccessCheck(
          AfdAdminSecurityDescriptor,
          &v7->SubjectSecurityContext,
          1u,
          AccessMask,
          0,
          &Privileges,
          GenericMapping,
          AccessMode,
          &GrantedAccess,
          a3);
  if ( Privileges )
  {
    SeAppendPrivileges(v7, Privileges);
    SeFreePrivileges(Privileges);
  }
  if ( v11 )
  {
    v7->PreviouslyGrantedAccess |= GrantedAccess;
    v7->RemainingDesiredAccess &= ~(GrantedAccess | 0x2000000);
  }
  SeUnlockSubjectContext(&v7->SubjectSecurityContext);
  return v11;
}

```

## disassembly

```asm
0x1400487e0  mov     rax, rsp
0x1400487e3  mov     [rax+8], rbx
0x1400487e7  mov     [rax+18h], rbp
0x1400487eb  push    rsi
0x1400487ec  push    rdi
0x1400487ed  push    r14
0x1400487ef  sub     rsp, 60h
0x1400487f3  mov     r14, r8
0x1400487f6  mov     qword ptr [rax-28h], 0
0x1400487fe  mov     rbx, rdx
0x140048801  mov     dword ptr [rax+10h], 0
0x140048808  mov     rbp, rcx
0x14004880b  mov     dword ptr [rax+20h], 10000000h
0x140048812  call    cs:__imp_IoGetFileObjectGenericMapping
0x140048819  nop     dword ptr [rax+rax+00h]
0x14004881e  mov     rdx, rax; GenericMapping
0x140048821  lea     rcx, [rsp+78h+AccessMask]; AccessMask
0x140048829  call    cs:__imp_RtlMapGenericMask
0x140048830  nop     dword ptr [rax+rax+00h]
0x140048835  mov     rax, [rbx+8]
0x140048839  mov     rdi, [rax+8]
0x14004883d  lea     rsi, [rdi+20h]
0x140048841  mov     rcx, rsi; SubjectContext
0x140048844  call    cs:__imp_SeLockSubjectContext
0x14004884b  nop     dword ptr [rax+rax+00h]
0x140048850  test    byte ptr [rbx+2], 1
0x140048854  mov     bl, 1
0x140048856  jnz     short loc_14004885B
0x140048858  mov     bl, [rbp+40h]
0x14004885b  call    cs:__imp_IoGetFileObjectGenericMapping
0x140048862  nop     dword ptr [rax+rax+00h]
0x140048867  mov     r9d, [rsp+78h+AccessMask]; DesiredAccess
0x14004886f  lea     rcx, [rsp+78h+arg_8]
0x140048877  mov     [rsp+78h+AccessStatus], r14; AccessStatus
0x14004887c  mov     r8b, 1; SubjectContextLocked
0x14004887f  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x140048884  mov     rdx, rsi; SubjectSecurityContext
0x140048887  mov     rcx, cs:AfdAdminSecurityDescriptor; SecurityDescriptor
0x14004888e  mov     [rsp+78h+AccessMode], bl; AccessMode
0x140048892  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x140048897  lea     rax, [rsp+78h+var_28]
0x14004889c  mov     [rsp+78h+Privileges], rax; Privileges
0x1400488a1  mov     [rsp+78h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x1400488a9  call    cs:__imp_SeAccessCheck
0x1400488b0  nop     dword ptr [rax+rax+00h]
0x1400488b5  mov     rdx, [rsp+78h+var_28]; Privileges
0x1400488ba  mov     bl, al
0x1400488bc  test    rdx, rdx
0x1400488bf  jz      short loc_1400488E1
0x1400488c1  mov     rcx, rdi; AccessState
0x1400488c4  call    cs:__imp_SeAppendPrivileges
0x1400488cb  nop     dword ptr [rax+rax+00h]
0x1400488d0  mov     rcx, [rsp+78h+var_28]; Privileges
0x1400488d5  call    cs:__imp_SeFreePrivileges
0x1400488dc  nop     dword ptr [rax+rax+00h]
0x1400488e1  test    bl, bl
0x1400488e3  jz      short loc_1400488FF
0x1400488e5  mov     eax, [rsp+78h+arg_8]
0x1400488ec  or      [rdi+14h], eax
0x1400488ef  mov     eax, [rsp+78h+arg_8]
0x1400488f6  bts     eax, 19h
0x1400488fa  not     eax
0x1400488fc  and     [rdi+10h], eax
0x1400488ff  mov     rcx, rsi; SubjectContext
0x140048902  call    cs:__imp_SeUnlockSubjectContext
0x140048909  nop     dword ptr [rax+rax+00h]
0x14004890e  lea     r11, [rsp+78h+var_18]
0x140048913  mov     al, bl
0x140048915  mov     rbx, [r11+20h]
0x140048919  mov     rbp, [r11+30h]
0x14004891d  mov     rsp, r11
0x140048920  pop     r14
0x140048922  pop     rdi
0x140048923  pop     rsi
0x140048924  retn
```
