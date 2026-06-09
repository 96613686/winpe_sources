# CommonUtil::CHResultExceptionImpl::~CHResultExceptionImpl(void)

- ea: `0x180007bb0`
- end: `0x180007bbf`
- name: `??1CHResultExceptionImpl@CommonUtil@@UEAA@XZ`
- size: `15`
- prototype: `void __fastcall(CommonUtil::CHResultExceptionImpl *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001ca8`

## pseudocode

```c
void __fastcall CommonUtil::CHResultExceptionImpl::~CHResultExceptionImpl(CommonUtil::CHResultExceptionImpl *this)
{
  *(_QWORD *)this = &CommonUtil::CHResultException::`vftable';
  exception::~exception(this);
}

```

## disassembly

```asm
0x180007bb0  lea     rax, ??_7CHResultException@CommonUtil@@6B@; const CommonUtil::CHResultException::`vftable'
0x180007bb7  mov     [rcx], rax
0x180007bba  jmp     ??1exception@@UEAA@XZ_0; exception::~exception(void)
```
