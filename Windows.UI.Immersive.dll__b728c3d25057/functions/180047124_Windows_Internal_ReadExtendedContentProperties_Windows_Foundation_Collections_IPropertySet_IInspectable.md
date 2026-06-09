# Windows::Internal::ReadExtendedContentProperties(Windows::Foundation::Collections::IPropertySet *,IInspectable * *)

- ea: `0x180047124`
- end: `0x180047623`
- name: `?ReadExtendedContentProperties@Internal@Windows@@YAJPEAUIPropertySet@Collections@Foundation@2@PEAPEAUIInspectable@@@Z`
- size: `1279`
- prototype: `__int64 __fastcall(Windows::Internal *__hidden this, struct Windows::Foundation::Collections::IPropertySet *, struct IInspectable **)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800323ec`

## callees

- `0x180012c50`
- `0x180013244`
- `0x180013660`
- `0x180024434`
- `0x180034db4`
- `0x180036d18`
- `0x1800387c8`
- `0x1800439a8`
- `0x180046efc`
- `0x180047124`
- `0x18004762c`
- `0x180047680`
- `0x180047720`
- `0x180050ba0`
- `0x18005659c`
- `0x180083164`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047478`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047498`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800474a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800474b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047478`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047498`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800474a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800474b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800472de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004733e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004738c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800473da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047428`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047571`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004759d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800475ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800475b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800475c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800475d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800472de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004733e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004738c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800473da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047428`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047571`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004759d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800475ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800475b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800475c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800475d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Internal::ReadExtendedContentProperties(
        Windows::Internal *this,
        struct Windows::Foundation::Collections::IPropertySet *a2,
        struct IInspectable **a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  int (__fastcall *v8)(__int64, PVOID, _QWORD); // rbx
  HSTRING_HEADER *v9; // rax
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, struct IUnknown **); // rdi
  int v12; // eax
  struct IUnknown *v13; // rdi
  const unsigned __int16 *v14; // rbx
  Windows::Internal::PopupWindowXAMLContentImpl *v15; // rax
  __int64 v16; // rax
  HSTRING_HEADER *v17; // rax
  unsigned int v18; // eax
  HSTRING_HEADER *v19; // rax
  unsigned int v20; // eax
  HSTRING_HEADER *v21; // rax
  unsigned int v22; // eax
  HSTRING_HEADER *v23; // rax
  unsigned int v24; // eax
  HSTRING_HEADER *v25; // rax
  unsigned int v26; // eax
  __int64 *v27; // rax
  const unsigned __int16 *v28; // rbx
  struct IUnknown *v29; // rcx
  int v31; // [rsp+20h] [rbp-89h]
  int v32; // [rsp+20h] [rbp-89h]
  HSTRING string; // [rsp+30h] [rbp-79h] BYREF
  HSTRING v34; // [rsp+38h] [rbp-71h] BYREF
  HSTRING v35; // [rsp+40h] [rbp-69h]
  HSTRING v36; // [rsp+48h] [rbp-61h]
  HSTRING v37; // [rsp+50h] [rbp-59h]
  struct IUnknown *v38; // [rsp+58h] [rbp-51h] BYREF
  Windows::Internal *v39; // [rsp+60h] [rbp-49h] BYREF
  PCWSTR StringRawBuffer; // [rsp+68h] [rbp-41h] BYREF
  __int64 v41; // [rsp+70h] [rbp-39h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64); // [rsp+78h] [rbp-31h] BYREF
  __int64 (__fastcall ***v43)(_QWORD, GUID *, struct IUnknown **); // [rsp+80h] [rbp-29h] BYREF
  int v44[2]; // [rsp+88h] [rbp-21h] BYREF
  PCWSTR v45; // [rsp+90h] [rbp-19h] BYREF
  PCWSTR v46; // [rsp+98h] [rbp-11h] BYREF
  PCWSTR v47; // [rsp+A0h] [rbp-9h] BYREF
  HSTRING_HEADER v48; // [rsp+A8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  *(_QWORD *)a2 = 0;
  v39 = this;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v39);
  v43 = 0;
  v42 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))this;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v42);
  v41 = 0;
  v5 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
         &v42,
         (__int64)&v41);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = v41;
    v8 = *(int (__fastcall **)(__int64, PVOID, _QWORD))(*(_QWORD *)v41 + 48LL);
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
           &v48,
           (const WCHAR **)c_MessageDialogContentProp_FullCustomExtendedContent);
    if ( v8(v7, v9[1].Reserved.Reserved1, &v43) < 0 )
    {
      string = 0;
      v37 = 0;
      v36 = 0;
      v35 = 0;
      WindowsDeleteString(0);
      v34 = 0;
      v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &v48,
              (const WCHAR **)&c_MessageDialogContentProp_Primary);
      v18 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v39,
              (HSTRING)v17[1].Reserved.Reserved1);
      wil::details::in1diag3::Log_IfFailedWithExpected(
        retaddr,
        (void *)0x148,
        (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
        (const char *)v18,
        1,
        0x8000000B);
      WindowsDeleteString(0);
      string = 0;
      v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &v48,
              (const WCHAR **)c_MessageDialogContentProp_Secondary);
      v20 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v39,
              (HSTRING)v19[1].Reserved.Reserved1);
      wil::details::in1diag3::Log_IfFailedWithExpected(
        retaddr,
        (void *)0x149,
        (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
        (const char *)v20,
        1,
        0x8000000B);
      WindowsDeleteString(0);
      v37 = 0;
      v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &v48,
              (const WCHAR **)c_MessageDialogContentProp_Glyph);
      v22 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v39,
              (HSTRING)v21[1].Reserved.Reserved1);
      wil::details::in1diag3::Log_IfFailedWithExpected(
        retaddr,
        (void *)0x14A,
        (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
        (const char *)v22,
        1,
        0x8000000B);
      WindowsDeleteString(0);
      v36 = 0;
      v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &v48,
              (const WCHAR **)c_MessageDialogContentProp_GlyphFont);
      v24 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v39,
              (HSTRING)v23[1].Reserved.Reserved1);
      wil::details::in1diag3::Log_IfFailedWithExpected(
        retaddr,
        (void *)0x14B,
        (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
        (const char *)v24,
        1,
        0x8000000B);
      WindowsDeleteString(0);
      v35 = 0;
      v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &v48,
              (const WCHAR **)c_MessageDialogContentProp_Hyperlink);
      v26 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v39,
              (HSTRING)v25[1].Reserved.Reserved1);
      wil::details::in1diag3::Log_IfFailedWithExpected(
        retaddr,
        (void *)0x14C,
        (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
        (const char *)v26,
        1,
        0x8000000B);
      StringRawBuffer = WindowsGetStringRawBuffer(0, 0);
      *(_QWORD *)v44 = WindowsGetStringRawBuffer(0, 0);
      v45 = WindowsGetStringRawBuffer(0, 0);
      v46 = WindowsGetStringRawBuffer(0, 0);
      v47 = WindowsGetStringRawBuffer(0, 0);
      v27 = Microsoft::WRL::Details::Make<Windows::Internal::PopupWindowExtendedStringContentImpl,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *>(
              (__int64 *)&v38,
              &v47,
              &v46,
              &v45,
              (const unsigned __int16 **)v44,
              &StringRawBuffer);
      v28 = (const unsigned __int16 *)*v27;
      StringRawBuffer = (PCWSTR)*v27;
      *v27 = 0;
      v29 = v38;
      if ( v38 )
      {
        v38 = 0;
        ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
      }
      if ( !v28 )
      {
        v6 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x150,
          (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
          (const char *)0x8007000ELL,
          v32);
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&StringRawBuffer);
        WindowsDeleteString(v35);
        v35 = 0;
        WindowsDeleteString(v36);
        v36 = 0;
        WindowsDeleteString(v37);
        v37 = 0;
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v34);
        v34 = 0;
        goto LABEL_17;
      }
      (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v28 + 8LL))(v28);
      *(_QWORD *)a2 = v28;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&StringRawBuffer);
      WindowsDeleteString(v35);
      v35 = 0;
      WindowsDeleteString(v36);
      v36 = 0;
      WindowsDeleteString(v37);
      v37 = 0;
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v34);
    }
    else
    {
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomXamlUIDialog>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_CustomXamlUIDialog>::GetImpl'::`2'::impl,
        1);
      v38 = 0;
      v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v43;
      v11 = **v43;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      v12 = v11(v10, &GUID_00000000_0000_0000_c000_000000000046, &v38);
      v6 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13A,
          (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
          (const char *)(unsigned int)v12,
          v31);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        goto LABEL_17;
      }
      v13 = v38;
      v14 = 0;
      v34 = 0;
      v15 = (Windows::Internal::PopupWindowXAMLContentImpl *)operator new(
                                                               0x28u,
                                                               (const struct std::nothrow_t *)&std::nothrow);
      string = (HSTRING)v15;
      if ( v15 )
      {
        v16 = Windows::Internal::PopupWindowXAMLContentImpl::PopupWindowXAMLContentImpl(v15, v13);
        Microsoft::WRL::ComPtr<Windows::Internal::PopupWindowXAMLContentImpl>::Attach(&v34, v16);
        string = 0;
        v14 = (const unsigned __int16 *)v34;
      }
      Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_3f7781bf84e6b498cf9989aa99f207ed_,-1,IPopupWindow *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_3f7781bf84e6b498cf9989aa99f207ed_,-1,IPopupWindow *>>(&string);
      StringRawBuffer = v14;
      if ( v14 )
        (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v14 + 8LL))(v14);
      *(_QWORD *)a2 = v14;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&StringRawBuffer);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    }
    v6 = 0;
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x132,
    (unsigned int)"shell\\windowsuiimmersive\\popup\\messagedialog.cpp",
    (const char *)(unsigned int)v5,
    v31);
