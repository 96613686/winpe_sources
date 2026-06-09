# std::filesystem::filesystem_error::_Pretty_message(std::basic_string_view<char,std::char_traits<char>>,std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x180022590`
- end: `0x18002278c`
- name: `?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z`
- size: `508`
- prototype: `_QWORD *__fastcall(_QWORD *Src, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800215a0`

## callees

- `0x180001eb8`
- `0x1800028f0`
- `0x1800203bc`
- `0x180020700`
- `0x180020930`
- `0x180020cf0`
- `0x1800222c4`
- `0x180022590`
- `0x1800228d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall std::filesystem::filesystem_error::_Pretty_message(_QWORD *Src, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  UINT v8; // r14d
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rcx
  _QWORD *v14; // rax
  _QWORD *v16; // [rsp+30h] [rbp-29h] BYREF
  __int64 v17; // [rsp+38h] [rbp-21h]
  _QWORD *v18; // [rsp+40h] [rbp-19h]
  _QWORD v19[2]; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int64 v20; // [rsp+58h] [rbp-1h]
  _QWORD Srca[3]; // [rsp+68h] [rbp+Fh] BYREF

  v18 = Src;
  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 15;
  *(_BYTE *)Src = 0;
  v8 = _std_fs_code_page(Src);
  if ( a3[3] <= 7u )
    v9 = a3;
  else
    v9 = (_QWORD *)*a3;
  v16 = v9;
  v17 = a3[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    Srca,
    v8,
    (__int64)&v16);
  if ( a4[3] <= 7u )
    v10 = a4;
  else
    v10 = (_QWORD *)*a4;
  v16 = v10;
  v17 = a4[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    v19,
    v8,
    (__int64)&v16);
  v11 = (((unsigned __int128)-(__int128)v20 >> 64) & 4) + 4 + v20 + *(_QWORD *)(a2 + 8) + Srca[2];
  v12 = Src[2];
  if ( v12 <= v11 && Src[3] != v11 )
  {
    if ( Src[3] >= v11 )
    {
      if ( v11 <= 0xF && Src[3] > 0xFu )
        std::string::_Become_small((const void **)Src);
    }
    else
    {
      std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(Src);
      Src[2] = v12;
    }
  }
  std::string::_Append<char>(Src);
  std::string::_Append<char>(Src);
  std::string::_Append<char>(Src);
  if ( v20 )
  {
    std::string::_Append<char>(Src);
    std::string::_Append<char>(Src);
  }
  v13 = Src[2];
  if ( v13 >= Src[3] )
  {
    std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src);
  }
  else
  {
    Src[2] = v13 + 1;
    if ( Src[3] <= 0xFu )
      v14 = Src;
    else
      v14 = (_QWORD *)*Src;
    *(_WORD *)((char *)v14 + v13) = 34;
  }
  std::string::_Tidy_deallocate(v19);
  std::string::_Tidy_deallocate(Srca);
  return Src;
}

```

## disassembly

