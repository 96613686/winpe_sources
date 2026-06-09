# ApplySecurityAttributesToWinsta

- ea: `0x14016d7e0`
- end: `0x14016d97c`
- name: `ApplySecurityAttributesToWinsta`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140029324`
- `0x14016d7e0`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x14016d825`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14016d825`
- `ntoskrnl!SeLockSubjectContext` at `0x14016d835`
- `ntoskrnl!SeLockSubjectContext` at `0x14016d835`
- `ntoskrnl!ObQueryNameInfo` at `0x14016d844`
- `ntoskrnl!ObQueryNameInfo` at `0x14016d844`
- `ntoskrnl!ObGetObjectSecurity` at `0x14016d931`
- `ntoskrnl!ObGetObjectSecurity` at `0x14016d931`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14016d8ac`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14016d94b`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14016d8ac`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14016d94b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14016d8bc`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14016d95b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14016d8bc`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14016d95b`
- `ntoskrnl!SeAssignSecurity` at `0x14016d887`
- `ntoskrnl!SeAssignSecurity` at `0x14016d887`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14016d89c`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14016d89c`
- `ntoskrnl!ObSetSecurityDescriptorInfo` at `0x14016d8f3`
- `ntoskrnl!ObSetSecurityDescriptorInfo` at `0x14016d8f3`
- `ntoskrnl!SeDeassignSecurity` at `0x14016d905`
- `ntoskrnl!SeDeassignSecurity` at `0x14016d905`

## pseudocode

```c
__int64 __fastcall ApplySecurityAttributesToWinsta(__int64 a1, void *a2)
{
  void *v4; // rcx
  NTSTATUS ObjectSecurity; // ebx
  __int64 v7; // rcx
  PSECURITY_DESCRIPTOR ParentDescriptor; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+48h] [rbp-28h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-20h] BYREF
  BOOLEAN MemoryAllocated; // [rsp+A0h] [rbp+30h] BYREF
  int v12; // [rsp+A8h] [rbp+38h] BYREF

  ParentDescriptor = 0;
  NewDescriptor = 0;
  v12 = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  MemoryAllocated = 0;
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  v4 = *(void **)ObQueryNameInfo(a1);
  if ( v4 && (ObjectSecurity = ObGetObjectSecurity(v4, &ParentDescriptor, &MemoryAllocated), ObjectSecurity < 0) )
  {
    SeUnlockSubjectContext(&SubjectContext);
    SeReleaseSubjectContext(&SubjectContext);
  }
  else
  {
    ObjectSecurity = SeAssignSecurity(
                       ParentDescriptor,
                       a2,
                       &NewDescriptor,
                       1u,
                       &SubjectContext,
                       (PGENERIC_MAPPING)&WinStaMapping,
                       PagedPool);
    ObReleaseObjectSecurity(ParentDescriptor, MemoryAllocated);
    SeUnlockSubjectContext(&SubjectContext);
    SeReleaseSubjectContext(&SubjectContext);
    if ( ObjectSecurity < 0 )
    {
      v7 = (unsigned int)ObjectSecurity;
      if ( ObjectSecurity == -1073741790 )
        v7 = 3221225506LL;
      SetLastNtError(v7);
    }
    else
    {
      v12 = 15;
      ObjectSecurity = ObSetSecurityDescriptorInfo(a1, &v12, NewDescriptor, a1 - 8, 1, &WinStaMapping);
      SeDeassignSecurity(&NewDescriptor);
    }
  }
  return (unsigned int)ObjectSecurity;
}

