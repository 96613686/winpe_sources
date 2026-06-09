# DiskDataHelper::CreateDisplayName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,int,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180016f04`
- end: `0x18001716c`
- name: `?CreateDisplayName@DiskDataHelper@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KH00AEAV23@@Z`
- size: `616`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, unsigned int, _QWORD *, _QWORD *, _QWORD *Src)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180013bb0`

## callees

- `0x180001bf0`
- `0x180002030`
- `0x1800053f0`
- `0x18000591c`
- `0x1800092d8`
- `0x1800092f0`
- `0x18000937c`
- `0x180016f04`
- `0x18001724c`

## pseudocode

```c
__int64 __fastcall DiskDataHelper::CreateDisplayName(
        _QWORD *a1,
        unsigned int a2,
        unsigned int a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *Src)
{
  _WORD *v9; // rcx
  unsigned int v10; // ebx
  _QWORD *v11; // rdx
  __int64 v12; // rax
  _QWORD *v13; // r12
  __int64 v14; // rax
  unsigned __int64 v15; // r15
  char *v16; // rbx
  __int64 last_trivial_2; // rax
  unsigned __int64 v18; // r14
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rax
  _QWORD *v22; // rax
  unsigned __int64 v23; // r8
  _QWORD *v24; // rdx
  __int128 v26; // [rsp+28h] [rbp-48h] BYREF
  __int128 v27; // [rsp+38h] [rbp-38h]
  _OWORD v28[2]; // [rsp+48h] [rbp-28h] BYREF

  Src[2] = 0;
  if ( Src[3] <= 7u )
    v9 = Src;
  else
    v9 = (_WORD *)*Src;
  *v9 = 0;
  v28[0] = 0;
  v28[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v28[0]) = 0;
  DiskDataHelper::GetDriveTypeString(a2, a3, v28);
  v10 = a2 - 8;
  if ( !v10 )
  {
    v24 = v28;
    if ( a5[2] )
      v24 = a5;
    std::wstring::append(Src, v24);
    goto LABEL_31;
  }
  if ( v10 == 1 )
  {
    v12 = a4[2];
    if ( v12 )
    {
      if ( a4[3] <= 7u )
        v13 = a4;
      else
        v13 = (_QWORD *)*a4;
      v14 = v12 - 1;
      v15 = -1;
      if ( v14 == -1 )
        v14 = -1;
      v16 = (char *)v13 + 2 * v14 + 2;
      last_trivial_2 = _std_find_last_trivial_2(v13, v16, 92);
      if ( (char *)last_trivial_2 == v16 )
        v18 = -1;
      else
        v18 = (last_trivial_2 - (__int64)v13) >> 1;
      v19 = v18 + 1;
      v26 = 0;
      v27 = 0;
      v20 = a4[2];
      if ( v20 < v18 + 1 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
      v21 = v20 - v19;
      if ( v21 != -1 )
        v15 = v21;
      if ( a4[3] <= 7u )
        v22 = a4;
      else
        v22 = (_QWORD *)*a4;
      std::wstring::_Construct<1,unsigned short const *>(&v26, (char *)v22 + 2 * v19, v15);
      std::wstring::append(Src, &v26);
      std::wstring::~wstring((char **)&v26);
      std::wstring::append(Src, L" (");
      v26 = 0;
      v27 = 0;
      v23 = a4[2];
      if ( v23 >= v18 )
        v23 = v18;
      if ( a4[3] > 7u )
        a4 = (_QWORD *)*a4;
      std::wstring::_Construct<1,unsigned short const *>(&v26, a4, v23);
      std::wstring::append(Src, &v26);
      std::wstring::~wstring((char **)&v26);
      std::wstring::append(Src, L") ");
    }
LABEL_31:
    std::wstring::append(Src, L" (");
    v11 = a1;
    goto LABEL_32;
  }
  std::wstring::append(Src, v28);
  std::wstring::append(Src, L" (");
  std::wstring::append(Src, a1);
  std::wstring::append(Src, L") ");
  if ( a5[2] )
  {
    std::wstring::append(Src, L" (");
    v11 = a5;
LABEL_32:
    std::wstring::append(Src, v11);
    std::wstring::append(Src, L") ");
  }
  return std::wstring::~wstring((char **)v28);
}

```

## disassembly

```asm
0x180016f04  mov     [rsp-38h+arg_8], rbx
0x180016f09  push    rbp
0x180016f0a  push    rsi
0x180016f0b  push    rdi
0x180016f0c  push    r12
0x180016f0e  push    r13
0x180016f10  push    r14
0x180016f12  push    r15
0x180016f14  mov     rbp, rsp
0x180016f17  sub     rsp, 70h
0x180016f1b  mov     rax, cs:__security_cookie
0x180016f22  xor     rax, rsp
0x180016f25  mov     [rbp+var_8], rax
0x180016f29  mov     rsi, r9
0x180016f2c  mov     r9d, r8d
0x180016f2f  mov     ebx, edx
0x180016f31  mov     r13, rcx
0x180016f34  mov     r14, [rbp+arg_20]
0x180016f38  mov     rdi, [rbp+Src]
0x180016f3c  xor     r15d, r15d
0x180016f3f  mov     [rdi+10h], r15
0x180016f43  cmp     qword ptr [rdi+18h], 7
0x180016f48  jbe     short loc_180016F4F
0x180016f4a  mov     rcx, [rdi]
0x180016f4d  jmp     short loc_180016F52
0x180016f4f  mov     rcx, rdi
0x180016f52  mov     [rcx], r15w
0x180016f56  xorps   xmm0, xmm0
0x180016f59  movups  [rbp+var_28], xmm0
0x180016f5d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180016f65  movdqu  [rbp+var_18], xmm1
0x180016f6a  mov     word ptr [rbp+var_28], r15w
0x180016f6f  lea     r8, [rbp+var_28]
0x180016f73  mov     edx, r9d
0x180016f76  mov     ecx, ebx
0x180016f78  call    ?GetDriveTypeString@DiskDataHelper@@SAXKHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DiskDataHelper::GetDriveTypeString(ulong,int,std::wstring &)
0x180016f7d  sub     ebx, 8
0x180016f80  jz      loc_1800170FB
0x180016f86  cmp     ebx, 1
0x180016f89  jz      short loc_180016FE1
0x180016f8b  lea     rdx, [rbp+var_28]
0x180016f8f  mov     rcx, rdi; Src
0x180016f92  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180016f97  lea     rdx, asc_18001D374; " ("
0x180016f9e  mov     rcx, rdi; Src
0x180016fa1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180016fa6  mov     rdx, r13
0x180016fa9  mov     rcx, rdi; Src
0x180016fac  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180016fb1  lea     rdx, asc_18001D37C; ") "
0x180016fb8  mov     rcx, rdi; Src
0x180016fbb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180016fc0  cmp     [r14+10h], r15
0x180016fc4  jz      loc_180017139
0x180016fca  lea     rdx, asc_18001D374; " ("
0x180016fd1  mov     rcx, rdi; Src
0x180016fd4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180016fd9  mov     rdx, r14
0x180016fdc  jmp     loc_180017121
0x180016fe1  mov     rax, [rsi+10h]
0x180016fe5  test    rax, rax
0x180016fe8  jz      loc_18001710F
0x180016fee  cmp     qword ptr [rsi+18h], 7
0x180016ff3  jbe     short loc_180016FFA
0x180016ff5  mov     r12, [rsi]
0x180016ff8  jmp     short loc_180016FFD
0x180016ffa  mov     r12, rsi
0x180016ffd  dec     rax
0x180017000  or      r15, 0FFFFFFFFFFFFFFFFh
0x180017004  cmp     rax, r15
0x180017007  cmovnb  rax, r15
0x18001700b  inc     rax
0x18001700e  lea     rbx, [r12+rax*2]
0x180017012  lea     r8d, [r15+5Dh]
0x180017016  mov     rdx, rbx
0x180017019  mov     rcx, r12
0x18001701c  call    __std_find_last_trivial_2
0x180017021  mov     r14, rax
0x180017024  cmp     rax, rbx
0x180017027  jz      short loc_180017031
0x180017029  sub     r14, r12
0x18001702c  sar     r14, 1
0x18001702f  jmp     short loc_180017034
0x180017031  mov     r14, r15
0x180017034  lea     rcx, [r14+1]
0x180017038  xorps   xmm0, xmm0
0x18001703b  movups  [rbp+var_48], xmm0
0x18001703f  xorps   xmm1, xmm1
0x180017042  movdqu  [rbp+var_38], xmm1
0x180017047  mov     rax, [rsi+10h]
0x18001704b  cmp     rax, rcx
0x18001704e  jb      loc_180017166
0x180017054  sub     rax, rcx
0x180017057  cmp     rax, r15
0x18001705a  cmovb   r15, rax
0x18001705e  cmp     qword ptr [rsi+18h], 7
0x180017063  jbe     short loc_18001706A
0x180017065  mov     rax, [rsi]
0x180017068  jmp     short loc_18001706D
0x18001706a  mov     rax, rsi
0x18001706d  lea     rdx, [rax+rcx*2]
0x180017071  mov     r8, r15
0x180017074  lea     rcx, [rbp+var_48]
0x180017078  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001707d  nop
0x18001707e  lea     rdx, [rbp+var_48]
0x180017082  mov     rcx, rdi; Src
0x180017085  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18001708a  nop
0x18001708b  lea     rcx, [rbp+var_48]
0x18001708f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017094  lea     rdx, asc_18001D374; " ("
0x18001709b  mov     rcx, rdi; Src
0x18001709e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800170a3  xorps   xmm0, xmm0
0x1800170a6  movups  [rbp+var_48], xmm0
0x1800170aa  xorps   xmm1, xmm1
0x1800170ad  movdqu  [rbp+var_38], xmm1
0x1800170b2  mov     r8, [rsi+10h]
0x1800170b6  cmp     r8, r14
0x1800170b9  cmovnb  r8, r14
0x1800170bd  cmp     qword ptr [rsi+18h], 7
0x1800170c2  jbe     short loc_1800170C7
0x1800170c4  mov     rsi, [rsi]
0x1800170c7  mov     rdx, rsi
0x1800170ca  lea     rcx, [rbp+var_48]
0x1800170ce  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800170d3  nop
0x1800170d4  lea     rdx, [rbp+var_48]
0x1800170d8  mov     rcx, rdi; Src
0x1800170db  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800170e0  nop
0x1800170e1  lea     rcx, [rbp+var_48]
0x1800170e5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800170ea  lea     rdx, asc_18001D37C; ") "
0x1800170f1  mov     rcx, rdi; Src
0x1800170f4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800170f9  jmp     short loc_18001710F
0x1800170fb  lea     rdx, [rbp+var_28]
0x1800170ff  cmp     [r14+10h], r15
0x180017103  cmovnz  rdx, r14
0x180017107  mov     rcx, rdi; Src
0x18001710a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18001710f  lea     rdx, asc_18001D374; " ("
0x180017116  mov     rcx, rdi; Src
0x180017119  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001711e  mov     rdx, r13
0x180017121  mov     rcx, rdi; Src
0x180017124  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180017129  lea     rdx, asc_18001D37C; ") "
0x180017130  mov     rcx, rdi; Src
0x180017133  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180017138  nop
0x180017139  lea     rcx, [rbp+var_28]
0x18001713d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017142  mov     rcx, [rbp+var_8]
0x180017146  xor     rcx, rsp; StackCookie
0x180017149  call    __security_check_cookie
0x18001714e  mov     rbx, [rsp+70h+arg_8]
0x180017156  add     rsp, 70h
0x18001715a  pop     r15
0x18001715c  pop     r14
0x18001715e  pop     r13
0x180017160  pop     r12
0x180017162  pop     rdi
0x180017163  pop     rsi
0x180017164  pop     rbp
0x180017165  retn
0x180017166  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
