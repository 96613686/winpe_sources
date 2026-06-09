# CComBase::`scalar deleting destructor'(uint)

- ea: `0x18006adf0`
- end: `0x18006ae22`
- name: `??_GCComBase@@UEAAPEAXI@Z`
- size: `50`
- prototype: `void *__fastcall(CComBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800085d0`
- `0x18006adf0`

## pseudocode

```c
CComBase *__fastcall CComBase::`scalar deleting destructor'(CComBase *this, char a2)
{
  *(_QWORD *)this = &CComBase::`vftable';
  _InterlockedDecrement(&g_cActiveObjects);
  if ( (a2 & 1) != 0 )
    auFree(this, 24);
  return this;
}

```

## disassembly

```asm
0x18006adf0  push    rbx
0x18006adf2  sub     rsp, 20h
0x18006adf6  lea     rax, ??_7CComBase@@6B@; const CComBase::`vftable'
0x18006adfd  mov     rbx, rcx
0x18006ae00  mov     [rcx], rax
0x18006ae03  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18006ae0a  test    dl, 1
0x18006ae0d  jz      short loc_18006AE19
0x18006ae0f  mov     edx, 18h
0x18006ae14  call    auFree
0x18006ae19  mov     rax, rbx
0x18006ae1c  add     rsp, 20h
0x18006ae20  pop     rbx
0x18006ae21  retn
```
