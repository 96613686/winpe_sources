# winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::UnpinModelPackage(winrt::hstring const &)

- ea: `0x180008700`
- end: `0x180008a50`
- name: `?UnpinModelPackage@ApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@QEAAXAEBUhstring@6@@Z`
- size: `848`
- prototype: `void __fastcall(winrt::Microsoft::Windows::Workloads::implementation::ApiInfo *__hidden this, const struct winrt::hstring *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a510`
- `0x18003d1ad`

## callees

- `0x1800027d0`
- `0x180002880`
- `0x1800029f0`
- `0x180008610`
- `0x180008700`
- `0x180010240`
- `0x180011190`
- `0x180013060`
- `0x180013420`
- `0x180032340`
- `0x180034ef0`
- `0x18003c020`
- `0x18003c6e0`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-5!DeletePackageDependency` at `0x1800089d8`
- `api-ms-win-appmodel-runtime-l1-1-5!DeletePackageDependency` at `0x1800089d8`

## string_xrefs

- `0x180008974`: `Failed to remove package dependency for id: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::UnpinModelPackage(
        winrt::Microsoft::Windows::Workloads::implementation::ApiInfo *this,
        const struct winrt::hstring *a2)
{
  const wchar_t *v3; // rdx
  unsigned __int64 v4; // r8
  void **v5; // rsi
  int v6; // eax
  signed __int64 v7; // rbx
  _QWORD *v8; // rdi
  __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  unsigned __int16 *v11; // rsi
  unsigned __int16 *v12; // r8
  __int64 v13; // rax
  const char *v14; // rbx
  char **v15; // rcx
  unsigned int v16; // eax
  void *Src[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v18; // [rsp+48h] [rbp-B8h]
  char *v19; // [rsp+58h] [rbp-A8h]
  char *v20[2]; // [rsp+60h] [rbp-A0h] BYREF
  __m128i si128; // [rsp+70h] [rbp-90h]
  __int128 v22; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+90h] [rbp-70h]
  _OWORD v24[16]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v22 = 0;
  v23 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v22, L";", 1u);
  memset(v24, 0, 0xF8u);
  if ( *(_QWORD *)a2 )
    v3 = *(const wchar_t **)(*(_QWORD *)a2 + 16LL);
  else
    v3 = &::Src;
  *(_OWORD *)Src = 0;
  v18 = 0;
  v4 = -1;
  do
    ++v4;
  while ( v3[v4] );
  std::wstring::_Construct<1,wchar_t const *>(Src, v3, v4);
  *(_QWORD *)&v24[0] = &std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbtable'{for `std::wistream'};
  *(_QWORD *)&v24[1] = &std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbtable'{for `std::wostream'};
  memset(&v24[10], 0, 20);
  *((_QWORD *)&v24[11] + 1) = 0;
  memset(&v24[12], 0, 50);
  *((_QWORD *)&v24[9] + 1) = &std::wistream::`vftable';
  DWORD1(v24[9]) = 128;
  *((_QWORD *)&v24[0] + 1) = 0;
  std::wios::init((char *)&v24[9] + 8, (char *)&v24[1] + 8);
  *(_QWORD *)((char *)&v24[1] + *(int *)(*(_QWORD *)&v24[1] + 4LL)) = &std::wostream::`vftable';
  *(_DWORD *)((char *)v24 + *(int *)(*(_QWORD *)&v24[1] + 4LL) + 12) = *(_DWORD *)(*(_QWORD *)&v24[1] + 4LL) - 16;
  *(_QWORD *)((char *)v24 + *(int *)(*(_QWORD *)&v24[0] + 4LL)) = &std::wiostream::`vftable';
  *(_DWORD *)((char *)&v23 + *(int *)(*(_QWORD *)&v24[0] + 4LL) + 12) = *(_DWORD *)(*(_QWORD *)&v24[0] + 4LL) - 32;
  *(_QWORD *)((char *)v24 + *(int *)(*(_QWORD *)&v24[0] + 4LL)) = &std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vftable';
  *(_DWORD *)((char *)&v23 + *(int *)(*(_QWORD *)&v24[0] + 4LL) + 12) = *(_DWORD *)(*(_QWORD *)&v24[0] + 4LL) - 152;
  v19 = (char *)&v24[1] + 8;
  std::wstreambuf::wstreambuf((char *)&v24[1] + 8);
  *((_QWORD *)&v24[1] + 1) = &std::wstringbuf::`vftable';
  v5 = Src;
  if ( *((_QWORD *)&v18 + 1) > 7u )
    v5 = (void **)Src[0];
  v6 = 0;
  if ( (unsigned __int64)v18 > 0x7FFFFFFF )
    std::_Xbad_alloc();
  if ( (_QWORD)v18 )
  {
    _mm_lfence();
    v7 = 2 * v18;
    v8 = std::_Allocate<16,std::_Default_allocate_traits>(2 * v18);
    memmove(v8, v5, v7);
    *(_QWORD *)&v24[8] = (char *)v8 + v7;
    **(_QWORD **)&v24[3] = v8;
    **(_QWORD **)&v24[5] = v8;
    **((_DWORD **)&v24[6] + 1) = v7 >> 1;
    v9 = *(_QWORD *)&v24[8];
    **((_QWORD **)&v24[3] + 1) = v8;
    **((_QWORD **)&v24[5] + 1) = v8;
    **(_DWORD **)&v24[7] = (v9 - (__int64)v8) >> 1;
    v6 = 1;
  }
  else
  {
    *(_QWORD *)&v24[8] = 0;
  }
  DWORD2(v24[8]) = v6;
  std::wstring::_Tidy_deallocate((__int64)Src);
  *(_OWORD *)v20 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v20[0]) = 0;
  v10 = *((_QWORD *)&v23 + 1);
  v11 = (unsigned __int16 *)v22;
  while ( 1 )
  {
    v12 = (unsigned __int16 *)&v22;
    if ( v10 > 7 )
      v12 = v11;
    v13 = std::getline<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v24, v20, *v12);
    if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v13 + 4LL) + v13 + 16) & 6) != 0 )
      break;
    v14 = (const char *)v20;
    if ( si128.m128i_i64[1] > 7uLL )
      v14 = v20[0];
    v15 = v20;
    if ( si128.m128i_i64[1] > 7uLL )
      v15 = (char **)v20[0];
    v16 = DeletePackageDependency(v15);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x1B7,
      (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Workloads\\ApiInfo.cpp",
      (const char *)v16,
      (int)"Failed to remove package dependency for id: %ws",
      v14);
  }
  std::wstring::_Tidy_deallocate((__int64)v20);
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v24);
  std::wstring::_Tidy_deallocate((__int64)&v22);
}

