# _DllMainCRTStartup

- ea: `0x180001c10`
- end: `0x180001c4d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001ad4`
- `0x180001c10`
- `0x180001d3c`

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
0x180001c10  mov     [rsp+arg_0], rbx
0x180001c15  mov     [rsp+arg_8], rsi
0x180001c1a  push    rdi
0x180001c1b  sub     rsp, 20h
0x180001c1f  mov     rdi, r8
0x180001c22  mov     ebx, edx
0x180001c24  mov     rsi, rcx
0x180001c27  cmp     edx, 1
0x180001c2a  jnz     short loc_180001C31
0x180001c2c  call    __security_init_cookie
0x180001c31  mov     r8, rdi; lpvReserved
0x180001c34  mov     edx, ebx; fdwReason
0x180001c36  mov     rcx, rsi; hinstDLL
0x180001c39  mov     rbx, [rsp+28h+arg_0]
0x180001c3e  mov     rsi, [rsp+28h+arg_8]
0x180001c43  add     rsp, 20h
0x180001c47  pop     rdi
0x180001c48  jmp     dllmain_dispatch
```
