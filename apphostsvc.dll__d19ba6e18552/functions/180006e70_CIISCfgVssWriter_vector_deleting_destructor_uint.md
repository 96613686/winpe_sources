# CIISCfgVssWriter::`vector deleting destructor'(uint)

- ea: `0x180006e70`
- end: `0x180006ed2`
- name: `??_ECIISCfgVssWriter@@UEAAPEAXI@Z`
- size: `98`
- prototype: `void *__fastcall(CIISCfgVssWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180006e70`
- `0x18000a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CIISCfgVssWriter *__fastcall CIISCfgVssWriter::`vector deleting destructor'(CIISCfgVssWriter *this, char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)this = &CVssWriter::`vftable';
  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 48LL))(v4);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006e70  mov     [rsp+arg_0], rbx
0x180006e75  push    rdi
0x180006e76  sub     rsp, 20h
0x180006e7a  mov     edi, edx
0x180006e7c  mov     rbx, rcx
0x180006e7f  lea     rax, ??_7CVssWriter@@6B@; const CVssWriter::`vftable'
0x180006e86  mov     [rcx], rax
0x180006e89  mov     rcx, [rcx+8]
0x180006e8d  test    rcx, rcx
0x180006e90  jz      short loc_180006EB6
0x180006e92  mov     rax, [rcx]
0x180006e95  mov     rax, [rax+30h]
0x180006e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e9e  mov     rcx, [rbx+8]
0x180006ea2  mov     rax, [rcx]
0x180006ea5  mov     rax, [rax+10h]
0x180006ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eae  mov     qword ptr [rbx+8], 0
0x180006eb6  test    dil, 1
0x180006eba  jz      short loc_180006EC4
0x180006ebc  mov     rcx, rbx; Block
0x180006ebf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006ec4  mov     rax, rbx
0x180006ec7  mov     rbx, [rsp+28h+arg_0]
0x180006ecc  add     rsp, 20h
0x180006ed0  pop     rdi
0x180006ed1  retn
```
