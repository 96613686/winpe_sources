# IsCallingProcess

- ea: `0x140209650`
- end: `0x1402097b4`
- name: `IsCallingProcess`
- size: `356`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001e010`
- `0x14007eb00`
- `0x140095c90`
- `0x14009a210`
- `0x1401bd640`
- `0x1401c3a98`
- `0x1401f4dc4`
- `0x1401f4f5c`

## callees

- `0x140209650`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14020975b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140209772`
- `ntoskrnl!ExFreePoolWithTag` at `0x14020975b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140209772`
- `ntoskrnl!SeAccessCheckFromState` at `0x140209742`
- `ntoskrnl!SeAccessCheckFromState` at `0x140209742`
- `ntoskrnl!SeQueryInformationToken` at `0x1402096c0`
- `ntoskrnl!SeQueryInformationToken` at `0x1402096ea`
- `ntoskrnl!SeQueryInformationToken` at `0x1402096c0`
- `ntoskrnl!SeQueryInformationToken` at `0x1402096ea`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140209792`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140209792`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140209782`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140209782`
- `ntoskrnl!SeLockSubjectContext` at `0x1402096a7`
- `ntoskrnl!SeLockSubjectContext` at `0x1402096a7`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140209697`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140209697`

## pseudocode

```c
BOOLEAN __fastcall IsCallingProcess(PSECURITY_DESCRIPTOR SecurityDescriptor, char a2)
{
  BOOLEAN v4; // bl
  PVOID TokenInformation; // [rsp+50h] [rbp-30h] BYREF
  PVOID P; // [rsp+58h] [rbp-28h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+60h] [rbp-20h] BYREF
  int AccessStatus; // [rsp+B0h] [rbp+30h] BYREF
  DWORD GrantedAccess; // [rsp+B8h] [rbp+38h] BYREF

  GrantedAccess = 0;
  AccessStatus = 0;
  TokenInformation = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  v4 = 0;
  P = 0;
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  AccessStatus = SeQueryInformationToken(SubjectContext.PrimaryToken, TokenAccessInformation, &TokenInformation);
  if ( AccessStatus >= 0 )
  {
    if ( !a2
      || !SubjectContext.ClientToken
      || (AccessStatus = SeQueryInformationToken(SubjectContext.ClientToken, TokenAccessInformation, &P),
          AccessStatus >= 0) )
    {
      v4 = SeAccessCheckFromState(
             SecurityDescriptor,
             (PTOKEN_ACCESS_INFORMATION)TokenInformation,
             (PTOKEN_ACCESS_INFORMATION)P,
             1u,
             0,
             0,
             &GenericMapping,
             1,
             &GrantedAccess,
             &AccessStatus);
    }
  }
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  return v4;
}

```

## disassembly

```asm
0x140209650  mov     [rsp-18h+arg_0], rbx
0x140209655  push    rbp
0x140209656  push    rsi
0x140209657  push    rdi
0x140209658  mov     rbp, rsp
0x14020965b  sub     rsp, 80h
0x140209662  xorps   xmm0, xmm0
0x140209665  mov     [rbp+arg_18], 0
0x14020966c  mov     rsi, rcx
0x14020966f  mov     [rbp+arg_10], 0
0x140209676  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14020967a  mov     [rbp+TokenInformation], 0
0x140209682  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x140209686  mov     dil, dl
0x140209689  xor     bl, bl
0x14020968b  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x14020968f  mov     [rbp+P], 0
0x140209697  call    cs:__imp_SeCaptureSubjectContext
0x14020969e  nop     dword ptr [rax+rax+00h]
0x1402096a3  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1402096a7  call    cs:__imp_SeLockSubjectContext
0x1402096ae  nop     dword ptr [rax+rax+00h]
0x1402096b3  mov     rcx, [rbp+SubjectContext.PrimaryToken]; Token
0x1402096b7  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1402096bb  mov     edx, 16h; TokenInformationClass
0x1402096c0  call    cs:__imp_SeQueryInformationToken
0x1402096c7  nop     dword ptr [rax+rax+00h]
0x1402096cc  mov     [rbp+arg_10], eax
0x1402096cf  test    eax, eax
0x1402096d1  js      short loc_140209750
0x1402096d3  test    dil, dil
0x1402096d6  jz      short loc_1402096FD
0x1402096d8  mov     rcx, [rbp+SubjectContext.ClientToken]; Token
0x1402096dc  test    rcx, rcx
0x1402096df  jz      short loc_1402096FD
0x1402096e1  lea     r8, [rbp+P]; TokenInformation
0x1402096e5  mov     edx, 16h; TokenInformationClass
0x1402096ea  call    cs:__imp_SeQueryInformationToken
0x1402096f1  nop     dword ptr [rax+rax+00h]
0x1402096f6  mov     [rbp+arg_10], eax
0x1402096f9  test    eax, eax
0x1402096fb  js      short loc_140209750
0x1402096fd  mov     r8, [rbp+P]; ClientTokenInformation
0x140209701  lea     rax, [rbp+arg_10]
0x140209705  mov     rdx, [rbp+TokenInformation]; PrimaryTokenInformation
0x140209709  mov     r9d, 1; DesiredAccess
0x14020970f  mov     [rsp+80h+AccessStatus], rax; AccessStatus
0x140209714  mov     rcx, rsi; SecurityDescriptor
0x140209717  lea     rax, [rbp+arg_18]
0x14020971b  mov     [rsp+80h+GrantedAccess], rax; GrantedAccess
0x140209720  lea     rax, GenericMapping
0x140209727  mov     [rsp+80h+AccessMode], 1; AccessMode
0x14020972c  mov     [rsp+80h+GenericMapping], rax; GenericMapping
0x140209731  mov     [rsp+80h+Privileges], 0; Privileges
0x14020973a  mov     [rsp+80h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x140209742  call    cs:__imp_SeAccessCheckFromState
0x140209749  nop     dword ptr [rax+rax+00h]
0x14020974e  mov     bl, al
0x140209750  mov     rcx, [rbp+TokenInformation]; P
0x140209754  test    rcx, rcx
0x140209757  jz      short loc_140209767
0x140209759  xor     edx, edx; Tag
0x14020975b  call    cs:__imp_ExFreePoolWithTag
0x140209762  nop     dword ptr [rax+rax+00h]
0x140209767  mov     rcx, [rbp+P]; P
0x14020976b  test    rcx, rcx
0x14020976e  jz      short loc_14020977E
0x140209770  xor     edx, edx; Tag
0x140209772  call    cs:__imp_ExFreePoolWithTag
0x140209779  nop     dword ptr [rax+rax+00h]
0x14020977e  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140209782  call    cs:__imp_SeUnlockSubjectContext
0x140209789  nop     dword ptr [rax+rax+00h]
0x14020978e  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140209792  call    cs:__imp_SeReleaseSubjectContext
0x140209799  nop     dword ptr [rax+rax+00h]
0x14020979e  mov     al, bl
0x1402097a0  mov     rbx, [rsp+80h+arg_0]
0x1402097a8  add     rsp, 80h
0x1402097af  pop     rdi
0x1402097b0  pop     rsi
0x1402097b1  pop     rbp
0x1402097b2  retn
```
