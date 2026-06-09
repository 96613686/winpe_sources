# SystemSettings::PenSettings::DevicesPenSetDesktopAppBase::Invoke(HWND__ *)

- ea: `0x18002b6d0`
- end: `0x18002b9da`
- name: `?Invoke@DevicesPenSetDesktopAppBase@PenSettings@SystemSettings@@UEAAJPEAUHWND__@@@Z`
- size: `778`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::DevicesPenSetDesktopAppBase *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180008128`
- `0x18000a2bc`
- `0x1800146a8`
- `0x180016138`
- `0x18001b284`
- `0x18001b2d0`
- `0x18001b510`
- `0x18001ce78`
- `0x18001ef74`
- `0x1800203f8`
- `0x18002b6d0`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b9ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b9ad`

## string_xrefs

- `0x18002b747`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002b7a4`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002b7e9`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002b858`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002b8fa`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002b958`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SystemSettings::PenSettings::DevicesPenSetDesktopAppBase::Invoke(
        SystemSettings::PenSettings::DevicesPenSetDesktopAppBase *this,
        const unsigned __int16 *a2)
{
  _QWORD *v3; // rax
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  HSTRING *v7; // r8
  int ResourceStringById; // eax
  HSTRING v9; // rbx
  int v10; // eax
  int v11; // edi
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, __int64 *); // rdi
  __int64 v14; // rdx
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rdi
  int v17; // eax
  __int64 v18; // rax
  __int64 v20; // [rsp+20h] [rbp-69h] BYREF
  __int64 v21; // [rsp+28h] [rbp-61h] BYREF
  __int64 v22; // [rsp+30h] [rbp-59h] BYREF
  HSTRING string; // [rsp+38h] [rbp-51h] BYREF
  SystemSettings::PenSettings::DevicesPenSetDesktopAppBase *v24; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v25[8]; // [rsp+48h] [rbp-41h] BYREF
  HSTRING v26; // [rsp+50h] [rbp-39h] BYREF
  HSTRING v27; // [rsp+70h] [rbp-19h] BYREF
  HSTRING v28; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v21 = 0;
  v3 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v28, (const unsigned __int16 (*)[39])a2);
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Pickers::IFileOpenPicker>>(
         *v3,
         &v21);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 2388;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      (const char *)(unsigned int)v4,
      v20);
    goto LABEL_31;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 88LL))(v21, 1);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 2389;
    goto LABEL_5;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 56LL))(v21, 1);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 2390;
    goto LABEL_5;
  }
  WindowsDeleteString(0);
  string = 0;
  ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                         (SystemSettings::DataModel *)L"SystemSettings_Devices_Pen_DesktopAppPicker_ChooseApplication",
                         &string,
                         v7);
  v5 = ResourceStringById;
  if ( ResourceStringById < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x959,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      (const char *)(unsigned int)ResourceStringById,
      v20);
    WindowsDeleteString(string);
    goto LABEL_31;
  }
  v9 = string;
  v10 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v21 + 104LL))(v21, string);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95A,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      (const char *)(unsigned int)v10,
      v20);
LABEL_12:
    WindowsDeleteString(v9);
    v5 = v11;
    goto LABEL_31;
  }
  v20 = 0;
  Windows::Internal::StringReference::StringReference(&v26, L".exe");
  v12 = v21;
  v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 112LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v11 = v13(v12, &v20);
  if ( v11 < 0 )
  {
    v14 = 2397;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      (const char *)(unsigned int)v11,
      v20);
LABEL_16:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    goto LABEL_12;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v20 + 104LL))(v20, v26);
  if ( v11 < 0 )
  {
    v14 = 2398;
    goto LABEL_15;
  }
  Windows::Internal::StringReference::StringReference(&v27, L".lnk");
  v11 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v20 + 104LL))(v20, v27);
  if ( v11 < 0 )
  {
    v14 = 2400;
    goto LABEL_15;
  }
  v22 = 0;
  v15 = v21;
  v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 120LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  v17 = v16(v15, &v22);
  v11 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x963,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      (const char *)(unsigned int)v17,
      v20);
LABEL_23:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
    goto LABEL_16;
  }
  v24 = this;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v24);
  v18 = lambda_f11977d2b9d3b11ee12c6d6ff112d1fb_::_lambda_f11977d2b9d3b11ee12c6d6ff112d1fb_(v25, &v24);
  v11 = StartOperationAndThenAgileCallback_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile____Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile_____lambda_f11977d2b9d3b11ee12c6d6ff112d1fb___(
          v22,
          v18);
  Microsoft::WRL::ComPtr__StartOperationAndThenAgileCallback_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile____Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile_____lambda_f11977d2b9d3b11ee12c6d6ff112d1fb____::_2_::FTMEventDelegate_::_ComPtr__StartOperationAndThenAgileCallback_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile____Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile_____lambda_f11977d2b9d3b11ee12c6d6ff112d1fb____::_2_::FTMEventDelegate_(v25);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96F,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      (const char *)(unsigned int)v11,
      v20);
    if ( this )
      (*(void (__fastcall **)(SystemSettings::PenSettings::DevicesPenSetDesktopAppBase *))(*(_QWORD *)this + 16LL))(this);
    goto LABEL_23;
  }
  if ( this )
    (*(void (__fastcall **)(SystemSettings::PenSettings::DevicesPenSetDesktopAppBase *))(*(_QWORD *)this + 16LL))(this);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  WindowsDeleteString(v9);
  v5 = 0;
LABEL_31:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  return v5;
}

```

