# std::filesystem::path::~path(void)

- ea: `0x18000915c`
- end: `0x180009161`
- name: `??1path@filesystem@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(char **this)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c282`
- `0x18000c294`
- `0x18000c300`
- `0x18000c316`
- `0x18000c32c`
- `0x18000c33e`
- `0x18000c36a`
- `0x18000c396`
- `0x18000c3cc`
- `0x18000c3de`
- `0x18000c42e`
- `0x18000c45a`
- `0x18000c46c`
- `0x18000c4df`

## callees

- `0x180008f20`

## pseudocode

```c
// attributes: thunk
void __fastcall std::filesystem::path::~path(char **this)
{
  std::wstring::~wstring(this);
}

```

## disassembly

```asm
0x18000915c  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
