# std::filesystem::filesystem_error::_Pretty_message(std::basic_string_view<char,std::char_traits<char>>,std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x180023838`
- end: `0x180023a3a`
- name: `?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z`
- size: `514`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180022830`

## callees

- `0x180001e50`
- `0x180002880`
- `0x180021960`
- `0x180021e2c`
- `0x1800223ec`
- `0x180023560`
- `0x180023838`
- `0x180023b80`
- `0x180023c0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall std::filesystem::filesystem_error::_Pretty_message(_QWORD *Src, __int64 a2)
{
  UINT v4; // r14d
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rcx
  _QWORD *v8; // rax
  _QWORD v10[2]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v11; // [rsp+50h] [rbp-9h]
  _QWORD Srca[3]; // [rsp+60h] [rbp+7h] BYREF

  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[2] = 0;
  Src[3] = 15;
  *(_BYTE *)Src = 0;
  v4 = _std_fs_code_page();
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(Srca, v4);
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(v10, v4);
  v5 = v11 + Srca[2] + *(_QWORD *)(a2 + 8) + (v11 != 0 ? 8LL : 4LL);
  v6 = Src[2];
  if ( v6 <= v5 && Src[3] != v5 )
  {
    if ( Src[3] >= v5 )
    {
      if ( v5 <= 0xF && Src[3] > 0xFu )
        std::string::_Become_small(Src);
    }
    else
    {
      std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(Src);
      Src[2] = v6;
    }
  }
  std::string::append(Src);
  std::string::append(Src);
  std::string::append(Src);
  if ( v11 )
  {
    std::string::append(Src);
    std::string::append(Src);
  }
  v7 = Src[2];
  if ( v7 >= Src[3] )
  {
    std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src);
  }
  else
  {
    Src[2] = v7 + 1;
    v8 = Src;
    if ( Src[3] > 0xFu )
      v8 = (_QWORD *)*Src;
    *(_WORD *)((char *)v8 + v7) = 34;
  }
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(Srca);
  return Src;
}

