# RegistryFunctions::RegQueryValueExW(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *)

- ea: `0x1800088e0`
- end: `0x18000891a`
- name: `?RegQueryValueExW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBGPEAK2PEAE2@Z`
- size: `58`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *, unsigned int *, unsigned int *lpType, unsigned __int8 *lpData, unsigned int *lpcbData)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000890e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000890e`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegQueryValueExW(
        RegistryFunctions *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        unsigned int *lpType,
        unsigned __int8 *lpData,
        unsigned int *lpcbData)
{
  return RegQueryValueExW(a2, a3, a4, lpType, lpData, lpcbData);
}

```

## disassembly

```asm
0x1800088e0  push    rbx
0x1800088e2  sub     rsp, 30h
0x1800088e6  mov     rax, [rsp+38h+arg_30]
0x1800088eb  mov     r10, r9
0x1800088ee  mov     r9, [rsp+38h+lpType]; lpType
0x1800088f3  mov     r11, r8
0x1800088f6  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800088fb  mov     rcx, rdx; hKey
0x1800088fe  mov     rax, [rsp+38h+arg_28]
0x180008903  mov     r8, r10; lpReserved
0x180008906  mov     rdx, r11; lpValueName
0x180008909  mov     [rsp+38h+lpData], rax; lpData
0x18000890e  call    cs:__imp_RegQueryValueExW
0x180008914  add     rsp, 30h
0x180008918  pop     rbx
0x180008919  retn
```
