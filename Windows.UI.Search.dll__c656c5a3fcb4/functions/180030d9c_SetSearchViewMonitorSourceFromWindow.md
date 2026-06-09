# SetSearchViewMonitorSourceFromWindow

- ea: `0x180030d9c`
- end: `0x180030f93`
- name: `SetSearchViewMonitorSourceFromWindow`
- size: `503`
- prototype: `__int64 __fastcall(IUnknown *punk)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800393fc`

## callees

- `0x180007b3c`
- `0x18000f2a8`
- `0x180030d9c`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180030df0`
- `SHCORE!IUnknown_QueryService` at `0x180030eac`
- `SHCORE!IUnknown_QueryService` at `0x180030df0`
- `SHCORE!IUnknown_QueryService` at `0x180030eac`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180030e7a`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180030e7a`

## pseudocode

```c
__int64 __fastcall SetSearchViewMonitorSourceFromWindow(IUnknown *punk, __int64 a2, __int64 a3)
{
  HRESULT v5; // ebx
  void *v6; // rdi
  __int64 (__fastcall *v7)(void *, __int64, GUID *, GUID *, __int64 *); // rbx
  void *v8; // rdi
  __int64 (__fastcall *v9)(void *, _QWORD, GUID *, _QWORD **); // rbx
  _QWORD *v10; // rsi
  void *v11; // rbx
  __int64 v12; // rax
  __int64 (__fastcall *v13)(_QWORD *, __int64, void *, _BYTE *); // rdi
  _BYTE v15[8]; // [rsp+30h] [rbp-19h] BYREF
  _QWORD *v16; // [rsp+38h] [rbp-11h] BYREF
  void *v17; // [rsp+40h] [rbp-9h] BYREF
  void *ppv; // [rsp+48h] [rbp-1h] BYREF
  __int64 v19; // [rsp+50h] [rbp+7h] BYREF
  void *ppvOut; // [rsp+58h] [rbp+Fh] BYREF
  HSTRING_HEADER propvar; // [rsp+60h] [rbp+17h] BYREF
  __int64 v22; // [rsp+78h] [rbp+2Fh]

  ppvOut = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  v5 = IUnknown_QueryService(
         punk,
         (const GUID *const)&SID_IImmersiveMonitorService,
         &GUID_4d4c1e64_e410_4faa_bafa_59ca069bfec2,
         &ppvOut);
  if ( v5 >= 0 )
  {
    v6 = ppvOut;
    v19 = 0;
    v7 = *(__int64 (__fastcall **)(void *, __int64, GUID *, GUID *, __int64 *))(*(_QWORD *)ppvOut + 88LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v19);
    v5 = v7(v6, a3, &GUID_880b26f8_9197_43d0_8045_8702d0d72000, &GUID_880b26f8_9197_43d0_8045_8702d0d72000, &v19);
    if ( v5 >= 0 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      *(_QWORD *)&propvar.Reserved.Reserved2[8] = v19;
      LOWORD(propvar.Reserved.Reserved1) = 13;
      v5 = PropVariantToWinRTPropertyValue(
             &propvar.Reserved.Reserved1,
             &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
             &ppv);
      if ( v5 >= 0 )
      {
        v17 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v17);
        v5 = IUnknown_QueryService(
               punk,
               &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
               &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
               &v17);
        if ( v5 >= 0 )
        {
          v8 = v17;
          v16 = 0;
          v9 = *(__int64 (__fastcall **)(void *, _QWORD, GUID *, _QWORD **))(*(_QWORD *)v17 + 40LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v16);
          v5 = v9(v8, 0, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v16);
          if ( v5 >= 0 )
          {
            v10 = v16;
            v11 = ppv;
            v15[0] = 0;
            v12 = *v16;
            v22 = 0;
            v13 = *(__int64 (__fastcall **)(_QWORD *, __int64, void *, _BYTE *))(v12 + 80);
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"sourceMonitor", 0xEu, 0xDu);
            v5 = v13(v10, v22, v11, v15);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v16);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v17);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v19);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180030d9c  mov     [rsp-8+arg_8], rbx
0x180030da1  mov     [rsp-8+arg_18], rsi
0x180030da6  push    rbp
0x180030da7  push    rdi
0x180030da8  push    r14
0x180030daa  lea     rbp, [rsp-47h]
0x180030daf  sub     rsp, 90h
0x180030db6  mov     rax, cs:__security_cookie
0x180030dbd  xor     rax, rsp
0x180030dc0  mov     [rbp+57h+var_20], rax
0x180030dc4  mov     rsi, rcx
0x180030dc7  mov     [rbp+57h+ppvOut], 0
0x180030dcf  lea     rcx, [rbp+57h+ppvOut]
0x180030dd3  mov     r14, r8
0x180030dd6  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030ddb  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x180030ddf  mov     rcx, rsi; punk
0x180030de2  lea     r8, _GUID_4d4c1e64_e410_4faa_bafa_59ca069bfec2; riid
0x180030de9  lea     rdx, SID_IImmersiveMonitorService; guidService
0x180030df0  call    cs:__imp_IUnknown_QueryService
0x180030df6  mov     ebx, eax
0x180030df8  test    eax, eax
0x180030dfa  js      loc_180030F64
0x180030e00  mov     rdi, [rbp+57h+ppvOut]
0x180030e04  lea     rcx, [rbp+57h+var_50]
0x180030e08  mov     [rbp+57h+var_50], 0
0x180030e10  mov     rax, [rdi]
0x180030e13  mov     rbx, [rax+58h]
0x180030e17  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030e1c  lea     rax, [rbp+57h+var_50]
0x180030e20  mov     rdx, r14
0x180030e23  lea     r8, _GUID_880b26f8_9197_43d0_8045_8702d0d72000
0x180030e2a  mov     [rsp+0A0h+var_80], rax
0x180030e2f  mov     rax, rbx
0x180030e32  mov     r9, r8
0x180030e35  mov     rcx, rdi
0x180030e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e3d  mov     ebx, eax
0x180030e3f  test    eax, eax
0x180030e41  js      loc_180030F5B
0x180030e47  lea     rcx, [rbp+57h+ppv]
0x180030e4b  mov     [rbp+57h+ppv], 0
0x180030e53  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030e58  mov     rax, [rbp+57h+var_50]
0x180030e5c  lea     r8, [rbp+57h+ppv]; ppv
0x180030e60  mov     r14d, 0Dh
0x180030e66  mov     [rbp+57h+var_38], rax
0x180030e6a  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x180030e71  mov     word ptr [rbp+57h+propvar], r14w
0x180030e76  lea     rcx, [rbp+57h+propvar]; propvar
0x180030e7a  call    cs:__imp_PropVariantToWinRTPropertyValue
0x180030e80  mov     ebx, eax
0x180030e82  test    eax, eax
0x180030e84  js      loc_180030F52
0x180030e8a  lea     rcx, [rbp+57h+var_60]
0x180030e8e  mov     [rbp+57h+var_60], 0
0x180030e96  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030e9b  lea     rdx, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd; guidService
0x180030ea2  mov     rcx, rsi; punk
0x180030ea5  mov     r8, rdx; riid
0x180030ea8  lea     r9, [rbp+57h+var_60]; ppvOut
0x180030eac  call    cs:__imp_IUnknown_QueryService
0x180030eb2  mov     ebx, eax
0x180030eb4  test    eax, eax
0x180030eb6  js      loc_180030F49
0x180030ebc  mov     rdi, [rbp+57h+var_60]
0x180030ec0  lea     rcx, [rbp+57h+var_68]
0x180030ec4  mov     [rbp+57h+var_68], 0
0x180030ecc  mov     rax, [rdi]
0x180030ecf  mov     rbx, [rax+28h]
0x180030ed3  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030ed8  lea     r9, [rbp+57h+var_68]
0x180030edc  xor     edx, edx
0x180030ede  lea     r8, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180030ee5  mov     rcx, rdi
0x180030ee8  mov     rax, rbx
0x180030eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ef0  mov     ebx, eax
0x180030ef2  test    eax, eax
0x180030ef4  js      short loc_180030F40
0x180030ef6  mov     rsi, [rbp+57h+var_68]
0x180030efa  lea     r8d, [r14+1]; unsigned int
0x180030efe  mov     rbx, [rbp+57h+ppv]
0x180030f02  lea     rdx, String2; "sourceMonitor"
0x180030f09  mov     [rbp+57h+var_70], 0
0x180030f0d  lea     rcx, [rbp+57h+propvar]; hstringHeader
0x180030f11  mov     r9d, r14d; unsigned int
0x180030f14  mov     rax, [rsi]
0x180030f17  mov     [rbp+57h+var_28], 0
0x180030f1f  mov     rdi, [rax+50h]
0x180030f23  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030f28  mov     rdx, [rbp+57h+var_28]
0x180030f2c  lea     r9, [rbp+57h+var_70]
0x180030f30  mov     r8, rbx
0x180030f33  mov     rcx, rsi
0x180030f36  mov     rax, rdi
0x180030f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f3e  mov     ebx, eax
0x180030f40  lea     rcx, [rbp+57h+var_68]
0x180030f44  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030f49  lea     rcx, [rbp+57h+var_60]
0x180030f4d  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030f52  lea     rcx, [rbp+57h+ppv]
0x180030f56  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030f5b  lea     rcx, [rbp+57h+var_50]
0x180030f5f  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030f64  lea     rcx, [rbp+57h+ppvOut]
0x180030f68  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030f6d  mov     eax, ebx
0x180030f6f  mov     rcx, [rbp+57h+var_20]
0x180030f73  xor     rcx, rsp; StackCookie
0x180030f76  call    __security_check_cookie
0x180030f7b  lea     r11, [rsp+0A0h+var_10]
0x180030f83  mov     rbx, [r11+28h]
0x180030f87  mov     rsi, [r11+38h]
0x180030f8b  mov     rsp, r11
0x180030f8e  pop     r14
0x180030f90  pop     rdi
0x180030f91  pop     rbp
0x180030f92  retn
```
