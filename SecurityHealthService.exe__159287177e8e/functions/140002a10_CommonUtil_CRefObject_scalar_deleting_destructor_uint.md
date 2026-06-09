# CommonUtil::CRefObject::`scalar deleting destructor'(uint)

- ea: `0x140002a10`
- end: `0x140002a3b`
- name: `??_GCRefObject@CommonUtil@@MEAAPEAXI@Z`
- size: `43`
- prototype: `CommonUtil::CRefObject *__fastcall(CommonUtil::CRefObject *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400015f4`
- `0x140002a10`

## pseudocode

```c
CommonUtil::CRefObject *__fastcall CommonUtil::CRefObject::`scalar deleting destructor'(
        CommonUtil::CRefObject *this,
        char a2)
{
  *(_QWORD *)this = &CommonUtil::CRefObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140002a10  push    rbx
0x140002a12  sub     rsp, 20h
0x140002a16  lea     rax, ??_7CRefObject@CommonUtil@@6B@; const CommonUtil::CRefObject::`vftable'
0x140002a1d  mov     rbx, rcx
0x140002a20  mov     [rcx], rax
0x140002a23  test    dl, 1
0x140002a26  jz      short loc_140002A32
0x140002a28  mov     edx, 10h; unsigned __int64
0x140002a2d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002a32  mov     rax, rbx
0x140002a35  add     rsp, 20h
0x140002a39  pop     rbx
0x140002a3a  retn
```
