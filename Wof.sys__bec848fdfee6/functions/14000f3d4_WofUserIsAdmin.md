# WofUserIsAdmin

- ea: `0x14000f3d4`
- end: `0x14000f453`
- name: `WofUserIsAdmin`
- size: `127`
- prototype: `BOOLEAN()`
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140023d80`
- `0x140023ec4`
- `0x140024b90`
- `0x140024cb4`
- `0x140026be0`
- `0x14003e870`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x14000f3ec`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000f3ec`
- `ntoskrnl!SeLockSubjectContext` at `0x14000f3fd`
- `ntoskrnl!SeLockSubjectContext` at `0x14000f3fd`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14000f42d`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14000f42d`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000f43e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000f43e`
- `ntoskrnl!SeTokenIsAdmin` at `0x14000f41a`
- `ntoskrnl!SeTokenIsAdmin` at `0x14000f41a`

## pseudocode

```c
BOOLEAN WofUserIsAdmin()
{
  PACCESS_TOKEN PrimaryToken; // rcx
  BOOLEAN IsAdmin; // bl
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+20h] [rbp-28h] BYREF

  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  IsAdmin = SeTokenIsAdmin(PrimaryToken);
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  return IsAdmin;
}

```

## disassembly

```asm
0x14000f3d4  push    rbx
0x14000f3d6  sub     rsp, 40h
0x14000f3da  xorps   xmm0, xmm0
0x14000f3dd  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x14000f3e2  movups  xmmword ptr [rsp+48h+SubjectContext.ClientToken], xmm0
0x14000f3e7  movups  xmmword ptr [rsp+48h+SubjectContext.PrimaryToken], xmm0
0x14000f3ec  call    cs:__imp_SeCaptureSubjectContext
0x14000f3f3  nop     dword ptr [rax+rax+00h]
0x14000f3f8  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x14000f3fd  call    cs:__imp_SeLockSubjectContext
0x14000f404  nop     dword ptr [rax+rax+00h]
0x14000f409  mov     rax, [rsp+48h+SubjectContext.ClientToken]
0x14000f40e  mov     rcx, [rsp+48h+SubjectContext.PrimaryToken]
0x14000f413  test    rax, rax
0x14000f416  cmovnz  rcx, rax; Token
0x14000f41a  call    cs:__imp_SeTokenIsAdmin
0x14000f421  nop     dword ptr [rax+rax+00h]
0x14000f426  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x14000f42b  mov     bl, al
0x14000f42d  call    cs:__imp_SeUnlockSubjectContext
0x14000f434  nop     dword ptr [rax+rax+00h]
0x14000f439  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x14000f43e  call    cs:__imp_SeReleaseSubjectContext
0x14000f445  nop     dword ptr [rax+rax+00h]
0x14000f44a  mov     al, bl
0x14000f44c  add     rsp, 40h
0x14000f450  pop     rbx
0x14000f451  retn
```