LABEL_17:
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v42);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
  return v6;
}

```

## disassembly

```asm
0x180047124  push    rbp
0x180047126  push    rbx
0x180047127  push    rsi
0x180047128  push    rdi
0x180047129  push    r14
0x18004712b  push    r15
0x18004712d  lea     rbp, [rsp-2Fh]
0x180047132  sub     rsp, 0D8h
0x180047139  mov     rax, cs:__security_cookie
0x180047140  xor     rax, rsp
0x180047143  mov     [rbp+57h+var_38], rax
0x180047147  mov     rsi, rdx
0x18004714a  mov     rbx, rcx
0x18004714d  xor     r15d, r15d
0x180047150  mov     [rdx], r15
0x180047153  mov     [rbp+57h+var_A0], rcx
0x180047157  lea     rcx, [rbp+57h+var_A0]
0x18004715b  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180047160  nop
0x180047161  mov     [rbp+57h+var_80], r15
0x180047165  mov     [rbp+57h+var_88], rbx
0x180047169  lea     rcx, [rbp+57h+var_88]
0x18004716d  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180047172  nop
0x180047173  mov     [rbp+57h+var_90], r15
0x180047177  lea     rdx, [rbp+57h+var_90]
0x18004717b  lea     rcx, [rbp+57h+var_88]
0x18004717f  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180047184  mov     ebx, eax
0x180047186  test    eax, eax
0x180047188  jns     short loc_1800471A7
0x18004718a  mov     rcx, [rbp+5Fh]; this
0x18004718e  mov     r9d, eax; char *
0x180047191  lea     r8, aShellWindowsui; "shell\\windowsuiimmersive\\popup\\messa"...
0x180047198  mov     edx, 132h; void *
0x18004719d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800471a2  jmp     loc_1800475DE
0x1800471a7  mov     rdi, [rbp+57h+var_90]
0x1800471ab  mov     rax, [rdi]
0x1800471ae  mov     rbx, [rax+30h]
0x1800471b2  lea     rdx, c_MessageDialogContentProp_FullCustomExtendedContent
0x1800471b9  lea     rcx, [rbp+57h+var_58]
0x1800471bd  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800471c2  nop
0x1800471c3  lea     r8, [rbp+57h+var_80]
0x1800471c7  mov     rdx, [rax+18h]
0x1800471cb  mov     rcx, rdi
0x1800471ce  mov     rax, rbx
0x1800471d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471d6  nop
0x1800471d7  test    eax, eax
0x1800471d9  js      loc_1800472C8
0x1800471df  mov     edx, 1
0x1800471e4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CustomXamlUIDialog@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CustomXamlUIDialog@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomXamlUIDialog> `wil::Feature<__WilFeatureTraits_Feature_CustomXamlUIDialog>::GetImpl(void)'::`2'::impl
0x1800471eb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CustomXamlUIDialog@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomXamlUIDialog>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800471f0  mov     [rbp+57h+var_A8], r15
0x1800471f4  mov     rbx, [rbp+57h+var_80]
0x1800471f8  mov     rax, [rbx]
0x1800471fb  mov     rdi, [rax]
0x1800471fe  lea     rcx, [rbp+57h+var_A8]
0x180047202  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047207  lea     r8, [rbp+57h+var_A8]
0x18004720b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180047212  mov     rcx, rbx
0x180047215  mov     rax, rdi
0x180047218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004721d  mov     ebx, eax
0x18004721f  test    eax, eax
0x180047221  jns     short loc_180047249
0x180047223  mov     rcx, [rbp+5Fh]; this
0x180047227  mov     r9d, eax; char *
0x18004722a  lea     r8, aShellWindowsui; "shell\\windowsuiimmersive\\popup\\messa"...
0x180047231  mov     edx, 13Ah; void *
0x180047236  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004723b  lea     rcx, [rbp+57h+var_A8]
0x18004723f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047244  jmp     loc_1800475DE
0x180047249  mov     rdi, [rbp+57h+var_A8]
0x18004724d  mov     rbx, r15
0x180047250  mov     [rbp+57h+var_C8], rbx
0x180047254  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004725b  mov     ecx, 28h ; '('; unsigned __int64
0x180047260  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180047265  mov     [rbp+57h+string], rax
0x180047269  test    rax, rax
0x18004726c  jz      short loc_18004728D
0x18004726e  mov     rdx, rdi; struct IUnknown *
0x180047271  mov     rcx, rax; this
0x180047274  call    ??0PopupWindowXAMLContentImpl@Internal@Windows@@QEAA@PEAUIUnknown@@@Z; Windows::Internal::PopupWindowXAMLContentImpl::PopupWindowXAMLContentImpl(IUnknown *)
0x180047279  mov     rdx, rax
0x18004727c  lea     rcx, [rbp+57h+var_C8]
0x180047280  call    ?Attach@?$ComPtr@VPopupWindowXAMLContentImpl@Internal@Windows@@@WRL@Microsoft@@QEAAXPEAVPopupWindowXAMLContentImpl@Internal@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Internal::PopupWindowXAMLContentImpl>::Attach(Windows::Internal::PopupWindowXAMLContentImpl *)
0x180047285  mov     [rbp+57h+string], r15
0x180047289  mov     rbx, [rbp+57h+var_C8]
0x18004728d  lea     rcx, [rbp+57h+string]
0x180047291  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@UIPopupEventHandler@@V_lambda_3f7781bf84e6b498cf9989aa99f207ed_@@$0?0PEAUIPopupWindow@@@?$DelegateArgTraits@P8IPopupEventHandler@@EAAJPEAUIPopupWindow@@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_3f7781bf84e6b498cf9989aa99f207ed_,-1,IPopupWindow *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_3f7781bf84e6b498cf9989aa99f207ed_,-1,IPopupWindow *>>(void)
0x180047296  mov     [rbp+57h+var_98], rbx
0x18004729a  test    rbx, rbx
0x18004729d  jz      short loc_1800472AE
0x18004729f  mov     rax, [rbx]
0x1800472a2  mov     rcx, rbx
0x1800472a5  mov     rax, [rax+8]
0x1800472a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472ae  mov     [rsi], rbx
0x1800472b1  lea     rcx, [rbp+57h+var_98]
0x1800472b5  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800472ba  lea     rcx, [rbp+57h+var_A8]
0x1800472be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800472c3  jmp     loc_1800475DB
0x1800472c8  mov     [rbp+57h+var_C8], r15
0x1800472cc  mov     [rbp+57h+string], r15
0x1800472d0  mov     [rbp+57h+var_B0], r15
0x1800472d4  mov     [rbp+57h+var_B8], r15
0x1800472d8  mov     [rbp+57h+var_C0], r15
0x1800472dc  xor     ecx, ecx; string
0x1800472de  call    cs:__imp_WindowsDeleteString
0x1800472e4  mov     [rbp+57h+var_C8], r15
0x1800472e8  lea     rdx, c_MessageDialogContentProp_Primary
0x1800472ef  lea     rcx, [rbp+57h+var_58]
0x1800472f3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800472f8  nop
0x1800472f9  lea     r9, [rbp+57h+var_C8]
0x1800472fd  mov     rdx, [rax+18h]
0x180047301  lea     rcx, [rbp+57h+var_A0]
0x180047305  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x18004730a  mov     rcx, [rbp+5Fh]; this
0x18004730e  mov     r14d, 8000000Bh
0x180047314  mov     [rsp+100h+var_D8], r14d; unsigned int
0x180047319  mov     ebx, 1
0x18004731e  mov     [rsp+100h+var_E0], ebx; int
0x180047322  mov     r9d, eax; char *
0x180047325  lea     rdi, aShellWindowsui; "shell\\windowsuiimmersive\\popup\\messa"...
0x18004732c  mov     r8, rdi; unsigned int
0x18004732f  mov     edx, 148h; void *
0x180047334  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180047339  nop
0x18004733a  mov     rcx, [rbp+57h+string]; string
0x18004733e  call    cs:__imp_WindowsDeleteString
0x180047344  mov     [rbp+57h+string], r15
0x180047348  lea     rdx, c_MessageDialogContentProp_Secondary
0x18004734f  lea     rcx, [rbp+57h+var_58]
0x180047353  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180047358  nop
0x180047359  lea     r9, [rbp+57h+string]
0x18004735d  mov     rdx, [rax+18h]
0x180047361  lea     rcx, [rbp+57h+var_A0]
0x180047365  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x18004736a  mov     rcx, [rbp+5Fh]; this
0x18004736e  mov     [rsp+100h+var_D8], r14d; unsigned int
0x180047373  mov     [rsp+100h+var_E0], ebx; int
0x180047377  mov     r9d, eax; char *
0x18004737a  mov     r8, rdi; unsigned int
0x18004737d  mov     edx, 149h; void *
0x180047382  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180047387  nop
0x180047388  mov     rcx, [rbp+57h+var_B0]; string
0x18004738c  call    cs:__imp_WindowsDeleteString
0x180047392  mov     [rbp+57h+var_B0], r15
0x180047396  lea     rdx, c_MessageDialogContentProp_Glyph
0x18004739d  lea     rcx, [rbp+57h+var_58]
0x1800473a1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800473a6  nop
0x1800473a7  lea     r9, [rbp+57h+var_B0]
0x1800473ab  mov     rdx, [rax+18h]
0x1800473af  lea     rcx, [rbp+57h+var_A0]
0x1800473b3  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x1800473b8  mov     rcx, [rbp+5Fh]; this
0x1800473bc  mov     [rsp+100h+var_D8], r14d; unsigned int
0x1800473c1  mov     [rsp+100h+var_E0], ebx; int
0x1800473c5  mov     r9d, eax; char *
0x1800473c8  mov     r8, rdi; unsigned int
0x1800473cb  mov     edx, 14Ah; void *
0x1800473d0  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x1800473d5  nop
0x1800473d6  mov     rcx, [rbp+57h+var_B8]; string
0x1800473da  call    cs:__imp_WindowsDeleteString
0x1800473e0  mov     [rbp+57h+var_B8], r15
0x1800473e4  lea     rdx, c_MessageDialogContentProp_GlyphFont
0x1800473eb  lea     rcx, [rbp+57h+var_58]
0x1800473ef  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800473f4  nop
0x1800473f5  lea     r9, [rbp+57h+var_B8]
0x1800473f9  mov     rdx, [rax+18h]
0x1800473fd  lea     rcx, [rbp+57h+var_A0]
0x180047401  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x180047406  mov     rcx, [rbp+5Fh]; this
0x18004740a  mov     [rsp+100h+var_D8], r14d; unsigned int
0x18004740f  mov     [rsp+100h+var_E0], ebx; int
0x180047413  mov     r9d, eax; char *
0x180047416  mov     r8, rdi; unsigned int
0x180047419  mov     edx, 14Bh; void *
0x18004741e  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180047423  nop
0x180047424  mov     rcx, [rbp+57h+var_C0]; string
0x180047428  call    cs:__imp_WindowsDeleteString
0x18004742e  mov     [rbp+57h+var_C0], r15
0x180047432  lea     rdx, c_MessageDialogContentProp_Hyperlink
0x180047439  lea     rcx, [rbp+57h+var_58]
0x18004743d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180047442  nop
0x180047443  lea     r9, [rbp+57h+var_C0]
0x180047447  mov     rdx, [rax+18h]
0x18004744b  lea     rcx, [rbp+57h+var_A0]
0x18004744f  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x180047454  mov     rcx, [rbp+5Fh]; this
0x180047458  mov     [rsp+100h+var_D8], r14d; unsigned int
0x18004745d  mov     [rsp+100h+var_E0], ebx; int
0x180047461  mov     r9d, eax; char *
0x180047464  mov     r8, rdi; unsigned int
0x180047467  mov     edx, 14Ch; void *
0x18004746c  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180047471  nop
0x180047472  xor     edx, edx; length
0x180047474  mov     rcx, [rbp+57h+var_C0]; string
0x180047478  call    cs:__imp_WindowsGetStringRawBuffer
0x18004747e  mov     [rbp+57h+var_98], rax
0x180047482  xor     edx, edx; length
0x180047484  mov     rcx, [rbp+57h+var_B8]; string
0x180047488  call    cs:__imp_WindowsGetStringRawBuffer
0x18004748e  mov     qword ptr [rbp+57h+var_78], rax
0x180047492  xor     edx, edx; length
0x180047494  mov     rcx, [rbp+57h+var_B0]; string
0x180047498  call    cs:__imp_WindowsGetStringRawBuffer
0x18004749e  mov     [rbp+57h+var_70], rax
0x1800474a2  xor     edx, edx; length
0x1800474a4  mov     rcx, [rbp+57h+string]; string
0x1800474a8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800474ae  mov     [rbp+57h+var_68], rax
0x1800474b2  xor     edx, edx; length
0x1800474b4  mov     rcx, [rbp+57h+var_C8]; string
0x1800474b8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800474be  mov     [rbp+57h+var_60], rax
0x1800474c2  lea     rax, [rbp+57h+var_98]
0x1800474c6  mov     qword ptr [rsp+100h+var_D8], rax
0x1800474cb  lea     rax, [rbp+57h+var_78]
0x1800474cf  mov     qword ptr [rsp+100h+var_E0], rax; int
0x1800474d4  lea     r9, [rbp+57h+var_70]
0x1800474d8  lea     r8, [rbp+57h+var_68]
0x1800474dc  lea     rdx, [rbp+57h+var_60]
0x1800474e0  lea     rcx, [rbp+57h+var_A8]
0x1800474e4  call    ??$Make@VPopupWindowExtendedStringContentImpl@Internal@Windows@@PEBGPEBGPEBGPEBGPEBG@Details@WRL@Microsoft@@YA?AV?$ComPtr@VPopupWindowExtendedStringContentImpl@Internal@Windows@@@12@$$QEAPEBG0000@Z; Microsoft::WRL::Details::Make<Windows::Internal::PopupWindowExtendedStringContentImpl,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *>(ushort const * &&,ushort const * &&,ushort const * &&,ushort const * &&,ushort const * &&)
0x1800474e9  mov     rbx, [rax]
0x1800474ec  mov     [rbp+57h+var_98], rbx
0x1800474f0  mov     [rax], r15
0x1800474f3  mov     rcx, [rbp+57h+var_A8]
0x1800474f7  test    rcx, rcx
0x1800474fa  jz      short loc_18004750D
0x1800474fc  mov     [rbp+57h+var_A8], r15
0x180047500  mov     rax, [rcx]
0x180047503  mov     rax, [rax+10h]
0x180047507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004750c  nop
0x18004750d  test    rbx, rbx
0x180047510  jnz     short loc_18004757D
0x180047512  mov     rcx, [rbp+5Fh]; this
0x180047516  mov     ebx, 8007000Eh
0x18004751b  mov     r9d, ebx; char *
0x18004751e  mov     r8, rdi; unsigned int
0x180047521  mov     edx, 150h; void *
0x180047526  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004752b  lea     rcx, [rbp+57h+var_98]
0x18004752f  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180047534  nop
0x180047535  mov     rcx, [rbp+57h+var_C0]; string
0x180047539  call    cs:__imp_WindowsDeleteString
0x18004753f  mov     [rbp+57h+var_C0], r15
0x180047543  mov     rcx, [rbp+57h+var_B8]; string
0x180047547  call    cs:__imp_WindowsDeleteString
0x18004754d  mov     [rbp+57h+var_B8], r15
0x180047551  mov     rcx, [rbp+57h+var_B0]; string
0x180047555  call    cs:__imp_WindowsDeleteString
0x18004755b  mov     [rbp+57h+var_B0], r15
0x18004755f  mov     rcx, [rbp+57h+string]; string
0x180047563  call    cs:__imp_WindowsDeleteString
0x180047569  mov     [rbp+57h+string], r15
0x18004756d  mov     rcx, [rbp+57h+var_C8]; string
0x180047571  call    cs:__imp_WindowsDeleteString
0x180047577  mov     [rbp+57h+var_C8], r15
0x18004757b  jmp     short loc_1800475DE
0x18004757d  mov     rax, [rbx]
0x180047580  mov     rcx, rbx
0x180047583  mov     rax, [rax+8]
0x180047587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004758c  mov     [rsi], rbx
0x18004758f  lea     rcx, [rbp+57h+var_98]
0x180047593  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180047598  nop
0x180047599  mov     rcx, [rbp+57h+var_C0]; string
0x18004759d  call    cs:__imp_WindowsDeleteString
0x1800475a3  mov     [rbp+57h+var_C0], r15
0x1800475a7  mov     rcx, [rbp+57h+var_B8]; string
0x1800475ab  call    cs:__imp_WindowsDeleteString
0x1800475b1  mov     [rbp+57h+var_B8], r15
0x1800475b5  mov     rcx, [rbp+57h+var_B0]; string
0x1800475b9  call    cs:__imp_WindowsDeleteString
0x1800475bf  mov     [rbp+57h+var_B0], r15
0x1800475c3  mov     rcx, [rbp+57h+string]; string
0x1800475c7  call    cs:__imp_WindowsDeleteString
0x1800475cd  mov     [rbp+57h+string], r15
0x1800475d1  mov     rcx, [rbp+57h+var_C8]; string
  ... truncated ...
```
