# _DllMainCRTStartup

- ea: `0x180026b80`
- end: `0x180026bbd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180026b80`
- `0x180026bc0`
- `0x1800270b0`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return sub_180026BC0(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180026b80  mov     [rsp+arg_0], rbx
0x180026b85  mov     [rsp+arg_8], rsi
0x180026b8a  push    rdi
0x180026b8b  sub     rsp, 20h
0x180026b8f  mov     rdi, r8
0x180026b92  mov     ebx, edx
0x180026b94  mov     rsi, rcx
0x180026b97  cmp     edx, 1
0x180026b9a  jnz     short loc_180026BA1
0x180026b9c  call    __security_init_cookie
0x180026ba1  mov     r8, rdi
0x180026ba4  mov     edx, ebx; fdwReason
0x180026ba6  mov     rcx, rsi; hinstDLL
0x180026ba9  mov     rbx, [rsp+28h+arg_0]
0x180026bae  mov     rsi, [rsp+28h+arg_8]
0x180026bb3  add     rsp, 20h
0x180026bb7  pop     rdi
0x180026bb8  jmp     sub_180026BC0
```
