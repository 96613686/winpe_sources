# CAVICmpStream::CS::ReadData(ulong,void *,long *)

- ea: `0x18000de10`
- end: `0x18000de7a`
- name: `?ReadData@CS@CAVICmpStream@@UEAAJKPEAXPEAJ@Z`
- size: `106`
- prototype: `int(CAVICmpStream::CS *__hidden this, unsigned int, void *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000de10`
- `0x180017365`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CAVICmpStream::CS::ReadData(CAVICmpStream::CS *this, int a2, void *a3, int *a4)
{
  __int64 v4; // rbx
  int v6; // ecx
  int v7; // eax

  v4 = *((_QWORD *)this + 1);
  if ( a2 != 1685222515 )
    return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 256) + 88LL))(*(_QWORD *)(v4 + 256));
  v6 = *(_DWORD *)(v4 + 368);
  if ( v6 )
  {
    v7 = *a4;
    if ( *a4 >= v6 )
      v7 = *(_DWORD *)(v4 + 368);
    memmove_0(a3, *(const void **)(v4 + 360), v7);
  }
  *a4 = *(_DWORD *)(v4 + 368);
  return 0;
}

```

## disassembly

```asm
0x18000de10  mov     [rsp+arg_0], rbx
0x18000de15  push    rdi
0x18000de16  sub     rsp, 30h
0x18000de1a  mov     rbx, [rcx+8]
0x18000de1e  mov     rdi, r9
0x18000de21  mov     r10, r8
0x18000de24  cmp     edx, 64727473h
0x18000de2a  jnz     short loc_18000DE5C
0x18000de2c  mov     ecx, [rbx+170h]
0x18000de32  test    ecx, ecx
0x18000de34  jz      short loc_18000DE50
0x18000de36  mov     eax, [r9]
0x18000de39  cmp     eax, ecx
0x18000de3b  mov     rdx, [rbx+168h]; Src
0x18000de42  cmovge  eax, ecx
0x18000de45  mov     rcx, r10; void *
0x18000de48  movsxd  r8, eax; Size
0x18000de4b  call    memmove_0
0x18000de50  mov     eax, [rbx+170h]
0x18000de56  mov     [rdi], eax
0x18000de58  xor     eax, eax
0x18000de5a  jmp     short loc_18000DE6F
0x18000de5c  mov     rcx, [rbx+100h]
0x18000de63  mov     rax, [rcx]
0x18000de66  mov     rax, [rax+58h]
0x18000de6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de6f  mov     rbx, [rsp+38h+arg_0]
0x18000de74  add     rsp, 30h
0x18000de78  pop     rdi
0x18000de79  retn
```
