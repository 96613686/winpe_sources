# Common::RegistryKey::DeleteSubKeyTree(ushort const *)

- ea: `0x18002c098`
- end: `0x18002c0bd`
- name: `?DeleteSubKeyTree@RegistryKey@Common@@QEAAJPEBG@Z`
- size: `37`
- prototype: `__int64 __fastcall(Common::RegistryKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e620`

## callees

- `0x18002c098`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002c0a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002c0a6`

## string_xrefs

- `0x18002c09f`: `Extensions`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::DeleteSubKeyTree(HKEY *this, const unsigned __int16 *a2)
{
  LSTATUS result; // eax

  result = RegDeleteTreeW(*this, L"Extensions");
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002c098  sub     rsp, 28h
0x18002c09c  mov     rcx, [rcx]; hKey
0x18002c09f  lea     rdx, SubKey; "Extensions"
0x18002c0a6  call    cs:__imp_RegDeleteTreeW
0x18002c0ac  test    eax, eax
0x18002c0ae  jle     short loc_18002C0B8
0x18002c0b0  movzx   eax, ax
0x18002c0b3  or      eax, 80070000h
0x18002c0b8  add     rsp, 28h
0x18002c0bc  retn
```
