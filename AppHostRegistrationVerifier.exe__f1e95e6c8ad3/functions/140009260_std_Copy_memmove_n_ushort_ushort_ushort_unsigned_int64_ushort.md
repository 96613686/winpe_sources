# std::_Copy_memmove_n<ushort *,ushort *>(ushort *,unsigned __int64,ushort *)

- ea: `0x140009260`
- end: `0x14000928e`
- name: `??$_Copy_memmove_n@PEAGPEAG@std@@YAPEAGPEAG_K0@Z`
- size: `46`
- prototype: `__int64 __fastcall(void *Src, __int64, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a934`

## callees

- `0x140002d44`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove_n<unsigned short *,unsigned short *>(void *Src, __int64 a2, void *a3)
{
  __int64 v4; // rbx

  v4 = 2 * a2;
  memmove_0(a3, Src, 2 * a2);
  return (__int64)a3 + v4;
}

```

## disassembly

```asm
0x140009260  mov     [rsp+arg_0], rbx
0x140009265  push    rdi
0x140009266  sub     rsp, 20h
0x14000926a  mov     rdi, r8
0x14000926d  lea     rbx, [rdx+rdx]
0x140009271  mov     rdx, rcx; Src
0x140009274  mov     r8, rbx; Size
0x140009277  mov     rcx, rdi; void *
0x14000927a  call    memmove_0
0x14000927f  lea     rax, [rbx+rdi]
0x140009283  mov     rbx, [rsp+28h+arg_0]
0x140009288  add     rsp, 20h
0x14000928c  pop     rdi
0x14000928d  retn
```
