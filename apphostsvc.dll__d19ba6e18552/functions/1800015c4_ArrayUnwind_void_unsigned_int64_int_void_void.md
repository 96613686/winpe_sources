# __ArrayUnwind(void *,unsigned __int64,int,void (*)(void *))

- ea: `0x1800015c4`
- end: `0x18000160b`
- name: `?__ArrayUnwind@@YAXPEAX_KHP6AX0@Z@Z`
- size: `71`
- prototype: `void __fastcall(void *, unsigned __int64, int, void (*)(void *))`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001558`
- `0x180001b6c`

## callees

- `0x1800015c4`
- `0x18000a010`

## import_xrefs

- `msvcrt!?terminate@@YAXXZ` at `0x180008ff0`
- `msvcrt!?terminate@@YAXXZ` at `0x180008ff0`

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
0x1800015c4  mov     [rsp+arg_8], rbx
0x1800015c9  push    rsi
0x1800015ca  push    rdi
0x1800015cb  push    r14
0x1800015cd  sub     rsp, 40h
0x1800015d1  mov     rsi, r9
0x1800015d4  mov     ebx, r8d
0x1800015d7  mov     r14, rdx
0x1800015da  mov     rdi, rcx
0x1800015dd  sub     ebx, 1
0x1800015e0  mov     [rsp+58h+arg_10], ebx
0x1800015e4  js      short loc_1800015FB
0x1800015e6  sub     rdi, r14
0x1800015e9  mov     [rsp+58h+arg_0], rdi
0x1800015ee  mov     rcx, rdi
0x1800015f1  mov     rax, rsi
0x1800015f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015f9  jmp     short loc_1800015DD
0x1800015fb  jmp     short $+2
0x1800015fd  mov     rbx, [rsp+58h+arg_8]
0x180001602  add     rsp, 40h
0x180001606  pop     r14
0x180001608  pop     rdi
0x180001609  pop     rsi
0x18000160a  retn
0x180008fc0  push    rbp
0x180008fc2  sub     rsp, 20h
0x180008fc6  mov     rbp, rdx
0x180008fc9  mov     [rbp+28h], rcx
0x180008fcd  mov     rax, [rbp+28h]
0x180008fd1  mov     rcx, [rax]
0x180008fd4  mov     [rbp+30h], rcx
0x180008fd8  mov     rax, [rbp+30h]
0x180008fdc  cmp     dword ptr [rax], 0E06D7363h
0x180008fe2  jz      short loc_180008FF0
0x180008fe4  mov     dword ptr [rbp+20h], 0
0x180008feb  mov     eax, [rbp+20h]
0x180008fee  jmp     short loc_180008FF7
0x180008ff0  call    cs:__imp_?terminate@@YAXXZ; terminate(void)
0x180008ff7  add     rsp, 20h
0x180008ffb  pop     rbp
0x180008ffc  retn
```
