# std::unique_ptr<HKEY__ *,release::Deleter<void>>::~unique_ptr<HKEY__ *,release::Deleter<void>>(void)

- ea: `0x1400027b4`
- end: `0x1400027cf`
- name: `??1?$unique_ptr@PEAUHKEY__@@U?$Deleter@X@release@@@std@@QEAA@XZ`
- size: `27`
- prototype: `LSTATUS __fastcall(HKEY **)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140013e34`
- `0x140013e6a`

## callees

- `0x1400027b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400027c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400027c3`

## pseudocode

```c
LSTATUS __fastcall std::unique_ptr<HKEY__ *,release::Deleter<void>>::~unique_ptr<HKEY__ *,release::Deleter<void>>(
        HKEY **a1)
{
  HKEY *v1; // rcx
  LSTATUS result; // eax

  v1 = *a1;
  if ( v1 )
    return RegCloseKey(*v1);
  return result;
}

```

## disassembly

```asm
0x1400027b4  sub     rsp, 28h
0x1400027b8  mov     rcx, [rcx]
0x1400027bb  test    rcx, rcx
0x1400027be  jz      short loc_1400027CA
0x1400027c0  mov     rcx, [rcx]; hKey
0x1400027c3  call    cs:__imp_RegCloseKey
0x1400027c9  nop
0x1400027ca  add     rsp, 28h
0x1400027ce  retn
```
