# _DllMainCRTStartup

- ea: `0x180002270`
- end: `0x1800022ad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002270`
- `0x1800022b4`
- `0x1800025b4`

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
0x180002270  mov     [rsp+arg_0], rbx
0x180002275  mov     [rsp+arg_8], rsi
0x18000227a  push    rdi
0x18000227b  sub     rsp, 20h
0x18000227f  mov     rdi, r8
0x180002282  mov     ebx, edx
0x180002284  mov     rsi, rcx
0x180002287  cmp     edx, 1
0x18000228a  jnz     short loc_180002291
0x18000228c  call    __security_init_cookie
0x180002291  mov     r8, rdi
0x180002294  mov     edx, ebx; fdwReason
0x180002296  mov     rcx, rsi; hinstDLL
0x180002299  mov     rbx, [rsp+28h+arg_0]
0x18000229e  mov     rsi, [rsp+28h+arg_8]
0x1800022a3  add     rsp, 20h
0x1800022a7  pop     rdi
0x1800022a8  jmp     __DllMainCRTStartup
```
