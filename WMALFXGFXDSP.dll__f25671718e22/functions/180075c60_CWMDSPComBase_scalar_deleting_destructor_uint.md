# CWMDSPComBase::`scalar deleting destructor'(uint)

- ea: `0x180075c60`
- end: `0x180075c8d`
- name: `??_GCWMDSPComBase@@UEAAPEAXI@Z`
- size: `45`
- prototype: `void *__fastcall(CWMDSPComBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180015104`
- `0x180075c60`

## pseudocode

```c
CWMDSPComBase *__fastcall CWMDSPComBase::`scalar deleting destructor'(CWMDSPComBase *this, char a2)
{
  *(_QWORD *)this = &CWMDSPComBase::`vftable';
  _InterlockedDecrement(&g_cActiveObjects);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180075c60  push    rbx
0x180075c62  sub     rsp, 20h
0x180075c66  lea     rax, ??_7CWMDSPComBase@@6B@; const CWMDSPComBase::`vftable'
0x180075c6d  mov     rbx, rcx
0x180075c70  mov     [rcx], rax
0x180075c73  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180075c7a  test    dl, 1
0x180075c7d  jz      short loc_180075C84
0x180075c7f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180075c84  mov     rax, rbx
0x180075c87  add     rsp, 20h
0x180075c8b  pop     rbx
0x180075c8c  retn
```
