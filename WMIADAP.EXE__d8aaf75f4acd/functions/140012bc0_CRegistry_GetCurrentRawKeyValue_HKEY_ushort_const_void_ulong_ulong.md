# CRegistry::GetCurrentRawKeyValue(HKEY__ *,ushort const *,void *,ulong *,ulong *)

- ea: `0x140012bc0`
- end: `0x140012bef`
- name: `?GetCurrentRawKeyValue@CRegistry@@AEAAKPEAUHKEY__@@PEBGPEAXPEAK3@Z`
- size: `47`
- prototype: `LSTATUS __fastcall(CRegistry *this, HKEY, const unsigned __int16 *, BYTE *lpData, unsigned int *lpType, unsigned int *lpcbData)`
- caller_count: `7`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1400124d0`
- `0x140012500`
- `0x140012620`
- `0x140012660`
- `0x140012720`
- `0x140012a00`
- `0x140012c00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012be4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012be4`

## pseudocode

```c
LSTATUS __fastcall CRegistry::GetCurrentRawKeyValue(
        CRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3,
        BYTE *lpData,
        unsigned int *lpType,
        unsigned int *lpcbData)
{
  return RegQueryValueExW(a2, a3, 0, lpType, lpData, lpcbData);
}

```

## disassembly

```asm
0x140012bc0  sub     rsp, 38h
0x140012bc4  mov     rax, [rsp+38h+arg_28]
0x140012bc9  mov     r10, r8
0x140012bcc  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140012bd1  mov     rcx, rdx; hKey
0x140012bd4  mov     [rsp+38h+lpData], r9; lpData
0x140012bd9  xor     r8d, r8d; lpReserved
0x140012bdc  mov     r9, [rsp+38h+lpType]; lpType
0x140012be1  mov     rdx, r10; lpValueName
0x140012be4  call    cs:__imp_RegQueryValueExW
0x140012bea  add     rsp, 38h
0x140012bee  retn
```
