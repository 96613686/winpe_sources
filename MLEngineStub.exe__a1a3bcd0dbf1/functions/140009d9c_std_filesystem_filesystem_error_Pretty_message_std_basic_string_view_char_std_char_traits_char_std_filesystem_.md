# std::filesystem::filesystem_error::_Pretty_message(std::basic_string_view<char,std::char_traits<char>>,std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x140009d9c`
- end: `0x14000a13a`
- name: `?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z`
- size: `926`
- prototype: `_QWORD *__fastcall(_QWORD *Src, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1400083e4`

## callees

- `0x140001848`
- `0x140002120`
- `0x1400023b4`
- `0x140007260`
- `0x1400074b8`
- `0x14000782c`
- `0x1400079a0`
- `0x14000877c`
- `0x140009d9c`
- `0x14000ad14`
- `0x14000ad20`

## pseudocode

```c
_QWORD *__fastcall std::filesystem::filesystem_error::_Pretty_message(_QWORD *Src, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  UINT v8; // r14d
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // r8
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r14
  _BYTE *v15; // rdi
  _BYTE *v16; // rcx
  __int64 v17; // rdi
  _QWORD *v18; // r14
  __int64 v19; // r8
  __int64 v20; // rdi
  _QWORD *v21; // rsi
  __int64 v22; // r8
  size_t v23; // rdi
  void **v24; // r9
  __int64 v25; // rsi
  _QWORD *v26; // r14
  __int64 v27; // r8
  __int64 v28; // rcx
  char *v29; // rdx
  size_t v30; // rdi
  void **v31; // r9
  __int64 v32; // rsi
  _QWORD *v33; // r14
  unsigned __int64 v34; // rcx
  _QWORD *v35; // rax
  _QWORD *v37; // [rsp+40h] [rbp-29h] BYREF
  __int64 v38; // [rsp+48h] [rbp-21h]
  _QWORD *v39; // [rsp+50h] [rbp-19h]
  void *v40[2]; // [rsp+58h] [rbp-11h] BYREF
  size_t v41; // [rsp+68h] [rbp-1h]
  unsigned __int64 v42; // [rsp+70h] [rbp+7h]
  void *Srca[2]; // [rsp+78h] [rbp+Fh] BYREF
  size_t Size; // [rsp+88h] [rbp+1Fh]
  unsigned __int64 v45; // [rsp+90h] [rbp+27h]

  v39 = Src;
  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 15;
  *(_BYTE *)Src = 0;
  v8 = _std_fs_code_page();
  if ( a3[3] <= 7u )
    v9 = a3;
  else
    v9 = (_QWORD *)*a3;
  v37 = v9;
  v38 = a3[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    Srca,
    v8,
    (__int64)&v37);
  if ( a4[3] <= 7u )
    v10 = a4;
  else
    v10 = (_QWORD *)*a4;
  v37 = v10;
  v38 = a4[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    v40,
    v8,
    (__int64)&v37);
  v12 = *(_QWORD *)(a2 + 8);
  v13 = (((unsigned __int128)-(__int128)v41 >> 64) & 4) + 4 + v41 + v12 + Size;
  v14 = Src[2];
  if ( v14 <= v13 && Src[3] != v13 )
  {
    if ( Src[3] >= v13 )
    {
      if ( v13 <= 0xF && Src[3] > 0xFu )
      {
        v15 = (_BYTE *)*Src;
        memcpy_0(Src, (const void *)*Src, v14 + 1);
        if ( (unsigned __int64)(Src[3] + 1LL) < 0x1000 )
        {
          v16 = v15;
        }
        else
        {
          v16 = (_BYTE *)*((_QWORD *)v15 - 1);
          if ( (unsigned __int64)(v15 - v16 - 8) > 0x1F )
            __fastfail(5u);
        }
        operator delete(v16);
        Src[3] = 15;
      }
    }
    else
    {
      std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(Src);
      Src[2] = v14;
    }
  }
  v17 = Src[2];
  if ( v12 > Src[3] - v17 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
      (void **)Src,
      v12,
      v11,
      *(const void **)a2,
      v12);
  }
  else
  {
    Src[2] = v17 + v12;
    if ( Src[3] <= 0xFu )
      v18 = Src;
    else
      v18 = (_QWORD *)*Src;
    memmove_0((char *)v18 + v17, *(const void **)a2, v12);
    *((_BYTE *)v18 + v17 + v12) = 0;
  }
  v20 = Src[2];
  if ( (unsigned __int64)(Src[3] - v20) < 3 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
      (void **)Src,
      3u,
      v19,
      ": \"",
      3u);
  }
  else
  {
    Src[2] = v20 + 3;
    if ( Src[3] <= 0xFu )
      v21 = Src;
    else
      v21 = (_QWORD *)*Src;
    memmove_0((char *)v21 + v20, ": \"", 3u);
    *((_BYTE *)v21 + v20 + 3) = 0;
  }
  v23 = Size;
  v24 = Srca;
  if ( v45 > 0xF )
    v24 = (void **)Srca[0];
  v25 = Src[2];
  if ( Size > Src[3] - v25 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
      (void **)Src,
      Size,
      v22,
      v24,
      Size);
  }
  else
  {
    Src[2] = v25 + Size;
    if ( Src[3] <= 0xFu )
      v26 = Src;
    else
      v26 = (_QWORD *)*Src;
    memmove_0((char *)v26 + v25, v24, v23);
    *((_BYTE *)v26 + v25 + v23) = 0;
  }
  if ( v41 )
  {
    v28 = Src[2];
    if ( (unsigned __int64)(Src[3] - v28) < 4 )
    {
      std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
        (void **)Src,
        4u,
        v27,
        "\", \"",
        4u);
    }
    else
    {
      Src[2] = v28 + 4;
      if ( Src[3] <= 0xFu )
        v29 = (char *)Src;
      else
        v29 = (char *)*Src;
      strcpy(&v29[v28], "\", \"");
    }
    v30 = v41;
    v31 = v40;
    if ( v42 > 0xF )
      v31 = (void **)v40[0];
    v32 = Src[2];
    if ( v41 > Src[3] - v32 )
    {
      std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
        (void **)Src,
        v41,
        v27,
        v31,
        v41);
    }
    else
    {
      Src[2] = v32 + v41;
      if ( Src[3] <= 0xFu )
        v33 = Src;
      else
        v33 = (_QWORD *)*Src;
      memmove_0((char *)v33 + v32, v31, v30);
      *((_BYTE *)v33 + v32 + v30) = 0;
    }
  }
  v34 = Src[2];
  if ( v34 >= Src[3] )
  {
    std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src);
  }
  else
  {
    Src[2] = v34 + 1;
    if ( Src[3] <= 0xFu )
      v35 = Src;
    else
      v35 = (_QWORD *)*Src;
    *(_WORD *)((char *)v35 + v34) = 34;
  }
  std::string::~string((char **)v40);
  std::string::~string((char **)Srca);
  return Src;
}

```

