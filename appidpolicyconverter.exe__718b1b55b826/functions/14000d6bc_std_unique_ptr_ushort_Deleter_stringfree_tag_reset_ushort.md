# std::unique_ptr<ushort,Deleter<stringfree_tag>>::reset(ushort *)

- ea: `0x14000d6bc`
- end: `0x14000d6ec`
- name: `?reset@?$unique_ptr@GU?$Deleter@Ustringfree_tag@@@@@std@@QEAAXPEAG@Z`
- size: `48`
- prototype: `void __fastcall(void **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000c938`

## callees

- `0x14000157c`
- `0x14000d6bc`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short,Deleter<stringfree_tag>>::reset(void **a1, void *a2)
{
  void *v4; // rcx

  v4 = *a1;
  if ( a2 != v4 )
  {
    if ( v4 )
      operator delete(v4);
    *a1 = a2;
  }
}

```

## disassembly

```asm
0x14000d6bc  mov     [rsp+arg_0], rbx
0x14000d6c1  push    rdi
0x14000d6c2  sub     rsp, 20h
0x14000d6c6  mov     rdi, rcx
0x14000d6c9  mov     rbx, rdx
0x14000d6cc  mov     rcx, [rcx]; Block
0x14000d6cf  cmp     rdx, rcx
0x14000d6d2  jz      short loc_14000D6E1
0x14000d6d4  test    rcx, rcx
0x14000d6d7  jz      short loc_14000D6DE
0x14000d6d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000d6de  mov     [rdi], rbx
0x14000d6e1  mov     rbx, [rsp+28h+arg_0]
0x14000d6e6  add     rsp, 20h
0x14000d6ea  pop     rdi
0x14000d6eb  retn
```
