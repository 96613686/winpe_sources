# std::filesystem::path::~path(void)

- ea: `0x1400089f8`
- end: `0x1400089fd`
- name: `??1path@filesystem@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(char **this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ae74`
- `0x14000ae86`
- `0x14000aef2`
- `0x14000af08`
- `0x14000af1e`
- `0x14000af30`
- `0x14000af5c`
- `0x14000af88`
- `0x14000afbe`
- `0x14000afd0`
- `0x14000afe2`
- `0x14000aff4`

## callees

- `0x1400087e4`

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
0x1400089f8  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
