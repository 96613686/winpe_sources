# CommonUtil::CHResultExceptionImpl::`scalar deleting destructor'(uint)

- ea: `0x14000e4c0`
- end: `0x14000e502`
- name: `??_GCHResultExceptionImpl@CommonUtil@@UEAAPEAXI@Z`
- size: `66`
- prototype: `CommonUtil::CHResultExceptionImpl *__fastcall(CommonUtil::CHResultExceptionImpl *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400015f4`
- `0x140002044`
- `0x14000e4c0`

## pseudocode

```c
CommonUtil::CHResultExceptionImpl *__fastcall CommonUtil::CHResultExceptionImpl::`scalar deleting destructor'(
        CommonUtil::CHResultExceptionImpl *this,
        char a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  _std_exception_destroy_0((char *)this + 8);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000e4c0  mov     [rsp+arg_0], rbx
0x14000e4c5  push    rdi
0x14000e4c6  sub     rsp, 20h
0x14000e4ca  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x14000e4d1  mov     rdi, rcx
0x14000e4d4  mov     [rcx], rax
0x14000e4d7  mov     ebx, edx
0x14000e4d9  add     rcx, 8
0x14000e4dd  call    __std_exception_destroy_0
0x14000e4e2  test    bl, 1
0x14000e4e5  jz      short loc_14000E4F4
0x14000e4e7  mov     edx, 30h ; '0'; unsigned __int64
0x14000e4ec  mov     rcx, rdi; void *
0x14000e4ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e4f4  mov     rbx, [rsp+28h+arg_0]
0x14000e4f9  mov     rax, rdi
0x14000e4fc  add     rsp, 20h
0x14000e500  pop     rdi
0x14000e501  retn
```