```

## disassembly

```asm
0x14016d7e0  mov     [rsp-18h+arg_0], rbx
0x14016d7e5  mov     [rsp-18h+arg_8], rsi
0x14016d7ea  push    rbp
0x14016d7eb  push    rdi
0x14016d7ec  push    r12
0x14016d7ee  mov     rbp, rsp
0x14016d7f1  sub     rsp, 70h
0x14016d7f5  xorps   xmm0, xmm0
0x14016d7f8  mov     [rbp+ParentDescriptor], 0
0x14016d800  mov     rdi, rcx
0x14016d803  mov     [rbp+NewDescriptor], 0
0x14016d80b  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016d80f  mov     [rbp+arg_18], 0
0x14016d816  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x14016d81a  mov     rsi, rdx
0x14016d81d  mov     [rbp+MemoryAllocated], 0
0x14016d821  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x14016d825  call    cs:__imp_SeCaptureSubjectContext
0x14016d82c  nop     dword ptr [rax+rax+00h]
0x14016d831  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016d835  call    cs:__imp_SeLockSubjectContext
0x14016d83c  nop     dword ptr [rax+rax+00h]
0x14016d841  mov     rcx, rdi
0x14016d844  call    cs:__imp_ObQueryNameInfo
0x14016d84b  nop     dword ptr [rax+rax+00h]
0x14016d850  mov     rcx, [rax]; Object
0x14016d853  test    rcx, rcx
0x14016d856  jnz     loc_14016D929
0x14016d85c  mov     rcx, [rbp+ParentDescriptor]; ParentDescriptor
0x14016d860  lea     rax, [rbp+SubjectContext]
0x14016d864  mov     [rsp+70h+PoolType], 1; PoolType
0x14016d86c  lea     r12, WinStaMapping
0x14016d873  mov     [rsp+70h+GenericMapping], r12; GenericMapping
0x14016d878  lea     r8, [rbp+NewDescriptor]; NewDescriptor
0x14016d87c  mov     r9b, 1; IsDirectoryObject
0x14016d87f  mov     [rsp+70h+var_50], rax; SubjectContext
0x14016d884  mov     rdx, rsi; ExplicitDescriptor
0x14016d887  call    cs:__imp_SeAssignSecurity
0x14016d88e  nop     dword ptr [rax+rax+00h]
0x14016d893  mov     dl, [rbp+MemoryAllocated]; MemoryAllocated
0x14016d896  mov     ebx, eax
0x14016d898  mov     rcx, [rbp+ParentDescriptor]; SecurityDescriptor
0x14016d89c  call    cs:__imp_ObReleaseObjectSecurity
0x14016d8a3  nop     dword ptr [rax+rax+00h]
0x14016d8a8  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016d8ac  call    cs:__imp_SeUnlockSubjectContext
0x14016d8b3  nop     dword ptr [rax+rax+00h]
0x14016d8b8  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016d8bc  call    cs:__imp_SeReleaseSubjectContext
0x14016d8c3  nop     dword ptr [rax+rax+00h]
0x14016d8c8  test    ebx, ebx
0x14016d8ca  js      loc_14016D969
0x14016d8d0  mov     r8, [rbp+NewDescriptor]
0x14016d8d4  lea     r9, [rdi-8]
0x14016d8d8  mov     [rsp+70h+GenericMapping], r12
0x14016d8dd  lea     rdx, [rbp+arg_18]
0x14016d8e1  mov     rcx, rdi
0x14016d8e4  mov     dword ptr [rsp+70h+var_50], 1
0x14016d8ec  mov     [rbp+arg_18], 0Fh
0x14016d8f3  call    cs:__imp_ObSetSecurityDescriptorInfo
0x14016d8fa  nop     dword ptr [rax+rax+00h]
0x14016d8ff  lea     rcx, [rbp+NewDescriptor]; SecurityDescriptor
0x14016d903  mov     ebx, eax
0x14016d905  call    cs:__imp_SeDeassignSecurity
0x14016d90c  nop     dword ptr [rax+rax+00h]
0x14016d911  lea     r11, [rsp+70h+var_s0]
0x14016d916  mov     eax, ebx
0x14016d918  mov     rbx, [r11+20h]
0x14016d91c  mov     rsi, [r11+28h]
0x14016d920  mov     rsp, r11
0x14016d923  pop     r12
0x14016d925  pop     rdi
0x14016d926  pop     rbp
0x14016d927  retn
0x14016d929  lea     r8, [rbp+MemoryAllocated]; MemoryAllocated
0x14016d92d  lea     rdx, [rbp+ParentDescriptor]; SecurityDescriptor
0x14016d931  call    cs:__imp_ObGetObjectSecurity
0x14016d938  nop     dword ptr [rax+rax+00h]
0x14016d93d  mov     ebx, eax
0x14016d93f  test    eax, eax
0x14016d941  jns     loc_14016D85C
0x14016d947  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016d94b  call    cs:__imp_SeUnlockSubjectContext
0x14016d952  nop     dword ptr [rax+rax+00h]
0x14016d957  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016d95b  call    cs:__imp_SeReleaseSubjectContext
0x14016d962  nop     dword ptr [rax+rax+00h]
0x14016d967  jmp     short loc_14016D911
0x14016d969  mov     eax, 0C0000022h
0x14016d96e  mov     ecx, ebx
0x14016d970  cmp     ebx, eax
0x14016d972  cmovz   ecx, eax
0x14016d975  call    SetLastNtError
0x14016d97a  jmp     short loc_14016D911
```
