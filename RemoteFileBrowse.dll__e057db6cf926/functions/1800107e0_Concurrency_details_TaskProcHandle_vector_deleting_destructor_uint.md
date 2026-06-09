# Concurrency::details::_TaskProcHandle::`vector deleting destructor'(uint)

- ea: `0x1800107e0`
- end: `0x18001080b`
- name: `??_E_TaskProcHandle@details@Concurrency@@UEAAPEAXI@Z`
- size: `43`
- prototype: `Concurrency::details::_TaskProcHandle *__fastcall(Concurrency::details::_TaskProcHandle *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x180002054`
- `0x1800107e0`

## pseudocode

```c
Concurrency::details::_TaskProcHandle *__fastcall Concurrency::details::_TaskProcHandle::`vector deleting destructor'(
        Concurrency::details::_TaskProcHandle *this,
        char a2)
{
  *(_QWORD *)this = &Concurrency::details::_TaskProcHandle::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800107e0  push    rbx
0x1800107e2  sub     rsp, 20h
0x1800107e6  lea     rax, ??_7_TaskProcHandle@details@Concurrency@@6B@; const Concurrency::details::_TaskProcHandle::`vftable'
0x1800107ed  mov     rbx, rcx
0x1800107f0  mov     [rcx], rax
0x1800107f3  test    dl, 1
0x1800107f6  jz      short loc_180010802
0x1800107f8  mov     edx, 8; unsigned __int64
0x1800107fd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010802  mov     rax, rbx
0x180010805  add     rsp, 20h
0x180010809  pop     rbx
0x18001080a  retn
```
