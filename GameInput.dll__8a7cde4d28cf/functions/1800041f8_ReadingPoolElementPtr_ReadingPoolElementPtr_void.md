# ReadingPoolElementPtr::~ReadingPoolElementPtr(void)

- ea: `0x1800041f8`
- end: `0x180004222`
- name: `??1ReadingPoolElementPtr@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(ReadingPoolElementPtr *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x1800043e0`
- `0x18000630c`
- `0x1800069f0`
- `0x180007140`
- `0x180007278`
- `0x180007850`
- `0x180008610`
- `0x18000a710`
- `0x18000ab40`

## callees

- `0x1800041f8`
- `0x18000a7a0`
- `0x1800248a8`

## pseudocode

```c
void __fastcall ReadingPoolElementPtr::~ReadingPoolElementPtr(ReadingPoolElementPtr *this)
{
  __int64 v2; // rcx
  SharedBuffer **v3; // r11

  v2 = *(_QWORD *)this;
  if ( v2 )
  {
    ReadingPool::ReleaseElementReference(*(_QWORD *)(v2 + 24), *((_QWORD *)this + 1));
    SharedBuffer::ReleaseReference(*v3);
  }
}

```

## disassembly

```asm
0x1800041f8  sub     rsp, 28h
0x1800041fc  mov     r11, rcx
0x1800041ff  mov     rcx, [rcx]
0x180004202  test    rcx, rcx
0x180004205  jz      short loc_18000421C
0x180004207  mov     rdx, [r11+8]
0x18000420b  mov     rcx, [rcx+18h]
0x18000420f  call    ?ReleaseElementReference@ReadingPool@@QEAAXVReadingPoolElementId@@@Z; ReadingPool::ReleaseElementReference(ReadingPoolElementId)
0x180004214  mov     rcx, [r11]; this
0x180004217  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x18000421c  add     rsp, 28h
0x180004220  retn
```
