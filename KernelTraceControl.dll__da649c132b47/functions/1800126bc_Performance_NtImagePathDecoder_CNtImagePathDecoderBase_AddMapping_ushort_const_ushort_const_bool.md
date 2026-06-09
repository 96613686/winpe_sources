# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)

- ea: `0x1800126bc`
- end: `0x18001285b`
- name: `?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z`
- size: `415`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001285c`

## callees

- `0x180011fb4`
- `0x18001210c`
- `0x180012264`
- `0x1800126bc`
- `0x180013598`
- `0x1800268f4`
- `0x180026e30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
        Performance::NtImagePathDecoder::CNtImagePathDecoderBase *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4)
{
  _WORD *v7; // rax
  _WORD *p_Block; // rax
  __int64 v9; // r9
  unsigned __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // [rsp+48h] [rbp-29h] BYREF
  void *v14; // [rsp+50h] [rbp-21h] BYREF
  __int64 v15; // [rsp+60h] [rbp-11h]
  unsigned __int64 v16; // [rsp+68h] [rbp-9h]
  __int64 v17; // [rsp+70h] [rbp-1h] BYREF
  void *Block; // [rsp+78h] [rbp+7h] BYREF
  __int64 v19; // [rsp+88h] [rbp+17h]
  unsigned __int64 v20; // [rsp+90h] [rbp+1Fh]

  v16 = 7;
  v15 = 0;
  LOWORD(v14) = 0;
  std::wstring::assign(&v13, a2);
  v20 = 7;
  v19 = 0;
  LOWORD(Block) = 0;
  std::wstring::assign(&v17, a3);
  if ( a4 )
  {
    if ( !v15 )
      goto LABEL_6;
    v7 = &v14;
    if ( v16 >= 8 )
      v7 = v14;
    if ( v7[v15 - 1] != 92 )
LABEL_6:
      std::wstring::push_back(&v13);
    if ( !v19 )
      goto LABEL_11;
    p_Block = &Block;
    if ( v20 >= 8 )
      p_Block = Block;
    if ( p_Block[v19 - 1] != 92 )
LABEL_11:
      std::wstring::push_back(&v17);
  }
  v9 = *((_QWORD *)this + 1);
  if ( v9 )
    v10 = (*((_QWORD *)this + 2) - v9) / 80;
  else
    v10 = 0;
  if ( v9 && v10 < (*((_QWORD *)this + 3) - v9) / 80 )
  {
    v11 = *((_QWORD *)this + 2);
    v12 = v11 + 80;
    std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
      v11,
      1,
      &v13);
    *((_QWORD *)this + 2) = v12;
  }
  else
  {
    std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Insert_n(
      (__int64)this,
      *((_QWORD *)this + 2),
      v10,
      (__int64)&v13);
  }
  if ( v20 >= 8 )
    operator delete(Block);
  v20 = 7;
  v19 = 0;
  LOWORD(Block) = 0;
  if ( v16 >= 8 )
    operator delete(v14);
}