## disassembly

```asm
0x18002b6d0  push    rbp
0x18002b6d2  push    rbx
0x18002b6d3  push    rsi
0x18002b6d4  push    rdi
0x18002b6d5  push    r14
0x18002b6d7  lea     rbp, [rsp-37h]
0x18002b6dc  sub     rsp, 0C0h
0x18002b6e3  mov     rax, cs:__security_cookie
0x18002b6ea  xor     rax, rsp
0x18002b6ed  mov     [rbp+57h+var_30], rax
0x18002b6f1  mov     r14, rcx
0x18002b6f4  mov     [rbp+57h+var_B8], 0
0x18002b6fc  lea     rcx, [rbp+57h+var_50]; string
0x18002b700  call    ??$?0$0CH@@StringReference@Internal@Windows@@QEAA@AEAY0CH@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[39])
0x18002b705  lea     rdx, [rbp+57h+var_B8]
0x18002b709  mov     rcx, [rax]
0x18002b70c  call    ??$ActivateInstance@V?$ComPtr@UIFileOpenPicker@Pickers@Storage@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIFileOpenPicker@Pickers@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Pickers::IFileOpenPicker>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Pickers::IFileOpenPicker>>)
0x18002b711  mov     ebx, eax
0x18002b713  test    eax, eax
0x18002b715  jns     short loc_18002B71E
0x18002b717  mov     edx, 954h
0x18002b71c  jmp     short loc_18002B740
0x18002b71e  mov     rcx, [rbp+57h+var_B8]
0x18002b722  mov     rax, [rcx]
0x18002b725  mov     edi, 1
0x18002b72a  mov     edx, edi
0x18002b72c  mov     rax, [rax+58h]
0x18002b730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b735  mov     ebx, eax
0x18002b737  test    eax, eax
0x18002b739  jns     short loc_18002B758
0x18002b73b  mov     edx, 955h; void *
0x18002b740  mov     rcx, [rbp+5Fh]; this
0x18002b744  mov     r9d, eax; char *
0x18002b747  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002b74e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b753  jmp     loc_18002B9B5
0x18002b758  mov     rcx, [rbp+57h+var_B8]
0x18002b75c  mov     rax, [rcx]
0x18002b75f  mov     edx, edi
0x18002b761  mov     rax, [rax+38h]
0x18002b765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b76a  mov     ebx, eax
0x18002b76c  test    eax, eax
0x18002b76e  jns     short loc_18002B777
0x18002b770  mov     edx, 956h
0x18002b775  jmp     short loc_18002B740
0x18002b777  xor     ecx, ecx; string
0x18002b779  call    cs:__imp_WindowsDeleteString
0x18002b77f  mov     [rbp+57h+string], 0
0x18002b787  lea     rdx, [rbp+57h+string]; HSTRING *
0x18002b78b  lea     rcx, aSystemsettings_18; "SystemSettings_Devices_Pen_DesktopAppPi"...
0x18002b792  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18002b797  mov     ebx, eax
0x18002b799  test    eax, eax
0x18002b79b  jns     short loc_18002B7C5
0x18002b79d  mov     rcx, [rbp+5Fh]; this
0x18002b7a1  mov     r9d, eax; char *
0x18002b7a4  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002b7ab  mov     edx, 959h; void *
0x18002b7b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b7b5  nop
0x18002b7b6  mov     rcx, [rbp+57h+string]; string
0x18002b7ba  call    cs:__imp_WindowsDeleteString
0x18002b7c0  jmp     loc_18002B9B5
0x18002b7c5  mov     rcx, [rbp+57h+var_B8]
0x18002b7c9  mov     rax, [rcx]
0x18002b7cc  mov     rbx, [rbp+57h+string]
0x18002b7d0  mov     rdx, rbx
0x18002b7d3  mov     rax, [rax+68h]
0x18002b7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7dc  mov     edi, eax
0x18002b7de  test    eax, eax
0x18002b7e0  jns     short loc_18002B80B
0x18002b7e2  mov     rcx, [rbp+5Fh]; this
0x18002b7e6  mov     r9d, eax; char *
0x18002b7e9  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002b7f0  mov     edx, 95Ah; void *
0x18002b7f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b7fa  nop
0x18002b7fb  mov     rcx, rbx; string
0x18002b7fe  call    cs:__imp_WindowsDeleteString
0x18002b804  mov     ebx, edi
0x18002b806  jmp     loc_18002B9B5
0x18002b80b  mov     [rbp+57h+var_C0], 0
0x18002b813  lea     rdx, aExe; ".exe"
0x18002b81a  lea     rcx, [rbp+57h+var_90]; string
0x18002b81e  call    ??$?0$04@StringReference@Internal@Windows@@QEAA@AEAY04$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[5])
0x18002b823  mov     rsi, [rbp+57h+var_B8]
0x18002b827  mov     rax, [rsi]
0x18002b82a  mov     rdi, [rax+70h]
0x18002b82e  lea     rcx, [rbp+57h+var_C0]
0x18002b832  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b837  lea     rdx, [rbp+57h+var_C0]
0x18002b83b  mov     rcx, rsi
0x18002b83e  mov     rax, rdi
0x18002b841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b846  mov     edi, eax
0x18002b848  test    eax, eax
0x18002b84a  jns     short loc_18002B870
0x18002b84c  mov     edx, 95Dh; void *
0x18002b851  mov     rcx, [rbp+5Fh]; this
0x18002b855  mov     r9d, edi; char *
0x18002b858  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002b85f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b864  nop
0x18002b865  lea     rcx, [rbp+57h+var_C0]
0x18002b869  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b86e  jmp     short loc_18002B7FB
0x18002b870  mov     rcx, [rbp+57h+var_C0]
0x18002b874  mov     rax, [rcx]
0x18002b877  mov     rdx, [rbp+57h+var_90]
0x18002b87b  mov     rax, [rax+68h]
0x18002b87f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b884  mov     edi, eax
0x18002b886  test    eax, eax
0x18002b888  jns     short loc_18002B891
0x18002b88a  mov     edx, 95Eh
0x18002b88f  jmp     short loc_18002B851
0x18002b891  lea     rdx, aLnk; ".lnk"
0x18002b898  lea     rcx, [rbp+57h+var_70]; string
0x18002b89c  call    ??$?0$04@StringReference@Internal@Windows@@QEAA@AEAY04$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[5])
0x18002b8a1  mov     rcx, [rbp+57h+var_C0]
0x18002b8a5  mov     rax, [rcx]
0x18002b8a8  mov     rdx, [rbp+57h+var_70]
0x18002b8ac  mov     rax, [rax+68h]
0x18002b8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8b5  mov     edi, eax
0x18002b8b7  test    eax, eax
0x18002b8b9  jns     short loc_18002B8C2
0x18002b8bb  mov     edx, 960h
0x18002b8c0  jmp     short loc_18002B851
0x18002b8c2  mov     [rbp+57h+var_B0], 0
0x18002b8ca  mov     rsi, [rbp+57h+var_B8]
0x18002b8ce  mov     rax, [rsi]
0x18002b8d1  mov     rdi, [rax+78h]
0x18002b8d5  lea     rcx, [rbp+57h+var_B0]
0x18002b8d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b8de  lea     rdx, [rbp+57h+var_B0]
0x18002b8e2  mov     rcx, rsi
0x18002b8e5  mov     rax, rdi
0x18002b8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8ed  mov     edi, eax
0x18002b8ef  test    eax, eax
0x18002b8f1  jns     short loc_18002B91A
0x18002b8f3  mov     rcx, [rbp+5Fh]; this
0x18002b8f7  mov     r9d, eax; char *
0x18002b8fa  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002b901  mov     edx, 963h; void *
0x18002b906  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b90b  nop
0x18002b90c  lea     rcx, [rbp+57h+var_B0]
0x18002b910  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b915  jmp     loc_18002B865
0x18002b91a  mov     [rbp+57h+var_A0], r14
0x18002b91e  lea     rcx, [rbp+57h+var_A0]
0x18002b922  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18002b927  nop
0x18002b928  lea     rdx, [rbp+57h+var_A0]
0x18002b92c  lea     rcx, [rbp+57h+var_98]
0x18002b930  call    _lambda_f11977d2b9d3b11ee12c6d6ff112d1fb____lambda_f11977d2b9d3b11ee12c6d6ff112d1fb_
0x18002b935  nop
0x18002b936  mov     rdx, rax
0x18002b939  mov     rcx, [rbp+57h+var_B0]
0x18002b93d  call    StartOperationAndThenAgileCallback_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Storage__StorageFile____Windows__Foundation__IAsyncOperation_Windows__Storage__StorageFile_____lambda_f11977d2b9d3b11ee12c6d6ff112d1fb___
0x18002b942  mov     edi, eax
0x18002b944  lea     rcx, [rbp+57h+var_98]
0x18002b948  call    Microsoft__WRL__ComPtr__StartOperationAndThenAgileCallback_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Storage__StorageFile____Windows__Foundation__IAsyncOperation_Windows__Storage__StorageFile_____lambda_f11977d2b9d3b11ee12c6d6ff112d1fb_______2___FTMEventDelegate____ComPtr__StartOperationAndThenAgileCallback_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Storage__StorageFile____Windows__Foundation__IAsyncOperation_Windows__Storage__StorageFile_____lambda_f11977d2b9d3b11ee12c6d6ff112d1fb_______2___FTMEventDelegate_
0x18002b94d  test    edi, edi
0x18002b94f  jns     short loc_18002B981
0x18002b951  mov     rcx, [rbp+5Fh]; this
0x18002b955  mov     r9d, edi; char *
0x18002b958  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002b95f  mov     edx, 96Fh; void *
0x18002b964  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b969  nop
0x18002b96a  test    r14, r14
0x18002b96d  jz      short loc_18002B97F
0x18002b96f  mov     rax, [r14]
0x18002b972  mov     rcx, r14
0x18002b975  mov     rax, [rax+10h]
0x18002b979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b97e  nop
0x18002b97f  jmp     short loc_18002B90C
0x18002b981  test    r14, r14
0x18002b984  jz      short loc_18002B996
0x18002b986  mov     rax, [r14]
0x18002b989  mov     rcx, r14
0x18002b98c  mov     rax, [rax+10h]
0x18002b990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b995  nop
0x18002b996  lea     rcx, [rbp+57h+var_B0]
0x18002b99a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b99f  nop
0x18002b9a0  lea     rcx, [rbp+57h+var_C0]
0x18002b9a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b9a9  nop
0x18002b9aa  mov     rcx, rbx; string
0x18002b9ad  call    cs:__imp_WindowsDeleteString
0x18002b9b3  xor     ebx, ebx
0x18002b9b5  lea     rcx, [rbp+57h+var_B8]
0x18002b9b9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b9be  mov     eax, ebx
0x18002b9c0  mov     rcx, [rbp+57h+var_30]
0x18002b9c4  xor     rcx, rsp; StackCookie
0x18002b9c7  call    __security_check_cookie
0x18002b9cc  add     rsp, 0C0h
0x18002b9d3  pop     r14
0x18002b9d5  pop     rdi
0x18002b9d6  pop     rsi
0x18002b9d7  pop     rbx
0x18002b9d8  pop     rbp
0x18002b9d9  retn
```
