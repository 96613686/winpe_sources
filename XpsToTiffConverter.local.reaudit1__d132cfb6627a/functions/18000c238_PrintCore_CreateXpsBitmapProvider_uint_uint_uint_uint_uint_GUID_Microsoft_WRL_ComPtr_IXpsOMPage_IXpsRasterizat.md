# PrintCore::CreateXpsBitmapProvider(uint,uint,uint,uint,uint,_GUID,Microsoft::WRL::ComPtr<IXpsOMPage>,IXpsRasterizationFactory2 *,IXpsRasterizerNotificationCallback *,IPageBitmapProvider * *)

- ea: `0x18000c238`
- end: `0x18000c3e0`
- name: `?CreateXpsBitmapProvider@PrintCore@@YAJIIIIIU_GUID@@V?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@PEAUIXpsRasterizationFactory2@@PEAUIXpsRasterizerNotificationCallback@@PEAPEAUIPageBitmapProvider@@@Z`
- size: `424`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ac30`

## callees

- `0x180001aac`
- `0x18000be40`
- `0x18000c238`
- `0x18000e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall PrintCore::CreateXpsBitmapProvider(
        int a1,
        int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int128 *a6,
        __int64 *a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10)
{
  _QWORD *v15; // rdi
  __int64 v16; // rcx
  const char *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v21; // rcx
  unsigned int v23; // [rsp+50h] [rbp-78h]
  __int64 v24; // [rsp+58h] [rbp-70h] BYREF
  __int64 v25; // [rsp+60h] [rbp-68h] BYREF
  __int64 v26; // [rsp+68h] [rbp-60h]
  __int64 v27; // [rsp+70h] [rbp-58h]
  __int64 *v28; // [rsp+78h] [rbp-50h]
  _QWORD *v29; // [rsp+80h] [rbp-48h]
  __int64 *v30; // [rsp+88h] [rbp-40h]
  __int128 Buf1[3]; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  try
  {
    v28 = a7;
    v27 = a8;
    v26 = a9;
    *a10 = 0;
    v15 = operator new(0x78u);
    v29 = v15;
    v16 = *a7;
    v24 = v16;
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
      v16 = v24;
    }
    v30 = &v24;
    v25 = v16;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    Buf1[0] = *a6;
    PrintCore::XpsPageBitmapProvider::XpsPageBitmapProvider((__int64)v15, a1, a2, a3, a4, a5, Buf1, &v25, v27, v26);
    *v15 = &winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>'};
    v15[1] = &winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>'};
    v18 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
  }
  catch ( ... )
  {
    v23 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x89,
            (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpsbitmapprovider\\xpspagebitmapprovider.cpp",
            v17);
    v21 = *v28;
    if ( *v28 )
    {
      *v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    return v23;
  }
  *a10 = v15;
  v19 = *a7;
  if ( *a7 )
  {
    *a7 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c238  mov     [rsp+arg_18], rsi
0x18000c23d  push    rdi
0x18000c23e  push    r12
0x18000c240  push    r13
0x18000c242  push    r14
0x18000c244  push    r15
0x18000c246  sub     rsp, 0A0h
0x18000c24d  mov     r15d, r9d
0x18000c250  mov     [rsp+0C8h+var_78], r8d
0x18000c255  mov     r13d, edx
0x18000c258  mov     r12d, ecx
0x18000c25b  mov     rsi, [rsp+0C8h+arg_30]
0x18000c263  mov     [rsp+0C8h+var_50], rsi
0x18000c268  mov     rax, [rsp+0C8h+arg_38]
0x18000c270  mov     [rsp+0C8h+var_58], rax
0x18000c275  mov     rax, [rsp+0C8h+arg_40]
0x18000c27d  mov     [rsp+0C8h+var_60], rax
0x18000c282  mov     r14, [rsp+0C8h+arg_48]
0x18000c28a  mov     qword ptr [r14], 0
0x18000c291  mov     ecx, 78h ; 'x'; Size
0x18000c296  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c29b  mov     rdi, rax
0x18000c29e  mov     [rsp+0C8h+var_48], rax
0x18000c2a6  mov     rcx, [rsi]
0x18000c2a9  mov     [rsp+0C8h+var_70], rcx
0x18000c2ae  test    rcx, rcx
0x18000c2b1  jz      short loc_18000C2C4
0x18000c2b3  mov     rax, [rcx]
0x18000c2b6  mov     rax, [rax+8]
0x18000c2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2bf  mov     rcx, [rsp+0C8h+var_70]
0x18000c2c4  lea     rax, [rsp+0C8h+var_70]
0x18000c2c9  mov     [rsp+0C8h+var_40], rax
0x18000c2d1  mov     [rsp+0C8h+var_68], rcx
0x18000c2d6  test    rcx, rcx
0x18000c2d9  jz      short loc_18000C2E8
0x18000c2db  mov     rax, [rcx]
0x18000c2de  mov     rax, [rax+8]
0x18000c2e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2e7  nop
0x18000c2e8  mov     rax, [rsp+0C8h+arg_28]
0x18000c2f0  movups  xmm0, xmmword ptr [rax]
0x18000c2f3  movdqu  [rsp+0C8h+var_38], xmm0
0x18000c2fc  mov     rax, [rsp+0C8h+var_60]
0x18000c301  mov     [rsp+0C8h+var_80], rax; __int64
0x18000c306  mov     rax, [rsp+0C8h+var_58]
0x18000c30b  mov     [rsp+0C8h+var_88], rax; __int64
0x18000c310  lea     rax, [rsp+0C8h+var_68]
0x18000c315  mov     [rsp+0C8h+var_90], rax; __int64
0x18000c31a  lea     rax, [rsp+0C8h+var_38]
0x18000c322  mov     [rsp+0C8h+Buf1], rax; Buf1
0x18000c327  mov     eax, [rsp+0C8h+arg_20]
0x18000c32e  mov     [rsp+0C8h+var_A0], eax; int
0x18000c332  mov     [rsp+0C8h+var_A8], r15d; int
0x18000c337  mov     r9d, [rsp+0C8h+var_78]; int
0x18000c33c  mov     r8d, r13d; int
0x18000c33f  mov     edx, r12d; int
0x18000c342  mov     rcx, rdi; int
0x18000c345  call    ??0XpsPageBitmapProvider@PrintCore@@QEAA@IIIIIU_GUID@@V?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@PEAUIXpsRasterizationFactory2@@PEAUIXpsRasterizerNotificationCallback@@@Z; PrintCore::XpsPageBitmapProvider::XpsPageBitmapProvider(uint,uint,uint,uint,uint,_GUID,Microsoft::WRL::ComPtr<IXpsOMPage>,IXpsRasterizationFactory2 *,IXpsRasterizerNotificationCallback *)
0x18000c34a  lea     rax, ??_7?$heap_implements@VXpsPageBitmapProvider@PrintCore@@@impl@winrt@@6B?$producers_base@VXpsPageBitmapProvider@PrintCore@@V?$tuple@UIPageBitmapProvider@@@std@@@12@@; const winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>'}
0x18000c351  mov     [rdi], rax
0x18000c354  lea     rax, ??_7?$heap_implements@VXpsPageBitmapProvider@PrintCore@@@impl@winrt@@6B?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@12@@; const winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>'}
0x18000c35b  mov     [rdi+8], rax
0x18000c35f  mov     rcx, [rsp+0C8h+var_70]
0x18000c364  test    rcx, rcx
0x18000c367  jz      short loc_18000C37F
0x18000c369  mov     [rsp+0C8h+var_70], 0
0x18000c372  mov     rax, [rcx]
0x18000c375  mov     rax, [rax+10h]
0x18000c379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c37e  nop
0x18000c37f  mov     [r14], rdi
0x18000c382  mov     rcx, [rsi]
0x18000c385  test    rcx, rcx
0x18000c388  jz      short loc_18000C39E
0x18000c38a  mov     qword ptr [rsi], 0
0x18000c391  mov     rax, [rcx]
0x18000c394  mov     rax, [rax+10h]
0x18000c398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c39d  nop
0x18000c39e  xor     eax, eax
0x18000c3a0  jmp     short loc_18000C3C7
0x18000c3a2  mov     rax, [rsp+0C8h+var_50]
0x18000c3a7  mov     rcx, [rax]
0x18000c3aa  test    rcx, rcx
0x18000c3ad  jz      short loc_18000C3C3
0x18000c3af  mov     qword ptr [rax], 0
0x18000c3b6  mov     rax, [rcx]
0x18000c3b9  mov     rax, [rax+10h]
0x18000c3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3c2  nop
0x18000c3c3  mov     eax, [rsp+0C8h+var_78]
0x18000c3c7  mov     rsi, [rsp+0C8h+arg_18]
0x18000c3cf  add     rsp, 0A0h
0x18000c3d6  pop     r15
0x18000c3d8  pop     r14
0x18000c3da  pop     r13
0x18000c3dc  pop     r12
0x18000c3de  pop     rdi
0x18000c3df  retn
```
