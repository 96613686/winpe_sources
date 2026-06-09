# Common::RegistryKey::SetValue(ushort const *,void const *,ulong,ulong)

- ea: `0x18000fdf0`
- end: `0x18000fe20`
- name: `?SetValue@RegistryKey@Common@@QEAAJPEBGPEBXKK@Z`
- size: `48`
- prototype: `int(Common::RegistryKey *__hidden this, const unsigned __int16 *, const void *, unsigned int, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c7f0`
- `0x18000d280`
- `0x18000d310`
- `0x18000d3d0`
- `0x18000d450`
- `0x18000d9d0`
- `0x18000da40`

## callees

- `0x18000fdf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fe09`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fe09`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::SetValue(
        HKEY *this,
        const unsigned __int16 *a2,
        const BYTE *lpData,
        DWORD cbData,
        DWORD dwType)
{
  LSTATUS result; // eax

  result = RegSetValueExW(*this, a2, 0, dwType, lpData, cbData);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000fdf0  sub     rsp, 38h
0x18000fdf4  mov     rcx, [rcx]; hKey
0x18000fdf7  mov     [rsp+38h+cbData], r9d; cbData
0x18000fdfc  mov     r9d, [rsp+38h+dwType]; dwType
0x18000fe01  mov     [rsp+38h+lpData], r8; lpData
0x18000fe06  xor     r8d, r8d; Reserved
0x18000fe09  call    cs:__imp_RegSetValueExW
0x18000fe0f  test    eax, eax
0x18000fe11  jle     short loc_18000FE1B
0x18000fe13  movzx   eax, ax
0x18000fe16  or      eax, 80070000h
0x18000fe1b  add     rsp, 38h
0x18000fe1f  retn
```
