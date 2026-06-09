# _DllMainCRTStartup

- ea: `0x1800076c0`
- end: `0x1800076fd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076c0`
- `0x180007704`
- `0x180007db4`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return _DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x1800076c0  mov     [rsp+arg_0], rbx
0x1800076c5  mov     [rsp+arg_8], rsi
0x1800076ca  push    rdi
0x1800076cb  sub     rsp, 20h
0x1800076cf  mov     rdi, r8
0x1800076d2  mov     ebx, edx
0x1800076d4  mov     rsi, rcx
0x1800076d7  cmp     edx, 1
0x1800076da  jnz     short loc_1800076E1
0x1800076dc  call    __security_init_cookie
0x1800076e1  mov     r8, rdi
0x1800076e4  mov     edx, ebx; fdwReason
0x1800076e6  mov     rcx, rsi; hinstDLL
0x1800076e9  mov     rbx, [rsp+28h+arg_0]
0x1800076ee  mov     rsi, [rsp+28h+arg_8]
0x1800076f3  add     rsp, 20h
0x1800076f7  pop     rdi
0x1800076f8  jmp     __DllMainCRTStartup
```
