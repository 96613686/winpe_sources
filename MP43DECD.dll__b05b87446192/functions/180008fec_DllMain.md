# DllMain

- ea: `0x180008fec`
- end: `0x18000901b`
- name: `DllMain`
- size: `47`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800016f4`

## callees

- `0x180008fec`
- `0x180020e08`
- `0x180020e40`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // rdx

  if ( fdwReason )
  {
    v3 = fdwReason - 1;
    if ( !(_DWORD)v3 )
    {
      g_hInst = hinstDLL;
      McGenEventRegister_EventRegister(hinstDLL, v3, lpvReserved);
    }
  }
  else if ( !lpvReserved )
  {
    McGenEventUnregister_EventUnregister(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x180008fec  sub     rsp, 28h
0x180008ff0  test    edx, edx
0x180008ff2  jz      short loc_180009007
0x180008ff4  sub     edx, 1
0x180008ff7  jnz     short loc_180009011
0x180008ff9  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInst
0x180009000  call    McGenEventRegister_EventRegister
0x180009005  jmp     short loc_180009011
0x180009007  test    r8, r8
0x18000900a  jnz     short loc_180009011
0x18000900c  call    McGenEventUnregister_EventUnregister
0x180009011  mov     eax, 1
0x180009016  add     rsp, 28h
0x18000901a  retn
```
