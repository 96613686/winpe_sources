# std::_Uninit_copy<_GUID *,_GUID *,std::allocator<_GUID>>(_GUID *,_GUID *,_GUID *,std::allocator<_GUID> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)

- ea: `0x18001beb8`
- end: `0x18001bee9`
- name: `??$_Uninit_copy@PEAU_GUID@@PEAU1@V?$allocator@U_GUID@@@std@@@std@@YAPEAU_GUID@@PEAU1@00AEAV?$allocator@U_GUID@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001beec`

## callees

- `0x18001beb8`

## pseudocode

```c
_OWORD *__fastcall std::_Uninit_copy<_GUID *,_GUID *,std::allocator<_GUID>>(_OWORD *a1, _OWORD *a2, _OWORD *a3)
{
  try
  {
    while ( a1 != a2 )
    {
      if ( a3 )
        *a3 = *a1;
      ++a3;
      ++a1;
    }
  }
  catch ( ... )
  {
    throw;
  }
  return a3;
}

```

## disassembly

```asm
0x18001beb8  sub     rsp, 38h
0x18001bebc  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001bec5  jmp     short loc_18001BEDC
0x18001bec7  test    r8, r8
0x18001beca  jz      short loc_18001BED4
0x18001becc  movups  xmm0, xmmword ptr [rcx]
0x18001becf  movdqu  xmmword ptr [r8], xmm0
0x18001bed4  add     r8, 10h
0x18001bed8  add     rcx, 10h
0x18001bedc  cmp     rcx, rdx
0x18001bedf  jnz     short loc_18001BEC7
0x18001bee1  mov     rax, r8
0x18001bee4  add     rsp, 38h
0x18001bee8  retn
```
