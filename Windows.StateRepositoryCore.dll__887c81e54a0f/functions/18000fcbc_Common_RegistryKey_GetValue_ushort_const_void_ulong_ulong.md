# Common::RegistryKey::GetValue(ushort const *,void *,ulong *,ulong *)

- ea: `0x18000fcbc`
- end: `0x18000fcec`
- name: `?GetValue@RegistryKey@Common@@QEAAJPEBGPEAXPEAK2@Z`
- size: `48`
- prototype: `LSTATUS __fastcall(HKEY *this, const unsigned __int16 *, BYTE *lpData, unsigned int *lpcbData, unsigned int *lpType)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fc70`

## callees

- `0x18000fcbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fcd5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fcd5`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::GetValue(
        HKEY *this,
        const unsigned __int16 *a2,
        BYTE *lpData,
        unsigned int *lpcbData,
        unsigned int *lpType)
{
  LSTATUS result; // eax

  result = RegQueryValueExW(*this, a2, 0, lpType, lpData, lpcbData);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000fcbc  sub     rsp, 38h
0x18000fcc0  mov     rcx, [rcx]; hKey
0x18000fcc3  mov     [rsp+38h+lpcbData], r9; lpcbData
0x18000fcc8  mov     r9, [rsp+38h+lpType]; lpType
0x18000fccd  mov     [rsp+38h+lpData], r8; lpData
0x18000fcd2  xor     r8d, r8d; lpReserved
0x18000fcd5  call    cs:__imp_RegQueryValueExW
0x18000fcdb  test    eax, eax
0x18000fcdd  jle     short loc_18000FCE7
0x18000fcdf  movzx   eax, ax
0x18000fce2  or      eax, 80070000h
0x18000fce7  add     rsp, 38h
0x18000fceb  retn
```
