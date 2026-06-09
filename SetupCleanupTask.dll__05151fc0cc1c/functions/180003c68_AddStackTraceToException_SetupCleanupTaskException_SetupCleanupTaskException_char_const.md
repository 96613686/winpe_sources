# AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)

- ea: `0x180003c68`
- end: `0x180003c80`
- name: `??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z`
- size: `24`
- prototype: `UnBCL::Exception *__fastcall(UnBCL::Exception *, const char *)`
- caller_count: `63`
- callee_count: `0`
- tags: `service_task, installer_update`

## callers

- `0x180004200`
- `0x180005174`
- `0x180005260`
- `0x180005f20`
- `0x1800064a4`
- `0x180006838`
- `0x1800092b0`
- `0x180009360`
- `0x180009838`
- `0x180009b90`
- `0x180009c90`
- `0x180009d34`
- `0x180009db4`
- `0x180009fb0`
- `0x18000a844`
- `0x18000b494`
- `0x18000b584`
- `0x18000b604`
- `0x18000b7f4`
- `0x18000b880`
- `0x18000ba70`
- `0x18000c23c`
- `0x18000c8a4`
- `0x18000ca44`
- `0x18000caf0`
- `0x18000cea4`
- `0x18000d620`
- `0x18000e454`
- `0x18000e550`
- `0x18000e760`
- `0x18000eff4`
- `0x18000f230`
- `0x18000f3bc`
- `0x18000fdd0`
- `0x18000fe80`
- `0x180010350`
- `0x1800104b0`
- `0x180010554`
- `0x1800105d4`
- `0x180010810`
- `0x180010bd4`
- `0x180011020`
- `0x1800110e0`
- `0x180011f54`
- `0x180012084`
- `0x180012104`
- `0x180012304`
- `0x180012390`
- `0x1800131d0`
- `0x180013b04`

## import_xrefs

- `unbcl!?AddStackTrace@Exception@UnBCL@@QEAAXPEBD@Z` at `0x180003c71`
- `unbcl!?AddStackTrace@Exception@UnBCL@@QEAAXPEBD@Z` at `0x180003c71`

## pseudocode

```c
UnBCL::Exception *__fastcall AddStackTraceToException<SetupCleanupTaskException>(UnBCL::Exception *a1, const char *a2)
{
  UnBCL::Exception::AddStackTrace(a1, a2);
  return a1;
}

```

## disassembly

```asm
0x180003c68  push    rbx
0x180003c6a  sub     rsp, 20h
0x180003c6e  mov     rbx, rcx
0x180003c71  call    cs:__imp_?AddStackTrace@Exception@UnBCL@@QEAAXPEBD@Z
0x180003c77  mov     rax, rbx
0x180003c7a  add     rsp, 20h
0x180003c7e  pop     rbx
0x180003c7f  retn
```
