# utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>>::~unique_ptr<uchar [0],utl::default_delete<uchar [0]>>(void)

- ea: `0x180002278`
- end: `0x18000228e`
- name: `??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002da4`
- `0x180002db6`
- `0x180002dc8`

## callees

- `0x180001424`
- `0x180002278`

## pseudocode

```c
void __fastcall utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::~unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x180002278  sub     rsp, 28h
0x18000227c  mov     rcx, [rcx]; void *
0x18000227f  test    rcx, rcx
0x180002282  jz      short loc_180002289
0x180002284  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002289  add     rsp, 28h
0x18000228d  retn
```
