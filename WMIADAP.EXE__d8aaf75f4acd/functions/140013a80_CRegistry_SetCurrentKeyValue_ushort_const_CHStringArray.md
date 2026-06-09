# CRegistry::SetCurrentKeyValue(ushort const *,CHStringArray &)

- ea: `0x140013a80`
- end: `0x140013a8f`
- name: `?SetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHStringArray@@@Z`
- size: `15`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, struct CHStringArray *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140013860`

## pseudocode

```c
__int64 __fastcall CRegistry::SetCurrentKeyValue(HKEY *this, const unsigned __int16 *a2, struct CHStringArray *a3)
{
  return CRegistry::SetCurrentKeyValue((CRegistry *)this, this[1], a2, a3);
}

```

## disassembly

```asm
0x140013a80  mov     r9, r8; struct CHStringArray *
0x140013a83  mov     r8, rdx; unsigned __int16 *
0x140013a86  mov     rdx, [rcx+8]; HKEY
0x140013a8a  jmp     ?SetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHStringArray@@@Z; CRegistry::SetCurrentKeyValue(HKEY__ *,ushort const *,CHStringArray &)
```
