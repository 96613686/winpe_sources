# PrintCore::XpsPageBitmapProvider::XpsPageBitmapProvider(uint,uint,uint,uint,uint,_GUID,Microsoft::WRL::ComPtr<IXpsOMPage>,IXpsRasterizationFactory2 *,IXpsRasterizerNotificationCallback *)

- ea: `0x18000dc78`
- end: `0x18000df91`
- name: `??0XpsPageBitmapProvider@PrintCore@@QEAA@IIIIIU_GUID@@V?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@PEAUIXpsRasterizationFactory2@@PEAUIXpsRasterizerNotificationCallback@@@Z`
- size: `793`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, void *Buf1, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000e2b4`

## callees

- `0x180002d30`
- `0x18000975c`
- `0x18000c9a8`
- `0x18000dc78`
- `0x18000f050`
- `0x18000f3c0`
- `0x18000f544`
- `0x180011010`

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
  _QWORD *v12; // r15
  _QWORD *v13; // r14
  int v14; // edi
  unsigned int v15; // ebp
  unsigned int v16; // edx
  __int64 (__fastcall *v17)(__int64, _QWORD); // rbp
  int v18; // eax
  __int64 v19; // rcx
  unsigned int v21; // eax
  int v22; // [rsp+20h] [rbp-68h]
  const char *v23; // [rsp+28h] [rbp-60h]
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
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  v12 = (_QWORD *)(a1 + 104);
  *(_QWORD *)(a1 + 104) = 0;
  v13 = (_QWORD *)(a1 + 112);
  *(_QWORD *)(a1 + 112) = 0;
  if ( a6 < 0x200000 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpsbitmapprovider\\xpspagebitmapprovider.cpp",
      (const char *)0x80070057LL,
      v22);
  *(_OWORD *)(a1 + 60) = *Buf1;
  v14 = 16;
  if ( !memcmp_0(Buf1, &GUID_WICPixelFormat24bppRGB, 0x10u) )
  {
    v14 = 24;
  }
  else if ( !memcmp_0(Buf1, &GUID_WICPixelFormat48bppRGB, 0x10u) )
  {
    v14 = 48;
  }
  else if ( !memcmp_0(Buf1, &GUID_WICPixelFormat32bppCMYK, 0x10u)
         || !memcmp_0(Buf1, &GUID_WICPixelFormat32bppPBGRA, 0x10u) )
  {
    v14 = 32;
  }
  else if ( !memcmp_0(Buf1, &GUID_WICPixelFormat64bppCMYK, 0x10u) )
  {
    v14 = 64;
  }
  else if ( !memcmp_0(Buf1, &GUID_WICPixelFormatBlackWhite, 0x10u) )
  {
    v14 = 1;
  }
  else if ( !memcmp_0(Buf1, &GUID_WICPixelFormat8bppGray, 0x10u) )
  {
    v14 = 8;
  }
  else if ( memcmp_0(Buf1, &GUID_WICPixelFormat16bppGray, 0x10u) )
  {
    v21 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpsbitmapprovider\\BitmapUtils.h",
      (const char *)v21,
      (int)"given pixel format is not recognized",
      v23);
  }
  *(_DWORD *)(a1 + 40) = v14;
  if ( *v13 != a10 )
  {
    if ( *v13 )
      winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(v13);
    *v13 = a10;
    if ( a10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a10 + 8LL))(a10);
  }
  v15 = (unsigned int)(*(_DWORD *)(a1 + 40) * a4 + 7) >> 3;
  *(_DWORD *)(a1 + 44) = v15;
  v16 = *(_DWORD *)(a1 + 36);
  if ( a6 / v15 <= v16 )
    v16 = a6 / v15;
  *(_DWORD *)(a1 + 48) = v16;
  std::vector<unsigned char>::resize(a1 + 80);
  v17 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a9 + 24LL);
  if ( *v12 )
    winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(v12);
  v18 = v17(a9, *a8);
  if ( v18 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpsbitmapprovider\\xpspagebitmapprovider.cpp",
      (const char *)(unsigned int)v18,
      0);
  v19 = *a8;
  if ( *a8 )
  {
    *a8 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return a1;
}

```

## disassembly

