# std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)

- ea: `0x18000f958`
- end: `0x18000f986`
- name: `??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z`
- size: `46`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `14`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180009770`
- `0x18000c964`
- `0x18000da9c`
- `0x18000ee28`
- `0x18000f4d8`
- `0x180010334`
- `0x1800108f0`
- `0x1800123a8`
- `0x18001c644`
- `0x18001c860`
- `0x18001c8bc`
- `0x18001c9bc`
- `0x18001cfa0`
- `0x18001dae4`

## callees

- `0x18000f958`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v2; // rax

  *a1 = 0;
  a1[1] = 0;
  v2 = a2[1];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  *a1 = *a2;
  a1[1] = a2[1];
  return a1;
}

```

## disassembly

```asm
0x18000f958  mov     qword ptr [rcx], 0
0x18000f95f  mov     qword ptr [rcx+8], 0
0x18000f967  mov     rax, [rdx+8]
0x18000f96b  test    rax, rax
0x18000f96e  jz      short loc_18000F974
0x18000f970  lock inc dword ptr [rax+8]
0x18000f974  mov     rax, [rdx]
0x18000f977  mov     [rcx], rax
0x18000f97a  mov     rax, [rdx+8]
0x18000f97e  mov     [rcx+8], rax
0x18000f982  mov     rax, rcx
0x18000f985  retn
```
