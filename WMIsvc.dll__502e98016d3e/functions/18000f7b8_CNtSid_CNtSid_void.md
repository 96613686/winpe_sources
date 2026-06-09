# CNtSid::~CNtSid(void)

- ea: `0x18000f7b8`
- end: `0x18000f7be`
- name: `??1CNtSid@@QEAA@XZ_0`
- size: `6`
- prototype: `void(CNtSid *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18000f7b8`

## pseudocode

```c
// attributes: thunk
void __fastcall CNtSid::~CNtSid(CNtSid *this)
{
  __imp_??1CNtSid@@QEAA@XZ(this);
}

```

## disassembly

```asm
0x18000f7b8  jmp     cs:__imp_??1CNtSid@@QEAA@XZ
```
