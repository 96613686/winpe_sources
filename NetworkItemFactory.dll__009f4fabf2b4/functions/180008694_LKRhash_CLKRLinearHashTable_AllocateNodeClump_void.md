# LKRhash::CLKRLinearHashTable::_AllocateNodeClump(void)

- ea: `0x180008694`
- end: `0x1800086e8`
- name: `?_AllocateNodeClump@CLKRLinearHashTable@LKRhash@@AEAAQEAVCNodeClump@2@XZ`
- size: `84`
- prototype: `struct LKRhash::CNodeClump *__fastcall(LKRhash::CLKRLinearHashTable *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180008bf4`
- `0x180009574`
- `0x18000a018`

## callees

- `0x180008694`
- `0x18000b010`

## pseudocode

```c
struct LKRhash::CNodeClump *__fastcall LKRhash::CLKRLinearHashTable::_AllocateNodeClump(
        LKRhash::CLKRLinearHashTable *this)
{
  struct LKRhash::CNodeClump *result; // rax
  __int64 i; // rcx

  result = (struct LKRhash::CNodeClump *)(***((__int64 (__fastcall ****)(_QWORD, __int64, __int64))this + 18))(
                                           *((_QWORD *)this + 18),
                                           56,
                                           4);
  if ( result )
  {
    *((_QWORD *)result + 2) = 0;
    for ( i = 3; i != -1; --i )
    {
      *((_DWORD *)result + i) = 31678523;
      *((_QWORD *)result + i + 3) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008694  sub     rsp, 28h
0x180008698  mov     rcx, [rcx+90h]
0x18000869f  mov     edx, 38h ; '8'
0x1800086a4  mov     rax, [rcx]
0x1800086a7  lea     r8d, [rdx-34h]
0x1800086ab  mov     rax, [rax]
0x1800086ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086b3  mov     [rsp+28h+arg_0], rax
0x1800086b8  test    rax, rax
0x1800086bb  jz      short loc_1800086E3
0x1800086bd  mov     qword ptr [rax+10h], 0
0x1800086c5  mov     ecx, 3
0x1800086ca  mov     dword ptr [rax+rcx*4], 1E3603Bh
0x1800086d1  mov     qword ptr [rax+rcx*8+18h], 0
0x1800086da  dec     rcx
0x1800086dd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800086e1  jnz     short loc_1800086CA
0x1800086e3  add     rsp, 28h
0x1800086e7  retn
```
