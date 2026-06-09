# _DllMainCRTStartup

- ea: `0x180002250`
- end: `0x18000228d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002250`
- `0x180002294`
- `0x1800028d4`

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
0x180002250  mov     [rsp+arg_0], rbx
0x180002255  mov     [rsp+arg_8], rsi
0x18000225a  push    rdi
0x18000225b  sub     rsp, 20h
0x18000225f  mov     rdi, r8
0x180002262  mov     ebx, edx
0x180002264  mov     rsi, rcx
0x180002267  cmp     edx, 1
0x18000226a  jnz     short loc_180002271
0x18000226c  call    __security_init_cookie
0x180002271  mov     r8, rdi
0x180002274  mov     edx, ebx; fdwReason
0x180002276  mov     rcx, rsi; hinstDLL
0x180002279  mov     rbx, [rsp+28h+arg_0]
0x18000227e  mov     rsi, [rsp+28h+arg_8]
0x180002283  add     rsp, 20h
0x180002287  pop     rdi
0x180002288  jmp     __DllMainCRTStartup
```
