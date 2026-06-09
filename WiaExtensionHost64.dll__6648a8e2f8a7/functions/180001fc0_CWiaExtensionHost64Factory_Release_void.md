# CWiaExtensionHost64Factory::Release(void)

- ea: `0x180001fc0`
- end: `0x180001ff9`
- name: `?Release@CWiaExtensionHost64Factory@@UEAAKXZ`
- size: `57`
- prototype: `__int64 __fastcall(CWiaExtensionHost64Factory *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180001464`
- `0x180001fc0`

## pseudocode

```c
__int64 __fastcall CWiaExtensionHost64Factory::Release(CWiaExtensionHost64Factory *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &CWiaExtensionHost64Factory::`vftable';
    _InterlockedDecrement((volatile signed __int32 *)&g_cRef);
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x180001fc0  push    rbx
0x180001fc2  sub     rsp, 20h
0x180001fc6  or      ebx, 0FFFFFFFFh
0x180001fc9  lock xadd [rcx+8], ebx
0x180001fce  sub     ebx, 1
0x180001fd1  jnz     short loc_180001FF1
0x180001fd3  test    rcx, rcx
0x180001fd6  jz      short loc_180001FF1
0x180001fd8  lea     rax, ??_7CWiaExtensionHost64Factory@@6B@; const CWiaExtensionHost64Factory::`vftable'
0x180001fdf  mov     [rcx], rax
0x180001fe2  lea     edx, [rbx+10h]; unsigned __int64
0x180001fe5  lock dec cs:?g_cRef@@3KA; ulong g_cRef
0x180001fec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180001ff1  mov     eax, ebx
0x180001ff3  add     rsp, 20h
0x180001ff7  pop     rbx
0x180001ff8  retn
```
