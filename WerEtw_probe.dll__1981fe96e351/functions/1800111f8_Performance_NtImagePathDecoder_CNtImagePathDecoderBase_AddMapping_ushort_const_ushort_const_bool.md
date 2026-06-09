# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)

- ea: `0x1800111f8`
- end: `0x18001138e`
- name: `?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z`
- size: `406`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800127d0`
- `0x180013890`

## callees

- `0x180001870`
- `0x18000b398`
- `0x18000b534`
- `0x18000bf98`
- `0x18000c6b8`
- `0x18000d074`
- `0x1800111f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
        Performance::NtImagePathDecoder::CNtImagePathDecoderBase *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4)
{
  __int64 v7; // rbx
  __int64 v8; // r8
  unsigned __int64 v9; // rdx
  __int128 *p_Src; // rax
  __int128 *v11; // rcx
  unsigned __int64 v12; // rdx
  __int128 *v13; // rax
  __int128 *v14; // rcx
  __int64 v15; // rbx
  __int128 Src; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 v17; // [rsp+40h] [rbp-40h]
  unsigned __int64 v18; // [rsp+48h] [rbp-38h]
  __int128 v19; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v20; // [rsp+60h] [rbp-20h]
  unsigned __int64 v21; // [rsp+68h] [rbp-18h]

  Src = 0;
  v17 = 0;
  v18 = 0;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  std::wstring::_Construct<1,unsigned short const *>(&Src, a2);
  v19 = 0;
  v20 = 0;
  v21 = 0;
  do
    ++v7;
  while ( a3[v7] );
  std::wstring::_Construct<1,unsigned short const *>(&v19, a3);
  if ( a4 )
  {
    v9 = v17;
    if ( !v17 )
      goto LABEL_10;
    p_Src = &Src;
    if ( v18 > 7 )
      p_Src = (__int128 *)Src;
    if ( *((_WORD *)p_Src + v17 - 1) != 92 )
    {
LABEL_10:
      v11 = &Src;
      if ( v17 >= v18 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&Src);
      }
      else
      {
        ++v17;
        if ( v18 > 7 )
          v11 = (__int128 *)Src;
        *(_DWORD *)((char *)v11 + 2 * v9) = 92;
      }
    }
    v12 = v20;
    if ( !v20 )
      goto LABEL_19;
    v13 = &v19;
    if ( v21 > 7 )
      v13 = (__int128 *)v19;
    if ( *((_WORD *)v13 + v20 - 1) != 92 )
    {
LABEL_19:
      v14 = &v19;
      if ( v20 >= v21 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&v19);
      }
      else
      {
        ++v20;
        if ( v21 > 7 )
          v14 = (__int128 *)v19;
        *(_DWORD *)((char *)v14 + 2 * v12) = 92;
      }
    }
  }
  v15 = *((_QWORD *)this + 1);
  if ( v15 == *((_QWORD *)this + 2) )
  {
    std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(
      this,
      *((_QWORD *)this + 1),
      (__int64)&Src);
  }
  else
  {
    std::wstring::wstring(v15, &Src);
    std::wstring::wstring(v15 + 32, &v19);
    *((_QWORD *)this + 1) += 64LL;
  }
  std::wstring::~wstring(&v19);
  std::wstring::~wstring(&Src);
}

