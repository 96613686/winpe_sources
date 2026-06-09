# CInputDialExperienceManager::OnEventQueued(CSingleViewShellExperience *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180134e90`
- end: `0x180135310`
- name: `?OnEventQueued@CInputDialExperienceManager@@EEAAJPEAVCSingleViewShellExperience@@PEAUHSTRING__@@PEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1152`
- prototype: `int(CInputDialExperienceManager *__hidden this, struct CSingleViewShellExperience *, HSTRING, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x180009dfc`
- `0x180016ba4`
- `0x18001702c`
- `0x180017808`
- `0x1800378dc`
- `0x180037b9c`
- `0x180053740`
- `0x18006f0ec`
- `0x18008ef68`
- `0x1800f1a00`
- `0x180100604`
- `0x180134e90`
- `0x180135318`
- `0x1801353b8`
- `0x180142e10`
- `0x1802066a4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801351d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180135298`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801352bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801352de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801351d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180135298`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801352bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801352de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180134f00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013525f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180134f00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013525f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x180135271`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x180135271`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CInputDialExperienceManager::OnEventQueued(
        CInputDialExperienceManager *this,
        ExperienceManagerUtils **a2,
        Microsoft::WRL::Wrappers::Details *a3,
        struct Windows::Foundation::Collections::IPropertySet *a4)
{
  int v8; // eax
  __int64 v9; // rax
  HSTRING v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rax
  HSTRING v13; // r8
  __int64 v14; // rax
  HSTRING v15; // r8
  __int64 v16; // rax
  HSTRING v17; // r8
  __int64 v18; // rax
  int v19; // eax
  char v20; // al
  __int64 v21; // rax
  HSTRING v22; // r8
  __int64 v23; // rax
  int v24; // eax
  char v25; // al
  __int64 v26; // rax
  HSTRING v27; // r8
  __int64 v28; // rax
  int v29; // eax
  char v30; // al
  HSTRING *v31; // rcx
  __int64 v32; // rax
  HSTRING v33; // r8
  __int64 v34; // rax
  int v35; // eax
  HSTRING v36; // r8
  unsigned int LastError; // ebx
  __int64 v38; // r9
  __int64 v39; // rdx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v40; // rdx
  HWND v41; // rbx
  const WCHAR *v42; // rax
  const char *v43; // r9
  int v45; // [rsp+20h] [rbp-60h]
  int StringRawBuffer; // [rsp+20h] [rbp-60h]
  HSTRING v47; // [rsp+30h] [rbp-50h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v48; // [rsp+38h] [rbp-48h] BYREF
  HSTRING v49; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v51[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v49 = (HSTRING)a3;
  string = 0;
  v8 = Microsoft::WRL::Wrappers::HString::Set(&string, &v49);
  if ( v8 >= 0 )
  {
    StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(string, 0);
    InputDial::InputDialTraceProvider::Info(
      "shell\\twinui\\inputdial\\experiencemanager\\inputdialexperiencemanager.cpp",
      "na",
      0x38Au,
      "OnEventQueued: %ws");
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x388,
      (unsigned int)"shell\\twinui\\inputdial\\experiencemanager\\inputdialexperiencemanager.cpp",
      (const char *)(unsigned int)v8,
      v45);
  }
  v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803F9AF8);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v9 + 24), v10) )
  {
    v11 = 11;
LABEL_10:
    InputDialMenuStateModel::ProcessEvent(*((_QWORD *)this + 37), v11, 0);
LABEL_45:
    LastError = 0;
    goto LABEL_46;
  }
  v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803F9AE8);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v12 + 24), v13) )
  {
    v11 = 12;
    goto LABEL_10;
  }
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803F9B00);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v14 + 24), v15) )
  {
    v11 = 13;
    goto LABEL_10;
  }
  v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803F9B40);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v16 + 24), v17) )
  {
    v48 = a4;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v48);
    LODWORD(v47) = 0;
    v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803CD568);
    v19 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<int>(
            (Windows::Internal::ShellHelpers::PropertySetHelper *)&v48,
            *(HSTRING *)(v18 + 24));
    if ( v19 >= 0 )
    {
      v20 = 1;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x39D,
        (unsigned int)"shell\\twinui\\inputdial\\experiencemanager\\inputdialexperiencemanager.cpp",
        (const char *)(unsigned int)v19,
        StringRawBuffer);
      v20 = 0;
    }
    if ( v20 )
    {
      v49 = (HSTRING)(unsigned int)v47;
      InputDialMenuStateModel::ProcessEvent(*((_QWORD *)this + 37), 16, &v49);
    }
    goto LABEL_43;
  }
  v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803F9B28);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v21 + 24), v22) )
  {
    v48 = a4;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v48);
    LODWORD(v47) = 0;
    v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803CD568);
    v24 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<int>(
            (Windows::Internal::ShellHelpers::PropertySetHelper *)&v48,
            *(HSTRING *)(v23 + 24));
    if ( v24 >= 0 )
    {
      v25 = 1;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3A8,
        (unsigned int)"shell\\twinui\\inputdial\\experiencemanager\\inputdialexperiencemanager.cpp",
        (const char *)(unsigned int)v24,
        StringRawBuffer);
      v25 = 0;
    }
    if ( v25 )
    {
      v49 = (HSTRING)(unsigned int)v47;
      InputDialMenuStateModel::ProcessEvent(*((_QWORD *)this + 37), 17, &v49);
    }
    goto LABEL_43;
  }
  v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803F9AF0);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v26 + 24), v27) )
  {
    v47 = (HSTRING)a4;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v47);
    v48 = 0;
    v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, &off_1803CD570);
    v29 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<Windows::Foundation::Point>(
            (Windows::Internal::ShellHelpers::PropertySetHelper *)&v47,
            *(HSTRING *)(v28 + 24));
    if ( v29 >= 0 )
    {
      v30 = 1;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3B5,
        (unsigned int)"shell\\twinui\\inputdial\\experiencemanager\\inputdialexperiencemanager.cpp",
        (const char *)(unsigned int)v29,
        StringRawBuffer);
      v30 = 0;
    }
    if ( v30 )
    {
      *((_DWORD *)this + 68) = (int)*(float *)&v48;
      *((_DWORD *)this + 69) = (int)*((float *)&v48 + 1);
    }
    v31 = &v47;
    goto LABEL_44;
  }
  v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803F9B38);
  if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v32 + 24), v33) )
    goto LABEL_45;
  v48 = a4;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v48);
  WindowsDeleteString(0);
  v47 = 0;
  v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803F9B20);
  v35 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v48,
          *(HSTRING *)(v34 + 24));
  LastError = v35;
  if ( v35 >= 0 )
  {
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                         (Microsoft::WRL::Wrappers::Details *)v47,
                         0,
                         v36) )
    {
      v41 = ExperienceManagerUtils::WindowFromViewWrapper(a2[3], v40);
      if ( !v41 )
      {
        LastError = -2147023728;
        v38 = 2147943568LL;
        v39 = 963;
        goto LABEL_38;
      }
      v42 = WindowsGetStringRawBuffer(v47, 0);
      if ( !SetWindowTextW(v41, v42) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x3C4,
                      (unsigned int)"shell\\twinui\\inputdial\\experiencemanager\\inputdialexperiencemanager.cpp",
                      v43);
        goto LABEL_41;
      }
    }
    WindowsDeleteString(v47);
    v47 = 0;
LABEL_43:
    v31 = (HSTRING *)&v48;
LABEL_44:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
    goto LABEL_45;
  }
  v38 = (unsigned int)v35;
  v39 = 959;
LABEL_38:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v39,
    (unsigned int)"shell\\twinui\\inputdial\\experiencemanager\\inputdialexperiencemanager.cpp",
    (const char *)v38,
    StringRawBuffer);
LABEL_41:
  WindowsDeleteString(v47);
  v47 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
LABEL_46:
  WindowsDeleteString(string);
  return LastError;
}

```

