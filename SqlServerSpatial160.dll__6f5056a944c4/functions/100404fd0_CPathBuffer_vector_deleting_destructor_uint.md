# CPathBuffer::`vector deleting destructor'(uint)

- ea: `0x100404fd0`
- end: `0x100405041`
- name: `??_ECPathBuffer@@UEAAPEAXI@Z`
- size: `113`
- prototype: `void *__fastcall(CPathBuffer *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x100403b50`
- `0x100404fd0`
- `0x100468a54`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
CPathBuffer *__fastcall CPathBuffer::`vector deleting destructor'(CPathBuffer *this, char a2)
{
  *(_QWORD *)this = &CPathBuffer::`vftable';
  COptimizedOutlineModule::~COptimizedOutlineModule((CPathBuffer *)((char *)this + 384));
  *((_QWORD *)this + 1) = &CWidener::`vftable';
  *((_QWORD *)this + 1) = &IMglGeometrySink::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x100404fd0  mov     [rsp+arg_0], rcx
0x100404fd5  push    rdi
0x100404fd6  sub     rsp, 30h
0x100404fda  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x100404fe3  mov     [rsp+38h+arg_8], rbx
0x100404fe8  mov     ebx, edx
0x100404fea  mov     rdi, rcx
0x100404fed  lea     rax, ??_7CPathBuffer@@6B@
0x100404ff4  mov     [rcx], rax
0x100404ff7  add     rcx, 180h; this
0x100404ffe  call    ??1COptimizedOutlineModule@@UEAA@XZ
0x100405003  nop
0x100405004  lea     rax, [rdi+8]
0x100405008  mov     [rsp+38h+arg_10], rax
0x10040500d  lea     rcx, ??_7CWidener@@6B@
0x100405014  mov     [rax], rcx
0x100405017  lea     rcx, ??_7IMglGeometrySink@@6B@
0x10040501e  mov     [rax], rcx
0x100405021  test    bl, 1
0x100405024  jz      short loc_100405033
0x100405026  mov     edx, 640h; unsigned __int64
0x10040502b  mov     rcx, rdi; void *
0x10040502e  call    ??3@YAXPEAX_K@Z
0x100405033  mov     rax, rdi
0x100405036  mov     rbx, [rsp+38h+arg_8]
0x10040503b  add     rsp, 30h
0x10040503f  pop     rdi
0x100405040  retn
```
