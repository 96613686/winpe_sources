# _DllMainCRTStartup

- ea: `0x180001fe0`
- end: `0x18000201d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001ea4`
- `0x180001fe0`
- `0x180002a5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180001fe0  mov     [rsp+arg_0], rbx
0x180001fe5  mov     [rsp+arg_8], rsi
0x180001fea  push    rdi
0x180001feb  sub     rsp, 20h
0x180001fef  mov     rdi, r8
0x180001ff2  mov     ebx, edx
0x180001ff4  mov     rsi, rcx
0x180001ff7  cmp     edx, 1
0x180001ffa  jnz     short loc_180002001
0x180001ffc  call    __security_init_cookie
0x180002001  mov     r8, rdi; lpvReserved
0x180002004  mov     edx, ebx; fdwReason
0x180002006  mov     rcx, rsi; hinstDLL
0x180002009  mov     rbx, [rsp+28h+arg_0]
0x18000200e  mov     rsi, [rsp+28h+arg_8]
0x180002013  add     rsp, 20h
0x180002017  pop     rdi
0x180002018  jmp     dllmain_dispatch
```
