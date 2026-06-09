# DllMain

- ea: `0x1800063ac`
- end: `0x1800063d0`
- name: `DllMain`
- size: `36`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001394`

## callees

- `0x1800063ac`
- `0x1800064e8`
- `0x180006528`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
      McGenEventRegister_EventRegister(hinstDLL, fdwReason, lpvReserved);
  }
  else
  {
    McGenEventUnregister_EventUnregister(hinstDLL, fdwReason, lpvReserved);
  }
  return 1;
}

```

## disassembly

```asm
0x1800063ac  sub     rsp, 28h
0x1800063b0  test    edx, edx
0x1800063b2  jz      short loc_1800063C0
0x1800063b4  cmp     edx, 1
0x1800063b7  jnz     short loc_1800063C5
0x1800063b9  call    McGenEventRegister_EventRegister
0x1800063be  jmp     short loc_1800063C5
0x1800063c0  call    McGenEventUnregister_EventUnregister
0x1800063c5  mov     eax, 1
0x1800063ca  add     rsp, 28h
0x1800063ce  retn
```
