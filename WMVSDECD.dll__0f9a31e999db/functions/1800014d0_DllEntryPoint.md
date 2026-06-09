# DllEntryPoint

- ea: `0x1800014d0`
- end: `0x18000150d`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001394`
- `0x1800014d0`
- `0x1800015b4`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_1800015B4();
  return sub_180001394(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x1800014d0  mov     [rsp+arg_0], rbx
0x1800014d5  mov     [rsp+arg_8], rsi
0x1800014da  push    rdi
0x1800014db  sub     rsp, 20h
0x1800014df  mov     rdi, r8
0x1800014e2  mov     ebx, edx
0x1800014e4  mov     rsi, rcx
0x1800014e7  cmp     edx, 1
0x1800014ea  jnz     short loc_1800014F1
0x1800014ec  call    sub_1800015B4
0x1800014f1  mov     r8, rdi
0x1800014f4  mov     edx, ebx
0x1800014f6  mov     rcx, rsi
0x1800014f9  mov     rbx, [rsp+28h+arg_0]
0x1800014fe  mov     rsi, [rsp+28h+arg_8]
0x180001503  add     rsp, 20h
0x180001507  pop     rdi
0x180001508  jmp     sub_180001394
```
