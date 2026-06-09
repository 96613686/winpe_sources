# CHXSmartScreen::CssTemplateInfo::CssTemplateInfo(void)

- ea: `0x140004518`
- end: `0x140004968`
- name: `??0CssTemplateInfo@CHXSmartScreen@@QE$AAA@XZ`
- size: `1104`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1400058e0`
- `0x1400147a0`

## callees

- `0x1400039b6`
- `0x140004518`
- `0x1400049dc`
- `0x140005bb0`
- `0x140005fa4`
- `0x1400086b0`
- `0x140008900`
- `0x140023f48`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x140004549`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x140004549`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
_QWORD *__fastcall CHXSmartScreen::CssTemplateInfo::CssTemplateInfo(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  __int64 v4; // r14
  int v5; // eax
  int v6; // eax
  HSTRING v7; // rbx
  __int64 v8; // rax
  int v9; // eax
  HSTRING v10; // rbx
  __int64 v11; // rax
  int v12; // eax
  HSTRING v13; // rbx
  __int64 v14; // rax
  int v15; // eax
  HSTRING v16; // rbx
  __int64 v17; // rax
  int v18; // eax
  HSTRING v19; // rbx
  __int64 v20; // rax
  int v21; // eax
  HSTRING v22; // rbx
  __int64 v23; // rax
  int v24; // eax
  HSTRING v25; // rbx
  __int64 v26; // rax
  int v27; // eax
  HSTRING v28; // rbx
  unsigned int v30; // [rsp+20h] [rbp-38h] BYREF
  __int64 v31; // [rsp+28h] [rbp-30h]
  _QWORD *v32; // [rsp+30h] [rbp-28h]
  __int64 v33; // [rsp+38h] [rbp-20h]
  __int64 v34; // [rsp+40h] [rbp-18h] BYREF

  v32 = a1;
  v31 = 0;
  Platform::Object::Object(a1 + 1);
  *a1 = &CHXSmartScreen::CssTemplateInfo::`vftable'{for `CHXSmartScreen::__ICssTemplateInfoPublicNonVirtuals'};
  a1[1] = &CHXSmartScreen::CssTemplateInfo::`vftable'{for `Platform::Object'};
  a1[2] = &CHXSmartScreen::CssTemplateInfo::`vftable'{for `__abi_IUnknown'};
  a1[3] = &CHXSmartScreen::CssTemplateInfo::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'};
  a1[13] = -1;
  if ( __abi_module )
    (**(void (__fastcall ***)(struct __abi_Module *))__abi_module)(__abi_module);
  v2 = Windows::UI::ViewManagement::UISettings::UISettings();
  v3 = v2;
  v34 = v2;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  v33 = v3;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = 0;
  v34 = 0;
  if ( v3 )
  {
    v5 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v3)(
           v3,
           _uuidof__AUIUISettings3_ViewManagement_UI_Windows__,
           &v34);
    if ( v5 < 0 )
      __abi_WinRTraiseException(v5);
    v4 = v34;
  }
  v31 = v4;
  v30 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v4 + 48LL))(v4, 4, &v30);
  if ( v6 < 0 )
    __abi_WinRTraiseException(v6);
  v7 = (HSTRING)ColorToHexString(v30);
  v34 = (__int64)v7;
  __abi_winrt_ptrto_string_assign(a1 + 5, v7);
  WindowsDeleteString_0(v7);
  v8 = __abi_winrt_cast_use_helper(0, v3, _uuidof__AUIUISettings3_ViewManagement_UI_Windows__, v4);
  v30 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v8 + 48LL))(v8, 4, &v30);
  if ( v9 < 0 )
    __abi_WinRTraiseException(v9);
  v10 = (HSTRING)ColorFromBackgroundColor(v30);
  v34 = (__int64)v10;
  __abi_winrt_ptrto_string_assign(a1 + 4, v10);
  WindowsDeleteString_0(v10);
  v11 = __abi_winrt_cast_use_helper(0, v3, _uuidof__AUIUISettings3_ViewManagement_UI_Windows__, v4);
  v30 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v11 + 48LL))(v11, 6, &v30);
  if ( v12 < 0 )
    __abi_WinRTraiseException(v12);
  v13 = (HSTRING)ColorToHexString(v30);
  v34 = (__int64)v13;
  __abi_winrt_ptrto_string_assign(a1 + 6, v13);
  WindowsDeleteString_0(v13);
  v14 = __abi_winrt_cast_use_helper(0, v3, _uuidof__AUIUISettings3_ViewManagement_UI_Windows__, v4);
  v30 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v14 + 48LL))(v14, 7, &v30);
  if ( v15 < 0 )
    __abi_WinRTraiseException(v15);
  v16 = (HSTRING)ColorToHexString(v30);
  v34 = (__int64)v16;
  __abi_winrt_ptrto_string_assign(a1 + 8, v16);
  WindowsDeleteString_0(v16);
  v17 = __abi_winrt_cast_use_helper(0, v3, _uuidof__AUIUISettings3_ViewManagement_UI_Windows__, v4);
  v30 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v17 + 48LL))(v17, 6, &v30);
  if ( v18 < 0 )
    __abi_WinRTraiseException(v18);
  v19 = (HSTRING)ColorFromBackgroundColor(v30);
  v34 = (__int64)v19;
  __abi_winrt_ptrto_string_assign(a1 + 7, v19);
  WindowsDeleteString_0(v19);
  v20 = __abi_winrt_cast_use_helper(0, v3, _uuidof__AUIUISettings3_ViewManagement_UI_Windows__, v4);
  v30 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v20 + 48LL))(v20, 5, &v30);
  if ( v21 < 0 )
    __abi_WinRTraiseException(v21);
  v22 = (HSTRING)ColorToHexString(v30);
  v34 = (__int64)v22;
  __abi_winrt_ptrto_string_assign(a1 + 9, v22);
  WindowsDeleteString_0(v22);
  v23 = __abi_winrt_cast_use_helper(0, v3, _uuidof__AUIUISettings3_ViewManagement_UI_Windows__, v4);
  v30 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v23 + 48LL))(v23, 6, &v30);
  if ( v24 < 0 )
    __abi_WinRTraiseException(v24);
  v25 = (HSTRING)ColorToHexString(v30);
  v34 = (__int64)v25;
  __abi_winrt_ptrto_string_assign(a1 + 10, v25);
  WindowsDeleteString_0(v25);
  v26 = __abi_winrt_cast_use_helper(0, v3, _uuidof__AUIUISettings3_ViewManagement_UI_Windows__, v4);
  v30 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v26 + 48LL))(v26, 5, &v30);
  if ( v27 < 0 )
    __abi_WinRTraiseException(v27);
  v28 = (HSTRING)ColorFromBackgroundColor(v30);
  v34 = (__int64)v28;
  __abi_winrt_ptrto_string_assign(a1 + 11, v28);
  WindowsDeleteString_0(v28);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v31 = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  return a1;
}

