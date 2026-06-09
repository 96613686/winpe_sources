# std::unique_ptr<uint [0],std::default_delete<uint [0]>>::~unique_ptr<uint [0],std::default_delete<uint [0]>>(void)

- ea: `0x18001217c`
- end: `0x180012192`
- name: `??1?$unique_ptr@$$BY0A@IU?$default_delete@$$BY0A@I@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001d224`
- `0x180020d80`
- `0x180023efd`
- `0x180023f0f`
- `0x18002402f`

## callees

- `0x180003434`
- `0x18001217c`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned int [0]>::~unique_ptr<unsigned int [0]>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18001217c  sub     rsp, 28h
0x180012180  mov     rcx, [rcx]; Block
0x180012183  test    rcx, rcx
0x180012186  jz      short loc_18001218D
0x180012188  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001218d  add     rsp, 28h
0x180012191  retn
```
