# CCsapi::Create(ushort,bool,ResourceLoader6::ILoadResources *,bool)

- ea: `0x180066238`
- end: `0x1800664c6`
- name: `?Create@CCsapi@@SAPEAV1@G_NPEAUILoadResources@ResourceLoader6@@0@Z`
- size: `654`
- prototype: `struct CCsapi *__fastcall(unsigned __int16, bool, struct ResourceLoader6::ILoadResources *, bool)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x180062ac4`

## callees

- `0x180005190`
- `0x1800162e4`
- `0x180017858`
- `0x18001a0d8`
- `0x180030bd0`
- `0x180031b60`
- `0x180031c0c`
- `0x18003dfcc`
- `0x18003e188`
- `0x180041288`
- `0x18004cb68`
- `0x18005ffe0`
- `0x18006556c`
- `0x1800660b4`
- `0x180066238`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180066428`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180066428`
- `OLEAUT32!__imp_VariantInit` at `0x18006633e`
- `OLEAUT32!__imp_VariantInit` at `0x18006633e`

## string_xrefs

- `0x180066391`: `ProofLexPath`
- `0x180066348`: `ProofLexPathLID%04x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
struct CCsapi *__fastcall CCsapi::Create(
        unsigned __int16 a1,
        unsigned __int64 a2,
        struct ResourceLoader6::ILoadResources *a3)
{
  unsigned int v4; // r14d
  CCsapi *v5; // rdi
  __int64 v6; // rcx
  NaturalLanguageTelemetry *v7; // rcx
  volatile signed __int32 *v8; // rax
  bool v9; // r8
  unsigned int v10; // edx
  unsigned __int64 v12; // rbx
  void *v13; // r14
  const unsigned __int16 *v14; // rax
  unsigned int v15; // edx
  unsigned int v16; // edx
  unsigned int v17; // edx
  unsigned int v18; // edx
  HINSTANCE v19; // [rsp+30h] [rbp-278h] BYREF
  volatile signed __int32 *v20; // [rsp+38h] [rbp-270h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-268h] BYREF
  CCsapi *v22; // [rsp+58h] [rbp-250h]
  struct ResourceLoader6::ILoadResources *v23; // [rsp+60h] [rbp-248h]
  __int64 v24; // [rsp+68h] [rbp-240h]
  unsigned __int16 v25[256]; // [rsp+80h] [rbp-228h] BYREF

  v24 = -2;
  v4 = a1;
  v23 = a3;
  v19 = 0;
  v5 = 0;
  if ( a3 )
  {
    if ( NaturalLanguageTelemetry::IsEnabled(a1, a2) )
    {
      wil::details::static_lazy<NaturalLanguageTelemetry>::get(
        v6,
        _lambda_8b38532d7f8164044ce71ba0dfe7148a_::_lambda_invoker_cdecl_);
      NaturalLanguageTelemetry::CCsapiLoadModule_(v7, v4);
    }
    if ( (*(int (__fastcall **)(struct ResourceLoader6::ILoadResources *, _QWORD, __int64, _QWORD, HINSTANCE *))(*(_QWORD *)a3 + 80LL))(
           a3,
           (unsigned __int16)v4,
           512,
           0,
           &v19) >= 0 )
    {
      v8 = (volatile signed __int32 *)operator new(0x140u);
      v20 = v8;
      if ( v8 )
        v5 = CCsapi::CCsapi((CCsapi *)v8, v19, v9);
      else
        v5 = 0;
      v22 = v5;
      *((_BYTE *)v5 + 248) = 1;
      if ( **((_WORD **)v5 + 1) )
      {
        (*(void (__fastcall **)(struct ResourceLoader6::ILoadResources *, HINSTANCE))(*(_QWORD *)a3 + 104LL))(a3, v19);
        CCsapi::`scalar deleting destructor'(v5, v10);
        return 0;
      }
      VariantInit(&pvarg);
      StringCchPrintfW(v25, 0x100u, L"ProofLexPathLID%04x", v4);
      if ( ((*(int (__fastcall **)(struct ResourceLoader6::ILoadResources *, unsigned __int16 *, VARIANTARG *))(*(_QWORD *)a3 + 40LL))(
              a3,
              v25,
              &pvarg) < 0
         || !pvarg.vt)
        && ((*(int (__fastcall **)(struct ResourceLoader6::ILoadResources *, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)a3 + 40LL))(
              a3,
              L"ProofLexPath",
              &pvarg) < 0
         || !pvarg.vt) )
      {
        (*(void (__fastcall **)(struct ResourceLoader6::ILoadResources *, HINSTANCE))(*(_QWORD *)a3 + 104LL))(a3, v19);
        CCsapi::`scalar deleting destructor'(v5, v18);
        _variant_t::~_variant_t(&pvarg);
        return 0;
      }
      _bstr_t::_bstr_t((_bstr_t *)&v20, (const struct _variant_t *)&pvarg);
      v12 = (int)(_bstr_t::length((_bstr_t *)&v20) + 1);
      v13 = operator new[](saturated_mul(v12, 2u));
      v14 = (const unsigned __int16 *)_bstr_t::operator unsigned short const *(&v20);
      if ( StringCchCopyW((unsigned __int16 *)v13, v12, v14) < 0 )
      {
        (*(void (__fastcall **)(struct ResourceLoader6::ILoadResources *, HINSTANCE))(*(_QWORD *)a3 + 104LL))(a3, v19);
        operator delete[](v13);
        CCsapi::`scalar deleting destructor'(v5, v16);
        _bstr_t::_Free(&v20, v17);
        _variant_t::~_variant_t(&pvarg);
        return 0;
      }
      *((_QWORD *)v5 + 29) = v13;
      _bstr_t::_Free(&v20, v15);
      _variant_t::~_variant_t(&pvarg);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180066238  mov     rax, rsp
