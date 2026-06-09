# _DllMainCRTStartup

- ea: `0x180001450`
- end: `0x18000148d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001450`
- `0x180001494`
- `0x180001c04`

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
0x180001450  mov     [rsp+arg_0], rbx
0x180001455  mov     [rsp+arg_8], rsi
0x18000145a  push    rdi
0x18000145b  sub     rsp, 20h
0x18000145f  mov     rdi, r8
0x180001462  mov     ebx, edx
0x180001464  mov     rsi, rcx
0x180001467  cmp     edx, 1
0x18000146a  jnz     short loc_180001471
0x18000146c  call    __security_init_cookie
0x180001471  mov     r8, rdi
0x180001474  mov     edx, ebx; fdwReason
0x180001476  mov     rcx, rsi; hinstDLL
0x180001479  mov     rbx, [rsp+28h+arg_0]
0x18000147e  mov     rsi, [rsp+28h+arg_8]
0x180001483  add     rsp, 20h
0x180001487  pop     rdi
0x180001488  jmp     __DllMainCRTStartup
```
