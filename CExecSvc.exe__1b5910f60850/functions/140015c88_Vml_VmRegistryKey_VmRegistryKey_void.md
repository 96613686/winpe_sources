# Vml::VmRegistryKey::~VmRegistryKey(void)

- ea: `0x140015c88`
- end: `0x140015cac`
- name: `??1VmRegistryKey@Vml@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14002313b`
- `0x14002314d`

## callees

- `0x140015c88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140015c99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140015c99`

## pseudocode

```c
void __fastcall Vml::VmRegistryKey::~VmRegistryKey(HKEY *this)
{
  HKEY v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    RegCloseKey(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x140015c88  push    rbx
0x140015c8a  sub     rsp, 20h
0x140015c8e  mov     rbx, rcx
0x140015c91  mov     rcx, [rcx]; hKey
0x140015c94  test    rcx, rcx
0x140015c97  jz      short loc_140015CA6
0x140015c99  call    cs:__imp_RegCloseKey
0x140015c9f  mov     qword ptr [rbx], 0
0x140015ca6  add     rsp, 20h
0x140015caa  pop     rbx
0x140015cab  retn
```
