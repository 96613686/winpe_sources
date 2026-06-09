# WindowsInternal::Shell::UnifiedTile::Private::SettingsVerb::Execute(WindowsInternal::Shell::UnifiedTile::IVerbExecutionArgs *)

- ea: `0x180373040`
- end: `0x180373452`
- name: `?Execute@SettingsVerb@Private@UnifiedTile@Shell@WindowsInternal@@UEAAJPEAUIVerbExecutionArgs@345@@Z`
- size: `1042`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::Private::SettingsVerb *__hidden this, struct WindowsInternal::Shell::UnifiedTile::IVerbExecutionArgs *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18004ffc0`
- `0x180112f58`
- `0x180141308`
- `0x180201e50`
- `0x18031d13c`
- `0x180320874`
- `0x180373008`
- `0x180373040`
- `0x1803734f8`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1803732ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180373319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18037336c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1803732ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180373319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18037336c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180373160`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803731a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037322c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180373270`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803732dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037332f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803733ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803733ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180373160`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803731a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037322c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180373270`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803732dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037332f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803733ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803733ff`

## string_xrefs

- `0x1803730d6`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\packagedtileverbs.cpp`
- `0x18037312d`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\packagedtileverbs.cpp`
- `0x180373189`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\packagedtileverbs.cpp`
- `0x180373211`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\packagedtileverbs.cpp`
- `0x18037328f`: `page=SettingsPageSystemComponents&target=SystemSettings_StorageSense_HiddenSystemComponentsAdvancedPageLink&invoke=true&parameter=`
- `0x18037334e`: `page=SettingsPageInstalledApps&target=SystemSettings_StorageSense_HiddenAppAdvancedPageLink&invoke=true&parameter=`
- `0x1803732fb`: `page=SettingsPageAppsSizes&target=SystemSettings_StorageSense_HiddenAppAdvancedPageLink&invoke=true&parameter=`

## pseudocode

```c
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::Private::SettingsVerb::Execute(
        WindowsInternal::Shell::UnifiedTile::Private::SettingsVerb *this,
        struct WindowsInternal::Shell::UnifiedTile::IVerbExecutionArgs *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v17)(_QWORD, GUID *, __int64 *); // rbx
  HRESULT v18; // eax
  __int64 v19; // rdx
  HSTRING v20; // rbx
  HSTRING v21; // rbx
  HSTRING v22; // rbx
  __int64 v23; // rdx
  HSTRING newString; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v27[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string1; // [rsp+70h] [rbp-90h]
  _QWORD v34[42]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  wil::ActivityBase<DataStoreTransformerLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DataStoreTransformerLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v34);
  v34[0] = &DataStoreTransformerTelemetry::SettingsVerbExecute::`vftable';
  DataStoreTransformerTelemetry::SettingsVerbExecute::StartActivity((DataStoreTransformerTelemetry::SettingsVerbExecute *)v34);
  v31 = 0;
  v4 = *((_QWORD *)this + 18);
  v5 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v4 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  v6 = v5(v4, &v31);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v28 = 0;
    v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v31;
    v9 = **v31;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    v10 = v9(v8, &GUID_a7668288_cc23_4b67_be8b_6c10455986b8, &v28);
    v7 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC0,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\packagedtileverbs.cpp",
        (const char *)(unsigned int)v10,
        (int)newString);
LABEL_5:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
      goto LABEL_32;
    }
    string = 0;
    v11 = v28;
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v13 = v12(v11, &string);
    v7 = v13;
    if ( v13 < 0 )
    {
      v14 = (unsigned int)v13;
      v15 = 195;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\packagedtileverbs.cpp",
        (const char *)v14,
        (int)newString);
