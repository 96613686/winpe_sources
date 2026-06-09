# _DllMainCRTStartup

- ea: `0x180007290`
- end: `0x1800072cd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007154`
- `0x180007290`
- `0x180007304`

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
0x180007290  mov     [rsp+arg_0], rbx
0x180007295  mov     [rsp+arg_8], rsi
0x18000729a  push    rdi
0x18000729b  sub     rsp, 20h
0x18000729f  mov     rdi, r8
0x1800072a2  mov     ebx, edx
0x1800072a4  mov     rsi, rcx
0x1800072a7  cmp     edx, 1
0x1800072aa  jnz     short loc_1800072B1
0x1800072ac  call    __security_init_cookie
0x1800072b1  mov     r8, rdi; lpvReserved
0x1800072b4  mov     edx, ebx; fdwReason
0x1800072b6  mov     rcx, rsi; hinstDLL
0x1800072b9  mov     rbx, [rsp+28h+arg_0]
0x1800072be  mov     rsi, [rsp+28h+arg_8]
0x1800072c3  add     rsp, 20h
0x1800072c7  pop     rdi
0x1800072c8  jmp     dllmain_dispatch
```
