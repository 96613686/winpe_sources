# _DllMainCRTStartup

- ea: `0x180002390`
- end: `0x1800023cd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002390`
- `0x1800023d4`
- `0x1800028b4`

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
0x180002390  mov     [rsp+arg_0], rbx
0x180002395  mov     [rsp+arg_8], rsi
0x18000239a  push    rdi
0x18000239b  sub     rsp, 20h
0x18000239f  mov     rdi, r8
0x1800023a2  mov     ebx, edx
0x1800023a4  mov     rsi, rcx
0x1800023a7  cmp     edx, 1
0x1800023aa  jnz     short loc_1800023B1
0x1800023ac  call    __security_init_cookie
0x1800023b1  mov     r8, rdi
0x1800023b4  mov     edx, ebx; fdwReason
0x1800023b6  mov     rcx, rsi; hinstDLL
0x1800023b9  mov     rbx, [rsp+28h+arg_0]
0x1800023be  mov     rsi, [rsp+28h+arg_8]
0x1800023c3  add     rsp, 20h
0x1800023c7  pop     rdi
0x1800023c8  jmp     __DllMainCRTStartup
```
