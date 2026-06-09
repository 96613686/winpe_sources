# std::unique_ptr<char [0],std::default_delete<char [0]>>::~unique_ptr<char [0],std::default_delete<char [0]>>(void)

- ea: `0x18000df1c`
- end: `0x18000df32`
- name: `??1?$unique_ptr@$$BY0A@DU?$default_delete@$$BY0A@D@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000e6f8`
- `0x180011533`

## callees

- `0x180002f84`
- `0x18000df1c`

## pseudocode

```c
void __fastcall std::unique_ptr<char [0]>::~unique_ptr<char [0]>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000df1c  sub     rsp, 28h
0x18000df20  mov     rcx, [rcx]; Block
0x18000df23  test    rcx, rcx
0x18000df26  jz      short loc_18000DF2D
0x18000df28  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000df2d  add     rsp, 28h
0x18000df31  retn
```
