# DdcTaskStateHandlerDesktopFactory::Release(void)

- ea: `0x180002360`
- end: `0x18000239f`
- name: `?Release@DdcTaskStateHandlerDesktopFactory@@UEAAKXZ`
- size: `63`
- prototype: `__int64 __fastcall(DdcTaskStateHandlerDesktopFactory *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x1800016f8`
- `0x180002360`

## pseudocode

```c
__int64 __fastcall DdcTaskStateHandlerDesktopFactory::Release(DdcTaskStateHandlerDesktopFactory *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &DdcTaskStateHandlerDesktopFactory::`vftable';
    _InterlockedDecrement(*((volatile signed __int32 **)this + 2));
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x180002360  push    rbx
0x180002362  sub     rsp, 20h
0x180002366  mov     r8, rcx
0x180002369  or      ebx, 0FFFFFFFFh
0x18000236c  lock xadd [rcx+8], ebx
0x180002371  sub     ebx, 1
0x180002374  jnz     short loc_180002397
0x180002376  test    rcx, rcx
0x180002379  jz      short loc_180002397
0x18000237b  lea     rax, ??_7DdcTaskStateHandlerDesktopFactory@@6B@; const DdcTaskStateHandlerDesktopFactory::`vftable'
0x180002382  mov     [rcx], rax
0x180002385  lea     edx, [rbx+18h]
0x180002388  mov     rcx, [rcx+10h]
0x18000238c  lock dec dword ptr [rcx]
0x18000238f  mov     rcx, r8; Block
0x180002392  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002397  mov     eax, ebx
0x180002399  add     rsp, 20h
0x18000239d  pop     rbx
0x18000239e  retn
```
