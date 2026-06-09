# Common::RegistryKey::SetValue(ushort const *,void const *,ulong,ulong)

- ea: `0x1801096f4`
- end: `0x180109728`
- name: `?SetValue@RegistryKey@Common@@QEAAJPEBGPEBXKK@Z`
- size: `52`
- prototype: `int(Common::RegistryKey *__hidden this, const unsigned __int16 *, const void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801064b4`

## callees

- `0x1801096f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180109711`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180109711`

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
0x1801096f4  sub     rsp, 38h
0x1801096f8  mov     rcx, [rcx]; hKey
0x1801096fb  mov     r9d, 0Bh; dwType
0x180109701  mov     [rsp+38h+cbData], 8; cbData
0x180109709  mov     [rsp+38h+lpData], r8; lpData
0x18010970e  xor     r8d, r8d; Reserved
0x180109711  call    cs:__imp_RegSetValueExW
0x180109717  test    eax, eax
0x180109719  jle     short loc_180109723
0x18010971b  movzx   eax, ax
0x18010971e  or      eax, 80070000h
0x180109723  add     rsp, 38h
0x180109727  retn
```
