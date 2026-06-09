# CPathSimpleBuffer::`vector deleting destructor'(uint)

- ea: `0x100405190`
- end: `0x100405201`
- name: `??_ECPathSimpleBuffer@@UEAAPEAXI@Z`
- size: `113`
- prototype: `void *__fastcall(CPathSimpleBuffer *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x100403b50`
- `0x100405190`
- `0x100468a54`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
CPathSimpleBuffer *__fastcall CPathSimpleBuffer::`vector deleting destructor'(CPathSimpleBuffer *this, char a2)
{
  *(_QWORD *)this = &CPathSimpleBuffer::`vftable';
  COptimizedOutlineModule::~COptimizedOutlineModule((CPathSimpleBuffer *)((char *)this + 416));
  *((_QWORD *)this + 1) = &CSimpleWidener::`vftable';
  *((_QWORD *)this + 1) = &IMglGeometrySink::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x100405190  mov     [rsp+arg_0], rcx
0x100405195  push    rdi
0x100405196  sub     rsp, 30h
0x10040519a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1004051a3  mov     [rsp+38h+arg_8], rbx
0x1004051a8  mov     ebx, edx
0x1004051aa  mov     rdi, rcx
0x1004051ad  lea     rax, ??_7CPathSimpleBuffer@@6B@
0x1004051b4  mov     [rcx], rax
0x1004051b7  add     rcx, 1A0h; this
0x1004051be  call    ??1COptimizedOutlineModule@@UEAA@XZ
0x1004051c3  nop
0x1004051c4  lea     rax, [rdi+8]
0x1004051c8  mov     [rsp+38h+arg_10], rax
0x1004051cd  lea     rcx, ??_7CSimpleWidener@@6B@
0x1004051d4  mov     [rax], rcx
0x1004051d7  lea     rcx, ??_7IMglGeometrySink@@6B@
0x1004051de  mov     [rax], rcx
0x1004051e1  test    bl, 1
0x1004051e4  jz      short loc_1004051F3
0x1004051e6  mov     edx, 660h; unsigned __int64
0x1004051eb  mov     rcx, rdi; void *
0x1004051ee  call    ??3@YAXPEAX_K@Z
0x1004051f3  mov     rax, rdi
0x1004051f6  mov     rbx, [rsp+38h+arg_8]
0x1004051fb  add     rsp, 30h
0x1004051ff  pop     rdi
0x100405200  retn
```
