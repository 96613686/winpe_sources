# std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)

- ea: `0x18001210c`
- end: `0x180012168`
- name: `??$_Uninit_fill_n@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KU1234@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KAEBU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180012264`
- `0x1800126bc`

## callees

- `0x18001210c`
- `0x180012174`

## pseudocode

```c
_UNKNOWN **__fastcall std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _UNKNOWN **result; // rax
  __int64 v6; // rbx
  _QWORD *v7; // rbx
  _UNKNOWN *retaddr; // [rsp+38h] [rbp+0h] BYREF
  _QWORD *v9; // [rsp+40h] [rbp+8h]

  result = &retaddr;
  v9 = (_QWORD *)a1;
  v6 = a1;
  try
  {
    while ( a2 )
    {
      result = std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::construct(a1, v6, a3);
      --a2;
      v6 += 80;
      v9 = (_QWORD *)v6;
    }
  }
  catch ( ... )
  {
    if ( (_QWORD *)a1 != v9 )
    {
      v7 = (_QWORD *)(a1 + 72);
      do
      {
        if ( *v7 >= 8u )
          operator delete((void *)*(v7 - 3));
        *v7 = 7;
        *(v7 - 1) = 0;
        *((_WORD *)v7 - 12) = 0;
        if ( *(v7 - 5) >= 8u )
          operator delete((void *)*(v7 - 8));
        *(v7 - 5) = 7;
        *(v7 - 6) = 0;
        *((_WORD *)v7 - 32) = 0;
        v7 += 10;
      }
      while ( v7 - 9 != v9 );
    }
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18001210c  mov     rax, rsp
0x18001210f  mov     [rax+20h], r9
0x180012113  mov     [rax+8], rcx
0x180012117  push    rdi
0x180012118  sub     rsp, 30h
0x18001211c  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x180012124  mov     [rax+10h], rbx
0x180012128  mov     [rax+18h], rsi
0x18001212c  mov     rsi, r8
0x18001212f  mov     rdi, rdx
0x180012132  mov     rbx, rcx
0x180012135  mov     [rsp+38h+arg_18], rcx
0x18001213a  test    rdi, rdi
0x18001213d  jz      short loc_180012158
0x18001213f  mov     r8, rsi
0x180012142  mov     rdx, rbx
0x180012145  call    ?construct@?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@QEAAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@AEBU3456@@Z; std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::construct(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)
0x18001214a  dec     rdi
0x18001214d  add     rbx, 50h ; 'P'
0x180012151  mov     [rsp+38h+arg_0], rbx
0x180012156  jmp     short loc_18001213A
0x180012158  mov     rbx, [rsp+38h+arg_8]
0x18001215d  mov     rsi, [rsp+38h+arg_10]
0x180012162  add     rsp, 30h
0x180012166  pop     rdi
0x180012167  retn
```
