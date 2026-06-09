# CommonUtil::CSecurityAttributesHolder::`scalar deleting destructor'(uint)

- ea: `0x180006100`
- end: `0x180006127`
- name: `??_GCSecurityAttributesHolder@CommonUtil@@MEAAPEAXI@Z`
- size: `39`
- prototype: `void *__fastcall(CommonUtil::CSecurityAttributesHolder *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006100`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006118`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006118`

## pseudocode

```c
CommonUtil::CSecurityAttributesHolder *__fastcall CommonUtil::CSecurityAttributesHolder::`scalar deleting destructor'(
        CommonUtil::CSecurityAttributesHolder *this,
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
0x180006100  push    rbx
0x180006102  sub     rsp, 20h
0x180006106  lea     rax, ??_7CRefObject@CommonUtil@@6B@; const CommonUtil::CRefObject::`vftable'
0x18000610d  mov     rbx, rcx
0x180006110  mov     [rcx], rax
0x180006113  test    dl, 1
0x180006116  jz      short loc_18000611E
0x180006118  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000611e  mov     rax, rbx
0x180006121  add     rsp, 20h
0x180006125  pop     rbx
0x180006126  retn
```
