# __ArrayUnwind(void *,unsigned __int64,int,void (*)(void *))

- ea: `0x180001a6c`
- end: `0x180001ab3`
- name: `?__ArrayUnwind@@YAXPEAX_KHP6AX0@Z@Z`
- size: `71`
- prototype: `void __fastcall(void *, unsigned __int64, int, void (*)(void *))`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001a00`
- `0x180001be4`

## callees

- `0x180001a6c`
- `0x18000a010`

## import_xrefs

- `msvcrt!?terminate@@YAXXZ` at `0x1800097e0`
- `msvcrt!?terminate@@YAXXZ` at `0x1800097e0`

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
0x180001a6c  mov     [rsp+arg_8], rbx
0x180001a71  push    rsi
0x180001a72  push    rdi
0x180001a73  push    r14
0x180001a75  sub     rsp, 40h
0x180001a79  mov     rsi, r9
0x180001a7c  mov     ebx, r8d
0x180001a7f  mov     r14, rdx
0x180001a82  mov     rdi, rcx
0x180001a85  sub     ebx, 1
0x180001a88  mov     [rsp+58h+arg_10], ebx
0x180001a8c  js      short loc_180001AA3
0x180001a8e  sub     rdi, r14
0x180001a91  mov     [rsp+58h+arg_0], rdi
0x180001a96  mov     rcx, rdi
0x180001a99  mov     rax, rsi
0x180001a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001aa1  jmp     short loc_180001A85
0x180001aa3  jmp     short $+2
0x180001aa5  mov     rbx, [rsp+58h+arg_8]
0x180001aaa  add     rsp, 40h
0x180001aae  pop     r14
0x180001ab0  pop     rdi
0x180001ab1  pop     rsi
0x180001ab2  retn
0x1800097b0  push    rbp
0x1800097b2  sub     rsp, 20h
0x1800097b6  mov     rbp, rdx
0x1800097b9  mov     [rbp+28h], rcx
0x1800097bd  mov     rax, [rbp+28h]
0x1800097c1  mov     rcx, [rax]
0x1800097c4  mov     [rbp+30h], rcx
0x1800097c8  mov     rax, [rbp+30h]
0x1800097cc  cmp     dword ptr [rax], 0E06D7363h
0x1800097d2  jz      short loc_1800097E0
0x1800097d4  mov     dword ptr [rbp+20h], 0
0x1800097db  mov     eax, [rbp+20h]
0x1800097de  jmp     short loc_1800097E7
0x1800097e0  call    cs:__imp_?terminate@@YAXXZ; terminate(void)
0x1800097e7  add     rsp, 20h
0x1800097eb  pop     rbp
0x1800097ec  retn
```
