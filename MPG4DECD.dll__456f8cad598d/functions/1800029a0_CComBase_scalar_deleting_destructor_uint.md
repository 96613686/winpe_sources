# CComBase::`scalar deleting destructor'(uint)

- ea: `0x1800029a0`
- end: `0x1800029d2`
- name: `??_GCComBase@@UEAAPEAXI@Z`
- size: `50`
- prototype: `void *__fastcall(CComBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001450`
- `0x1800029a0`

## pseudocode

```c
CComBase *__fastcall CComBase::`scalar deleting destructor'(CComBase *this, char a2)
{
  *(_QWORD *)this = &CComBase::`vftable';
  _InterlockedDecrement(&g_cActiveObjects);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800029a0  push    rbx
0x1800029a2  sub     rsp, 20h
0x1800029a6  lea     rax, ??_7CComBase@@6B@; const CComBase::`vftable'
0x1800029ad  mov     rbx, rcx
0x1800029b0  mov     [rcx], rax
0x1800029b3  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x1800029ba  test    dl, 1
0x1800029bd  jz      short loc_1800029C9
0x1800029bf  mov     edx, 18h; unsigned __int64
0x1800029c4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800029c9  mov     rax, rbx
0x1800029cc  add     rsp, 20h
0x1800029d0  pop     rbx
0x1800029d1  retn
```
