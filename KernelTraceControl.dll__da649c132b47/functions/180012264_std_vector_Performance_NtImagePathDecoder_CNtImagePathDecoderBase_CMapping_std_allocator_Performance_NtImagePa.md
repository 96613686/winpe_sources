# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::_Insert_n(std::_Vector_iterator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)

- ea: `0x180012264`
- end: `0x1800126bc`
- name: `?_Insert_n@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEAAXV?$_Vector_iterator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@2@_KAEBUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@Z`
- size: `1112`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800126bc`

## callees

- `0x18000252c`
- `0x18000f438`
- `0x18001210c`
- `0x180012204`
- `0x180012264`
- `0x1800132ec`
- `0x180013934`
- `0x18002687c`
- `0x1800268f4`
- `0x180026e30`
- `0x180026f66`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Insert_n(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // rdi
  __int64 v7; // rcx
  __int64 v8; // r9
  unsigned __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  char *v16; // rax
  char *v17; // r14
  __int64 v18; // rax
  __int64 v19; // r13
  __int64 v20; // r9
  __int64 v21; // rdi
  __int64 v22; // rcx
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rbx
  __int64 v26; // rbx
  __int64 v27; // rbx
  __int64 v28; // rcx
  char *v30; // [rsp+30h] [rbp-C8h]
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-B0h] BYREF
  char v32[8]; // [rsp+60h] [rbp-98h] BYREF
  void *v33; // [rsp+68h] [rbp-90h]
  __int64 v34; // [rsp+78h] [rbp-80h]
  unsigned __int64 v35; // [rsp+80h] [rbp-78h]
  char v36[8]; // [rsp+88h] [rbp-70h] BYREF
  void *Block; // [rsp+90h] [rbp-68h]
  __int64 v38; // [rsp+A0h] [rbp-58h]
  unsigned __int64 v39; // [rsp+A8h] [rbp-50h]

  v5 = a2;
  v35 = 7;
  v34 = 0;
  LOWORD(v33) = 0;
  std::wstring::assign(v32, a4, 0, -1);
  v39 = 7;
  v38 = 0;
  LOWORD(Block) = 0;
  std::wstring::assign(v36, a4 + 40, 0, -1);
  v8 = *(_QWORD *)(a1 + 8);
  if ( v8 )
  {
    v7 = *(_QWORD *)(a1 + 24) - v8;
    v9 = v7 / 80;
  }
  else
  {
    v9 = 0;
  }
  if ( v8 )
  {
    v7 = *(_QWORD *)(a1 + 16) - v8;
    v10 = v7 / 80;
  }
  else
  {
    v10 = 0;
  }
  if ( v10 == 0x333333333333333LL )
    std::vector<_GUID>::_Xlen(v7, 0x333333333333333LL, v9);
  if ( v8 )
    v11 = (*(_QWORD *)(a1 + 16) - v8) / 80;
  else
    v11 = 0;
  if ( v9 >= v11 + 1 )
  {
    v23 = *(_QWORD *)(a1 + 16);
    if ( (v23 - v5) / 80 )
    {
      v26 = v23 - 80;
      *(_QWORD *)(a1 + 16) = std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
                               v23 - 80,
                               v23,
                               *(_QWORD *)(a1 + 16));
      while ( v26 != v5 )
      {
        v26 -= 80;
        std::wstring::assign(v26 + 80, v26, 0, -1);
        std::wstring::assign(v26 + 120, v26 + 40, 0, -1);
      }
      v27 = v5 + 80;
      while ( v5 != v27 )
      {
        std::wstring::assign(v5, v32, 0, -1);
        std::wstring::assign(v5 + 40, v36, 0, -1);
        v5 += 80;
      }
    }
    else
    {
      std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
        v5,
        v23,
        v5 + 80);
      try
      {
        std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
          *(_QWORD *)(a1 + 16),
          1 - (*(_QWORD *)(a1 + 16) - v5) / 80,
          v32);
      }
      catch ( ... )
      {
        std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Destroy(
          v24,
          a2 + 80,
          *(_QWORD *)(a1 + 16) + 80LL);
        throw;
      }
      *(_QWORD *)(a1 + 16) += 80LL;
      v25 = *(_QWORD *)(a1 + 16) - 80LL;
      while ( v5 != v25 )
      {
        std::wstring::assign(v5, v32, 0, -1);
        std::wstring::assign(v5 + 40, v36, 0, -1);
        v5 += 80;
      }
    }
  }
  else
  {
    v12 = 0;
    if ( 0x333333333333333LL - (v9 >> 1) >= v9 )
      v12 = v9 + (v9 >> 1);
    if ( v8 )
      v13 = (*(_QWORD *)(a1 + 16) - v8) / 80;
    else
      v13 = 0;
    if ( v12 < v13 + 1 )
    {
      if ( v8 )
        v14 = (*(_QWORD *)(a1 + 16) - v8) / 80;
      else
        v14 = 0;
      v12 = v14 + 1;
    }
    v15 = v12;
    if ( v12 )
    {
      if ( 0xFFFFFFFFFFFFFFFFuLL / v12 < 0x50 )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, 0);
        throw (std::bad_alloc *)pExceptionObject;
      }
    }
    else
    {
      v15 = 0;
    }
    v16 = (char *)operator new(80 * v15);
    v17 = v16;
    v30 = v16;
    try
    {
      v18 = std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
              *(_QWORD *)(a1 + 8),
              v5,
              v16);
      v19 = v18 + 80;
      std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
        v18,
        1,
        v32);
      std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
        v5,
        *(_QWORD *)(a1 + 16),
        v19);
    }
    catch ( ... )
    {
      std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Destroy(v22, v30, v19);
      std::allocator<unsigned int>::deallocate(v28, v30);
      throw;
    }
    v20 = *(_QWORD *)(a1 + 8);
    if ( v20 )
    {
      v22 = *(_QWORD *)(a1 + 16) - v20;
      v21 = v22 / 80;
    }
    else
    {
      v21 = 0;
    }
    if ( v20 )
    {
      std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Destroy(
        v22,
        *(_QWORD *)(a1 + 8),
        *(_QWORD *)(a1 + 16));
      operator delete(*(void **)(a1 + 8));
    }
    *(_QWORD *)(a1 + 24) = &v17[80 * v12];
    *(_QWORD *)(a1 + 16) = &v17[80 * v21 + 80];
    *(_QWORD *)(a1 + 8) = v17;
  }
  if ( v39 >= 8 )
    operator delete(Block);
  v39 = 7;
  v38 = 0;
  LOWORD(Block) = 0;
  if ( v35 >= 8 )
    operator delete(v33);
}

```

