# std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)

- ea: `0x1800119b0`
- end: `0x180011a34`
- name: `??$_Uninit_fill_n@PEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KU1234@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KAEBU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011ab8`
- `0x180011e8c`

## callees

- `0x1800119b0`
- `0x180013934`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_UNKNOWN **__fastcall std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _UNKNOWN **result; // rax
  _QWORD *v6; // rbx
  _QWORD *v7; // rbx
  _UNKNOWN *retaddr; // [rsp+48h] [rbp+0h] BYREF
  _QWORD *v9; // [rsp+50h] [rbp+8h]

  result = &retaddr;
  v9 = a1;
  v6 = a1;
  try
  {
    while ( a2 )
    {
      if ( v6 )
      {
        v6[4] = 7;
        v6[3] = 0;
        *((_WORD *)v6 + 4) = 0;
        result = (_UNKNOWN **)std::wstring::assign(v6, a3, 0, -1);
      }
      --a2;
      v6 += 5;
      v9 = v6;
    }
  }
  catch ( ... )
  {
    if ( a1 != v9 )
    {
      v7 = a1 + 4;
      do
      {
        if ( *v7 >= 8u )
          operator delete((void *)*(v7 - 3));
        *v7 = 7;
        *(v7 - 1) = 0;
        *((_WORD *)v7 - 12) = 0;
        v7 += 5;
      }
      while ( v7 - 4 != v9 );
    }
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x1800119b0  mov     rax, rsp
0x1800119b3  mov     [rax+20h], r9
0x1800119b7  mov     [rax+8], rcx
0x1800119bb  push    rsi
0x1800119bc  push    rdi
0x1800119bd  push    r14
0x1800119bf  sub     rsp, 30h
0x1800119c3  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800119cb  mov     [rax+18h], rbx
0x1800119cf  mov     rsi, r8
0x1800119d2  mov     rdi, rdx
0x1800119d5  mov     rbx, rcx
0x1800119d8  mov     [rsp+48h+arg_18], rcx
0x1800119dd  xor     r14d, r14d
0x1800119e0  test    rdi, rdi
0x1800119e3  jz      short loc_180011A26
0x1800119e5  mov     [rsp+48h+arg_8], rbx
0x1800119ea  mov     [rsp+48h+var_20], rbx
0x1800119ef  test    rbx, rbx
0x1800119f2  jz      short loc_180011A18
0x1800119f4  mov     qword ptr [rbx+20h], 7
0x1800119fc  mov     [rbx+18h], r14
0x180011a00  mov     [rbx+8], r14w
0x180011a05  or      r9, 0FFFFFFFFFFFFFFFFh
0x180011a09  xor     r8d, r8d
0x180011a0c  mov     rdx, rsi
0x180011a0f  mov     rcx, rbx
0x180011a12  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180011a17  nop
0x180011a18  dec     rdi
0x180011a1b  add     rbx, 28h ; '('
0x180011a1f  mov     [rsp+48h+arg_0], rbx
0x180011a24  jmp     short loc_1800119E0
0x180011a26  mov     rbx, [rsp+48h+arg_10]
0x180011a2b  add     rsp, 30h
0x180011a2f  pop     r14
0x180011a31  pop     rdi
0x180011a32  pop     rsi
0x180011a33  retn
```
