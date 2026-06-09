# _DllMainCRTStartup

- ea: `0x1800028c0`
- end: `0x1800028fd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002784`
- `0x1800028c0`
- `0x180002cec`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x1800028c0  mov     [rsp+arg_0], rbx
0x1800028c5  mov     [rsp+arg_8], rsi
0x1800028ca  push    rdi
0x1800028cb  sub     rsp, 20h
0x1800028cf  mov     rdi, r8
0x1800028d2  mov     ebx, edx
0x1800028d4  mov     rsi, rcx
0x1800028d7  cmp     edx, 1
0x1800028da  jnz     short loc_1800028E1
0x1800028dc  call    __security_init_cookie
0x1800028e1  mov     r8, rdi; lpvReserved
0x1800028e4  mov     edx, ebx; fdwReason
0x1800028e6  mov     rcx, rsi; hinstDLL
0x1800028e9  mov     rbx, [rsp+28h+arg_0]
0x1800028ee  mov     rsi, [rsp+28h+arg_8]
0x1800028f3  add     rsp, 20h
0x1800028f7  pop     rdi
0x1800028f8  jmp     dllmain_dispatch
```
