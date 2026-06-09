# _DllMainCRTStartup

- ea: `0x180001ba0`
- end: `0x180001bdd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001ba0`
- `0x180001be4`
- `0x180002074`

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
0x180001ba0  mov     [rsp+arg_0], rbx
0x180001ba5  mov     [rsp+arg_8], rsi
0x180001baa  push    rdi
0x180001bab  sub     rsp, 20h
0x180001baf  mov     rdi, r8
0x180001bb2  mov     ebx, edx
0x180001bb4  mov     rsi, rcx
0x180001bb7  cmp     edx, 1
0x180001bba  jnz     short loc_180001BC1
0x180001bbc  call    __security_init_cookie
0x180001bc1  mov     r8, rdi
0x180001bc4  mov     edx, ebx; fdwReason
0x180001bc6  mov     rcx, rsi; hinstDLL
0x180001bc9  mov     rbx, [rsp+28h+arg_0]
0x180001bce  mov     rsi, [rsp+28h+arg_8]
0x180001bd3  add     rsp, 20h
0x180001bd7  pop     rdi
0x180001bd8  jmp     __DllMainCRTStartup
```
