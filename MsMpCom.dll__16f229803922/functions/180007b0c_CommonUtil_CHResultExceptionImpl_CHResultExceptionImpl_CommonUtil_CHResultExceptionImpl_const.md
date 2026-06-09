# CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl(CommonUtil::CHResultExceptionImpl const &)

- ea: `0x180007b0c`
- end: `0x180007b57`
- name: `??0CHResultExceptionImpl@CommonUtil@@QEAA@AEBV01@@Z`
- size: `75`
- prototype: `__int64 __fastcall(CommonUtil::CHResultExceptionImpl *__hidden this, const struct CommonUtil::CHResultExceptionImpl *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001c9c`

## pseudocode

```c
CommonUtil::CHResultExceptionImpl *__fastcall CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl(
        CommonUtil::CHResultExceptionImpl *this,
        const struct CommonUtil::CHResultExceptionImpl *a2)
{
  exception::exception(this, a2);
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
0x180007b0c  mov     [rsp+arg_0], rbx
0x180007b11  push    rdi
0x180007b12  sub     rsp, 20h
0x180007b16  mov     rbx, rdx
0x180007b19  mov     rdi, rcx
0x180007b1c  call    ??0exception@@QEAA@AEBV0@@Z_0; exception::exception(exception const &)
0x180007b21  lea     rax, ??_7CHResultExceptionImpl@CommonUtil@@6B@; const CommonUtil::CHResultExceptionImpl::`vftable'
0x180007b28  mov     [rdi], rax
0x180007b2b  movsd   xmm0, qword ptr [rbx+18h]
0x180007b30  movsd   qword ptr [rdi+18h], xmm0
0x180007b35  mov     eax, [rbx+20h]
0x180007b38  mov     [rdi+20h], eax
0x180007b3b  movzx   eax, word ptr [rbx+24h]
0x180007b3f  mov     [rdi+24h], ax
0x180007b43  mov     eax, [rbx+28h]
0x180007b46  mov     rbx, [rsp+28h+arg_0]
0x180007b4b  mov     [rdi+28h], eax
0x180007b4e  mov     rax, rdi
0x180007b51  add     rsp, 20h
0x180007b55  pop     rdi
0x180007b56  retn
```