## disassembly

```asm
0x180134e90  mov     [rsp-28h+arg_18], rbx
0x180134e95  push    rbp
0x180134e96  push    rsi
0x180134e97  push    rdi
0x180134e98  push    r14
0x180134e9a  push    r15
0x180134e9c  mov     rbp, rsp
0x180134e9f  sub     rsp, 80h
0x180134ea6  mov     rax, cs:__security_cookie
0x180134ead  xor     rax, rsp
0x180134eb0  mov     [rbp+var_10], rax
0x180134eb4  mov     r14, r9
0x180134eb7  mov     rsi, r8
0x180134eba  mov     r15, rdx
0x180134ebd  mov     rbx, rcx
0x180134ec0  mov     [rbp+var_40], r8
0x180134ec4  mov     [rbp+string], 0
0x180134ecc  lea     rdx, [rbp+var_40]; HSTRING *
0x180134ed0  lea     rcx, [rbp+string]; newString
0x180134ed4  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180134ed9  mov     rcx, [rbp+28h]; this
0x180134edd  test    eax, eax
0x180134edf  jns     short loc_180134EFA
0x180134ee1  mov     r9d, eax; char *
0x180134ee4  lea     rdi, aShellTwinuiInp_2; "shell\\twinui\\inputdial\\experienceman"...
0x180134eeb  mov     r8, rdi; unsigned int
0x180134eee  mov     edx, 388h; void *
0x180134ef3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180134ef8  jmp     short loc_180134F34
0x180134efa  xor     edx, edx; length
0x180134efc  mov     rcx, [rbp+string]; string
0x180134f00  call    cs:__imp_WindowsGetStringRawBuffer
0x180134f07  nop     dword ptr [rax+rax+00h]
0x180134f0c  mov     qword ptr [rsp+80h+var_60], rax; int
0x180134f11  lea     r9, aOneventqueuedW; "OnEventQueued: %ws"
0x180134f18  mov     r8d, 38Ah; unsigned int
0x180134f1e  lea     rdx, aNa; "na"
0x180134f25  lea     rdi, aShellTwinuiInp_2; "shell\\twinui\\inputdial\\experienceman"...
0x180134f2c  mov     rcx, rdi; char *
0x180134f2f  call    ?Info@InputDialTraceProvider@InputDial@@SAXPEBD0I0ZZ; InputDial::InputDialTraceProvider::Info(char const *,char const *,uint,char const *,...)
0x180134f34  lea     rdx, off_1803F9AF8; "AnimateInCompleted"
0x180134f3b  lea     rcx, [rbp+var_30]
0x180134f3f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180134f44  mov     rdx, [rax+18h]; HSTRING
0x180134f48  mov     rcx, rsi; this
0x180134f4b  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180134f50  test    eax, eax
0x180134f52  jnz     short loc_180134F59
0x180134f54  lea     edx, [rax+0Bh]
0x180134f57  jmp     short loc_180134FA1
0x180134f59  lea     rdx, off_1803F9AE8; "AnimateInPreviewMenuCompleted"
0x180134f60  lea     rcx, [rbp+var_30]
0x180134f64  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180134f69  mov     rdx, [rax+18h]; HSTRING
0x180134f6d  mov     rcx, rsi; this
0x180134f70  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180134f75  test    eax, eax
0x180134f77  jnz     short loc_180134F7E
0x180134f79  lea     edx, [rax+0Ch]
0x180134f7c  jmp     short loc_180134FA1
0x180134f7e  lea     rdx, off_1803F9B00; "AnimateOutCompleted"
0x180134f85  lea     rcx, [rbp+var_30]
0x180134f89  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180134f8e  mov     rdx, [rax+18h]; HSTRING
0x180134f92  mov     rcx, rsi; this
0x180134f95  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180134f9a  test    eax, eax
0x180134f9c  jnz     short loc_180134FB5
0x180134f9e  lea     edx, [rax+0Dh]
0x180134fa1  xor     r8d, r8d
0x180134fa4  mov     rcx, [rbx+128h]
0x180134fab  call    ?ProcessEvent@InputDialMenuStateModel@@QEAAJW4EventType@@PEATEventData@@@Z; InputDialMenuStateModel::ProcessEvent(EventType,EventData *)
0x180134fb0  jmp     loc_1801352D8
0x180134fb5  lea     rdx, off_1803F9B40; "ItemClickDown"
0x180134fbc  lea     rcx, [rbp+var_30]
0x180134fc0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180134fc5  mov     rdx, [rax+18h]; HSTRING
0x180134fc9  mov     rcx, rsi; this
0x180134fcc  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180134fd1  test    eax, eax
0x180134fd3  jnz     loc_18013505B
0x180134fd9  mov     [rbp+var_48], r14
0x180134fdd  lea     rcx, [rbp+var_48]
0x180134fe1  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180134fe6  nop
0x180134fe7  mov     dword ptr [rbp+var_50], 0
0x180134fee  lea     rdx, off_1803CD568; "Int32Value"
0x180134ff5  lea     rcx, [rbp+var_30]
0x180134ff9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180134ffe  nop
0x180134fff  lea     r9, [rbp+var_50]
0x180135003  mov     rdx, [rax+18h]; HSTRING
0x180135007  lea     rcx, [rbp+var_48]; this
0x18013500b  call    ??$GetValue@H@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAH@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<int>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(int *),int *)
0x180135010  mov     rcx, [rbp+28h]; this
0x180135014  test    eax, eax
0x180135016  jns     short loc_18013502C
0x180135018  mov     r9d, eax; char *
0x18013501b  mov     r8, rdi; unsigned int
0x18013501e  mov     edx, 39Dh; void *
0x180135023  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180135028  xor     al, al
0x18013502a  jmp     short loc_18013502E
0x18013502c  mov     al, 1
0x18013502e  test    al, al
0x180135030  jz      short loc_180135056
0x180135032  mov     [rbp+var_40], 0
0x18013503a  mov     eax, dword ptr [rbp+var_50]
0x18013503d  mov     dword ptr [rbp+var_40], eax
0x180135040  lea     r8, [rbp+var_40]
0x180135044  mov     edx, 10h
0x180135049  mov     rcx, [rbx+128h]
0x180135050  call    ?ProcessEvent@InputDialMenuStateModel@@QEAAJW4EventType@@PEATEventData@@@Z; InputDialMenuStateModel::ProcessEvent(EventType,EventData *)
0x180135055  nop
0x180135056  jmp     loc_1801352CF
0x18013505b  lea     rdx, off_1803F9B28; "ItemClickUp"
0x180135062  lea     rcx, [rbp+var_30]
0x180135066  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18013506b  mov     rdx, [rax+18h]; HSTRING
0x18013506f  mov     rcx, rsi; this
0x180135072  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180135077  test    eax, eax
0x180135079  jnz     loc_180135101
0x18013507f  mov     [rbp+var_48], r14
0x180135083  lea     rcx, [rbp+var_48]
0x180135087  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18013508c  nop
0x18013508d  mov     dword ptr [rbp+var_50], 0
0x180135094  lea     rdx, off_1803CD568; "Int32Value"
0x18013509b  lea     rcx, [rbp+var_30]
0x18013509f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801350a4  nop
0x1801350a5  lea     r9, [rbp+var_50]
0x1801350a9  mov     rdx, [rax+18h]; HSTRING
0x1801350ad  lea     rcx, [rbp+var_48]; this
0x1801350b1  call    ??$GetValue@H@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAH@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<int>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(int *),int *)
0x1801350b6  mov     rcx, [rbp+28h]; this
0x1801350ba  test    eax, eax
0x1801350bc  jns     short loc_1801350D2
0x1801350be  mov     r9d, eax; char *
0x1801350c1  mov     r8, rdi; unsigned int
0x1801350c4  mov     edx, 3A8h; void *
0x1801350c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801350ce  xor     al, al
0x1801350d0  jmp     short loc_1801350D4
0x1801350d2  mov     al, 1
0x1801350d4  test    al, al
0x1801350d6  jz      short loc_1801350FC
0x1801350d8  mov     [rbp+var_40], 0
0x1801350e0  mov     eax, dword ptr [rbp+var_50]
0x1801350e3  mov     dword ptr [rbp+var_40], eax
0x1801350e6  lea     r8, [rbp+var_40]
0x1801350ea  mov     edx, 11h
0x1801350ef  mov     rcx, [rbx+128h]
0x1801350f6  call    ?ProcessEvent@InputDialMenuStateModel@@QEAAJW4EventType@@PEATEventData@@@Z; InputDialMenuStateModel::ProcessEvent(EventType,EventData *)
0x1801350fb  nop
0x1801350fc  jmp     loc_1801352CF
0x180135101  lea     rdx, off_1803F9AF0; "WindowPositionChanged"
0x180135108  lea     rcx, [rbp+var_30]
0x18013510c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180135111  mov     rdx, [rax+18h]; HSTRING
0x180135115  mov     rcx, rsi; this
0x180135118  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18013511d  test    eax, eax
0x18013511f  jnz     short loc_180135198
0x180135121  mov     [rbp+var_50], r14
0x180135125  lea     rcx, [rbp+var_50]
0x180135129  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18013512e  nop
0x18013512f  xor     eax, eax
0x180135131  mov     [rbp+var_48], rax
0x180135135  lea     rdx, off_1803CD570; "WindowPosition_Param"
0x18013513c  lea     rcx, [rbp+var_30]
0x180135140  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180135145  nop
0x180135146  lea     r9, [rbp+var_48]
0x18013514a  mov     rdx, [rax+18h]; HSTRING
0x18013514e  lea     rcx, [rbp+var_50]; this
0x180135152  call    ??$GetValue@UPoint@Foundation@Windows@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAUPoint@63@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<Windows::Foundation::Point>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(Windows::Foundation::Point *),Windows::Foundation::Point *)
0x180135157  mov     rcx, [rbp+28h]; this
0x18013515b  test    eax, eax
0x18013515d  jns     short loc_180135173
0x18013515f  mov     r9d, eax; char *
0x180135162  mov     r8, rdi; unsigned int
0x180135165  mov     edx, 3B5h; void *
0x18013516a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18013516f  xor     al, al
0x180135171  jmp     short loc_180135175
0x180135173  mov     al, 1
0x180135175  test    al, al
0x180135177  jz      short loc_18013518F
0x180135179  cvttss2si eax, dword ptr [rbp+var_48]
0x18013517e  mov     [rbx+110h], eax
0x180135184  cvttss2si eax, dword ptr [rbp+var_48+4]
0x180135189  mov     [rbx+114h], eax
0x18013518f  lea     rcx, [rbp+var_50]
0x180135193  jmp     loc_1801352D3
0x180135198  lea     rdx, off_1803F9B38; "NotifyWindowName"
0x18013519f  lea     rcx, [rbp+var_30]
0x1801351a3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801351a8  mov     rdx, [rax+18h]; HSTRING
0x1801351ac  mov     rcx, rsi; this
0x1801351af  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1801351b4  test    eax, eax
0x1801351b6  jnz     loc_1801352D8
0x1801351bc  mov     [rbp+var_48], r14
0x1801351c0  lea     rcx, [rbp+var_48]
0x1801351c4  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1801351c9  nop
0x1801351ca  mov     [rbp+var_50], 0
0x1801351d2  xor     ecx, ecx; string
0x1801351d4  call    cs:__imp_WindowsDeleteString
0x1801351db  nop     dword ptr [rax+rax+00h]
0x1801351e0  mov     [rbp+var_50], 0
0x1801351e8  lea     rdx, off_1803F9B20; "TextContent"
0x1801351ef  lea     rcx, [rbp+var_30]
0x1801351f3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801351f8  nop
0x1801351f9  lea     r9, [rbp+var_50]
0x1801351fd  mov     rdx, [rax+18h]; HSTRING
0x180135201  lea     rcx, [rbp+var_48]; this
0x180135205  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x18013520a  mov     ebx, eax
0x18013520c  test    eax, eax
0x18013520e  jns     short loc_18013521A
0x180135210  mov     r9d, eax
0x180135213  mov     edx, 3BFh
0x180135218  jmp     short loc_18013524B
0x18013521a  xor     edx, edx; HSTRING
0x18013521c  mov     rcx, [rbp+var_50]; this
0x180135220  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180135225  test    eax, eax
0x180135227  jz      loc_1801352B7
0x18013522d  mov     rcx, [r15+18h]; this
0x180135231  call    ?WindowFromViewWrapper@ExperienceManagerUtils@@YAPEAUHWND__@@PEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@@Z; ExperienceManagerUtils::WindowFromViewWrapper(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)
0x180135236  mov     rbx, rax
0x180135239  test    rax, rax
0x18013523c  jnz     short loc_180135259
0x18013523e  mov     ebx, 80070490h
0x180135243  mov     r9d, ebx; char *
0x180135246  mov     edx, 3C3h; void *
0x18013524b  mov     r8, rdi; unsigned int
0x18013524e  mov     rcx, [rbp+28h]; this
0x180135252  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180135257  jmp     short loc_180135294
0x180135259  xor     edx, edx; length
0x18013525b  mov     rcx, [rbp+var_50]; string
0x18013525f  call    cs:__imp_WindowsGetStringRawBuffer
0x180135266  nop     dword ptr [rax+rax+00h]
0x18013526b  mov     rdx, rax; lpString
0x18013526e  mov     rcx, rbx; hWnd
0x180135271  call    cs:__imp_SetWindowTextW
0x180135278  nop     dword ptr [rax+rax+00h]
0x18013527d  test    eax, eax
0x18013527f  jnz     short loc_1801352B7
0x180135281  mov     rcx, [rbp+28h]; this
0x180135285  mov     r8, rdi; unsigned int
0x180135288  mov     edx, 3C4h; void *
0x18013528d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180135292  mov     ebx, eax
0x180135294  mov     rcx, [rbp+var_50]; string
0x180135298  call    cs:__imp_WindowsDeleteString
0x18013529f  nop     dword ptr [rax+rax+00h]
0x1801352a4  mov     [rbp+var_50], 0
0x1801352ac  lea     rcx, [rbp+var_48]
0x1801352b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801352b5  jmp     short loc_1801352DA
0x1801352b7  mov     rcx, [rbp+var_50]; string
0x1801352bb  call    cs:__imp_WindowsDeleteString
0x1801352c2  nop     dword ptr [rax+rax+00h]
0x1801352c7  mov     [rbp+var_50], 0
0x1801352cf  lea     rcx, [rbp+var_48]
0x1801352d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801352d8  xor     ebx, ebx
0x1801352da  mov     rcx, [rbp+string]; string
0x1801352de  call    cs:__imp_WindowsDeleteString
0x1801352e5  nop     dword ptr [rax+rax+00h]
0x1801352ea  mov     eax, ebx
0x1801352ec  mov     rcx, [rbp+var_10]
0x1801352f0  xor     rcx, rsp; StackCookie
0x1801352f3  call    __security_check_cookie
0x1801352f8  mov     rbx, [rsp+80h+arg_18]
0x180135300  add     rsp, 80h
0x180135307  pop     r15
0x180135309  pop     r14
0x18013530b  pop     rdi
0x18013530c  pop     rsi
0x18013530d  pop     rbp
0x18013530e  retn
```
