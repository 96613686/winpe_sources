# CMILCOMBase::`scalar deleting destructor'(uint)

- ea: `0x180022880`
- end: `0x1800228b2`
- name: `??_GCMILCOMBase@@UEAAPEAXI@Z`
- size: `50`
- prototype: `void *__fastcall(CMILCOMBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180021a54`
- `0x180022880`

## pseudocode

```c
CMILCOMBase *__fastcall CMILCOMBase::`scalar deleting destructor'(CMILCOMBase *this, char a2)
{
  *(_QWORD *)this = &CMILCOMBase::`vftable';
  _InterlockedDecrement(&g_cActiveObjects);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180022880  push    rbx
0x180022882  sub     rsp, 20h
0x180022886  lea     rax, ??_7CMILCOMBase@@6B@; const CMILCOMBase::`vftable'
0x18002288d  mov     rbx, rcx
0x180022890  mov     [rcx], rax
0x180022893  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18002289a  test    dl, 1
0x18002289d  jz      short loc_1800228A9
0x18002289f  mov     edx, 10h
0x1800228a4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800228a9  mov     rax, rbx
0x1800228ac  add     rsp, 20h
0x1800228b0  pop     rbx
0x1800228b1  retn
```
