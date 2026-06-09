# PrintCore::XpsPageBitmapProvider::XpsPageBitmapProvider(uint,uint,uint,uint,uint,_GUID,Microsoft::WRL::ComPtr<IXpsOMPage>,IXpsRasterizationFactory2 *,IXpsRasterizerNotificationCallback *)

- ea: `0x18001b130`
- end: `0x18001b367`
- name: `??0XpsPageBitmapProvider@PrintCore@@QEAA@IIIIIU_GUID@@V?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@PEAUIXpsRasterizationFactory2@@PEAUIXpsRasterizerNotificationCallback@@@Z`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001afe4`

## callees

- `0x180002148`
- `0x18000e1a0`
- `0x18000f448`
- `0x180010f34`
- `0x18001afbc`
- `0x18001b10c`
- `0x18001b130`
- `0x18001b95c`
- `0x18001c7b0`
- `0x18001f010`

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
        PrintCore *a7,
        _QWORD *a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v14; // rcx
  int v15; // r9d
  struct _GUID *v16; // rdx
  _QWORD *v17; // r14
  unsigned int v18; // ebp
  unsigned int v19; // ecx
  unsigned __int64 v20; // rdi
  __int64 v21; // rdx
  __int64 v22; // rbp
  unsigned __int64 v23; // rcx
  size_t v24; // rax
  size_t v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD); // rbp
  int v27; // eax
  __int64 v28; // rcx
  int v30; // [rsp+20h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>();
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  std::atomic<unsigned __int64>::atomic<unsigned __int64>(v14 + 16);
  *(_QWORD *)a1 = &winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>'};
  *(_QWORD *)(a1 + 8) = &winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>'};
  *(_DWORD *)(a1 + 24) = a2;
  *(_DWORD *)(a1 + 28) = a3;
  *(_DWORD *)(a1 + 32) = v15;
  *(_DWORD *)(a1 + 36) = a5;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(a1 + 80);
  *(_QWORD *)(a1 + 104) = v16;
  v17 = (_QWORD *)(a1 + 112);
  *(_QWORD *)(a1 + 112) = v16;
  if ( a6 < 0x200000 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpsbitmapprovider\\xpspagebitmapprovider.cpp",
      (const char *)0x80070057LL,
      v30);
  *(_OWORD *)(a1 + 60) = *(_OWORD *)a7;
  *(_DWORD *)(a1 + 40) = PrintCore::GetBitsPerPixel(a7, v16);
  if ( *v17 != a10 )
  {
    if ( *v17 )
      winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(a1 + 112);
    *v17 = a10;
    if ( a10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a10 + 8LL))(a10);
  }
  v18 = (unsigned int)(*(_DWORD *)(a1 + 40) * a4 + 7) >> 3;
  *(_DWORD *)(a1 + 44) = v18;
  v19 = *(_DWORD *)(a1 + 36);
  if ( a6 / v18 <= v19 )
    v19 = a6 / v18;
  *(_DWORD *)(a1 + 48) = v19;
  v20 = v18 * v19;
  v21 = *(_QWORD *)(a1 + 80);
  v22 = *(_QWORD *)(a1 + 88);
  v23 = v22 - v21;
  if ( v20 >= v22 - v21 )
  {
    if ( v20 <= v23 )
      goto LABEL_17;
    if ( v20 > *(_QWORD *)(a1 + 96) - v21 )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a1 + 80, v20);
      goto LABEL_17;
    }
    v25 = v20 - v23;
    memset_0(*(void **)(a1 + 88), 0, v25);
    v24 = v25 + v22;
  }
  else
  {
    v24 = v20 + v21;
  }
  *(_QWORD *)(a1 + 88) = v24;
LABEL_17:
  v26 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a9 + 24LL);
  if ( *(_QWORD *)(a1 + 104) )
    winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(a1 + 104);
  v27 = v26(a9, *a8);
  if ( v27 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpsbitmapprovider\\xpspagebitmapprovider.cpp",
      (const char *)(unsigned int)v27,
      0);
  v28 = *a8;
  if ( *a8 )
  {
    *a8 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  return a1;
}

```

