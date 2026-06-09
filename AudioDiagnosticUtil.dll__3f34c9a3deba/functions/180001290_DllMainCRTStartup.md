# _DllMainCRTStartup

- ea: `0x180001290`
- end: `0x1800012cd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001290`
- `0x1800012d4`
- `0x1800015e4`

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
0x180001290  mov     [rsp+arg_0], rbx
0x180001295  mov     [rsp+arg_8], rsi
0x18000129a  push    rdi
0x18000129b  sub     rsp, 20h
0x18000129f  mov     rdi, r8
0x1800012a2  mov     ebx, edx
0x1800012a4  mov     rsi, rcx
0x1800012a7  cmp     edx, 1
0x1800012aa  jnz     short loc_1800012B1
0x1800012ac  call    __security_init_cookie
0x1800012b1  mov     r8, rdi
0x1800012b4  mov     edx, ebx; fdwReason
0x1800012b6  mov     rcx, rsi; hinstDLL
0x1800012b9  mov     rbx, [rsp+28h+arg_0]
0x1800012be  mov     rsi, [rsp+28h+arg_8]
0x1800012c3  add     rsp, 20h
0x1800012c7  pop     rdi
0x1800012c8  jmp     __DllMainCRTStartup
```
