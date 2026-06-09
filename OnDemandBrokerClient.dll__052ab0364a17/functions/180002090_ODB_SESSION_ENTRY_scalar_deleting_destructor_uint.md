# _ODB_SESSION_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180002090`
- end: `0x1800020c7`
- name: `??_G_ODB_SESSION_ENTRY@@QEAAPEAXI@Z`
- size: `55`
- prototype: `_ODB_SESSION_ENTRY *__fastcall(_ODB_SESSION_ENTRY *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001b70`
- `0x180001e60`
- `0x180001f60`

## callees

- `0x180002090`
- `0x18000437c`
- `0x180007010`

## pseudocode

```c
_ODB_SESSION_ENTRY *__fastcall _ODB_SESSION_ENTRY::`scalar deleting destructor'(_ODB_SESSION_ENTRY *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 3);
  if ( v2 )
  {
    *((_QWORD *)this + 3) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002090  push    rbx
0x180002092  sub     rsp, 20h
0x180002096  mov     rbx, rcx
0x180002099  mov     rcx, [rcx+18h]
0x18000209d  test    rcx, rcx
0x1800020a0  jz      short loc_1800020B6
0x1800020a2  mov     qword ptr [rbx+18h], 0
0x1800020aa  mov     rax, [rcx]
0x1800020ad  mov     rax, [rax+10h]
0x1800020b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020b6  mov     rcx, rbx; Block
0x1800020b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800020be  mov     rax, rbx
0x1800020c1  add     rsp, 20h
0x1800020c5  pop     rbx
0x1800020c6  retn
```
