# CSpellerGlobalState::BackgroundInitialize(void)

- ea: `0x180272bf4`
- end: `0x180272e4c`
- name: `?BackgroundInitialize@CSpellerGlobalState@@AEAAXXZ`
- size: `600`
- prototype: `void __fastcall(CSpellerGlobalState *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18026f440`

## callees

- `0x180048d5c`
- `0x1800fea60`
- `0x180123e7c`
- `0x180127034`
- `0x18013beb8`
- `0x18026f458`
- `0x18026faf8`
- `0x180270444`
- `0x180272ba0`
- `0x180272bf4`
- `0x180272e54`
- `0x180276b74`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180272c17`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180272c17`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180272cb9`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180272cd5`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180272cb9`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180272cd5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180272e06`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180272e06`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180272db1`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180272ddc`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180272db1`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180272ddc`

## pseudocode

```c
void __fastcall CSpellerGlobalState::BackgroundInitialize(CSpellerGlobalState *this)
{
  HRESULT v2; // eax
  unsigned __int64 v3; // rdx
  unsigned __int8 v4; // cl
  HRESULT MultilingualSpellers; // r14d
  char v6; // r15
  unsigned int v7; // r12d
  __int64 (__fastcall *v8)(LPUNKNOWN *); // rbx
  HSTRING CurrentInputMethodLanguageTag; // rax
  struct ISpellChecker *Speller; // rax
  HRESULT v11; // eax
  LPUNKNOWN v12; // rbx
  _DWORD *v13; // rax
  struct ISpellCheckerFactory *v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  LPUNKNOWN v17; // [rsp+50h] [rbp+30h] BYREF
  LPUNKNOWN v18; // [rsp+58h] [rbp+38h] BYREF
  LPUNKNOWN pUnk; // [rsp+60h] [rbp+40h] BYREF

  CSpellerGlobalState::CalculateSettings(this);
  v2 = CoInitializeEx(0, 2u);
  MultilingualSpellers = v2;
  if ( v2 == -2147417850 )
  {
    v6 = 0;
    v7 = 1;
  }
  else
  {
    v7 = 0;
    v6 = 1;
    if ( v2 < 0 )
      goto LABEL_24;
  }
  v8 = (__int64 (__fastcall *)(LPUNKNOWN *))*((_QWORD *)this + 12);
  v18 = 0;
  pUnk = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  MultilingualSpellers = v8(&v18);
  if ( MultilingualSpellers >= 0 )
  {
    CurrentInputMethodLanguageTag = CSpellerGlobalState::GetCurrentInputMethodLanguageTag(this, *((_DWORD *)this + 18));
    Speller = CreateSpeller(
                (struct ISpellCheckerFactory *)v18,
                *((_DWORD *)this + 18),
                CurrentInputMethodLanguageTag,
                *((_BYTE *)this + 340) == 0);
    Microsoft::WRL::ComPtr<ISpellChecker>::operator=(&pUnk, Speller);
    if ( !pUnk
      || (MultilingualSpellers = CoMarshalInterThreadInterfaceInStream(
                                   &GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b,
                                   pUnk,
                                   (LPSTREAM *)this + 15),
          MultilingualSpellers >= 0) )
    {
      v11 = CoMarshalInterThreadInterfaceInStream(
              &GUID_8e018a9d_2415_4677_bf08_794ea61f94bb,
              v18,
              (LPSTREAM *)this + 14);
      v12 = v18;
      MultilingualSpellers = v11;
      if ( *((LPUNKNOWN *)this + 6) != v18 )
      {
        v17 = v18;
        Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalAddRef(&v17);
        v17 = (LPUNKNOWN)*((_QWORD *)this + 6);
        *((_QWORD *)this + 6) = v12;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
      }
      if ( MultilingualSpellers >= 0 )
      {
        v13 = operator new(0x18u);
        *(_QWORD *)v13 = 0;
        v13[2] = 8;
        *((_QWORD *)v13 + 2) = 0;
        v14 = (struct ISpellCheckerFactory *)v18;
        *((_QWORD *)this + 3) = v13;
        MultilingualSpellers = CSpellerGlobalState::CreateMultilingualSpellers(this, v14, 1);
      }
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 48);
  if ( MultilingualSpellers < 0 )
    goto LABEL_14;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 26, 3, 1) != 1 )
  {
    MultilingualSpellers = -2147467260;
LABEL_14:
    _InterlockedCompareExchange((volatile signed __int32 *)this + 26, 4, 1);
    if ( v18 )
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    if ( pUnk )
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    if ( CoGetInterfaceAndReleaseStream(
           *((LPSTREAM *)this + 15),
           &GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b,
           (LPVOID *)&pUnk) >= 0 )
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    if ( CoGetInterfaceAndReleaseStream(
           *((LPSTREAM *)this + 14),
           &GUID_8e018a9d_2415_4677_bf08_794ea61f94bb,
           (LPVOID *)&v18) >= 0 )
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  if ( v6 )
    CoUninitialize();
LABEL_24:
  if ( CSpellCheckerTelemetry::IsEnabled(v4, v3) )
  {
    wil::details::static_lazy<CSpellCheckerTelemetry>::get(
      v15,
      _lambda_3c853e741dc03bb96b7f8662095382b4_::_lambda_invoker_cdecl_);
    CSpellCheckerTelemetry::LogSpellerBackCoInitStatus_(v16, v7, (unsigned int)MultilingualSpellers);
  }
  (*(void (__fastcall **)(CSpellerGlobalState *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x180272bf4  mov     [rsp-28h+arg_18], rbx
0x180272bf9  push    rbp
0x180272bfa  push    rsi
0x180272bfb  push    r12
0x180272bfd  push    r14
0x180272bff  push    r15
0x180272c01  mov     rbp, rsp
0x180272c04  sub     rsp, 20h
0x180272c08  mov     rsi, rcx
0x180272c0b  call    ?CalculateSettings@CSpellerGlobalState@@AEAAXXZ; CSpellerGlobalState::CalculateSettings(void)
0x180272c10  mov     edx, 2; dwCoInit
0x180272c15  xor     ecx, ecx; pvReserved
0x180272c17  call    cs:__imp_CoInitializeEx
0x180272c1d  mov     r14d, eax
0x180272c20  cmp     eax, 80010106h
0x180272c25  jnz     short loc_180272C32
0x180272c27  xor     r15b, r15b
0x180272c2a  mov     r12d, 1
0x180272c30  jmp     short loc_180272C40
0x180272c32  xor     r12d, r12d
0x180272c35  mov     r15b, 1
0x180272c38  test    eax, eax
0x180272c3a  js      loc_180272E0C
0x180272c40  mov     rbx, [rsi+60h]
0x180272c44  lea     rcx, [rbp+arg_8]
0x180272c48  mov     [rbp+arg_8], 0
0x180272c50  mov     [rbp+pUnk], 0
0x180272c58  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180272c5d  lea     rcx, [rbp+arg_8]
0x180272c61  mov     rax, rbx
0x180272c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180272c69  mov     r14d, eax
0x180272c6c  test    eax, eax
0x180272c6e  js      loc_180272D45
0x180272c74  mov     edx, [rsi+48h]; unsigned int
0x180272c77  mov     rcx, rsi; this
0x180272c7a  call    ?GetCurrentInputMethodLanguageTag@CSpellerGlobalState@@AEBAPEAUHSTRING__@@K@Z; CSpellerGlobalState::GetCurrentInputMethodLanguageTag(ulong)
0x180272c7f  cmp     byte ptr [rsi+154h], 0
0x180272c86  mov     r8, rax; HSTRING
0x180272c89  mov     edx, [rsi+48h]; unsigned int
0x180272c8c  mov     rcx, [rbp+arg_8]; struct ISpellCheckerFactory *
0x180272c90  setz    r9b; bool
0x180272c94  call    ?CreateSpeller@@YAPEAUISpellChecker@@PEAUISpellCheckerFactory@@KPEAUHSTRING__@@_N@Z; CreateSpeller(ISpellCheckerFactory *,ulong,HSTRING__ *,bool)
0x180272c99  mov     rdx, rax
0x180272c9c  lea     rcx, [rbp+pUnk]
0x180272ca0  call    ??4?$ComPtr@UISpellChecker@@@WRL@Microsoft@@QEAAAEAV012@PEAUISpellChecker@@@Z; Microsoft::WRL::ComPtr<ISpellChecker>::operator=(ISpellChecker *)
0x180272ca5  mov     rdx, [rbp+pUnk]; pUnk
0x180272ca9  test    rdx, rdx
0x180272cac  jz      short loc_180272CC6
0x180272cae  lea     r8, [rsi+78h]; ppStm
0x180272cb2  lea     rcx, _GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b; riid
0x180272cb9  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180272cbf  mov     r14d, eax
0x180272cc2  test    eax, eax
0x180272cc4  js      short loc_180272D45
0x180272cc6  mov     rdx, [rbp+arg_8]; pUnk
0x180272cca  lea     r8, [rsi+70h]; ppStm
0x180272cce  lea     rcx, _GUID_8e018a9d_2415_4677_bf08_794ea61f94bb; riid
0x180272cd5  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180272cdb  mov     rbx, [rbp+arg_8]
0x180272cdf  mov     r14d, eax
0x180272ce2  cmp     [rsi+30h], rbx
0x180272ce6  jz      short loc_180272D0A
0x180272ce8  lea     rcx, [rbp+arg_0]
0x180272cec  mov     [rbp+arg_0], rbx
0x180272cf0  call    ?InternalAddRef@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalAddRef(void)
0x180272cf5  mov     rax, [rsi+30h]
0x180272cf9  lea     rcx, [rbp+arg_0]
0x180272cfd  mov     [rbp+arg_0], rax
0x180272d01  mov     [rsi+30h], rbx
0x180272d05  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180272d0a  test    r14d, r14d
0x180272d0d  js      short loc_180272D45
0x180272d0f  mov     ecx, 18h; Size
0x180272d14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180272d19  mov     r8b, 1; bool
0x180272d1c  mov     rcx, rsi; this
0x180272d1f  mov     qword ptr [rax], 0
0x180272d26  mov     dword ptr [rax+8], 8
0x180272d2d  mov     qword ptr [rax+10h], 0
0x180272d35  mov     rdx, [rbp+arg_8]; struct ISpellCheckerFactory *
0x180272d39  mov     [rsi+18h], rax
0x180272d3d  call    ?CreateMultilingualSpellers@CSpellerGlobalState@@QEAAJPEAUISpellCheckerFactory@@_N@Z; CSpellerGlobalState::CreateMultilingualSpellers(ISpellCheckerFactory *,bool)
0x180272d42  mov     r14d, eax
0x180272d45  lea     rcx, [rsi+30h]
0x180272d49  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180272d4e  test    r14d, r14d
0x180272d51  js      short loc_180272D6C
0x180272d53  mov     ecx, 3
0x180272d58  lea     eax, [rcx-2]
0x180272d5b  lock cmpxchg [rsi+68h], ecx
0x180272d60  jz      loc_180272DEF
0x180272d66  mov     r14d, 80004004h
0x180272d6c  mov     ecx, 4
0x180272d71  lea     eax, [rcx-3]
0x180272d74  lock cmpxchg [rsi+68h], ecx
0x180272d79  cmp     [rbp+arg_8], 0
0x180272d7e  jz      short loc_180272D89
0x180272d80  lea     rcx, [rbp+arg_8]
0x180272d84  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180272d89  cmp     [rbp+pUnk], 0
0x180272d8e  jz      short loc_180272D99
0x180272d90  lea     rcx, [rbp+pUnk]
0x180272d94  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180272d99  lea     rcx, [rbp+pUnk]
0x180272d9d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180272da2  mov     rcx, [rsi+78h]; pStm
0x180272da6  lea     r8, [rbp+pUnk]; ppv
0x180272daa  lea     rdx, _GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b; iid
0x180272db1  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180272db7  test    eax, eax
0x180272db9  js      short loc_180272DC4
0x180272dbb  lea     rcx, [rbp+pUnk]
0x180272dbf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180272dc4  lea     rcx, [rbp+arg_8]
0x180272dc8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180272dcd  mov     rcx, [rsi+70h]; pStm
0x180272dd1  lea     r8, [rbp+arg_8]; ppv
0x180272dd5  lea     rdx, _GUID_8e018a9d_2415_4677_bf08_794ea61f94bb; iid
0x180272ddc  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180272de2  test    eax, eax
0x180272de4  js      short loc_180272DEF
0x180272de6  lea     rcx, [rbp+arg_8]
0x180272dea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180272def  lea     rcx, [rbp+pUnk]
0x180272df3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180272df8  lea     rcx, [rbp+arg_8]
0x180272dfc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180272e01  test    r15b, r15b
0x180272e04  jz      short loc_180272E0C
0x180272e06  call    cs:__imp_CoUninitialize
0x180272e0c  call    ?IsEnabled@CSpellCheckerTelemetry@@SA_NE_K@Z; CSpellCheckerTelemetry::IsEnabled(uchar,unsigned __int64)
0x180272e11  test    al, al
0x180272e13  jz      short loc_180272E2C
0x180272e15  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_3c853e741dc03bb96b7f8662095382b4_@@CA@XZ; _lambda_3c853e741dc03bb96b7f8662095382b4_::_lambda_invoker_cdecl_(void)
0x180272e1c  call    ?get@?$static_lazy@VCSpellCheckerTelemetry@@@details@wil@@QEAAPEAVCSpellCheckerTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CSpellCheckerTelemetry>::get(void (*)(void))
0x180272e21  mov     r8d, r14d
0x180272e24  mov     edx, r12d
0x180272e27  call    ?LogSpellerBackCoInitStatus_@CSpellCheckerTelemetry@@QEBAXW4TelemetrySpellCheckerBackFailure@@J@Z; CSpellCheckerTelemetry::LogSpellerBackCoInitStatus_(TelemetrySpellCheckerBackFailure,long)
0x180272e2c  mov     rax, [rsi]
0x180272e2f  mov     rcx, rsi
0x180272e32  mov     rax, [rax+10h]
0x180272e36  mov     rbx, [rsp+20h+arg_18]
0x180272e3b  add     rsp, 20h
0x180272e3f  pop     r15
0x180272e41  pop     r14
0x180272e43  pop     r12
0x180272e45  pop     rsi
0x180272e46  pop     rbp
0x180272e47  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
