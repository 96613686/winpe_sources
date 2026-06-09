# DdcCommandHandlerDesktop::Release(void)

- ea: `0x1800031c0`
- end: `0x1800031ff`
- name: `?Release@DdcCommandHandlerDesktop@@UEAAKXZ`
- size: `63`
- prototype: `__int64 __fastcall(DdcCommandHandlerDesktop *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800016f8`
- `0x1800031c0`

## pseudocode

```c
__int64 __fastcall DdcCommandHandlerDesktop::Release(DdcCommandHandlerDesktop *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &DdcCommandHandlerDesktop::`vftable';
    _InterlockedDecrement(*((volatile signed __int32 **)this + 2));
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x1800031c0  push    rbx
0x1800031c2  sub     rsp, 20h
0x1800031c6  mov     r8, rcx
0x1800031c9  or      ebx, 0FFFFFFFFh
0x1800031cc  lock xadd [rcx+8], ebx
0x1800031d1  sub     ebx, 1
0x1800031d4  jnz     short loc_1800031F7
0x1800031d6  test    rcx, rcx
0x1800031d9  jz      short loc_1800031F7
0x1800031db  lea     rax, ??_7DdcCommandHandlerDesktop@@6B@; const DdcCommandHandlerDesktop::`vftable'
0x1800031e2  mov     [rcx], rax
0x1800031e5  lea     edx, [rbx+18h]
0x1800031e8  mov     rcx, [rcx+10h]
0x1800031ec  lock dec dword ptr [rcx]
0x1800031ef  mov     rcx, r8; Block
0x1800031f2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800031f7  mov     eax, ebx
0x1800031f9  add     rsp, 20h
0x1800031fd  pop     rbx
0x1800031fe  retn
```
