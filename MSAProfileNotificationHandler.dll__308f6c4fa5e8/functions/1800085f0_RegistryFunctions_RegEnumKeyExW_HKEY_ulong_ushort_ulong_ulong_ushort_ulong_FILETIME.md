# RegistryFunctions::RegEnumKeyExW(HKEY__ *,ulong,ushort *,ulong *,ulong *,ushort *,ulong *,_FILETIME *)

- ea: `0x1800085f0`
- end: `0x180008647`
- name: `?RegEnumKeyExW@RegistryFunctions@@UEAAJPEAUHKEY__@@KPEAGPEAK212PEAU_FILETIME@@@Z`
- size: `87`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, DWORD, unsigned __int16 *, unsigned int *lpcchName, unsigned int *lpReserved, unsigned __int16 *lpClass, unsigned int *lpcchClass, struct _FILETIME *lpftLastWriteTime)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000863b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000863b`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegEnumKeyExW(
        RegistryFunctions *this,
        HKEY a2,
        DWORD a3,
        unsigned __int16 *a4,
        unsigned int *lpcchName,
        unsigned int *lpReserved,
        unsigned __int16 *lpClass,
        unsigned int *lpcchClass,
        struct _FILETIME *lpftLastWriteTime)
{
  return RegEnumKeyExW(a2, a3, a4, lpcchName, lpReserved, lpClass, lpcchClass, lpftLastWriteTime);
}

```

## disassembly

```asm
0x1800085f0  push    rbx
0x1800085f2  sub     rsp, 40h
0x1800085f6  mov     rax, [rsp+48h+arg_40]
0x1800085fe  mov     r10, r9
0x180008601  mov     r9, [rsp+48h+lpcchName]; lpcchName
0x180008606  mov     r11d, r8d
0x180008609  mov     [rsp+48h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000860e  mov     rcx, rdx; hKey
0x180008611  mov     rax, [rsp+48h+arg_38]
0x180008619  mov     r8, r10; lpName
0x18000861c  mov     [rsp+48h+lpcchClass], rax; lpcchClass
0x180008621  mov     edx, r11d; dwIndex
0x180008624  mov     rax, [rsp+48h+arg_30]
0x18000862c  mov     [rsp+48h+lpClass], rax; lpClass
0x180008631  mov     rax, [rsp+48h+arg_28]
0x180008636  mov     [rsp+48h+lpReserved], rax; lpReserved
0x18000863b  call    cs:__imp_RegEnumKeyExW
0x180008641  add     rsp, 40h
0x180008645  pop     rbx
0x180008646  retn
```
