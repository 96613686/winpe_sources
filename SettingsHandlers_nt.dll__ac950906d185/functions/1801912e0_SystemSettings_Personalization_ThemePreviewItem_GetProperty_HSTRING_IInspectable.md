# SystemSettings::Personalization::ThemePreviewItem::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x1801912e0`
- end: `0x1801916de`
- name: `?GetProperty@ThemePreviewItem@Personalization@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `1022`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::ThemePreviewItem *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180019a20`
- `0x1800201c4`
- `0x180020224`
- `0x180021398`
- `0x180032208`
- `0x18004d01c`
- `0x18005019c`
- `0x180098728`
- `0x180190e2c`
- `0x1801912e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019143a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019148e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801914df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180191518`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801915b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801915cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801915e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180191627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180191639`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801916ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801916bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019143a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019148e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801914df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180191518`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801915b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801915cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801915e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180191627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180191639`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801916ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801916bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180191548`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019155d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180191575`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180191657`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019166f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180191548`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019155d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180191575`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180191657`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019166f`

## pseudocode

```c
__int64 __fastcall SystemSettings::Personalization::ThemePreviewItem::GetProperty(
        SystemSettings::Personalization::ThemePreviewItem *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  int UInt32; // ebx
  __int64 v8; // rdx
  const unsigned __int16 *v10; // r8
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r8
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rcx
  int ResourceStringById; // eax
  __int64 v17; // rdx
  int v18; // eax
  bool v19; // zf
  unsigned int v20; // edx
  HSTRING v21; // rsi
  PCWSTR v22; // r15
  PCWSTR v23; // rax
  HSTRING v24; // rbx
  PCWSTR v25; // r14
  PCWSTR v26; // rax
  int v27; // eax
  int v28; // r14d
  int v29; // esi
  __int64 v30; // rdx
  __int64 v31; // r14
  PCWSTR StringRawBuffer; // rax
  PCWSTR v33; // rsi
  PCWSTR v34; // rax
  HSTRING v35; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v36[3]; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  HSTRING v38; // [rsp+80h] [rbp+40h] BYREF
  HSTRING string; // [rsp+88h] [rbp+48h] BYREF

  *a3 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802F6BC8, (const unsigned __int16 *)a3) )
  {
    UInt32 = SystemSettings::DataModel::PropValueHelper::CreateString(*((const unsigned __int16 **)this + 28), a3);
    if ( UInt32 < 0 )
    {
      v8 = 211;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\themepreview.cpp",
        (const char *)(unsigned int)UInt32,
        (int)v35);
      return (unsigned int)UInt32;
    }
    return 0;
  }
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180317A08, v6) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180317A28, v10) )
    {
      UInt32 = SystemSettings::DataModel::PropValueHelper::CreateString(*((const unsigned __int16 **)this + 34), a3);
      if ( UInt32 < 0 )
      {
        v8 = 219;
        goto LABEL_4;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180317A50, v11) )
    {
      UInt32 = SystemSettings::DataModel::PropValueHelper::CreateUInt32(*((_DWORD *)this + 75), a3);
      if ( UInt32 < 0 )
      {
        v8 = 223;
        goto LABEL_4;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180317A78, v12) )
    {
      UInt32 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 296), a3);
      if ( UInt32 < 0 )
      {
        v8 = 227;
        goto LABEL_4;
      }
      return 0;
    }
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180317AA0, v13) )
      return 0;
    WindowsDeleteString(0);
    v14 = *((_QWORD *)this + 38);
    v15 = (const unsigned __int16 *)*((_QWORD *)this + 31);
    v38 = 0;
    ResourceStringById = GetResourceStringById(
                           v15,
                           *(struct Windows::ApplicationModel::Resources::Core::IResourceMap **)(v14 + 64),
                           &v38);
    UInt32 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\themepreview.cpp",
        (const char *)(unsigned int)ResourceStringById,
        (int)v35);
LABEL_30:
      WindowsDeleteString(v38);
      return (unsigned int)UInt32;
    }
    WindowsDeleteString(0);
    v17 = *((_QWORD *)this + 38);
    string = 0;
    v18 = GetResourceStringById(
            L"SystemSettings_Personalize_Themes_Preview_AutomationText",
            *(struct Windows::ApplicationModel::Resources::Core::IResourceMap **)(v17 + 64),
            &string);
    UInt32 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\themepreview.cpp",
        (const char *)(unsigned int)v18,
        (int)v35);
      WindowsDeleteString(string);
      goto LABEL_30;
    }
    v19 = *((_BYTE *)this + 296) == 0;
    memset(v36, 0, sizeof(v36));
    if ( v19 )
    {
      v31 = *((_QWORD *)this + 34);
      StringRawBuffer = WindowsGetStringRawBuffer(v38, 0);
      v24 = string;
      v33 = StringRawBuffer;
      v34 = WindowsGetStringRawBuffer(string, 0);
      v29 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeMessage(
              v36,
              v34,
              v33,
              v31);
      if ( v29 < 0 )
      {
        v30 = 245;
LABEL_29:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\themepreview.cpp",
          (const char *)(unsigned int)v29,
          (int)v35);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v36);
        WindowsDeleteString(v24);
        UInt32 = v29;
        goto LABEL_30;
      }
    }
    else
    {
      WindowsDeleteString(0);
      v20 = *((_DWORD *)this + 75);
      v35 = 0;
      SystemSettings::Personalization::ThemePreviewItem::GetColorName(this, v20, &v35);
      v21 = v35;
      v22 = WindowsGetStringRawBuffer(v35, 0);
      v23 = WindowsGetStringRawBuffer(v38, 0);
      v24 = string;
      v25 = v23;
      v26 = WindowsGetStringRawBuffer(string, 0);
      v27 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeMessage(
              v36,
              v26,
              v25,
              v22);
      v28 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF1,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\themepreview.cpp",
          (const char *)(unsigned int)v27,
          (int)v35);
        WindowsDeleteString(v21);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v36);
        WindowsDeleteString(v24);
        UInt32 = v28;
        goto LABEL_30;
      }
      WindowsDeleteString(v21);
    }
    v29 = SystemSettings::DataModel::PropValueHelper::CreateString(v36[0], a3);
    if ( v29 >= 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v36);
      WindowsDeleteString(v24);
      WindowsDeleteString(v38);
      return 0;
    }
    v30 = 248;
    goto LABEL_29;
  }
  UInt32 = SystemSettings::DataModel::PropValueHelper::CreateString(*((const unsigned __int16 **)this + 31), a3);
  if ( UInt32 < 0 )
  {
    v8 = 215;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x1801912e0  mov     [rsp-28h+arg_0], rbx
0x1801912e5  push    rbp
0x1801912e6  push    rsi
0x1801912e7  push    r12
0x1801912e9  push    r14
0x1801912eb  push    r15
0x1801912ed  mov     rbp, rsp
0x1801912f0  sub     rsp, 40h
0x1801912f4  mov     rbx, rdx
0x1801912f7  mov     qword ptr [r8], 0
0x1801912fe  mov     r14, rcx
0x180191301  lea     rdx, stru_1802F6BC8; HSTRING
0x180191308  mov     rcx, rbx; this
0x18019130b  mov     r12, r8
0x18019130e  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180191313  test    al, al
0x180191315  jz      short loc_18019134F
0x180191317  mov     rcx, [r14+0E0h]; unsigned __int16 *
0x18019131e  mov     rdx, r12; struct IInspectable **
0x180191321  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180191326  mov     ebx, eax
0x180191328  test    eax, eax
0x18019132a  jns     loc_1801916C9
0x180191330  mov     edx, 0D3h; void *
0x180191335  mov     rcx, [rbp+28h]; this
0x180191339  lea     r8, aShellSystemset_21; "shell\\systemsettingsthreshold\\handler"...
0x180191340  mov     r9d, ebx; char *
0x180191343  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180191348  mov     eax, ebx
0x18019134a  jmp     loc_1801916CB
0x18019134f  lea     rdx, stru_180317A08; HSTRING
0x180191356  mov     rcx, rbx; this
0x180191359  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18019135e  test    al, al
0x180191360  jz      short loc_180191382
0x180191362  mov     rcx, [r14+0F8h]; unsigned __int16 *
0x180191369  mov     rdx, r12; struct IInspectable **
0x18019136c  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180191371  mov     ebx, eax
0x180191373  test    eax, eax
0x180191375  jns     loc_1801916C9
0x18019137b  mov     edx, 0D7h
0x180191380  jmp     short loc_180191335
0x180191382  lea     rdx, stru_180317A28; HSTRING
0x180191389  mov     rcx, rbx; this
0x18019138c  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180191391  test    al, al
0x180191393  jz      short loc_1801913B5
0x180191395  mov     rcx, [r14+110h]; unsigned __int16 *
0x18019139c  mov     rdx, r12; struct IInspectable **
0x18019139f  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801913a4  mov     ebx, eax
0x1801913a6  test    eax, eax
0x1801913a8  jns     loc_1801916C9
0x1801913ae  mov     edx, 0DBh
0x1801913b3  jmp     short loc_180191335
0x1801913b5  lea     rdx, stru_180317A50; HSTRING
0x1801913bc  mov     rcx, rbx; this
0x1801913bf  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801913c4  test    al, al
0x1801913c6  jz      short loc_1801913EB
0x1801913c8  mov     ecx, [r14+12Ch]; unsigned int
0x1801913cf  mov     rdx, r12; struct IInspectable **
0x1801913d2  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x1801913d7  mov     ebx, eax
0x1801913d9  test    eax, eax
0x1801913db  jns     loc_1801916C9
0x1801913e1  mov     edx, 0DFh
0x1801913e6  jmp     loc_180191335
0x1801913eb  lea     rdx, stru_180317A78; HSTRING
0x1801913f2  mov     rcx, rbx; this
0x1801913f5  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801913fa  test    al, al
0x1801913fc  jz      short loc_180191421
0x1801913fe  mov     cl, [r14+128h]; unsigned __int8
0x180191405  mov     rdx, r12; struct IInspectable **
0x180191408  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18019140d  mov     ebx, eax
0x18019140f  test    eax, eax
0x180191411  jns     loc_1801916C9
0x180191417  mov     edx, 0E3h
0x18019141c  jmp     loc_180191335
0x180191421  lea     rdx, stru_180317AA0; HSTRING
0x180191428  mov     rcx, rbx; this
0x18019142b  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180191430  test    al, al
0x180191432  jz      loc_1801916C9
0x180191438  xor     ecx, ecx; string
0x18019143a  call    cs:__imp_WindowsDeleteString
0x180191441  nop     dword ptr [rax+rax+00h]
0x180191446  mov     rdx, [r14+130h]
0x18019144d  lea     r8, [rbp+arg_10]; HSTRING *
0x180191451  mov     rcx, [r14+0F8h]; unsigned __int16 *
0x180191458  mov     [rbp+arg_10], 0
0x180191460  mov     rdx, [rdx+40h]; struct Windows::ApplicationModel::Resources::Core::IResourceMap *
0x180191464  call    ?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z; GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)
0x180191469  mov     ebx, eax
0x18019146b  test    eax, eax
0x18019146d  jns     short loc_18019148C
0x18019146f  mov     rcx, [rbp+28h]; this
0x180191473  lea     r8, aShellSystemset_21; "shell\\systemsettingsthreshold\\handler"...
0x18019147a  mov     r9d, eax; char *
0x18019147d  mov     edx, 0E8h; void *
0x180191482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180191487  jmp     loc_180191635
0x18019148c  xor     ecx, ecx; string
0x18019148e  call    cs:__imp_WindowsDeleteString
0x180191495  nop     dword ptr [rax+rax+00h]
0x18019149a  mov     rdx, [r14+130h]
0x1801914a1  lea     r8, [rbp+string]; HSTRING *
0x1801914a5  lea     rcx, aSystemsettings_150; "SystemSettings_Personalize_Themes_Previ"...
0x1801914ac  mov     [rbp+string], 0
0x1801914b4  mov     rdx, [rdx+40h]; struct Windows::ApplicationModel::Resources::Core::IResourceMap *
0x1801914b8  call    ?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z; GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)
0x1801914bd  mov     ebx, eax
0x1801914bf  test    eax, eax
0x1801914c1  jns     short loc_1801914F0
0x1801914c3  mov     rcx, [rbp+28h]; this
0x1801914c7  lea     r8, aShellSystemset_21; "shell\\systemsettingsthreshold\\handler"...
0x1801914ce  mov     r9d, eax; char *
0x1801914d1  mov     edx, 0EAh; void *
0x1801914d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801914db  mov     rcx, [rbp+string]; string
0x1801914df  call    cs:__imp_WindowsDeleteString
0x1801914e6  nop     dword ptr [rax+rax+00h]
0x1801914eb  jmp     loc_180191635
0x1801914f0  cmp     byte ptr [r14+128h], 0
0x1801914f8  mov     [rbp+var_18], 0
0x180191500  mov     [rbp+var_10], 0
0x180191508  mov     [rbp+var_8], 0
0x180191510  jz      loc_18019164A
0x180191516  xor     ecx, ecx; string
0x180191518  call    cs:__imp_WindowsDeleteString
0x18019151f  nop     dword ptr [rax+rax+00h]
0x180191524  mov     edx, [r14+12Ch]; unsigned int
0x18019152b  lea     r8, [rbp+var_20]; HSTRING *
0x18019152f  mov     rcx, r14; this
0x180191532  mov     [rbp+var_20], 0
0x18019153a  call    ?GetColorName@ThemePreviewItem@Personalization@SystemSettings@@AEAAJKPEAPEAUHSTRING__@@@Z; SystemSettings::Personalization::ThemePreviewItem::GetColorName(ulong,HSTRING__ * *)
0x18019153f  mov     rsi, [rbp+var_20]
0x180191543  xor     edx, edx; length
0x180191545  mov     rcx, rsi; string
0x180191548  call    cs:__imp_WindowsGetStringRawBuffer
0x18019154f  nop     dword ptr [rax+rax+00h]
0x180191554  mov     rcx, [rbp+arg_10]; string
0x180191558  xor     edx, edx; length
0x18019155a  mov     r15, rax
0x18019155d  call    cs:__imp_WindowsGetStringRawBuffer
0x180191564  nop     dword ptr [rax+rax+00h]
0x180191569  mov     rbx, [rbp+string]
0x18019156d  xor     edx, edx; length
0x18019156f  mov     rcx, rbx; string
0x180191572  mov     r14, rax
0x180191575  call    cs:__imp_WindowsGetStringRawBuffer
0x18019157c  nop     dword ptr [rax+rax+00h]
0x180191581  mov     r9, r15
0x180191584  lea     rcx, [rbp+var_18]
0x180191588  mov     rdx, rax
0x18019158b  mov     r8, r14
0x18019158e  call    ?InitializeMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeMessage(ushort const *,...)
0x180191593  mov     r14d, eax
0x180191596  test    eax, eax
0x180191598  jns     short loc_1801915DE
0x18019159a  mov     rcx, [rbp+28h]; this
0x18019159e  lea     r8, aShellSystemset_21; "shell\\systemsettingsthreshold\\handler"...
0x1801915a5  mov     r9d, eax; char *
0x1801915a8  mov     edx, 0F1h; void *
0x1801915ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801915b2  mov     rcx, rsi; string
0x1801915b5  call    cs:__imp_WindowsDeleteString
0x1801915bc  nop     dword ptr [rax+rax+00h]
0x1801915c1  lea     rcx, [rbp+var_18]
0x1801915c5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801915ca  mov     rcx, rbx; string
0x1801915cd  call    cs:__imp_WindowsDeleteString
0x1801915d4  nop     dword ptr [rax+rax+00h]
0x1801915d9  mov     ebx, r14d
0x1801915dc  jmp     short loc_180191635
0x1801915de  mov     rcx, rsi; string
0x1801915e1  call    cs:__imp_WindowsDeleteString
0x1801915e8  nop     dword ptr [rax+rax+00h]
0x1801915ed  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x1801915f1  mov     rdx, r12; struct IInspectable **
0x1801915f4  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801915f9  mov     esi, eax
0x1801915fb  test    eax, eax
0x1801915fd  jns     loc_1801916A1
0x180191603  mov     edx, 0F8h; void *
0x180191608  mov     rcx, [rbp+28h]; this
0x18019160c  lea     r8, aShellSystemset_21; "shell\\systemsettingsthreshold\\handler"...
0x180191613  mov     r9d, esi; char *
0x180191616  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019161b  lea     rcx, [rbp+var_18]
0x18019161f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180191624  mov     rcx, rbx; string
0x180191627  call    cs:__imp_WindowsDeleteString
0x18019162e  nop     dword ptr [rax+rax+00h]
0x180191633  mov     ebx, esi
0x180191635  mov     rcx, [rbp+arg_10]; string
0x180191639  call    cs:__imp_WindowsDeleteString
0x180191640  nop     dword ptr [rax+rax+00h]
0x180191645  jmp     loc_180191348
0x18019164a  mov     rcx, [rbp+arg_10]; string
0x18019164e  xor     edx, edx; length
0x180191650  mov     r14, [r14+110h]
0x180191657  call    cs:__imp_WindowsGetStringRawBuffer
0x18019165e  nop     dword ptr [rax+rax+00h]
0x180191663  mov     rbx, [rbp+string]
0x180191667  xor     edx, edx; length
0x180191669  mov     rcx, rbx; string
0x18019166c  mov     rsi, rax
0x18019166f  call    cs:__imp_WindowsGetStringRawBuffer
0x180191676  nop     dword ptr [rax+rax+00h]
0x18019167b  mov     r9, r14
0x18019167e  lea     rcx, [rbp+var_18]
0x180191682  mov     rdx, rax
0x180191685  mov     r8, rsi
0x180191688  call    ?InitializeMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeMessage(ushort const *,...)
0x18019168d  mov     esi, eax
0x18019168f  test    eax, eax
0x180191691  jns     loc_1801915ED
0x180191697  mov     edx, 0F5h
0x18019169c  jmp     loc_180191608
0x1801916a1  lea     rcx, [rbp+var_18]
0x1801916a5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801916aa  mov     rcx, rbx; string
0x1801916ad  call    cs:__imp_WindowsDeleteString
0x1801916b4  nop     dword ptr [rax+rax+00h]
0x1801916b9  mov     rcx, [rbp+arg_10]; string
0x1801916bd  call    cs:__imp_WindowsDeleteString
0x1801916c4  nop     dword ptr [rax+rax+00h]
0x1801916c9  xor     eax, eax
0x1801916cb  mov     rbx, [rsp+40h+arg_0]
0x1801916d0  add     rsp, 40h
0x1801916d4  pop     r15
0x1801916d6  pop     r14
0x1801916d8  pop     r12
0x1801916da  pop     rsi
0x1801916db  pop     rbp
0x1801916dc  retn
```
