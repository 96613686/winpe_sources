# RegistryFunctions::RegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)

- ea: `0x1800087c0`
- end: `0x1800087e8`
- name: `?RegOpenKeyExW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBGKKPEAPEAU2@@Z`
- size: `40`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *, DWORD, REGSAM, HKEY *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800087e1`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegOpenKeyExW(
        RegistryFunctions *this,
        HKEY a2,
        const unsigned __int16 *a3,
        DWORD a4,
        REGSAM a5,
        HKEY *a6)
{
  return RegOpenKeyExW(a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x1800087c0  push    rbx
0x1800087c2  mov     rax, [rsp+8+arg_28]
0x1800087c7  mov     r10d, r9d
0x1800087ca  mov     r9d, [rsp+8+arg_20]
0x1800087cf  mov     r11, r8
0x1800087d2  mov     rcx, rdx
0x1800087d5  mov     qword ptr [rsp+8+arg_20], rax
0x1800087da  mov     r8d, r10d
0x1800087dd  mov     rdx, r11
0x1800087e0  pop     rbx
0x1800087e1  jmp     cs:__imp_RegOpenKeyExW
```
