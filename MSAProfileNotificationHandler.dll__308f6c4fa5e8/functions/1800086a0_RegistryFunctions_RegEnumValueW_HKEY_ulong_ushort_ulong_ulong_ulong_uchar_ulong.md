# RegistryFunctions::RegEnumValueW(HKEY__ *,ulong,ushort *,ulong *,ulong *,ulong *,uchar *,ulong *)

- ea: `0x1800086a0`
- end: `0x1800086f7`
- name: `?RegEnumValueW@RegistryFunctions@@UEAAJPEAUHKEY__@@KPEAGPEAK22PEAE2@Z`
- size: `87`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, DWORD, unsigned __int16 *, unsigned int *lpcchValueName, unsigned int *lpReserved, unsigned int *lpType, unsigned __int8 *lpData, unsigned int *lpcbData)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800086eb`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800086eb`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegEnumValueW(
        RegistryFunctions *this,
        HKEY a2,
        DWORD a3,
        unsigned __int16 *a4,
        unsigned int *lpcchValueName,
        unsigned int *lpReserved,
        unsigned int *lpType,
        unsigned __int8 *lpData,
        unsigned int *lpcbData)
{
  return RegEnumValueW(a2, a3, a4, lpcchValueName, lpReserved, lpType, lpData, lpcbData);
}

```

## disassembly

```asm
0x1800086a0  push    rbx
0x1800086a2  sub     rsp, 40h
0x1800086a6  mov     rax, [rsp+48h+arg_40]
0x1800086ae  mov     r10, r9
0x1800086b1  mov     r9, [rsp+48h+lpcchValueName]; lpcchValueName
0x1800086b6  mov     r11d, r8d
0x1800086b9  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800086be  mov     rcx, rdx; hKey
0x1800086c1  mov     rax, [rsp+48h+arg_38]
0x1800086c9  mov     r8, r10; lpValueName
0x1800086cc  mov     [rsp+48h+lpData], rax; lpData
0x1800086d1  mov     edx, r11d; dwIndex
0x1800086d4  mov     rax, [rsp+48h+arg_30]
0x1800086dc  mov     [rsp+48h+lpType], rax; lpType
0x1800086e1  mov     rax, [rsp+48h+arg_28]
0x1800086e6  mov     [rsp+48h+lpReserved], rax; lpReserved
0x1800086eb  call    cs:__imp_RegEnumValueW
0x1800086f1  add     rsp, 40h
0x1800086f5  pop     rbx
0x1800086f6  retn
```
