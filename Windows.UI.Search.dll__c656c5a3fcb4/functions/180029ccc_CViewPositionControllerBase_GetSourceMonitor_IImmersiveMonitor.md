# CViewPositionControllerBase::_GetSourceMonitor(IImmersiveMonitor * *)

- ea: `0x180029ccc`
- end: `0x180029eab`
- name: `?_GetSourceMonitor@CViewPositionControllerBase@@IEAAJPEAPEAUIImmersiveMonitor@@@Z`
- size: `479`
- prototype: `int(CViewPositionControllerBase *__hidden this, struct IImmersiveMonitor **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180029620`
- `0x1800296f0`

## callees

- `0x180007b3c`
- `0x18000f2a8`
- `0x1800296ac`
- `0x180029ccc`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029dfc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029dfc`
- `SHCORE!IUnknown_QueryService` at `0x180029d22`
- `SHCORE!IUnknown_QueryService` at `0x180029e2b`
- `SHCORE!IUnknown_QueryService` at `0x180029d22`
- `SHCORE!IUnknown_QueryService` at `0x180029e2b`
- `PROPSYS!__imp_WinRTPropertyValueToPropVariant` at `0x180029dd7`
- `PROPSYS!__imp_WinRTPropertyValueToPropVariant` at `0x180029dd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CViewPositionControllerBase::_GetSourceMonitor(IUnknown **this, struct IImmersiveMonitor **a2)
{
  HRESULT ObjectW; // ebx
  void *v5; // rdi
  __int64 (__fastcall *v6)(void *, _QWORD, GUID *, __int64 *); // rbx
  __int64 v7; // rdi
  int (__fastcall *v8)(__int64, __int64, IUnknown **); // rbx
  void *v10; // [rsp+30h] [rbp-50h] BYREF
  IUnknown *punkPropertyValue; // [rsp+38h] [rbp-48h] BYREF
  __int64 v12; // [rsp+40h] [rbp-40h] BYREF
  void *ppvOut; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER ppropvar; // [rsp+50h] [rbp-30h] BYREF
  __int64 v15; // [rsp+68h] [rbp-18h]

  *a2 = 0;
  ppvOut = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  ObjectW = IUnknown_QueryService(
              this[2],
              &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
              &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
              &ppvOut);
  if ( ObjectW >= 0 )
  {
    v12 = 0;
    v5 = ppvOut;
    v6 = *(__int64 (__fastcall **)(void *, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppvOut + 40LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v12);
    ObjectW = v6(v5, *((unsigned int *)this + 26), &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v12);
    if ( ObjectW >= 0 )
    {
      punkPropertyValue = 0;
      v7 = v12;
      v8 = *(int (__fastcall **)(__int64, __int64, IUnknown **))(*(_QWORD *)v12 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&punkPropertyValue);
      v15 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&ppropvar, L"sourceMonitor", 0xEu, 0xDu);
      if ( v8(v7, v15, &punkPropertyValue) < 0 )
      {
        v10 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v10);
        ObjectW = IUnknown_QueryService(
                    this[2],
                    (const GUID *const)&SID_IImmersiveMonitorService,
                    &GUID_4d4c1e64_e410_4faa_bafa_59ca069bfec2,
                    &v10);
        if ( ObjectW >= 0 )
          ObjectW = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, GUID *, struct IImmersiveMonitor **))(*(_QWORD *)v10 + 72LL))(
                      v10,
                      0,
                      &GUID_880b26f8_9197_43d0_8045_8702d0d72000,
                      &GUID_880b26f8_9197_43d0_8045_8702d0d72000,
                      a2);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v10);
      }
      else
      {
        LOWORD(ppropvar.Reserved.Reserved1) = 0;
        ObjectW = WinRTPropertyValueToPropVariant(punkPropertyValue, &ppropvar.Reserved.Reserved1);
        if ( ObjectW >= 0 )
          ObjectW = CPropVariant::GetObjectW(
                      (CPropVariant *)&ppropvar,
                      &GUID_880b26f8_9197_43d0_8045_8702d0d72000,
                      (void **)a2);
        PropVariantClear(&ppropvar.Reserved.Reserved1);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&punkPropertyValue);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v12);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  return (unsigned int)ObjectW;
}