```

## disassembly

```asm
0x140004518  push    rbp
0x14000451a  push    rbx
0x14000451b  push    rsi
0x14000451c  push    rdi
0x14000451d  push    r12
0x14000451f  push    r14
0x140004521  mov     rbp, rsp
0x140004524  sub     rsp, 58h
0x140004528  mov     rax, cs:__security_cookie
0x14000452f  xor     rax, rsp
0x140004532  mov     [rbp+var_10], rax
0x140004536  mov     rsi, rcx
0x140004539  mov     [rbp+var_28], rcx
0x14000453d  mov     [rbp+var_30], 0
0x140004545  add     rcx, 8
0x140004549  call    cs:__imp_??0Object@Platform@@QE$AAA@XZ; Platform::Object::Object(void)
0x14000454f  lea     rax, ??_7CssTemplateInfo@CHXSmartScreen@@6B__ICssTemplateInfoPublicNonVirtuals@1@@; const CHXSmartScreen::CssTemplateInfo::`vftable'{for `CHXSmartScreen::__ICssTemplateInfoPublicNonVirtuals'}
0x140004556  mov     [rsi], rax
0x140004559  lea     rax, ??_7CssTemplateInfo@CHXSmartScreen@@6BObject@Platform@@@; const CHXSmartScreen::CssTemplateInfo::`vftable'{for `Platform::Object'}
0x140004560  mov     [rsi+8], rax
0x140004564  lea     rax, ??_7CssTemplateInfo@CHXSmartScreen@@6B__abi_IUnknown@@@; const CHXSmartScreen::CssTemplateInfo::`vftable'{for `__abi_IUnknown'}
0x14000456b  mov     [rsi+10h], rax
0x14000456f  lea     rax, ??_7CssTemplateInfo@CHXSmartScreen@@6BObject@Platform@@IWeakReferenceSource@Details@3@@; const CHXSmartScreen::CssTemplateInfo::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'}
0x140004576  mov     [rsi+18h], rax
0x14000457a  mov     qword ptr [rsi+68h], 0FFFFFFFFFFFFFFFFh
0x140004582  mov     rcx, cs:?__abi_module@@3PEAU__abi_Module@@EA; __abi_Module * __abi_module
0x140004589  test    rcx, rcx
0x14000458c  jz      short loc_14000459A
0x14000458e  mov     rax, [rcx]
0x140004591  mov     rax, [rax]
0x140004594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004599  nop
0x14000459a  mov     [rbp+var_18], 0
0x1400045a2  call    ??0UISettings@ViewManagement@UI@Windows@@QE$AAA@XZ; Windows::UI::ViewManagement::UISettings::UISettings(void)
0x1400045a7  mov     rdi, rax
0x1400045aa  mov     [rbp+var_18], rax
0x1400045ae  test    rax, rax
0x1400045b1  jz      short loc_1400045C2
0x1400045b3  mov     rax, [rax]
0x1400045b6  mov     rcx, rdi
0x1400045b9  mov     rax, [rax+8]
0x1400045bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045c2  mov     [rbp+var_20], rdi
0x1400045c6  test    rdi, rdi
0x1400045c9  jz      short loc_1400045DB
0x1400045cb  mov     rax, [rdi]
0x1400045ce  mov     rcx, rdi
0x1400045d1  mov     rax, [rax+10h]
0x1400045d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045da  nop
0x1400045db  xor     r14d, r14d
0x1400045de  mov     [rbp+var_18], r14
0x1400045e2  lea     r12, __uuidof_?AUIUISettings3@ViewManagement@UI@Windows@@
0x1400045e9  test    rdi, rdi
0x1400045ec  jz      short loc_14000460F
0x1400045ee  mov     rax, [rdi]
0x1400045f1  lea     r8, [rbp+var_18]
0x1400045f5  mov     rdx, r12
0x1400045f8  mov     rcx, rdi
0x1400045fb  mov     rax, [rax]
0x1400045fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004603  test    eax, eax
0x140004605  js      loc_140004928
0x14000460b  mov     r14, [rbp+var_18]
0x14000460f  mov     [rbp+var_30], r14
0x140004613  mov     [rbp+var_38], 0
0x14000461a  mov     rax, [r14]
0x14000461d  lea     r8, [rbp+var_38]
0x140004621  mov     edx, 4
0x140004626  mov     rcx, r14
0x140004629  mov     rax, [rax+30h]
0x14000462d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004632  test    eax, eax
0x140004634  js      loc_140004930
0x14000463a  mov     ecx, [rbp+var_38]
0x14000463d  call    ?ColorToHexString@@YAPE$AAVString@Platform@@VColor@UI@Windows@@@Z; ColorToHexString(Windows::UI::Color)
0x140004642  mov     rbx, rax
0x140004645  mov     [rbp+var_18], rax
0x140004649  lea     rcx, [rsi+28h]
0x14000464d  mov     rdx, rax
0x140004650  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x140004655  nop
0x140004656  mov     rcx, rbx; string
0x140004659  call    WindowsDeleteString_0
0x14000465e  mov     r9, r14
0x140004661  mov     r8, r12
0x140004664  mov     rdx, rdi
0x140004667  xor     ecx, ecx
0x140004669  call    ?__abi_winrt_cast_use_helper@@YAPE$AAVObject@Platform@@_NPEAXAEBU_GUID@@PEAU__abi_IUnknown@@@Z; __abi_winrt_cast_use_helper(bool,void *,_GUID const &,__abi_IUnknown *)
0x14000466e  mov     rcx, rax
0x140004671  mov     [rbp+var_38], 0
0x140004678  mov     rax, [rax]
0x14000467b  lea     r8, [rbp+var_38]
0x14000467f  mov     edx, 4
0x140004684  mov     rax, [rax+30h]
0x140004688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000468d  test    eax, eax
0x14000468f  js      loc_140004938
0x140004695  mov     ecx, [rbp+var_38]
0x140004698  call    ?ColorFromBackgroundColor@@YAPE$AAVString@Platform@@VColor@UI@Windows@@@Z; ColorFromBackgroundColor(Windows::UI::Color)
0x14000469d  mov     rbx, rax
0x1400046a0  mov     [rbp+var_18], rax
0x1400046a4  lea     rcx, [rsi+20h]
0x1400046a8  mov     rdx, rax
0x1400046ab  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x1400046b0  nop
0x1400046b1  mov     rcx, rbx; string
0x1400046b4  call    WindowsDeleteString_0
0x1400046b9  mov     r9, r14
0x1400046bc  mov     r8, r12
0x1400046bf  mov     rdx, rdi
0x1400046c2  xor     ecx, ecx
0x1400046c4  call    ?__abi_winrt_cast_use_helper@@YAPE$AAVObject@Platform@@_NPEAXAEBU_GUID@@PEAU__abi_IUnknown@@@Z; __abi_winrt_cast_use_helper(bool,void *,_GUID const &,__abi_IUnknown *)
0x1400046c9  mov     rcx, rax
0x1400046cc  mov     [rbp+var_38], 0
0x1400046d3  mov     rax, [rax]
0x1400046d6  lea     r8, [rbp+var_38]
0x1400046da  mov     edx, 6
0x1400046df  mov     rax, [rax+30h]
0x1400046e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046e8  test    eax, eax
0x1400046ea  js      loc_140004940
0x1400046f0  mov     ecx, [rbp+var_38]
0x1400046f3  call    ?ColorToHexString@@YAPE$AAVString@Platform@@VColor@UI@Windows@@@Z; ColorToHexString(Windows::UI::Color)
0x1400046f8  mov     rbx, rax
0x1400046fb  mov     [rbp+var_18], rax
0x1400046ff  lea     rcx, [rsi+30h]
0x140004703  mov     rdx, rax
0x140004706  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x14000470b  nop
0x14000470c  mov     rcx, rbx; string
0x14000470f  call    WindowsDeleteString_0
0x140004714  mov     r9, r14
0x140004717  mov     r8, r12
0x14000471a  mov     rdx, rdi
0x14000471d  xor     ecx, ecx
0x14000471f  call    ?__abi_winrt_cast_use_helper@@YAPE$AAVObject@Platform@@_NPEAXAEBU_GUID@@PEAU__abi_IUnknown@@@Z; __abi_winrt_cast_use_helper(bool,void *,_GUID const &,__abi_IUnknown *)
0x140004724  mov     rcx, rax
0x140004727  mov     [rbp+var_38], 0
0x14000472e  mov     rax, [rax]
0x140004731  lea     r8, [rbp+var_38]
0x140004735  mov     edx, 7
0x14000473a  mov     rax, [rax+30h]
0x14000473e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004743  test    eax, eax
0x140004745  js      loc_140004948
0x14000474b  mov     ecx, [rbp+var_38]
0x14000474e  call    ?ColorToHexString@@YAPE$AAVString@Platform@@VColor@UI@Windows@@@Z; ColorToHexString(Windows::UI::Color)
0x140004753  mov     rbx, rax
0x140004756  mov     [rbp+var_18], rax
0x14000475a  lea     rcx, [rsi+40h]
0x14000475e  mov     rdx, rax
0x140004761  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x140004766  nop
0x140004767  mov     rcx, rbx; string
0x14000476a  call    WindowsDeleteString_0
0x14000476f  mov     r9, r14
0x140004772  mov     r8, r12
0x140004775  mov     rdx, rdi
0x140004778  xor     ecx, ecx
0x14000477a  call    ?__abi_winrt_cast_use_helper@@YAPE$AAVObject@Platform@@_NPEAXAEBU_GUID@@PEAU__abi_IUnknown@@@Z; __abi_winrt_cast_use_helper(bool,void *,_GUID const &,__abi_IUnknown *)
0x14000477f  mov     rcx, rax
0x140004782  mov     [rbp+var_38], 0
0x140004789  mov     rax, [rax]
0x14000478c  lea     r8, [rbp+var_38]
0x140004790  mov     edx, 6
0x140004795  mov     rax, [rax+30h]
0x140004799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000479e  test    eax, eax
0x1400047a0  js      loc_140004950
0x1400047a6  mov     ecx, [rbp+var_38]
0x1400047a9  call    ?ColorFromBackgroundColor@@YAPE$AAVString@Platform@@VColor@UI@Windows@@@Z; ColorFromBackgroundColor(Windows::UI::Color)
0x1400047ae  mov     rbx, rax
0x1400047b1  mov     [rbp+var_18], rax
0x1400047b5  lea     rcx, [rsi+38h]
0x1400047b9  mov     rdx, rax
0x1400047bc  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x1400047c1  nop
0x1400047c2  mov     rcx, rbx; string
0x1400047c5  call    WindowsDeleteString_0
0x1400047ca  mov     r9, r14
0x1400047cd  mov     r8, r12
0x1400047d0  mov     rdx, rdi
0x1400047d3  xor     ecx, ecx
0x1400047d5  call    ?__abi_winrt_cast_use_helper@@YAPE$AAVObject@Platform@@_NPEAXAEBU_GUID@@PEAU__abi_IUnknown@@@Z; __abi_winrt_cast_use_helper(bool,void *,_GUID const &,__abi_IUnknown *)
0x1400047da  mov     rcx, rax
0x1400047dd  mov     [rbp+var_38], 0
0x1400047e4  mov     rax, [rax]
0x1400047e7  lea     r8, [rbp+var_38]
0x1400047eb  mov     edx, 5
0x1400047f0  mov     rax, [rax+30h]
0x1400047f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047f9  test    eax, eax
0x1400047fb  js      loc_140004958
0x140004801  mov     ecx, [rbp+var_38]
0x140004804  call    ?ColorToHexString@@YAPE$AAVString@Platform@@VColor@UI@Windows@@@Z; ColorToHexString(Windows::UI::Color)
0x140004809  mov     rbx, rax
0x14000480c  mov     [rbp+var_18], rax
0x140004810  lea     rcx, [rsi+48h]
0x140004814  mov     rdx, rax
0x140004817  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x14000481c  nop
0x14000481d  mov     rcx, rbx; string
0x140004820  call    WindowsDeleteString_0
0x140004825  mov     r9, r14
0x140004828  mov     r8, r12
0x14000482b  mov     rdx, rdi
0x14000482e  xor     ecx, ecx
0x140004830  call    ?__abi_winrt_cast_use_helper@@YAPE$AAVObject@Platform@@_NPEAXAEBU_GUID@@PEAU__abi_IUnknown@@@Z; __abi_winrt_cast_use_helper(bool,void *,_GUID const &,__abi_IUnknown *)
0x140004835  mov     rcx, rax
0x140004838  mov     [rbp+var_38], 0
0x14000483f  mov     rax, [rax]
0x140004842  lea     r8, [rbp+var_38]
0x140004846  mov     edx, 6
0x14000484b  mov     rax, [rax+30h]
0x14000484f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004854  test    eax, eax
0x140004856  js      loc_140004960
0x14000485c  mov     ecx, [rbp+var_38]
0x14000485f  call    ?ColorToHexString@@YAPE$AAVString@Platform@@VColor@UI@Windows@@@Z; ColorToHexString(Windows::UI::Color)
0x140004864  mov     rbx, rax
0x140004867  mov     [rbp+var_18], rax
0x14000486b  lea     rcx, [rsi+50h]
0x14000486f  mov     rdx, rax
0x140004872  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x140004877  nop
0x140004878  mov     rcx, rbx; string
0x14000487b  call    WindowsDeleteString_0
0x140004880  mov     r9, r14
0x140004883  mov     r8, r12
0x140004886  mov     rdx, rdi
0x140004889  xor     ecx, ecx
0x14000488b  call    ?__abi_winrt_cast_use_helper@@YAPE$AAVObject@Platform@@_NPEAXAEBU_GUID@@PEAU__abi_IUnknown@@@Z; __abi_winrt_cast_use_helper(bool,void *,_GUID const &,__abi_IUnknown *)
0x140004890  mov     rcx, rax
0x140004893  mov     [rbp+var_38], 0
0x14000489a  mov     rax, [rax]
0x14000489d  lea     r8, [rbp+var_38]
0x1400048a1  mov     edx, 5
0x1400048a6  mov     rax, [rax+30h]
0x1400048aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048af  test    eax, eax
0x1400048b1  js      short loc_140004920
0x1400048b3  mov     ecx, [rbp+var_38]
0x1400048b6  call    ?ColorFromBackgroundColor@@YAPE$AAVString@Platform@@VColor@UI@Windows@@@Z; ColorFromBackgroundColor(Windows::UI::Color)
0x1400048bb  mov     rbx, rax
0x1400048be  mov     [rbp+var_18], rax
0x1400048c2  lea     rcx, [rsi+58h]
0x1400048c6  mov     rdx, rax
0x1400048c9  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x1400048ce  nop
0x1400048cf  mov     rcx, rbx; string
0x1400048d2  call    WindowsDeleteString_0
0x1400048d7  nop
0x1400048d8  mov     rax, [r14]
0x1400048db  mov     rcx, r14
0x1400048de  mov     rax, [rax+10h]
0x1400048e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048e7  mov     [rbp+var_30], 0
0x1400048ef  test    rdi, rdi
0x1400048f2  jz      short loc_140004904
0x1400048f4  mov     rcx, [rdi]
0x1400048f7  mov     rax, [rcx+10h]
0x1400048fb  mov     rcx, rdi
0x1400048fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004903  nop
0x140004904  mov     rax, rsi
0x140004907  mov     rcx, [rbp+var_10]
0x14000490b  xor     rcx, rsp; StackCookie
0x14000490e  call    __security_check_cookie
0x140004913  add     rsp, 58h
0x140004917  pop     r14
0x140004919  pop     r12
0x14000491b  pop     rdi
0x14000491c  pop     rsi
0x14000491d  pop     rbx
0x14000491e  pop     rbp
0x14000491f  retn
0x140004920  mov     ecx, eax; int
0x140004922  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x140004928  mov     ecx, eax; int
0x14000492a  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x140004930  mov     ecx, eax; int
0x140004932  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x140004938  mov     ecx, eax; int
0x14000493a  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x140004940  mov     ecx, eax; int
0x140004942  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x140004948  mov     ecx, eax; int
0x14000494a  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x140004950  mov     ecx, eax; int
0x140004952  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x140004958  mov     ecx, eax; int
0x14000495a  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x140004960  mov     ecx, eax; int
0x140004962  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