## disassembly

```asm
0x18001b130  mov     [rsp+arg_0], rcx
0x18001b135  push    rbx
0x18001b136  push    rbp
0x18001b137  push    rsi
0x18001b138  push    rdi
0x18001b139  push    r12
0x18001b13b  push    r13
0x18001b13d  push    r14
0x18001b13f  push    r15
0x18001b141  sub     rsp, 58h
0x18001b145  mov     ebp, r9d
0x18001b148  mov     r12d, r8d
0x18001b14b  mov     r13d, edx
0x18001b14e  mov     rbx, rcx
0x18001b151  call    ??0?$producers_base@VXpsPageBitmapProvider@PrintCore@@V?$tuple@UIPageBitmapProvider@@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>(void)
0x18001b156  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001b15d  add     rcx, 10h
0x18001b161  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x18001b166  nop
0x18001b167  lea     rax, ??_7?$heap_implements@VXpsPageBitmapProvider@PrintCore@@@impl@winrt@@6B?$producers_base@VXpsPageBitmapProvider@PrintCore@@V?$tuple@UIPageBitmapProvider@@@std@@@12@@; const winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>'}
0x18001b16e  mov     [rbx], rax
0x18001b171  lea     rax, ??_7?$heap_implements@VXpsPageBitmapProvider@PrintCore@@@impl@winrt@@6B?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@12@@; const winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>'}
0x18001b178  mov     [rbx+8], rax
0x18001b17c  mov     [rbx+18h], r13d
0x18001b180  mov     [rbx+1Ch], r12d
0x18001b184  mov     [rbx+20h], r9d
0x18001b188  mov     eax, [rsp+98h+arg_20]
0x18001b18f  mov     [rbx+24h], eax
0x18001b192  xor     edx, edx
0x18001b194  mov     [rbx+28h], rdx
0x18001b198  mov     [rbx+30h], rdx
0x18001b19c  mov     [rbx+38h], edx
0x18001b19f  lea     rsi, [rbx+50h]
0x18001b1a3  mov     rcx, rsi
0x18001b1a6  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(void)
0x18001b1ab  nop
0x18001b1ac  lea     r15, [rbx+68h]
0x18001b1b0  mov     [r15], rdx
0x18001b1b3  lea     r14, [rbx+70h]
0x18001b1b7  mov     [r14], rdx
0x18001b1ba  mov     rcx, [rsp+98h]; this
0x18001b1c2  cmp     [rsp+98h+arg_28], 200000h
0x18001b1cd  jnb     short loc_18001B1E7
0x18001b1cf  mov     r9d, 80070057h; char *
0x18001b1d5  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\drivers\\"...
0x18001b1dc  mov     edx, 1Bh; void *
0x18001b1e1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001b1e7  mov     rcx, [rsp+98h+arg_30]; this
0x18001b1ef  movaps  xmm0, xmmword ptr [rcx]
0x18001b1f2  movdqu  xmmword ptr [rbx+3Ch], xmm0
0x18001b1f7  call    ?GetBitsPerPixel@PrintCore@@YAIAEAU_GUID@@@Z; PrintCore::GetBitsPerPixel(_GUID &)
0x18001b1fc  mov     [rbx+28h], eax
0x18001b1ff  mov     rdi, [rsp+98h+arg_48]
0x18001b207  cmp     [r14], rdi
0x18001b20a  jz      short loc_18001B232
0x18001b20c  cmp     qword ptr [r14], 0
0x18001b210  jz      short loc_18001B21A
0x18001b212  mov     rcx, r14
0x18001b215  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18001b21a  mov     [r14], rdi
0x18001b21d  test    rdi, rdi
0x18001b220  jz      short loc_18001B232
0x18001b222  mov     rax, [rdi]
0x18001b225  mov     rcx, rdi
0x18001b228  mov     rax, [rax+8]
0x18001b22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b231  nop
0x18001b232  imul    ebp, [rbx+28h]
0x18001b236  add     ebp, 7
0x18001b239  shr     ebp, 3
0x18001b23c  mov     [rbx+2Ch], ebp
0x18001b23f  xor     edx, edx
0x18001b241  mov     eax, [rsp+98h+arg_28]
0x18001b248  div     ebp
0x18001b24a  mov     ecx, [rbx+24h]
0x18001b24d  cmp     eax, ecx
0x18001b24f  cmovbe  ecx, eax
0x18001b252  mov     [rbx+30h], ecx
0x18001b255  imul    ecx, ebp
0x18001b258  mov     edi, ecx
0x18001b25a  mov     rdx, [rsi]
0x18001b25d  mov     rbp, [rsi+8]
0x18001b261  mov     rcx, rbp
0x18001b264  sub     rcx, rdx
0x18001b267  cmp     rdi, rcx
0x18001b26a  jnb     short loc_18001B272
0x18001b26c  lea     rax, [rdi+rdx]
0x18001b270  jmp     short loc_18001B2A1
0x18001b272  jbe     short loc_18001B2A5
0x18001b274  mov     rax, [rsi+10h]
0x18001b278  sub     rax, rdx
0x18001b27b  cmp     rdi, rax
0x18001b27e  jbe     short loc_18001B28D
0x18001b280  mov     rdx, rdi
0x18001b283  mov     rcx, rsi
0x18001b286  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001b28b  jmp     short loc_18001B2A5
0x18001b28d  sub     rdi, rcx
0x18001b290  mov     r8, rdi; Size
0x18001b293  xor     edx, edx; Val
0x18001b295  mov     rcx, rbp; void *
0x18001b298  call    memset_0
0x18001b29d  lea     rax, [rdi+rbp]
0x18001b2a1  mov     [rsi+8], rax
0x18001b2a5  xor     edi, edi
0x18001b2a7  cmp     dword ptr [rbx+28h], 20h ; ' '
0x18001b2ab  setnbe  dil
0x18001b2af  mov     r14d, 1
0x18001b2b5  add     edi, r14d
0x18001b2b8  mov     rsi, [rsp+98h+arg_40]
0x18001b2c0  mov     rax, [rsi]
0x18001b2c3  mov     rbp, [rax+18h]
0x18001b2c7  cmp     qword ptr [r15], 0
0x18001b2cb  jz      short loc_18001B2D5
0x18001b2cd  mov     rcx, r15
0x18001b2d0  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18001b2d5  xorps   xmm3, xmm3
0x18001b2d8  cvtsi2ss xmm3, r12
0x18001b2dd  xorps   xmm2, xmm2
0x18001b2e0  cvtsi2ss xmm2, r13
0x18001b2e5  mov     [rsp+98h+var_58], r15
0x18001b2ea  mov     [rsp+98h+var_60], r14d
0x18001b2ef  mov     [rsp+98h+var_68], edi
0x18001b2f3  mov     [rsp+98h+var_70], r14d
0x18001b2f8  mov     [rsp+98h+var_78], 0; int
0x18001b300  mov     rdi, [rsp+98h+arg_38]
0x18001b308  mov     rdx, [rdi]
0x18001b30b  mov     rcx, rsi
0x18001b30e  mov     rax, rbp
0x18001b311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b316  mov     rcx, [rsp+98h]; this
0x18001b31e  test    eax, eax
0x18001b320  jns     short loc_18001B337
0x18001b322  mov     r9d, eax; char *
0x18001b325  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\drivers\\"...
0x18001b32c  mov     edx, 32h ; '2'; void *
0x18001b331  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001b337  mov     rcx, [rdi]
0x18001b33a  test    rcx, rcx
0x18001b33d  jz      short loc_18001B353
0x18001b33f  mov     qword ptr [rdi], 0
0x18001b346  mov     rax, [rcx]
0x18001b349  mov     rax, [rax+10h]
0x18001b34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b352  nop
0x18001b353  mov     rax, rbx
0x18001b356  add     rsp, 58h
0x18001b35a  pop     r15
0x18001b35c  pop     r14
0x18001b35e  pop     r13
0x18001b360  pop     r12
0x18001b362  pop     rdi
0x18001b363  pop     rsi
0x18001b364  pop     rbp
0x18001b365  pop     rbx
0x18001b366  retn
```
