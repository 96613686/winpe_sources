# CWiaExtensionHost64::Release(void)

- ea: `0x180001e30`
- end: `0x180001e69`
- name: `?Release@CWiaExtensionHost64@@UEAAKXZ`
- size: `57`
- prototype: `__int64 __fastcall(CWiaExtensionHost64 *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180001464`
- `0x180001e30`

## pseudocode

```c
__int64 __fastcall CWiaExtensionHost64::Release(CWiaExtensionHost64 *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &CWiaExtensionHost64::`vftable';
    _InterlockedDecrement((volatile signed __int32 *)&g_cRef);
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x180001e30  push    rbx
0x180001e32  sub     rsp, 20h
0x180001e36  or      ebx, 0FFFFFFFFh
0x180001e39  lock xadd [rcx+8], ebx
0x180001e3e  sub     ebx, 1
0x180001e41  jnz     short loc_180001E61
0x180001e43  test    rcx, rcx
0x180001e46  jz      short loc_180001E61
0x180001e48  lea     rax, ??_7CWiaExtensionHost64@@6B@; const CWiaExtensionHost64::`vftable'
0x180001e4f  mov     [rcx], rax
0x180001e52  lea     edx, [rbx+10h]; unsigned __int64
0x180001e55  lock dec cs:?g_cRef@@3KA; ulong g_cRef
0x180001e5c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180001e61  mov     eax, ebx
0x180001e63  add     rsp, 20h
0x180001e67  pop     rbx
0x180001e68  retn
```
