# std::unique_ptr<ushort const *,std::default_delete<ushort const *>>::~unique_ptr<ushort const *,std::default_delete<ushort const *>>(void)

- ea: `0x180007040`
- end: `0x18000705b`
- name: `??1?$unique_ptr@PEBGU?$default_delete@PEBG@std@@@std@@QEAA@XZ`
- size: `27`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000a5e8`

## callees

- `0x180001a70`
- `0x180007040`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short const *>::~unique_ptr<unsigned short const *>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1, 8u);
}

```

## disassembly

```asm
0x180007040  sub     rsp, 28h
0x180007044  mov     rcx, [rcx]; void *
0x180007047  test    rcx, rcx
0x18000704a  jz      short loc_180007056
0x18000704c  mov     edx, 8; unsigned __int64
0x180007051  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007056  add     rsp, 28h
0x18000705a  retn
```
