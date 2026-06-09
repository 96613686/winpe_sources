# RegistryFunctions::RegCloseKey(HKEY__ *)

- ea: `0x1800084a0`
- end: `0x1800084aa`
- name: `?RegCloseKey@RegistryFunctions@@UEAAJPEAUHKEY__@@@Z`
- size: `10`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084a3`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegCloseKey(RegistryFunctions *this, HKEY a2)
{
  return RegCloseKey(a2);
}

```

## disassembly

```asm
0x1800084a0  mov     rcx, rdx
0x1800084a3  jmp     cs:__imp_RegCloseKey
```
