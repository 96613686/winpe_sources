# CComBase::`scalar deleting destructor'(uint)

- ea: `0x18000f060`
- end: `0x18000f092`
- name: `??_GCComBase@@UEAAPEAXI@Z`
- size: `50`
- prototype: `void *__fastcall(CComBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e2b0`
- `0x18000f060`

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
0x18000f060  push    rbx
0x18000f062  sub     rsp, 20h
0x18000f066  lea     rax, ??_7CComBase@@6B@; const CComBase::`vftable'
0x18000f06d  mov     rbx, rcx
0x18000f070  mov     [rcx], rax
0x18000f073  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18000f07a  test    dl, 1
0x18000f07d  jz      short loc_18000F089
0x18000f07f  mov     edx, 18h; unsigned __int64
0x18000f084  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f089  mov     rax, rbx
0x18000f08c  add     rsp, 20h
0x18000f090  pop     rbx
0x18000f091  retn
```
