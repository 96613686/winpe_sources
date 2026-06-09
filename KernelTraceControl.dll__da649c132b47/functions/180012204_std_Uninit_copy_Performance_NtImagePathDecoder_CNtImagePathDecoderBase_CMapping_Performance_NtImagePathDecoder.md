# std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)

- ea: `0x180012204`
- end: `0x180012264`
- name: `??$_Uninit_copy@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@00AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180012264`

## callees

- `0x180012174`
- `0x180012204`

## pseudocode

```c
__int64 __fastcall std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // rdi
  _QWORD *v7; // rbx
  _QWORD *v8; // [rsp+50h] [rbp+18h]

  v8 = (_QWORD *)a3;
  v3 = a3;
  v5 = a1;
  try
  {
    while ( v5 != a2 )
    {
      std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::construct(a1, v3, v5);
      v3 += 80;
      v8 = (_QWORD *)v3;
      v5 += 80;
    }
  }
  catch ( ... )
  {
    if ( (_QWORD *)a3 != v8 )
    {
      v7 = (_QWORD *)(a3 + 72);
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
      while ( v7 - 9 != v8 );
    }
    throw;
  }
  return v3;
}

```

## disassembly

```asm
0x180012204  mov     rax, rsp
0x180012207  mov     [rax+20h], r9
0x18001220b  mov     [rax+18h], r8
0x18001220f  push    rdi
0x180012210  sub     rsp, 30h
0x180012214  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18001221c  mov     [rax+8], rbx
0x180012220  mov     [rax+10h], rsi
0x180012224  mov     rbx, r8
0x180012227  mov     rsi, rdx
0x18001222a  mov     rdi, rcx
0x18001222d  mov     [rsp+38h+arg_18], rbx
0x180012232  cmp     rdi, rsi
0x180012235  jz      short loc_180012251
0x180012237  mov     r8, rdi
0x18001223a  mov     rdx, rbx
0x18001223d  call    ?construct@?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@QEAAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@AEBU3456@@Z; std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::construct(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)
0x180012242  add     rbx, 50h ; 'P'
0x180012246  mov     [rsp+38h+arg_10], rbx
0x18001224b  add     rdi, 50h ; 'P'
0x18001224f  jmp     short loc_180012232
0x180012251  mov     rax, rbx
0x180012254  mov     rbx, [rsp+38h+arg_0]
0x180012259  mov     rsi, [rsp+38h+arg_8]
0x18001225e  add     rsp, 30h
0x180012262  pop     rdi
0x180012263  retn
```
