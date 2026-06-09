# CbsLanguageSession::InstalledLanguageFeaturesOfType(PayloadType,bool)

- ea: `0x180024388`
- end: `0x180024631`
- name: `?InstalledLanguageFeaturesOfType@CbsLanguageSession@@QEBA?AV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@W4PayloadType@@_N@Z`
- size: `681`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180024198`

## callees

- `0x180003520`
- `0x180004100`
- `0x18000410c`
- `0x1800058dc`
- `0x180005954`
- `0x180006380`
- `0x18000a844`
- `0x18000b6b4`
- `0x180023fdc`
- `0x180024388`

## pseudocode

```c
__int64 __fastcall CbsLanguageSession::InstalledLanguageFeaturesOfType(__int64 a1, __int64 a2)
{
  wchar_t **v3; // rax
  __int64 **v4; // rdx
  unsigned __int64 v5; // r8
  __m128i *v6; // rdi
  unsigned __int64 v7; // rbx
  __m128i v8; // kr00_16
  unsigned __int64 v9; // r12
  __m128i *v10; // rax
  void **v11; // rdx
  size_t v12; // r8
  char *v13; // rcx
  char *v14; // r15
  __int64 v15; // rbx
  __int64 v16; // rcx
  _QWORD *v17; // r15
  size_t v18; // rbx
  void **v19; // rdx
  __int64 v21; // [rsp+30h] [rbp-79h] BYREF
  void *Src[2]; // [rsp+38h] [rbp-71h] BYREF
  __m128i si128; // [rsp+48h] [rbp-61h]
  __int64 v24; // [rsp+60h] [rbp-49h]
  _OWORD v25[2]; // [rsp+68h] [rbp-41h] BYREF
  char *v26[4]; // [rsp+88h] [rbp-21h] BYREF
  __m128i v27; // [rsp+A8h] [rbp-1h] BYREF
  __m128i v28; // [rsp+B8h] [rbp+Fh]

  v24 = a1;
  v21 = a2;
  v3 = &off_18002B6B0;
  do
  {
    if ( *((_DWORD *)v3 + 2) == 256 )
      break;
    v3 += 2;
  }
  while ( v3 != (wchar_t **)&Feature_TestAccPerf__private_requiresFeatures );
  v4 = (__int64 **)*v3;
  *(_OWORD *)Src = 0;
  si128 = 0;
  v5 = -1;
  do
    ++v5;
  while ( *((_WORD *)v4 + v5) );
  std::wstring::_Construct<1,unsigned short const *>((__int64)Src, v4, v5);
  memset(v25, 0, sizeof(v25));
  std::wstring::_Construct<1,unsigned short const *>((__int64)v25, L"Language", 8u);
  v6 = (__m128i *)std::operator+<unsigned short>(v26, v25, L".");
  v27 = 0;
  v28 = 0;
  v7 = v6[1].m128i_u64[0];
  v8 = si128;
  v9 = v7 + si128.m128i_i64[0];
  if ( si128.m128i_i64[0] <= v6[1].m128i_i64[1] - v7 && si128.m128i_i64[1] <= (unsigned __int64)v6[1].m128i_i64[1] )
  {
    v27 = *v6;
    v28 = v6[1];
    v6[1].m128i_i64[0] = 0;
    v6[1].m128i_i64[1] = 7;
    v6->m128i_i16[0] = 0;
    v10 = &v27;
    if ( v28.m128i_i64[1] > 7uLL )
      v10 = (__m128i *)v27.m128i_i64[0];
    v11 = Src;
    if ( v8.m128i_i64[1] > 7uLL )
      v11 = (void **)Src[0];
    v12 = 2 * v8.m128i_i64[0] + 2;
    v13 = &v10->m128i_i8[2 * v7];
LABEL_13:
    memcpy_0(v13, v11, v12);
    v28.m128i_i64[0] = v9;
    goto LABEL_27;
  }
  if ( v7 <= si128.m128i_i64[1] - si128.m128i_i64[0] )
  {
    v27 = *(__m128i *)Src;
    v28 = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Src[0]) = 0;
    v14 = (char *)v27.m128i_i64[0];
    v15 = 2 * v7;
    memmove_0((void *)(v15 + v27.m128i_i64[0]), (const void *)v27.m128i_i64[0], 2 * v8.m128i_i64[0] + 2);
    if ( v6[1].m128i_i64[1] > 7uLL )
      v6 = (__m128i *)v6->m128i_i64[0];
    v12 = v15;
    v11 = (void **)v6;
    v13 = v14;
    goto LABEL_13;
  }
  v16 = 0x7FFFFFFFFFFFFFFELL;
  if ( 0x7FFFFFFFFFFFFFFELL - v7 < si128.m128i_i64[0] )
    std::_Xlen_string();
  if ( (v9 | 7) <= 0x7FFFFFFFFFFFFFFELL )
  {
    v16 = v9 | 7;
    if ( (v9 | 7) < 0xA )
      v16 = 10;
  }
  v21 = v16;
  v17 = std::wstring::_Allocate_for_capacity<0>(v16, &v21);
  v27.m128i_i64[0] = (__int64)v17;
  v28.m128i_i64[0] = v9;
  v28.m128i_i64[1] = v21;
  if ( v6[1].m128i_i64[1] > 7uLL )
    v6 = (__m128i *)v6->m128i_i64[0];
  v18 = 2 * v7;
  memcpy_0(v17, v6, v18);
  v19 = Src;
  if ( v8.m128i_i64[1] > 7uLL )
    v19 = (void **)Src[0];
  memcpy_0((char *)v17 + v18, v19, 2 * v8.m128i_i64[0] + 2);
