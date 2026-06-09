# IRegistryKey::~IRegistryKey(void)

- ea: `0x1800203fc`
- end: `0x180020407`
- name: `??1IRegistryKey@@UEAA@XZ`
- size: `11`
- prototype: `void __fastcall(IRegistryKey *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180023b36`
- `0x180024891`
- `0x180024a69`

## pseudocode

```c
void __fastcall IRegistryKey::~IRegistryKey(IRegistryKey *this)
{
  *(_QWORD *)this = &IRegistryKey::`vftable';
}

```

## disassembly

```asm
0x1800203fc  lea     rax, ??_7IRegistryKey@@6B@; const IRegistryKey::`vftable'
0x180020403  mov     [rcx], rax
0x180020406  retn
```
