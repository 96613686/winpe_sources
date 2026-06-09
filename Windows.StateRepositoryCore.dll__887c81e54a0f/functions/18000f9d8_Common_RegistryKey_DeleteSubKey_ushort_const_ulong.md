# Common::RegistryKey::DeleteSubKey(ushort const *,ulong)

- ea: `0x18000f9d8`
- end: `0x18000f9ff`
- name: `?DeleteSubKey@RegistryKey@Common@@QEAAJPEBGK@Z`
- size: `39`
- prototype: `LSTATUS __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c154`

## callees

- `0x18000f9d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000f9e8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000f9e8`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::DeleteSubKey(HKEY *this, const unsigned __int16 *a2)
{
  LSTATUS result; // eax

  result = RegDeleteKeyExW(*this, a2, 0x100u, 0);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000f9d8  sub     rsp, 28h
0x18000f9dc  mov     rcx, [rcx]; hKey
0x18000f9df  xor     r9d, r9d; Reserved
0x18000f9e2  mov     r8d, 100h; samDesired
0x18000f9e8  call    cs:__imp_RegDeleteKeyExW
0x18000f9ee  test    eax, eax
0x18000f9f0  jle     short loc_18000F9FA
0x18000f9f2  movzx   eax, ax
0x18000f9f5  or      eax, 80070000h
0x18000f9fa  add     rsp, 28h
0x18000f9fe  retn
```
