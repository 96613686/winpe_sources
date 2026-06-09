# _DllMainCRTStartup

- ea: `0x18000f590`
- end: `0x18000f5cd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f590`
- `0x18000f5d4`
- `0x18000fca4`

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
0x18000f590  mov     [rsp+arg_0], rbx
0x18000f595  mov     [rsp+arg_8], rsi
0x18000f59a  push    rdi
0x18000f59b  sub     rsp, 20h
0x18000f59f  mov     rdi, r8
0x18000f5a2  mov     ebx, edx
0x18000f5a4  mov     rsi, rcx
0x18000f5a7  cmp     edx, 1
0x18000f5aa  jnz     short loc_18000F5B1
0x18000f5ac  call    __security_init_cookie
0x18000f5b1  mov     r8, rdi
0x18000f5b4  mov     edx, ebx; fdwReason
0x18000f5b6  mov     rcx, rsi; hinstDLL
0x18000f5b9  mov     rbx, [rsp+28h+arg_0]
0x18000f5be  mov     rsi, [rsp+28h+arg_8]
0x18000f5c3  add     rsp, 20h
0x18000f5c7  pop     rdi
0x18000f5c8  jmp     __DllMainCRTStartup
```