LABEL_9:
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_5;
    }
    if ( !string )
    {
      v7 = -2147023728;
      v14 = 2147943568LL;
      v15 = 196;
      goto LABEL_8;
    }
    newString = 0;
    v29 = 0;
    v16 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 18);
    v17 = **v16;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    v18 = v17(v16, &GUID_dd471f4c_6551_41ef_b8a3_cafff5e87a37, &v29);
    v7 = v18;
    if ( v18 >= 0 )
    {
      v27[0] = 0;
      v18 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v29 + 48LL))(v29, v27);
      v7 = v18;
      if ( v18 >= 0 )
      {
        if ( v27[0] )
        {
          WindowsDeleteString(newString);
          newString = 0;
          v20 = string;
          string1 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"page=SettingsPageSystemComponents&target=SystemSettings_StorageSense_HiddenSystemComponentsAdvancedPageLink&"
             "invoke=true&parameter=",
            0x83u,
            0x82u);
          v18 = WindowsConcatString(string1, v20, &newString);
          v7 = v18;
          if ( v18 < 0 )
          {
            v19 = 209;
            goto LABEL_14;
          }
        }
        else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RenameSettingsPageAppsSizesReferences>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RenameSettingsPageAppsSizesReferences>::GetImpl'::`2'::impl) )
        {
          WindowsDeleteString(newString);
          newString = 0;
          v22 = string;
          string1 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"page=SettingsPageInstalledApps&target=SystemSettings_StorageSense_HiddenAppAdvancedPageLink&invoke=true&parameter=",
            0x73u,
            0x72u);
          v18 = WindowsConcatString(string1, v22, &newString);
          v7 = v18;
          if ( v18 < 0 )
          {
            v19 = 216;
            goto LABEL_14;
          }
        }
        else
        {
          WindowsDeleteString(newString);
          newString = 0;
          v21 = string;
          string1 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"page=SettingsPageAppsSizes&target=SystemSettings_StorageSense_HiddenAppAdvancedPageLink&invoke=true&parameter=",
            0x6Fu,
            0x6Eu);
          v18 = WindowsConcatString(string1, v21, &newString);
          v7 = v18;
          if ( v18 < 0 )
          {
            v19 = 221;
            goto LABEL_14;
          }
        }
        v23 = 0;
        v30 = 0;
        if ( a2 )
        {
          v18 = (*(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IVerbExecutionArgs *, unsigned int *))(*(_QWORD *)a2 + 88LL))(
                  a2,
                  &v30);
          v7 = v18;
          if ( v18 < 0 )
          {
            v19 = 228;
            goto LABEL_14;
          }
          v23 = v30;
        }
        v18 = anonymous_namespace_::ActivateSettingsApp(newString, v23, *((_QWORD *)this + 16));
        v7 = v18;
        if ( v18 >= 0 )
        {
          wil::ActivityBase<DataStoreTransformerLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v34);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
          WindowsDeleteString(newString);
          newString = 0;
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
          v7 = 0;
          goto LABEL_32;
        }
        v19 = 231;
        goto LABEL_14;
      }
      v19 = 204;
    }
    else
    {
      v19 = 201;
    }
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\packagedtileverbs.cpp",
      (const char *)(unsigned int)v18,
      (int)newString);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    WindowsDeleteString(newString);
    newString = 0;
    goto LABEL_9;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xBD,
    (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\packagedtileverbs.cpp",
    (const char *)(unsigned int)v6,
    (int)newString);
LABEL_32:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  DataStoreTransformerTelemetry::SettingsVerbExecute::~SettingsVerbExecute((DataStoreTransformerTelemetry::SettingsVerbExecute *)v34);
  return v7;
}

