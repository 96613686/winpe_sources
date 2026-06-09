# std::filesystem::filesystem_error::filesystem_error(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::filesystem::path const &,std::error_code)

- ea: `0x1800215a0`
- end: `0x1800217c8`
- name: `??0filesystem_error@filesystem@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBVpath@12@Verror_code@2@@Z`
- size: `552`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180022794`
- `0x1800227ec`

## callees

- `0x1800028f0`
- `0x1800032f6`
- `0x18001c81c`
- `0x1800203bc`
- `0x18002057c`
- `0x180020634`
- `0x1800215a0`
- `0x180022590`
- `0x1800228d4`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall std::filesystem::filesystem_error::filesystem_error(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        unsigned int *a4)
{
  unsigned int v6; // r12d
  unsigned int v7; // ebx
  __int64 v8; // r14
  __int64 v9; // r8
  const char *v10; // rax
  const char **v11; // r15
  _QWORD *v12; // rdx
  const char *v13; // rcx
  __int64 v14; // rax
  const char *p_Src; // [rsp+20h] [rbp-69h] BYREF
  __int64 v17; // [rsp+28h] [rbp-61h]
  __int128 Src; // [rsp+30h] [rbp-59h] BYREF
  __m128i v19; // [rsp+40h] [rbp-49h]
  __int64 v20; // [rsp+50h] [rbp-39h]
  __int128 v21; // [rsp+60h] [rbp-29h] BYREF
  __m128i si128; // [rsp+70h] [rbp-19h]
  _QWORD v23[2]; // [rsp+80h] [rbp-9h] BYREF

  v20 = a1;
  v6 = *a4;
  v7 = a4[1];
  v8 = *((_QWORD *)a4 + 1);
  Src = 0;
  v19 = 0u;
  v9 = a2[2];
  if ( a2[3] > 0xFu )
    a2 = (_QWORD *)*a2;
  std::string::_Construct<2,char const *>(&Src, a2, v9);
  p_Src = (const char *)&Src;
  if ( v19.m128i_i64[0] )
    std::string::_Append<char>(&Src);
  (*(void (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v8 + 16LL))(v8, v23, v6);
  std::string::_Append<char>(&Src);
  std::string::_Tidy_deallocate(v23);
  v21 = Src;
  si128 = v19;
  v19.m128i_i64[0] = 0;
  v19.m128i_i64[1] = 15;
  LOBYTE(Src) = 0;
  std::string::_Tidy_deallocate(&Src);
  v10 = (const char *)&v21;
  if ( si128.m128i_i64[1] > 0xFuLL )
    v10 = (const char *)v21;
  *(_QWORD *)a1 = &std::exception::`vftable';
  v11 = (const char **)(a1 + 8);
  *(_OWORD *)(a1 + 8) = 0;
  p_Src = v10;
  v17 = 1;
  o___std_exception_copy_0(&p_Src, a1 + 8);
  *(_QWORD *)a1 = &std::runtime_error::`vftable';
  std::string::_Tidy_deallocate(&v21);
  *(_DWORD *)(a1 + 24) = v6;
  *(_DWORD *)(a1 + 28) = v7;
  *(_QWORD *)(a1 + 32) = v8;
  *(_QWORD *)a1 = &std::filesystem::filesystem_error::`vftable';
  *(_OWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  if ( a3[3] <= 7u )
    v12 = a3;
  else
    v12 = (_QWORD *)*a3;
  std::wstring::_Construct<2,unsigned short const *>(a1 + 40, v12, a3[2]);
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 7;
  *(_WORD *)(a1 + 72) = 0;
  v21 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v21) = 0;
  v13 = "Unknown exception";
  if ( *v11 )
    v13 = *v11;
  v14 = -1;
  do
    ++v14;
  while ( v13[v14] );
  p_Src = v13;
  v17 = v14;
  std::filesystem::filesystem_error::_Pretty_message((void *)(a1 + 104));
  std::wstring::_Tidy_deallocate(&v21);
  return a1;
}

