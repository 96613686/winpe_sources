# IsCallingProcessAdmin

- ea: `0x1402097bc`
- end: `0x140209844`
- name: `IsCallingProcessAdmin`
- size: `136`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001e010`

## callees

- `0x1402097bc`

## import_xrefs

- `ntoskrnl!SeTokenIsAdmin` at `0x14020980b`
- `ntoskrnl!SeTokenIsAdmin` at `0x14020980b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14020982f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14020982f`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14020981e`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14020981e`
- `ntoskrnl!SeLockSubjectContext` at `0x1402097e5`
- `ntoskrnl!SeLockSubjectContext` at `0x1402097e5`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402097d4`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402097d4`

## pseudocode

```c
BOOLEAN IsCallingProcessAdmin()
{
  void *PrimaryToken; // rcx
  BOOLEAN IsAdmin; // bl
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+20h] [rbp-28h] BYREF

  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  if ( PrimaryToken )
    IsAdmin = SeTokenIsAdmin(PrimaryToken);
  else
    IsAdmin = 0;
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  return IsAdmin;
}

```

## disassembly

```asm
0x1402097bc  push    rbx
0x1402097be  sub     rsp, 40h
0x1402097c2  xorps   xmm0, xmm0
0x1402097c5  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x1402097ca  movups  xmmword ptr [rsp+48h+SubjectContext.ClientToken], xmm0
0x1402097cf  movups  xmmword ptr [rsp+48h+SubjectContext.PrimaryToken], xmm0
0x1402097d4  call    cs:__imp_SeCaptureSubjectContext
0x1402097db  nop     dword ptr [rax+rax+00h]
0x1402097e0  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x1402097e5  call    cs:__imp_SeLockSubjectContext
0x1402097ec  nop     dword ptr [rax+rax+00h]
0x1402097f1  mov     rax, [rsp+48h+SubjectContext.ClientToken]
0x1402097f6  mov     rcx, [rsp+48h+SubjectContext.PrimaryToken]
0x1402097fb  test    rax, rax
0x1402097fe  cmovnz  rcx, rax; Token
0x140209802  test    rcx, rcx
0x140209805  jnz     short loc_14020980B
0x140209807  xor     bl, bl
0x140209809  jmp     short loc_140209819
0x14020980b  call    cs:__imp_SeTokenIsAdmin
0x140209812  nop     dword ptr [rax+rax+00h]
0x140209817  mov     bl, al
0x140209819  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x14020981e  call    cs:__imp_SeUnlockSubjectContext
0x140209825  nop     dword ptr [rax+rax+00h]
0x14020982a  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x14020982f  call    cs:__imp_SeReleaseSubjectContext
0x140209836  nop     dword ptr [rax+rax+00h]
0x14020983b  mov     al, bl
0x14020983d  add     rsp, 40h
0x140209841  pop     rbx
0x140209842  retn
```
