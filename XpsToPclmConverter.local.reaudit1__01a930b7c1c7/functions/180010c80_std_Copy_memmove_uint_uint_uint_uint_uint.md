# std::_Copy_memmove<uint *,uint *>(uint *,uint *,uint *)

- ea: `0x180010c80`
- end: `0x180010cb0`
- name: `??$_Copy_memmove@PEAIPEAI@std@@YAPEAIPEAI00@Z`
- size: `48`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001107c`
- `0x180014630`
- `0x180014670`

## callees

- `0x180007751`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove<unsigned int *,unsigned int *>(void *Src, __int64 a2, void *a3)
{
  __int64 v4; // rbx

  v4 = a2 - (_QWORD)Src;
  memmove_0(a3, Src, a2 - (_QWORD)Src);
  return (__int64)a3 + v4;
}

```

## disassembly

```asm
0x180010c80  mov     [rsp+arg_0], rbx
0x180010c85  push    rdi
0x180010c86  sub     rsp, 20h
0x180010c8a  mov     rbx, rdx
0x180010c8d  mov     rdi, r8
0x180010c90  sub     rbx, rcx
0x180010c93  mov     rdx, rcx; Src
0x180010c96  mov     r8, rbx; Size
0x180010c99  mov     rcx, rdi; void *
0x180010c9c  call    memmove_0
0x180010ca1  lea     rax, [rbx+rdi]
0x180010ca5  mov     rbx, [rsp+28h+arg_0]
0x180010caa  add     rsp, 20h
0x180010cae  pop     rdi
0x180010caf  retn
```
