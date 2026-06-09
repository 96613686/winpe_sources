# UnionFs::Utils::CheckCurrentThreadIntegrity(UnionFs::StackEventTracer &,ulong)

- ea: `0x140069a80`
- end: `0x140069bc6`
- name: `?CheckCurrentThreadIntegrity@Utils@UnionFs@@YAJAEAVStackEventTracer@2@K@Z`
- size: `326`
- prototype: `__int64 __fastcall(UnionFs::Utils *__hidden this, struct UnionFs::StackEventTracer *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140009830`
- `0x14000c280`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x140069a80`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x140069ae3`
- `ntoskrnl!SeQueryInformationToken` at `0x140069ae3`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140069b3e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140069ba7`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140069b3e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140069ba7`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140069b27`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140069b90`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140069b27`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140069b90`
- `ntoskrnl!SeLockSubjectContext` at `0x140069ab8`
- `ntoskrnl!SeLockSubjectContext` at `0x140069ab8`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140069aa8`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140069aa8`

## string_xrefs

- `0x140069af5`: `API: Getting token integrity`
- `0x140069b06`: `UnionFs::Utils::CheckCurrentThreadIntegrity`
- `0x140069b6a`: `UnionFs::Utils::CheckCurrentThreadIntegrity`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CheckCurrentThreadIntegrity(
        UnionFs::Utils *this,
        struct UnionFs::StackEventTracer *a2)
{
  int v2; // edi
  PACCESS_TOKEN PrimaryToken; // rcx
  NTSTATUS v4; // ebx
  const char *v6; // [rsp+28h] [rbp-28h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+30h] [rbp-20h] BYREF
  PVOID TokenInformation; // [rsp+68h] [rbp+18h] BYREF

  LODWORD(TokenInformation) = (_DWORD)a2;
  v2 = (int)this;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  LODWORD(TokenInformation) = 0;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  v4 = SeQueryInformationToken(PrimaryToken, TokenIntegrityLevel, &TokenInformation);
  if ( v4 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v4,
      v2,
      (struct UnionFs::StackEventTracer *)0x10E002123EELL,
      (unsigned __int64)"UnionFs::Utils::CheckCurrentThreadIntegrity",
      "API: Getting token integrity",
      v6);
LABEL_5:
    if ( SubjectContext.PrimaryToken )
    {
      SeUnlockSubjectContext(&SubjectContext);
      if ( SubjectContext.PrimaryToken )
        SeReleaseSubjectContext(&SubjectContext);
    }
    return (unsigned int)v4;
  }
  if ( (unsigned int)TokenInformation < 0x2000 )
  {
    v4 = -1073741790;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000022LL,
      v2,
      (struct UnionFs::StackEventTracer *)0x117002123F5LL,
      (unsigned __int64)"UnionFs::Utils::CheckCurrentThreadIntegrity",
      "ORIGIN: Rejecting low/untrusted caller",
      v6);
    goto LABEL_5;
  }
  if ( SubjectContext.PrimaryToken )
  {
    SeUnlockSubjectContext(&SubjectContext);
    if ( SubjectContext.PrimaryToken )
      SeReleaseSubjectContext(&SubjectContext);
  }
  return 0;
}

```

## disassembly

```asm
0x140069a80  mov     [rsp-8+arg_0], rbx
0x140069a85  mov     [rsp-8+arg_10], rdi
0x140069a8a  mov     dword ptr [rsp-8+TokenInformation], edx
0x140069a8e  push    rbp
0x140069a8f  mov     rbp, rsp
0x140069a92  sub     rsp, 50h
0x140069a96  xorps   xmm0, xmm0
0x140069a99  mov     rdi, rcx
0x140069a9c  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140069aa0  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x140069aa4  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x140069aa8  call    cs:__imp_SeCaptureSubjectContext
0x140069aaf  nop     dword ptr [rax+rax+00h]
0x140069ab4  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140069ab8  call    cs:__imp_SeLockSubjectContext
0x140069abf  nop     dword ptr [rax+rax+00h]
0x140069ac4  mov     rax, [rbp+SubjectContext.ClientToken]
0x140069ac8  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140069acc  mov     rcx, [rbp+SubjectContext.PrimaryToken]
0x140069ad0  test    rax, rax
0x140069ad3  mov     edx, 19h; TokenInformationClass
0x140069ad8  mov     dword ptr [rbp+TokenInformation], 0
0x140069adf  cmovnz  rcx, rax; Token
0x140069ae3  call    cs:__imp_SeQueryInformationToken
0x140069aea  nop     dword ptr [rax+rax+00h]
0x140069aef  mov     ebx, eax
0x140069af1  test    eax, eax
0x140069af3  jns     short loc_140069B4E
0x140069af5  lea     rax, aApiGettingToke; "API: Getting token integrity"
0x140069afc  mov     r8, 10E002123EEh; struct UnionFs::StackEventTracer *
0x140069b06  lea     r9, aUnionfsUtilsCh_1; "UnionFs::Utils::CheckCurrentThreadInteg"...
0x140069b0d  mov     [rsp+50h+var_30], rax; char *
0x140069b12  mov     rdx, rdi; int
0x140069b15  mov     ecx, ebx; this
0x140069b17  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069b1c  cmp     [rbp+SubjectContext.PrimaryToken], 0
0x140069b21  jz      short loc_140069B4A
0x140069b23  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140069b27  call    cs:__imp_SeUnlockSubjectContext
0x140069b2e  nop     dword ptr [rax+rax+00h]
0x140069b33  cmp     [rbp+SubjectContext.PrimaryToken], 0
0x140069b38  jz      short loc_140069B4A
0x140069b3a  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140069b3e  call    cs:__imp_SeReleaseSubjectContext
0x140069b45  nop     dword ptr [rax+rax+00h]
0x140069b4a  mov     eax, ebx
0x140069b4c  jmp     short loc_140069BB5
0x140069b4e  cmp     dword ptr [rbp+TokenInformation], 2000h
0x140069b55  jnb     short loc_140069B85
0x140069b57  lea     rax, aOriginRejectin_1; "ORIGIN: Rejecting low/untrusted caller"
0x140069b5e  mov     ebx, 0C0000022h
0x140069b63  mov     ecx, ebx; this
0x140069b65  mov     [rsp+50h+var_30], rax; char *
0x140069b6a  lea     r9, aUnionfsUtilsCh_1; "UnionFs::Utils::CheckCurrentThreadInteg"...
0x140069b71  mov     r8, 117002123F5h; struct UnionFs::StackEventTracer *
0x140069b7b  mov     rdx, rdi; int
0x140069b7e  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069b83  jmp     short loc_140069B1C
0x140069b85  cmp     [rbp+SubjectContext.PrimaryToken], 0
0x140069b8a  jz      short loc_140069BB3
0x140069b8c  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140069b90  call    cs:__imp_SeUnlockSubjectContext
0x140069b97  nop     dword ptr [rax+rax+00h]
0x140069b9c  cmp     [rbp+SubjectContext.PrimaryToken], 0
0x140069ba1  jz      short loc_140069BB3
0x140069ba3  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140069ba7  call    cs:__imp_SeReleaseSubjectContext
0x140069bae  nop     dword ptr [rax+rax+00h]
0x140069bb3  xor     eax, eax
0x140069bb5  mov     rbx, [rsp+50h+arg_0]
0x140069bba  mov     rdi, [rsp+50h+arg_10]
0x140069bbf  add     rsp, 50h
0x140069bc3  pop     rbp
0x140069bc4  retn
```
