# CSearchPaneBroker::UpdateSearchBoxText(HWND__ *,ushort const *)

- ea: `0x180038640`
- end: `0x1800387d6`
- name: `?UpdateSearchBoxText@CSearchPaneBroker@@UEAAJPEAUHWND__@@PEBG@Z`
- size: `406`
- prototype: `__int64 __fastcall(CSearchPaneBroker *__hidden this, HWND, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007b3c`
- `0x18000f2a8`
- `0x1800358b0`
- `0x18003638c`
- `0x180038640`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x1800386d1`
- `SHCORE!IUnknown_QueryService` at `0x1800386d1`
- `USER32!IsWindowVisible` at `0x180038686`
- `USER32!IsWindowVisible` at `0x180038686`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180038748`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180038748`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSearchPaneBroker::UpdateSearchBoxText(IUnknown **this, HWND a2, const unsigned __int16 *a3)
{
  void *v5; // rdi
  int (__fastcall *v6)(void *, _QWORD, GUID *, __int64 *); // rbx
  __int64 v7; // rsi
  void (__fastcall *v8)(__int64, __int64, void *, _BYTE *); // rdi
  void *v9; // rbx
  _BYTE v11[8]; // [rsp+30h] [rbp-19h] BYREF
  void *ppv; // [rsp+38h] [rbp-11h] BYREF
  __int64 v13; // [rsp+40h] [rbp-9h] BYREF
  void *ppvOut; // [rsp+48h] [rbp-1h] BYREF
  HWND hWnd; // [rsp+50h] [rbp+7h] BYREF
  HSTRING_HEADER propvar; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v17; // [rsp+70h] [rbp+27h]

  hWnd = 0;
  if ( (int)GetWindowFromSite(this[7], &hWnd) >= 0 && IsWindowVisible(hWnd) && !IsWindowCloaked(hWnd) && a3 )
  {
    ppvOut = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
    if ( IUnknown_QueryService(
           this[7],
           &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
           &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
           &ppvOut) >= 0 )
    {
      v13 = 0;
      v5 = ppvOut;
      v6 = *(int (__fastcall **)(void *, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppvOut + 40LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v13);
      if ( v6(v5, 0, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v13) >= 0 )
      {
        ppv = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
        LOWORD(propvar.Reserved.Reserved1) = 31;
        *(_QWORD *)&propvar.Reserved.Reserved2[8] = a3;
        if ( PropVariantToWinRTPropertyValue(
               &propvar.Reserved.Reserved1,
               &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
               &ppv) >= 0 )
        {
          v11[0] = 0;
          v7 = v13;
          v8 = *(void (__fastcall **)(__int64, __int64, void *, _BYTE *))(*(_QWORD *)v13 + 80LL);
          v9 = ppv;
          v17 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"QueryText", 0xAu, 9u);
          v8(v7, v17, v9, v11);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v13);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  }
  return 0;
}

```

## disassembly

