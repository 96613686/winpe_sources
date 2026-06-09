# RegistryKey::~RegistryKey(void)

- ea: `0x180005308`
- end: `0x18000531f`
- name: `??1RegistryKey@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006208`
- `0x180006af8`
- `0x18000e0d8`
- `0x180012240`
- `0x180012260`
- `0x180012280`
- `0x180012584`
- `0x1800129f1`
- `0x180012a15`
- `0x180014196`
- `0x1800141a8`

## callees

- `0x180005308`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005314`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005314`

## pseudocode

```c
void __fastcall RegistryKey::~RegistryKey(HKEY *this)
{
  HKEY v1; // rcx

  v1 = *this;
  if ( v1 )
    RegCloseKey(v1);
}

```

## disassembly

```asm
0x180005308  sub     rsp, 28h
0x18000530c  mov     rcx, [rcx]; hKey
0x18000530f  test    rcx, rcx
0x180005312  jz      short loc_18000531A
0x180005314  call    cs:__imp_RegCloseKey
0x18000531a  add     rsp, 28h
0x18000531e  retn
```