```

## disassembly

```asm
0x1800215a0  push    rbp
0x1800215a2  push    rbx
0x1800215a3  push    rsi
0x1800215a4  push    rdi
0x1800215a5  push    r12
0x1800215a7  push    r14
0x1800215a9  push    r15
0x1800215ab  lea     rbp, [rsp-27h]
0x1800215b0  sub     rsp, 0B0h
0x1800215b7  mov     rax, cs:__security_cookie
0x1800215be  xor     rax, rsp
0x1800215c1  mov     [rbp+57h+var_40], rax
0x1800215c5  mov     rsi, r8
0x1800215c8  mov     rdi, rcx
0x1800215cb  mov     [rbp+57h+var_90], rcx
0x1800215cf  mov     r12d, [r9]
0x1800215d2  mov     ebx, [r9+4]
0x1800215d6  mov     r14, [r9+8]
0x1800215da  xorps   xmm0, xmm0
0x1800215dd  movups  [rbp+57h+Src], xmm0
0x1800215e1  mov     qword ptr [rbp+57h+var_A0], 0
0x1800215e9  mov     qword ptr [rbp+57h+var_A0+8], 0
0x1800215f1  mov     r8, [rdx+10h]
0x1800215f5  mov     r15d, 0Fh
0x1800215fb  cmp     [rdx+18h], r15
0x1800215ff  jbe     short loc_180021604
0x180021601  mov     rdx, [rdx]
0x180021604  lea     rcx, [rbp+57h+Src]
0x180021608  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x18002160d  lea     rax, [rbp+57h+Src]
0x180021611  mov     [rbp+57h+var_C0], rax
0x180021615  cmp     qword ptr [rbp+57h+var_A0], 0
0x18002161a  jz      short loc_180021632
0x18002161c  mov     r8d, 2
0x180021622  lea     rdx, asc_180030F28; ": "
0x180021629  lea     rcx, [rbp+57h+Src]; Src
0x18002162d  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180021632  mov     rax, [r14]
0x180021635  mov     r8d, r12d
0x180021638  lea     rdx, [rbp+57h+var_60]
0x18002163c  mov     rcx, r14
0x18002163f  mov     rax, [rax+10h]
0x180021643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021648  nop
0x180021649  lea     rdx, [rbp+57h+var_60]
0x18002164d  cmp     [rbp+57h+var_48], r15
0x180021651  cmova   rdx, [rbp+57h+var_60]
0x180021656  mov     r8, [rbp+57h+var_50]
0x18002165a  lea     rcx, [rbp+57h+Src]; Src
0x18002165e  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180021663  nop
0x180021664  lea     rcx, [rbp+57h+var_60]
0x180021668  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002166d  movups  xmm0, [rbp+57h+Src]
0x180021671  movups  [rbp+57h+var_80], xmm0
0x180021675  movups  xmm1, [rbp+57h+var_A0]
0x180021679  movups  [rbp+57h+var_70], xmm1
0x18002167d  mov     qword ptr [rbp+57h+var_A0], 0
0x180021685  mov     qword ptr [rbp+57h+var_A0+8], r15
0x180021689  mov     byte ptr [rbp+57h+Src], 0
0x18002168d  lea     rcx, [rbp+57h+Src]
0x180021691  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180021696  lea     rax, [rbp+57h+var_80]
0x18002169a  cmp     qword ptr [rbp+57h+var_70+8], r15
0x18002169e  cmova   rax, qword ptr [rbp+57h+var_80]
0x1800216a3  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800216aa  mov     [rdi], rcx
0x1800216ad  lea     r15, [rdi+8]
0x1800216b1  xorps   xmm0, xmm0
0x1800216b4  movups  xmmword ptr [r15], xmm0
0x1800216b8  mov     [rbp+57h+var_C0], rax
0x1800216bc  mov     byte ptr [rbp+57h+var_B8], 1
0x1800216c0  xor     eax, eax
0x1800216c2  mov     dword ptr [rbp+57h+var_B8+1], eax
0x1800216c5  mov     word ptr [rbp+57h+var_B8+5], ax
0x1800216c9  mov     byte ptr [rbp+57h+var_B8+7], al
0x1800216cc  mov     rdx, r15
0x1800216cf  lea     rcx, [rbp+57h+var_C0]
0x1800216d3  call    _o___std_exception_copy_0
0x1800216d8  lea     rax, ??_7runtime_error@std@@6B@; const std::runtime_error::`vftable'
0x1800216df  mov     [rdi], rax
0x1800216e2  lea     rcx, [rbp+57h+var_80]
0x1800216e6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800216eb  mov     [rdi+18h], r12d
0x1800216ef  mov     [rdi+1Ch], ebx
0x1800216f2  mov     [rdi+20h], r14
0x1800216f6  lea     rax, ??_7filesystem_error@filesystem@std@@6B@; const std::filesystem::filesystem_error::`vftable'
0x1800216fd  mov     [rdi], rax
0x180021700  lea     rcx, [rdi+28h]
0x180021704  xorps   xmm0, xmm0
0x180021707  movups  xmmword ptr [rcx], xmm0
0x18002170a  mov     qword ptr [rcx+10h], 0
0x180021712  mov     qword ptr [rcx+18h], 0
0x18002171a  cmp     qword ptr [rsi+18h], 7
0x18002171f  jbe     short loc_180021726
0x180021721  mov     rdx, [rsi]
0x180021724  jmp     short loc_180021729
0x180021726  mov     rdx, rsi
0x180021729  mov     r8, [rsi+10h]
0x18002172d  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180021732  nop
0x180021733  xorps   xmm0, xmm0
0x180021736  movups  xmmword ptr [rdi+48h], xmm0
0x18002173a  mov     qword ptr [rdi+58h], 0
0x180021742  mov     qword ptr [rdi+60h], 7
0x18002174a  xor     eax, eax
0x18002174c  mov     [rdi+48h], ax
0x180021750  movups  [rbp+57h+var_80], xmm0
0x180021754  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002175c  movdqu  [rbp+57h+var_70], xmm1
0x180021761  mov     word ptr [rbp+57h+var_80], ax
0x180021765  lea     rcx, aUnknownExcepti; "Unknown exception"
0x18002176c  cmp     [r15], rax
0x18002176f  cmovnz  rcx, [r15]
0x180021773  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021777  inc     rax
0x18002177a  cmp     byte ptr [rcx+rax], 0
0x18002177e  jnz     short loc_180021777
0x180021780  mov     [rbp+57h+var_C0], rcx
0x180021784  mov     [rbp+57h+var_B8], rax
0x180021788  lea     rcx, [rdi+68h]; Src
0x18002178c  lea     r9, [rbp+57h+var_80]
0x180021790  mov     r8, rsi
0x180021793  lea     rdx, [rbp+57h+var_C0]
0x180021797  call    ?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z; std::filesystem::filesystem_error::_Pretty_message(std::string_view,std::filesystem::path const &,std::filesystem::path const &)
0x18002179c  nop
0x18002179d  lea     rcx, [rbp+57h+var_80]
0x1800217a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800217a6  nop
0x1800217a7  mov     rax, rdi
0x1800217aa  mov     rcx, [rbp+57h+var_40]
0x1800217ae  xor     rcx, rsp; StackCookie
0x1800217b1  call    __security_check_cookie
0x1800217b6  add     rsp, 0B0h
0x1800217bd  pop     r15
0x1800217bf  pop     r14
0x1800217c1  pop     r12
0x1800217c3  pop     rdi
0x1800217c4  pop     rsi
0x1800217c5  pop     rbx
0x1800217c6  pop     rbp
0x1800217c7  retn
```
