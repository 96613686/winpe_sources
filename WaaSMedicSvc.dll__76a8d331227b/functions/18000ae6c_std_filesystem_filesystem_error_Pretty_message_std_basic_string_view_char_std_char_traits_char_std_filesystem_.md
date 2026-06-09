# std::filesystem::filesystem_error::_Pretty_message(std::basic_string_view<char,std::char_traits<char>>,std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x18000ae6c`
- end: `0x18000b20a`
- name: `?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z`
- size: `926`
- prototype: `_QWORD *__fastcall(_QWORD *Src, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180008b20`

## callees

- `0x180001858`
- `0x180002200`
- `0x1800025d0`
- `0x1800079f4`
- `0x180007c4c`
- `0x180007fc0`
- `0x180008134`
- `0x180008eb8`
- `0x18000ae6c`
- `0x18000bd94`
- `0x18000bda0`

## pseudocode

```c
_QWORD *__fastcall std::filesystem::filesystem_error::_Pretty_message(_QWORD *Src, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  UINT v8; // r14d
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  size_t v11; // rsi
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // r14
  _BYTE *v14; // rdi
  _BYTE *v15; // rcx
  __int64 v16; // rdi
  _QWORD *v17; // r14
  __int64 v18; // rdi
  _QWORD *v19; // rsi
  size_t v20; // rdi
  void **v21; // r9
  __int64 v22; // rsi
  _QWORD *v23; // r14
  __int64 v24; // rcx
  char *v25; // rdx
  size_t v26; // rdi
  void **v27; // r9
  __int64 v28; // rsi
  _QWORD *v29; // r14
  unsigned __int64 v30; // rcx
  _QWORD *v31; // rax
  _QWORD *v33; // [rsp+40h] [rbp-29h] BYREF
  __int64 v34; // [rsp+48h] [rbp-21h]
  _QWORD *v35; // [rsp+50h] [rbp-19h]
  void *v36[2]; // [rsp+58h] [rbp-11h] BYREF
  size_t v37; // [rsp+68h] [rbp-1h]
  unsigned __int64 v38; // [rsp+70h] [rbp+7h]
  void *Srca[2]; // [rsp+78h] [rbp+Fh] BYREF
  size_t Size; // [rsp+88h] [rbp+1Fh]
  unsigned __int64 v41; // [rsp+90h] [rbp+27h]

  v35 = Src;
  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 15;
  *(_BYTE *)Src = 0;
  v8 = _std_fs_code_page();
  if ( a3[3] <= 7u )
    v9 = a3;
  else
    v9 = (_QWORD *)*a3;
  v33 = v9;
  v34 = a3[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    Srca,
    v8,
    (__int64)&v33);
  if ( a4[3] <= 7u )
    v10 = a4;
  else
    v10 = (_QWORD *)*a4;
  v33 = v10;
  v34 = a4[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    v36,
    v8,
    (__int64)&v33);
  v11 = *(_QWORD *)(a2 + 8);
  v12 = (((unsigned __int128)-(__int128)v37 >> 64) & 4) + 4 + v37 + v11 + Size;
  v13 = Src[2];
  if ( v13 <= v12 && Src[3] != v12 )
  {
    if ( Src[3] >= v12 )
    {
      if ( v12 <= 0xF && Src[3] > 0xFu )
      {
        v14 = (_BYTE *)*Src;
        memcpy_0(Src, (const void *)*Src, v13 + 1);
        if ( (unsigned __int64)(Src[3] + 1LL) < 0x1000 )
        {
          v15 = v14;
        }
        else
        {
          v15 = (_BYTE *)*((_QWORD *)v14 - 1);
          if ( (unsigned __int64)(v14 - v15 - 8) > 0x1F )
            __fastfail(5u);
        }
        operator delete(v15);
        Src[3] = 15;
      }
    }
    else
    {
      std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(Src);
      Src[2] = v13;
    }
  }
  v16 = Src[2];
  if ( v11 > Src[3] - v16 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(Src, v11);
  }
  else
  {
    Src[2] = v16 + v11;
    if ( Src[3] <= 0xFu )
      v17 = Src;
    else
      v17 = (_QWORD *)*Src;
    memmove_0((char *)v17 + v16, *(const void **)a2, v11);
    *((_BYTE *)v17 + v16 + v11) = 0;
  }
  v18 = Src[2];
  if ( (unsigned __int64)(Src[3] - v18) < 3 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(Src, 3u);
  }
  else
  {
    Src[2] = v18 + 3;
    if ( Src[3] <= 0xFu )
      v19 = Src;
    else
      v19 = (_QWORD *)*Src;
    memmove_0((char *)v19 + v18, ": \"", 3u);
    *((_BYTE *)v19 + v18 + 3) = 0;
  }
  v20 = Size;
  v21 = Srca;
  if ( v41 > 0xF )
    v21 = (void **)Srca[0];
  v22 = Src[2];
  if ( Size > Src[3] - v22 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(Src, Size);
  }
  else
  {
    Src[2] = v22 + Size;
    if ( Src[3] <= 0xFu )
      v23 = Src;
    else
      v23 = (_QWORD *)*Src;
    memmove_0((char *)v23 + v22, v21, v20);
    *((_BYTE *)v23 + v22 + v20) = 0;
  }
  if ( v37 )
  {
    v24 = Src[2];
    if ( (unsigned __int64)(Src[3] - v24) < 4 )
    {
      std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(Src, 4u);
    }
    else
    {
      Src[2] = v24 + 4;
      if ( Src[3] <= 0xFu )
        v25 = (char *)Src;
      else
        v25 = (char *)*Src;
      strcpy(&v25[v24], "\", \"");
    }
    v26 = v37;
    v27 = v36;
    if ( v38 > 0xF )
      v27 = (void **)v36[0];
    v28 = Src[2];
    if ( v37 > Src[3] - v28 )
    {
      std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
        Src,
        v37);
    }
    else
    {
      Src[2] = v28 + v37;
      if ( Src[3] <= 0xFu )
        v29 = Src;
      else
        v29 = (_QWORD *)*Src;
      memmove_0((char *)v29 + v28, v27, v26);
      *((_BYTE *)v29 + v28 + v26) = 0;
    }
  }
  v30 = Src[2];
  if ( v30 >= Src[3] )
  {
    std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src);
  }
  else
  {
    Src[2] = v30 + 1;
    if ( Src[3] <= 0xFu )
      v31 = Src;
    else
      v31 = (_QWORD *)*Src;
    *(_WORD *)((char *)v31 + v30) = 34;
  }
  std::string::~string((char **)v36);
  std::string::~string((char **)Srca);
  return Src;
}

```

