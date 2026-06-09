# PrintCore::XpsPageBitmapProvider::XpsPageBitmapProvider(uint,uint,uint,uint,uint,_GUID,Microsoft::WRL::ComPtr<IXpsOMPage>,IXpsRasterizationFactory2 *,IXpsRasterizerNotificationCallback *)

- ea: `0x18000be40`
- end: `0x18000c1a2`
- name: `??0XpsPageBitmapProvider@PrintCore@@QEAA@IIIIIU_GUID@@V?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@PEAUIXpsRasterizationFactory2@@PEAUIXpsRasterizerNotificationCallback@@@Z`
- size: `866`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, void *Buf1, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000c238`

## callees

- `0x1800020e4`
- `0x180002dd4`
- `0x18000b0ac`
- `0x18000b62c`
- `0x18000bd08`
- `0x18000be40`
- `0x18000c96c`
- `0x18000cb44`
- `0x18000e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall PrintCore::XpsPageBitmapProvider::XpsPageBitmapProvider(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        unsigned int a6,
        _OWORD *Buf1,
        _QWORD *a8,
        __int64 a9,
        __int64 a10)
{
  __int64 *v12; // r14
  _QWORD *v13; // r12
  _QWORD *v14; // r15
  int v15; // edi
  unsigned int v16; // ebp
  unsigned int v17; // ecx
  unsigned __int64 v18; // rdi
  __int64 v19; // rdx
  __int64 v20; // rsi
  unsigned __int64 v21; // rcx
  __int64 v22; // rax
  size_t v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD); // rbp
  int v25; // eax
  __int64 v26; // rcx
  unsigned int v28; // eax
  int v29; // [rsp+20h] [rbp-68h]
  const char *v30; // [rsp+28h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *(_QWORD *)a1 = &winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 16) = 1;
  *(_QWORD *)a1 = &winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>'};
  *(_QWORD *)(a1 + 8) = &winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>'};
  *(_DWORD *)(a1 + 24) = a2;
  *(_DWORD *)(a1 + 28) = a3;
  *(_DWORD *)(a1 + 32) = a4;
  *(_DWORD *)(a1 + 36) = a5;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  v12 = (__int64 *)(a1 + 80);
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  v13 = (_QWORD *)(a1 + 104);
  *(_QWORD *)(a1 + 104) = 0;
  v14 = (_QWORD *)(a1 + 112);
  *(_QWORD *)(a1 + 112) = 0;
  if ( a6 < 0x200000 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpsbitmapprovider\\xpspagebitmapprovider.cpp",
      (const char *)0x80070057LL,
      v29);
  *(_OWORD *)(a1 + 60) = *Buf1;
  v15 = 16;
  if ( !memcmp_0(Buf1, &GUID_WICPixelFormat24bppRGB, 0x10u) )
  {
    v15 = 24;
  }
  else if ( !memcmp_0(Buf1, &GUID_WICPixelFormat48bppRGB, 0x10u) )
  {
    v15 = 48;
  }
  else if ( !memcmp_0(Buf1, &GUID_WICPixelFormat32bppCMYK, 0x10u)
         || !memcmp_0(Buf1, &GUID_WICPixelFormat32bppPBGRA, 0x10u) )
  {
    v15 = 32;
  }
  else if ( !memcmp_0(Buf1, &GUID_WICPixelFormat64bppCMYK, 0x10u) )
  {
    v15 = 64;
  }
  else if ( !memcmp_0(Buf1, &GUID_WICPixelFormatBlackWhite, 0x10u) )
  {
    v15 = 1;
  }
  else if ( !memcmp_0(Buf1, &GUID_WICPixelFormat8bppGray, 0x10u) )
  {
    v15 = 8;
  }
  else if ( memcmp_0(Buf1, &GUID_WICPixelFormat16bppGray, 0x10u) )
  {
    v28 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpsbitmapprovider\\BitmapUtils.h",
      (const char *)v28,
      (int)"given pixel format is not recognized",
      v30);
  }
  *(_DWORD *)(a1 + 40) = v15;
  if ( *v14 != a10 )
  {
    if ( *v14 )
      winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(v14);
    *v14 = a10;
    if ( a10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a10 + 8LL))(a10);
  }
  v16 = (unsigned int)(*(_DWORD *)(a1 + 40) * a4 + 7) >> 3;
  *(_DWORD *)(a1 + 44) = v16;
  v17 = *(_DWORD *)(a1 + 36);
  if ( a6 / v16 <= v17 )
    v17 = a6 / v16;
  *(_DWORD *)(a1 + 48) = v17;
  v18 = v16 * v17;
  v19 = *v12;
  v20 = v12[1];
  v21 = v20 - *v12;
  if ( v18 >= v21 )
  {
    if ( v18 <= v21 )
      goto LABEL_31;
    if ( v18 > v12[2] - v19 )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v12, v18);
      goto LABEL_31;
    }
    v23 = v18 - v21;
    memset_0((void *)v12[1], 0, v23);
    v22 = v23 + v20;
  }
  else
  {
    v22 = v18 + v19;
  }
  v12[1] = v22;
