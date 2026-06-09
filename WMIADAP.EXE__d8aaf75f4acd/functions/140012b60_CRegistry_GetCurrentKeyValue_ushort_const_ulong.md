# CRegistry::GetCurrentKeyValue(ushort const *,ulong &)

- ea: `0x140012b60`
- end: `0x140012b6f`
- name: `?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAK@Z`
- size: `15`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140012660`

## pseudocode

```c
__int64 __fastcall CRegistry::GetCurrentKeyValue(HKEY *this, const unsigned __int16 *a2, unsigned int *a3)
{
  return CRegistry::GetCurrentKeyValue((CRegistry *)this, this[1], a2, a3);
}

```

## disassembly

```asm
0x140012b60  mov     r9, r8; unsigned int *
0x140012b63  mov     r8, rdx; unsigned __int16 *
0x140012b66  mov     rdx, [rcx+8]; HKEY
0x140012b6a  jmp     ?GetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAK@Z; CRegistry::GetCurrentKeyValue(HKEY__ *,ushort const *,ulong &)
```
