# CRegistry::GetCurrentKeyValue(ushort const *,CHStringArray &)

- ea: `0x140012ba0`
- end: `0x140012baf`
- name: `?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHStringArray@@@Z`
- size: `15`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, struct CHStringArray *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140012a00`

## pseudocode

```c
__int64 __fastcall CRegistry::GetCurrentKeyValue(HKEY *this, const unsigned __int16 *a2, struct CHStringArray *a3)
{
  return CRegistry::GetCurrentKeyValue((CRegistry *)this, this[1], a2, a3);
}

```

## disassembly

```asm
0x140012ba0  mov     r9, r8; struct CHStringArray *
0x140012ba3  mov     r8, rdx; unsigned __int16 *
0x140012ba6  mov     rdx, [rcx+8]; HKEY
0x140012baa  jmp     ?GetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHStringArray@@@Z; CRegistry::GetCurrentKeyValue(HKEY__ *,ushort const *,CHStringArray &)
```
