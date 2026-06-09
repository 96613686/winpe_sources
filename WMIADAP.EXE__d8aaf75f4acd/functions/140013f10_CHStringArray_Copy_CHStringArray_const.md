# CHStringArray::Copy(CHStringArray const &)

- ea: `0x140013f10`
- end: `0x140013f45`
- name: `?Copy@CHStringArray@@QEAAXAEBV1@@Z`
- size: `53`
- prototype: `void __fastcall(CHStringArray *__hidden this, const struct CHStringArray *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x140013f4c`
- `0x140014280`

## pseudocode

```c
void __fastcall CHStringArray::Copy(CHStringArray *this, const struct CHStringArray *a2)
{
  CHStringArray::SetSize(this, *((_DWORD *)a2 + 2), -1);
  CopyElements(*(CHString **)this);
}

```

## disassembly

```asm
0x140013f10  mov     [rsp+arg_0], rbx
0x140013f15  push    rdi
0x140013f16  sub     rsp, 20h
0x140013f1a  mov     rbx, rdx
0x140013f1d  or      r8d, 0FFFFFFFFh; int
0x140013f21  mov     edx, [rdx+8]; int
0x140013f24  mov     rdi, rcx
0x140013f27  call    ?SetSize@CHStringArray@@QEAAXHH@Z; CHStringArray::SetSize(int,int)
0x140013f2c  mov     r8d, [rbx+8]
0x140013f30  mov     rdx, [rbx]
0x140013f33  mov     rcx, [rdi]; this
0x140013f36  mov     rbx, [rsp+28h+arg_0]
0x140013f3b  add     rsp, 20h
0x140013f3f  pop     rdi
0x140013f40  jmp     CopyElements
```
