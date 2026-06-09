# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::~unique_ptr<ushort [0],std::default_delete<ushort [0]>>(void)

- ea: `0x18000ef74`
- end: `0x18000ef8a`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **, const struct std::nothrow_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011862`

## callees

- `0x180001b6c`
- `0x18000ef74`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(
        void **a1,
        const struct std::nothrow_t *a2)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    operator delete(v2, a2);
}

```

## disassembly

```asm
0x18000ef74  sub     rsp, 28h
0x18000ef78  mov     rcx, [rcx]; void *
0x18000ef7b  test    rcx, rcx
0x18000ef7e  jz      short loc_18000EF85
0x18000ef80  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ef85  add     rsp, 28h
0x18000ef89  retn
```
