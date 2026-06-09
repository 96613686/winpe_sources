# CNtAcl::~CNtAcl(void)

- ea: `0x18000f7c4`
- end: `0x18000f7ca`
- name: `??1CNtAcl@@QEAA@XZ_0`
- size: `6`
- prototype: `void(CNtAcl *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x18000f7c4`

## pseudocode

```c
// attributes: thunk
void __fastcall CNtAcl::~CNtAcl(CNtAcl *this)
{
  __imp_??1CNtAcl@@QEAA@XZ(this);
}

```

## disassembly

```asm
0x18000f7c4  jmp     cs:__imp_??1CNtAcl@@QEAA@XZ
```
