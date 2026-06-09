# CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl(CommonUtil::CHResultExceptionImpl const &)

- ea: `0x14000e410`
- end: `0x14000e473`
- name: `??0CHResultExceptionImpl@CommonUtil@@QEAA@AEBV01@@Z`
- size: `99`
- prototype: `CommonUtil::CHResultExceptionImpl *__fastcall(CommonUtil::CHResultExceptionImpl *this, const struct CommonUtil::CHResultExceptionImpl *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002038`

## pseudocode

```c
CommonUtil::CHResultExceptionImpl *__fastcall CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl(
        CommonUtil::CHResultExceptionImpl *this,
        const struct CommonUtil::CHResultExceptionImpl *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  _std_exception_copy_0((char *)a2 + 8);
  *(_QWORD *)this = &CommonUtil::CHResultExceptionImpl::`vftable';
  *((_QWORD *)this + 3) = *((_QWORD *)a2 + 3);
  *((_DWORD *)this + 8) = *((_DWORD *)a2 + 8);
  *((_WORD *)this + 18) = *((_WORD *)a2 + 18);
  *((_DWORD *)this + 10) = *((_DWORD *)a2 + 10);
  return this;
}

```

## disassembly

```asm
0x14000e410  mov     [rsp+arg_0], rbx
0x14000e415  push    rdi
0x14000e416  sub     rsp, 20h
0x14000e41a  mov     rbx, rdx
0x14000e41d  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x14000e424  mov     [rcx], rax
0x14000e427  lea     rdx, [rcx+8]
0x14000e42b  mov     rdi, rcx
0x14000e42e  xorps   xmm0, xmm0
0x14000e431  movups  xmmword ptr [rdx], xmm0
0x14000e434  lea     rcx, [rbx+8]
0x14000e438  call    __std_exception_copy_0
0x14000e43d  lea     rax, ??_7CHResultExceptionImpl@CommonUtil@@6B@; const CommonUtil::CHResultExceptionImpl::`vftable'
0x14000e444  mov     [rdi], rax
0x14000e447  movsd   xmm0, qword ptr [rbx+18h]
0x14000e44c  movsd   qword ptr [rdi+18h], xmm0
0x14000e451  mov     eax, [rbx+20h]
0x14000e454  mov     [rdi+20h], eax
0x14000e457  movzx   eax, word ptr [rbx+24h]
0x14000e45b  mov     [rdi+24h], ax
0x14000e45f  mov     eax, [rbx+28h]
0x14000e462  mov     rbx, [rsp+28h+arg_0]
0x14000e467  mov     [rdi+28h], eax
0x14000e46a  mov     rax, rdi
0x14000e46d  add     rsp, 20h
0x14000e471  pop     rdi
0x14000e472  retn
```
