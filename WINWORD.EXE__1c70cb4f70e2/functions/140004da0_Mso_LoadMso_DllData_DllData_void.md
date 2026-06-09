# Mso::LoadMso::DllData::~DllData(void)

- ea: `0x140004da0`
- end: `0x140004da6`
- name: `??1DllData@LoadMso@Mso@@QEAA@XZ`
- size: `6`
- prototype: `void __fastcall(Mso::LoadMso::DllData *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140004da8`

## pseudocode

```c
void __fastcall Mso::LoadMso::DllData::~DllData(Mso::LoadMso::DllData *this)
{
  Mso::LoadMso::LoadDllResults::~LoadDllResults((Mso::LoadMso::DllData *)((char *)this + 24));
}

```

## disassembly

```asm
0x140004da0  add     rcx, 18h; this
0x140004da4  jmp     short ??1LoadDllResults@LoadMso@Mso@@QEAA@XZ; Mso::LoadMso::LoadDllResults::~LoadDllResults(void)
```
