# DllMain

- ea: `0x180009dec`
- end: `0x180009e14`
- name: `DllMain`
- size: `40`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001e54`

## callees

- `0x180009dec`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x180009dfb`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180009dfb`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v3; // ebx

  v3 = 1;
  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    return !ATL::CAtlBaseModule::m_bInitFailed;
  }
  return v3;
}

```

## disassembly

```asm
0x180009dec  push    rbx
0x180009dee  sub     rsp, 20h
0x180009df2  mov     ebx, 1
0x180009df7  cmp     edx, ebx
0x180009df9  jnz     short loc_180009E0C
0x180009dfb  call    cs:__imp_DisableThreadLibraryCalls
0x180009e01  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x180009e08  jz      short loc_180009E0C
0x180009e0a  xor     ebx, ebx
0x180009e0c  mov     eax, ebx
0x180009e0e  add     rsp, 20h
0x180009e12  pop     rbx
0x180009e13  retn
```