```asm
0x180022590  mov     [rsp-8+arg_10], rbx
0x180022595  push    rbp
0x180022596  push    rsi
0x180022597  push    rdi
0x180022598  push    r14
0x18002259a  push    r15
0x18002259c  lea     rbp, [rsp-37h]
0x1800225a1  sub     rsp, 90h
0x1800225a8  mov     rax, cs:__security_cookie
0x1800225af  xor     rax, rsp
0x1800225b2  mov     [rbp+57h+var_28], rax
0x1800225b6  mov     rsi, r9
0x1800225b9  mov     rdi, r8
0x1800225bc  mov     r15, rdx
0x1800225bf  mov     rbx, rcx
0x1800225c2  mov     [rbp+57h+var_70], rcx
0x1800225c6  mov     [rbp+57h+var_90], 0
0x1800225cd  xorps   xmm0, xmm0
0x1800225d0  movups  xmmword ptr [rcx], xmm0
0x1800225d3  mov     qword ptr [rcx+10h], 0
0x1800225db  mov     qword ptr [rcx+18h], 0Fh
0x1800225e3  mov     byte ptr [rcx], 0
0x1800225e6  mov     [rbp+57h+var_90], 1
0x1800225ed  call    __std_fs_code_page
0x1800225f2  mov     r14d, eax
0x1800225f5  cmp     qword ptr [rdi+18h], 7
0x1800225fa  jbe     short loc_180022601
0x1800225fc  mov     rax, [rdi]
0x1800225ff  jmp     short loc_180022604
0x180022601  mov     rax, rdi
0x180022604  mov     [rbp+57h+var_80], rax
0x180022608  mov     rax, [rdi+10h]
0x18002260c  mov     [rbp+57h+var_78], rax
0x180022610  lea     r8, [rbp+57h+var_80]
0x180022614  mov     edx, r14d; CodePage
0x180022617  lea     rcx, [rbp+57h+Src]; Src
0x18002261b  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x180022620  nop
0x180022621  cmp     qword ptr [rsi+18h], 7
0x180022626  jbe     short loc_18002262D
0x180022628  mov     rax, [rsi]
0x18002262b  jmp     short loc_180022630
0x18002262d  mov     rax, rsi
0x180022630  mov     [rbp+57h+var_80], rax
0x180022634  mov     rax, [rsi+10h]
0x180022638  mov     [rbp+57h+var_78], rax
0x18002263c  lea     r8, [rbp+57h+var_80]
0x180022640  mov     edx, r14d; CodePage
0x180022643  lea     rcx, [rbp+57h+var_68]; Src
0x180022647  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x18002264c  nop
0x18002264d  mov     rax, [rbp+57h+var_58]
0x180022651  neg     rax
0x180022654  sbb     rdx, rdx
0x180022657  and     edx, 4
0x18002265a  add     rdx, 4
0x18002265e  mov     rsi, [r15+8]
0x180022662  mov     rax, [rbp+57h+var_38]
0x180022666  add     rax, rsi
0x180022669  add     rax, [rbp+57h+var_58]
0x18002266d  add     rax, rdx
0x180022670  mov     rdi, [rbx+10h]
0x180022674  cmp     rdi, rax
0x180022677  ja      short loc_1800226AA
0x180022679  cmp     [rbx+18h], rax
0x18002267d  jz      short loc_1800226AA
0x18002267f  jnb     short loc_180022695
0x180022681  sub     rax, rdi
0x180022684  mov     rdx, rax
0x180022687  mov     rcx, rbx; Src
0x18002268a  call    ??$_Reallocate_grow_by@V_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@$$V@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@@Z; std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(unsigned __int64,_lambda_9013ee9e23efe4882b67eff5b0ecf103_)
0x18002268f  mov     [rbx+10h], rdi
0x180022693  jmp     short loc_1800226AA
0x180022695  cmp     rax, 0Fh
0x180022699  ja      short loc_1800226AA
0x18002269b  cmp     qword ptr [rbx+18h], 0Fh
0x1800226a0  jbe     short loc_1800226AA
0x1800226a2  mov     rcx, rbx
0x1800226a5  call    ?_Become_small@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Become_small(void)
0x1800226aa  mov     r8, rsi
0x1800226ad  mov     rdx, [r15]
0x1800226b0  mov     rcx, rbx; Src
0x1800226b3  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800226b8  mov     r8d, 3
0x1800226be  lea     rdx, asc_180030D48; ": \""
0x1800226c5  mov     rcx, rbx; Src
0x1800226c8  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800226cd  lea     rdx, [rbp+57h+Src]
0x1800226d1  cmp     [rbp+57h+var_30], 0Fh
0x1800226d6  cmova   rdx, [rbp+57h+Src]
0x1800226db  mov     r8, [rbp+57h+var_38]
0x1800226df  mov     rcx, rbx; Src
0x1800226e2  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800226e7  cmp     [rbp+57h+var_58], 0
0x1800226ec  jz      short loc_18002271D
0x1800226ee  mov     r8d, 4
0x1800226f4  lea     rdx, asc_180030D4C; "\", \""
0x1800226fb  mov     rcx, rbx; Src
0x1800226fe  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180022703  lea     rdx, [rbp+57h+var_68]
0x180022707  cmp     [rbp+57h+var_50], 0Fh
0x18002270c  cmova   rdx, [rbp+57h+var_68]
0x180022711  mov     r8, [rbp+57h+var_58]
0x180022715  mov     rcx, rbx; Src
0x180022718  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x18002271d  mov     rcx, [rbx+10h]
0x180022721  cmp     rcx, [rbx+18h]
0x180022725  jnb     short loc_180022746
0x180022727  lea     rax, [rcx+1]
0x18002272b  mov     [rbx+10h], rax
0x18002272f  cmp     qword ptr [rbx+18h], 0Fh
0x180022734  jbe     short loc_18002273B
0x180022736  mov     rax, [rbx]
0x180022739  jmp     short loc_18002273E
0x18002273b  mov     rax, rbx
0x18002273e  mov     word ptr [rcx+rax], 22h ; '"'
0x180022744  jmp     short loc_180022752
0x180022746  mov     r9b, 22h ; '"'
0x180022749  mov     rcx, rbx; Src
0x18002274c  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x180022751  nop
0x180022752  lea     rcx, [rbp+57h+var_68]
0x180022756  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002275b  nop
0x18002275c  lea     rcx, [rbp+57h+Src]
0x180022760  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180022765  mov     rax, rbx
0x180022768  mov     rcx, [rbp+57h+var_28]
0x18002276c  xor     rcx, rsp; StackCookie
0x18002276f  call    __security_check_cookie
0x180022774  mov     rbx, [rsp+0B0h+arg_10]
0x18002277c  add     rsp, 90h
0x180022783  pop     r15
0x180022785  pop     r14
0x180022787  pop     rdi
0x180022788  pop     rsi
0x180022789  pop     rbp
0x18002278a  retn
```
