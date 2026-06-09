# DllEntryPoint

- ea: `0x1801658d0`
- end: `0x18016590d`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18016579c`
- `0x1801658d0`
- `0x180165f80`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_180165F80();
  return sub_18016579C(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x1801658d0  mov     [rsp+arg_0], rbx
0x1801658d5  mov     [rsp+arg_8], rsi
0x1801658da  push    rdi
0x1801658db  sub     rsp, 20h
0x1801658df  mov     rdi, r8
0x1801658e2  mov     ebx, edx
0x1801658e4  mov     rsi, rcx
0x1801658e7  cmp     edx, 1
0x1801658ea  jnz     short loc_1801658F1
0x1801658ec  call    sub_180165F80
0x1801658f1  mov     r8, rdi
0x1801658f4  mov     edx, ebx
0x1801658f6  mov     rcx, rsi
0x1801658f9  mov     rbx, [rsp+28h+arg_0]
0x1801658fe  mov     rsi, [rsp+28h+arg_8]
0x180165903  add     rsp, 20h
0x180165907  pop     rdi
0x180165908  jmp     sub_18016579C
```
