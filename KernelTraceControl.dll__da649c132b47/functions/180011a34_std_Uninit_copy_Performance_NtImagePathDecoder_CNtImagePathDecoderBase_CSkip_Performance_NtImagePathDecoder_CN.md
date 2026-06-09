# std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)

- ea: `0x180011a34`
- end: `0x180011ab5`
- name: `??$_Uninit_copy@PEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@00AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011ab8`

## callees

- `0x180011a34`
- `0x180013934`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rbx
  _QWORD *v7; // rbx
  _QWORD *v8; // [rsp+70h] [rbp+18h]

  v8 = a3;
  v3 = a3;
  try
  {
    while ( a1 != a2 )
    {
      if ( v3 )
      {
        v3[4] = 7;
        v3[3] = 0;
        *((_WORD *)v3 + 4) = 0;
        std::wstring::assign(v3, a1, 0, -1);
      }
      v3 += 5;
      v8 = v3;
      a1 += 40;
    }
  }
  catch ( ... )
  {
    if ( a3 != v8 )
    {
      v7 = a3 + 4;
      do
      {
        if ( *v7 >= 8u )
          operator delete((void *)*(v7 - 3));
        *v7 = 7;
        *(v7 - 1) = 0;
        *((_WORD *)v7 - 12) = 0;
        v7 += 5;
      }
      while ( v7 - 4 != v8 );
    }
    throw;
  }
  return v3;
}

```

## disassembly

```asm
0x180011a34  mov     [rsp+arg_18], r9
0x180011a39  mov     [rsp+arg_10], r8
0x180011a3e  push    rbx
0x180011a3f  push    rsi
0x180011a40  push    rdi
0x180011a41  push    r14
0x180011a43  sub     rsp, 38h
0x180011a47  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180011a50  mov     rbx, r8
0x180011a53  mov     rsi, rdx
0x180011a56  mov     rdi, rcx
0x180011a59  mov     [rsp+58h+arg_18], rbx
0x180011a5e  xor     r14d, r14d
0x180011a61  cmp     rdi, rsi
0x180011a64  jz      short loc_180011AA8
0x180011a66  mov     [rsp+58h+arg_0], rbx
0x180011a6b  mov     [rsp+58h+arg_8], rbx
0x180011a70  test    rbx, rbx
0x180011a73  jz      short loc_180011A99
0x180011a75  mov     qword ptr [rbx+20h], 7
0x180011a7d  mov     [rbx+18h], r14
0x180011a81  mov     [rbx+8], r14w
0x180011a86  or      r9, 0FFFFFFFFFFFFFFFFh
0x180011a8a  xor     r8d, r8d
0x180011a8d  mov     rdx, rdi
0x180011a90  mov     rcx, rbx
0x180011a93  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180011a98  nop
0x180011a99  add     rbx, 28h ; '('
0x180011a9d  mov     [rsp+58h+arg_10], rbx
0x180011aa2  add     rdi, 28h ; '('
0x180011aa6  jmp     short loc_180011A61
0x180011aa8  mov     rax, rbx
0x180011aab  add     rsp, 38h
0x180011aaf  pop     r14
0x180011ab1  pop     rdi
0x180011ab2  pop     rsi
0x180011ab3  pop     rbx
0x180011ab4  retn
```
