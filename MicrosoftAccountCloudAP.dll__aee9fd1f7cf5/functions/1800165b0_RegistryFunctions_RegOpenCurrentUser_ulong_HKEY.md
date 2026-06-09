# RegistryFunctions::RegOpenCurrentUser(ulong,HKEY__ * *)

- ea: `0x1800165b0`
- end: `0x1800165bc`
- name: `?RegOpenCurrentUser@RegistryFunctions@@UEAAJKPEAPEAUHKEY__@@@Z`
- size: `12`
- prototype: `__int64 __fastcall(RegistryFunctions *__hidden this, unsigned int, HKEY *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800165b5`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegOpenCurrentUser(RegistryFunctions *this, REGSAM a2, HKEY *a3)
{
  return RegOpenCurrentUser(a2, a3);
}

```

## disassembly

```asm
0x1800165b0  mov     ecx, edx
0x1800165b2  mov     rdx, r8
0x1800165b5  jmp     cs:__imp_RegOpenCurrentUser
```
