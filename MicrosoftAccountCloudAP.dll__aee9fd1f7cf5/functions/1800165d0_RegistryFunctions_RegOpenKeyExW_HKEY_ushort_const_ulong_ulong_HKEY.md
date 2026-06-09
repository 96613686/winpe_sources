# RegistryFunctions::RegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)

- ea: `0x1800165d0`
- end: `0x1800165f8`
- name: `?RegOpenKeyExW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBGKKPEAPEAU2@@Z`
- size: `40`
- prototype: `__int64 __fastcall(RegistryFunctions *__hidden this, HKEY, const unsigned __int16 *, unsigned int, unsigned int, HKEY *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800165f1`

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
0x1800165d0  push    rbx
0x1800165d2  mov     rax, [rsp+8+arg_28]
0x1800165d7  mov     r10d, r9d
0x1800165da  mov     r9d, [rsp+8+arg_20]
0x1800165df  mov     r11, r8
0x1800165e2  mov     rcx, rdx
0x1800165e5  mov     qword ptr [rsp+8+arg_20], rax
0x1800165ea  mov     r8d, r10d
0x1800165ed  mov     rdx, r11
0x1800165f0  pop     rbx
0x1800165f1  jmp     cs:__imp_RegOpenKeyExW
```