```

## disassembly

```asm
0x180008700  mov     [rsp-8+arg_0], rbx
0x180008705  mov     [rsp-8+arg_10], rsi
0x18000870a  push    rbp
0x18000870b  push    rdi
0x18000870c  push    r14
0x18000870e  lea     rbp, [rsp-0B0h]
0x180008716  sub     rsp, 1B0h
0x18000871d  mov     rax, cs:__security_cookie
0x180008724  xor     rax, rsp
0x180008727  mov     [rbp+0C0h+var_20], rax
0x18000872e  mov     rbx, rdx
0x180008731  xor     r14d, r14d
0x180008734  mov     [rsp+1C0h+var_190], r14d
0x180008739  xorps   xmm0, xmm0
0x18000873c  movups  [rbp+0C0h+var_140], xmm0
0x180008740  xorps   xmm1, xmm1
0x180008743  movdqu  [rbp+0C0h+var_130], xmm1
0x180008748  mov     r8d, 1
0x18000874e  lea     rdx, asc_18004800C; ";"
0x180008755  lea     rcx, [rbp+0C0h+var_140]
0x180008759  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000875e  nop
0x18000875f  xor     edx, edx; Val
0x180008761  mov     r8d, 0F8h; Size
0x180008767  lea     rcx, [rbp+0C0h+var_120]; void *
0x18000876b  call    memset
0x180008770  mov     rdx, [rbx]
0x180008773  test    rdx, rdx
0x180008776  jz      short loc_18000877E
0x180008778  mov     rdx, [rdx+10h]
0x18000877c  jmp     short loc_180008785
0x18000877e  lea     rdx, Src
0x180008785  xorps   xmm0, xmm0
0x180008788  movups  xmmword ptr [rsp+1C0h+Src], xmm0
0x18000878d  xorps   xmm1, xmm1
0x180008790  movdqu  [rsp+1C0h+var_178], xmm1
0x180008796  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000879d  nop     dword ptr [rax]
0x1800087a0  inc     r8
0x1800087a3  cmp     word ptr [rdx+r8*2], 0
0x1800087a9  jnz     short loc_1800087A0
0x1800087ab  lea     rcx, [rsp+1C0h+Src]
0x1800087b0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800087b5  nop
0x1800087b6  lea     rcx, cs:180000000h
0x1800087bd  lea     rax, rva ??_8?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@7B?$basic_istream@_WU?$char_traits@_W@std@@@1@@[rcx]; const std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbtable'{for `std::wistream'} ...
0x1800087c4  mov     [rbp+0C0h+var_120], rax
0x1800087c8  lea     rax, rva ??_8?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@7B?$basic_ostream@_WU?$char_traits@_W@std@@@1@@[rcx]; const std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbtable'{for `std::wostream'} ...
0x1800087cf  mov     [rbp+0C0h+var_110], rax
0x1800087d3  mov     [rbp+0C0h+var_80], r14
0x1800087d7  mov     [rbp+0C0h+var_78], r14
0x1800087db  mov     [rbp+0C0h+var_70], r14d
0x1800087df  mov     [rbp+0C0h+var_68], r14
0x1800087e3  xorps   xmm0, xmm0
0x1800087e6  movdqa  [rbp+0C0h+var_60], xmm0
0x1800087eb  xorps   xmm1, xmm1
0x1800087ee  movdqa  [rbp+0C0h+var_50], xmm1
0x1800087f3  movdqa  [rbp+0C0h+var_40], xmm0
0x1800087fb  mov     [rbp+0C0h+var_30], r14w
0x180008803  mov     [rsp+1C0h+var_190], 1
0x18000880b  lea     rax, ??_7?$basic_istream@_WU?$char_traits@_W@std@@@std@@6B@; const std::wistream::`vftable'
0x180008812  mov     [rbp+0C0h+var_88], rax
0x180008816  mov     [rbp+0C0h+var_8C], 80h
0x18000881d  mov     [rbp+0C0h+var_118], r14
0x180008821  lea     rdx, [rbp+0C0h+var_108]
0x180008825  lea     rcx, [rbp+0C0h+var_88]
0x180008829  call    ?init@?$basic_ios@_WU?$char_traits@_W@std@@@std@@IEAAXPEAV?$basic_streambuf@_WU?$char_traits@_W@std@@@2@_N@Z; std::wios::init(std::wstreambuf *,bool)
0x18000882e  nop
0x18000882f  mov     rax, [rbp+0C0h+var_110]
0x180008833  movsxd  rcx, dword ptr [rax+4]
0x180008837  lea     rax, ??_7?$basic_ostream@_WU?$char_traits@_W@std@@@std@@6B@; const std::wostream::`vftable'
0x18000883e  mov     [rbp+rcx+0C0h+var_110], rax
0x180008843  mov     rax, [rbp+0C0h+var_110]
0x180008847  movsxd  rcx, dword ptr [rax+4]
0x18000884b  lea     edx, [rcx-10h]
0x18000884e  mov     dword ptr [rbp+rcx+0C0h+var_118+4], edx
0x180008852  mov     rax, [rbp+0C0h+var_120]
0x180008856  movsxd  rcx, dword ptr [rax+4]
0x18000885a  lea     rax, ??_7?$basic_iostream@_WU?$char_traits@_W@std@@@std@@6B@; const std::wiostream::`vftable'
0x180008861  mov     [rbp+rcx+0C0h+var_120], rax
0x180008866  mov     rax, [rbp+0C0h+var_120]
0x18000886a  movsxd  rcx, dword ptr [rax+4]
0x18000886e  lea     edx, [rcx-20h]
0x180008871  mov     dword ptr [rbp+rcx+0C0h+var_130+0Ch], edx
0x180008875  mov     rax, [rbp+0C0h+var_120]
0x180008879  movsxd  rcx, dword ptr [rax+4]
0x18000887d  lea     rax, ??_7?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@6B@; const std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vftable'
0x180008884  mov     [rbp+rcx+0C0h+var_120], rax
0x180008889  mov     rax, [rbp+0C0h+var_120]
0x18000888d  movsxd  rcx, dword ptr [rax+4]
0x180008891  lea     edx, [rcx-98h]
0x180008897  mov     dword ptr [rbp+rcx+0C0h+var_130+0Ch], edx
0x18000889b  lea     rax, [rbp+0C0h+var_108]
0x18000889f  mov     [rsp+1C0h+var_168], rax
0x1800088a4  lea     rcx, [rbp+0C0h+var_108]
0x1800088a8  call    ??0?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEAA@XZ; std::wstreambuf::wstreambuf(void)
0x1800088ad  nop
0x1800088ae  lea     rax, ??_7?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@6B@; const std::wstringbuf::`vftable'
0x1800088b5  mov     [rbp+0C0h+var_108], rax
0x1800088b9  lea     rsi, [rsp+1C0h+Src]
0x1800088be  cmp     qword ptr [rsp+1C0h+var_178+8], 7
0x1800088c4  cmova   rsi, [rsp+1C0h+Src]
0x1800088ca  mov     eax, r14d
0x1800088cd  mov     rbx, qword ptr [rsp+1C0h+var_178]
0x1800088d2  cmp     rbx, 7FFFFFFFh
0x1800088d9  ja      loc_180008A4A
0x1800088df  test    rbx, rbx
0x1800088e2  jz      short loc_180008947
0x1800088e4  lfence
0x1800088e7  add     rbx, rbx
0x1800088ea  mov     rcx, rbx
0x1800088ed  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800088f2  mov     rdi, rax
0x1800088f5  mov     r8, rbx; Size
0x1800088f8  mov     rdx, rsi; Src
0x1800088fb  mov     rcx, rax; void *
0x1800088fe  call    memmove
0x180008903  lea     rcx, [rdi+rbx]
0x180008907  mov     [rbp+0C0h+var_A0], rcx
0x18000890b  mov     rcx, [rbp+0C0h+var_F0]
0x18000890f  mov     [rcx], rdi
0x180008912  mov     rcx, [rbp+0C0h+var_D0]
0x180008916  mov     [rcx], rdi
0x180008919  sar     rbx, 1
0x18000891c  mov     rcx, [rbp+0C0h+var_B8]
0x180008920  mov     [rcx], ebx
0x180008922  mov     rcx, [rbp+0C0h+var_A0]
0x180008926  mov     rax, [rbp+0C0h+var_E8]
0x18000892a  mov     [rax], rdi
0x18000892d  mov     rax, [rbp+0C0h+var_C8]
0x180008931  mov     [rax], rdi
0x180008934  sub     rcx, rdi
0x180008937  sar     rcx, 1
0x18000893a  mov     rax, [rbp+0C0h+var_B0]
0x18000893e  mov     [rax], ecx
0x180008940  mov     eax, 1
0x180008945  jmp     short loc_18000894B
0x180008947  mov     [rbp+0C0h+var_A0], r14
0x18000894b  mov     [rbp+0C0h+var_98], eax
0x18000894e  lea     rcx, [rsp+1C0h+Src]
0x180008953  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180008958  xorps   xmm0, xmm0
0x18000895b  movups  xmmword ptr [rsp+1C0h+var_160], xmm0
0x180008960  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180008968  movdqu  [rsp+1C0h+var_150], xmm1
0x18000896e  mov     word ptr [rsp+1C0h+var_160], r14w
0x180008974  lea     r14, aFailedToRemove; "Failed to remove package dependency for"...
0x18000897b  mov     rdi, qword ptr [rbp+0C0h+var_130+8]
0x18000897f  mov     rsi, qword ptr [rbp+0C0h+var_140]
0x180008983  nop     dword ptr [rax+00h]
0x180008987  nop     word ptr [rax+rax+00000000h]
0x180008990  lea     r8, [rbp+0C0h+var_140]
0x180008994  cmp     rdi, 7
0x180008998  cmova   r8, rsi
0x18000899c  movzx   r8d, word ptr [r8]
0x1800089a0  lea     rdx, [rsp+1C0h+var_160]
0x1800089a5  lea     rcx, [rbp+0C0h+var_120]
0x1800089a9  call    ??$getline@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@YAAEAV?$basic_istream@_WU?$char_traits@_W@std@@@0@$$QEAV10@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@_W@Z; std::getline<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wistream &&,std::wstring &,wchar_t)
0x1800089ae  mov     rcx, [rax]
0x1800089b1  movsxd  rdx, dword ptr [rcx+4]
0x1800089b5  test    byte ptr [rdx+rax+10h], 6
0x1800089ba  jnz     short loc_180008A05
0x1800089bc  lea     rbx, [rsp+1C0h+var_160]
0x1800089c1  cmp     qword ptr [rsp+1C0h+var_150+8], 7
0x1800089c7  cmova   rbx, [rsp+1C0h+var_160]
0x1800089cd  lea     rcx, [rsp+1C0h+var_160]
0x1800089d2  cmova   rcx, [rsp+1C0h+var_160]
0x1800089d8  call    cs:__imp_DeletePackageDependency
0x1800089de  mov     rcx, [rbp+0C8h]; this
0x1800089e5  mov     [rsp+1C0h+var_198], rbx; char *
0x1800089ea  mov     qword ptr [rsp+1C0h+var_1A0], r14; int
0x1800089ef  mov     r9d, eax; char *
0x1800089f2  lea     r8, aCW1SProductApi; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800089f9  mov     edx, 1B7h; void *
0x1800089fe  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180008a03  jmp     short loc_180008990
0x180008a05  lea     rcx, [rsp+1C0h+var_160]
0x180008a0a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180008a0f  nop
0x180008a10  lea     rcx, [rbp+0C0h+var_120]
0x180008a14  call    ??_D?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(void)
0x180008a19  nop
0x180008a1a  lea     rcx, [rbp+0C0h+var_140]
0x180008a1e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180008a23  mov     rcx, [rbp+0C0h+var_20]
0x180008a2a  xor     rcx, rsp; StackCookie
0x180008a2d  call    __security_check_cookie
0x180008a32  lea     r11, [rsp+1C0h+var_10]
0x180008a3a  mov     rbx, [r11+20h]
0x180008a3e  mov     rsi, [r11+30h]
0x180008a42  mov     rsp, r11
0x180008a45  pop     r14
0x180008a47  pop     rdi
0x180008a48  pop     rbp
0x180008a49  retn
0x180008a4a  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
