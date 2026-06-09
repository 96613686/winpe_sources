# RegistryFunctions::RegOpenCurrentUser(ulong,HKEY__ * *)

- ea: `0x1800087a0`
- end: `0x1800087ac`
- name: `?RegOpenCurrentUser@RegistryFunctions@@UEAAJKPEAPEAUHKEY__@@@Z`
- size: `12`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, REGSAM, HKEY *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800087a5`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegOpenCurrentUser(RegistryFunctions *this, REGSAM a2, HKEY *a3)
{
  return RegOpenCurrentUser(a2, a3);
}

```

## disassembly

```asm
0x1800087a0  mov     ecx, edx
0x1800087a2  mov     rdx, r8
0x1800087a5  jmp     cs:__imp_RegOpenCurrentUser
```
