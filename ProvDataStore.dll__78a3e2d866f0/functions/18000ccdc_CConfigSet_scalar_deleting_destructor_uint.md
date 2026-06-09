# CConfigSet::`scalar deleting destructor'(uint)

- ea: `0x18000ccdc`
- end: `0x18000ccfc`
- name: `??_GCConfigSet@@QEAAPEAXI@Z`
- size: `32`
- prototype: `CConfigSet *__fastcall(CConfigSet *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x180011bb2`

## callees

- `0x180009354`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cced`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cced`

## pseudocode

```c
CConfigSet *__fastcall CConfigSet::`scalar deleting destructor'(CConfigSet *this)
{
  FreeProvisionData(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000ccdc  push    rbx
0x18000ccde  sub     rsp, 20h
0x18000cce2  mov     rbx, rcx
0x18000cce5  call    ?FreeProvisionData@@YAXPEAU_MVProvisionData@@@Z; FreeProvisionData(_MVProvisionData *)
0x18000ccea  mov     rcx, rbx
0x18000cced  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ccf3  mov     rax, rbx
0x18000ccf6  add     rsp, 20h
0x18000ccfa  pop     rbx
0x18000ccfb  retn
```
