# std::unique_ptr<uchar [0],std::default_delete<uchar [0]>>::~unique_ptr<uchar [0],std::default_delete<uchar [0]>>(void)

- ea: `0x140007e80`
- end: `0x140007e96`
- name: `??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400081bc`
- `0x14000897a`

## callees

- `0x140001754`
- `0x140007e80`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(void **a1, unsigned __int64 a2)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    operator delete(v2, a2);
}

```

## disassembly

```asm
0x140007e80  sub     rsp, 28h
0x140007e84  mov     rcx, [rcx]; void *
0x140007e87  test    rcx, rcx
0x140007e8a  jz      short loc_140007E91
0x140007e8c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007e91  add     rsp, 28h
0x140007e95  retn
```
