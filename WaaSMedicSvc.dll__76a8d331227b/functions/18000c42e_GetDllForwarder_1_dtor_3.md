# _GetDllForwarder_::_1_::dtor$3

- ea: `0x18000c42e`
- end: `0x18000c43e`
- name: `_GetDllForwarder_::_1_::dtor$3`
- size: `16`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000915c`

## pseudocode

```c
void GetDllForwarder_::_1_::dtor_3()
{
  std::filesystem::path::~path((char **)&lpLibFileName);
}

```

## disassembly

```asm
0x18000c42e  lea     rcx, off_180013090
0x18000c435  add     rcx, 18h; this
0x18000c439  jmp     ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
```
