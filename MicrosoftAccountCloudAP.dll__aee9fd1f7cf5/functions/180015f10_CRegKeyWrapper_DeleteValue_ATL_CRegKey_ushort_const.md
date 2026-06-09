# CRegKeyWrapper::DeleteValue(ATL::CRegKey *,ushort const *)

- ea: `0x180015f10`
- end: `0x180015f1d`
- name: `?DeleteValue@CRegKeyWrapper@@UEAAJPEAVCRegKey@ATL@@PEBG@Z`
- size: `13`
- prototype: `LSTATUS __fastcall(CRegKeyWrapper *this, HKEY *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015f16`

## pseudocode

```c
LSTATUS __fastcall CRegKeyWrapper::DeleteValue(CRegKeyWrapper *this, HKEY *a2, const unsigned __int16 *a3)
{
  return RegDeleteValueW(*a2, a3);
}

```

## disassembly

```asm
0x180015f10  mov     rcx, [rdx]
0x180015f13  mov     rdx, r8
0x180015f16  jmp     cs:__imp_RegDeleteValueW
```
