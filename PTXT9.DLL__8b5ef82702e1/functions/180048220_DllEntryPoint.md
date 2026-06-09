# DllEntryPoint

- ea: `0x180048220`
- end: `0x18004825a`
- name: `DllEntryPoint`
- size: `58`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180048220`
- `0x18004825c`
- `0x18004f5e0`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_18004F5E0();
  return sub_18004825C(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180048220  mov     [rsp+arg_0], rbx
0x180048225  mov     [rsp+arg_8], rsi
0x18004822a  push    rdi
0x18004822b  sub     rsp, 20h
0x18004822f  mov     rdi, r8
0x180048232  mov     ebx, edx
0x180048234  mov     rsi, rcx
0x180048237  cmp     edx, 1
0x18004823a  jnz     short loc_180048241
0x18004823c  call    sub_18004F5E0
0x180048241  mov     r8, rdi
0x180048244  mov     edx, ebx
0x180048246  mov     rcx, rsi
0x180048249  mov     rbx, [rsp+28h+arg_0]
0x18004824e  mov     rsi, [rsp+28h+arg_8]
0x180048253  add     rsp, 20h
0x180048257  pop     rdi
0x180048258  jmp     short sub_18004825C
```
