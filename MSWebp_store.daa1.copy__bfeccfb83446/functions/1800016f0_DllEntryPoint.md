# DllEntryPoint

- ea: `0x1800016f0`
- end: `0x18000172d`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800015bc`
- `0x1800016f0`
- `0x180001b64`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_180001B64();
  return sub_1800015BC(hinstDLL);
}

```

## disassembly

```asm
0x1800016f0  mov     [rsp+arg_0], rbx
0x1800016f5  mov     [rsp+arg_8], rsi
0x1800016fa  push    rdi
0x1800016fb  sub     rsp, 20h
0x1800016ff  mov     rdi, r8
0x180001702  mov     ebx, edx
0x180001704  mov     rsi, rcx
0x180001707  cmp     edx, 1
0x18000170a  jnz     short loc_180001711
0x18000170c  call    sub_180001B64
0x180001711  mov     r8, rdi
0x180001714  mov     edx, ebx
0x180001716  mov     rcx, rsi; hLibModule
0x180001719  mov     rbx, [rsp+28h+arg_0]
0x18000171e  mov     rsi, [rsp+28h+arg_8]
0x180001723  add     rsp, 20h
0x180001727  pop     rdi
0x180001728  jmp     sub_1800015BC
```
