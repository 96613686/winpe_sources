# STRU_PATH::~STRU_PATH(void)

- ea: `0x180001ac9`
- end: `0x180001acf`
- name: `??1STRU_PATH@@QEAA@XZ_0`
- size: `6`
- prototype: `void(STRU_PATH *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x180001ac9`

## pseudocode

```c
// attributes: thunk
void __fastcall STRU_PATH::~STRU_PATH(STRU_PATH *this)
{
  __imp_??1STRU_PATH@@QEAA@XZ(this);
}

```

## disassembly

```asm
0x180001ac9  jmp     cs:__imp_??1STRU_PATH@@QEAA@XZ
```
