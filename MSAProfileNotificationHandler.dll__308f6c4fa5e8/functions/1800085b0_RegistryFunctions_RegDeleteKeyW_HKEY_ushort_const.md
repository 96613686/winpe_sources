# RegistryFunctions::RegDeleteKeyW(HKEY__ *,ushort const *)

- ea: `0x1800085b0`
- end: `0x1800085c6`
- name: `?RegDeleteKeyW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBG@Z`
- size: `22`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800085bf`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegDeleteKeyW(RegistryFunctions *this, HKEY a2, const unsigned __int16 *a3)
{
  return RegDeleteKeyExW(a2, a3, 0, 0);
}

```

## disassembly

```asm
0x1800085b0  mov     rax, r8
0x1800085b3  mov     rcx, rdx
0x1800085b6  mov     rdx, rax
0x1800085b9  xor     r9d, r9d
0x1800085bc  xor     r8d, r8d
0x1800085bf  jmp     cs:__imp_RegDeleteKeyExW
```
