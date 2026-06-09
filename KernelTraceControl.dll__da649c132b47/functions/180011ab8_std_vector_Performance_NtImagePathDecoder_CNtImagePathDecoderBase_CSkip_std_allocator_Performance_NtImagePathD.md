# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::_Insert_n(std::_Vector_iterator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &)

- ea: `0x180011ab8`
- end: `0x180011e8b`
- name: `?_Insert_n@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEAAXV?$_Vector_iterator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@2@_KAEBUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180011e8c`

## callees

- `0x18000252c`
- `0x18000f438`
- `0x1800119b0`
- `0x180011a34`
- `0x180011ab8`
- `0x180013934`
- `0x18002687c`
- `0x1800268f4`
- `0x180026e30`
- `0x180026f66`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Insert_n(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rbx
  __int64 v6; // rcx
  __int64 v7; // r8
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rdx
  unsigned __int64 v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  char *v15; // rax
  char *v16; // r15
  __int64 v17; // rax
  __int64 v18; // r14
  __int64 v19; // rcx
  _QWORD *v20; // rbx
  __int64 v21; // r14
  _QWORD *v22; // r12
  _QWORD *v23; // rbx
  __int64 v24; // r14
  __int64 v25; // rcx
  __int64 v26; // rdi
  __int64 v27; // rsi
  __int64 v28; // rdi
  __int64 v29; // rcx
  char *v31; // [rsp+30h] [rbp-98h]
  __int64 v32; // [rsp+38h] [rbp-90h]
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-80h] BYREF
  char v34[8]; // [rsp+60h] [rbp-68h] BYREF
  void *Block; // [rsp+68h] [rbp-60h]
  __int64 v36; // [rsp+78h] [rbp-50h]
  unsigned __int64 v37; // [rsp+80h] [rbp-48h]

  v4 = a2;
  v37 = 7;
  v36 = 0;
  LOWORD(Block) = 0;
  std::wstring::assign(v34, a4, 0, -1);
  v7 = *(_QWORD *)(a1 + 8);
  if ( v7 )
  {
    v6 = *(_QWORD *)(a1 + 24) - v7;
    v8 = v6 / 40;
  }
  else
  {
    v8 = 0;
  }
  if ( v7 )
  {
    v6 = *(_QWORD *)(a1 + 16) - v7;
    v9 = v6 / 40;
  }
  else
  {
    v9 = 0;
  }
  if ( v9 == 0x666666666666666LL )
    std::vector<_GUID>::_Xlen(v6, 0x666666666666666LL, v7);
  if ( v7 )
    v10 = (*(_QWORD *)(a1 + 16) - v7) / 40;
  else
    v10 = 0;
  if ( v8 >= v10 + 1 )
  {
    v24 = *(_QWORD *)(a1 + 16);
    if ( (v24 - v4) / 40 )
    {
      v27 = v24 - 40;
      *(_QWORD *)(a1 + 16) = std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(
                               v24 - 40,
                               v24,
                               *(_QWORD *)(a1 + 16));
      while ( v27 != v4 )
      {
        v27 -= 40;
        std::wstring::assign(v27 + 40, v27, 0, -1);
      }
      v28 = v4 + 40;
      while ( v4 != v28 )
      {
        std::wstring::assign(v4, v34, 0, -1);
        v4 += 40;
      }
    }
    else
    {
      std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(
        v4,
        v24,
        v4 + 40);
      try
      {
        std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(
          *(_QWORD *)(a1 + 16),
          1 - (*(_QWORD *)(a1 + 16) - v4) / 40,
          v34);
      }
      catch ( ... )
      {
        std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Destroy(
          v25,
          a2 + 40,
          *(_QWORD *)(a1 + 16) + 40LL);
        throw;
      }
      *(_QWORD *)(a1 + 16) += 40LL;
      v26 = *(_QWORD *)(a1 + 16) - 40LL;
      while ( v4 != v26 )
      {
        std::wstring::assign(v4, v34, 0, -1);
        v4 += 40;
      }
    }
  }
  else
  {
    v11 = 0;
    if ( 0x666666666666666LL - (v8 >> 1) >= v8 )
      v11 = v8 + (v8 >> 1);
    if ( v7 )
      v12 = (*(_QWORD *)(a1 + 16) - v7) / 40;
    else
      v12 = 0;
    if ( v11 < v12 + 1 )
    {
      if ( v7 )
        v13 = (*(_QWORD *)(a1 + 16) - v7) / 40;
      else
        v13 = 0;
      v11 = v13 + 1;
    }
    v14 = v11;
    if ( v11 )
    {
      if ( 0xFFFFFFFFFFFFFFFFuLL / v11 < 0x28 )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, 0);
        throw (std::bad_alloc *)pExceptionObject;
      }
    }
    else
    {
      v14 = 0;
    }
    v15 = (char *)operator new(40 * v14);
    v16 = v15;
    v31 = v15;
    try
    {
      v17 = std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(
              *(_QWORD *)(a1 + 8),
              v4,
              v15);
      v18 = v17 + 40;
      std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(
        v17,
        1,
        v34);
      v32 = v18;
      std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(
        v4,
        *(_QWORD *)(a1 + 16),
        v18);
    }
    catch ( ... )
    {
      std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Destroy(v19, v31, v32);
      std::allocator<unsigned int>::deallocate(v29, v31);
      throw;
    }
    v20 = *(_QWORD **)(a1 + 8);
    if ( v20 )
      v21 = (*(_QWORD *)(a1 + 16) - (_QWORD)v20) / 40LL;
    else
      v21 = 0;
    if ( v20 )
    {
      v22 = *(_QWORD **)(a1 + 16);
      if ( v20 != v22 )
      {
        v23 = v20 + 4;
        do
        {
          if ( *v23 >= 8u )
            operator delete((void *)*(v23 - 3));
          *v23 = 7;
          *(v23 - 1) = 0;
          *((_WORD *)v23 - 12) = 0;
          v23 += 5;
        }
        while ( v23 - 4 != v22 );
      }
      operator delete(*(void **)(a1 + 8));
    }
    *(_QWORD *)(a1 + 24) = &v16[40 * v11];
    *(_QWORD *)(a1 + 16) = &v16[40 * v21 + 40];
    *(_QWORD *)(a1 + 8) = v16;
  }
  if ( v37 >= 8 )
    operator delete(Block);
}

