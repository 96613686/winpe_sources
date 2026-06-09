# _DllMainCRTStartup

- ea: `0x180008560`
- end: `0x18000859d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008560`
- `0x1800085a4`
- `0x180008a84`

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
0x180008560  mov     [rsp+arg_0], rbx
0x180008565  mov     [rsp+arg_8], rsi
0x18000856a  push    rdi
0x18000856b  sub     rsp, 20h
0x18000856f  mov     rdi, r8
0x180008572  mov     ebx, edx
0x180008574  mov     rsi, rcx
0x180008577  cmp     edx, 1
0x18000857a  jnz     short loc_180008581
0x18000857c  call    __security_init_cookie
0x180008581  mov     r8, rdi
0x180008584  mov     edx, ebx; fdwReason
0x180008586  mov     rcx, rsi; hinstDLL
0x180008589  mov     rbx, [rsp+28h+arg_0]
0x18000858e  mov     rsi, [rsp+28h+arg_8]
0x180008593  add     rsp, 20h
0x180008597  pop     rdi
0x180008598  jmp     __DllMainCRTStartup
```
