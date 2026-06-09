# DllMain

- ea: `0x1800049cc`
- end: `0x1800049ff`
- name: `DllMain`
- size: `51`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001484`

## callees

- `0x1800049cc`
- `0x180004b18`
- `0x180004b50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800049d5`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800049d5`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL result; // eax

  if ( fdwReason != 1 )
  {
    if ( !fdwReason )
      McGenEventUnregister_EventUnregister(hinstDLL, fdwReason, lpvReserved);
    return 1;
  }
  DisableThreadLibraryCalls(hinstDLL);
  McGenEventRegister_EventRegister();
  result = 0;
  if ( !ATL::CAtlBaseModule::m_bInitFailed )
    return 1;
  return result;
}

```

## disassembly

```asm
0x1800049cc  sub     rsp, 28h
0x1800049d0  cmp     edx, 1
0x1800049d3  jnz     short loc_1800049EC
0x1800049d5  call    cs:__imp_DisableThreadLibraryCalls
0x1800049db  call    McGenEventRegister_EventRegister
0x1800049e0  xor     eax, eax
0x1800049e2  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, al; bool ATL::CAtlBaseModule::m_bInitFailed
0x1800049e8  jz      short loc_1800049F5
0x1800049ea  jmp     short loc_1800049FA
0x1800049ec  test    edx, edx
0x1800049ee  jnz     short loc_1800049F5
0x1800049f0  call    McGenEventUnregister_EventUnregister
0x1800049f5  mov     eax, 1
0x1800049fa  add     rsp, 28h
0x1800049fe  retn
```
