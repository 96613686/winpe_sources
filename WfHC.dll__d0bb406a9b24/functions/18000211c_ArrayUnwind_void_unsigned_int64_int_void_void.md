# __ArrayUnwind(void *,unsigned __int64,int,void (*)(void *))

- ea: `0x18000211c`
- end: `0x180002163`
- name: `?__ArrayUnwind@@YAXPEAX_KHP6AX0@Z@Z`
- size: `71`
- prototype: `void __fastcall(char *, __int64, int, void (__fastcall *)(char *))`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800020b0`
- `0x180002198`

## callees

- `0x18000211c`
- `0x18000e010`

## import_xrefs

- `msvcrt!?terminate@@YAXXZ` at `0x18000ca22`
- `msvcrt!?terminate@@YAXXZ` at `0x18000ca22`

## pseudocode

```c
void __fastcall __ArrayUnwind(char *a1, __int64 a2, int a3, void (__fastcall *a4)(char *))
{
  while ( --a3 >= 0 )
  {
    a1 -= a2;
    a4(a1);
  }
}

```

## disassembly

```asm
0x18000211c  mov     [rsp+arg_8], rbx
0x180002121  push    rsi
0x180002122  push    rdi
0x180002123  push    r14
0x180002125  sub     rsp, 40h
0x180002129  mov     rsi, r9
0x18000212c  mov     ebx, r8d
0x18000212f  mov     r14, rdx
0x180002132  mov     rdi, rcx
0x180002135  sub     ebx, 1
0x180002138  mov     [rsp+58h+arg_10], ebx
0x18000213c  js      short loc_180002153
0x18000213e  sub     rdi, r14
0x180002141  mov     [rsp+58h+arg_0], rdi
0x180002146  mov     rcx, rdi
0x180002149  mov     rax, rsi
0x18000214c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002151  jmp     short loc_180002135
0x180002153  jmp     short $+2
0x180002155  mov     rbx, [rsp+58h+arg_8]
0x18000215a  add     rsp, 40h
0x18000215e  pop     r14
0x180002160  pop     rdi
0x180002161  pop     rsi
0x180002162  retn
0x18000c9f2  push    rbp
0x18000c9f4  sub     rsp, 20h
0x18000c9f8  mov     rbp, rdx
0x18000c9fb  mov     [rbp+28h], rcx
0x18000c9ff  mov     rax, [rbp+28h]
0x18000ca03  mov     rcx, [rax]
0x18000ca06  mov     [rbp+30h], rcx
0x18000ca0a  mov     rax, [rbp+30h]
0x18000ca0e  cmp     dword ptr [rax], 0E06D7363h
0x18000ca14  jz      short loc_18000CA22
0x18000ca16  mov     dword ptr [rbp+20h], 0
0x18000ca1d  mov     eax, [rbp+20h]
0x18000ca20  jmp     short loc_18000CA29
0x18000ca22  call    cs:__imp_?terminate@@YAXXZ; terminate(void)
0x18000ca29  add     rsp, 20h
0x18000ca2d  pop     rbp
0x18000ca2e  retn
```