## disassembly

```asm
0x140009d9c  mov     [rsp-8+arg_10], rbx
0x140009da1  mov     [rsp-8+arg_18], rsi
0x140009da6  push    rbp
0x140009da7  push    rdi
0x140009da8  push    r12
0x140009daa  push    r14
0x140009dac  push    r15
0x140009dae  lea     rbp, [rsp-37h]
0x140009db3  sub     rsp, 0A0h
0x140009dba  mov     rax, cs:__security_cookie
0x140009dc1  xor     rax, rsp
0x140009dc4  mov     [rbp+57h+var_28], rax
0x140009dc8  mov     rsi, r9
0x140009dcb  mov     rdi, r8
0x140009dce  mov     r15, rdx
0x140009dd1  mov     rbx, rcx
0x140009dd4  mov     [rbp+57h+var_70], rcx
0x140009dd8  mov     [rbp+57h+var_90], 0
0x140009ddf  xorps   xmm0, xmm0
0x140009de2  movups  xmmword ptr [rcx], xmm0
0x140009de5  mov     qword ptr [rcx+10h], 0
0x140009ded  mov     r12d, 0Fh
0x140009df3  mov     [rcx+18h], r12
0x140009df7  mov     byte ptr [rcx], 0
0x140009dfa  mov     [rbp+57h+var_90], 1
0x140009e01  call    __std_fs_code_page
0x140009e06  mov     r14d, eax
0x140009e09  cmp     qword ptr [rdi+18h], 7
0x140009e0e  jbe     short loc_140009E15
0x140009e10  mov     rax, [rdi]
0x140009e13  jmp     short loc_140009E18
0x140009e15  mov     rax, rdi
0x140009e18  mov     [rbp+57h+var_80], rax
0x140009e1c  mov     rax, [rdi+10h]
0x140009e20  mov     [rbp+57h+var_78], rax
0x140009e24  lea     r8, [rbp+57h+var_80]
0x140009e28  mov     edx, r14d; CodePage
0x140009e2b  lea     rcx, [rbp+57h+Src]; Src
0x140009e2f  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x140009e34  nop
0x140009e35  cmp     qword ptr [rsi+18h], 7
0x140009e3a  jbe     short loc_140009E41
0x140009e3c  mov     rax, [rsi]
0x140009e3f  jmp     short loc_140009E44
0x140009e41  mov     rax, rsi
0x140009e44  mov     [rbp+57h+var_80], rax
0x140009e48  mov     rax, [rsi+10h]
0x140009e4c  mov     [rbp+57h+var_78], rax
0x140009e50  lea     r8, [rbp+57h+var_80]
0x140009e54  mov     edx, r14d; CodePage
0x140009e57  lea     rcx, [rbp+57h+var_68]; Src
0x140009e5b  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x140009e60  nop
0x140009e61  mov     rax, [rbp+57h+var_58]
0x140009e65  neg     rax
0x140009e68  sbb     rdx, rdx
0x140009e6b  and     edx, 4
0x140009e6e  add     rdx, 4
0x140009e72  mov     rsi, [r15+8]
0x140009e76  mov     rax, [rbp+57h+Size]
0x140009e7a  add     rax, rsi
0x140009e7d  add     rax, [rbp+57h+var_58]
0x140009e81  add     rax, rdx
0x140009e84  mov     r14, [rbx+10h]
0x140009e88  cmp     r14, rax
0x140009e8b  ja      short loc_140009F00
0x140009e8d  cmp     [rbx+18h], rax
0x140009e91  jz      short loc_140009F00
0x140009e93  jnb     short loc_140009EA9
0x140009e95  sub     rax, r14
0x140009e98  mov     rdx, rax
0x140009e9b  mov     rcx, rbx; Src
0x140009e9e  call    ??$_Reallocate_grow_by@V_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@$$V@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@@Z; std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(unsigned __int64,_lambda_9013ee9e23efe4882b67eff5b0ecf103_)
0x140009ea3  mov     [rbx+10h], r14
0x140009ea7  jmp     short loc_140009F00
0x140009ea9  cmp     rax, r12
0x140009eac  ja      short loc_140009F00
0x140009eae  cmp     [rbx+18h], r12
0x140009eb2  jbe     short loc_140009F00
0x140009eb4  mov     rdi, [rbx]
0x140009eb7  lea     r8, [r14+1]; Size
0x140009ebb  mov     rdx, rdi; Src
0x140009ebe  mov     rcx, rbx; void *
0x140009ec1  call    memcpy_0
0x140009ec6  mov     rdx, [rbx+18h]
0x140009eca  inc     rdx; unsigned __int64
0x140009ecd  cmp     rdx, 1000h
0x140009ed4  jb      short loc_140009EF4
0x140009ed6  mov     rcx, [rdi-8]
0x140009eda  sub     rdi, rcx
0x140009edd  sub     rdi, 8
0x140009ee1  cmp     rdi, 1Fh
0x140009ee5  ja      short loc_140009EED
0x140009ee7  add     rdx, 27h ; '''
0x140009eeb  jmp     short loc_140009EF7
0x140009eed  mov     ecx, 5
0x140009ef2  int     29h; Win8: RtlFailFast(ecx)
0x140009ef4  mov     rcx, rdi; void *
0x140009ef7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009efc  mov     [rbx+18h], r12
0x140009f00  mov     rdi, [rbx+10h]
0x140009f04  mov     rax, [rbx+18h]
0x140009f08  sub     rax, rdi
0x140009f0b  cmp     rsi, rax
0x140009f0e  ja      short loc_140009F40
0x140009f10  lea     rax, [rdi+rsi]
0x140009f14  mov     [rbx+10h], rax
0x140009f18  cmp     [rbx+18h], r12
0x140009f1c  jbe     short loc_140009F23
0x140009f1e  mov     r14, [rbx]
0x140009f21  jmp     short loc_140009F26
0x140009f23  mov     r14, rbx
0x140009f26  lea     rcx, [rdi+r14]; void *
0x140009f2a  mov     r8, rsi; Size
0x140009f2d  mov     rdx, [r15]; Src
0x140009f30  call    memmove_0
0x140009f35  lea     rax, [rdi+rsi]
0x140009f39  mov     byte ptr [rax+r14], 0
0x140009f3e  jmp     short loc_140009F53
0x140009f40  mov     [rsp+0C0h+var_A0], rsi; Size
0x140009f45  mov     r9, [r15]
0x140009f48  mov     rdx, rsi
0x140009f4b  mov     rcx, rbx; Src
0x140009f4e  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x140009f53  mov     rdi, [rbx+10h]
0x140009f57  mov     rax, [rbx+18h]
0x140009f5b  sub     rax, rdi
0x140009f5e  mov     edx, 3
0x140009f63  cmp     rax, rdx
0x140009f66  jb      short loc_140009F98
0x140009f68  lea     rax, [rdi+3]
0x140009f6c  mov     [rbx+10h], rax
0x140009f70  cmp     [rbx+18h], r12
0x140009f74  jbe     short loc_140009F7B
0x140009f76  mov     rsi, [rbx]
0x140009f79  jmp     short loc_140009F7E
0x140009f7b  mov     rsi, rbx
0x140009f7e  lea     rcx, [rdi+rsi]; void *
0x140009f82  mov     r8, rdx; Size
0x140009f85  lea     rdx, asc_14000DE90; ": \""
0x140009f8c  call    memmove_0
0x140009f91  mov     byte ptr [rdi+rsi+3], 0
0x140009f96  jmp     short loc_140009FAC
0x140009f98  mov     [rsp+0C0h+var_A0], rdx; Size
0x140009f9d  lea     r9, asc_14000DE90; ": \""
0x140009fa4  mov     rcx, rbx; Src
0x140009fa7  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x140009fac  mov     rdi, [rbp+57h+Size]
0x140009fb0  lea     r9, [rbp+57h+Src]
0x140009fb4  cmp     [rbp+57h+var_30], r12
0x140009fb8  cmova   r9, [rbp+57h+Src]
0x140009fbd  mov     rsi, [rbx+10h]
0x140009fc1  mov     rax, [rbx+18h]
0x140009fc5  sub     rax, rsi
0x140009fc8  cmp     rdi, rax
0x140009fcb  ja      short loc_140009FFC
0x140009fcd  lea     rax, [rsi+rdi]
0x140009fd1  mov     [rbx+10h], rax
0x140009fd5  cmp     [rbx+18h], r12
0x140009fd9  jbe     short loc_140009FE0
0x140009fdb  mov     r14, [rbx]
0x140009fde  jmp     short loc_140009FE3
0x140009fe0  mov     r14, rbx
0x140009fe3  lea     rcx, [rsi+r14]; void *
0x140009fe7  mov     r8, rdi; Size
0x140009fea  mov     rdx, r9; Src
0x140009fed  call    memmove_0
0x140009ff2  lea     rax, [rsi+r14]
0x140009ff6  mov     byte ptr [rax+rdi], 0
0x140009ffa  jmp     short loc_14000A00C
0x140009ffc  mov     [rsp+0C0h+var_A0], rdi; Size
0x14000a001  mov     rdx, rdi
0x14000a004  mov     rcx, rbx; Src
0x14000a007  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x14000a00c  cmp     [rbp+57h+var_58], 0
0x14000a011  jz      loc_14000A0C7
0x14000a017  mov     rcx, [rbx+10h]
0x14000a01b  mov     rax, [rbx+18h]
0x14000a01f  sub     rax, rcx
0x14000a022  mov     edx, 4
0x14000a027  cmp     rax, rdx
0x14000a02a  jb      short loc_14000A052
0x14000a02c  lea     rax, [rcx+4]
0x14000a030  mov     [rbx+10h], rax
0x14000a034  cmp     [rbx+18h], r12
0x14000a038  jbe     short loc_14000A03F
0x14000a03a  mov     rdx, [rbx]
0x14000a03d  jmp     short loc_14000A042
0x14000a03f  mov     rdx, rbx
0x14000a042  mov     eax, dword ptr cs:asc_14000DE94; "\", \""
0x14000a048  mov     [rcx+rdx], eax
0x14000a04b  mov     byte ptr [rcx+rdx+4], 0
0x14000a050  jmp     short loc_14000A066
0x14000a052  mov     [rsp+0C0h+var_A0], rdx; Size
0x14000a057  lea     r9, asc_14000DE94; "\", \""
0x14000a05e  mov     rcx, rbx; Src
0x14000a061  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x14000a066  mov     rdi, [rbp+57h+var_58]
0x14000a06a  lea     r9, [rbp+57h+var_68]
0x14000a06e  cmp     [rbp+57h+var_50], r12
0x14000a072  cmova   r9, [rbp+57h+var_68]
0x14000a077  mov     rsi, [rbx+10h]
0x14000a07b  mov     rax, [rbx+18h]
0x14000a07f  sub     rax, rsi
0x14000a082  cmp     rdi, rax
0x14000a085  ja      short loc_14000A0B7
0x14000a087  lea     rax, [rsi+rdi]
0x14000a08b  mov     [rbx+10h], rax
0x14000a08f  cmp     [rbx+18h], r12
0x14000a093  jbe     short loc_14000A09A
0x14000a095  mov     r14, [rbx]
0x14000a098  jmp     short loc_14000A09D
0x14000a09a  mov     r14, rbx
0x14000a09d  lea     rcx, [rsi+r14]; void *
0x14000a0a1  mov     r8, rdi; Size
0x14000a0a4  mov     rdx, r9; Src
0x14000a0a7  call    memmove_0
0x14000a0ac  lea     rax, [rsi+rdi]
0x14000a0b0  mov     byte ptr [rax+r14], 0
0x14000a0b5  jmp     short loc_14000A0C7
0x14000a0b7  mov     [rsp+0C0h+var_A0], rdi; Size
0x14000a0bc  mov     rdx, rdi
0x14000a0bf  mov     rcx, rbx; Src
0x14000a0c2  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x14000a0c7  mov     rcx, [rbx+10h]
0x14000a0cb  cmp     rcx, [rbx+18h]
0x14000a0cf  jnb     short loc_14000A0EF
0x14000a0d1  lea     rax, [rcx+1]
0x14000a0d5  mov     [rbx+10h], rax
0x14000a0d9  cmp     [rbx+18h], r12
0x14000a0dd  jbe     short loc_14000A0E4
0x14000a0df  mov     rax, [rbx]
0x14000a0e2  jmp     short loc_14000A0E7
0x14000a0e4  mov     rax, rbx
0x14000a0e7  mov     word ptr [rcx+rax], 22h ; '"'
0x14000a0ed  jmp     short loc_14000A0FB
0x14000a0ef  mov     r9b, 22h ; '"'
0x14000a0f2  mov     rcx, rbx; Src
0x14000a0f5  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x14000a0fa  nop
0x14000a0fb  lea     rcx, [rbp+57h+var_68]
0x14000a0ff  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000a104  nop
0x14000a105  lea     rcx, [rbp+57h+Src]
0x14000a109  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000a10e  mov     rax, rbx
0x14000a111  mov     rcx, [rbp+57h+var_28]
0x14000a115  xor     rcx, rsp; StackCookie
0x14000a118  call    __security_check_cookie
0x14000a11d  lea     r11, [rsp+0C0h+var_20]
0x14000a125  mov     rbx, [r11+40h]
0x14000a129  mov     rsi, [r11+48h]
0x14000a12d  mov     rsp, r11
0x14000a130  pop     r15
0x14000a132  pop     r14
0x14000a134  pop     r12
0x14000a136  pop     rdi
0x14000a137  pop     rbp
0x14000a138  retn
```
