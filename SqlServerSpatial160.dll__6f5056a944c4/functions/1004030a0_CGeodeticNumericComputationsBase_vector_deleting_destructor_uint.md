# CGeodeticNumericComputationsBase::`vector deleting destructor'(uint)

- ea: `0x1004030a0`
- end: `0x1004030d8`
- name: `??_ECGeodeticNumericComputationsBase@@UEAAPEAXI@Z`
- size: `56`
- prototype: `void *__fastcall(CGeodeticNumericComputationsBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1004030a0`
- `0x100468a54`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CGeodeticNumericComputationsBase *__fastcall CGeodeticNumericComputationsBase::`vector deleting destructor'(
        CGeodeticNumericComputationsBase *this,
        char a2)
{
  *(_QWORD *)this = &IMglGeometrySink::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1004030a0  mov     [rsp+arg_0], rcx
0x1004030a5  push    rbx
0x1004030a6  sub     rsp, 30h
0x1004030aa  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1004030b3  mov     rbx, rcx
0x1004030b6  lea     rax, ??_7IMglGeometrySink@@6B@
0x1004030bd  mov     [rcx], rax
0x1004030c0  test    dl, 1
0x1004030c3  jz      short loc_1004030CF
0x1004030c5  mov     edx, 38h ; '8'; unsigned __int64
0x1004030ca  call    ??3@YAXPEAX_K@Z
0x1004030cf  mov     rax, rbx
0x1004030d2  add     rsp, 30h
0x1004030d6  pop     rbx
0x1004030d7  retn
```
