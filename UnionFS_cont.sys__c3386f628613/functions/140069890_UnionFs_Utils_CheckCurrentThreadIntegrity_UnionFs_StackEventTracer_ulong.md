# UnionFs::Utils::CheckCurrentThreadIntegrity(UnionFs::StackEventTracer &,ulong)

- ea: `0x140069890`
- end: `0x1400699d6`
- name: `?CheckCurrentThreadIntegrity@Utils@UnionFs@@YAJAEAVStackEventTracer@2@K@Z`
- size: `326`
- prototype: `__int64 __fastcall(UnionFs::Utils *__hidden this, struct UnionFs::StackEventTracer *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140009860`
- `0x14000c2b0`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x140069890`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x1400698f3`
- `ntoskrnl!SeQueryInformationToken` at `0x1400698f3`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14006994e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400699b7`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14006994e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400699b7`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140069937`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400699a0`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140069937`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400699a0`
- `ntoskrnl!SeLockSubjectContext` at `0x1400698c8`
- `ntoskrnl!SeLockSubjectContext` at `0x1400698c8`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400698b8`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400698b8`

## string_xrefs

- `0x140069905`: `API: Getting token integrity`
- `0x140069916`: `UnionFs::Utils::CheckCurrentThreadIntegrity`
- `0x14006997a`: `UnionFs::Utils::CheckCurrentThreadIntegrity`

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
      (struct UnionFs::StackEventTracer *)0x10E002123B8LL,
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
      (struct UnionFs::StackEventTracer *)0x117002123BFLL,
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
0x140069890  mov     [rsp-8+arg_0], rbx
0x140069895  mov     [rsp-8+arg_10], rdi
0x14006989a  mov     dword ptr [rsp-8+TokenInformation], edx
0x14006989e  push    rbp
0x14006989f  mov     rbp, rsp
0x1400698a2  sub     rsp, 50h
0x1400698a6  xorps   xmm0, xmm0
0x1400698a9  mov     rdi, rcx
0x1400698ac  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400698b0  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x1400698b4  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x1400698b8  call    cs:__imp_SeCaptureSubjectContext
0x1400698bf  nop     dword ptr [rax+rax+00h]
0x1400698c4  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400698c8  call    cs:__imp_SeLockSubjectContext
0x1400698cf  nop     dword ptr [rax+rax+00h]
0x1400698d4  mov     rax, [rbp+SubjectContext.ClientToken]
0x1400698d8  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1400698dc  mov     rcx, [rbp+SubjectContext.PrimaryToken]
0x1400698e0  test    rax, rax
0x1400698e3  mov     edx, 19h; TokenInformationClass
0x1400698e8  mov     dword ptr [rbp+TokenInformation], 0
0x1400698ef  cmovnz  rcx, rax; Token
0x1400698f3  call    cs:__imp_SeQueryInformationToken
0x1400698fa  nop     dword ptr [rax+rax+00h]
0x1400698ff  mov     ebx, eax
0x140069901  test    eax, eax
0x140069903  jns     short loc_14006995E
0x140069905  lea     rax, aApiGettingToke; "API: Getting token integrity"
0x14006990c  mov     r8, 10E002123B8h; struct UnionFs::StackEventTracer *
0x140069916  lea     r9, aUnionfsUtilsCh_1; "UnionFs::Utils::CheckCurrentThreadInteg"...
0x14006991d  mov     [rsp+50h+var_30], rax; char *
0x140069922  mov     rdx, rdi; int
0x140069925  mov     ecx, ebx; this
0x140069927  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006992c  cmp     [rbp+SubjectContext.PrimaryToken], 0
0x140069931  jz      short loc_14006995A
0x140069933  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140069937  call    cs:__imp_SeUnlockSubjectContext
0x14006993e  nop     dword ptr [rax+rax+00h]
0x140069943  cmp     [rbp+SubjectContext.PrimaryToken], 0
0x140069948  jz      short loc_14006995A
0x14006994a  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14006994e  call    cs:__imp_SeReleaseSubjectContext
0x140069955  nop     dword ptr [rax+rax+00h]
0x14006995a  mov     eax, ebx
0x14006995c  jmp     short loc_1400699C5
0x14006995e  cmp     dword ptr [rbp+TokenInformation], 2000h
0x140069965  jnb     short loc_140069995
0x140069967  lea     rax, aOriginRejectin_1; "ORIGIN: Rejecting low/untrusted caller"
0x14006996e  mov     ebx, 0C0000022h
0x140069973  mov     ecx, ebx; this
0x140069975  mov     [rsp+50h+var_30], rax; char *
0x14006997a  lea     r9, aUnionfsUtilsCh_1; "UnionFs::Utils::CheckCurrentThreadInteg"...
0x140069981  mov     r8, 117002123BFh; struct UnionFs::StackEventTracer *
0x14006998b  mov     rdx, rdi; int
0x14006998e  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069993  jmp     short loc_14006992C
0x140069995  cmp     [rbp+SubjectContext.PrimaryToken], 0
0x14006999a  jz      short loc_1400699C3
0x14006999c  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400699a0  call    cs:__imp_SeUnlockSubjectContext
0x1400699a7  nop     dword ptr [rax+rax+00h]
0x1400699ac  cmp     [rbp+SubjectContext.PrimaryToken], 0
0x1400699b1  jz      short loc_1400699C3
0x1400699b3  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400699b7  call    cs:__imp_SeReleaseSubjectContext
0x1400699be  nop     dword ptr [rax+rax+00h]
0x1400699c3  xor     eax, eax
0x1400699c5  mov     rbx, [rsp+50h+arg_0]
0x1400699ca  mov     rdi, [rsp+50h+arg_10]
0x1400699cf  add     rsp, 50h
0x1400699d3  pop     rbp
0x1400699d4  retn
```
