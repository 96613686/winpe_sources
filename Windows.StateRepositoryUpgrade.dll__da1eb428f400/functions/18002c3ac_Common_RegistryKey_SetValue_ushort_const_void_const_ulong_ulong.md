# Common::RegistryKey::SetValue(ushort const *,void const *,ulong,ulong)

- ea: `0x18002c3ac`
- end: `0x18002c3e0`
- name: `?SetValue@RegistryKey@Common@@QEAAJPEBGPEBXKK@Z`
- size: `52`
- prototype: `int(Common::RegistryKey *__hidden this, const unsigned __int16 *, const void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024f74`

## callees

- `0x18002c3ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c3c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c3c9`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::SetValue(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData)
{
  LSTATUS result; // eax

  result = RegSetValueExW(*this, a2, 0, 0xBu, lpData, 8u);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002c3ac  sub     rsp, 38h
0x18002c3b0  mov     rcx, [rcx]; hKey
0x18002c3b3  mov     r9d, 0Bh; dwType
0x18002c3b9  mov     [rsp+38h+cbData], 8; cbData
0x18002c3c1  mov     [rsp+38h+lpData], r8; lpData
0x18002c3c6  xor     r8d, r8d; Reserved
0x18002c3c9  call    cs:__imp_RegSetValueExW
0x18002c3cf  test    eax, eax
0x18002c3d1  jle     short loc_18002C3DB
0x18002c3d3  movzx   eax, ax
0x18002c3d6  or      eax, 80070000h
0x18002c3db  add     rsp, 38h
0x18002c3df  retn
```
