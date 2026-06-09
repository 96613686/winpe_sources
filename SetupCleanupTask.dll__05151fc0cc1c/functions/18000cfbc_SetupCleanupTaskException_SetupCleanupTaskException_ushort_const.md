# SetupCleanupTaskException::SetupCleanupTaskException(ushort const *)

- ea: `0x18000cfbc`
- end: `0x18000cfe3`
- name: `??0SetupCleanupTaskException@@QEAA@PEBG@Z`
- size: `39`
- prototype: `SetupCleanupTaskException *__fastcall(SetupCleanupTaskException *__hidden this, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `0`
- tags: `service_task, installer_update`

## callers

- `0x180006838`
- `0x180009838`
- `0x18000ba70`
- `0x18000c23c`
- `0x18000f230`
- `0x18000f3bc`
- `0x1800131d0`

## import_xrefs

- `unbcl!??0Exception@UnBCL@@QEAA@PEBG@Z` at `0x18000cfc9`
- `unbcl!??0Exception@UnBCL@@QEAA@PEBG@Z` at `0x18000cfc9`

## pseudocode

```c
SetupCleanupTaskException *__fastcall SetupCleanupTaskException::SetupCleanupTaskException(
        SetupCleanupTaskException *this,
        const unsigned __int16 *a2)
{
  UnBCL::Exception::Exception(this, a2);
  *(_QWORD *)this = &SetupCleanupTaskException::`vftable';
  return this;
}

```

## disassembly

```asm
0x18000cfbc  mov     [rsp+arg_0], rcx
0x18000cfc1  push    rbx
0x18000cfc2  sub     rsp, 20h
0x18000cfc6  mov     rbx, rcx
0x18000cfc9  call    cs:__imp_??0Exception@UnBCL@@QEAA@PEBG@Z; UnBCL::Exception::Exception(ushort const *)
0x18000cfcf  nop
0x18000cfd0  lea     rax, ??_7SetupCleanupTaskException@@6B@; const SetupCleanupTaskException::`vftable'
0x18000cfd7  mov     [rbx], rax
0x18000cfda  mov     rax, rbx
0x18000cfdd  add     rsp, 20h
0x18000cfe1  pop     rbx
0x18000cfe2  retn
```
