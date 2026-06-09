# DllEntryPoint

- ea: `0x18001c4c0`
- end: `0x18001c4fd`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18001c38c`
- `0x18001c4c0`
- `0x18001c500`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_18001C500();
  return sub_18001C38C(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x18001c4c0  mov     [rsp+arg_0], rbx
0x18001c4c5  mov     [rsp+arg_8], rsi
0x18001c4ca  push    rdi
0x18001c4cb  sub     rsp, 20h
0x18001c4cf  mov     rdi, r8
0x18001c4d2  mov     ebx, edx
0x18001c4d4  mov     rsi, rcx
0x18001c4d7  cmp     edx, 1
0x18001c4da  jnz     short loc_18001C4E1
0x18001c4dc  call    sub_18001C500
0x18001c4e1  mov     r8, rdi
0x18001c4e4  mov     edx, ebx
0x18001c4e6  mov     rcx, rsi
0x18001c4e9  mov     rbx, [rsp+28h+arg_0]
0x18001c4ee  mov     rsi, [rsp+28h+arg_8]
0x18001c4f3  add     rsp, 20h
0x18001c4f7  pop     rdi
0x18001c4f8  jmp     sub_18001C38C
```
