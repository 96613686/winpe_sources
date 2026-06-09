# CommonUtil::CHResultException::CHResultException(CommonUtil::CHResultException const &)

- ea: `0x14000c644`
- end: `0x14000c681`
- name: `??0CHResultException@CommonUtil@@QEAA@AEBV01@@Z`
- size: `61`
- prototype: `CommonUtil::CHResultException *__fastcall(CommonUtil::CHResultException *this, const struct CommonUtil::CHResultException *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x14000c668`
- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x14000c668`

## pseudocode

```c
CommonUtil::CHResultException *__fastcall CommonUtil::CHResultException::CHResultException(
        CommonUtil::CHResultException *this,
        const struct CommonUtil::CHResultException *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  __std_exception_copy((char *)a2 + 8);
  *(_QWORD *)this = &CommonUtil::CHResultException::`vftable';
  return this;
}

```

## disassembly

```asm
0x14000c644  push    rbx
0x14000c646  sub     rsp, 20h
0x14000c64a  mov     rbx, rcx
0x14000c64d  mov     rax, rdx
0x14000c650  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x14000c657  xorps   xmm0, xmm0
0x14000c65a  mov     [rbx], rcx
0x14000c65d  lea     rdx, [rbx+8]
0x14000c661  lea     rcx, [rax+8]
0x14000c665  movups  xmmword ptr [rdx], xmm0
0x14000c668  call    cs:__imp___std_exception_copy
0x14000c66e  lea     rax, ??_7CHResultException@CommonUtil@@6B@; const CommonUtil::CHResultException::`vftable'
0x14000c675  mov     [rbx], rax
0x14000c678  mov     rax, rbx
0x14000c67b  add     rsp, 20h
0x14000c67f  pop     rbx
0x14000c680  retn
```
