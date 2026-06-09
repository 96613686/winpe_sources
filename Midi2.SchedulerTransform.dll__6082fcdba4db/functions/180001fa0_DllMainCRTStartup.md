# _DllMainCRTStartup

- ea: `0x180001fa0`
- end: `0x180001fdd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001e64`
- `0x180001fa0`
- `0x1800024a0`

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
0x180001fa0  mov     [rsp+arg_0], rbx
0x180001fa5  mov     [rsp+arg_8], rsi
0x180001faa  push    rdi
0x180001fab  sub     rsp, 20h
0x180001faf  mov     rdi, r8
0x180001fb2  mov     ebx, edx
0x180001fb4  mov     rsi, rcx
0x180001fb7  cmp     edx, 1
0x180001fba  jnz     short loc_180001FC1
0x180001fbc  call    __security_init_cookie
0x180001fc1  mov     r8, rdi; lpvReserved
0x180001fc4  mov     edx, ebx; fdwReason
0x180001fc6  mov     rcx, rsi; hinstDLL
0x180001fc9  mov     rbx, [rsp+28h+arg_0]
0x180001fce  mov     rsi, [rsp+28h+arg_8]
0x180001fd3  add     rsp, 20h
0x180001fd7  pop     rdi
0x180001fd8  jmp     dllmain_dispatch
```
