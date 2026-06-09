# SrpIsTokenService

- ea: `0x140032e40`
- end: `0x140032f52`
- name: `SrpIsTokenService`
- size: `274`
- prototype: `__int64 __fastcall(void *, BOOLEAN *)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140024280`
- `0x14002da5c`
- `0x140034550`
- `0x1400373b0`

## callees

- `0x140032e40`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140032e7d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140032e7d`
- `ntoskrnl!ObfDereferenceObject` at `0x140032f44`
- `ntoskrnl!ObfDereferenceObject` at `0x140032f44`
- `ntoskrnl!SeAccessCheck` at `0x140032f03`
- `ntoskrnl!SeAccessCheck` at `0x140032f03`

## pseudocode

```c
__int64 __fastcall SrpIsTokenService(void *a1, BOOLEAN *a2)
{
  NTSTATUS v3; // eax
  PVOID v4; // rdi
  unsigned int v5; // ebx
  BOOLEAN v6; // al
  PVOID Object; // [rsp+50h] [rbp-48h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectSecurityContext; // [rsp+58h] [rbp-40h] BYREF
  int AccessStatus; // [rsp+B0h] [rbp+18h] BYREF
  DWORD GrantedAccess; // [rsp+B8h] [rbp+20h] BYREF

  Object = 0;
  memset(&SubjectSecurityContext, 0, sizeof(SubjectSecurityContext));
  v3 = ObReferenceObjectByHandle(a1, 0, 0, 0, &Object, 0);
  v4 = Object;
  v5 = v3;
  if ( v3 >= 0 )
  {
    SubjectSecurityContext.ClientToken = 0;
    *(_QWORD *)&SubjectSecurityContext.ImpersonationLevel = 0;
    SubjectSecurityContext.ProcessAuditId = 0;
    SubjectSecurityContext.PrimaryToken = Object;
    AccessStatus = 0;
    GrantedAccess = 0;
    v6 = SeAccessCheck(
           qword_14000A378,
           &SubjectSecurityContext,
           0,
           1u,
           0,
           0,
           (PGENERIC_MAPPING)&GenericMapping,
           1,
           &GrantedAccess,
           &AccessStatus);
    v5 = AccessStatus;
    if ( !v6 )
    {
      if ( AccessStatus != -1073741790 )
        goto LABEL_6;
      v5 = 0;
    }
    *a2 = v6;
  }
LABEL_6:
  if ( v4 )
    ObfDereferenceObject(v4);
  return v5;
}

```

## disassembly

```asm
0x140032e40  mov     [rsp+arg_0], rbx
0x140032e45  push    rbp
0x140032e46  push    rsi
0x140032e47  push    rdi
0x140032e48  sub     rsp, 80h
0x140032e4f  xorps   xmm0, xmm0
0x140032e52  lea     rax, [rsp+98h+var_48]
0x140032e57  xor     ebp, ebp
0x140032e59  mov     rsi, rdx
0x140032e5c  mov     [rsp+98h+HandleInformation], rbp; HandleInformation
0x140032e61  xor     r9d, r9d; AccessMode
0x140032e64  xor     r8d, r8d; ObjectType
0x140032e67  mov     [rsp+98h+Object], rax; Object
0x140032e6c  xor     edx, edx; DesiredAccess
0x140032e6e  mov     [rsp+98h+var_48], rbp
0x140032e73  movups  xmmword ptr [rsp+98h+SubjectSecurityContext.ClientToken], xmm0
0x140032e78  movups  xmmword ptr [rsp+98h+SubjectSecurityContext.PrimaryToken], xmm0
0x140032e7d  call    cs:__imp_ObReferenceObjectByHandle
0x140032e84  nop     dword ptr [rax+rax+00h]
0x140032e89  mov     rdi, [rsp+98h+var_48]
0x140032e8e  mov     ebx, eax
0x140032e90  test    eax, eax
0x140032e92  js      loc_140032F26
0x140032e98  lea     rax, [rsp+98h+arg_10]
0x140032ea0  mov     [rsp+98h+SubjectSecurityContext.ClientToken], rbp
0x140032ea5  mov     [rsp+98h+AccessStatus], rax; AccessStatus
0x140032eaa  lea     rdx, [rsp+98h+SubjectSecurityContext]; SubjectSecurityContext
0x140032eaf  lea     rax, [rsp+98h+arg_18]
0x140032eb7  mov     qword ptr [rsp+98h+SubjectSecurityContext.ImpersonationLevel], rbp
0x140032ebc  mov     [rsp+98h+GrantedAccess], rax; GrantedAccess
0x140032ec1  lea     rcx, qword_14000A378; SecurityDescriptor
0x140032ec8  mov     [rsp+98h+AccessMode], 1; AccessMode
0x140032ecd  lea     rax, GenericMapping
0x140032ed4  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x140032ed9  mov     r9d, 1; DesiredAccess
0x140032edf  mov     [rsp+98h+HandleInformation], rbp; Privileges
0x140032ee4  xor     r8d, r8d; SubjectContextLocked
0x140032ee7  mov     dword ptr [rsp+98h+Object], ebp; PreviouslyGrantedAccess
0x140032eeb  mov     [rsp+98h+SubjectSecurityContext.ProcessAuditId], rbp
0x140032ef0  mov     [rsp+98h+SubjectSecurityContext.PrimaryToken], rdi
0x140032ef5  mov     [rsp+98h+arg_10], ebp
0x140032efc  mov     [rsp+98h+arg_18], ebp
0x140032f03  call    cs:__imp_SeAccessCheck
0x140032f0a  nop     dword ptr [rax+rax+00h]
0x140032f0f  mov     ebx, [rsp+98h+arg_10]
0x140032f16  test    al, al
0x140032f18  jnz     short loc_140032F24
0x140032f1a  cmp     ebx, 0C0000022h
0x140032f20  jnz     short loc_140032F26
0x140032f22  mov     ebx, ebp
0x140032f24  mov     [rsi], al
0x140032f26  test    rdi, rdi
0x140032f29  jnz     short loc_140032F41
0x140032f2b  mov     eax, ebx
0x140032f2d  mov     rbx, [rsp+98h+arg_0]
0x140032f35  add     rsp, 80h
0x140032f3c  pop     rdi
0x140032f3d  pop     rsi
0x140032f3e  pop     rbp
0x140032f3f  retn
0x140032f41  mov     rcx, rdi; Object
0x140032f44  call    cs:__imp_ObfDereferenceObject
0x140032f4b  nop     dword ptr [rax+rax+00h]
0x140032f50  jmp     short loc_140032F2B
```
