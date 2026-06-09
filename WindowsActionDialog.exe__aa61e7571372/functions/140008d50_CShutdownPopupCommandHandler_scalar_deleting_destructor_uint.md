# CShutdownPopupCommandHandler::`scalar deleting destructor'(uint)

- ea: `0x140008d50`
- end: `0x140008d78`
- name: `??_GCShutdownPopupCommandHandler@@UEAAPEAXI@Z`
- size: `40`
- prototype: `void *__fastcall(CShutdownPopupCommandHandler *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x14000175c`
- `0x140008d50`

## pseudocode

```c
CShutdownPopupCommandHandler *__fastcall CShutdownPopupCommandHandler::`scalar deleting destructor'(
        CShutdownPopupCommandHandler *this,
        char a2)
{
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140008d50  push    rbx
0x140008d52  sub     rsp, 20h
0x140008d56  mov     dword ptr [rcx+0Ch], 0C0000001h
0x140008d5d  mov     rbx, rcx
0x140008d60  test    dl, 1
0x140008d63  jz      short loc_140008D6F
0x140008d65  mov     edx, 20h ; ' '
0x140008d6a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008d6f  mov     rax, rbx
0x140008d72  add     rsp, 20h
0x140008d76  pop     rbx
0x140008d77  retn
```
