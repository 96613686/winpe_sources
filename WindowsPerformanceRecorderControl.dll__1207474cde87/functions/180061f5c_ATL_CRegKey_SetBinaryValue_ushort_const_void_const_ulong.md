# ATL::CRegKey::SetBinaryValue(ushort const *,void const *,ulong)

- ea: `0x180061f5c`
- end: `0x180061f81`
- name: `?SetBinaryValue@CRegKey@ATL@@QEAAJPEBGPEBXK@Z`
- size: `37`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const void *, unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18003415c`
- `0x18003c92c`
- `0x180060f8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061f76`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061f76`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetBinaryValue(
        HKEY *this,
        const unsigned __int16 *a2,
        const BYTE *lpData,
        DWORD cbData)
{
  return RegSetValueExW(*this, a2, 0, 3u, lpData, cbData);
}

```

## disassembly

```asm
0x180061f5c  sub     rsp, 38h
0x180061f60  mov     rcx, [rcx]; hKey
0x180061f63  mov     [rsp+38h+cbData], r9d; cbData
0x180061f68  mov     r9d, 3; dwType
0x180061f6e  mov     [rsp+38h+lpData], r8; lpData
0x180061f73  xor     r8d, r8d; Reserved
0x180061f76  call    cs:__imp_RegSetValueExW
0x180061f7c  add     rsp, 38h
0x180061f80  retn
```
