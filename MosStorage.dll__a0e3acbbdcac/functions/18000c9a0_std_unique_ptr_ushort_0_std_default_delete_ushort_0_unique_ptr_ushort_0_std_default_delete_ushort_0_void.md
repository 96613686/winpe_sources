# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::~unique_ptr<ushort [0],std::default_delete<ushort [0]>>(void)

- ea: `0x18000c9a0`
- end: `0x18000c9b6`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ef4c`

## callees

- `0x18000207c`
- `0x18000c9a0`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000c9a0  sub     rsp, 28h
0x18000c9a4  mov     rcx, [rcx]; Block
0x18000c9a7  test    rcx, rcx
0x18000c9aa  jz      short loc_18000C9B1
0x18000c9ac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c9b1  add     rsp, 28h
0x18000c9b5  retn
```
