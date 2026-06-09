# std::_Uninit_move<HrtfDataDesc *,HrtfDataDesc *,std::allocator<HrtfDataDesc>,HrtfDataDesc>(HrtfDataDesc *,HrtfDataDesc *,HrtfDataDesc *,std::_Wrap_alloc<std::allocator<HrtfDataDesc>> &,HrtfDataDesc *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x1800040f0`
- end: `0x18000419a`
- name: `??$_Uninit_move@PEAUHrtfDataDesc@@PEAU1@V?$allocator@UHrtfDataDesc@@@std@@U1@@std@@YAPEAUHrtfDataDesc@@PEAU1@00AEAU?$_Wrap_alloc@V?$allocator@UHrtfDataDesc@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `170`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007334`

## callees

- `0x1800040f0`

## pseudocode

```c
__int64 __fastcall std::_Uninit_move<HrtfDataDesc *,HrtfDataDesc *,std::allocator<HrtfDataDesc>,HrtfDataDesc>(
        _DWORD *a1,
        _DWORD *a2,
        __int64 a3)
{
  _QWORD *v3; // r9
  _QWORD *v4; // r10

  if ( a1 != a2 )
  {
    v3 = a1 + 2;
    v4 = a1 + 8;
    do
    {
      *(_DWORD *)a3 = *a1;
      *(_QWORD *)(a3 + 8) = 0;
      *(_QWORD *)(a3 + 16) = 0;
      *(_QWORD *)(a3 + 24) = 0;
      *(_QWORD *)(a3 + 8) = *v3;
      *(_QWORD *)(a3 + 16) = v3[1];
      *(_QWORD *)(a3 + 24) = v3[2];
      *v3 = 0;
      v3[1] = 0;
      v3[2] = 0;
      *(_QWORD *)(a3 + 32) = 0;
      *(_QWORD *)(a3 + 40) = 0;
      *(_QWORD *)(a3 + 48) = 0;
      *(_QWORD *)(a3 + 32) = *v4;
      *(_QWORD *)(a3 + 40) = v4[1];
      *(_QWORD *)(a3 + 48) = v4[2];
      *v4 = 0;
      v4[1] = 0;
      v4[2] = 0;
      a3 += 56;
      a1 += 14;
      v3 += 7;
      v4 += 7;
    }
    while ( a1 != a2 );
  }
  return a3;
}

```

## disassembly

```asm
0x1800040f0  mov     [rsp+arg_18], r9
0x1800040f5  mov     [rsp+arg_10], r8
0x1800040fa  sub     rsp, 28h
0x1800040fe  mov     [rsp+28h+arg_18], r8
0x180004103  cmp     rcx, rdx
0x180004106  jz      loc_180004192
0x18000410c  lea     r9, [rcx+8]
0x180004110  lea     r10, [rcx+20h]
0x180004114  xor     r11d, r11d
0x180004117  mov     eax, [rcx]
0x180004119  mov     [r8], eax
0x18000411c  mov     [r8+8], r11
0x180004120  mov     [r8+10h], r11
0x180004124  mov     [r8+18h], r11
0x180004128  mov     rax, [r9]
0x18000412b  mov     [r8+8], rax
0x18000412f  mov     rax, [r9+8]
0x180004133  mov     [r8+10h], rax
0x180004137  mov     rax, [r9+10h]
0x18000413b  mov     [r8+18h], rax
0x18000413f  mov     [r9], r11
0x180004142  mov     [r9+8], r11
0x180004146  mov     [r9+10h], r11
0x18000414a  mov     [r8+20h], r11
0x18000414e  mov     [r8+28h], r11
0x180004152  mov     [r8+30h], r11
0x180004156  mov     rax, [r10]
0x180004159  mov     [r8+20h], rax
0x18000415d  mov     rax, [r10+8]
0x180004161  mov     [r8+28h], rax
0x180004165  mov     rax, [r10+10h]
0x180004169  mov     [r8+30h], rax
0x18000416d  mov     [r10], r11
0x180004170  mov     [r10+8], r11
0x180004174  mov     [r10+10h], r11
0x180004178  add     r8, 38h ; '8'
0x18000417c  mov     [rsp+28h+arg_10], r8
0x180004181  add     rcx, 38h ; '8'
0x180004185  lea     r9, [r9+38h]
0x180004189  lea     r10, [r10+38h]
0x18000418d  cmp     rcx, rdx
0x180004190  jnz     short loc_180004117
0x180004192  mov     rax, r8
0x180004195  add     rsp, 28h
0x180004199  retn
```
