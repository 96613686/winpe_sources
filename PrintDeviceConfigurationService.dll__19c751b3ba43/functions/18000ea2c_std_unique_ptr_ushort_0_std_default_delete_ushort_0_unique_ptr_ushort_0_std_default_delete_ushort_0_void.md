# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::~unique_ptr<ushort [0],std::default_delete<ushort [0]>>(void)

- ea: `0x18000ea2c`
- end: `0x18000ea42`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000f32c`
- `0x180016d5a`

## callees

- `0x180002490`
- `0x18000ea2c`

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
0x18000ea2c  sub     rsp, 28h
0x18000ea30  mov     rcx, [rcx]; void *
0x18000ea33  test    rcx, rcx
0x18000ea36  jz      short loc_18000EA3D
0x18000ea38  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ea3d  add     rsp, 28h
0x18000ea41  retn
```