```

## disassembly

```asm
0x180011ab8  mov     [rsp+arg_8], rdx
0x180011abd  mov     r11, rsp
0x180011ac0  push    rbx
0x180011ac1  push    rsi
0x180011ac2  push    rdi
0x180011ac3  push    r12
0x180011ac5  push    r13
0x180011ac7  push    r14
0x180011ac9  push    r15
0x180011acb  sub     rsp, 90h
0x180011ad2  mov     [rsp+0C8h+var_88], 0FFFFFFFFFFFFFFFEh
0x180011adb  mov     rax, cs:__security_cookie
0x180011ae2  xor     rax, rsp
0x180011ae5  mov     [rsp+0C8h+var_40], rax
0x180011aed  mov     rax, r9
0x180011af0  mov     rbx, rdx
0x180011af3  mov     rdi, rcx
0x180011af6  mov     [rsp+0C8h+var_98], rcx
0x180011afb  mov     qword ptr [r11-48h], 7
0x180011b03  xor     r14d, r14d
0x180011b06  mov     [r11-50h], r14
0x180011b0a  mov     [r11-60h], r14w
0x180011b0f  or      r15, 0FFFFFFFFFFFFFFFFh
0x180011b13  mov     r9, r15
0x180011b16  xor     r8d, r8d
0x180011b19  mov     rdx, rax
0x180011b1c  lea     rcx, [r11-68h]
0x180011b20  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180011b25  nop
0x180011b26  mov     r8, [rdi+8]
0x180011b2a  mov     r12, 6666666666666667h
0x180011b34  test    r8, r8
0x180011b37  jnz     short loc_180011B3E
0x180011b39  mov     r9d, r14d
0x180011b3c  jmp     short loc_180011B5C
0x180011b3e  mov     rcx, [rdi+18h]
0x180011b42  sub     rcx, r8
0x180011b45  mov     rax, r12
0x180011b48  imul    rcx
0x180011b4b  mov     r9, rdx
0x180011b4e  sar     r9, 4
0x180011b52  mov     rax, r9
0x180011b55  shr     rax, 3Fh
0x180011b59  add     r9, rax
0x180011b5c  test    r8, r8
0x180011b5f  jnz     short loc_180011B66
0x180011b61  mov     rdx, r14
0x180011b64  jmp     short loc_180011B81
0x180011b66  mov     rcx, [rdi+10h]
0x180011b6a  sub     rcx, r8
0x180011b6d  mov     rax, r12
0x180011b70  imul    rcx
0x180011b73  sar     rdx, 4
0x180011b77  mov     rax, rdx
0x180011b7a  shr     rax, 3Fh
0x180011b7e  add     rdx, rax
0x180011b81  mov     r10, 666666666666666h
0x180011b8b  mov     rax, r10
0x180011b8e  sub     rax, rdx
0x180011b91  mov     r13d, 1
0x180011b97  cmp     rax, r13
0x180011b9a  jnb     short loc_180011BA2
0x180011b9c  call    ?_Xlen@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@KAXXZ; std::vector<_GUID>::_Xlen(void)
0x180011ba2  test    r8, r8
0x180011ba5  jnz     short loc_180011BAC
0x180011ba7  mov     rdx, r14
0x180011baa  jmp     short loc_180011BC7
0x180011bac  mov     rcx, [rdi+10h]
0x180011bb0  sub     rcx, r8
0x180011bb3  mov     rax, r12
0x180011bb6  imul    rcx
0x180011bb9  sar     rdx, 4
0x180011bbd  mov     rax, rdx
0x180011bc0  shr     rax, 3Fh
0x180011bc4  add     rdx, rax
0x180011bc7  lea     rax, [rdx+1]
0x180011bcb  cmp     r9, rax
0x180011bce  jnb     loc_180011D6C
0x180011bd4  mov     rax, r9
0x180011bd7  shr     rax, 1
0x180011bda  sub     r10, rax
0x180011bdd  add     rax, r9
0x180011be0  mov     rsi, r14
0x180011be3  cmp     r10, r9
0x180011be6  cmovnb  rsi, rax
0x180011bea  test    r8, r8
0x180011bed  jnz     short loc_180011BF4
0x180011bef  mov     rdx, r14
0x180011bf2  jmp     short loc_180011C0F
0x180011bf4  mov     rcx, [rdi+10h]
0x180011bf8  sub     rcx, r8
0x180011bfb  mov     rax, r12
0x180011bfe  imul    rcx
0x180011c01  sar     rdx, 4
0x180011c05  mov     rax, rdx
0x180011c08  shr     rax, 3Fh
0x180011c0c  add     rdx, rax
0x180011c0f  lea     rax, [rdx+1]
0x180011c13  cmp     rsi, rax
0x180011c16  jnb     short loc_180011C41
0x180011c18  test    r8, r8
0x180011c1b  jnz     short loc_180011C22
0x180011c1d  mov     rdx, r14
0x180011c20  jmp     short loc_180011C3D
0x180011c22  mov     rcx, [rdi+10h]
0x180011c26  sub     rcx, r8
0x180011c29  mov     rax, r12
0x180011c2c  imul    rcx
0x180011c2f  sar     rdx, 4
0x180011c33  mov     rax, rdx
0x180011c36  shr     rax, 3Fh
0x180011c3a  add     rdx, rax
0x180011c3d  lea     rsi, [rdx+1]
0x180011c41  mov     rcx, rsi
0x180011c44  test    rsi, rsi
0x180011c47  jnz     short loc_180011C4E
0x180011c49  mov     rcx, r14
0x180011c4c  jmp     short loc_180011C7A
0x180011c4e  xor     edx, edx
0x180011c50  mov     rax, r15
0x180011c53  div     rsi
0x180011c56  cmp     rax, 28h ; '('
0x180011c5a  jnb     short loc_180011C7A
0x180011c5c  xor     edx, edx; char *
0x180011c5e  lea     rcx, [rsp+0C8h+pExceptionObject]; this
0x180011c63  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x180011c68  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180011c6f  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180011c74  call    _CxxThrowException_0
0x180011c7a  lea     rcx, [rcx+rcx*4]
0x180011c7e  shl     rcx, 3; Size
0x180011c82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011c87  mov     r15, rax
0x180011c8a  mov     [rsp+0C8h+var_98], rax
0x180011c8f  mov     [rsp+0C8h+var_90], rax
0x180011c94  mov     r8, rax
0x180011c97  mov     rdx, rbx
0x180011c9a  mov     rcx, [rdi+8]
0x180011c9e  call    ??$_Uninit_copy@PEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@00AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x180011ca3  mov     [rsp+0C8h+var_90], rax
0x180011ca8  lea     r14, [rax+28h]
0x180011cac  lea     r8, [rsp+0C8h+var_68]
0x180011cb1  mov     rdx, r13
0x180011cb4  mov     rcx, rax
0x180011cb7  call    ??$_Uninit_fill_n@PEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KU1234@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KAEBU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x180011cbc  mov     [rsp+0C8h+var_90], r14
0x180011cc1  mov     r8, r14
0x180011cc4  mov     rdx, [rdi+10h]
0x180011cc8  mov     rcx, rbx
0x180011ccb  call    ??$_Uninit_copy@PEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@00AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x180011cd0  nop
0x180011cd1  mov     rbx, [rdi+8]
0x180011cd5  xor     r13d, r13d
0x180011cd8  test    rbx, rbx
0x180011cdb  jnz     short loc_180011CE2
0x180011cdd  mov     r14d, r13d
0x180011ce0  jmp     short loc_180011D00
0x180011ce2  mov     rcx, [rdi+10h]
0x180011ce6  sub     rcx, rbx
0x180011ce9  mov     rax, r12
0x180011cec  imul    rcx
0x180011cef  mov     r14, rdx
0x180011cf2  sar     r14, 4
0x180011cf6  mov     rax, r14
0x180011cf9  shr     rax, 3Fh
0x180011cfd  add     r14, rax
0x180011d00  test    rbx, rbx
0x180011d03  jz      short loc_180011D47
0x180011d05  mov     r12, [rdi+10h]
0x180011d09  cmp     rbx, r12
0x180011d0c  jz      short loc_180011D3E
0x180011d0e  add     rbx, 20h ; ' '
0x180011d12  cmp     qword ptr [rbx], 8
0x180011d16  jb      short loc_180011D21
0x180011d18  mov     rcx, [rbx-18h]; Block
0x180011d1c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011d21  mov     qword ptr [rbx], 7
0x180011d28  mov     [rbx-8], r13
0x180011d2c  mov     [rbx-18h], r13w
0x180011d31  add     rbx, 28h ; '('
0x180011d35  lea     rax, [rbx-20h]
0x180011d39  cmp     rax, r12
0x180011d3c  jnz     short loc_180011D12
0x180011d3e  mov     rcx, [rdi+8]; Block
0x180011d42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011d47  lea     rax, [rsi+rsi*4]
0x180011d4b  lea     rcx, [r15+rax*8]
0x180011d4f  mov     [rdi+18h], rcx
0x180011d53  lea     rax, [r14+1]
0x180011d57  lea     rax, [rax+rax*4]
0x180011d5b  lea     rcx, [r15+rax*8]
0x180011d5f  mov     [rdi+10h], rcx
0x180011d63  mov     [rdi+8], r15
0x180011d67  jmp     loc_180011E53
0x180011d6c  mov     r14, [rdi+10h]
0x180011d70  mov     rcx, r14
0x180011d73  sub     rcx, rbx
0x180011d76  mov     rax, r12
0x180011d79  imul    rcx
0x180011d7c  sar     rdx, 4
0x180011d80  mov     rax, rdx
0x180011d83  shr     rax, 3Fh
0x180011d87  add     rdx, rax
0x180011d8a  cmp     rdx, r13
0x180011d8d  mov     rdx, r14
0x180011d90  jnb     short loc_180011DFB
0x180011d92  lea     r8, [rbx+28h]
0x180011d96  mov     rcx, rbx
0x180011d99  call    ??$_Uninit_copy@PEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@00AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x180011d9e  nop
0x180011d9f  mov     rcx, [rdi+10h]
0x180011da3  mov     r8, rcx
0x180011da6  sub     r8, rbx
0x180011da9  mov     rax, r12
0x180011dac  imul    r8
0x180011daf  sar     rdx, 4
0x180011db3  mov     rax, rdx
0x180011db6  shr     rax, 3Fh
0x180011dba  add     rdx, rax
0x180011dbd  sub     r13, rdx
0x180011dc0  lea     r8, [rsp+0C8h+var_68]
0x180011dc5  mov     rdx, r13
0x180011dc8  call    ??$_Uninit_fill_n@PEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KU1234@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@_KAEBU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_fill_n<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,unsigned __int64,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x180011dcd  nop
0x180011dce  add     qword ptr [rdi+10h], 28h ; '('
0x180011dd3  mov     rdi, [rdi+10h]
0x180011dd7  add     rdi, 0FFFFFFFFFFFFFFD8h
0x180011ddb  jmp     short loc_180011DF4
0x180011ddd  mov     r9, r15
0x180011de0  xor     r8d, r8d
0x180011de3  lea     rdx, [rsp+0C8h+var_68]
0x180011de8  mov     rcx, rbx
0x180011deb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180011df0  add     rbx, 28h ; '('
0x180011df4  cmp     rbx, rdi
0x180011df7  jnz     short loc_180011DDD
0x180011df9  jmp     short loc_180011E53
0x180011dfb  lea     rsi, [r14-28h]
0x180011dff  mov     r8, r14
0x180011e02  mov     rcx, rsi
0x180011e05  call    ??$_Uninit_copy@PEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@PEAU1234@00AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_copy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x180011e0a  mov     [rdi+10h], rax
0x180011e0e  cmp     rbx, rsi
0x180011e11  jz      short loc_180011E31
0x180011e13  sub     r14, rsi
0x180011e16  sub     rsi, 28h ; '('
0x180011e1a  lea     rcx, [rsi+r14]
0x180011e1e  mov     r9, r15
0x180011e21  xor     r8d, r8d
0x180011e24  mov     rdx, rsi
0x180011e27  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180011e2c  cmp     rsi, rbx
0x180011e2f  jnz     short loc_180011E16
0x180011e31  lea     rdi, [rbx+28h]
0x180011e35  jmp     short loc_180011E4E
0x180011e37  mov     r9, r15
0x180011e3a  xor     r8d, r8d
0x180011e3d  lea     rdx, [rsp+0C8h+var_68]
0x180011e42  mov     rcx, rbx
0x180011e45  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180011e4a  add     rbx, 28h ; '('
0x180011e4e  cmp     rbx, rdi
0x180011e51  jnz     short loc_180011E37
0x180011e53  cmp     [rsp+0C8h+var_48], 8
0x180011e5c  jb      short loc_180011E68
0x180011e5e  mov     rcx, [rsp+0C8h+Block]; Block
0x180011e63  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011e68  mov     rcx, [rsp+0C8h+var_40]
0x180011e70  xor     rcx, rsp; StackCookie
0x180011e73  call    __security_check_cookie
0x180011e78  add     rsp, 90h
0x180011e7f  pop     r15
0x180011e81  pop     r14
0x180011e83  pop     r13
0x180011e85  pop     r12
0x180011e87  pop     rdi
0x180011e88  pop     rsi
0x180011e89  pop     rbx
0x180011e8a  retn
```
