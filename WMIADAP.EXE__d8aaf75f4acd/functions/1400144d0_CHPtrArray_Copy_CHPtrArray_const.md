# CHPtrArray::Copy(CHPtrArray const &)

- ea: `0x1400144d0`
- end: `0x140014509`
- name: `?Copy@CHPtrArray@@QEAAXAEBV1@@Z`
- size: `57`
- prototype: `void __fastcall(CHPtrArray *__hidden this, const struct CHPtrArray *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1400027e1`
- `0x140014830`

## pseudocode

```c
void __fastcall CHPtrArray::Copy(CHPtrArray *this, const struct CHPtrArray *a2)
{
  CHPtrArray::SetSize(this, *((_DWORD *)a2 + 2), -1);
  memcpy_0(*(void **)this, *(const void **)a2, 8LL * *((int *)a2 + 2));
}

```

## disassembly

```asm
0x1400144d0  mov     [rsp+arg_0], rbx
0x1400144d5  push    rdi
0x1400144d6  sub     rsp, 20h
0x1400144da  mov     rbx, rdx
0x1400144dd  or      r8d, 0FFFFFFFFh; int
0x1400144e1  mov     edx, [rdx+8]; int
0x1400144e4  mov     rdi, rcx
0x1400144e7  call    ?SetSize@CHPtrArray@@QEAAXHH@Z; CHPtrArray::SetSize(int,int)
0x1400144ec  movsxd  r8, dword ptr [rbx+8]
0x1400144f0  mov     rdx, [rbx]; Src
0x1400144f3  mov     rcx, [rdi]; void *
0x1400144f6  shl     r8, 3; Size
0x1400144fa  mov     rbx, [rsp+28h+arg_0]
0x1400144ff  add     rsp, 20h
0x140014503  pop     rdi
0x140014504  jmp     memcpy_0
```
