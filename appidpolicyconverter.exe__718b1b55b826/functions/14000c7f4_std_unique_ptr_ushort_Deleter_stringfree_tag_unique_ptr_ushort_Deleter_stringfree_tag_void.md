# std::unique_ptr<ushort,Deleter<stringfree_tag>>::~unique_ptr<ushort,Deleter<stringfree_tag>>(void)

- ea: `0x14000c7f4`
- end: `0x14000c80a`
- name: `??1?$unique_ptr@GU?$Deleter@Ustringfree_tag@@@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140014838`
- `0x14001484a`
- `0x14001485c`

## callees

- `0x14000157c`
- `0x14000c7f4`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short,Deleter<stringfree_tag>>::~unique_ptr<unsigned short,Deleter<stringfree_tag>>(
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
0x14000c7f4  sub     rsp, 28h
0x14000c7f8  mov     rcx, [rcx]; Block
0x14000c7fb  test    rcx, rcx
0x14000c7fe  jz      short loc_14000C805
0x14000c800  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c805  add     rsp, 28h
0x14000c809  retn
```
