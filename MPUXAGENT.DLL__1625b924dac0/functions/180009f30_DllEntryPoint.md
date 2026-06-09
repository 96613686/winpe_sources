# DllEntryPoint

- ea: `0x180009f30`
- end: `0x180009f6d`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180009dfc`
- `0x180009f30`
- `0x18000a750`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_18000A750();
  return sub_180009DFC(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180009f30  mov     [rsp+arg_0], rbx
0x180009f35  mov     [rsp+arg_8], rsi
0x180009f3a  push    rdi
0x180009f3b  sub     rsp, 20h
0x180009f3f  mov     rdi, r8
0x180009f42  mov     ebx, edx
0x180009f44  mov     rsi, rcx
0x180009f47  cmp     edx, 1
0x180009f4a  jnz     short loc_180009F51
0x180009f4c  call    sub_18000A750
0x180009f51  mov     r8, rdi; lpvReserved
0x180009f54  mov     edx, ebx; fdwReason
0x180009f56  mov     rcx, rsi; hinstDLL
0x180009f59  mov     rbx, [rsp+28h+arg_0]
0x180009f5e  mov     rsi, [rsp+28h+arg_8]
0x180009f63  add     rsp, 20h
0x180009f67  pop     rdi
0x180009f68  jmp     sub_180009DFC
```
