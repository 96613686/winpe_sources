# DllEntryPoint

- ea: `0x180005400`
- end: `0x18000543d`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800052c4`
- `0x180005400`
- `0x18000585c`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_18000585C();
  return sub_1800052C4(hinstDLL);
}

```

## disassembly

```asm
0x180005400  mov     [rsp+arg_0], rbx
0x180005405  mov     [rsp+arg_8], rsi
0x18000540a  push    rdi
0x18000540b  sub     rsp, 20h
0x18000540f  mov     rdi, r8
0x180005412  mov     ebx, edx
0x180005414  mov     rsi, rcx
0x180005417  cmp     edx, 1
0x18000541a  jnz     short loc_180005421
0x18000541c  call    sub_18000585C
0x180005421  mov     r8, rdi
0x180005424  mov     edx, ebx
0x180005426  mov     rcx, rsi; hLibModule
0x180005429  mov     rbx, [rsp+28h+arg_0]
0x18000542e  mov     rsi, [rsp+28h+arg_8]
0x180005433  add     rsp, 20h
0x180005437  pop     rdi
0x180005438  jmp     sub_1800052C4
```
