# DllEntryPoint

- ea: `0x180011a90`
- end: `0x180011acd`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180011960`
- `0x180011a90`
- `0x180011ad0`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_180011AD0();
  return sub_180011960(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180011a90  mov     [rsp+arg_0], rbx
0x180011a95  mov     [rsp+arg_8], rsi
0x180011a9a  push    rdi
0x180011a9b  sub     rsp, 20h
0x180011a9f  mov     rdi, r8
0x180011aa2  mov     ebx, edx
0x180011aa4  mov     rsi, rcx
0x180011aa7  cmp     edx, 1
0x180011aaa  jnz     short loc_180011AB1
0x180011aac  call    sub_180011AD0
0x180011ab1  mov     r8, rdi
0x180011ab4  mov     edx, ebx
0x180011ab6  mov     rcx, rsi
0x180011ab9  mov     rbx, [rsp+28h+arg_0]
0x180011abe  mov     rsi, [rsp+28h+arg_8]
0x180011ac3  add     rsp, 20h
0x180011ac7  pop     rdi
0x180011ac8  jmp     sub_180011960
```
