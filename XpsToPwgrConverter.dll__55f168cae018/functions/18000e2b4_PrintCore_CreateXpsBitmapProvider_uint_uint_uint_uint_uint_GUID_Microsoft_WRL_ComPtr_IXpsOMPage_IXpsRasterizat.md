# PrintCore::CreateXpsBitmapProvider(uint,uint,uint,uint,uint,_GUID,Microsoft::WRL::ComPtr<IXpsOMPage>,IXpsRasterizationFactory2 *,IXpsRasterizerNotificationCallback *,IPageBitmapProvider * *)

- ea: `0x18000e2b4`
- end: `0x18000e45c`
- name: `?CreateXpsBitmapProvider@PrintCore@@YAJIIIIIU_GUID@@V?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@PEAUIXpsRasterizationFactory2@@PEAUIXpsRasterizerNotificationCallback@@PEAPEAUIPageBitmapProvider@@@Z`
- size: `424`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000927c`

## callees

- `0x18000200c`
- `0x18000dc78`
- `0x18000e2b4`
- `0x180011010`

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
  unsigned int v17; // r8d
  const char *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v22; // rcx
  unsigned int v24; // [rsp+50h] [rbp-78h]
  __int64 v25; // [rsp+58h] [rbp-70h] BYREF
  __int64 v26; // [rsp+60h] [rbp-68h] BYREF
  __int64 v27; // [rsp+68h] [rbp-60h]
  __int64 v28; // [rsp+70h] [rbp-58h]
  __int64 *v29; // [rsp+78h] [rbp-50h]
  _QWORD *v30; // [rsp+80h] [rbp-48h]
  __int64 *v31; // [rsp+88h] [rbp-40h]
  __int128 Buf1[3]; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  try
  {
    v29 = a7;
    v28 = a8;
    v27 = a9;
    *a10 = 0;
    v15 = operator new(0x78u);
    v30 = v15;
    v16 = *a7;
    v25 = v16;
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
      v16 = v25;
    }
    v31 = &v25;
    v26 = v16;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    Buf1[0] = *a6;
    PrintCore::XpsPageBitmapProvider::XpsPageBitmapProvider((__int64)v15, a1, a2, a3, a4, a5, Buf1, &v26, v28, v27);
    *v15 = &winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>'};
    v15[1] = &winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>'};
    v19 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  catch ( ... )
  {
    v24 = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x89, v17, v18);
    v22 = *v29;
    if ( *v29 )
    {
      *v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return v24;
  }
  *a10 = v15;
  v20 = *a7;
  if ( *a7 )
  {
    *a7 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e2b4  mov     [rsp+arg_18], rsi
0x18000e2b9  push    rdi
0x18000e2ba  push    r12
0x18000e2bc  push    r13
0x18000e2be  push    r14
0x18000e2c0  push    r15
0x18000e2c2  sub     rsp, 0A0h
0x18000e2c9  mov     r15d, r9d
0x18000e2cc  mov     [rsp+0C8h+var_78], r8d
0x18000e2d1  mov     r13d, edx
0x18000e2d4  mov     r12d, ecx
0x18000e2d7  mov     rsi, [rsp+0C8h+arg_30]
0x18000e2df  mov     [rsp+0C8h+var_50], rsi
0x18000e2e4  mov     rax, [rsp+0C8h+arg_38]
0x18000e2ec  mov     [rsp+0C8h+var_58], rax
0x18000e2f1  mov     rax, [rsp+0C8h+arg_40]
0x18000e2f9  mov     [rsp+0C8h+var_60], rax
0x18000e2fe  mov     r14, [rsp+0C8h+arg_48]
0x18000e306  mov     qword ptr [r14], 0
0x18000e30d  mov     ecx, 78h ; 'x'; Size
0x18000e312  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e317  mov     rdi, rax
0x18000e31a  mov     [rsp+0C8h+var_48], rax
0x18000e322  mov     rcx, [rsi]
0x18000e325  mov     [rsp+0C8h+var_70], rcx
0x18000e32a  test    rcx, rcx
0x18000e32d  jz      short loc_18000E340
0x18000e32f  mov     rax, [rcx]
0x18000e332  mov     rax, [rax+8]
0x18000e336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e33b  mov     rcx, [rsp+0C8h+var_70]
0x18000e340  lea     rax, [rsp+0C8h+var_70]
0x18000e345  mov     [rsp+0C8h+var_40], rax
0x18000e34d  mov     [rsp+0C8h+var_68], rcx
0x18000e352  test    rcx, rcx
0x18000e355  jz      short loc_18000E364
0x18000e357  mov     rax, [rcx]
0x18000e35a  mov     rax, [rax+8]
0x18000e35e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e363  nop
0x18000e364  mov     rax, [rsp+0C8h+arg_28]
0x18000e36c  movups  xmm0, xmmword ptr [rax]
0x18000e36f  movdqu  [rsp+0C8h+var_38], xmm0
0x18000e378  mov     rax, [rsp+0C8h+var_60]
0x18000e37d  mov     [rsp+0C8h+var_80], rax; __int64
0x18000e382  mov     rax, [rsp+0C8h+var_58]
0x18000e387  mov     [rsp+0C8h+var_88], rax; __int64
0x18000e38c  lea     rax, [rsp+0C8h+var_68]
0x18000e391  mov     [rsp+0C8h+var_90], rax; __int64
0x18000e396  lea     rax, [rsp+0C8h+var_38]
0x18000e39e  mov     [rsp+0C8h+Buf1], rax; Buf1
0x18000e3a3  mov     eax, [rsp+0C8h+arg_20]
0x18000e3aa  mov     [rsp+0C8h+var_A0], eax; int
0x18000e3ae  mov     [rsp+0C8h+var_A8], r15d; int
0x18000e3b3  mov     r9d, [rsp+0C8h+var_78]; int
0x18000e3b8  mov     r8d, r13d; int
0x18000e3bb  mov     edx, r12d; int
0x18000e3be  mov     rcx, rdi; int
0x18000e3c1  call    ??0XpsPageBitmapProvider@PrintCore@@QEAA@IIIIIU_GUID@@V?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@PEAUIXpsRasterizationFactory2@@PEAUIXpsRasterizerNotificationCallback@@@Z; PrintCore::XpsPageBitmapProvider::XpsPageBitmapProvider(uint,uint,uint,uint,uint,_GUID,Microsoft::WRL::ComPtr<IXpsOMPage>,IXpsRasterizationFactory2 *,IXpsRasterizerNotificationCallback *)
0x18000e3c6  lea     rax, ??_7?$heap_implements@VXpsPageBitmapProvider@PrintCore@@@impl@winrt@@6B?$producers_base@VXpsPageBitmapProvider@PrintCore@@V?$tuple@UIPageBitmapProvider@@@std@@@12@@; const winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::producers_base<PrintCore::XpsPageBitmapProvider,std::tuple<IPageBitmapProvider>>'}
0x18000e3cd  mov     [rdi], rax
0x18000e3d0  lea     rax, ??_7?$heap_implements@VXpsPageBitmapProvider@PrintCore@@@impl@winrt@@6B?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@12@@; const winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::`vftable'{for `winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>'}
0x18000e3d7  mov     [rdi+8], rax
0x18000e3db  mov     rcx, [rsp+0C8h+var_70]
0x18000e3e0  test    rcx, rcx
0x18000e3e3  jz      short loc_18000E3FB
0x18000e3e5  mov     [rsp+0C8h+var_70], 0
0x18000e3ee  mov     rax, [rcx]
0x18000e3f1  mov     rax, [rax+10h]
0x18000e3f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3fa  nop
0x18000e3fb  mov     [r14], rdi
0x18000e3fe  mov     rcx, [rsi]
0x18000e401  test    rcx, rcx
0x18000e404  jz      short loc_18000E41A
0x18000e406  mov     qword ptr [rsi], 0
0x18000e40d  mov     rax, [rcx]
0x18000e410  mov     rax, [rax+10h]
0x18000e414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e419  nop
0x18000e41a  xor     eax, eax
0x18000e41c  jmp     short loc_18000E443
0x18000e41e  mov     rax, [rsp+0C8h+var_50]
0x18000e423  mov     rcx, [rax]
0x18000e426  test    rcx, rcx
0x18000e429  jz      short loc_18000E43F
0x18000e42b  mov     qword ptr [rax], 0
0x18000e432  mov     rax, [rcx]
0x18000e435  mov     rax, [rax+10h]
0x18000e439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e43e  nop
0x18000e43f  mov     eax, [rsp+0C8h+var_78]
0x18000e443  mov     rsi, [rsp+0C8h+arg_18]
0x18000e44b  add     rsp, 0A0h
0x18000e452  pop     r15
0x18000e454  pop     r14
0x18000e456  pop     r13
0x18000e458  pop     r12
0x18000e45a  pop     rdi
0x18000e45b  retn
```
