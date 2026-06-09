# DllMain

- ea: `0x1800090ac`
- end: `0x1800090db`
- name: `DllMain`
- size: `47`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001724`

## callees

- `0x1800090ac`
- `0x180020ec8`
- `0x180020f00`

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
0x1800090ac  sub     rsp, 28h
0x1800090b0  test    edx, edx
0x1800090b2  jz      short loc_1800090C7
0x1800090b4  sub     edx, 1
0x1800090b7  jnz     short loc_1800090D1
0x1800090b9  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInst
0x1800090c0  call    McGenEventRegister_EventRegister
0x1800090c5  jmp     short loc_1800090D1
0x1800090c7  test    r8, r8
0x1800090ca  jnz     short loc_1800090D1
0x1800090cc  call    McGenEventUnregister_EventUnregister
0x1800090d1  mov     eax, 1
0x1800090d6  add     rsp, 28h
0x1800090da  retn
```
