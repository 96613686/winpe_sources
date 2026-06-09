# SystemSettings::StorageSenseHandlers::CAppTileData::GetNamedValue(HSTRING__ *,IInspectable * *)

- ea: `0x1800a8734`
- end: `0x1800a894e`
- name: `?GetNamedValue@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `538`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppTileData *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180041bc0`

## callees

- `0x18000e6cc`
- `0x180019ff0`
- `0x18001f688`
- `0x18003dbc4`
- `0x1800a7f7c`
- `0x1800a8194`
- `0x1800a8734`
- `0x1800a8a88`
- `0x1800a8cb4`
- `0x1800ad168`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a876d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a87c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8854`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a88db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8936`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a876d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a87c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8854`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a88db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8936`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppTileData::GetNamedValue(
        SystemSettings::StorageSenseHandlers::CAppTileData *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  int LogoPath; // eax
  int LogoBackground; // ebx
  __int64 v9; // rdx
  const unsigned __int16 *v11; // r8
  __int64 v12; // rdx
  const unsigned __int16 *v13; // r8
  __int64 v14; // rdx
  int v15; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+20h]
  HSTRING string; // [rsp+60h] [rbp+38h] BYREF

  *a3 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180108C20, (const unsigned __int16 *)a3) )
  {
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    LogoPath = SystemSettings::StorageSenseHandlers::CAppTileData::GetLogoPath(this, &string);
    LogoBackground = LogoPath;
    if ( LogoPath < 0 )
    {
      v9 = 939;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
        (const char *)(unsigned int)LogoPath,
        v15);
      WindowsDeleteString(string);
      return (unsigned int)LogoBackground;
    }
    LogoPath = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
    LogoBackground = LogoPath;
    if ( LogoPath < 0 )
    {
      v9 = 940;
      goto LABEL_6;
    }
    goto LABEL_26;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180116D60, v6) )
  {
    LODWORD(string) = 0;
    LogoBackground = SystemSettings::StorageSenseHandlers::CAppTileData::GetLogoBackground(
                       this,
                       (unsigned int *)&string);
    if ( LogoBackground >= 0 )
    {
      LogoBackground = SystemSettings::DataModel::PropValueHelper::CreateUInt32((unsigned int)string, a3);
      if ( LogoBackground >= 0 )
        return 0;
      v12 = 946;
    }
    else
    {
      v12 = 945;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)LogoBackground,
      v15);
    return (unsigned int)LogoBackground;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180116F30, v11) )
  {
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    LogoPath = SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFamilyName(this, &string);
    LogoBackground = LogoPath;
    if ( LogoPath < 0 )
    {
      v9 = 951;
      goto LABEL_6;
    }
    LogoPath = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
    LogoBackground = LogoPath;
    if ( LogoPath < 0 )
    {
      v9 = 952;
      goto LABEL_6;
    }
    goto LABEL_26;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180116380, v13) )
  {
    LOBYTE(v14) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SettingsLogoLoader>::ReportUsage(
      &`wil::Feature<__WilFeatureTraits_Feature_SettingsLogoLoader>::GetImpl'::`2'::impl,
      v14);
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    LogoPath = SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFullName(this, &string);
    LogoBackground = LogoPath;
    if ( LogoPath < 0 )
    {
      v9 = 957;
      goto LABEL_6;
    }
    LogoPath = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
    LogoBackground = LogoPath;
    if ( LogoPath < 0 )
    {
      v9 = 958;
      goto LABEL_6;
    }
LABEL_26:
    WindowsDeleteString(string);
    return 0;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800a8734  push    rbp
0x1800a8736  push    rbx
0x1800a8737  push    rsi
0x1800a8738  push    rdi
0x1800a8739  mov     rbp, rsp
0x1800a873c  sub     rsp, 28h
0x1800a8740  mov     rdi, r8
0x1800a8743  mov     rbx, rdx
0x1800a8746  mov     rsi, rcx
0x1800a8749  mov     qword ptr [r8], 0
0x1800a8750  lea     rdx, stru_180108C20; HSTRING
0x1800a8757  mov     rcx, rbx; this
0x1800a875a  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800a875f  test    al, al
0x1800a8761  jz      short loc_1800A87D5
0x1800a8763  mov     [rbp+string], 0
0x1800a876b  xor     ecx, ecx; string
0x1800a876d  call    cs:__imp_WindowsDeleteString
0x1800a8773  mov     [rbp+string], 0
0x1800a877b  lea     rdx, [rbp+string]; HSTRING *
0x1800a877f  mov     rcx, rsi; this
0x1800a8782  call    ?GetLogoPath@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetLogoPath(HSTRING__ * *)
0x1800a8787  mov     ebx, eax
0x1800a8789  test    eax, eax
0x1800a878b  jns     short loc_1800A8794
0x1800a878d  mov     edx, 3ABh
0x1800a8792  jmp     short loc_1800A87AB
0x1800a8794  mov     rdx, rdi; struct IInspectable **
0x1800a8797  mov     rcx, [rbp+string]; HSTRING
0x1800a879b  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1800a87a0  mov     ebx, eax
0x1800a87a2  test    eax, eax
0x1800a87a4  jns     short loc_1800A87D0
0x1800a87a6  mov     edx, 3ACh; void *
0x1800a87ab  mov     r9d, eax; char *
0x1800a87ae  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a87b5  mov     rcx, [rbp+20h]; this
0x1800a87b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a87be  nop
0x1800a87bf  mov     rcx, [rbp+string]; string
0x1800a87c3  call    cs:__imp_WindowsDeleteString
0x1800a87c9  mov     eax, ebx
0x1800a87cb  jmp     loc_1800A8945
0x1800a87d0  jmp     loc_1800A8932
0x1800a87d5  lea     rdx, stru_180116D60; HSTRING
0x1800a87dc  mov     rcx, rbx; this
0x1800a87df  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800a87e4  test    al, al
0x1800a87e6  jz      short loc_1800A8837
0x1800a87e8  mov     dword ptr [rbp+string], 0
0x1800a87ef  lea     rdx, [rbp+string]; unsigned int *
0x1800a87f3  mov     rcx, rsi; this
0x1800a87f6  call    ?GetLogoBackground@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAI@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetLogoBackground(uint *)
0x1800a87fb  mov     ebx, eax
0x1800a87fd  test    eax, eax
0x1800a87ff  jns     short loc_1800A881B
0x1800a8801  mov     edx, 3B1h; void *
0x1800a8806  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a880d  mov     r9d, ebx; char *
0x1800a8810  mov     rcx, [rbp+20h]; this
0x1800a8814  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8819  jmp     short loc_1800A87C9
0x1800a881b  mov     rdx, rdi; struct IInspectable **
0x1800a881e  mov     ecx, dword ptr [rbp+string]; unsigned int
0x1800a8821  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x1800a8826  mov     ebx, eax
0x1800a8828  test    eax, eax
0x1800a882a  jns     loc_1800A893C
0x1800a8830  mov     edx, 3B2h
0x1800a8835  jmp     short loc_1800A8806
0x1800a8837  lea     rdx, stru_180116F30; HSTRING
0x1800a883e  mov     rcx, rbx; this
0x1800a8841  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800a8846  test    al, al
0x1800a8848  jz      short loc_1800A88B0
0x1800a884a  mov     [rbp+string], 0
0x1800a8852  xor     ecx, ecx; string
0x1800a8854  call    cs:__imp_WindowsDeleteString
0x1800a885a  mov     [rbp+string], 0
0x1800a8862  lea     rdx, [rbp+string]; HSTRING *
0x1800a8866  mov     rcx, rsi; this
0x1800a8869  call    ?GetPackageFamilyName@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFamilyName(HSTRING__ * *)
0x1800a886e  mov     ebx, eax
0x1800a8870  test    eax, eax
0x1800a8872  jns     short loc_1800A887B
0x1800a8874  mov     edx, 3B7h
0x1800a8879  jmp     short loc_1800A8892
0x1800a887b  mov     rdx, rdi; struct IInspectable **
0x1800a887e  mov     rcx, [rbp+string]; HSTRING
0x1800a8882  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1800a8887  mov     ebx, eax
0x1800a8889  test    eax, eax
0x1800a888b  jns     short loc_1800A88AB
0x1800a888d  mov     edx, 3B8h; void *
0x1800a8892  mov     r9d, eax; char *
0x1800a8895  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a889c  mov     rcx, [rbp+20h]; this
0x1800a88a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a88a5  nop
0x1800a88a6  jmp     loc_1800A87BF
0x1800a88ab  jmp     loc_1800A8932
0x1800a88b0  lea     rdx, stru_180116380; HSTRING
0x1800a88b7  mov     rcx, rbx; this
0x1800a88ba  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800a88bf  test    al, al
0x1800a88c1  jz      short loc_1800A8940
0x1800a88c3  mov     dl, 1
0x1800a88c5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SettingsLogoLoader@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SettingsLogoLoader@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SettingsLogoLoader> `wil::Feature<__WilFeatureTraits_Feature_SettingsLogoLoader>::GetImpl(void)'::`2'::impl
0x1800a88cc  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_SettingsLogoLoader@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SettingsLogoLoader>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800a88d1  mov     [rbp+string], 0
0x1800a88d9  xor     ecx, ecx; string
0x1800a88db  call    cs:__imp_WindowsDeleteString
0x1800a88e1  mov     [rbp+string], 0
0x1800a88e9  lea     rdx, [rbp+string]; HSTRING *
0x1800a88ed  mov     rcx, rsi; this
0x1800a88f0  call    ?GetPackageFullName@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFullName(HSTRING__ * *)
0x1800a88f5  mov     ebx, eax
0x1800a88f7  test    eax, eax
0x1800a88f9  jns     short loc_1800A8902
0x1800a88fb  mov     edx, 3BDh
0x1800a8900  jmp     short loc_1800A8919
0x1800a8902  mov     rdx, rdi; struct IInspectable **
0x1800a8905  mov     rcx, [rbp+string]; HSTRING
0x1800a8909  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1800a890e  mov     ebx, eax
0x1800a8910  test    eax, eax
0x1800a8912  jns     short loc_1800A8932
0x1800a8914  mov     edx, 3BEh; void *
0x1800a8919  mov     r9d, eax; char *
0x1800a891c  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a8923  mov     rcx, [rbp+20h]; this
0x1800a8927  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a892c  nop
0x1800a892d  jmp     loc_1800A87BF
0x1800a8932  mov     rcx, [rbp+string]; string
0x1800a8936  call    cs:__imp_WindowsDeleteString
0x1800a893c  xor     eax, eax
0x1800a893e  jmp     short loc_1800A8945
0x1800a8940  mov     eax, 80070057h
0x1800a8945  add     rsp, 28h
0x1800a8949  pop     rdi
0x1800a894a  pop     rsi
0x1800a894b  pop     rbx
0x1800a894c  pop     rbp
0x1800a894d  retn
```
