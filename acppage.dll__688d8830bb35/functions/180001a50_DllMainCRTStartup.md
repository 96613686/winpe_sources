# _DllMainCRTStartup

- ea: `0x180001a50`
- end: `0x180001a8d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001a50`
- `0x180001a94`
- `0x1800020a4`

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
0x180001a50  mov     [rsp+arg_0], rbx
0x180001a55  mov     [rsp+arg_8], rsi
0x180001a5a  push    rdi
0x180001a5b  sub     rsp, 20h
0x180001a5f  mov     rdi, r8
0x180001a62  mov     ebx, edx
0x180001a64  mov     rsi, rcx
0x180001a67  cmp     edx, 1
0x180001a6a  jnz     short loc_180001A71
0x180001a6c  call    __security_init_cookie
0x180001a71  mov     r8, rdi
0x180001a74  mov     edx, ebx; fdwReason
0x180001a76  mov     rcx, rsi; hinstDLL
0x180001a79  mov     rbx, [rsp+28h+arg_0]
0x180001a7e  mov     rsi, [rsp+28h+arg_8]
0x180001a83  add     rsp, 20h
0x180001a87  pop     rdi
0x180001a88  jmp     __DllMainCRTStartup
```
