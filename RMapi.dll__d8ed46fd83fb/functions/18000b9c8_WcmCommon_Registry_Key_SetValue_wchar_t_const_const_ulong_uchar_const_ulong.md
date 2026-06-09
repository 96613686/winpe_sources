# WcmCommon::Registry::Key::SetValue(wchar_t const * const,ulong,uchar const *,ulong)

- ea: `0x18000b9c8`
- end: `0x18000b9f9`
- name: `?SetValue@Key@Registry@WcmCommon@@QEAAJQEB_WKPEBEK@Z`
- size: `49`
- prototype: `int(WcmCommon::Registry::Key *__hidden this, const wchar_t *const, unsigned int, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b960`

## callees

- `0x18000b9c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b9e2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b9e2`

## pseudocode

```c
LSTATUS __fastcall WcmCommon::Registry::Key::SetValue(
        HKEY *this,
        const WCHAR *a2,
        DWORD a3,
        const unsigned __int8 *lpData,
        DWORD cbData)
{
  LSTATUS result; // eax

  result = RegSetValueExW(*this, a2, 0, a3, lpData, cbData);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000b9c8  sub     rsp, 38h
0x18000b9cc  mov     eax, [rsp+38h+arg_20]
0x18000b9d0  mov     rcx, [rcx]; hKey
0x18000b9d3  mov     [rsp+38h+cbData], eax; cbData
0x18000b9d7  mov     [rsp+38h+lpData], r9; lpData
0x18000b9dc  mov     r9d, r8d; dwType
0x18000b9df  xor     r8d, r8d; Reserved
0x18000b9e2  call    cs:__imp_RegSetValueExW
0x18000b9e8  test    eax, eax
0x18000b9ea  jle     short loc_18000B9F4
0x18000b9ec  movzx   eax, ax
0x18000b9ef  or      eax, 80070000h
0x18000b9f4  add     rsp, 38h
0x18000b9f8  retn
```
