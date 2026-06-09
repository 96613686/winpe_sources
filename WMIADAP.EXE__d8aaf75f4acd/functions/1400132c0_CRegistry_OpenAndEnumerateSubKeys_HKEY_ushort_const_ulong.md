# CRegistry::OpenAndEnumerateSubKeys(HKEY__ *,ushort const *,ulong)

- ea: `0x1400132c0`
- end: `0x1400132c9`
- name: `?OpenAndEnumerateSubKeys@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `9`
- prototype: `LSTATUS __fastcall(CRegistry *this, HKEY, WCHAR *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1400131d0`

## pseudocode

```c
LSTATUS __fastcall CRegistry::OpenAndEnumerateSubKeys(CRegistry *this, HKEY a2, WCHAR *a3, int a4)
{
  return CRegistry::Open(this, a2, a3, a4 | 8);
}

```

## disassembly

```asm
0x1400132c0  or      r9d, 8; unsigned int
0x1400132c4  jmp     ?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
```
