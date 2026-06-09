# std::unique_ptr<uchar [0],std::default_delete<uchar [0]>>::~unique_ptr<uchar [0],std::default_delete<uchar [0]>>(void)

- ea: `0x14000350c`
- end: `0x140003522`
- name: `??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140011042`
- `0x140011054`
- `0x140011066`
- `0x140011078`
- `0x14001108a`

## callees

- `0x1400016c4`
- `0x14000350c`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x14000350c  sub     rsp, 28h
0x140003510  mov     rcx, [rcx]; Block
0x140003513  test    rcx, rcx
0x140003516  jz      short loc_14000351D
0x140003518  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000351d  add     rsp, 28h
0x140003521  retn
```
