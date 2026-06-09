# CRegistry::myRegDeleteValue(HKEY__ *,ushort const *)

- ea: `0x140012230`
- end: `0x14001223d`
- name: `?myRegDeleteValue@CRegistry@@AEAAJPEAUHKEY__@@PEBG@Z`
- size: `13`
- prototype: `LSTATUS __fastcall(CRegistry *this, HKEY, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140012236`

## pseudocode

```c
LSTATUS __fastcall CRegistry::myRegDeleteValue(CRegistry *this, HKEY a2, const unsigned __int16 *a3)
{
  return RegDeleteValueW(a2, a3);
}

```

## disassembly

```asm
0x140012230  mov     rcx, rdx; public: unsigned long CRegistry::DeleteCurrentKeyValue(struct HKEY__ *, unsigned short const *)
0x140012233  mov     rdx, r8
0x140012236  jmp     cs:__imp_RegDeleteValueW
```
