# CComBase::`scalar deleting destructor'(uint)

- ea: `0x1800028e0`
- end: `0x180002912`
- name: `??_GCComBase@@UEAAPEAXI@Z`
- size: `50`
- prototype: `void *__fastcall(CComBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001420`
- `0x1800028e0`

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
0x1800028e0  push    rbx
0x1800028e2  sub     rsp, 20h
0x1800028e6  lea     rax, ??_7CComBase@@6B@; const CComBase::`vftable'
0x1800028ed  mov     rbx, rcx
0x1800028f0  mov     [rcx], rax
0x1800028f3  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x1800028fa  test    dl, 1
0x1800028fd  jz      short loc_180002909
0x1800028ff  mov     edx, 18h; unsigned __int64
0x180002904  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002909  mov     rax, rbx
0x18000290c  add     rsp, 20h
0x180002910  pop     rbx
0x180002911  retn
```