```

## disassembly

```asm
0x180373040  mov     [rsp-8+arg_10], rbx
0x180373045  push    rbp
0x180373046  push    rsi
0x180373047  push    rdi
0x180373048  push    r14
0x18037304a  push    r15
0x18037304c  lea     rbp, [rsp-0E0h]
0x180373054  sub     rsp, 1E0h
0x18037305b  mov     rax, cs:__security_cookie
0x180373062  xor     rax, rsp
0x180373065  mov     [rbp+100h+var_30], rax
0x18037306c  mov     rsi, rdx
0x18037306f  mov     r14, rcx
0x180373072  lea     rdx, aSettingsverbex; "SettingsVerbExecute"
0x180373079  lea     rcx, [rbp+100h+var_180]; struct wil::details::IFailureCallback *
0x18037307d  call    ??0?$ActivityBase@VDataStoreTransformerLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DataStoreTransformerLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DataStoreTransformerLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180373082  lea     rax, ??_7SettingsVerbExecute@DataStoreTransformerTelemetry@@6B@; const DataStoreTransformerTelemetry::SettingsVerbExecute::`vftable'
0x180373089  mov     [rbp+100h+var_180], rax
0x18037308d  lea     rcx, [rbp+100h+var_180]; this
0x180373091  call    ?StartActivity@SettingsVerbExecute@DataStoreTransformerTelemetry@@QEAAXXZ; DataStoreTransformerTelemetry::SettingsVerbExecute::StartActivity(void)
0x180373096  xor     r15d, r15d
0x180373099  mov     [rsp+200h+var_1B0], r15
0x18037309e  mov     rdi, [r14+90h]
0x1803730a5  mov     rax, [rdi]
0x1803730a8  mov     rbx, [rax+30h]
0x1803730ac  lea     rcx, [rsp+200h+var_1B0]
0x1803730b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803730b6  lea     rdx, [rsp+200h+var_1B0]
0x1803730bb  mov     rcx, rdi
0x1803730be  mov     rax, rbx
0x1803730c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803730c6  mov     ebx, eax
0x1803730c8  test    eax, eax
0x1803730ca  jns     short loc_1803730EC
0x1803730cc  mov     rcx, [rbp+108h]; this
0x1803730d3  mov     r9d, eax; char *
0x1803730d6  lea     r8, aShellcommonShe_181; "shellcommon\\shell\\datastorecache\\tra"...
0x1803730dd  mov     edx, 0BDh; void *
0x1803730e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803730e7  jmp     loc_180373417
0x1803730ec  mov     [rsp+200h+var_1C8], r15
0x1803730f1  mov     rdi, [rsp+200h+var_1B0]
0x1803730f6  mov     rax, [rdi]
0x1803730f9  mov     rbx, [rax]
0x1803730fc  lea     rcx, [rsp+200h+var_1C8]
0x180373101  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180373106  lea     r8, [rsp+200h+var_1C8]
0x18037310b  lea     rdx, _GUID_a7668288_cc23_4b67_be8b_6c10455986b8
0x180373112  mov     rcx, rdi
0x180373115  mov     rax, rbx
0x180373118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037311d  mov     ebx, eax
0x18037311f  test    eax, eax
0x180373121  jns     short loc_18037314D
0x180373123  mov     rcx, [rbp+108h]; this
0x18037312a  mov     r9d, eax; char *
0x18037312d  lea     r8, aShellcommonShe_181; "shellcommon\\shell\\datastorecache\\tra"...
0x180373134  mov     edx, 0C0h; void *
0x180373139  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037313e  lea     rcx, [rsp+200h+var_1C8]
0x180373143  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180373148  jmp     loc_180373417
0x18037314d  mov     [rsp+200h+string], r15
0x180373152  mov     rdi, [rsp+200h+var_1C8]
0x180373157  mov     rax, [rdi]
0x18037315a  mov     rbx, [rax+30h]
0x18037315e  xor     ecx, ecx; string
0x180373160  call    cs:__imp_WindowsDeleteString
0x180373166  mov     [rsp+200h+string], r15
0x18037316b  lea     rdx, [rsp+200h+string]
0x180373170  mov     rcx, rdi
0x180373173  mov     rax, rbx
0x180373176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037317b  mov     ebx, eax
0x18037317d  test    eax, eax
0x18037317f  jns     short loc_1803731AE
0x180373181  mov     r9d, eax; char *
0x180373184  mov     edx, 0C3h; void *
0x180373189  lea     r8, aShellcommonShe_181; "shellcommon\\shell\\datastorecache\\tra"...
0x180373190  mov     rcx, [rbp+108h]; this
0x180373197  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037319c  mov     rcx, [rsp+200h+string]; string
0x1803731a1  call    cs:__imp_WindowsDeleteString
0x1803731a7  mov     [rsp+200h+string], r15
0x1803731ac  jmp     short loc_18037313E
0x1803731ae  cmp     [rsp+200h+string], r15
0x1803731b3  jnz     short loc_1803731C4
0x1803731b5  mov     ebx, 80070490h
0x1803731ba  mov     r9d, ebx
0x1803731bd  mov     edx, 0C4h
0x1803731c2  jmp     short loc_180373189
0x1803731c4  mov     [rsp+200h+newString], r15; int
0x1803731c9  mov     [rsp+200h+var_1C0], r15
0x1803731ce  mov     rdi, [r14+90h]
0x1803731d5  mov     rax, [rdi]
0x1803731d8  mov     rbx, [rax]
0x1803731db  lea     rcx, [rsp+200h+var_1C0]
0x1803731e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803731e5  lea     r8, [rsp+200h+var_1C0]
0x1803731ea  lea     rdx, _GUID_dd471f4c_6551_41ef_b8a3_cafff5e87a37
0x1803731f1  mov     rcx, rdi
0x1803731f4  mov     rax, rbx
0x1803731f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803731fc  mov     ebx, eax
0x1803731fe  test    eax, eax
0x180373200  jns     short loc_18037323C
0x180373202  mov     edx, 0C9h; void *
0x180373207  mov     rcx, [rbp+108h]; this
0x18037320e  mov     r9d, eax; char *
0x180373211  lea     r8, aShellcommonShe_181; "shellcommon\\shell\\datastorecache\\tra"...
0x180373218  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037321d  lea     rcx, [rsp+200h+var_1C0]
0x180373222  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180373227  mov     rcx, [rsp+200h+newString]; string
0x18037322c  call    cs:__imp_WindowsDeleteString
0x180373232  mov     [rsp+200h+newString], r15
0x180373237  jmp     loc_18037319C
0x18037323c  mov     [rsp+200h+var_1D0], r15b
0x180373241  mov     rcx, [rsp+200h+var_1C0]
0x180373246  mov     rax, [rcx]
0x180373249  lea     rdx, [rsp+200h+var_1D0]
0x18037324e  mov     rax, [rax+30h]
0x180373252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180373257  mov     ebx, eax
0x180373259  test    eax, eax
0x18037325b  jns     short loc_180373264
0x18037325d  mov     edx, 0CCh
0x180373262  jmp     short loc_180373207
0x180373264  cmp     [rsp+200h+var_1D0], r15b
0x180373269  jz      short loc_1803732C7
0x18037326b  mov     rcx, [rsp+200h+newString]; string
0x180373270  call    cs:__imp_WindowsDeleteString
0x180373276  mov     [rsp+200h+newString], r15
0x18037327b  mov     rbx, [rsp+200h+string]
0x180373280  mov     [rsp+200h+string1], r15
0x180373285  mov     r9d, 82h; unsigned int
0x18037328b  lea     r8d, [r9+1]; unsigned int
0x18037328f  lea     rdx, aPageSettingspa_2; "page=SettingsPageSystemComponents&targe"...
0x180373296  lea     rcx, [rsp+200h+hstringHeader]; hstringHeader
0x18037329b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1803732a0  lea     r8, [rsp+200h+newString]; newString
0x1803732a5  mov     rdx, rbx; string2
0x1803732a8  mov     rcx, [rsp+200h+string1]; string1
0x1803732ad  call    cs:__imp_WindowsConcatString
0x1803732b3  mov     ebx, eax
0x1803732b5  test    eax, eax
0x1803732b7  jns     loc_180373382
0x1803732bd  mov     edx, 0D1h
0x1803732c2  jmp     loc_180373207
0x1803732c7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RenameSettingsPageAppsSizesReferences@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RenameSettingsPageAppsSizesReferences@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RenameSettingsPageAppsSizesReferences> `wil::Feature<__WilFeatureTraits_Feature_RenameSettingsPageAppsSizesReferences>::GetImpl(void)'::`2'::impl
0x1803732ce  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RenameSettingsPageAppsSizesReferences@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RenameSettingsPageAppsSizesReferences>::__private_IsEnabled(void)
0x1803732d3  mov     rcx, [rsp+200h+newString]; string
0x1803732d8  test    al, al
0x1803732da  jnz     short loc_18037332F
0x1803732dc  call    cs:__imp_WindowsDeleteString
0x1803732e2  mov     [rsp+200h+newString], r15
0x1803732e7  mov     rbx, [rsp+200h+string]
0x1803732ec  mov     [rsp+200h+string1], r15
0x1803732f1  mov     r9d, 6Eh ; 'n'; unsigned int
0x1803732f7  lea     r8d, [r9+1]; unsigned int
0x1803732fb  lea     rdx, aPageSettingspa_4; "page=SettingsPageAppsSizes&target=Syste"...
0x180373302  lea     rcx, [rsp+200h+hstringHeader]; hstringHeader
0x180373307  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18037330c  lea     r8, [rsp+200h+newString]; newString
0x180373311  mov     rdx, rbx; string2
0x180373314  mov     rcx, [rsp+200h+string1]; string1
0x180373319  call    cs:__imp_WindowsConcatString
0x18037331f  mov     ebx, eax
0x180373321  test    eax, eax
0x180373323  jns     short loc_180373382
0x180373325  mov     edx, 0DDh
0x18037332a  jmp     loc_180373207
0x18037332f  call    cs:__imp_WindowsDeleteString
0x180373335  mov     [rsp+200h+newString], r15
0x18037333a  mov     rbx, [rsp+200h+string]
0x18037333f  mov     [rsp+200h+string1], r15
0x180373344  mov     r9d, 72h ; 'r'; unsigned int
0x18037334a  lea     r8d, [r9+1]; unsigned int
0x18037334e  lea     rdx, aPageSettingspa; "page=SettingsPageInstalledApps&target=S"...
0x180373355  lea     rcx, [rsp+200h+hstringHeader]; hstringHeader
0x18037335a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18037335f  lea     r8, [rsp+200h+newString]; newString
0x180373364  mov     rdx, rbx; string2
0x180373367  mov     rcx, [rsp+200h+string1]; string1
0x18037336c  call    cs:__imp_WindowsConcatString
0x180373372  mov     ebx, eax
0x180373374  test    eax, eax
0x180373376  jns     short loc_180373382
0x180373378  mov     edx, 0D8h
0x18037337d  jmp     loc_180373207
0x180373382  mov     edx, r15d
0x180373385  mov     [rsp+200h+var_1B8], edx
0x180373389  test    rsi, rsi
0x18037338c  jz      short loc_1803733B6
0x18037338e  mov     rax, [rsi]
0x180373391  lea     rdx, [rsp+200h+var_1B8]
0x180373396  mov     rcx, rsi
0x180373399  mov     rax, [rax+58h]
0x18037339d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803733a2  mov     ebx, eax
0x1803733a4  test    eax, eax
0x1803733a6  jns     short loc_1803733B2
0x1803733a8  mov     edx, 0E4h
0x1803733ad  jmp     loc_180373207
0x1803733b2  mov     edx, [rsp+200h+var_1B8]
0x1803733b6  mov     r8, [r14+80h]
0x1803733bd  mov     rcx, [rsp+200h+newString]
0x1803733c2  call    _anonymous_namespace___ActivateSettingsApp
0x1803733c7  mov     ebx, eax
0x1803733c9  test    eax, eax
0x1803733cb  jns     short loc_1803733D7
0x1803733cd  mov     edx, 0E7h
0x1803733d2  jmp     loc_180373207
0x1803733d7  lea     rcx, [rbp+100h+var_180]
0x1803733db  call    ?Stop@?$ActivityBase@VDataStoreTransformerLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DataStoreTransformerLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1803733e0  lea     rcx, [rsp+200h+var_1C0]
0x1803733e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803733ea  mov     rcx, [rsp+200h+newString]; string
0x1803733ef  call    cs:__imp_WindowsDeleteString
0x1803733f5  mov     [rsp+200h+newString], r15
0x1803733fa  mov     rcx, [rsp+200h+string]; string
0x1803733ff  call    cs:__imp_WindowsDeleteString
0x180373405  mov     [rsp+200h+string], r15
0x18037340a  lea     rcx, [rsp+200h+var_1C8]
0x18037340f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180373414  mov     ebx, r15d
0x180373417  lea     rcx, [rsp+200h+var_1B0]
0x18037341c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180373421  lea     rcx, [rbp+100h+var_180]; this
0x180373425  call    ??1SettingsVerbExecute@DataStoreTransformerTelemetry@@QEAA@XZ; DataStoreTransformerTelemetry::SettingsVerbExecute::~SettingsVerbExecute(void)
0x18037342a  mov     eax, ebx
0x18037342c  mov     rcx, [rbp+100h+var_30]
0x180373433  xor     rcx, rsp; StackCookie
0x180373436  call    __security_check_cookie
0x18037343b  mov     rbx, [rsp+200h+arg_10]
0x180373443  add     rsp, 1E0h
0x18037344a  pop     r15
0x18037344c  pop     r14
0x18037344e  pop     rdi
0x18037344f  pop     rsi
0x180373450  pop     rbp
0x180373451  retn
```
