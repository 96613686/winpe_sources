# DllEntryPoint

- ea: `0x180001500`
- end: `0x18000153d`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800013c4`
- `0x180001500`
- `0x180001574`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_180001574();
  return sub_1800013C4(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180001500  mov     [rsp+arg_0], rbx
0x180001505  mov     [rsp+arg_8], rsi
0x18000150a  push    rdi
0x18000150b  sub     rsp, 20h
0x18000150f  mov     rdi, r8
0x180001512  mov     ebx, edx
0x180001514  mov     rsi, rcx
0x180001517  cmp     edx, 1
0x18000151a  jnz     short loc_180001521
0x18000151c  call    sub_180001574
0x180001521  mov     r8, rdi
0x180001524  mov     edx, ebx
0x180001526  mov     rcx, rsi
0x180001529  mov     rbx, [rsp+28h+arg_0]
0x18000152e  mov     rsi, [rsp+28h+arg_8]
0x180001533  add     rsp, 20h
0x180001537  pop     rdi
0x180001538  jmp     sub_1800013C4
```
