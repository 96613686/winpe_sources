# std::vector<uchar,std::allocator<uchar>>::_Tidy(void)

- ea: `0x18000ec70`
- end: `0x18000eca3`
- name: `?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ`
- size: `51`
- prototype: `void __fastcall(__int64)`
- caller_count: `16`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006af8`
- `0x18000d790`
- `0x18000d7f0`
- `0x18000e90c`
- `0x18000ea94`
- `0x18000edd0`
- `0x18000eec0`
- `0x18000efe8`
- `0x18000f140`
- `0x18000f268`
- `0x18000f378`
- `0x18000f4a0`
- `0x180010548`
- `0x1800108e4`
- `0x180014230`
- `0x1800142f0`

## callees

- `0x1800080d4`
- `0x18000ec70`

## pseudocode

```c
void __fastcall std::vector<unsigned char>::_Tidy(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18000ec70  push    rbx
0x18000ec72  sub     rsp, 20h
0x18000ec76  mov     rbx, rcx
0x18000ec79  mov     rcx, [rcx]; Block
0x18000ec7c  test    rcx, rcx
0x18000ec7f  jz      short loc_18000EC9D
0x18000ec81  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ec86  mov     qword ptr [rbx], 0
0x18000ec8d  mov     qword ptr [rbx+8], 0
0x18000ec95  mov     qword ptr [rbx+10h], 0
0x18000ec9d  add     rsp, 20h
0x18000eca1  pop     rbx
0x18000eca2  retn
```
