# InconsistencyDetected(_LIST_ENTRY *,_LIST_ENTRY *,_LIST_ENTRY *,tagOpenedDbgSection *,int)

- ea: `0x180009d20`
- end: `0x180009da7`
- name: `?InconsistencyDetected@@YAXPEAU_LIST_ENTRY@@00PEAUtagOpenedDbgSection@@H@Z`
- size: `135`
- prototype: `void __fastcall(struct _LIST_ENTRY *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180009df8`

## callees

- `0x180002a00`
- `0x180009990`
- `0x180009d20`

## pseudocode

```c
void __fastcall InconsistencyDetected(
        struct _LIST_ENTRY *a1,
        struct _LIST_ENTRY *a2,
        struct _LIST_ENTRY *a3,
        void **a4,
        int a5)
{
  struct _LIST_ENTRY *Flink; // rbx
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *v10; // rcx

  if ( !a5 )
    goto LABEL_6;
  Flink = a3->Flink;
  if ( a3->Flink->Blink != a3 || (Blink = a3->Blink, Blink->Flink != a3) )
    __fastfail(3u);
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  CloseDbgSection(*a4, a4[1]);
  operator delete(a4);
  if ( Flink != a1 )
  {
    a3 = Flink;
LABEL_6:
    v10 = a1->Blink;
    a1->Blink = a3->Blink;
    a3->Blink->Flink = a1;
    a3->Blink = a2->Blink;
    a2->Blink->Flink = a3;
    a2->Blink = v10;
    v10->Flink = a2;
  }
}

```

## disassembly

```asm
0x180009d20  push    rbx
0x180009d22  push    rbp
0x180009d23  push    rsi
0x180009d24  push    rdi
0x180009d25  sub     rsp, 28h
0x180009d29  cmp     [rsp+48h+arg_20], 0
0x180009d2e  mov     rdi, r9
0x180009d31  mov     rbp, rdx
0x180009d34  mov     rsi, rcx
0x180009d37  jz      short loc_180009D6E
0x180009d39  mov     rbx, [r8]
0x180009d3c  cmp     [rbx+8], r8
0x180009d40  jnz     short loc_180009DA0
0x180009d42  mov     rax, [r8+8]
0x180009d46  cmp     [rax], r8
0x180009d49  jnz     short loc_180009DA0
0x180009d4b  mov     [rax], rbx
0x180009d4e  mov     [rbx+8], rax
0x180009d52  mov     rdx, [r9+8]; void *
0x180009d56  mov     rcx, [r9]; void *
0x180009d59  call    ?CloseDbgSection@@YAXPEAX0@Z; CloseDbgSection(void *,void *)
0x180009d5e  mov     rcx, rdi; void *
0x180009d61  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009d66  cmp     rbx, rsi
0x180009d69  jz      short loc_180009D97
0x180009d6b  mov     r8, rbx
0x180009d6e  mov     rax, [r8+8]
0x180009d72  mov     rcx, [rsi+8]
0x180009d76  mov     [rsi+8], rax
0x180009d7a  mov     rax, [r8+8]
0x180009d7e  mov     [rax], rsi
0x180009d81  mov     rax, [rbp+8]
0x180009d85  mov     [r8+8], rax
0x180009d89  mov     rax, [rbp+8]
0x180009d8d  mov     [rax], r8
0x180009d90  mov     [rbp+8], rcx
0x180009d94  mov     [rcx], rbp
0x180009d97  add     rsp, 28h
0x180009d9b  pop     rdi
0x180009d9c  pop     rsi
0x180009d9d  pop     rbp
0x180009d9e  pop     rbx
0x180009d9f  retn
0x180009da0  mov     ecx, 3
0x180009da5  int     29h; Win8: RtlFailFast(ecx)
```
