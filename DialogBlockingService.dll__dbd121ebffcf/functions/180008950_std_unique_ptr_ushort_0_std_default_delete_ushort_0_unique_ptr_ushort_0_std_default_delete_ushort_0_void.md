# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::~unique_ptr<ushort [0],std::default_delete<ushort [0]>>(void)

- ea: `0x180008950`
- end: `0x180008966`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000cd75`

## callees

- `0x180001644`
- `0x180008950`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(void **a1, unsigned __int64 a2)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    operator delete(v2, a2);
}

```

## disassembly

```asm
0x180008950  sub     rsp, 28h
0x180008954  mov     rcx, [rcx]; void *
0x180008957  test    rcx, rcx
0x18000895a  jz      short loc_180008961
0x18000895c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008961  add     rsp, 28h
0x180008965  retn
```