## disassembly

```asm
0x180012264  mov     [rsp+arg_8], rdx
0x180012269  mov     r11, rsp
0x18001226c  push    rbx
0x18001226d  push    rsi
0x18001226e  push    rdi
0x18001226f  push    r12
0x180012271  push    r13
0x180012273  push    r14
0x180012275  push    r15
0x180012277  sub     rsp, 0C0h
0x18001227e  mov     [rsp+0F8h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180012287  mov     rax, cs:__security_cookie
0x18001228e  xor     rax, rsp
0x180012291  mov     [rsp+0F8h+var_48], rax
0x180012299  mov     rbx, r9
0x18001229c  mov     rdi, rdx
0x18001229f  mov     rsi, rcx
0x1800122a2  mov     [rsp+0F8h+var_C8], rcx
0x1800122a7  mov     r15d, 7
0x1800122ad  mov     [r11-78h], r15
0x1800122b1  xor     r13d, r13d
0x1800122b4  mov     [r11-80h], r13
0x1800122b8  mov     word ptr [rsp+0F8h+var_90], r13w
0x1800122be  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800122c2  mov     r9, r14
0x1800122c5  xor     r8d, r8d
0x1800122c8  mov     rdx, rbx
0x1800122cb  lea     rcx, [rsp+0F8h+var_98]
0x1800122d0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800122d5  nop
0x1800122d6  mov     [rsp+0F8h+var_50], r15
0x1800122de  mov     [rsp+0F8h+var_58], r13
0x1800122e6  mov     word ptr [rsp+0F8h+Block], r13w
0x1800122ef  lea     rdx, [rbx+28h]
0x1800122f3  mov     r9, r14
0x1800122f6  xor     r8d, r8d
0x1800122f9  lea     rcx, [rsp+0F8h+var_70]
0x180012301  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180012306  nop
0x180012307  mov     r9, [rsi+8]
0x18001230b  mov     r15, 6666666666666667h
0x180012315  test    r9, r9
0x180012318  jnz     short loc_18001231F
0x18001231a  mov     r8d, r13d
0x18001231d  jmp     short loc_18001233D
0x18001231f  mov     rcx, [rsi+18h]
0x180012323  sub     rcx, r9
0x180012326  mov     rax, r15
0x180012329  imul    rcx
0x18001232c  mov     r8, rdx
0x18001232f  sar     r8, 5
0x180012333  mov     rax, r8
0x180012336  shr     rax, 3Fh
0x18001233a  add     r8, rax
0x18001233d  test    r9, r9
0x180012340  jnz     short loc_180012347
0x180012342  mov     rdx, r13
0x180012345  jmp     short loc_180012362
0x180012347  mov     rcx, [rsi+10h]
0x18001234b  sub     rcx, r9
0x18001234e  mov     rax, r15
0x180012351  imul    rcx
0x180012354  sar     rdx, 5
0x180012358  mov     rax, rdx
0x18001235b  shr     rax, 3Fh
0x18001235f  add     rdx, rax
0x180012362  mov     r10, 333333333333333h
0x18001236c  mov     rax, r10
0x18001236f  sub     rax, rdx
0x180012372  mov     r12d, 1
0x180012378  cmp     rax, r12
0x18001237b  jnb     short loc_180012383
0x18001237d  call    ?_Xlen@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@KAXXZ; std::vector<_GUID>::_Xlen(void)
0x180012383  test    r9, r9
0x180012386  jnz     short loc_18001238D
0x180012388  mov     rdx, r13
0x18001238b  jmp     short loc_1800123A8
0x18001238d  mov     rcx, [rsi+10h]
0x180012391  sub     rcx, r9
0x180012394  mov     rax, r15
0x180012397  imul    rcx
0x18001239a  sar     rdx, 5
0x18001239e  mov     rax, rdx
0x1800123a1  shr     rax, 3Fh
0x1800123a5  add     rdx, rax
0x1800123a8  lea     rax, [rdx+1]
0x1800123ac  cmp     r8, rax
0x1800123af  jnb     loc_180012526
0x1800123b5  mov     rax, r8
0x1800123b8  shr     rax, 1
0x1800123bb  sub     r10, rax
0x1800123be  add     rax, r8
0x1800123c1  mov     rbx, r13
0x1800123c4  cmp     r10, r8
0x1800123c7  cmovnb  rbx, rax
0x1800123cb  test    r9, r9
0x1800123ce  jnz     short loc_1800123D5
0x1800123d0  mov     rdx, r13
0x1800123d3  jmp     short loc_1800123F0
0x1800123d5  mov     rcx, [rsi+10h]
0x1800123d9  sub     rcx, r9
0x1800123dc  mov     rax, r15
0x1800123df  imul    rcx
0x1800123e2  sar     rdx, 5
0x1800123e6  mov     rax, rdx
0x1800123e9  shr     rax, 3Fh
0x1800123ed  add     rdx, rax
0x1800123f0  lea     rax, [rdx+1]
0x1800123f4  cmp     rbx, rax
0x1800123f7  jnb     short loc_180012422
0x1800123f9  test    r9, r9
0x1800123fc  jnz     short loc_180012403
0x1800123fe  mov     rdx, r13
0x180012401  jmp     short loc_18001241E
0x180012403  mov     rcx, [rsi+10h]
0x180012407  sub     rcx, r9
0x18001240a  mov     rax, r15
0x18001240d  imul    rcx
0x180012410  sar     rdx, 5
0x180012414  mov     rax, rdx
0x180012417  shr     rax, 3Fh
0x18001241b  add     rdx, rax
0x18001241e  lea     rbx, [rdx+1]
0x180012422  mov     rcx, rbx
0x180012425  test    rbx, rbx
0x180012428  jnz     short loc_18001242F
0x18001242a  mov     rcx, r13
0x18001242d  jmp     short loc_18001245B
0x18001242f  xor     edx, edx
0x180012431  mov     rax, r14
0x180012434  div     rbx
0x180012437  cmp     rax, 50h ; 'P'
0x18001243b  jnb     short loc_18001245B
0x18001243d  xor     edx, edx; char *
0x18001243f  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x180012444  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x180012449  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180012450  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180012455  call    _CxxThrowException_0
0x18001245b  lea     rcx, [rcx+rcx*4]
0x18001245f  shl     rcx, 4; Size
0x180012463  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012468  mov     r14, rax
0x18001246b  mov     [rsp+0F8h+var_C8], rax
0x180012470  mov     [rsp+0F8h+var_C0], rax
0x180012475  mov     r8, rax
0x180012478  mov     rdx, rdi
0x18001247b  mov     rcx, [rsi+8]
0x18001247f  call    ??$_Uninit_copy@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@00AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x180012484  mov     [rsp+0F8h+var_C0], rax
0x180012489  lea     r13, [rax+50h]
0x18001248d  lea     r8, [rsp+0F8h+var_98]
0x180012492  mov     rdx, r12
0x180012495  mov     rcx, rax
0x180012498  call    ??$_Uninit_fill_n@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KU1234@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KAEBU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x18001249d  mov     [rsp+0F8h+var_C0], r13
0x1800124a2  mov     r8, r13
0x1800124a5  mov     rdx, [rsi+10h]
0x1800124a9  mov     rcx, rdi
0x1800124ac  call    ??$_Uninit_copy@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@00AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x1800124b1  nop
0x1800124b2  mov     r9, [rsi+8]
0x1800124b6  xor     r13d, r13d
0x1800124b9  test    r9, r9
0x1800124bc  jnz     short loc_1800124C3
0x1800124be  mov     edi, r13d
0x1800124c1  jmp     short loc_1800124E1
0x1800124c3  mov     rcx, [rsi+10h]
0x1800124c7  sub     rcx, r9
0x1800124ca  mov     rax, r15
0x1800124cd  imul    rcx
0x1800124d0  mov     rdi, rdx
0x1800124d3  sar     rdi, 5
0x1800124d7  mov     rax, rdi
0x1800124da  shr     rax, 3Fh
0x1800124de  add     rdi, rax
0x1800124e1  test    r9, r9
0x1800124e4  jz      short loc_1800124FB
0x1800124e6  mov     r8, [rsi+10h]
0x1800124ea  mov     rdx, r9
0x1800124ed  call    ?_Destroy@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEAAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@0@Z; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Destroy(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)
0x1800124f2  mov     rcx, [rsi+8]; Block
0x1800124f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800124fb  lea     rax, [rbx+rbx*4]
0x1800124ff  shl     rax, 4
0x180012503  add     rax, r14
0x180012506  mov     [rsi+18h], rax
0x18001250a  lea     rax, [rdi+1]
0x18001250e  lea     rax, [rax+rax*4]
0x180012512  shl     rax, 4
0x180012516  add     rax, r14
0x180012519  mov     [rsi+10h], rax
0x18001251d  mov     [rsi+8], r14
0x180012521  jmp     loc_18001264F
0x180012526  mov     r9, [rsi+10h]
0x18001252a  mov     rcx, r9
0x18001252d  sub     rcx, rdi
0x180012530  mov     rax, r15
0x180012533  imul    rcx
0x180012536  sar     rdx, 5
0x18001253a  mov     rax, rdx
0x18001253d  shr     rax, 3Fh
0x180012541  add     rdx, rax
0x180012544  cmp     rdx, r12
0x180012547  mov     rdx, r9
0x18001254a  jnb     loc_1800125D0
0x180012550  lea     r8, [rdi+50h]
0x180012554  mov     rcx, rdi
0x180012557  call    ??$_Uninit_copy@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@00AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x18001255c  nop
0x18001255d  mov     rcx, [rsi+10h]
0x180012561  mov     r8, rcx
0x180012564  sub     r8, rdi
0x180012567  mov     rax, r15
0x18001256a  imul    r8
0x18001256d  sar     rdx, 5
0x180012571  mov     rax, rdx
0x180012574  shr     rax, 3Fh
0x180012578  add     rdx, rax
0x18001257b  sub     r12, rdx
0x18001257e  lea     r8, [rsp+0F8h+var_98]
0x180012583  mov     rdx, r12
0x180012586  call    ??$_Uninit_fill_n@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KU1234@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KAEBU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x18001258b  nop
0x18001258c  add     qword ptr [rsi+10h], 50h ; 'P'
0x180012591  mov     rbx, [rsi+10h]
0x180012595  add     rbx, 0FFFFFFFFFFFFFFB0h
0x180012599  jmp     short loc_1800125C9
0x18001259b  mov     r9, r14
0x18001259e  xor     r8d, r8d
0x1800125a1  lea     rdx, [rsp+0F8h+var_98]
0x1800125a6  mov     rcx, rdi
0x1800125a9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800125ae  lea     rcx, [rdi+28h]
0x1800125b2  mov     r9, r14
0x1800125b5  xor     r8d, r8d
0x1800125b8  lea     rdx, [rsp+0F8h+var_70]
0x1800125c0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800125c5  add     rdi, 50h ; 'P'
0x1800125c9  cmp     rdi, rbx
0x1800125cc  jnz     short loc_18001259B
0x1800125ce  jmp     short loc_18001264F
0x1800125d0  lea     rbx, [r9-50h]
0x1800125d4  mov     r8, r9
0x1800125d7  mov     rcx, rbx
0x1800125da  call    ??$_Uninit_copy@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@00AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x1800125df  mov     [rsi+10h], rax
0x1800125e3  cmp     rdi, rbx
0x1800125e6  jz      short loc_180012616
0x1800125e8  sub     rbx, 50h ; 'P'
0x1800125ec  lea     rcx, [rbx+50h]
0x1800125f0  mov     r9, r14
0x1800125f3  xor     r8d, r8d
0x1800125f6  mov     rdx, rbx
0x1800125f9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800125fe  lea     rdx, [rbx+28h]
0x180012602  lea     rcx, [rbx+78h]
0x180012606  mov     r9, r14
0x180012609  xor     r8d, r8d
0x18001260c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180012611  cmp     rbx, rdi
0x180012614  jnz     short loc_1800125E8
0x180012616  lea     rbx, [rdi+50h]
0x18001261a  jmp     short loc_18001264A
0x18001261c  mov     r9, r14
0x18001261f  xor     r8d, r8d
0x180012622  lea     rdx, [rsp+0F8h+var_98]
0x180012627  mov     rcx, rdi
0x18001262a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001262f  lea     rcx, [rdi+28h]
0x180012633  mov     r9, r14
0x180012636  xor     r8d, r8d
0x180012639  lea     rdx, [rsp+0F8h+var_70]
0x180012641  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180012646  add     rdi, 50h ; 'P'
0x18001264a  cmp     rdi, rbx
0x18001264d  jnz     short loc_18001261C
0x18001264f  cmp     [rsp+0F8h+var_50], 8
0x180012658  jb      short loc_180012667
0x18001265a  mov     rcx, [rsp+0F8h+Block]; Block
0x180012662  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012667  mov     [rsp+0F8h+var_50], 7
0x180012673  mov     [rsp+0F8h+var_58], r13
0x18001267b  mov     word ptr [rsp+0F8h+Block], r13w
0x180012684  cmp     [rsp+0F8h+var_78], 8
0x18001268d  jb      short loc_180012699
0x18001268f  mov     rcx, [rsp+0F8h+var_90]; Block
0x180012694  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012699  mov     rcx, [rsp+0F8h+var_48]
0x1800126a1  xor     rcx, rsp; StackCookie
0x1800126a4  call    __security_check_cookie
0x1800126a9  add     rsp, 0C0h
0x1800126b0  pop     r15
0x1800126b2  pop     r14
0x1800126b4  pop     r13
0x1800126b6  pop     r12
0x1800126b8  pop     rdi
0x1800126b9  pop     rsi
0x1800126ba  pop     rbx
0x1800126bb  retn
  ... truncated ...
```
