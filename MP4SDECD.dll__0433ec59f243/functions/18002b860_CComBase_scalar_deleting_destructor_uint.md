# CComBase::`scalar deleting destructor'(uint)

- ea: `0x18002b860`
- end: `0x18002b892`
- name: `??_GCComBase@@UEAAPEAXI@Z`
- size: `50`
- prototype: `void *__fastcall(CComBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002aae4`
- `0x18002b860`

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
0x18002b860  push    rbx
0x18002b862  sub     rsp, 20h
0x18002b866  lea     rax, ??_7CComBase@@6B@; const CComBase::`vftable'
0x18002b86d  mov     rbx, rcx
0x18002b870  mov     [rcx], rax
0x18002b873  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18002b87a  test    dl, 1
0x18002b87d  jz      short loc_18002B889
0x18002b87f  mov     edx, 18h
0x18002b884  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b889  mov     rax, rbx
0x18002b88c  add     rsp, 20h
0x18002b890  pop     rbx
0x18002b891  retn
```
