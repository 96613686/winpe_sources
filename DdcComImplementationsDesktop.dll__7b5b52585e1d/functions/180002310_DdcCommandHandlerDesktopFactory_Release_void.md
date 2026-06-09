# DdcCommandHandlerDesktopFactory::Release(void)

- ea: `0x180002310`
- end: `0x18000234f`
- name: `?Release@DdcCommandHandlerDesktopFactory@@UEAAKXZ`
- size: `63`
- prototype: `__int64 __fastcall(DdcCommandHandlerDesktopFactory *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800016f8`
- `0x180002310`

## pseudocode

```c
__int64 __fastcall DdcCommandHandlerDesktopFactory::Release(DdcCommandHandlerDesktopFactory *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &DdcCommandHandlerDesktopFactory::`vftable';
    _InterlockedDecrement(*((volatile signed __int32 **)this + 2));
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x180002310  push    rbx
0x180002312  sub     rsp, 20h
0x180002316  mov     r8, rcx
0x180002319  or      ebx, 0FFFFFFFFh
0x18000231c  lock xadd [rcx+8], ebx
0x180002321  sub     ebx, 1
0x180002324  jnz     short loc_180002347
0x180002326  test    rcx, rcx
0x180002329  jz      short loc_180002347
0x18000232b  lea     rax, ??_7DdcCommandHandlerDesktopFactory@@6B@; const DdcCommandHandlerDesktopFactory::`vftable'
0x180002332  mov     [rcx], rax
0x180002335  lea     edx, [rbx+18h]
0x180002338  mov     rcx, [rcx+10h]
0x18000233c  lock dec dword ptr [rcx]
0x18000233f  mov     rcx, r8; Block
0x180002342  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002347  mov     eax, ebx
0x180002349  add     rsp, 20h
0x18000234d  pop     rbx
0x18000234e  retn
```
