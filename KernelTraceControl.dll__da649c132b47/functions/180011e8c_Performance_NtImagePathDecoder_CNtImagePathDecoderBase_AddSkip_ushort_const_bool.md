# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(ushort const *,bool)

- ea: `0x180011e8c`
- end: `0x180011fb3`
- name: `?AddSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG_N@Z`
- size: `295`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001285c`

## callees

- `0x1800119b0`
- `0x180011ab8`
- `0x180011e8c`
- `0x180011fb4`
- `0x180013598`
- `0x1800268f4`
- `0x180026e30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(
        Performance::NtImagePathDecoder::CNtImagePathDecoderBase *this,
        const unsigned __int16 *a2)
{
  _WORD *p_Block; // rax
  __int64 v4; // r8
  unsigned __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // [rsp+38h] [rbp-38h] BYREF
  void *Block; // [rsp+40h] [rbp-30h] BYREF
  __int64 v10; // [rsp+50h] [rbp-20h]
  unsigned __int64 v11; // [rsp+58h] [rbp-18h]

  v11 = 7;
  v10 = 0;
  LOWORD(Block) = 0;
  std::wstring::assign(&v8, a2);
  if ( !v10 )
    goto LABEL_5;
  p_Block = &Block;
  if ( v11 >= 8 )
    p_Block = Block;
  if ( p_Block[v10 - 1] != 92 )
LABEL_5:
    std::wstring::push_back(&v8);
  v4 = *((_QWORD *)this + 5);
  if ( v4 )
    v5 = (*((_QWORD *)this + 6) - v4) / 40;
  else
    v5 = 0;
  if ( v4 && v5 < (*((_QWORD *)this + 7) - v4) / 40 )
  {
    v6 = *((_QWORD *)this + 6);
    v7 = v6 + 40;
    std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(
      v6,
      1,
      &v8);
    *((_QWORD *)this + 6) = v7;
  }
  else
  {
    std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Insert_n(
      (__int64)this + 32,
      *((_QWORD *)this + 6),
      v4,
      (__int64)&v8);
  }
  if ( v11 >= 8 )
    operator delete(Block);
}

```

## disassembly

```asm
0x180011e8c  mov     rax, rsp
0x180011e8f  push    rbp
0x180011e90  mov     rbp, rsp
0x180011e93  sub     rsp, 70h
0x180011e97  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x180011e9f  mov     [rax+18h], rbx
0x180011ea3  mov     [rax+20h], rdi
0x180011ea7  mov     rax, cs:__security_cookie
0x180011eae  xor     rax, rsp
0x180011eb1  mov     [rbp+var_10], rax
0x180011eb5  mov     rdi, rcx
0x180011eb8  mov     [rbp+var_18], 7
0x180011ec0  xor     ebx, ebx
0x180011ec2  mov     [rbp+var_20], rbx
0x180011ec6  mov     word ptr [rbp+Block], bx
0x180011eca  lea     rcx, [rbp+var_38]
0x180011ece  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180011ed3  nop
0x180011ed4  mov     rcx, [rbp+var_20]
0x180011ed8  test    rcx, rcx
0x180011edb  jz      short loc_180011EF3
0x180011edd  lea     rax, [rbp+Block]
0x180011ee1  cmp     [rbp+var_18], 8
0x180011ee6  cmovnb  rax, [rbp+Block]
0x180011eeb  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180011ef1  jz      short loc_180011EFC
0x180011ef3  lea     rcx, [rbp+var_38]
0x180011ef7  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180011efc  mov     r8, [rdi+28h]
0x180011f00  mov     r10, 6666666666666667h
0x180011f0a  test    r8, r8
0x180011f0d  jnz     short loc_180011F14
0x180011f0f  mov     r9, rbx
0x180011f12  jmp     short loc_180011F32
0x180011f14  mov     rcx, [rdi+30h]
0x180011f18  sub     rcx, r8
0x180011f1b  mov     rax, r10
0x180011f1e  imul    rcx
0x180011f21  mov     r9, rdx
0x180011f24  sar     r9, 4
0x180011f28  mov     rcx, r9
0x180011f2b  shr     rcx, 3Fh
0x180011f2f  add     r9, rcx
0x180011f32  test    r8, r8
0x180011f35  jz      short loc_180011F73
0x180011f37  mov     rcx, [rdi+38h]
0x180011f3b  sub     rcx, r8
0x180011f3e  mov     rax, r10
0x180011f41  imul    rcx
0x180011f44  sar     rdx, 4
0x180011f48  mov     rax, rdx
0x180011f4b  shr     rax, 3Fh
0x180011f4f  add     rdx, rax
0x180011f52  cmp     r9, rdx
0x180011f55  jnb     short loc_180011F73
0x180011f57  mov     rcx, [rdi+30h]
0x180011f5b  lea     rbx, [rcx+28h]
0x180011f5f  lea     r8, [rbp+var_38]
0x180011f63  mov     edx, 1
0x180011f68  call    ??$_Uninit_fill_n@PEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KU1234@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KAEBU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x180011f6d  mov     [rdi+30h], rbx
0x180011f71  jmp     short loc_180011F85
0x180011f73  lea     r9, [rbp+var_38]
0x180011f77  mov     rdx, [rdi+30h]
0x180011f7b  lea     rcx, [rdi+20h]
0x180011f7f  call    ?_Insert_n@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEAAXV?$_Vector_iterator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@2@_KAEBUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@Z; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Insert_n(std::_Vector_iterator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &)
0x180011f84  nop
0x180011f85  cmp     [rbp+var_18], 8
0x180011f8a  jb      short loc_180011F95
0x180011f8c  mov     rcx, [rbp+Block]; Block
0x180011f90  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011f95  mov     rcx, [rbp+var_10]
0x180011f99  xor     rcx, rsp; StackCookie
0x180011f9c  call    __security_check_cookie
0x180011fa1  lea     r11, [rsp+70h+var_s0]
0x180011fa6  mov     rbx, [r11+20h]
0x180011faa  mov     rdi, [r11+28h]
0x180011fae  mov     rsp, r11
0x180011fb1  pop     rbp
0x180011fb2  retn
```
