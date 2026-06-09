# std::unique_ptr<HKEY__,release::Deleter<void>>::~unique_ptr<HKEY__,release::Deleter<void>>(void)

- ea: `0x140002814`
- end: `0x14000282c`
- name: `??1?$unique_ptr@UHKEY__@@U?$Deleter@X@release@@@std@@QEAA@XZ`
- size: `24`
- prototype: `LSTATUS __fastcall(HKEY *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140013cd7`
- `0x140013ce9`
- `0x140013cfb`
- `0x140013d1f`

## callees

- `0x140002814`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002820`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002820`

## pseudocode

```c
LSTATUS __fastcall std::unique_ptr<HKEY__,release::Deleter<void>>::~unique_ptr<HKEY__,release::Deleter<void>>(HKEY *a1)
{
  HKEY v1; // rcx
  LSTATUS result; // eax

  v1 = *a1;
  if ( v1 )
    return RegCloseKey(v1);
  return result;
}

```

## disassembly

```asm
0x140002814  sub     rsp, 28h
0x140002818  mov     rcx, [rcx]; hKey
0x14000281b  test    rcx, rcx
0x14000281e  jz      short loc_140002827
0x140002820  call    cs:__imp_RegCloseKey
0x140002826  nop
0x140002827  add     rsp, 28h
0x14000282b  retn
```
