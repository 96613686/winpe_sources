# _DllMainCRTStartup

- ea: `0x180001400`
- end: `0x18000143d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001400`
- `0x180001444`
- `0x180001764`

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
0x180001400  mov     [rsp+arg_0], rbx
0x180001405  mov     [rsp+arg_8], rsi
0x18000140a  push    rdi
0x18000140b  sub     rsp, 20h
0x18000140f  mov     rdi, r8
0x180001412  mov     ebx, edx
0x180001414  mov     rsi, rcx
0x180001417  cmp     edx, 1
0x18000141a  jnz     short loc_180001421
0x18000141c  call    __security_init_cookie
0x180001421  mov     r8, rdi
0x180001424  mov     edx, ebx; fdwReason
0x180001426  mov     rcx, rsi; hinstDLL
0x180001429  mov     rbx, [rsp+28h+arg_0]
0x18000142e  mov     rsi, [rsp+28h+arg_8]
0x180001433  add     rsp, 20h
0x180001437  pop     rdi
0x180001438  jmp     __DllMainCRTStartup
```