```asm
0x180038640  push    rbp
0x180038642  push    rbx
0x180038643  push    rsi
0x180038644  push    rdi
0x180038645  lea     rbp, [rsp-3Fh]
0x18003864a  sub     rsp, 88h
0x180038651  mov     rax, cs:__security_cookie
0x180038658  xor     rax, rsp
0x18003865b  mov     [rbp+57h+var_28], rax
0x18003865f  mov     rsi, r8
0x180038662  mov     rbx, rcx
0x180038665  mov     [rbp+57h+hWnd], 0
0x18003866d  lea     rdx, [rbp+57h+hWnd]; phwnd
0x180038671  mov     rcx, [rcx+38h]; punk
0x180038675  call    ?GetWindowFromSite@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; GetWindowFromSite(IUnknown *,HWND__ * *)
0x18003867a  test    eax, eax
0x18003867c  js      loc_1800387BC
0x180038682  mov     rcx, [rbp+57h+hWnd]; hWnd
0x180038686  call    cs:__imp_IsWindowVisible
0x18003868c  test    eax, eax
0x18003868e  jz      loc_1800387BC
0x180038694  mov     rcx, [rbp+57h+hWnd]; HWND
0x180038698  call    ?IsWindowCloaked@@YA_NPEAUHWND__@@@Z; IsWindowCloaked(HWND__ *)
0x18003869d  test    al, al
0x18003869f  jnz     loc_1800387BC
0x1800386a5  test    rsi, rsi
0x1800386a8  jz      loc_1800387BC
0x1800386ae  mov     [rbp+57h+ppvOut], 0
0x1800386b6  lea     rcx, [rbp+57h+ppvOut]
0x1800386ba  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800386bf  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x1800386c3  lea     rdx, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd; guidService
0x1800386ca  mov     r8, rdx; riid
0x1800386cd  mov     rcx, [rbx+38h]; punk
0x1800386d1  call    cs:__imp_IUnknown_QueryService
0x1800386d7  test    eax, eax
0x1800386d9  js      loc_1800387B3
0x1800386df  mov     [rbp+57h+var_60], 0
0x1800386e7  mov     rdi, [rbp+57h+ppvOut]
0x1800386eb  mov     rax, [rdi]
0x1800386ee  mov     rbx, [rax+28h]
0x1800386f2  lea     rcx, [rbp+57h+var_60]
0x1800386f6  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800386fb  lea     r9, [rbp+57h+var_60]
0x1800386ff  lea     r8, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180038706  xor     edx, edx
0x180038708  mov     rcx, rdi
0x18003870b  mov     rax, rbx
0x18003870e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038713  test    eax, eax
0x180038715  js      loc_1800387A9
0x18003871b  mov     [rbp+57h+ppv], 0
0x180038723  lea     rcx, [rbp+57h+ppv]
0x180038727  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003872c  mov     eax, 1Fh
0x180038731  mov     word ptr [rbp+57h+propvar], ax
0x180038735  mov     [rbp+57h+var_40], rsi
0x180038739  lea     r8, [rbp+57h+ppv]; ppv
0x18003873d  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x180038744  lea     rcx, [rbp+57h+propvar]; propvar
0x180038748  call    cs:__imp_PropVariantToWinRTPropertyValue
0x18003874e  test    eax, eax
0x180038750  js      short loc_18003879F
0x180038752  mov     [rbp+57h+var_70], 0
0x180038756  mov     rsi, [rbp+57h+var_60]
0x18003875a  mov     rax, [rsi]
0x18003875d  mov     rdi, [rax+50h]
0x180038761  mov     rbx, [rbp+57h+ppv]
0x180038765  mov     [rbp+57h+var_30], 0
0x18003876d  mov     r9d, 9; unsigned int
0x180038773  lea     r8d, [r9+1]; unsigned int
0x180038777  lea     rdx, aQuerytext; "QueryText"
0x18003877e  lea     rcx, [rbp+57h+propvar]; hstringHeader
0x180038782  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180038787  nop
0x180038788  lea     r9, [rbp+57h+var_70]
0x18003878c  mov     r8, rbx
0x18003878f  mov     rdx, [rbp+57h+var_30]
0x180038793  mov     rcx, rsi
0x180038796  mov     rax, rdi
0x180038799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003879e  nop
0x18003879f  lea     rcx, [rbp+57h+ppv]
0x1800387a3  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800387a8  nop
0x1800387a9  lea     rcx, [rbp+57h+var_60]
0x1800387ad  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800387b2  nop
0x1800387b3  lea     rcx, [rbp+57h+ppvOut]
0x1800387b7  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800387bc  xor     eax, eax
0x1800387be  mov     rcx, [rbp+57h+var_28]
0x1800387c2  xor     rcx, rsp; StackCookie
0x1800387c5  call    __security_check_cookie
0x1800387ca  add     rsp, 88h
0x1800387d1  pop     rdi
0x1800387d2  pop     rsi
0x1800387d3  pop     rbx
0x1800387d4  pop     rbp
0x1800387d5  retn
```
