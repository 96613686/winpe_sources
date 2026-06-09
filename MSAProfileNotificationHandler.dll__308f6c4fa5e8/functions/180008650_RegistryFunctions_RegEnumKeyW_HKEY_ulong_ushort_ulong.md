# RegistryFunctions::RegEnumKeyW(HKEY__ *,ulong,ushort *,ulong)

- ea: `0x180008650`
- end: `0x18000868c`
- name: `?RegEnumKeyW@RegistryFunctions@@UEAAJPEAUHKEY__@@KPEAGK@Z`
- size: `60`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, DWORD, unsigned __int16 *, DWORD cchName)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180008681`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180008681`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegEnumKeyW(
        RegistryFunctions *this,
        HKEY a2,
        DWORD a3,
        unsigned __int16 *a4,
        DWORD cchName)
{
  return RegEnumKeyExW(a2, a3, a4, &cchName, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x180008650  sub     rsp, 48h
0x180008654  xor     ecx, ecx
0x180008656  mov     rax, r9
0x180008659  mov     [rsp+48h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x18000865e  lea     r9, [rsp+48h+cchName]; lpcchName
0x180008663  mov     [rsp+48h+lpcchClass], rcx; lpcchClass
0x180008668  mov     r10d, r8d
0x18000866b  mov     [rsp+48h+lpClass], rcx; lpClass
0x180008670  mov     r11, rdx
0x180008673  mov     [rsp+48h+lpReserved], rcx; lpReserved
0x180008678  mov     r8, rax; lpName
0x18000867b  mov     rcx, r11; hKey
0x18000867e  mov     edx, r10d; dwIndex
0x180008681  call    cs:__imp_RegEnumKeyExW
0x180008687  add     rsp, 48h
0x18000868b  retn
```
