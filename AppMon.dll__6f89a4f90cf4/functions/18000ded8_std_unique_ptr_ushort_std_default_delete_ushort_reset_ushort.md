# std::unique_ptr<ushort,std::default_delete<ushort>>::reset(ushort *)

- ea: `0x18000ded8`
- end: `0x18000def9`
- name: `?reset@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAXPEAG@Z`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000bafc`

## callees

- `0x1800019f0`
- `0x18000ded8`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short>::reset(void **a1, void *a2)
{
  void *v2; // rax

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
    operator delete(v2);
}

```

## disassembly

```asm
0x18000ded8  sub     rsp, 28h
0x18000dedc  mov     rax, [rcx]
0x18000dedf  mov     [rcx], rdx
0x18000dee2  test    rax, rax
0x18000dee5  jz      short loc_18000DEF4
0x18000dee7  mov     edx, 2; unsigned __int64
0x18000deec  mov     rcx, rax; void *
0x18000deef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000def4  add     rsp, 28h
0x18000def8  retn
```
