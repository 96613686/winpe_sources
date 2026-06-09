# CommonUtil::CHResultExceptionImpl::~CHResultExceptionImpl(void)

- ea: `0x14000d614`
- end: `0x14000d627`
- name: `??1CHResultExceptionImpl@CommonUtil@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(CommonUtil::CHResultExceptionImpl *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002044`

## pseudocode

```c
void __fastcall CommonUtil::CHResultExceptionImpl::~CHResultExceptionImpl(CommonUtil::CHResultExceptionImpl *this)
{
  *(_QWORD *)this = &std::exception::`vftable';
  _std_exception_destroy_0((char *)this + 8);
}

```

## disassembly

```asm
0x14000d614  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x14000d61b  mov     [rcx], rax
0x14000d61e  add     rcx, 8
0x14000d622  jmp     __std_exception_destroy_0
```
