# _DllMainCRTStartup

- ea: `0x1800017e0`
- end: `0x18000181d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800017e0`
- `0x180001824`
- `0x180001e54`

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
0x1800017e0  mov     [rsp+arg_0], rbx
0x1800017e5  mov     [rsp+arg_8], rsi
0x1800017ea  push    rdi
0x1800017eb  sub     rsp, 20h
0x1800017ef  mov     rdi, r8
0x1800017f2  mov     ebx, edx
0x1800017f4  mov     rsi, rcx
0x1800017f7  cmp     edx, 1
0x1800017fa  jnz     short loc_180001801
0x1800017fc  call    __security_init_cookie
0x180001801  mov     r8, rdi
0x180001804  mov     edx, ebx; fdwReason
0x180001806  mov     rcx, rsi; hinstDLL
0x180001809  mov     rbx, [rsp+28h+arg_0]
0x18000180e  mov     rsi, [rsp+28h+arg_8]
0x180001813  add     rsp, 20h
0x180001817  pop     rdi
0x180001818  jmp     __DllMainCRTStartup
```
