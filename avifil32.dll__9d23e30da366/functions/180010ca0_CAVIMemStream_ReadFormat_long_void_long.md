# CAVIMemStream::ReadFormat(long,void *,long *)

- ea: `0x180010ca0`
- end: `0x180010ce0`
- name: `?ReadFormat@CAVIMemStream@@UEAAJJPEAXPEAJ@Z`
- size: `64`
- prototype: `int(CAVIMemStream *__hidden this, int, void *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180010ca0`
- `0x180017365`

## pseudocode

```c
__int64 __fastcall CAVIMemStream::ReadFormat(const void **this, __int64 a2, void *a3, int *a4)
{
  int *v4; // rbx
  int v6; // eax

  v4 = (int *)(this + 4);
  if ( a3 )
  {
    v6 = *a4;
    if ( *a4 >= *v4 )
      v6 = *v4;
    memmove_0(a3, this[3], v6);
  }
  *a4 = *v4;
  return 0;
}

```

## disassembly

```asm
0x180010ca0  mov     [rsp+arg_0], rbx
0x180010ca5  push    rdi
0x180010ca6  sub     rsp, 20h
0x180010caa  lea     rbx, [rcx+20h]
0x180010cae  mov     rdi, r9
0x180010cb1  mov     r9, r8
0x180010cb4  test    r8, r8
0x180010cb7  jz      short loc_180010CCF
0x180010cb9  mov     eax, [rdi]
0x180010cbb  cmp     eax, [rbx]
0x180010cbd  mov     rdx, [rcx+18h]; Src
0x180010cc1  mov     rcx, r9; void *
0x180010cc4  cmovge  eax, [rbx]
0x180010cc7  movsxd  r8, eax; Size
0x180010cca  call    memmove_0
0x180010ccf  mov     eax, [rbx]
0x180010cd1  mov     rbx, [rsp+28h+arg_0]
0x180010cd6  mov     [rdi], eax
0x180010cd8  xor     eax, eax
0x180010cda  add     rsp, 20h
0x180010cde  pop     rdi
0x180010cdf  retn
```
