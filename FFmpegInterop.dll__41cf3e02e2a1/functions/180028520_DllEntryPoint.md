# DllEntryPoint

- ea: `0x180028520`
- end: `0x18002855d`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800283ec`
- `0x180028520`
- `0x180028b0c`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_180028B0C();
  return sub_1800283EC(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180028520  mov     [rsp+arg_0], rbx
0x180028525  mov     [rsp+arg_8], rsi
0x18002852a  push    rdi
0x18002852b  sub     rsp, 20h
0x18002852f  mov     rdi, r8
0x180028532  mov     ebx, edx
0x180028534  mov     rsi, rcx
0x180028537  cmp     edx, 1
0x18002853a  jnz     short loc_180028541
0x18002853c  call    sub_180028B0C
0x180028541  mov     r8, rdi
0x180028544  mov     edx, ebx
0x180028546  mov     rcx, rsi
0x180028549  mov     rbx, [rsp+28h+arg_0]
0x18002854e  mov     rsi, [rsp+28h+arg_8]
0x180028553  add     rsp, 20h
0x180028557  pop     rdi
0x180028558  jmp     sub_1800283EC
```
