# std::_Ref_count_obj2<Concurrency::details::_Task_impl<uchar>>::`vector deleting destructor'(uint)

- ea: `0x180010600`
- end: `0x18001062b`
- name: `??_E?$_Ref_count_obj2@U?$_Task_impl@E@details@Concurrency@@@std@@UEAAPEAXI@Z`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x180002054`
- `0x180010600`

## pseudocode

```c
_QWORD *__fastcall std::_Ref_count_obj2<Concurrency::details::_Task_impl<unsigned char>>::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &std::_Ref_count_obj2<Concurrency::details::_Task_impl<unsigned char>>::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180010600  push    rbx
0x180010602  sub     rsp, 20h
0x180010606  lea     rax, ??_7?$_Ref_count_obj2@U?$_Task_impl@E@details@Concurrency@@@std@@6B@; const std::_Ref_count_obj2<Concurrency::details::_Task_impl<uchar>>::`vftable'
0x18001060d  mov     rbx, rcx
0x180010610  mov     [rcx], rax
0x180010613  test    dl, 1
0x180010616  jz      short loc_180010622
0x180010618  mov     edx, 1C8h; unsigned __int64
0x18001061d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010622  mov     rax, rbx
0x180010625  add     rsp, 20h
0x180010629  pop     rbx
0x18001062a  retn
```
