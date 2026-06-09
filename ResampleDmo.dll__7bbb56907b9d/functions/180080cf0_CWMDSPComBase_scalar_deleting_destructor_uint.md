# CWMDSPComBase::`scalar deleting destructor'(uint)

- ea: `0x180080cf0`
- end: `0x180080d1d`
- name: `??_GCWMDSPComBase@@UEAAPEAXI@Z`
- size: `45`
- prototype: `void *__fastcall(CWMDSPComBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000b1b0`
- `0x180080cf0`

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
0x180080cf0  push    rbx
0x180080cf2  sub     rsp, 20h
0x180080cf6  lea     rax, ??_7CWMDSPComBase@@6B@; const CWMDSPComBase::`vftable'
0x180080cfd  mov     rbx, rcx
0x180080d00  mov     [rcx], rax
0x180080d03  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180080d0a  test    dl, 1
0x180080d0d  jz      short loc_180080D14
0x180080d0f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180080d14  mov     rax, rbx
0x180080d17  add     rsp, 20h
0x180080d1b  pop     rbx
0x180080d1c  retn
```
