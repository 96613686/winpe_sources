# Vml::VmExeModule<CExec::Svc::Service>::~VmExeModule<CExec::Svc::Service>(void)

- ea: `0x14000f82c`
- end: `0x14000f837`
- name: `??1?$VmExeModule@VService@Svc@CExec@@@Vml@@UEAA@XZ`
- size: `11`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x1400229c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000f830`

## pseudocode

```c
void __fastcall Vml::VmExeModule<CExec::Svc::Service>::~VmExeModule<CExec::Svc::Service>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  DeleteCriticalSection(a1 + 1);
}

```

## disassembly

```asm
0x14000f82c  add     rcx, 28h ; '('
0x14000f830  jmp     cs:__imp_DeleteCriticalSection
```
