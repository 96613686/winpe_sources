# _dynamic_atexit_destructor_for__g_PitrDll__

- ea: `0x180011090`
- end: `0x1800110c4`
- name: `_dynamic_atexit_destructor_for__g_PitrDll__`
- size: `52`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011090`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800110ae`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800110ae`

## pseudocode

```c
int dynamic_atexit_destructor_for__g_PitrDll__()
{
  void **v0; // rax

  v0 = &RAII::CAutoFreeLibrary::`vftable';
  g_PitrDll = &RAII::CAutoFreeLibrary::`vftable';
  if ( hLibModule )
  {
    LODWORD(v0) = FreeLibrary(hLibModule);
    hLibModule = 0;
  }
  return (int)v0;
}

```

## disassembly

```asm
0x180011090  sub     rsp, 28h
0x180011094  mov     rcx, cs:hLibModule; hLibModule
0x18001109b  lea     rax, ??_7CAutoFreeLibrary@RAII@@6B@; const RAII::CAutoFreeLibrary::`vftable'
0x1800110a2  mov     cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A, rax; RAII::CAutoFreeLibrary g_PitrDll
0x1800110a9  test    rcx, rcx
0x1800110ac  jz      short loc_1800110BF
0x1800110ae  call    cs:__imp_FreeLibrary
0x1800110b4  mov     cs:hLibModule, 0
0x1800110bf  add     rsp, 28h
0x1800110c3  retn
```
