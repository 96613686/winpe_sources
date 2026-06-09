# DdcTaskStateHandlerDesktop::Release(void)

- ea: `0x180003f20`
- end: `0x180003f5f`
- name: `?Release@DdcTaskStateHandlerDesktop@@UEAAKXZ`
- size: `63`
- prototype: `__int64 __fastcall(DdcTaskStateHandlerDesktop *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x1800016f8`
- `0x180003f20`

## pseudocode

```c
__int64 __fastcall DdcTaskStateHandlerDesktop::Release(DdcTaskStateHandlerDesktop *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &DdcTaskStateHandlerDesktop::`vftable';
    _InterlockedDecrement(*((volatile signed __int32 **)this + 2));
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x180003f20  push    rbx
0x180003f22  sub     rsp, 20h
0x180003f26  mov     r8, rcx
0x180003f29  or      ebx, 0FFFFFFFFh
0x180003f2c  lock xadd [rcx+8], ebx
0x180003f31  sub     ebx, 1
0x180003f34  jnz     short loc_180003F57
0x180003f36  test    rcx, rcx
0x180003f39  jz      short loc_180003F57
0x180003f3b  lea     rax, ??_7DdcTaskStateHandlerDesktop@@6B@; const DdcTaskStateHandlerDesktop::`vftable'
0x180003f42  mov     [rcx], rax
0x180003f45  lea     edx, [rbx+18h]
0x180003f48  mov     rcx, [rcx+10h]
0x180003f4c  lock dec dword ptr [rcx]
0x180003f4f  mov     rcx, r8; Block
0x180003f52  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003f57  mov     eax, ebx
0x180003f59  add     rsp, 20h
0x180003f5d  pop     rbx
0x180003f5e  retn
```