## disassembly

```asm
0x18000ae6c  mov     [rsp-8+arg_10], rbx
0x18000ae71  mov     [rsp-8+arg_18], rsi
0x18000ae76  push    rbp
0x18000ae77  push    rdi
0x18000ae78  push    r12
0x18000ae7a  push    r14
0x18000ae7c  push    r15
0x18000ae7e  lea     rbp, [rsp-37h]
0x18000ae83  sub     rsp, 0A0h
0x18000ae8a  mov     rax, cs:__security_cookie
0x18000ae91  xor     rax, rsp
0x18000ae94  mov     [rbp+57h+var_28], rax
0x18000ae98  mov     rsi, r9
0x18000ae9b  mov     rdi, r8
0x18000ae9e  mov     r15, rdx
0x18000aea1  mov     rbx, rcx
0x18000aea4  mov     [rbp+57h+var_70], rcx
0x18000aea8  mov     [rbp+57h+var_90], 0
0x18000aeaf  xorps   xmm0, xmm0
0x18000aeb2  movups  xmmword ptr [rcx], xmm0
0x18000aeb5  mov     qword ptr [rcx+10h], 0
0x18000aebd  mov     r12d, 0Fh
0x18000aec3  mov     [rcx+18h], r12
0x18000aec7  mov     byte ptr [rcx], 0
0x18000aeca  mov     [rbp+57h+var_90], 1
0x18000aed1  call    __std_fs_code_page
0x18000aed6  mov     r14d, eax
0x18000aed9  cmp     qword ptr [rdi+18h], 7
0x18000aede  jbe     short loc_18000AEE5
0x18000aee0  mov     rax, [rdi]
0x18000aee3  jmp     short loc_18000AEE8
0x18000aee5  mov     rax, rdi
0x18000aee8  mov     [rbp+57h+var_80], rax
0x18000aeec  mov     rax, [rdi+10h]
0x18000aef0  mov     [rbp+57h+var_78], rax
0x18000aef4  lea     r8, [rbp+57h+var_80]
0x18000aef8  mov     edx, r14d; CodePage
0x18000aefb  lea     rcx, [rbp+57h+Src]; Src
0x18000aeff  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x18000af04  nop
0x18000af05  cmp     qword ptr [rsi+18h], 7
0x18000af0a  jbe     short loc_18000AF11
0x18000af0c  mov     rax, [rsi]
0x18000af0f  jmp     short loc_18000AF14
0x18000af11  mov     rax, rsi
0x18000af14  mov     [rbp+57h+var_80], rax
0x18000af18  mov     rax, [rsi+10h]
0x18000af1c  mov     [rbp+57h+var_78], rax
0x18000af20  lea     r8, [rbp+57h+var_80]
0x18000af24  mov     edx, r14d; CodePage
0x18000af27  lea     rcx, [rbp+57h+var_68]; Src
0x18000af2b  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x18000af30  nop
0x18000af31  mov     rax, [rbp+57h+var_58]
0x18000af35  neg     rax
0x18000af38  sbb     rdx, rdx
0x18000af3b  and     edx, 4
0x18000af3e  add     rdx, 4
0x18000af42  mov     rsi, [r15+8]
0x18000af46  mov     rax, [rbp+57h+Size]
0x18000af4a  add     rax, rsi
0x18000af4d  add     rax, [rbp+57h+var_58]
0x18000af51  add     rax, rdx
0x18000af54  mov     r14, [rbx+10h]
0x18000af58  cmp     r14, rax
0x18000af5b  ja      short loc_18000AFD0
0x18000af5d  cmp     [rbx+18h], rax
0x18000af61  jz      short loc_18000AFD0
0x18000af63  jnb     short loc_18000AF79
0x18000af65  sub     rax, r14
0x18000af68  mov     rdx, rax
0x18000af6b  mov     rcx, rbx; Src
0x18000af6e  call    ??$_Reallocate_grow_by@V_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@$$V@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@@Z; std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(unsigned __int64,_lambda_9013ee9e23efe4882b67eff5b0ecf103_)
0x18000af73  mov     [rbx+10h], r14
0x18000af77  jmp     short loc_18000AFD0
0x18000af79  cmp     rax, r12
0x18000af7c  ja      short loc_18000AFD0
0x18000af7e  cmp     [rbx+18h], r12
0x18000af82  jbe     short loc_18000AFD0
0x18000af84  mov     rdi, [rbx]
0x18000af87  lea     r8, [r14+1]; Size
0x18000af8b  mov     rdx, rdi; Src
0x18000af8e  mov     rcx, rbx; void *
0x18000af91  call    memcpy_0
0x18000af96  mov     rdx, [rbx+18h]
0x18000af9a  inc     rdx; unsigned __int64
0x18000af9d  cmp     rdx, 1000h
0x18000afa4  jb      short loc_18000AFC4
0x18000afa6  mov     rcx, [rdi-8]
0x18000afaa  sub     rdi, rcx
0x18000afad  sub     rdi, 8
0x18000afb1  cmp     rdi, 1Fh
0x18000afb5  ja      short loc_18000AFBD
0x18000afb7  add     rdx, 27h ; '''
0x18000afbb  jmp     short loc_18000AFC7
0x18000afbd  mov     ecx, 5
0x18000afc2  int     29h; Win8: RtlFailFast(ecx)
0x18000afc4  mov     rcx, rdi; void *
0x18000afc7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000afcc  mov     [rbx+18h], r12
0x18000afd0  mov     rdi, [rbx+10h]
0x18000afd4  mov     rax, [rbx+18h]
0x18000afd8  sub     rax, rdi
0x18000afdb  cmp     rsi, rax
0x18000afde  ja      short loc_18000B010
0x18000afe0  lea     rax, [rdi+rsi]
0x18000afe4  mov     [rbx+10h], rax
0x18000afe8  cmp     [rbx+18h], r12
0x18000afec  jbe     short loc_18000AFF3
0x18000afee  mov     r14, [rbx]
0x18000aff1  jmp     short loc_18000AFF6
0x18000aff3  mov     r14, rbx
0x18000aff6  lea     rcx, [rdi+r14]; void *
0x18000affa  mov     r8, rsi; Size
0x18000affd  mov     rdx, [r15]; Src
0x18000b000  call    memmove_0
0x18000b005  lea     rax, [rdi+rsi]
0x18000b009  mov     byte ptr [rax+r14], 0
0x18000b00e  jmp     short loc_18000B023
0x18000b010  mov     [rsp+0C0h+var_A0], rsi; Size
0x18000b015  mov     r9, [r15]
0x18000b018  mov     rdx, rsi
0x18000b01b  mov     rcx, rbx; Src
0x18000b01e  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x18000b023  mov     rdi, [rbx+10h]
0x18000b027  mov     rax, [rbx+18h]
0x18000b02b  sub     rax, rdi
0x18000b02e  mov     edx, 3
0x18000b033  cmp     rax, rdx
0x18000b036  jb      short loc_18000B068
0x18000b038  lea     rax, [rdi+3]
0x18000b03c  mov     [rbx+10h], rax
0x18000b040  cmp     [rbx+18h], r12
0x18000b044  jbe     short loc_18000B04B
0x18000b046  mov     rsi, [rbx]
0x18000b049  jmp     short loc_18000B04E
0x18000b04b  mov     rsi, rbx
0x18000b04e  lea     rcx, [rdi+rsi]; void *
0x18000b052  mov     r8, rdx; Size
0x18000b055  lea     rdx, asc_18000F0E0; ": \""
0x18000b05c  call    memmove_0
0x18000b061  mov     byte ptr [rdi+rsi+3], 0
0x18000b066  jmp     short loc_18000B07C
0x18000b068  mov     [rsp+0C0h+var_A0], rdx; Size
0x18000b06d  lea     r9, asc_18000F0E0; ": \""
0x18000b074  mov     rcx, rbx; Src
0x18000b077  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x18000b07c  mov     rdi, [rbp+57h+Size]
0x18000b080  lea     r9, [rbp+57h+Src]
0x18000b084  cmp     [rbp+57h+var_30], r12
0x18000b088  cmova   r9, [rbp+57h+Src]
0x18000b08d  mov     rsi, [rbx+10h]
0x18000b091  mov     rax, [rbx+18h]
0x18000b095  sub     rax, rsi
0x18000b098  cmp     rdi, rax
0x18000b09b  ja      short loc_18000B0CC
0x18000b09d  lea     rax, [rsi+rdi]
0x18000b0a1  mov     [rbx+10h], rax
0x18000b0a5  cmp     [rbx+18h], r12
0x18000b0a9  jbe     short loc_18000B0B0
0x18000b0ab  mov     r14, [rbx]
0x18000b0ae  jmp     short loc_18000B0B3
0x18000b0b0  mov     r14, rbx
0x18000b0b3  lea     rcx, [rsi+r14]; void *
0x18000b0b7  mov     r8, rdi; Size
0x18000b0ba  mov     rdx, r9; Src
0x18000b0bd  call    memmove_0
0x18000b0c2  lea     rax, [rsi+r14]
0x18000b0c6  mov     byte ptr [rax+rdi], 0
0x18000b0ca  jmp     short loc_18000B0DC
0x18000b0cc  mov     [rsp+0C0h+var_A0], rdi; Size
0x18000b0d1  mov     rdx, rdi
0x18000b0d4  mov     rcx, rbx; Src
0x18000b0d7  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x18000b0dc  cmp     [rbp+57h+var_58], 0
0x18000b0e1  jz      loc_18000B197
0x18000b0e7  mov     rcx, [rbx+10h]
0x18000b0eb  mov     rax, [rbx+18h]
0x18000b0ef  sub     rax, rcx
0x18000b0f2  mov     edx, 4
0x18000b0f7  cmp     rax, rdx
0x18000b0fa  jb      short loc_18000B122
0x18000b0fc  lea     rax, [rcx+4]
0x18000b100  mov     [rbx+10h], rax
0x18000b104  cmp     [rbx+18h], r12
0x18000b108  jbe     short loc_18000B10F
0x18000b10a  mov     rdx, [rbx]
0x18000b10d  jmp     short loc_18000B112
0x18000b10f  mov     rdx, rbx
0x18000b112  mov     eax, dword ptr cs:asc_18000F0E4; "\", \""
0x18000b118  mov     [rcx+rdx], eax
0x18000b11b  mov     byte ptr [rcx+rdx+4], 0
0x18000b120  jmp     short loc_18000B136
0x18000b122  mov     [rsp+0C0h+var_A0], rdx; Size
0x18000b127  lea     r9, asc_18000F0E4; "\", \""
0x18000b12e  mov     rcx, rbx; Src
0x18000b131  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x18000b136  mov     rdi, [rbp+57h+var_58]
0x18000b13a  lea     r9, [rbp+57h+var_68]
0x18000b13e  cmp     [rbp+57h+var_50], r12
0x18000b142  cmova   r9, [rbp+57h+var_68]
0x18000b147  mov     rsi, [rbx+10h]
0x18000b14b  mov     rax, [rbx+18h]
0x18000b14f  sub     rax, rsi
0x18000b152  cmp     rdi, rax
0x18000b155  ja      short loc_18000B187
0x18000b157  lea     rax, [rsi+rdi]
0x18000b15b  mov     [rbx+10h], rax
0x18000b15f  cmp     [rbx+18h], r12
0x18000b163  jbe     short loc_18000B16A
0x18000b165  mov     r14, [rbx]
0x18000b168  jmp     short loc_18000B16D
0x18000b16a  mov     r14, rbx
0x18000b16d  lea     rcx, [rsi+r14]; void *
0x18000b171  mov     r8, rdi; Size
0x18000b174  mov     rdx, r9; Src
0x18000b177  call    memmove_0
0x18000b17c  lea     rax, [rsi+rdi]
0x18000b180  mov     byte ptr [rax+r14], 0
0x18000b185  jmp     short loc_18000B197
0x18000b187  mov     [rsp+0C0h+var_A0], rdi; Size
0x18000b18c  mov     rdx, rdi
0x18000b18f  mov     rcx, rbx; Src
0x18000b192  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x18000b197  mov     rcx, [rbx+10h]
0x18000b19b  cmp     rcx, [rbx+18h]
0x18000b19f  jnb     short loc_18000B1BF
0x18000b1a1  lea     rax, [rcx+1]
0x18000b1a5  mov     [rbx+10h], rax
0x18000b1a9  cmp     [rbx+18h], r12
0x18000b1ad  jbe     short loc_18000B1B4
0x18000b1af  mov     rax, [rbx]
0x18000b1b2  jmp     short loc_18000B1B7
0x18000b1b4  mov     rax, rbx
0x18000b1b7  mov     word ptr [rcx+rax], 22h ; '"'
0x18000b1bd  jmp     short loc_18000B1CB
0x18000b1bf  mov     r9b, 22h ; '"'
0x18000b1c2  mov     rcx, rbx; Src
0x18000b1c5  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18000b1ca  nop
0x18000b1cb  lea     rcx, [rbp+57h+var_68]
0x18000b1cf  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000b1d4  nop
0x18000b1d5  lea     rcx, [rbp+57h+Src]
0x18000b1d9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000b1de  mov     rax, rbx
0x18000b1e1  mov     rcx, [rbp+57h+var_28]
0x18000b1e5  xor     rcx, rsp; StackCookie
0x18000b1e8  call    __security_check_cookie
0x18000b1ed  lea     r11, [rsp+0C0h+var_20]
0x18000b1f5  mov     rbx, [r11+40h]
0x18000b1f9  mov     rsi, [r11+48h]
0x18000b1fd  mov     rsp, r11
0x18000b200  pop     r15
0x18000b202  pop     r14
0x18000b204  pop     r12
0x18000b206  pop     rdi
0x18000b207  pop     rbp
0x18000b208  retn
```
