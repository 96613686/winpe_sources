# _DllMainCRTStartup

- ea: `0x180002550`
- end: `0x18000258d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002550`
- `0x180002594`
- `0x180002a74`

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
0x180002550  mov     [rsp+arg_0], rbx
0x180002555  mov     [rsp+arg_8], rsi
0x18000255a  push    rdi
0x18000255b  sub     rsp, 20h
0x18000255f  mov     rdi, r8
0x180002562  mov     ebx, edx
0x180002564  mov     rsi, rcx
0x180002567  cmp     edx, 1
0x18000256a  jnz     short loc_180002571
0x18000256c  call    __security_init_cookie
0x180002571  mov     r8, rdi
0x180002574  mov     edx, ebx; fdwReason
0x180002576  mov     rcx, rsi; hinstDLL
0x180002579  mov     rbx, [rsp+28h+arg_0]
0x18000257e  mov     rsi, [rsp+28h+arg_8]
0x180002583  add     rsp, 20h
0x180002587  pop     rdi
0x180002588  jmp     __DllMainCRTStartup
```
