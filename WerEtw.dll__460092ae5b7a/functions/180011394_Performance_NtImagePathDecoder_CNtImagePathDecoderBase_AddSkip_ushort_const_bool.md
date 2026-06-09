# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(ushort const *,bool)

- ea: `0x180011394`
- end: `0x180011480`
- name: `?AddSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG_N@Z`
- size: `236`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800127d0`

## callees

- `0x180001870`
- `0x18000b398`
- `0x18000b534`
- `0x18000c1bc`
- `0x18000c6b8`
- `0x18000d074`
- `0x180011394`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(
        Performance::NtImagePathDecoder::CNtImagePathDecoderBase *this,
        const unsigned __int16 *a2)
{
  unsigned __int64 v3; // r8
  unsigned __int64 v4; // rdx
  __int128 *p_Src; // rax
  __int128 *v6; // rcx
  __int128 Src; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int64 v8; // [rsp+30h] [rbp-20h]
  unsigned __int64 v9; // [rsp+38h] [rbp-18h]

  Src = 0;
  v8 = 0;
  v9 = 0;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  std::wstring::_Construct<1,unsigned short const *>(&Src, a2, v3);
  v4 = v8;
  if ( !v8 )
    goto LABEL_7;
  p_Src = &Src;
  if ( v9 > 7 )
    p_Src = (__int128 *)Src;
  if ( *((_WORD *)p_Src + v8 - 1) != 92 )
  {
LABEL_7:
    v6 = &Src;
    if ( v8 >= v9 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&Src);
    }
    else
    {
      ++v8;
      if ( v9 > 7 )
        v6 = (__int128 *)Src;
      *(_DWORD *)((char *)v6 + 2 * v4) = 92;
    }
  }
  if ( *((_QWORD *)this + 4) == *((_QWORD *)this + 5) )
  {
    std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &>(
      (_QWORD *)this + 3,
      *((_QWORD *)this + 4),
      (__int64)&Src);
  }
  else
  {
    std::wstring::wstring(*((_QWORD *)this + 4), (__int64)&Src);
    *((_QWORD *)this + 4) += 32LL;
  }
  std::wstring::~wstring((char **)&Src);
}

```

## disassembly

```asm
0x180011394  mov     [rsp-8+arg_10], rbx
0x180011399  mov     [rsp-8+arg_18], rdi
0x18001139e  push    rbp
0x18001139f  mov     rbp, rsp
0x1800113a2  sub     rsp, 50h
0x1800113a6  mov     rax, cs:__security_cookie
0x1800113ad  xor     rax, rsp
0x1800113b0  mov     [rbp+var_10], rax
0x1800113b4  mov     rbx, rcx
0x1800113b7  xorps   xmm0, xmm0
0x1800113ba  movups  [rbp+Src], xmm0
0x1800113be  xor     edi, edi
0x1800113c0  mov     [rbp+var_20], rdi
0x1800113c4  mov     [rbp+var_18], rdi
0x1800113c8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800113cc  inc     r8
0x1800113cf  cmp     [rdx+r8*2], di
0x1800113d4  jnz     short loc_1800113CC
0x1800113d6  lea     rcx, [rbp+Src]
0x1800113da  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800113df  nop
0x1800113e0  mov     r9d, 5Ch ; '\'
0x1800113e6  mov     r8, [rbp+var_18]
0x1800113ea  mov     rdx, [rbp+var_20]
0x1800113ee  test    rdx, rdx
0x1800113f1  jz      short loc_180011408
0x1800113f3  lea     rax, [rbp+Src]
0x1800113f7  cmp     r8, 7
0x1800113fb  cmova   rax, qword ptr [rbp+Src]
0x180011400  cmp     [rax+rdx*2-2], r9w
0x180011406  jz      short loc_18001142D
0x180011408  lea     rcx, [rbp+Src]; Src
0x18001140c  cmp     rdx, r8
0x18001140f  jnb     short loc_180011428
0x180011411  lea     rax, [rdx+1]
0x180011415  mov     [rbp+var_20], rax
0x180011419  cmp     r8, 7
0x18001141d  cmova   rcx, qword ptr [rbp+Src]
0x180011422  mov     [rcx+rdx*2], r9d
0x180011426  jmp     short loc_18001142D
0x180011428  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18001142d  mov     rax, [rbx+20h]
0x180011431  cmp     rax, [rbx+28h]
0x180011435  jz      short loc_18001144A
0x180011437  lea     rdx, [rbp+Src]
0x18001143b  mov     rcx, rax
0x18001143e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011443  add     qword ptr [rbx+20h], 20h ; ' '
0x180011448  jmp     short loc_18001145B
0x18001144a  lea     r8, [rbp+Src]
0x18001144e  mov     rdx, rax
0x180011451  lea     rcx, [rbx+18h]
0x180011455  call    ??$_Emplace_reallocate@AEBUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &)
0x18001145a  nop
0x18001145b  lea     rcx, [rbp+Src]
0x18001145f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011464  mov     rcx, [rbp+var_10]
0x180011468  xor     rcx, rsp; StackCookie
0x18001146b  call    __security_check_cookie
0x180011470  mov     rbx, [rsp+50h+arg_10]
0x180011475  mov     rdi, [rsp+50h+arg_18]
0x18001147a  add     rsp, 50h
0x18001147e  pop     rbp
0x18001147f  retn
```
