# LKRhash::CLKRLinearHashTable::_AllocateSegmentDirectory(unsigned __int64)

- ea: `0x18000882c`
- end: `0x18000889e`
- name: `?_AllocateSegmentDirectory@CLKRLinearHashTable@LKRhash@@AEAAQEAVCDirEntry@2@_K@Z`
- size: `114`
- prototype: `struct LKRhash::CDirEntry *__fastcall(LKRhash::CLKRLinearHashTable *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180008bf4`
- `0x180009574`
- `0x18000a330`

## callees

- `0x18000882c`
- `0x18000b010`

## pseudocode

```c
struct LKRhash::CDirEntry *__fastcall LKRhash::CLKRLinearHashTable::_AllocateSegmentDirectory(
        LKRhash::CLKRLinearHashTable *this,
        unsigned __int64 a2)
{
  struct LKRhash::CDirEntry *result; // rax
  unsigned __int64 i; // rcx
  _QWORD *v5; // rdx

  if ( a2 - 8 > 0xFFFF8 )
    return 0;
  result = (struct LKRhash::CDirEntry *)(***((__int64 (__fastcall ****)(_QWORD, __int64, __int64))this + 18))(
                                          *((_QWORD *)this + 18),
                                          8 * a2,
                                          3);
  if ( result )
  {
    for ( i = 0; i < a2; ++i )
    {
      v5 = (_QWORD *)((char *)result + 8 * i);
      if ( v5 )
        *v5 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000882c  push    rbx
0x18000882e  sub     rsp, 20h
0x180008832  lea     rax, [rdx-8]
0x180008836  mov     rbx, rdx
0x180008839  cmp     rax, 0FFFF8h
0x18000883f  ja      short loc_180008896
0x180008841  mov     rcx, [rcx+90h]
0x180008848  lea     rdx, ds:0[rdx*8]
0x180008850  mov     r8d, 3
0x180008856  mov     rax, [rcx]
0x180008859  mov     rax, [rax]
0x18000885c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008861  mov     [rsp+28h+arg_8], rax
0x180008866  test    rax, rax
0x180008869  jz      short loc_180008898
0x18000886b  xor     ecx, ecx
0x18000886d  mov     [rsp+28h+arg_8], rcx
0x180008872  test    rbx, rbx
0x180008875  jz      short loc_180008898
0x180008877  lea     rdx, [rax+rcx*8]
0x18000887b  test    rdx, rdx
0x18000887e  jz      short loc_180008887
0x180008880  mov     qword ptr [rdx], 0
0x180008887  inc     rcx
0x18000888a  mov     [rsp+28h+arg_8], rcx
0x18000888f  cmp     rcx, rbx
0x180008892  jb      short loc_180008877
0x180008894  jmp     short loc_180008898
0x180008896  xor     eax, eax
0x180008898  add     rsp, 20h
0x18000889c  pop     rbx
0x18000889d  retn
```
