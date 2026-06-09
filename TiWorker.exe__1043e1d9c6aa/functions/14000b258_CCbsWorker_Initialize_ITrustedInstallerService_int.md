# CCbsWorker::Initialize(ITrustedInstallerService *,int)

- ea: `0x14000b258`
- end: `0x14000b2f0`
- name: `?Initialize@CCbsWorker@@UEAAJPEAUITrustedInstallerService@@H@Z`
- size: `152`
- prototype: `__int64 __fastcall(CCbsWorker *__hidden this, struct ITrustedInstallerService *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x1400096f0`

## callees

- `0x14000b258`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x14000b281`: `TrustedInstaller service object already set, TrustedInstaller must've crashed`
- `0x14000b2c6`: `Error: Not reversed from impersonation on func: %s`

## pseudocode

```c
__int64 __fastcall CCbsWorker::Initialize(CCbsWorker *this, struct ITrustedInstallerService *a2, int a3)
{
  __int64 v6; // rax

  if ( vpTrustedInstallerService && a2 != vpTrustedInstallerService )
    CBSWdsLog(0x4000000, 0, 0, "TrustedInstaller service object already set, TrustedInstaller must've crashed");
  v6 = *(_QWORD *)a2;
  vpTrustedInstallerService = a2;
  (*(void (__fastcall **)(struct ITrustedInstallerService *))(v6 + 8))(a2);
  *((_DWORD *)this - 6) = a3;
  if ( NtCurrentTeb()->IsImpersonating )
    CBSWdsLog(0x4000000, 0, 0, "Error: Not reversed from impersonation on func: %s", "CCbsWorker::Initialize");
  return 0;
}

```

## disassembly

```asm
0x14000b258  mov     [rsp+arg_0], rbx
0x14000b25d  mov     [rsp+arg_8], rsi
0x14000b262  push    rdi
0x14000b263  sub     rsp, 30h
0x14000b267  mov     rax, cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA; ITrustedInstallerService * vpTrustedInstallerService
0x14000b26e  mov     edi, r8d
0x14000b271  mov     rbx, rdx
0x14000b274  mov     rsi, rcx
0x14000b277  test    rax, rax
0x14000b27a  jz      short loc_14000B297
0x14000b27c  cmp     rdx, rax
0x14000b27f  jz      short loc_14000B297
0x14000b281  lea     r9, aTrustedinstall; "TrustedInstaller service object already"...
0x14000b288  xor     r8d, r8d
0x14000b28b  xor     edx, edx
0x14000b28d  mov     ecx, 4000000h
0x14000b292  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000b297  mov     rax, [rbx]
0x14000b29a  mov     rcx, rbx
0x14000b29d  mov     cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA, rbx; ITrustedInstallerService * vpTrustedInstallerService
0x14000b2a4  mov     rax, [rax+8]
0x14000b2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b2ad  mov     [rsi-18h], edi
0x14000b2b0  mov     eax, gs:179Ch
0x14000b2b8  test    eax, eax
0x14000b2ba  jz      short loc_14000B2DE
0x14000b2bc  lea     rax, aCcbsworkerInit; "CCbsWorker::Initialize"
0x14000b2c3  xor     r8d, r8d
0x14000b2c6  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000b2cd  mov     [rsp+38h+var_18], rax
0x14000b2d2  xor     edx, edx
0x14000b2d4  mov     ecx, 4000000h
0x14000b2d9  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000b2de  mov     rbx, [rsp+38h+arg_0]
0x14000b2e3  xor     eax, eax
0x14000b2e5  mov     rsi, [rsp+38h+arg_8]
0x14000b2ea  add     rsp, 30h
0x14000b2ee  pop     rdi
0x14000b2ef  retn
```
