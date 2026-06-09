# CRegistry::DeleteCurrentKeyValue(ushort const *)

- ea: `0x140012250`
- end: `0x14001225b`
- name: `?DeleteCurrentKeyValue@CRegistry@@QEAAKPEBG@Z`
- size: `11`
- prototype: `LSTATUS __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140012254`

## pseudocode

```c
LSTATUS __fastcall CRegistry::DeleteCurrentKeyValue(HKEY *this, const unsigned __int16 *a2)
{
  return RegDeleteValueW(this[1], a2);
}

```

## disassembly

```asm
0x140012250  mov     rcx, [rcx+8]; public: unsigned long CRegistry::DeleteCurrentKeyValue(unsigned short const *)
0x140012254  jmp     cs:__imp_RegDeleteValueW
```
