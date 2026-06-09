# CCbsWorker::CreateSessionNotify(ulong,ulong *,wchar_t * *)

- ea: `0x14000a884`
- end: `0x14000a8f8`
- name: `?CreateSessionNotify@CCbsWorker@@UEAAJKPEAKPEAPEA_W@Z`
- size: `116`
- prototype: `__int64 __fastcall(CCbsWorker *__hidden this, unsigned int, unsigned int *, wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x1400094a0`

## callees

- `0x14000a884`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x14000a8d8`: `Error: Not reversed from impersonation on func: %s`
- `0x14000a89b`: `CreateSessionNotify is not implemented.`
- `0x14000a8ce`: `CCbsWorker::CreateSessionNotify`

## pseudocode

```c
__int64 __fastcall CCbsWorker::CreateSessionNotify(CCbsWorker *this, unsigned int a2, unsigned int *a3, wchar_t **a4)
{
  unsigned int SessionNotify; // ebx

  if ( vpfnCbsCreateSessionNotify )
  {
    SessionNotify = vpfnCbsCreateSessionNotify(vpTrustedInstallerService, a2, a3, a4);
  }
  else
  {
    SessionNotify = -2147467263;
    CBSWdsLog(0x4000000u, -2147467263, (size_t *)1, "CreateSessionNotify is not implemented.");
  }
  if ( NtCurrentTeb()->IsImpersonating )
    CBSWdsLog(0x4000000u, 0, 0, "Error: Not reversed from impersonation on func: %s", "CCbsWorker::CreateSessionNotify");
  return SessionNotify;
}

```

## disassembly

```asm
0x14000a884  push    rbx
0x14000a886  sub     rsp, 30h
0x14000a88a  mov     rax, cs:?vpfnCbsCreateSessionNotify@@3P6AJPEAUITrustedInstallerService@@KPEAKPEAPEA_W@ZEA; long (*vpfnCbsCreateSessionNotify)(ITrustedInstallerService *,ulong,ulong *,wchar_t * *)
0x14000a891  test    rax, rax
0x14000a894  jnz     short loc_14000A8B4
0x14000a896  mov     ebx, 80004001h
0x14000a89b  lea     r9, aCreatesessionn_0; "CreateSessionNotify is not implemented."
0x14000a8a2  mov     edx, ebx
0x14000a8a4  lea     r8d, [rax+1]
0x14000a8a8  mov     ecx, 4000000h
0x14000a8ad  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a8b2  jmp     short loc_14000A8C2
0x14000a8b4  mov     rcx, cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA; ITrustedInstallerService * vpTrustedInstallerService
0x14000a8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a8c0  mov     ebx, eax
0x14000a8c2  mov     edx, gs:179Ch
0x14000a8ca  test    edx, edx
0x14000a8cc  jz      short loc_14000A8F0
0x14000a8ce  lea     rax, aCcbsworkerCrea_0; "CCbsWorker::CreateSessionNotify"
0x14000a8d5  xor     r8d, r8d
0x14000a8d8  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000a8df  mov     [rsp+38h+var_18], rax
0x14000a8e4  xor     edx, edx
0x14000a8e6  mov     ecx, 4000000h
0x14000a8eb  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a8f0  mov     eax, ebx
0x14000a8f2  add     rsp, 30h
0x14000a8f6  pop     rbx
0x14000a8f7  retn
```
