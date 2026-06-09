# RegistryFunctions::RegQueryInfoKeyW(HKEY__ *,ulong *)

- ea: `0x180008890`
- end: `0x1800088d2`
- name: `?RegQueryInfoKeyW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEAK@Z`
- size: `66`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800088c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800088c7`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegQueryInfoKeyW(RegistryFunctions *this, HKEY a2, unsigned int *a3)
{
  return RegQueryInfoKeyW(a2, 0, 0, 0, 0, a3, 0, 0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x180008890  mov     r11, rsp
0x180008893  sub     rsp, 68h
0x180008897  xor     ecx, ecx
0x180008899  mov     rax, rdx
0x18000889c  mov     [r11-10h], rcx
0x1800088a0  xor     r9d, r9d; lpReserved
0x1800088a3  mov     [r11-18h], rcx
0x1800088a7  xor     edx, edx; lpClass
0x1800088a9  mov     [r11-20h], rcx
0x1800088ad  mov     [r11-28h], rcx
0x1800088b1  mov     [r11-30h], rcx
0x1800088b5  mov     [r11-38h], rcx
0x1800088b9  mov     [r11-40h], r8
0x1800088bd  xor     r8d, r8d; lpcchClass
0x1800088c0  mov     [r11-48h], rcx
0x1800088c4  mov     rcx, rax; hKey
0x1800088c7  call    cs:__imp_RegQueryInfoKeyW
0x1800088cd  add     rsp, 68h
0x1800088d1  retn
```