```

## disassembly

```asm
0x180023838  mov     [rsp-8+arg_10], rbx
0x18002383d  push    rbp
0x18002383e  push    rsi
0x18002383f  push    rdi
0x180023840  push    r14
0x180023842  push    r15
0x180023844  lea     rbp, [rsp-37h]
0x180023849  sub     rsp, 90h
0x180023850  mov     rax, cs:__security_cookie
0x180023857  xor     rax, rsp
0x18002385a  mov     [rbp+57h+var_30], rax
0x18002385e  mov     rdi, r9
0x180023861  mov     rsi, r8
0x180023864  mov     r15, rdx
0x180023867  mov     rbx, rcx
0x18002386a  mov     [rbp+57h+var_78], rcx
0x18002386e  and     [rbp+57h+var_80], 0
0x180023872  xorps   xmm0, xmm0
0x180023875  movups  xmmword ptr [rcx], xmm0
0x180023878  and     qword ptr [rcx+10h], 0
0x18002387d  and     qword ptr [rcx+10h], 0
0x180023882  mov     qword ptr [rcx+18h], 0Fh
0x18002388a  mov     byte ptr [rcx], 0
0x18002388d  mov     [rbp+57h+var_80], 1
0x180023894  call    __std_fs_code_page
0x180023899  mov     r14d, eax
0x18002389c  mov     rcx, rsi
0x18002389f  cmp     qword ptr [rsi+18h], 7
0x1800238a4  jbe     short loc_1800238A9
0x1800238a6  mov     rcx, [rsi]
0x1800238a9  mov     rax, [rsi+10h]
0x1800238ad  mov     qword ptr [rbp+57h+var_90], rcx
0x1800238b1  mov     qword ptr [rbp+57h+var_90+8], rax
0x1800238b5  movaps  xmm0, [rbp+57h+var_90]
0x1800238b9  movdqa  [rbp+57h+var_90], xmm0
0x1800238be  lea     r8, [rbp+57h+var_90]
0x1800238c2  mov     edx, r14d; CodePage
0x1800238c5  lea     rcx, [rbp+57h+Src]; Src
0x1800238c9  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x1800238ce  nop
0x1800238cf  mov     rcx, rdi
0x1800238d2  cmp     qword ptr [rdi+18h], 7
0x1800238d7  jbe     short loc_1800238DC
0x1800238d9  mov     rcx, [rdi]
0x1800238dc  mov     rax, [rdi+10h]
0x1800238e0  mov     qword ptr [rbp+57h+var_90], rcx
0x1800238e4  mov     qword ptr [rbp+57h+var_90+8], rax
0x1800238e8  movaps  xmm0, [rbp+57h+var_90]
0x1800238ec  movdqa  [rbp+57h+var_90], xmm0
0x1800238f1  lea     r8, [rbp+57h+var_90]
0x1800238f5  mov     edx, r14d; CodePage
0x1800238f8  lea     rcx, [rbp+57h+var_70]; Src
0x1800238fc  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x180023901  nop
0x180023902  mov     rax, [rbp+57h+var_60]
0x180023906  neg     rax
0x180023909  sbb     rcx, rcx
0x18002390c  and     ecx, 4
0x18002390f  mov     rax, [r15+8]
0x180023913  add     rax, [rbp+57h+var_40]
0x180023917  add     rax, [rbp+57h+var_60]
0x18002391b  lea     rdx, [rcx+4]
0x18002391f  add     rdx, rax
0x180023922  mov     rdi, [rbx+10h]
0x180023926  cmp     rdi, rdx
0x180023929  ja      short loc_180023959
0x18002392b  cmp     [rbx+18h], rdx
0x18002392f  jz      short loc_180023959
0x180023931  jnb     short loc_180023944
0x180023933  sub     rdx, rdi
0x180023936  mov     rcx, rbx; Src
0x180023939  call    ??$_Reallocate_grow_by@V_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@$$V@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@@Z; std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(unsigned __int64,_lambda_9013ee9e23efe4882b67eff5b0ecf103_)
0x18002393e  mov     [rbx+10h], rdi
0x180023942  jmp     short loc_180023959
0x180023944  cmp     rdx, 0Fh
0x180023948  ja      short loc_180023959
0x18002394a  cmp     qword ptr [rbx+18h], 0Fh
0x18002394f  jbe     short loc_180023959
0x180023951  mov     rcx, rbx
0x180023954  call    ?_Become_small@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Become_small(void)
0x180023959  mov     r8, [r15+8]
0x18002395d  mov     rdx, [r15]
0x180023960  mov     rcx, rbx; Src
0x180023963  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x180023968  mov     r8d, 3
0x18002396e  lea     rdx, asc_180032CC8; ": \""
0x180023975  mov     rcx, rbx; Src
0x180023978  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x18002397d  lea     rdx, [rbp+57h+Src]
0x180023981  cmp     [rbp+57h+var_38], 0Fh
0x180023986  cmova   rdx, [rbp+57h+Src]
0x18002398b  mov     r8, [rbp+57h+var_40]
0x18002398f  mov     rcx, rbx; Src
0x180023992  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x180023997  cmp     [rbp+57h+var_60], 0
0x18002399c  jz      short loc_1800239CD
0x18002399e  mov     r8d, 4
0x1800239a4  lea     rdx, asc_180032CCC; "\", \""
0x1800239ab  mov     rcx, rbx; Src
0x1800239ae  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x1800239b3  lea     rdx, [rbp+57h+var_70]
0x1800239b7  cmp     [rbp+57h+var_58], 0Fh
0x1800239bc  cmova   rdx, [rbp+57h+var_70]
0x1800239c1  mov     r8, [rbp+57h+var_60]
0x1800239c5  mov     rcx, rbx; Src
0x1800239c8  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x1800239cd  mov     rcx, [rbx+10h]
0x1800239d1  cmp     rcx, [rbx+18h]
0x1800239d5  jnb     short loc_1800239F4
0x1800239d7  lea     rax, [rcx+1]
0x1800239db  mov     [rbx+10h], rax
0x1800239df  mov     rax, rbx
0x1800239e2  cmp     qword ptr [rbx+18h], 0Fh
0x1800239e7  jbe     short loc_1800239EC
0x1800239e9  mov     rax, [rbx]
0x1800239ec  mov     word ptr [rax+rcx], 22h ; '"'
0x1800239f2  jmp     short loc_180023A00
0x1800239f4  mov     r9b, 22h ; '"'
0x1800239f7  mov     rcx, rbx; Src
0x1800239fa  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x1800239ff  nop
0x180023a00  lea     rcx, [rbp+57h+var_70]
0x180023a04  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180023a09  nop
0x180023a0a  lea     rcx, [rbp+57h+Src]
0x180023a0e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180023a13  mov     rax, rbx
0x180023a16  mov     rcx, [rbp+57h+var_30]
0x180023a1a  xor     rcx, rsp; StackCookie
0x180023a1d  call    __security_check_cookie
0x180023a22  mov     rbx, [rsp+0B0h+arg_10]
0x180023a2a  add     rsp, 90h
0x180023a31  pop     r15
0x180023a33  pop     r14
0x180023a35  pop     rdi
0x180023a36  pop     rsi
0x180023a37  pop     rbp
0x180023a38  retn
```
