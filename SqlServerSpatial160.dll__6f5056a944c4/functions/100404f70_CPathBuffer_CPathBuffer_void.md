# CPathBuffer::~CPathBuffer(void)

- ea: `0x100404f70`
- end: `0x100404fc0`
- name: `??1CPathBuffer@@UEAA@XZ`
- size: `80`
- prototype: `void __fastcall(CPathBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10046f4b2`

## callees

- `0x100403b50`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CPathBuffer::~CPathBuffer(CPathBuffer *this)
{
  *(_QWORD *)this = &CPathBuffer::`vftable';
  COptimizedOutlineModule::~COptimizedOutlineModule((CPathBuffer *)((char *)this + 384));
  *((_QWORD *)this + 1) = &CWidener::`vftable';
  *((_QWORD *)this + 1) = &IMglGeometrySink::`vftable';
}

```

## disassembly

```asm
0x100404f70  mov     [rsp+arg_0], rcx
0x100404f75  push    rbx
0x100404f76  sub     rsp, 30h
0x100404f7a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x100404f83  mov     rbx, rcx
0x100404f86  lea     rax, ??_7CPathBuffer@@6B@; const CPathBuffer::`vftable'
0x100404f8d  mov     [rcx], rax
0x100404f90  add     rcx, 180h; this
0x100404f97  call    ??1COptimizedOutlineModule@@UEAA@XZ; COptimizedOutlineModule::~COptimizedOutlineModule(void)
0x100404f9c  nop
0x100404f9d  lea     rax, [rbx+8]
0x100404fa1  mov     [rsp+38h+arg_8], rax
0x100404fa6  lea     rcx, ??_7CWidener@@6B@; const CWidener::`vftable'
0x100404fad  mov     [rax], rcx
0x100404fb0  lea     rcx, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x100404fb7  mov     [rax], rcx
0x100404fba  add     rsp, 30h
0x100404fbe  pop     rbx
0x100404fbf  retn
```
