# _DllMainCRTStartup

- ea: `0x180001500`
- end: `0x18000153d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800013c4`
- `0x180001500`
- `0x18000196c`

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
0x180001500  mov     [rsp+arg_0], rbx
0x180001505  mov     [rsp+arg_8], rsi
0x18000150a  push    rdi
0x18000150b  sub     rsp, 20h
0x18000150f  mov     rdi, r8
0x180001512  mov     ebx, edx
0x180001514  mov     rsi, rcx
0x180001517  cmp     edx, 1
0x18000151a  jnz     short loc_180001521
0x18000151c  call    __security_init_cookie
0x180001521  mov     r8, rdi; lpvReserved
0x180001524  mov     edx, ebx; fdwReason
0x180001526  mov     rcx, rsi; hinstDLL
0x180001529  mov     rbx, [rsp+28h+arg_0]
0x18000152e  mov     rsi, [rsp+28h+arg_8]
0x180001533  add     rsp, 20h
0x180001537  pop     rdi
0x180001538  jmp     dllmain_dispatch
```
