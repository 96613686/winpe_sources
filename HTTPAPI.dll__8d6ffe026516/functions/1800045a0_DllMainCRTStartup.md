# _DllMainCRTStartup

- ea: `0x1800045a0`
- end: `0x1800045dd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800045a0`
- `0x1800045e4`
- `0x180004718`

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
0x1800045a0  mov     [rsp+arg_0], rbx
0x1800045a5  mov     [rsp+arg_8], rsi
0x1800045aa  push    rdi
0x1800045ab  sub     rsp, 20h
0x1800045af  mov     rdi, r8
0x1800045b2  mov     ebx, edx
0x1800045b4  mov     rsi, rcx
0x1800045b7  cmp     edx, 1
0x1800045ba  jnz     short loc_1800045C1
0x1800045bc  call    __security_init_cookie
0x1800045c1  mov     r8, rdi
0x1800045c4  mov     edx, ebx; fdwReason
0x1800045c6  mov     rcx, rsi; hinstDLL
0x1800045c9  mov     rbx, [rsp+28h+arg_0]
0x1800045ce  mov     rsi, [rsp+28h+arg_8]
0x1800045d3  add     rsp, 20h
0x1800045d7  pop     rdi
0x1800045d8  jmp     __DllMainCRTStartup
```
