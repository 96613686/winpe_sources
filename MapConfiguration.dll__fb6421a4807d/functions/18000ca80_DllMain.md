# DllMain

- ea: `0x18000ca80`
- end: `0x18000cab2`
- name: `DllMain`
- size: `50`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180009314`

## callees

- `0x18000ca80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ca8d`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ca8d`
- `ZTrace_Maps!ZTraceInit` at `0x18000ca9a`
- `ZTrace_Maps!ZTraceInit` at `0x18000ca9a`
- `ZTrace_Maps!ZTraceClose` at `0x18000caa2`
- `ZTrace_Maps!ZTraceClose` at `0x18000caa2`

## string_xrefs

- `0x18000ca93`: `*** starting ztrace:onecoreuap\windows\maps\mapengine\mapconfiguration\dllmain.cpp***`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      ZTraceInit("*** starting ztrace:onecoreuap\\windows\\maps\\mapengine\\mapconfiguration\\dllmain.cpp***");
    }
  }
  else
  {
    ZTraceClose();
  }
  return 1;
}

```

## disassembly

```asm
0x18000ca80  sub     rsp, 28h
0x18000ca84  test    edx, edx
0x18000ca86  jz      short loc_18000CAA2
0x18000ca88  cmp     edx, 1
0x18000ca8b  jnz     short loc_18000CAA8
0x18000ca8d  call    cs:__imp_DisableThreadLibraryCalls
0x18000ca93  lea     rcx, aStartingZtrace; "*** starting ztrace:onecoreuap\\windows"...
0x18000ca9a  call    cs:__imp_?ZTraceInit@@YAXPEBD@Z; ZTraceInit(char const *)
0x18000caa0  jmp     short loc_18000CAA8
0x18000caa2  call    cs:__imp_?ZTraceClose@@YAXXZ; ZTraceClose(void)
0x18000caa8  mov     eax, 1
0x18000caad  add     rsp, 28h
0x18000cab1  retn
```
