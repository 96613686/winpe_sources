# px_ippsMalloc_8u

- ea: `0x180011040`
- end: `0x180011069`
- name: `px_ippsMalloc_8u`
- size: `41`
- prototype: ``
- caller_count: `54`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d210`
- `0x18000d370`
- `0x18000d54c`
- `0x18000d8d0`
- `0x18000d9c0`
- `0x18000dd90`
- `0x18000df70`
- `0x18000e0cc`
- `0x18000e3c0`
- `0x18000e560`
- `0x18000e760`
- `0x18000eaf0`
- `0x18000ebe0`
- `0x18000efb0`
- `0x18000f1d0`
- `0x18000f364`
- `0x18000f680`
- `0x18000f820`
- `0x18000fa20`
- `0x18000fdb0`
- `0x18000fea0`
- `0x180010270`
- `0x180010490`
- `0x180010624`
- `0x180047aa0`
- `0x180047c40`
- `0x180047f10`
- `0x180048120`
- `0x1800483c0`
- `0x1800486b0`
- `0x180048910`
- `0x180048ab0`
- `0x180048d70`
- `0x180048f80`
- `0x180049220`
- `0x180049510`
- `0x1800496a0`
- `0x180049840`
- `0x180049b00`
- `0x180049d10`
- `0x180049fb0`
- `0x18004a2a0`
- `0x18004aad4`
- `0x18004ad34`
- `0x18004f898`
- `0x1800532cc`
- `0x18005335c`
- `0x18005372c`
- `0x180053c34`
- `0x180055260`

## callees

- `0x18000abfc`
- `0x180011040`

## pseudocode

```c
_QWORD *__fastcall px_ippsMalloc_8u(int a1)
{
  _QWORD *result; // rax
  _QWORD *v2; // rcx

  result = operator new(a1 + 40LL);
  v2 = result;
  if ( result )
  {
    result = (_QWORD *)(((unsigned __int64)result + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(result - 1) = v2;
  }
  return result;
}

```

## disassembly

```asm
0x180011040  sub     rsp, 28h
0x180011044  movsxd  rcx, ecx
0x180011047  add     rcx, 28h ; '('; Size
0x18001104b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011050  mov     rcx, rax
0x180011053  test    rax, rax
0x180011056  jz      short loc_180011064
0x180011058  add     rax, 27h ; '''
0x18001105c  and     rax, 0FFFFFFFFFFFFFFE0h
0x180011060  mov     [rax-8], rcx
0x180011064  add     rsp, 28h
0x180011068  retn
```
