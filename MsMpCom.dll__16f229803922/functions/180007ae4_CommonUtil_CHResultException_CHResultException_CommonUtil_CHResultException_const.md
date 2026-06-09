# CommonUtil::CHResultException::CHResultException(CommonUtil::CHResultException const &)

- ea: `0x180007ae4`
- end: `0x180007b05`
- name: `??0CHResultException@CommonUtil@@QEAA@AEBV01@@Z`
- size: `33`
- prototype: `__int64 __fastcall(CommonUtil::CHResultException *__hidden this, const struct CommonUtil::CHResultException *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001c9c`

## pseudocode

```c
CommonUtil::CHResultException *__fastcall CommonUtil::CHResultException::CHResultException(
        CommonUtil::CHResultException *this,
        const struct CommonUtil::CHResultException *a2)
{
  exception::exception(this, a2);
  *(_QWORD *)this = &CommonUtil::CHResultException::`vftable';
  return this;
}

```

## disassembly

```asm
0x180007ae4  push    rbx
0x180007ae6  sub     rsp, 20h
0x180007aea  mov     rbx, rcx
0x180007aed  call    ??0exception@@QEAA@AEBV0@@Z_0; exception::exception(exception const &)
0x180007af2  lea     rax, ??_7CHResultException@CommonUtil@@6B@; const CommonUtil::CHResultException::`vftable'
0x180007af9  mov     [rbx], rax
0x180007afc  mov     rax, rbx
0x180007aff  add     rsp, 20h
0x180007b03  pop     rbx
0x180007b04  retn
```
