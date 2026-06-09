# _DllMainCRTStartup

- ea: `0x180001570`
- end: `0x1800015ad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001570`
- `0x1800015b4`
- `0x180001a54`

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
0x180001570  mov     [rsp+arg_0], rbx
0x180001575  mov     [rsp+arg_8], rsi
0x18000157a  push    rdi
0x18000157b  sub     rsp, 20h
0x18000157f  mov     rdi, r8
0x180001582  mov     ebx, edx
0x180001584  mov     rsi, rcx
0x180001587  cmp     edx, 1
0x18000158a  jnz     short loc_180001591
0x18000158c  call    __security_init_cookie
0x180001591  mov     r8, rdi
0x180001594  mov     edx, ebx; fdwReason
0x180001596  mov     rcx, rsi; hinstDLL
0x180001599  mov     rbx, [rsp+28h+arg_0]
0x18000159e  mov     rsi, [rsp+28h+arg_8]
0x1800015a3  add     rsp, 20h
0x1800015a7  pop     rdi
0x1800015a8  jmp     __DllMainCRTStartup
```