LABEL_31:
  v24 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a9 + 24LL);
  if ( *v13 )
    winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(v13);
  v25 = v24(a9, *a8);
  if ( v25 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpsbitmapprovider\\xpspagebitmapprovider.cpp",
      (const char *)(unsigned int)v25,
      0);
  v26 = *a8;
  if ( *a8 )
  {
    *a8 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  return a1;
}

```

## disassembly

```asm
0x18000be40  mov     [rsp+arg_10], rbx
0x18000be45  mov     [rsp+arg_8], edx
0x18000be49  mov     [rsp+arg_0], rcx
0x18000be4e  push    rbp
0x18000be4f  push    rsi
0x18000be50  push    rdi
0x18000be51  push    r12
0x18000be53  push    r13
0x18000be55  push    r14
0x18000be57  push    r15
0x18000be59  sub     rsp, 50h
0x18000be5d  mov     ebp, r9d
0x18000be60  mov     r13d, r8d
0x18000be63  mov     rbx, rcx
0x18000be66  lea     rcx, ??_7?$producers_base@VXpsPageBitmapProvider@PrintCore@@V?$tuple@UIPageBitmapProvider@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>::`vftable'
0x18000be6d  mov     [rbx], rcx
0x18000be70  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000be77  mov     qword ptr [rbx+10h], 1
0x18000be7f  lea     rcx, ??_7?$heap_implements@VXpsPageBitmapProvider@PrintCore@@@impl@winrt@@6B?$producers_base@VXpsPageBitmapProvider@PrintCore@@V?$tuple@UIPageBitmapProvider@@@std@@@12@@; const winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>'}
0x18000be86  mov     [rbx], rcx
0x18000be89  lea     rcx, ??_7?$heap_implements@VXpsPageBitmapProvider@PrintCore@@@impl@winrt@@6B?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@12@@; const winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>'}
0x18000be90  mov     [rbx+8], rcx
0x18000be94  mov     [rbx+18h], edx
0x18000be97  mov     [rbx+1Ch], r13d
0x18000be9b  mov     [rbx+20h], r9d
0x18000be9f  mov     eax, [rsp+88h+arg_20]
0x18000bea6  mov     [rbx+24h], eax
0x18000bea9  xor     eax, eax
0x18000beab  mov     [rbx+28h], rax
0x18000beaf  mov     [rbx+30h], rax
0x18000beb3  mov     [rbx+38h], eax
0x18000beb6  lea     r14, [rbx+50h]
0x18000beba  mov     [r14], rax
0x18000bebd  mov     [r14+8], rax
0x18000bec1  mov     [r14+10h], rax
0x18000bec5  lea     r12, [rbx+68h]
0x18000bec9  mov     [r12], rax
0x18000becd  lea     r15, [rbx+70h]
0x18000bed1  mov     [r15], rax
0x18000bed4  mov     rcx, [rsp+88h]; this
0x18000bedc  cmp     [rsp+88h+arg_28], 200000h
0x18000bee7  jb      loc_18000C18A
0x18000beed  mov     rsi, [rsp+88h+Buf1]
0x18000bef5  movaps  xmm0, xmmword ptr [rsi]
0x18000bef8  movdqu  xmmword ptr [rbx+3Ch], xmm0
0x18000befd  lea     edi, [rax+10h]
0x18000bf00  mov     r8d, edi; Size
0x18000bf03  lea     rdx, GUID_WICPixelFormat24bppRGB; Buf2
0x18000bf0a  mov     rcx, rsi; Buf1
0x18000bf0d  call    memcmp_0
0x18000bf12  test    eax, eax
0x18000bf14  jnz     short loc_18000BF1E
0x18000bf16  lea     edi, [rax+18h]
0x18000bf19  jmp     loc_18000BFDE
0x18000bf1e  mov     r8, rdi; Size
0x18000bf21  lea     rdx, GUID_WICPixelFormat48bppRGB; Buf2
0x18000bf28  mov     rcx, rsi; Buf1
0x18000bf2b  call    memcmp_0
0x18000bf30  test    eax, eax
0x18000bf32  jnz     short loc_18000BF3C
0x18000bf34  lea     edi, [rax+30h]
0x18000bf37  jmp     loc_18000BFDE
0x18000bf3c  mov     r8, rdi; Size
0x18000bf3f  lea     rdx, GUID_WICPixelFormat32bppCMYK; Buf2
0x18000bf46  mov     rcx, rsi; Buf1
0x18000bf49  call    memcmp_0
0x18000bf4e  test    eax, eax
0x18000bf50  jz      loc_18000BFD9
0x18000bf56  mov     r8, rdi; Size
0x18000bf59  lea     rdx, GUID_WICPixelFormat32bppPBGRA; Buf2
0x18000bf60  mov     rcx, rsi; Buf1
0x18000bf63  call    memcmp_0
0x18000bf68  test    eax, eax
0x18000bf6a  jz      short loc_18000BFD9
0x18000bf6c  mov     r8, rdi; Size
0x18000bf6f  lea     rdx, GUID_WICPixelFormat64bppCMYK; Buf2
0x18000bf76  mov     rcx, rsi; Buf1
0x18000bf79  call    memcmp_0
0x18000bf7e  test    eax, eax
0x18000bf80  jnz     short loc_18000BF87
0x18000bf82  lea     edi, [rax+40h]
0x18000bf85  jmp     short loc_18000BFDE
0x18000bf87  mov     r8, rdi; Size
0x18000bf8a  lea     rdx, GUID_WICPixelFormatBlackWhite; Buf2
0x18000bf91  mov     rcx, rsi; Buf1
0x18000bf94  call    memcmp_0
0x18000bf99  test    eax, eax
0x18000bf9b  jnz     short loc_18000BFA2
0x18000bf9d  lea     edi, [rax+1]
0x18000bfa0  jmp     short loc_18000BFDE
0x18000bfa2  mov     r8, rdi; Size
0x18000bfa5  lea     rdx, GUID_WICPixelFormat8bppGray; Buf2
0x18000bfac  mov     rcx, rsi; Buf1
0x18000bfaf  call    memcmp_0
0x18000bfb4  test    eax, eax
0x18000bfb6  jnz     short loc_18000BFBD
0x18000bfb8  lea     edi, [rax+8]
0x18000bfbb  jmp     short loc_18000BFDE
0x18000bfbd  mov     r8, rdi; Size
0x18000bfc0  lea     rdx, GUID_WICPixelFormat16bppGray; Buf2
0x18000bfc7  mov     rcx, rsi; Buf1
0x18000bfca  call    memcmp_0
0x18000bfcf  test    eax, eax
0x18000bfd1  jnz     loc_18000C157
0x18000bfd7  jmp     short loc_18000BFDE
0x18000bfd9  mov     edi, 20h ; ' '
0x18000bfde  mov     [rbx+28h], edi
0x18000bfe1  mov     rdi, [rsp+88h+arg_48]
0x18000bfe9  cmp     [r15], rdi
0x18000bfec  jz      short loc_18000C014
0x18000bfee  cmp     qword ptr [r15], 0
0x18000bff2  jz      short loc_18000BFFC
0x18000bff4  mov     rcx, r15
0x18000bff7  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000bffc  mov     [r15], rdi
0x18000bfff  test    rdi, rdi
0x18000c002  jz      short loc_18000C014
0x18000c004  mov     rax, [rdi]
0x18000c007  mov     rcx, rdi
0x18000c00a  mov     rax, [rax+8]
0x18000c00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c013  nop
0x18000c014  imul    ebp, [rbx+28h]
0x18000c018  add     ebp, 7
0x18000c01b  shr     ebp, 3
0x18000c01e  mov     [rbx+2Ch], ebp
0x18000c021  xor     edx, edx
0x18000c023  mov     eax, [rsp+88h+arg_28]
0x18000c02a  div     ebp
0x18000c02c  mov     ecx, [rbx+24h]
0x18000c02f  cmp     eax, ecx
0x18000c031  cmovbe  ecx, eax
0x18000c034  mov     [rbx+30h], ecx
0x18000c037  imul    ecx, ebp
0x18000c03a  mov     edi, ecx
0x18000c03c  mov     rdx, [r14]
0x18000c03f  mov     rsi, [r14+8]
0x18000c043  mov     rcx, rsi
0x18000c046  sub     rcx, rdx
0x18000c049  cmp     rdi, rcx
0x18000c04c  jnb     short loc_18000C054
0x18000c04e  lea     rax, [rdi+rdx]
0x18000c052  jmp     short loc_18000C083
0x18000c054  jbe     short loc_18000C087
0x18000c056  mov     rax, [r14+10h]
0x18000c05a  sub     rax, rdx
0x18000c05d  cmp     rdi, rax
0x18000c060  jbe     short loc_18000C06F
0x18000c062  mov     rdx, rdi
0x18000c065  mov     rcx, r14
0x18000c068  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000c06d  jmp     short loc_18000C087
0x18000c06f  sub     rdi, rcx
0x18000c072  mov     r8, rdi; Size
0x18000c075  xor     edx, edx; Val
0x18000c077  mov     rcx, rsi; void *
0x18000c07a  call    memset_0
0x18000c07f  lea     rax, [rdi+rsi]
0x18000c083  mov     [r14+8], rax
0x18000c087  xor     edi, edi
0x18000c089  cmp     dword ptr [rbx+28h], 20h ; ' '
0x18000c08d  setnbe  dil
0x18000c091  inc     edi
0x18000c093  mov     rsi, [rsp+88h+arg_40]
0x18000c09b  mov     rax, [rsi]
0x18000c09e  mov     rbp, [rax+18h]
0x18000c0a2  cmp     qword ptr [r12], 0
0x18000c0a7  jz      short loc_18000C0B1
0x18000c0a9  mov     rcx, r12
0x18000c0ac  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000c0b1  xorps   xmm3, xmm3
0x18000c0b4  cvtsi2ss xmm3, r13
0x18000c0b9  mov     edx, [rsp+88h+arg_8]
0x18000c0c0  xorps   xmm2, xmm2
0x18000c0c3  cvtsi2ss xmm2, rdx
0x18000c0c8  mov     [rsp+88h+var_48], r12
0x18000c0cd  mov     [rsp+88h+var_50], 1
0x18000c0d5  mov     [rsp+88h+var_58], edi
0x18000c0d9  mov     dword ptr [rsp+88h+var_60], 1
0x18000c0e1  mov     [rsp+88h+var_68], 0; int
0x18000c0e9  mov     rdi, [rsp+88h+arg_38]
0x18000c0f1  mov     rdx, [rdi]
0x18000c0f4  mov     rcx, rsi
0x18000c0f7  mov     rax, rbp
0x18000c0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0ff  mov     rcx, [rsp+88h]; this
0x18000c107  test    eax, eax
0x18000c109  js      short loc_18000C142
0x18000c10b  mov     rcx, [rdi]
0x18000c10e  test    rcx, rcx
0x18000c111  jz      short loc_18000C127
0x18000c113  mov     qword ptr [rdi], 0
0x18000c11a  mov     rax, [rcx]
0x18000c11d  mov     rax, [rax+10h]
0x18000c121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c126  nop
0x18000c127  mov     rax, rbx
0x18000c12a  mov     rbx, [rsp+88h+arg_10]
0x18000c132  add     rsp, 50h
0x18000c136  pop     r15
0x18000c138  pop     r14
0x18000c13a  pop     r13
0x18000c13c  pop     r12
0x18000c13e  pop     rdi
0x18000c13f  pop     rsi
0x18000c140  pop     rbp
0x18000c141  retn
0x18000c142  mov     r9d, eax; char *
0x18000c145  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000c14c  mov     edx, 32h ; '2'; void *
0x18000c151  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c157  mov     ecx, 80070057h
0x18000c15c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000c161  mov     r9d, eax; char *
0x18000c164  mov     rcx, [rsp+88h]; this
0x18000c16c  lea     rax, aGivenPixelForm; "given pixel format is not recognized"
0x18000c173  mov     qword ptr [rsp+88h+var_68], rax; int
0x18000c178  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000c17f  mov     edx, 34h ; '4'; void *
0x18000c184  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000c18a  mov     r9d, 80070057h; char *
0x18000c190  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000c197  mov     edx, 1Bh; void *
0x18000c19c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
