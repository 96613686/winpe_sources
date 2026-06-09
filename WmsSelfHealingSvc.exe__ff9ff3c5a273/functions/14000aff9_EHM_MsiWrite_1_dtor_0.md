# ___EHM_MsiWrite_::_1_::dtor$0

- ea: `0x14000aff9`
- end: `0x14000b005`
- name: `___EHM_MsiWrite_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, MSIHANDLE *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140003684`

## pseudocode

```c
void __fastcall __EHM_MsiWrite_::_1_::dtor_0(__int64 a1, MSIHANDLE *a2)
{
  PMSIHANDLE::~PMSIHANDLE(a2);
}

```

## disassembly

```asm
0x14000aff9  lea     rcx, [rdx+0]; this
0x14000b000  jmp     ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
```
