# DllEntryPoint

- ea: `0x1800230d0`
- end: `0x18002310d`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180022f9c`
- `0x1800230d0`
- `0x180023110`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_180023110();
  return sub_180022F9C(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x1800230d0  mov     [rsp+arg_0], rbx
0x1800230d5  mov     [rsp+arg_8], rsi
0x1800230da  push    rdi
0x1800230db  sub     rsp, 20h
0x1800230df  mov     rdi, r8
0x1800230e2  mov     ebx, edx
0x1800230e4  mov     rsi, rcx
0x1800230e7  cmp     edx, 1
0x1800230ea  jnz     short loc_1800230F1
0x1800230ec  call    sub_180023110
0x1800230f1  mov     r8, rdi
0x1800230f4  mov     edx, ebx
0x1800230f6  mov     rcx, rsi
0x1800230f9  mov     rbx, [rsp+28h+arg_0]
0x1800230fe  mov     rsi, [rsp+28h+arg_8]
0x180023103  add     rsp, 20h
0x180023107  pop     rdi
0x180023108  jmp     sub_180022F9C
```
