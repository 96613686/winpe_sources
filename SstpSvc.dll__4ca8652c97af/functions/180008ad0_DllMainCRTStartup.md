# _DllMainCRTStartup

- ea: `0x180008ad0`
- end: `0x180008b0d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008ad0`
- `0x180008b14`
- `0x1800090d4`

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
0x180008ad0  mov     [rsp+arg_0], rbx
0x180008ad5  mov     [rsp+arg_8], rsi
0x180008ada  push    rdi
0x180008adb  sub     rsp, 20h
0x180008adf  mov     rdi, r8
0x180008ae2  mov     ebx, edx
0x180008ae4  mov     rsi, rcx
0x180008ae7  cmp     edx, 1
0x180008aea  jnz     short loc_180008AF1
0x180008aec  call    __security_init_cookie
0x180008af1  mov     r8, rdi
0x180008af4  mov     edx, ebx; fdwReason
0x180008af6  mov     rcx, rsi; hinstDLL
0x180008af9  mov     rbx, [rsp+28h+arg_0]
0x180008afe  mov     rsi, [rsp+28h+arg_8]
0x180008b03  add     rsp, 20h
0x180008b07  pop     rdi
0x180008b08  jmp     __DllMainCRTStartup
```
