# CommonUtil::CHResultExceptionImpl::`scalar deleting destructor'(uint)

- ea: `0x140002e30`
- end: `0x140002e72`
- name: `??_GCHResultExceptionImpl@CommonUtil@@UEAAPEAXI@Z`
- size: `66`
- prototype: `void *__fastcall(CommonUtil::CHResultExceptionImpl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140002e30`
- `0x140005c40`
- `0x14000792c`

## pseudocode

```c
CommonUtil::CHResultExceptionImpl *__fastcall CommonUtil::CHResultExceptionImpl::`scalar deleting destructor'(
        CommonUtil::CHResultExceptionImpl *this,
        char a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  _std_exception_destroy((char *)this + 8);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140002e30  mov     [rsp+arg_0], rbx
0x140002e35  push    rdi
0x140002e36  sub     rsp, 20h
0x140002e3a  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x140002e41  mov     rdi, rcx
0x140002e44  mov     [rcx], rax
0x140002e47  mov     ebx, edx
0x140002e49  add     rcx, 8
0x140002e4d  call    __std_exception_destroy
0x140002e52  test    bl, 1
0x140002e55  jz      short loc_140002E64
0x140002e57  mov     edx, 30h ; '0'; unsigned __int64
0x140002e5c  mov     rcx, rdi; void *
0x140002e5f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002e64  mov     rbx, [rsp+28h+arg_0]
0x140002e69  mov     rax, rdi
0x140002e6c  add     rsp, 20h
0x140002e70  pop     rdi
0x140002e71  retn
```
