# CPathSimpleBuffer::~CPathSimpleBuffer(void)

- ea: `0x100405130`
- end: `0x100405180`
- name: `??1CPathSimpleBuffer@@UEAA@XZ`
- size: `80`
- prototype: `void __fastcall(CPathSimpleBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10046fa3e`

## callees

- `0x100403b50`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CPathSimpleBuffer::~CPathSimpleBuffer(CPathSimpleBuffer *this)
{
  *(_QWORD *)this = &CPathSimpleBuffer::`vftable';
  COptimizedOutlineModule::~COptimizedOutlineModule((CPathSimpleBuffer *)((char *)this + 416));
  *((_QWORD *)this + 1) = &CSimpleWidener::`vftable';
  *((_QWORD *)this + 1) = &IMglGeometrySink::`vftable';
}

```

## disassembly

```asm
0x100405130  mov     [rsp+arg_0], rcx
0x100405135  push    rbx
0x100405136  sub     rsp, 30h
0x10040513a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x100405143  mov     rbx, rcx
0x100405146  lea     rax, ??_7CPathSimpleBuffer@@6B@; const CPathSimpleBuffer::`vftable'
0x10040514d  mov     [rcx], rax
0x100405150  add     rcx, 1A0h; this
0x100405157  call    ??1COptimizedOutlineModule@@UEAA@XZ; COptimizedOutlineModule::~COptimizedOutlineModule(void)
0x10040515c  nop
0x10040515d  lea     rax, [rbx+8]
0x100405161  mov     [rsp+38h+arg_8], rax
0x100405166  lea     rcx, ??_7CSimpleWidener@@6B@; const CSimpleWidener::`vftable'
0x10040516d  mov     [rax], rcx
0x100405170  lea     rcx, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x100405177  mov     [rax], rcx
0x10040517a  add     rsp, 30h
0x10040517e  pop     rbx
0x10040517f  retn
```
