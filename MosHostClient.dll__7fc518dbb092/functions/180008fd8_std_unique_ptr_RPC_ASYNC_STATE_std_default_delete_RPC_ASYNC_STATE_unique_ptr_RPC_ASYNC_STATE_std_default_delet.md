# std::unique_ptr<_RPC_ASYNC_STATE,std::default_delete<_RPC_ASYNC_STATE>>::~unique_ptr<_RPC_ASYNC_STATE,std::default_delete<_RPC_ASYNC_STATE>>(void)

- ea: `0x180008fd8`
- end: `0x180008fee`
- name: `??1?$unique_ptr@U_RPC_ASYNC_STATE@@U?$default_delete@U_RPC_ASYNC_STATE@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011285`
- `0x1800113a7`
- `0x1800114d5`
- `0x18001155f`
- `0x180011583`
- `0x1800115ea`

## callees

- `0x180002534`
- `0x180008fd8`

## pseudocode

```c
void __fastcall std::unique_ptr<_RPC_ASYNC_STATE>::~unique_ptr<_RPC_ASYNC_STATE>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x180008fd8  sub     rsp, 28h
0x180008fdc  mov     rcx, [rcx]; Block
0x180008fdf  test    rcx, rcx
0x180008fe2  jz      short loc_180008FE9
0x180008fe4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008fe9  add     rsp, 28h
0x180008fed  retn
```
