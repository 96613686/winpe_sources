# CommonUtil::IRefObject::`scalar deleting destructor'(uint)

- ea: `0x14000e6b0`
- end: `0x14000e6db`
- name: `??_GIRefObject@CommonUtil@@MEAAPEAXI@Z`
- size: `43`
- prototype: `CommonUtil::IRefObject *__fastcall(CommonUtil::IRefObject *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400015f4`
- `0x14000e6b0`

## pseudocode

```c
CommonUtil::IRefObject *__fastcall CommonUtil::IRefObject::`scalar deleting destructor'(
        CommonUtil::IRefObject *this,
        char a2)
{
  *(_QWORD *)this = &CommonUtil::IRefObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000e6b0  push    rbx
0x14000e6b2  sub     rsp, 20h
0x14000e6b6  lea     rax, ??_7IRefObject@CommonUtil@@6B@; const CommonUtil::IRefObject::`vftable'
0x14000e6bd  mov     rbx, rcx
0x14000e6c0  mov     [rcx], rax
0x14000e6c3  test    dl, 1
0x14000e6c6  jz      short loc_14000E6D2
0x14000e6c8  mov     edx, 8; unsigned __int64
0x14000e6cd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e6d2  mov     rax, rbx
0x14000e6d5  add     rsp, 20h
0x14000e6d9  pop     rbx
0x14000e6da  retn
```
