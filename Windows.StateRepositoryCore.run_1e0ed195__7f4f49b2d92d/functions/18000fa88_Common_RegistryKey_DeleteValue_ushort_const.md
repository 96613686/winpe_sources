# Common::RegistryKey::DeleteValue(ushort const *)

- ea: `0x18000fa88`
- end: `0x18000faa6`
- name: `?DeleteValue@RegistryKey@Common@@QEAAJPEBG@Z`
- size: `30`
- prototype: `__int64 __fastcall(Common::RegistryKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cc90`

## callees

- `0x18000fa88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fa8f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fa8f`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::DeleteValue(HKEY *this, const unsigned __int16 *a2)
{
  LSTATUS result; // eax

  result = RegDeleteValueW(*this, a2);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000fa88  sub     rsp, 28h
0x18000fa8c  mov     rcx, [rcx]; hKey
0x18000fa8f  call    cs:__imp_RegDeleteValueW
0x18000fa95  test    eax, eax
0x18000fa97  jle     short loc_18000FAA1
0x18000fa99  movzx   eax, ax
0x18000fa9c  or      eax, 80070000h
0x18000faa1  add     rsp, 28h
0x18000faa5  retn
```