```

## disassembly

```asm
0x1800111f8  mov     [rsp-28h+arg_18], rbx
0x1800111fd  push    rbp
0x1800111fe  push    rsi
0x1800111ff  push    rdi
0x180011200  push    r14
0x180011202  push    r15
0x180011204  mov     rbp, rsp
0x180011207  sub     rsp, 80h
0x18001120e  mov     rax, cs:__security_cookie
0x180011215  xor     rax, rsp
0x180011218  mov     [rbp+var_10], rax
0x18001121c  mov     r14b, r9b
0x18001121f  mov     rsi, r8
0x180011222  mov     rdi, rcx
0x180011225  xorps   xmm0, xmm0
0x180011228  movups  [rbp+Src], xmm0
0x18001122c  xor     r15d, r15d
0x18001122f  mov     [rbp+var_40], r15
0x180011233  mov     [rbp+var_38], r15
0x180011237  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001123b  mov     r8, rbx
0x18001123e  inc     r8
0x180011241  cmp     [rdx+r8*2], r15w
0x180011246  jnz     short loc_18001123E
0x180011248  lea     rcx, [rbp+Src]
0x18001124c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011251  nop
0x180011252  xorps   xmm0, xmm0
0x180011255  movups  [rbp+var_30], xmm0
0x180011259  mov     [rbp+var_20], r15
0x18001125d  mov     [rbp+var_18], r15
0x180011261  inc     rbx
0x180011264  cmp     [rsi+rbx*2], r15w
0x180011269  jnz     short loc_180011261
0x18001126b  mov     r8, rbx
0x18001126e  mov     rdx, rsi
0x180011271  lea     rcx, [rbp+var_30]
0x180011275  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001127a  nop
0x18001127b  test    r14b, r14b
0x18001127e  jz      loc_180011319
0x180011284  mov     ebx, 5Ch ; '\'
0x180011289  mov     r8, [rbp+var_38]
0x18001128d  mov     rdx, [rbp+var_40]
0x180011291  test    rdx, rdx
0x180011294  jz      short loc_1800112AA
0x180011296  lea     rax, [rbp+Src]
0x18001129a  cmp     r8, 7
0x18001129e  cmova   rax, qword ptr [rbp+Src]
0x1800112a3  cmp     [rax+rdx*2-2], bx
0x1800112a8  jz      short loc_1800112D1
0x1800112aa  lea     rcx, [rbp+Src]; Src
0x1800112ae  cmp     rdx, r8
0x1800112b1  jnb     short loc_1800112C9
0x1800112b3  lea     rax, [rdx+1]
0x1800112b7  mov     [rbp+var_40], rax
0x1800112bb  cmp     r8, 7
0x1800112bf  cmova   rcx, qword ptr [rbp+Src]
0x1800112c4  mov     [rcx+rdx*2], ebx
0x1800112c7  jmp     short loc_1800112D1
0x1800112c9  mov     r9d, ebx
0x1800112cc  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800112d1  mov     r8, [rbp+var_18]
0x1800112d5  mov     rdx, [rbp+var_20]
0x1800112d9  test    rdx, rdx
0x1800112dc  jz      short loc_1800112F2
0x1800112de  lea     rax, [rbp+var_30]
0x1800112e2  cmp     r8, 7
0x1800112e6  cmova   rax, qword ptr [rbp+var_30]
0x1800112eb  cmp     [rax+rdx*2-2], bx
0x1800112f0  jz      short loc_180011319
0x1800112f2  lea     rcx, [rbp+var_30]; Src
0x1800112f6  cmp     rdx, r8
0x1800112f9  jnb     short loc_180011311
0x1800112fb  lea     rax, [rdx+1]
0x1800112ff  mov     [rbp+var_20], rax
0x180011303  cmp     r8, 7
0x180011307  cmova   rcx, qword ptr [rbp+var_30]
0x18001130c  mov     [rcx+rdx*2], ebx
0x18001130f  jmp     short loc_180011319
0x180011311  mov     r9d, ebx
0x180011314  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180011319  mov     rbx, [rdi+8]
0x18001131d  cmp     rbx, [rdi+10h]
0x180011321  jz      short loc_180011349
0x180011323  mov     [rbp+var_60], rbx
0x180011327  lea     rdx, [rbp+Src]
0x18001132b  mov     rcx, rbx
0x18001132e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011333  nop
0x180011334  lea     rcx, [rbx+20h]
0x180011338  lea     rdx, [rbp+var_30]
0x18001133c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011341  nop
0x180011342  add     qword ptr [rdi+8], 40h ; '@'
0x180011347  jmp     short loc_180011359
0x180011349  lea     r8, [rbp+Src]
0x18001134d  mov     rdx, rbx
0x180011350  mov     rcx, rdi
0x180011353  call    ??$_Emplace_reallocate@AEBUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)
0x180011358  nop
0x180011359  lea     rcx, [rbp+var_30]
0x18001135d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011362  lea     rcx, [rbp+Src]
0x180011366  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001136b  mov     rcx, [rbp+var_10]
0x18001136f  xor     rcx, rsp; StackCookie
0x180011372  call    __security_check_cookie
0x180011377  mov     rbx, [rsp+80h+arg_18]
0x18001137f  add     rsp, 80h
0x180011386  pop     r15
0x180011388  pop     r14
0x18001138a  pop     rdi
0x18001138b  pop     rsi
0x18001138c  pop     rbp
0x18001138d  retn
```
