# Csl::OfflineHive::SetMultiStringValue(ushort const *,ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> const &)

- ea: `0x18002bca8`
- end: `0x18002bf5d`
- name: `?SetMultiStringValue@OfflineHive@Csl@@QEAAJPEBG0AEBV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(Csl::OfflineHive *, const unsigned __int16 *, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180029264`
- `0x180029ef8`

## callees

- `0x180002164`
- `0x180002534`
- `0x180002c48`
- `0x1800045e4`
- `0x1800095f8`
- `0x180009e10`
- `0x18000d1b0`
- `0x18002bca8`
- `0x18002bf64`
- `0x1800361a8`

## string_xrefs

- `0x18002bcf8`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002be69`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::SetMultiStringValue(
        Csl::OfflineHive *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 *a4)
{
  void *v7; // rcx
  void *v8; // r15
  __int64 v9; // rbx
  unsigned __int64 v10; // r14
  __int64 v11; // rdx
  char *v12; // r8
  void *v13; // r9
  unsigned __int64 v14; // rbx
  __int64 v15; // rsi
  __int64 v16; // rbx
  __int64 v17; // rcx
  size_t v19; // rbx
  unsigned int v20; // ebx
  void *Src; // [rsp+30h] [rbp-49h] BYREF
  char *v22; // [rsp+38h] [rbp-41h]
  _WORD v23[8]; // [rsp+40h] [rbp-39h] BYREF
  void *v24; // [rsp+50h] [rbp-29h] BYREF
  char *v25; // [rsp+58h] [rbp-21h]
  _WORD v26[8]; // [rsp+60h] [rbp-19h] BYREF
  void *v27[2]; // [rsp+70h] [rbp-9h] BYREF
  _WORD v28[40]; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v24 = v26;
  v25 = (char *)v26;
  v26[0] = 0;
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(&v24) )
  {
    v8 = v24;
    v9 = *a4;
    Src = v23;
    v22 = (char *)v23;
    v23[0] = 0;
    v27[0] = v28;
    v10 = (v25 - (_BYTE *)v24) >> 1;
    v27[1] = v28;
    v28[0] = 0;
    while ( v9 != a4[1] )
    {
      if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
              (__int64)v27,
              *(const void **)v9,
              (__int64)(*(_QWORD *)(v9 + 8) - *(_QWORD *)v9) >> 1) )
        goto LABEL_9;
      v9 += 32;
      if ( v9 == a4[1] )
        break;
      if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
              (__int64)v27,
              v8,
              v10) )
      {
LABEL_9:
        if ( v27[0] != v28 )
          operator delete(v27[0], (const struct std::nothrow_t *)&std::nothrow);
        v11 = 716;
        goto LABEL_21;
      }
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      (__int64)&Src,
      (__int64)v27);
    if ( v27[0] != v28 )
      operator delete(v27[0], (const struct std::nothrow_t *)&std::nothrow);
    v12 = v22;
    v13 = Src;
    v14 = (*a4 != a4[1]) + ((v22 - (_BYTE *)Src) >> 1) + 1;
    if ( !v14 )
    {
      v15 = -1;
      v16 = -1;
LABEL_27:
      memcpy_0((void *)v15, v13, 2 * (unsigned int)((v12 - (_BYTE *)v13) >> 1) + 2);
      v20 = Csl::OfflineHive::SetValue(
              a1,
              a2,
              a3,
              (const unsigned __int8 *)v15,
              2 * (unsigned int)((v16 - v15) >> 1),
              7u);
      if ( v15 != -1 )
        operator delete((void *)v15, (const struct std::nothrow_t *)&std::nothrow);
      if ( Src != v23 )
        operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
      if ( v24 != v26 )
        operator delete(v24, (const struct std::nothrow_t *)&std::nothrow);
      return v20;
    }
    v17 = 8;
    if ( v14 > 8 )
    {
      if ( v14 > 0x3FFFFFFFFFFFFFFFLL )
        goto LABEL_20;
      v17 = (*a4 != a4[1]) + ((v22 - (_BYTE *)Src) >> 1) + 1;
    }
    v15 = (__int64)operator new(2 * v17, (const struct std::nothrow_t *)&std::nothrow);
    if ( ((v15 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v19 = 2 * v14;
      memset_0((void *)v15, 0, v19);
      v12 = v22;
      v16 = v15 + v19;
      v13 = Src;
      goto LABEL_27;
    }
LABEL_20:
    v11 = 722;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
      (const char *)0x8007000ELL);
    if ( Src != v23 )
      operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v24;
    if ( v24 == v26 )
      return 2147942414LL;
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2C8,
    (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
    (const char *)0x8007000ELL);
  v7 = v24;
  if ( v24 != v26 )
LABEL_24:
    operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18002bca8  mov     [rsp-8+arg_0], rcx
0x18002bcad  push    rbp
0x18002bcae  push    rbx
0x18002bcaf  push    rsi
0x18002bcb0  push    rdi
0x18002bcb1  push    r12
0x18002bcb3  push    r13
0x18002bcb5  push    r14
0x18002bcb7  push    r15
0x18002bcb9  lea     rbp, [rsp-1Fh]
0x18002bcbe  sub     rsp, 98h
0x18002bcc5  lea     rax, [rbp+57h+var_70]
0x18002bcc9  mov     r12, r8
0x18002bccc  mov     [rbp+57h+var_80], rax
0x18002bcd0  lea     rcx, [rbp+57h+var_80]
0x18002bcd4  lea     rax, [rbp+57h+var_70]
0x18002bcd8  xor     r8d, r8d
0x18002bcdb  mov     [rbp+57h+var_78], rax
0x18002bcdf  mov     rsi, r9
0x18002bce2  xor     eax, eax
0x18002bce4  mov     r13, rdx
0x18002bce7  mov     [rbp+57h+var_70], ax
0x18002bceb  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(unsigned __int64,ushort)
0x18002bcf0  test    al, al
0x18002bcf2  jnz     short loc_18002BD2C
0x18002bcf4  mov     rcx, [rbp+5Fh]; this
0x18002bcf8  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002bcff  mov     r9d, 8007000Eh; char *
0x18002bd05  mov     edx, 2C8h; void *
0x18002bd0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bd0f  mov     rcx, [rbp+57h+var_80]
0x18002bd13  lea     rax, [rbp+57h+var_70]
0x18002bd17  cmp     rcx, rax
0x18002bd1a  jz      loc_18002BEA5
0x18002bd20  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002bd27  jmp     loc_18002BEA0
0x18002bd2c  mov     r15, [rbp+57h+var_80]
0x18002bd30  lea     rax, [rbp+57h+var_90]
0x18002bd34  mov     r14, [rbp+57h+var_78]
0x18002bd38  mov     rbx, [rsi]
0x18002bd3b  sub     r14, r15
0x18002bd3e  mov     [rbp+57h+Src], rax
0x18002bd42  lea     rax, [rbp+57h+var_90]
0x18002bd46  mov     [rbp+57h+var_98], rax
0x18002bd4a  xor     eax, eax
0x18002bd4c  mov     [rbp+57h+var_90], ax
0x18002bd50  lea     rax, [rbp+57h+var_50]
0x18002bd54  mov     [rbp+57h+var_60], rax
0x18002bd58  lea     rax, [rbp+57h+var_50]
0x18002bd5c  sar     r14, 1
0x18002bd5f  mov     [rbp+57h+var_58], rax
0x18002bd63  xor     eax, eax
0x18002bd65  mov     [rbp+57h+var_50], ax
0x18002bd69  cmp     rbx, [rsi+8]
0x18002bd6d  jz      short loc_18002BDCC
0x18002bd6f  mov     r8, [rbx+8]
0x18002bd73  lea     rcx, [rbp+57h+var_60]
0x18002bd77  sub     r8, [rbx]
0x18002bd7a  mov     rdx, [rbx]
0x18002bd7d  sar     r8, 1
0x18002bd80  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18002bd85  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002bd8c  test    al, al
0x18002bd8e  jz      short loc_18002BDAD
0x18002bd90  add     rbx, 20h ; ' '
0x18002bd94  cmp     rbx, [rsi+8]
0x18002bd98  jz      short loc_18002BDCC
0x18002bd9a  mov     r8, r14
0x18002bd9d  lea     rcx, [rbp+57h+var_60]
0x18002bda1  mov     rdx, r15
0x18002bda4  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18002bda9  test    al, al
0x18002bdab  jnz     short loc_18002BD69
0x18002bdad  mov     rcx, [rbp+57h+var_60]; void *
0x18002bdb1  lea     rax, [rbp+57h+var_50]
0x18002bdb5  cmp     rcx, rax
0x18002bdb8  jz      short loc_18002BDC2
0x18002bdba  mov     rdx, rdi; struct std::nothrow_t *
0x18002bdbd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002bdc2  mov     edx, 2CCh
0x18002bdc7  jmp     loc_18002BE65
0x18002bdcc  lea     rdx, [rbp+57h+var_60]
0x18002bdd0  lea     rcx, [rbp+57h+Src]
0x18002bdd4  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x18002bdd9  mov     rcx, [rbp+57h+var_60]; void *
0x18002bddd  lea     rax, [rbp+57h+var_50]
0x18002bde1  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002bde8  cmp     rcx, rax
0x18002bdeb  jz      short loc_18002BDF5
0x18002bded  mov     rdx, rdi; struct std::nothrow_t *
0x18002bdf0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002bdf5  mov     r8, [rbp+57h+var_98]
0x18002bdf9  xor     ecx, ecx
0x18002bdfb  mov     r9, [rbp+57h+Src]
0x18002bdff  mov     rbx, r8
0x18002be02  mov     rax, [rsi+8]
0x18002be06  sub     rbx, r9
0x18002be09  sar     rbx, 1
0x18002be0c  cmp     [rsi], rax
0x18002be0f  setnz   cl
0x18002be12  inc     rbx
0x18002be15  add     rbx, rcx
0x18002be18  jnz     short loc_18002BE2B
0x18002be1a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002be1e  lea     rbx, ds:0FFFFFFFFFFFFFFFFh[rbx*2]
0x18002be26  jmp     loc_18002BECA
0x18002be2b  mov     ecx, 8
0x18002be30  cmp     rbx, rcx
0x18002be33  jbe     short loc_18002BE47
0x18002be35  mov     rax, 3FFFFFFFFFFFFFFFh
0x18002be3f  cmp     rbx, rax
0x18002be42  ja      short loc_18002BE60
0x18002be44  mov     rcx, rbx
0x18002be47  add     rcx, rcx; unsigned __int64
0x18002be4a  mov     rdx, rdi; struct std::nothrow_t *
0x18002be4d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002be52  mov     rsi, rax
0x18002be55  inc     rax
0x18002be58  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002be5e  jnz     short loc_18002BEAF
0x18002be60  mov     edx, 2D2h; void *
0x18002be65  mov     rcx, [rbp+5Fh]; this
0x18002be69  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002be70  mov     r9d, 8007000Eh; char *
0x18002be76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002be7b  mov     rcx, [rbp+57h+Src]; void *
0x18002be7f  lea     rax, [rbp+57h+var_90]
0x18002be83  cmp     rcx, rax
0x18002be86  jz      short loc_18002BE90
0x18002be88  mov     rdx, rdi; struct std::nothrow_t *
0x18002be8b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002be90  mov     rcx, [rbp+57h+var_80]; void *
0x18002be94  lea     rax, [rbp+57h+var_70]
0x18002be98  cmp     rcx, rax
0x18002be9b  jz      short loc_18002BEA5
0x18002be9d  mov     rdx, rdi; struct std::nothrow_t *
0x18002bea0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002bea5  mov     eax, 8007000Eh
0x18002beaa  jmp     loc_18002BF48
0x18002beaf  add     rbx, rbx
0x18002beb2  xor     edx, edx; Val
0x18002beb4  mov     r8, rbx; Size
0x18002beb7  mov     rcx, rsi; void *
0x18002beba  call    memset_0
0x18002bebf  mov     r8, [rbp+57h+var_98]
0x18002bec3  add     rbx, rsi
0x18002bec6  mov     r9, [rbp+57h+Src]
0x18002beca  sub     r8, r9
0x18002becd  mov     rdx, r9; Src
0x18002bed0  sar     r8, 1
0x18002bed3  mov     rcx, rsi; void *
0x18002bed6  lea     r8d, ds:2[r8*2]; Size
0x18002bede  call    memcpy_0
0x18002bee3  mov     rcx, [rbp+57h+arg_0]; this
0x18002bee7  sub     rbx, rsi
0x18002beea  sar     rbx, 1
0x18002beed  mov     r9, rsi; unsigned __int8 *
0x18002bef0  add     ebx, ebx
0x18002bef2  mov     [rsp+0D0h+var_A8], 7; unsigned int
0x18002befa  mov     r8, r12; unsigned __int16 *
0x18002befd  mov     [rsp+0D0h+var_B0], ebx; unsigned int
0x18002bf01  mov     rdx, r13; unsigned __int16 *
0x18002bf04  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x18002bf09  mov     ebx, eax
0x18002bf0b  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002bf0f  jz      short loc_18002BF1C
0x18002bf11  mov     rdx, rdi; struct std::nothrow_t *
0x18002bf14  mov     rcx, rsi; void *
0x18002bf17  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002bf1c  mov     rcx, [rbp+57h+Src]; void *
0x18002bf20  lea     rax, [rbp+57h+var_90]
0x18002bf24  cmp     rcx, rax
0x18002bf27  jz      short loc_18002BF31
0x18002bf29  mov     rdx, rdi; struct std::nothrow_t *
0x18002bf2c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002bf31  mov     rcx, [rbp+57h+var_80]; void *
0x18002bf35  lea     rax, [rbp+57h+var_70]
0x18002bf39  cmp     rcx, rax
0x18002bf3c  jz      short loc_18002BF46
0x18002bf3e  mov     rdx, rdi; struct std::nothrow_t *
0x18002bf41  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002bf46  mov     eax, ebx
0x18002bf48  add     rsp, 98h
0x18002bf4f  pop     r15
0x18002bf51  pop     r14
0x18002bf53  pop     r13
0x18002bf55  pop     r12
0x18002bf57  pop     rdi
0x18002bf58  pop     rsi
0x18002bf59  pop     rbx
0x18002bf5a  pop     rbp
0x18002bf5b  retn
```