LABEL_27:
  std::wstring::~wstring(v26);
  std::wstring::~wstring((char **)v25);
  std::wstring::~wstring((char **)Src);
  CbsSession::FeaturesOfCapability<CbsLanguageFeature,bool (CbsLanguageFeature const &)>(
    v24,
    a2,
    (unsigned int)&v27,
    1,
    (__int64)CbsLanguageSession::IsInstalled);
  std::wstring::~wstring((char **)&v27);
  return a2;
}

```

## disassembly

```asm
0x180024388  mov     [rsp-8+arg_10], rbx
0x18002438d  push    rbp
0x18002438e  push    rsi
0x18002438f  push    rdi
0x180024390  push    r12
0x180024392  push    r13
0x180024394  push    r14
0x180024396  push    r15
0x180024398  lea     rbp, [rsp-27h]
0x18002439d  sub     rsp, 0D0h
0x1800243a4  mov     rax, cs:__security_cookie
0x1800243ab  xor     rax, rsp
0x1800243ae  mov     [rbp+57h+var_38], rax
0x1800243b2  mov     r14, rdx
0x1800243b5  mov     [rbp+57h+var_A0], rcx
0x1800243b9  mov     [rbp+57h+var_D0], rdx
0x1800243bd  xor     r15d, r15d
0x1800243c0  lea     rax, off_18002B6B0; "Basic"
0x1800243c7  cmp     dword ptr [rax+8], 100h
0x1800243ce  jz      short loc_1800243E0
0x1800243d0  add     rax, 10h
0x1800243d4  lea     rcx, Feature_TestAccPerf__private_requiresFeatures
0x1800243db  cmp     rax, rcx
0x1800243de  jnz     short loc_1800243C7
0x1800243e0  mov     rdx, [rax]
0x1800243e3  xorps   xmm0, xmm0
0x1800243e6  movups  xmmword ptr [rbp+57h+Src], xmm0
0x1800243ea  xorps   xmm1, xmm1
0x1800243ed  movdqu  [rbp+57h+var_B8], xmm1
0x1800243f2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800243f6  inc     r8
0x1800243f9  cmp     [rdx+r8*2], r15w
0x1800243fe  jnz     short loc_1800243F6
0x180024400  lea     rcx, [rbp+57h+Src]
0x180024404  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180024409  nop
0x18002440a  xorps   xmm0, xmm0
0x18002440d  movups  [rbp+57h+var_98], xmm0
0x180024411  xorps   xmm1, xmm1
0x180024414  movdqu  [rbp+57h+var_88], xmm1
0x180024419  mov     r8d, 8
0x18002441f  lea     rdx, aLanguage; "Language"
0x180024426  lea     rcx, [rbp+57h+var_98]
0x18002442a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002442f  nop
0x180024430  lea     r8, S; "."
0x180024437  lea     rdx, [rbp+57h+var_98]
0x18002443b  lea     rcx, [rbp+57h+var_78]
0x18002443f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180024444  mov     rdi, rax
0x180024447  xorps   xmm0, xmm0
0x18002444a  movups  [rbp+57h+var_58], xmm0
0x18002444e  xorps   xmm1, xmm1
0x180024451  movdqu  [rbp+57h+var_48], xmm1
0x180024456  mov     rbx, [rax+10h]
0x18002445a  mov     rsi, qword ptr [rbp+57h+var_B8]
0x18002445e  mov     r13, qword ptr [rbp+57h+var_B8+8]
0x180024462  lea     r12, [rbx+rsi]
0x180024466  mov     rax, [rax+18h]
0x18002446a  sub     rax, rbx
0x18002446d  cmp     rsi, rax
0x180024470  ja      short loc_1800244CC
0x180024472  cmp     r13, [rdi+18h]
0x180024476  ja      short loc_1800244CC
0x180024478  movups  xmm0, xmmword ptr [rdi]
0x18002447b  movups  [rbp+57h+var_58], xmm0
0x18002447f  movups  xmm1, xmmword ptr [rdi+10h]
0x180024483  movups  [rbp+57h+var_48], xmm1
0x180024487  mov     [rdi+10h], r15
0x18002448b  mov     qword ptr [rdi+18h], 7
0x180024493  mov     [rdi], r15w
0x180024497  lea     rax, [rbp+57h+var_58]
0x18002449b  cmp     qword ptr [rbp+57h+var_48+8], 7
0x1800244a0  cmova   rax, qword ptr [rbp+57h+var_58]
0x1800244a5  lea     rdx, [rbp+57h+Src]
0x1800244a9  cmp     r13, 7
0x1800244ad  cmova   rdx, [rbp+57h+Src]; Src
0x1800244b2  lea     r8, ds:2[rsi*2]; Size
0x1800244ba  lea     rcx, [rax+rbx*2]; void *
0x1800244be  call    memcpy_0
0x1800244c3  mov     qword ptr [rbp+57h+var_48], r12
0x1800244c7  jmp     loc_1800245B8
0x1800244cc  mov     rax, r13
0x1800244cf  sub     rax, rsi
0x1800244d2  cmp     rbx, rax
0x1800244d5  ja      short loc_18002452A
0x1800244d7  movups  xmm2, xmmword ptr [rbp+57h+Src]
0x1800244db  movups  [rbp+57h+var_58], xmm2
0x1800244df  movups  xmm0, [rbp+57h+var_B8]
0x1800244e3  movups  [rbp+57h+var_48], xmm0
0x1800244e7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800244ef  movdqu  [rbp+57h+var_B8], xmm1
0x1800244f4  mov     word ptr [rbp+57h+Src], r15w
0x1800244f9  movq    r15, xmm2
0x1800244fe  add     rbx, rbx
0x180024501  lea     r8, ds:2[rsi*2]; Size
0x180024509  lea     rcx, [rbx+r15]; void *
0x18002450d  mov     rdx, r15; Src
0x180024510  call    memmove_0
0x180024515  cmp     qword ptr [rdi+18h], 7
0x18002451a  jbe     short loc_18002451F
0x18002451c  mov     rdi, [rdi]
0x18002451f  mov     r8, rbx
0x180024522  mov     rdx, rdi
0x180024525  mov     rcx, r15
0x180024528  jmp     short loc_1800244BE
0x18002452a  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180024534  mov     rax, rcx
0x180024537  sub     rax, rbx
0x18002453a  cmp     rax, rsi
0x18002453d  jb      loc_18002462B
0x180024543  mov     rax, r12
0x180024546  or      rax, 7
0x18002454a  cmp     rax, rcx
0x18002454d  ja      short loc_18002455E
0x18002454f  mov     rcx, rax
0x180024552  mov     edx, 0Ah
0x180024557  cmp     rax, rdx
0x18002455a  cmovb   rcx, rdx
0x18002455e  mov     [rbp+57h+var_D0], rcx
0x180024562  lea     rdx, [rbp+57h+var_D0]
0x180024566  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x18002456b  mov     r15, rax
0x18002456e  mov     qword ptr [rbp+57h+var_58], rax
0x180024572  mov     qword ptr [rbp+57h+var_48], r12
0x180024576  mov     rax, [rbp+57h+var_D0]
0x18002457a  mov     qword ptr [rbp+57h+var_48+8], rax
0x18002457e  cmp     qword ptr [rdi+18h], 7
0x180024583  jbe     short loc_180024588
0x180024585  mov     rdi, [rdi]
0x180024588  add     rbx, rbx
0x18002458b  mov     r8, rbx; Size
0x18002458e  mov     rdx, rdi; Src
0x180024591  mov     rcx, r15; void *
0x180024594  call    memcpy_0
0x180024599  lea     rdx, [rbp+57h+Src]
0x18002459d  cmp     r13, 7
0x1800245a1  cmova   rdx, [rbp+57h+Src]; Src
0x1800245a6  lea     r8, ds:2[rsi*2]; Size
0x1800245ae  lea     rcx, [rbx+r15]; void *
0x1800245b2  call    memcpy_0
0x1800245b7  nop
0x1800245b8  lea     rcx, [rbp+57h+var_78]; void *
0x1800245bc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800245c1  nop
0x1800245c2  lea     rcx, [rbp+57h+var_98]; void *
0x1800245c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800245cb  nop
0x1800245cc  lea     rcx, [rbp+57h+Src]; void *
0x1800245d0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800245d5  lea     rax, ?IsInstalled@CbsLanguageSession@@CA_NAEBVCbsLanguageFeature@@@Z; CbsLanguageSession::IsInstalled(CbsLanguageFeature const &)
0x1800245dc  mov     [rsp+100h+var_E0], rax
0x1800245e1  mov     r9d, 1
0x1800245e7  lea     r8, [rbp+57h+var_58]
0x1800245eb  mov     rdx, r14
0x1800245ee  mov     rcx, [rbp+57h+var_A0]
0x1800245f2  call    ??$FeaturesOfCapability@VCbsLanguageFeature@@$$A6A_NAEBV1@@Z@CbsSession@@QEBA?AV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@IA6A_NAEBVCbsLanguageFeature@@@Z@Z; CbsSession::FeaturesOfCapability<CbsLanguageFeature,bool (CbsLanguageFeature const &)>(std::wstring const &,uint,bool (&)(CbsLanguageFeature const &))
0x1800245f7  nop
0x1800245f8  lea     rcx, [rbp+57h+var_58]; void *
0x1800245fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024601  mov     rax, r14
0x180024604  mov     rcx, [rbp+57h+var_38]
0x180024608  xor     rcx, rsp; StackCookie
0x18002460b  call    __security_check_cookie
0x180024610  mov     rbx, [rsp+100h+arg_10]
0x180024618  add     rsp, 0D0h
0x18002461f  pop     r15
0x180024621  pop     r14
0x180024623  pop     r13
0x180024625  pop     r12
0x180024627  pop     rdi
0x180024628  pop     rsi
0x180024629  pop     rbp
0x18002462a  retn
0x18002462b  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