```

## disassembly

```asm
0x1800126bc  mov     rax, rsp
0x1800126bf  push    rbp
0x1800126c0  push    rsi
0x1800126c1  push    rdi
0x1800126c2  push    r14
0x1800126c4  push    r15
0x1800126c6  lea     rbp, [rax-5Fh]
0x1800126ca  sub     rsp, 0A0h
0x1800126d1  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x1800126d9  mov     [rax+20h], rbx
0x1800126dd  mov     rax, cs:__security_cookie
0x1800126e4  xor     rax, rsp
0x1800126e7  mov     [rbp+57h+var_30], rax
0x1800126eb  mov     dil, r9b
0x1800126ee  mov     rbx, r8
0x1800126f1  mov     rsi, rcx
0x1800126f4  mov     r15d, 7
0x1800126fa  mov     [rbp+57h+var_60], r15
0x1800126fe  xor     r14d, r14d
0x180012701  mov     [rbp+57h+var_68], r14
0x180012705  mov     word ptr [rbp+57h+var_78], r14w
0x18001270a  lea     rcx, [rbp+57h+var_80]
0x18001270e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180012713  nop
0x180012714  mov     [rbp+57h+var_38], r15
0x180012718  mov     [rbp+57h+var_40], r14
0x18001271c  mov     word ptr [rbp+57h+Block], r14w
0x180012721  mov     rdx, rbx
0x180012724  lea     rcx, [rbp+57h+var_58]
0x180012728  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001272d  nop
0x18001272e  test    dil, dil
0x180012731  jz      short loc_180012783
0x180012733  mov     rcx, [rbp+57h+var_68]
0x180012737  test    rcx, rcx
0x18001273a  jz      short loc_180012752
0x18001273c  lea     rax, [rbp+57h+var_78]
0x180012740  cmp     [rbp+57h+var_60], 8
0x180012745  cmovnb  rax, [rbp+57h+var_78]
0x18001274a  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180012750  jz      short loc_18001275B
0x180012752  lea     rcx, [rbp+57h+var_80]
0x180012756  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x18001275b  mov     rcx, [rbp+57h+var_40]
0x18001275f  test    rcx, rcx
0x180012762  jz      short loc_18001277A
0x180012764  lea     rax, [rbp+57h+Block]
0x180012768  cmp     [rbp+57h+var_38], 8
0x18001276d  cmovnb  rax, [rbp+57h+Block]
0x180012772  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180012778  jz      short loc_180012783
0x18001277a  lea     rcx, [rbp+57h+var_58]
0x18001277e  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180012783  mov     r9, [rsi+8]
0x180012787  mov     r10, 6666666666666667h
0x180012791  test    r9, r9
0x180012794  jnz     short loc_18001279B
0x180012796  mov     r8, r14
0x180012799  jmp     short loc_1800127B9
0x18001279b  mov     rcx, [rsi+10h]
0x18001279f  sub     rcx, r9
0x1800127a2  mov     rax, r10
0x1800127a5  imul    rcx
0x1800127a8  mov     r8, rdx
0x1800127ab  sar     r8, 5
0x1800127af  mov     rcx, r8
0x1800127b2  shr     rcx, 3Fh
0x1800127b6  add     r8, rcx
0x1800127b9  test    r9, r9
0x1800127bc  jz      short loc_1800127FA
0x1800127be  mov     rcx, [rsi+18h]
0x1800127c2  sub     rcx, r9
0x1800127c5  mov     rax, r10
0x1800127c8  imul    rcx
0x1800127cb  sar     rdx, 5
0x1800127cf  mov     rax, rdx
0x1800127d2  shr     rax, 3Fh
0x1800127d6  add     rdx, rax
0x1800127d9  cmp     r8, rdx
0x1800127dc  jnb     short loc_1800127FA
0x1800127de  mov     rcx, [rsi+10h]
0x1800127e2  lea     rbx, [rcx+50h]
0x1800127e6  lea     r8, [rbp+57h+var_80]
0x1800127ea  mov     edx, 1
0x1800127ef  call    ??$_Uninit_fill_n@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KU1234@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KAEBU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x1800127f4  mov     [rsi+10h], rbx
0x1800127f8  jmp     short loc_18001280B
0x1800127fa  lea     r9, [rbp+57h+var_80]
0x1800127fe  mov     rdx, [rsi+10h]
0x180012802  mov     rcx, rsi
0x180012805  call    ?_Insert_n@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEAAXV?$_Vector_iterator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@2@_KAEBUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@Z; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Insert_n(std::_Vector_iterator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)
0x18001280a  nop
0x18001280b  cmp     [rbp+57h+var_38], 8
0x180012810  jb      short loc_18001281B
0x180012812  mov     rcx, [rbp+57h+Block]; Block
0x180012816  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001281b  mov     [rbp+57h+var_38], r15
0x18001281f  mov     [rbp+57h+var_40], r14
0x180012823  mov     word ptr [rbp+57h+Block], r14w
0x180012828  cmp     [rbp+57h+var_60], 8
0x18001282d  jb      short loc_180012838
0x18001282f  mov     rcx, [rbp+57h+var_78]; Block
0x180012833  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012838  mov     rcx, [rbp+57h+var_30]
0x18001283c  xor     rcx, rsp; StackCookie
0x18001283f  call    __security_check_cookie
0x180012844  mov     rbx, [rsp+0C0h+arg_18]
0x18001284c  add     rsp, 0A0h
0x180012853  pop     r15
0x180012855  pop     r14
0x180012857  pop     rdi
0x180012858  pop     rsi
0x180012859  pop     rbp
0x18001285a  retn
```
