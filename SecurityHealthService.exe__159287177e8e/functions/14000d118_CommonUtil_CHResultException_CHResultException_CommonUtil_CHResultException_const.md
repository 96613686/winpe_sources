# CommonUtil::CHResultException::CHResultException(CommonUtil::CHResultException const &)

- ea: `0x14000d118`
- end: `0x14000d154`
- name: `??0CHResultException@CommonUtil@@QEAA@AEBV01@@Z`
- size: `60`
- prototype: `CommonUtil::CHResultException *__fastcall(CommonUtil::CHResultException *this, const struct CommonUtil::CHResultException *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002038`

## pseudocode

```c
CommonUtil::CHResultException *__fastcall CommonUtil::CHResultException::CHResultException(
        CommonUtil::CHResultException *this,
        const struct CommonUtil::CHResultException *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  _std_exception_copy_0((char *)a2 + 8);
  *(_QWORD *)this = &CommonUtil::CHResultException::`vftable';
  return this;
}

```

## disassembly

```asm
0x14000d118  push    rbx
0x14000d11a  sub     rsp, 20h
0x14000d11e  mov     rbx, rcx
0x14000d121  mov     rax, rdx
0x14000d124  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x14000d12b  xorps   xmm0, xmm0
0x14000d12e  mov     [rbx], rcx
0x14000d131  lea     rdx, [rbx+8]
0x14000d135  lea     rcx, [rax+8]
0x14000d139  movups  xmmword ptr [rdx], xmm0
0x14000d13c  call    __std_exception_copy_0
0x14000d141  lea     rax, ??_7CHResultException@CommonUtil@@6B@; const CommonUtil::CHResultException::`vftable'
0x14000d148  mov     [rbx], rax
0x14000d14b  mov     rax, rbx
0x14000d14e  add     rsp, 20h
0x14000d152  pop     rbx
0x14000d153  retn
```
