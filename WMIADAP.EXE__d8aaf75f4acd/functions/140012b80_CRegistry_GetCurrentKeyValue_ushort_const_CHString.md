# CRegistry::GetCurrentKeyValue(ushort const *,CHString &)

- ea: `0x140012b80`
- end: `0x140012b8f`
- name: `?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z`
- size: `15`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, struct CHString *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140012720`

## pseudocode

```c
__int64 __fastcall CRegistry::GetCurrentKeyValue(HKEY *this, const unsigned __int16 *a2, struct CHString *a3)
{
  return CRegistry::GetCurrentKeyValue((CRegistry *)this, this[1], a2, a3);
}

```

## disassembly

```asm
0x140012b80  mov     r9, r8; struct CHString *
0x140012b83  mov     r8, rdx; unsigned __int16 *
0x140012b86  mov     rdx, [rcx+8]; HKEY
0x140012b8a  jmp     ?GetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(HKEY__ *,ushort const *,CHString &)
```
