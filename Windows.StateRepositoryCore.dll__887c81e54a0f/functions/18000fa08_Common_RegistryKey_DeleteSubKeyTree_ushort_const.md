# Common::RegistryKey::DeleteSubKeyTree(ushort const *)

- ea: `0x18000fa08`
- end: `0x18000fa26`
- name: `?DeleteSubKeyTree@RegistryKey@Common@@QEAAJPEBG@Z`
- size: `30`
- prototype: `LSTATUS __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d710`
- `0x18000fa2c`

## callees

- `0x18000fa08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000fa0f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000fa0f`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::DeleteSubKeyTree(HKEY *this, const unsigned __int16 *a2)
{
  LSTATUS result; // eax

  result = RegDeleteTreeW(*this, a2);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000fa08  sub     rsp, 28h
0x18000fa0c  mov     rcx, [rcx]; hKey
0x18000fa0f  call    cs:__imp_RegDeleteTreeW
0x18000fa15  test    eax, eax
0x18000fa17  jle     short loc_18000FA21
0x18000fa19  movzx   eax, ax
0x18000fa1c  or      eax, 80070000h
0x18000fa21  add     rsp, 28h
0x18000fa25  retn
```
