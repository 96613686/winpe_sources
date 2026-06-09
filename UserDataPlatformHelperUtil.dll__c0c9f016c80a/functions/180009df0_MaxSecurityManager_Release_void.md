# MaxSecurityManager::Release(void)

- ea: `0x180009df0`
- end: `0x180009e1f`
- name: `?Release@MaxSecurityManager@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(MaxSecurityManager *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001160`
- `0x180009df0`

## pseudocode

```c
__int64 __fastcall MaxSecurityManager::Release(MaxSecurityManager *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &MaxSecurityManager::`vftable';
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x180009df0  push    rbx
0x180009df2  sub     rsp, 20h
0x180009df6  or      ebx, 0FFFFFFFFh
0x180009df9  lock xadd [rcx+8], ebx
0x180009dfe  sub     ebx, 1
0x180009e01  jnz     short loc_180009E17
0x180009e03  test    rcx, rcx
0x180009e06  jz      short loc_180009E17
0x180009e08  lea     rax, ??_7MaxSecurityManager@@6B@; const MaxSecurityManager::`vftable'
0x180009e0f  mov     [rcx], rax
0x180009e12  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009e17  mov     eax, ebx
0x180009e19  add     rsp, 20h
0x180009e1d  pop     rbx
0x180009e1e  retn
```