```asm
0x18000dc78  mov     [rsp+arg_10], rbx
0x18000dc7d  mov     [rsp+arg_8], edx
0x18000dc81  mov     [rsp+arg_0], rcx
0x18000dc86  push    rbp
0x18000dc87  push    rsi
0x18000dc88  push    rdi
0x18000dc89  push    r12
0x18000dc8b  push    r13
0x18000dc8d  push    r14
0x18000dc8f  push    r15
0x18000dc91  sub     rsp, 50h
0x18000dc95  mov     ebp, r9d
0x18000dc98  mov     r13d, r8d
0x18000dc9b  mov     rbx, rcx
0x18000dc9e  lea     rcx, ??_7?$producers_base@VXpsPageBitmapProvider@PrintCore@@V?$tuple@UIPageBitmapProvider@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>::`vftable'
0x18000dca5  mov     [rbx], rcx
0x18000dca8  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000dcaf  mov     qword ptr [rbx+10h], 1
0x18000dcb7  lea     rcx, ??_7?$heap_implements@VXpsPageBitmapProvider@PrintCore@@@impl@winrt@@6B?$producers_base@VXpsPageBitmapProvider@PrintCore@@V?$tuple@UIPageBitmapProvider@@@std@@@12@@; const winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>'}
0x18000dcbe  mov     [rbx], rcx
0x18000dcc1  lea     rcx, ??_7?$heap_implements@VXpsPageBitmapProvider@PrintCore@@@impl@winrt@@6B?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@12@@; const winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>'}
0x18000dcc8  mov     [rbx+8], rcx
0x18000dccc  mov     [rbx+18h], edx
0x18000dccf  mov     [rbx+1Ch], r13d
0x18000dcd3  mov     [rbx+20h], r9d
0x18000dcd7  mov     eax, [rsp+88h+arg_20]
0x18000dcde  mov     [rbx+24h], eax
0x18000dce1  xor     eax, eax
0x18000dce3  mov     [rbx+28h], rax
0x18000dce7  mov     [rbx+30h], rax
0x18000dceb  mov     [rbx+38h], eax
0x18000dcee  mov     [rbx+50h], rax
0x18000dcf2  mov     [rbx+58h], rax
0x18000dcf6  mov     [rbx+60h], rax
0x18000dcfa  lea     r15, [rbx+68h]
0x18000dcfe  mov     [r15], rax
0x18000dd01  lea     r14, [rbx+70h]
0x18000dd05  mov     [r14], rax
0x18000dd08  mov     rcx, [rsp+88h]; this
0x18000dd10  cmp     [rsp+88h+arg_28], 200000h
0x18000dd1b  jb      loc_18000DF79
0x18000dd21  mov     rsi, [rsp+88h+Buf1]
0x18000dd29  movaps  xmm0, xmmword ptr [rsi]
0x18000dd2c  movdqu  xmmword ptr [rbx+3Ch], xmm0
0x18000dd31  lea     edi, [rax+10h]
0x18000dd34  mov     r8d, edi; Size
0x18000dd37  lea     rdx, GUID_WICPixelFormat24bppRGB; Buf2
0x18000dd3e  mov     rcx, rsi; Buf1
0x18000dd41  call    memcmp_0
0x18000dd46  test    eax, eax
0x18000dd48  jnz     short loc_18000DD52
0x18000dd4a  lea     edi, [rax+18h]
0x18000dd4d  jmp     loc_18000DE12
0x18000dd52  mov     r8, rdi; Size
0x18000dd55  lea     rdx, GUID_WICPixelFormat48bppRGB; Buf2
0x18000dd5c  mov     rcx, rsi; Buf1
0x18000dd5f  call    memcmp_0
0x18000dd64  test    eax, eax
0x18000dd66  jnz     short loc_18000DD70
0x18000dd68  lea     edi, [rax+30h]
0x18000dd6b  jmp     loc_18000DE12
0x18000dd70  mov     r8, rdi; Size
0x18000dd73  lea     rdx, GUID_WICPixelFormat32bppCMYK; Buf2
0x18000dd7a  mov     rcx, rsi; Buf1
0x18000dd7d  call    memcmp_0
0x18000dd82  test    eax, eax
0x18000dd84  jz      loc_18000DE0D
0x18000dd8a  mov     r8, rdi; Size
0x18000dd8d  lea     rdx, GUID_WICPixelFormat32bppPBGRA; Buf2
0x18000dd94  mov     rcx, rsi; Buf1
0x18000dd97  call    memcmp_0
0x18000dd9c  test    eax, eax
0x18000dd9e  jz      short loc_18000DE0D
0x18000dda0  mov     r8, rdi; Size
0x18000dda3  lea     rdx, GUID_WICPixelFormat64bppCMYK; Buf2
0x18000ddaa  mov     rcx, rsi; Buf1
0x18000ddad  call    memcmp_0
0x18000ddb2  test    eax, eax
0x18000ddb4  jnz     short loc_18000DDBB
0x18000ddb6  lea     edi, [rax+40h]
0x18000ddb9  jmp     short loc_18000DE12
0x18000ddbb  mov     r8, rdi; Size
0x18000ddbe  lea     rdx, GUID_WICPixelFormatBlackWhite; Buf2
0x18000ddc5  mov     rcx, rsi; Buf1
0x18000ddc8  call    memcmp_0
0x18000ddcd  test    eax, eax
0x18000ddcf  jnz     short loc_18000DDD6
0x18000ddd1  lea     edi, [rax+1]
0x18000ddd4  jmp     short loc_18000DE12
0x18000ddd6  mov     r8, rdi; Size
0x18000ddd9  lea     rdx, GUID_WICPixelFormat8bppGray; Buf2
0x18000dde0  mov     rcx, rsi; Buf1
0x18000dde3  call    memcmp_0
0x18000dde8  test    eax, eax
0x18000ddea  jnz     short loc_18000DDF1
0x18000ddec  lea     edi, [rax+8]
0x18000ddef  jmp     short loc_18000DE12
0x18000ddf1  mov     r8, rdi; Size
0x18000ddf4  lea     rdx, GUID_WICPixelFormat16bppGray; Buf2
0x18000ddfb  mov     rcx, rsi; Buf1
0x18000ddfe  call    memcmp_0
0x18000de03  test    eax, eax
0x18000de05  jnz     loc_18000DF46
0x18000de0b  jmp     short loc_18000DE12
0x18000de0d  mov     edi, 20h ; ' '
0x18000de12  mov     [rbx+28h], edi
0x18000de15  mov     rdi, [rsp+88h+arg_48]
0x18000de1d  cmp     [r14], rdi
0x18000de20  jz      short loc_18000DE48
0x18000de22  cmp     qword ptr [r14], 0
0x18000de26  jz      short loc_18000DE30
0x18000de28  mov     rcx, r14
0x18000de2b  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000de30  mov     [r14], rdi
0x18000de33  test    rdi, rdi
0x18000de36  jz      short loc_18000DE48
0x18000de38  mov     rax, [rdi]
0x18000de3b  mov     rcx, rdi
0x18000de3e  mov     rax, [rax+8]
0x18000de42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de47  nop
0x18000de48  imul    ebp, [rbx+28h]
0x18000de4c  add     ebp, 7
0x18000de4f  shr     ebp, 3
0x18000de52  mov     [rbx+2Ch], ebp
0x18000de55  xor     edx, edx
0x18000de57  mov     eax, [rsp+88h+arg_28]
0x18000de5e  div     ebp
0x18000de60  mov     edx, [rbx+24h]
0x18000de63  cmp     eax, edx
0x18000de65  cmovbe  edx, eax
0x18000de68  mov     [rbx+30h], edx
0x18000de6b  imul    edx, ebp
0x18000de6e  lea     rcx, [rbx+50h]
0x18000de72  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18000de77  xor     edi, edi
0x18000de79  cmp     dword ptr [rbx+28h], 20h ; ' '
0x18000de7d  setnbe  dil
0x18000de81  inc     edi
0x18000de83  mov     rsi, [rsp+88h+arg_40]
0x18000de8b  mov     rax, [rsi]
0x18000de8e  mov     rbp, [rax+18h]
0x18000de92  cmp     qword ptr [r15], 0
0x18000de96  jz      short loc_18000DEA0
0x18000de98  mov     rcx, r15
0x18000de9b  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000dea0  xorps   xmm3, xmm3
0x18000dea3  cvtsi2ss xmm3, r13
0x18000dea8  mov     edx, [rsp+88h+arg_8]
0x18000deaf  xorps   xmm2, xmm2
0x18000deb2  cvtsi2ss xmm2, rdx
0x18000deb7  mov     [rsp+88h+var_48], r15
0x18000debc  mov     [rsp+88h+var_50], 1
0x18000dec4  mov     [rsp+88h+var_58], edi
0x18000dec8  mov     dword ptr [rsp+88h+var_60], 1
0x18000ded0  mov     [rsp+88h+var_68], 0; int
0x18000ded8  mov     rdi, [rsp+88h+arg_38]
0x18000dee0  mov     rdx, [rdi]
0x18000dee3  mov     rcx, rsi
0x18000dee6  mov     rax, rbp
0x18000dee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deee  mov     rcx, [rsp+88h]; this
0x18000def6  test    eax, eax
0x18000def8  js      short loc_18000DF31
0x18000defa  mov     rcx, [rdi]
0x18000defd  test    rcx, rcx
0x18000df00  jz      short loc_18000DF16
0x18000df02  mov     qword ptr [rdi], 0
0x18000df09  mov     rax, [rcx]
0x18000df0c  mov     rax, [rax+10h]
0x18000df10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df15  nop
0x18000df16  mov     rax, rbx
0x18000df19  mov     rbx, [rsp+88h+arg_10]
0x18000df21  add     rsp, 50h
0x18000df25  pop     r15
0x18000df27  pop     r14
0x18000df29  pop     r13
0x18000df2b  pop     r12
0x18000df2d  pop     rdi
0x18000df2e  pop     rsi
0x18000df2f  pop     rbp
0x18000df30  retn
0x18000df31  mov     r9d, eax; char *
0x18000df34  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000df3b  mov     edx, 32h ; '2'; void *
0x18000df40  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000df46  mov     ecx, 80070057h
0x18000df4b  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000df50  mov     r9d, eax; char *
0x18000df53  mov     rcx, [rsp+88h]; this
0x18000df5b  lea     rax, aGivenPixelForm; "given pixel format is not recognized"
0x18000df62  mov     qword ptr [rsp+88h+var_68], rax; int
0x18000df67  lea     r8, aOnecoreuapPrin_2; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000df6e  mov     edx, 34h ; '4'; void *
0x18000df73  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000df79  mov     r9d, 80070057h; char *
0x18000df7f  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000df86  mov     edx, 1Bh; void *
0x18000df8b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
