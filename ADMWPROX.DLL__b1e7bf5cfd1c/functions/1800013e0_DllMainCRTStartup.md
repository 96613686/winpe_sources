# _DllMainCRTStartup

- ea: `0x1800013e0`
- end: `0x18000141d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800013e0`
- `0x180001424`
- `0x180001754`

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
0x1800013e0  mov     [rsp+arg_0], rbx
0x1800013e5  mov     [rsp+arg_8], rsi
0x1800013ea  push    rdi
0x1800013eb  sub     rsp, 20h
0x1800013ef  mov     rdi, r8
0x1800013f2  mov     ebx, edx
0x1800013f4  mov     rsi, rcx
0x1800013f7  cmp     edx, 1
0x1800013fa  jnz     short loc_180001401
0x1800013fc  call    __security_init_cookie
0x180001401  mov     r8, rdi
0x180001404  mov     edx, ebx; fdwReason
0x180001406  mov     rcx, rsi; hinstDLL
0x180001409  mov     rbx, [rsp+28h+arg_0]
0x18000140e  mov     rsi, [rsp+28h+arg_8]
0x180001413  add     rsp, 20h
0x180001417  pop     rdi
0x180001418  jmp     __DllMainCRTStartup
```
