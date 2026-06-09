# AfdPerformSecurityCheck

- ea: `0x140048860`
- end: `0x1400489a6`
- name: `AfdPerformSecurityCheck`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400218d4`

## callees

- `0x140048860`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140048892`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400488db`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140048892`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400488db`
- `ntoskrnl!RtlMapGenericMask` at `0x1400488a9`
- `ntoskrnl!RtlMapGenericMask` at `0x1400488a9`
- `ntoskrnl!SeLockSubjectContext` at `0x1400488c4`
- `ntoskrnl!SeLockSubjectContext` at `0x1400488c4`
- `ntoskrnl!SeAccessCheck` at `0x140048929`
- `ntoskrnl!SeAccessCheck` at `0x140048929`
- `ntoskrnl!SeAppendPrivileges` at `0x140048944`
- `ntoskrnl!SeAppendPrivileges` at `0x140048944`
- `ntoskrnl!SeFreePrivileges` at `0x140048955`
- `ntoskrnl!SeFreePrivileges` at `0x140048955`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140048982`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140048982`

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
0x140048860  mov     rax, rsp
0x140048863  mov     [rax+8], rbx
0x140048867  mov     [rax+18h], rbp
0x14004886b  push    rsi
0x14004886c  push    rdi
0x14004886d  push    r14
0x14004886f  sub     rsp, 60h
0x140048873  mov     r14, r8
0x140048876  mov     qword ptr [rax-28h], 0
0x14004887e  mov     rbx, rdx
0x140048881  mov     dword ptr [rax+10h], 0
0x140048888  mov     rbp, rcx
0x14004888b  mov     dword ptr [rax+20h], 10000000h
0x140048892  call    cs:__imp_IoGetFileObjectGenericMapping
0x140048899  nop     dword ptr [rax+rax+00h]
0x14004889e  mov     rdx, rax; GenericMapping
0x1400488a1  lea     rcx, [rsp+78h+AccessMask]; AccessMask
0x1400488a9  call    cs:__imp_RtlMapGenericMask
0x1400488b0  nop     dword ptr [rax+rax+00h]
0x1400488b5  mov     rax, [rbx+8]
0x1400488b9  mov     rdi, [rax+8]
0x1400488bd  lea     rsi, [rdi+20h]
0x1400488c1  mov     rcx, rsi; SubjectContext
0x1400488c4  call    cs:__imp_SeLockSubjectContext
0x1400488cb  nop     dword ptr [rax+rax+00h]
0x1400488d0  test    byte ptr [rbx+2], 1
0x1400488d4  mov     bl, 1
0x1400488d6  jnz     short loc_1400488DB
0x1400488d8  mov     bl, [rbp+40h]
0x1400488db  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400488e2  nop     dword ptr [rax+rax+00h]
0x1400488e7  mov     r9d, [rsp+78h+AccessMask]; DesiredAccess
0x1400488ef  lea     rcx, [rsp+78h+arg_8]
0x1400488f7  mov     [rsp+78h+AccessStatus], r14; AccessStatus
0x1400488fc  mov     r8b, 1; SubjectContextLocked
0x1400488ff  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x140048904  mov     rdx, rsi; SubjectSecurityContext
0x140048907  mov     rcx, cs:AfdAdminSecurityDescriptor; SecurityDescriptor
0x14004890e  mov     [rsp+78h+AccessMode], bl; AccessMode
0x140048912  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x140048917  lea     rax, [rsp+78h+var_28]
0x14004891c  mov     [rsp+78h+Privileges], rax; Privileges
0x140048921  mov     [rsp+78h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x140048929  call    cs:__imp_SeAccessCheck
0x140048930  nop     dword ptr [rax+rax+00h]
0x140048935  mov     rdx, [rsp+78h+var_28]; Privileges
0x14004893a  mov     bl, al
0x14004893c  test    rdx, rdx
0x14004893f  jz      short loc_140048961
0x140048941  mov     rcx, rdi; AccessState
0x140048944  call    cs:__imp_SeAppendPrivileges
0x14004894b  nop     dword ptr [rax+rax+00h]
0x140048950  mov     rcx, [rsp+78h+var_28]; Privileges
0x140048955  call    cs:__imp_SeFreePrivileges
0x14004895c  nop     dword ptr [rax+rax+00h]
0x140048961  test    bl, bl
0x140048963  jz      short loc_14004897F
0x140048965  mov     eax, [rsp+78h+arg_8]
0x14004896c  or      [rdi+14h], eax
0x14004896f  mov     eax, [rsp+78h+arg_8]
0x140048976  bts     eax, 19h
0x14004897a  not     eax
0x14004897c  and     [rdi+10h], eax
0x14004897f  mov     rcx, rsi; SubjectContext
0x140048982  call    cs:__imp_SeUnlockSubjectContext
0x140048989  nop     dword ptr [rax+rax+00h]
0x14004898e  lea     r11, [rsp+78h+var_18]
0x140048993  mov     al, bl
0x140048995  mov     rbx, [r11+20h]
0x140048999  mov     rbp, [r11+30h]
0x14004899d  mov     rsp, r11
0x1400489a0  pop     r14
0x1400489a2  pop     rdi
0x1400489a3  pop     rsi
0x1400489a4  retn
```
