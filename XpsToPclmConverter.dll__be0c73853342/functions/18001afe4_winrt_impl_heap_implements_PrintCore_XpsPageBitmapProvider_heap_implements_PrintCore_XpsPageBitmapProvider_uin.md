# winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::heap_implements<PrintCore::XpsPageBitmapProvider>(uint,uint,uint,uint,uint,_GUID,Microsoft::WRL::ComPtr<IXpsOMPage>,IXpsRasterizationFactory2 *,IXpsRasterizerNotificationCallback *)

- ea: `0x18001afe4`
- end: `0x18001b0cd`
- name: `??0?$heap_implements@VXpsPageBitmapProvider@PrintCore@@@impl@winrt@@QEAA@IIIIIU_GUID@@V?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@PEAUIXpsRasterizationFactory2@@PEAUIXpsRasterizerNotificationCallback@@@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ae80`

## callees

- `0x18000df0c`
- `0x18001afe4`
- `0x18001b130`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::heap_implements<PrintCore::XpsPageBitmapProvider>(
        _QWORD *a1,
        int a2,
        int a3,
        int a4,
        int a5,
        unsigned int a6,
        __int128 *a7,
        __int64 *a8,
        __int64 a9,
        __int64 a10)
{
  __int64 *v14; // r15
  __int64 v15; // rcx
  __int128 v17; // [rsp+50h] [rbp-28h] BYREF
  _QWORD *v18; // [rsp+80h] [rbp+8h] BYREF

  v18 = a1;
  v14 = a8;
  v18 = (_QWORD *)*a8;
  Microsoft::WRL::ComPtr<IXpsOMPage>::InternalAddRef((__int64 *)&v18);
  v17 = *a7;
  PrintCore::XpsPageBitmapProvider::XpsPageBitmapProvider(
    (__int64)a1,
    a2,
    a3,
    a4,
    a5,
    a6,
    (PrintCore *)&v17,
    &v18,
    a9,
    a10);
  *a1 = &winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>'};
  a1[1] = &winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>'};
  v15 = *v14;
  if ( *v14 )
  {
    *v14 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return a1;
}

```

## disassembly

```asm
0x18001afe4  mov     r11, rsp
0x18001afe7  mov     [r11+10h], rbx
0x18001afeb  mov     [r11+18h], rsi
0x18001afef  mov     [r11+8], rcx
0x18001aff3  push    rdi
0x18001aff4  push    r14
0x18001aff6  push    r15
0x18001aff8  sub     rsp, 60h
0x18001affc  mov     ebx, r9d
0x18001afff  mov     edi, r8d
0x18001b002  mov     esi, edx
0x18001b004  mov     r14, rcx
0x18001b007  mov     r15, [r11+40h]
0x18001b00b  mov     rax, [r15]
0x18001b00e  mov     [r11+8], rax
0x18001b012  lea     rcx, [r11+8]
0x18001b016  call    ?InternalAddRef@?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXpsOMPage>::InternalAddRef(void)
0x18001b01b  mov     rax, [rsp+78h+arg_30]
0x18001b023  movaps  xmm0, xmmword ptr [rax]
0x18001b026  movdqa  [rsp+78h+var_28], xmm0
0x18001b02c  mov     rax, [rsp+78h+arg_48]
0x18001b034  mov     [rsp+78h+var_30], rax
0x18001b039  mov     rax, [rsp+78h+arg_40]
0x18001b041  mov     [rsp+78h+var_38], rax
0x18001b046  lea     rax, [rsp+78h+arg_0]
0x18001b04e  mov     [rsp+78h+var_40], rax
0x18001b053  lea     rax, [rsp+78h+var_28]
0x18001b058  mov     [rsp+78h+var_48], rax
0x18001b05d  mov     eax, [rsp+78h+arg_28]
0x18001b064  mov     [rsp+78h+var_50], eax
0x18001b068  mov     eax, [rsp+78h+arg_20]
0x18001b06f  mov     [rsp+78h+var_58], eax
0x18001b073  mov     r9d, ebx
0x18001b076  mov     r8d, edi
0x18001b079  mov     edx, esi
0x18001b07b  mov     rcx, r14
0x18001b07e  call    ??0XpsPageBitmapProvider@PrintCore@@QEAA@IIIIIU_GUID@@V?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@PEAUIXpsRasterizationFactory2@@PEAUIXpsRasterizerNotificationCallback@@@Z; PrintCore::XpsPageBitmapProvider::XpsPageBitmapProvider(uint,uint,uint,uint,uint,_GUID,Microsoft::WRL::ComPtr<IXpsOMPage>,IXpsRasterizationFactory2 *,IXpsRasterizerNotificationCallback *)
0x18001b083  lea     rax, ??_7?$heap_implements@VXpsPageBitmapProvider@PrintCore@@@impl@winrt@@6B?$producers_base@VXpsPageBitmapProvider@PrintCore@@V?$tuple@UIPageBitmapProvider@@@std@@@12@@; const winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>'}
0x18001b08a  mov     [r14], rax
0x18001b08d  lea     rax, ??_7?$heap_implements@VXpsPageBitmapProvider@PrintCore@@@impl@winrt@@6B?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@12@@; const winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>'}
0x18001b094  mov     [r14+8], rax
0x18001b098  mov     rcx, [r15]
0x18001b09b  test    rcx, rcx
0x18001b09e  jz      short loc_18001B0B4
0x18001b0a0  mov     qword ptr [r15], 0
0x18001b0a7  mov     rax, [rcx]
0x18001b0aa  mov     rax, [rax+10h]
0x18001b0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0b3  nop
0x18001b0b4  mov     rax, r14
0x18001b0b7  lea     r11, [rsp+78h+var_18]
0x18001b0bc  mov     rbx, [r11+28h]
0x18001b0c0  mov     rsi, [r11+30h]
0x18001b0c4  mov     rsp, r11
0x18001b0c7  pop     r15
0x18001b0c9  pop     r14
0x18001b0cb  pop     rdi
0x18001b0cc  retn
```