```

## disassembly

```asm
0x180029ccc  mov     [rsp-18h+arg_10], rbx
0x180029cd1  mov     [rsp-18h+arg_18], rsi
0x180029cd6  push    rbp
0x180029cd7  push    rdi
0x180029cd8  push    r14
0x180029cda  mov     rbp, rsp
0x180029cdd  sub     rsp, 80h
0x180029ce4  mov     rax, cs:__security_cookie
0x180029ceb  xor     rax, rsp
0x180029cee  mov     [rbp+var_10], rax
0x180029cf2  mov     rsi, rdx
0x180029cf5  mov     r14, rcx
0x180029cf8  mov     qword ptr [rdx], 0
0x180029cff  mov     [rbp+ppvOut], 0
0x180029d07  lea     rcx, [rbp+ppvOut]
0x180029d0b  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180029d10  lea     r9, [rbp+ppvOut]; ppvOut
0x180029d14  lea     rdx, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd; guidService
0x180029d1b  mov     r8, rdx; riid
0x180029d1e  mov     rcx, [r14+10h]; punk
0x180029d22  call    cs:__imp_IUnknown_QueryService
0x180029d28  mov     ebx, eax
0x180029d2a  test    eax, eax
0x180029d2c  js      loc_180029E7C
0x180029d32  mov     [rbp+var_40], 0
0x180029d3a  mov     rdi, [rbp+ppvOut]
0x180029d3e  mov     rax, [rdi]
0x180029d41  mov     rbx, [rax+28h]
0x180029d45  lea     rcx, [rbp+var_40]
0x180029d49  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180029d4e  lea     r9, [rbp+var_40]
0x180029d52  lea     r8, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180029d59  mov     edx, [r14+68h]
0x180029d5d  mov     rcx, rdi
0x180029d60  mov     rax, rbx
0x180029d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d68  mov     ebx, eax
0x180029d6a  test    eax, eax
0x180029d6c  js      loc_180029E72
0x180029d72  mov     [rbp+punkPropertyValue], 0
0x180029d7a  mov     rdi, [rbp+var_40]
0x180029d7e  mov     rax, [rdi]
0x180029d81  mov     rbx, [rax+30h]
0x180029d85  lea     rcx, [rbp+punkPropertyValue]
0x180029d89  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180029d8e  mov     [rbp+var_18], 0
0x180029d96  mov     r9d, 0Dh; unsigned int
0x180029d9c  lea     r8d, [r9+1]; unsigned int
0x180029da0  lea     rdx, String2; "sourceMonitor"
0x180029da7  lea     rcx, [rbp+ppropvar]; hstringHeader
0x180029dab  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180029db0  nop
0x180029db1  lea     r8, [rbp+punkPropertyValue]
0x180029db5  mov     rdx, [rbp+var_18]
0x180029db9  mov     rcx, rdi
0x180029dbc  mov     rax, rbx
0x180029dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dc4  nop
0x180029dc5  test    eax, eax
0x180029dc7  js      short loc_180029E04
0x180029dc9  xor     eax, eax
0x180029dcb  mov     word ptr [rbp+ppropvar], ax
0x180029dcf  lea     rdx, [rbp+ppropvar]; ppropvar
0x180029dd3  mov     rcx, [rbp+punkPropertyValue]; punkPropertyValue
0x180029dd7  call    cs:__imp_WinRTPropertyValueToPropVariant
0x180029ddd  mov     ebx, eax
0x180029ddf  test    eax, eax
0x180029de1  js      short loc_180029DF8
0x180029de3  mov     r8, rsi; void **
0x180029de6  lea     rdx, _GUID_880b26f8_9197_43d0_8045_8702d0d72000; struct _GUID *
0x180029ded  lea     rcx, [rbp+ppropvar]; this
0x180029df1  call    ?GetObjectW@CPropVariant@@QEBAJAEBU_GUID@@PEAPEAX@Z; CPropVariant::GetObjectW(_GUID const &,void * *)
0x180029df6  mov     ebx, eax
0x180029df8  lea     rcx, [rbp+ppropvar]; pvar
0x180029dfc  call    cs:__imp_PropVariantClear
0x180029e02  jmp     short loc_180029E68
0x180029e04  mov     [rbp+var_50], 0
0x180029e0c  lea     rcx, [rbp+var_50]
0x180029e10  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180029e15  lea     r9, [rbp+var_50]; ppvOut
0x180029e19  lea     r8, _GUID_4d4c1e64_e410_4faa_bafa_59ca069bfec2; riid
0x180029e20  lea     rdx, SID_IImmersiveMonitorService; guidService
0x180029e27  mov     rcx, [r14+10h]; punk
0x180029e2b  call    cs:__imp_IUnknown_QueryService
0x180029e31  mov     ebx, eax
0x180029e33  test    eax, eax
0x180029e35  js      short loc_180029E5E
0x180029e37  mov     rcx, [rbp+var_50]
0x180029e3b  mov     rax, [rcx]
0x180029e3e  mov     [rsp+80h+var_60], rsi
0x180029e43  lea     r9, _GUID_880b26f8_9197_43d0_8045_8702d0d72000
0x180029e4a  lea     r8, _GUID_880b26f8_9197_43d0_8045_8702d0d72000
0x180029e51  xor     edx, edx
0x180029e53  mov     rax, [rax+48h]
0x180029e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e5c  mov     ebx, eax
0x180029e5e  lea     rcx, [rbp+var_50]
0x180029e62  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180029e67  nop
0x180029e68  lea     rcx, [rbp+punkPropertyValue]
0x180029e6c  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180029e71  nop
0x180029e72  lea     rcx, [rbp+var_40]
0x180029e76  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180029e7b  nop
0x180029e7c  lea     rcx, [rbp+ppvOut]
0x180029e80  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180029e85  mov     eax, ebx
0x180029e87  mov     rcx, [rbp+var_10]
0x180029e8b  xor     rcx, rsp; StackCookie
0x180029e8e  call    __security_check_cookie
0x180029e93  lea     r11, [rsp+80h+var_s0]
0x180029e9b  mov     rbx, [r11+30h]
0x180029e9f  mov     rsi, [r11+38h]
0x180029ea3  mov     rsp, r11
0x180029ea6  pop     r14
0x180029ea8  pop     rdi
0x180029ea9  pop     rbp
0x180029eaa  retn
```
