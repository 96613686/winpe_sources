# LKRhash::CLKRLinearHashTable::_FreeSegment(LKRhash::CSegment *)

- ea: `0x180009af0`
- end: `0x180009b4b`
- name: `?_FreeSegment@CLKRLinearHashTable@LKRhash@@AEBA_NPEAVCSegment@2@@Z`
- size: `91`
- prototype: `bool __fastcall(LKRhash::CLKRLinearHashTable *__hidden this, struct LKRhash::CSegment *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800089a4`
- `0x180008bf4`
- `0x18000a330`

## callees

- `0x180009af0`
- `0x18000b010`

## pseudocode

```c
char __fastcall LKRhash::CLKRLinearHashTable::_FreeSegment(
        LKRhash::CLKRLinearHashTable *this,
        struct LKRhash::CSegment *a2)
{
  __int64 v2; // r8

  if ( *((_DWORD *)this + 16) == 1 )
  {
    (*(void (__fastcall **)(_QWORD, struct LKRhash::CSegment *, _QWORD, struct LKRhash::CSegment *))(**((_QWORD **)this + 18) + 8LL))(
      *((_QWORD *)this + 18),
      a2,
      0,
      a2);
  }
  else
  {
    if ( *((_DWORD *)this + 16) == 3 )
      v2 = 2;
    else
      v2 = 1;
    (*(void (__fastcall **)(_QWORD, struct LKRhash::CSegment *, __int64, struct LKRhash::CSegment *))(**((_QWORD **)this + 18) + 8LL))(
      *((_QWORD *)this + 18),
      a2,
      v2,
      a2);
  }
  return 1;
}

```

## disassembly

```asm
0x180009af0  sub     rsp, 28h
0x180009af4  mov     r8d, [rcx+40h]
0x180009af8  mov     r9, rdx
0x180009afb  sub     r8d, 1
0x180009aff  jz      short loc_180009B2B
0x180009b01  sub     r8d, 1
0x180009b05  jz      short loc_180009B23
0x180009b07  cmp     r8d, 1
0x180009b0b  jnz     short loc_180009B23
0x180009b0d  mov     r8d, 2
0x180009b13  mov     rcx, [rcx+90h]
0x180009b1a  mov     rax, [rcx]
0x180009b1d  mov     rax, [rax+8]
0x180009b21  jmp     short loc_180009B3F
0x180009b23  mov     r8d, 1
0x180009b29  jmp     short loc_180009B13
0x180009b2b  mov     rcx, [rcx+90h]
0x180009b32  xor     r8d, r8d
0x180009b35  mov     rdx, [rcx]
0x180009b38  mov     rax, [rdx+8]
0x180009b3c  mov     rdx, r9
0x180009b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b44  mov     al, 1
0x180009b46  add     rsp, 28h
0x180009b4a  retn
```