0x18006623b  push    rdi
0x18006623c  push    r14
0x18006623e  push    r15
0x180066240  sub     rsp, 290h
0x180066247  mov     [rsp+2A8h+var_240], 0FFFFFFFFFFFFFFFEh
0x180066250  mov     [rax+10h], rbx
0x180066254  mov     [rax+20h], rsi
0x180066258  mov     rax, cs:__security_cookie
0x18006625f  xor     rax, rsp
0x180066262  mov     [rsp+2A8h+var_28], rax
0x18006626a  mov     rsi, r8
0x18006626d  movzx   r14d, cx
0x180066271  mov     [rsp+2A8h+var_248], r8
0x180066276  xor     r15d, r15d
0x180066279  mov     [rsp+2A8h+var_278], r15
0x18006627e  mov     edi, r15d
0x180066281  test    r8, r8
0x180066284  jz      loc_18006646C
0x18006628a  mov     ebx, r14d
0x18006628d  call    ?IsEnabled@NaturalLanguageTelemetry@@SA_NE_K@Z; NaturalLanguageTelemetry::IsEnabled(uchar,unsigned __int64)
0x180066292  test    al, al
0x180066294  jz      short loc_1800662A9
0x180066296  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8b38532d7f8164044ce71ba0dfe7148a_@@CA@XZ; _lambda_8b38532d7f8164044ce71ba0dfe7148a_::_lambda_invoker_cdecl_(void)
0x18006629d  call    ?get@?$static_lazy@VNaturalLanguageTelemetry@@@details@wil@@QEAAPEAVNaturalLanguageTelemetry@@P6AXXZ@Z; wil::details::static_lazy<NaturalLanguageTelemetry>::get(void (*)(void))
0x1800662a2  mov     edx, ebx; unsigned int
0x1800662a4  call    ?CCsapiLoadModule_@NaturalLanguageTelemetry@@QEBAXK@Z; NaturalLanguageTelemetry::CCsapiLoadModule_(ulong)
0x1800662a9  mov     rax, [rsi]
0x1800662ac  lea     rcx, [rsp+2A8h+var_278]
0x1800662b1  mov     [rsp+2A8h+var_288], rcx
0x1800662b6  xor     r9d, r9d
0x1800662b9  mov     r8d, 200h
0x1800662bf  movzx   edx, r14w
0x1800662c3  mov     rcx, rsi
0x1800662c6  mov     rax, [rax+50h]
0x1800662ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800662cf  test    eax, eax
0x1800662d1  js      loc_18006646C
0x1800662d7  mov     ecx, 140h; Size
0x1800662dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800662e1  mov     [rsp+2A8h+var_270], rax
0x1800662e6  test    rax, rax
0x1800662e9  jz      short loc_1800662FD
0x1800662eb  mov     rdx, [rsp+2A8h+var_278]; HINSTANCE
0x1800662f0  mov     rcx, rax; this
0x1800662f3  call    ??0CCsapi@@QEAA@QEAUHINSTANCE__@@_N@Z; CCsapi::CCsapi(HINSTANCE__ * const,bool)
0x1800662f8  mov     rdi, rax
0x1800662fb  jmp     short loc_180066300
0x1800662fd  mov     rdi, r15
0x180066300  mov     [rsp+2A8h+var_250], rdi
0x180066305  mov     byte ptr [rdi+0F8h], 1
0x18006630c  mov     rax, [rdi+8]
0x180066310  cmp     [rax], r15w
0x180066314  jz      short loc_180066339
0x180066316  mov     rax, [rsi]
0x180066319  mov     rdx, [rsp+2A8h+var_278]
0x18006631e  mov     rcx, rsi
0x180066321  mov     rax, [rax+68h]
0x180066325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006632a  mov     rcx, rdi; this
0x18006632d  call    ??_GCCsapi@@QEAAPEAXI@Z; CCsapi::`scalar deleting destructor'(uint)
0x180066332  xor     eax, eax
0x180066334  jmp     loc_18006646F
0x180066339  lea     rcx, [rsp+2A8h+pvarg]; pvarg
0x18006633e  call    cs:__imp_VariantInit
0x180066344  nop
0x180066345  mov     r9d, ebx
0x180066348  lea     r8, aProoflexpathli; "ProofLexPathLID%04x"
0x18006634f  mov     edx, 100h; unsigned __int64
0x180066354  lea     rcx, [rsp+2A8h+var_228]; unsigned __int16 *
0x18006635c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180066361  mov     rax, [rsi]
0x180066364  lea     r8, [rsp+2A8h+pvarg]
0x180066369  lea     rdx, [rsp+2A8h+var_228]
0x180066371  mov     rcx, rsi
0x180066374  mov     rax, [rax+28h]
0x180066378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006637d  test    eax, eax
0x18006637f  js      short loc_180066389
0x180066381  cmp     word ptr [rsp+2A8h+pvarg], r15w
0x180066387  jnz     short loc_1800663B8
0x180066389  mov     rax, [rsi]
0x18006638c  lea     r8, [rsp+2A8h+pvarg]
0x180066391  lea     rdx, aProoflexpath; "ProofLexPath"
0x180066398  mov     rcx, rsi
0x18006639b  mov     rax, [rax+28h]
0x18006639f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800663a4  test    eax, eax
0x1800663a6  js      loc_1800664A7
0x1800663ac  cmp     word ptr [rsp+2A8h+pvarg], r15w
0x1800663b2  jz      loc_1800664A7
0x1800663b8  lea     rdx, [rsp+2A8h+pvarg]; struct _variant_t *
0x1800663bd  lea     rcx, [rsp+2A8h+var_270]; this
0x1800663c2  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x1800663c7  nop
0x1800663c8  lea     rcx, [rsp+2A8h+var_270]; this
0x1800663cd  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x1800663d2  inc     eax
0x1800663d4  movsxd  rbx, eax
0x1800663d7  mov     eax, 2
0x1800663dc  mul     rbx
0x1800663df  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800663e6  cmovb   rax, rcx
0x1800663ea  mov     rcx, rax; unsigned __int64
0x1800663ed  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800663f2  mov     r14, rax
0x1800663f5  lea     rcx, [rsp+2A8h+var_270]
0x1800663fa  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x1800663ff  mov     r8, rax; unsigned __int16 *
0x180066402  mov     rdx, rbx; unsigned __int64
0x180066405  mov     rcx, r14; unsigned __int16 *
0x180066408  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006640d  test    eax, eax
0x18006640f  jns     short loc_180066450
0x180066411  mov     rcx, [rsi]
0x180066414  mov     rax, [rcx+68h]
0x180066418  mov     rdx, [rsp+2A8h+var_278]
0x18006641d  mov     rcx, rsi
0x180066420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066425  mov     rcx, r14
0x180066428  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18006642e  mov     rcx, rdi; this
0x180066431  call    ??_GCCsapi@@QEAAPEAXI@Z; CCsapi::`scalar deleting destructor'(uint)
0x180066436  nop
0x180066437  lea     rcx, [rsp+2A8h+var_270]; this
0x18006643c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180066441  nop
0x180066442  lea     rcx, [rsp+2A8h+pvarg]; this
0x180066447  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006644c  xor     eax, eax
0x18006644e  jmp     short loc_18006646F
0x180066450  mov     [rdi+0E8h], r14
0x180066457  lea     rcx, [rsp+2A8h+var_270]; this
0x18006645c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180066461  nop
0x180066462  lea     rcx, [rsp+2A8h+pvarg]; this
0x180066467  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006646c  mov     rax, rdi
0x18006646f  mov     rcx, [rsp+2A8h+var_28]
0x180066477  xor     rcx, rsp; StackCookie
0x18006647a  call    __security_check_cookie
0x18006647f  lea     r11, [rsp+2A8h+var_18]
0x180066487  mov     rbx, [r11+28h]
0x18006648b  mov     rsi, [r11+38h]
0x18006648f  mov     rsp, r11
0x180066492  pop     r15
0x180066494  pop     r14
0x180066496  pop     rdi
0x180066497  retn
0x180066498  lea     rcx, [rsp+2A8h+pvarg]; this
0x18006649d  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800664a2  jmp     loc_180066332
0x1800664a7  mov     rax, [rsi]
0x1800664aa  mov     rdx, [rsp+2A8h+var_278]
0x1800664af  mov     rcx, rsi
0x1800664b2  mov     rax, [rax+68h]
0x1800664b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800664bb  mov     rcx, rdi; this
0x1800664be  call    ??_GCCsapi@@QEAAPEAXI@Z; CCsapi::`scalar deleting destructor'(uint)
0x1800664c3  jmp     short loc_180066498
```
