# SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x18001fd70`
- end: `0x18001fee7`
- name: `?GetProperty@CBatterySaverDynamicResolution@BatterySaverOneCoreDataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `375`
- prototype: `int(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000eacc`
- `0x18001c908`
- `0x18001d140`
- `0x18001e7f4`
- `0x18001fd70`
- `0x180020c50`
- `0x180023fb0`
- `0x1800280c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001febf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fecf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001febf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fecf`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::GetProperty(
        SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution *v6; // rcx
  const unsigned __int16 *v7; // r8
  int SupportedResolutionsList; // ebx
  __int64 v9; // rdx
  SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution *v11; // rcx
  const unsigned __int16 *v12; // r8
  __int64 v13; // rdx
  const unsigned __int16 *v14; // r8
  int v15; // eax
  __int64 v16; // rdx
  HSTRING v17; // rcx
  int v18; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180056A88, (const unsigned __int16 *)a3) )
  {
    SupportedResolutionsList = SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::GetSupportedResolutionsList(
                                 v6,
                                 a3);
    if ( SupportedResolutionsList < 0 )
    {
      v9 = 3342;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\batterysaver.cpp",
        (const char *)(unsigned int)SupportedResolutionsList,
        v18);
      return (unsigned int)SupportedResolutionsList;
    }
  }
  else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180056AA0, v7) )
  {
    v13 = *((_QWORD *)this + 28);
    if ( v13 )
    {
      SupportedResolutionsList = SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::GetDisplayTextForResolution(
                                   v11,
                                   *(const unsigned __int16 **)(v13 + 8),
                                   a3);
      if ( SupportedResolutionsList < 0 )
      {
        v9 = 3350;
        goto LABEL_4;
      }
    }
  }
  else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180056AC8, v12) )
  {
    SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 232) == 0, a3);
    *((_BYTE *)this + 232) = 0;
  }
  else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180056AF0, v14) )
  {
    string = 0;
    v15 = Microsoft::WRL::Wrappers::HString::Set(
            (Microsoft::WRL::Wrappers::HString *)&string,
            L"SystemSettings_BatterySaver_LandingPage_DynamicResolution_Note",
            0x3Eu);
    SupportedResolutionsList = v15;
    if ( v15 >= 0 )
    {
      v17 = string;
      string = 0;
      v15 = SystemSettings::DataModel::PropValueHelper::CreateString(v17, a3);
      SupportedResolutionsList = v15;
      if ( v15 >= 0 )
      {
        WindowsDeleteString(string);
        return 0;
      }
      v16 = 3366;
    }
    else
    {
      v16 = 3365;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\batterysaver.cpp",
      (const char *)(unsigned int)v15,
      v18);
    WindowsDeleteString(string);
    return (unsigned int)SupportedResolutionsList;
  }
  return 0;
}

```

## disassembly

```asm
0x18001fd70  mov     [rsp+arg_0], rbx
0x18001fd75  mov     [rsp+arg_8], rsi
0x18001fd7a  push    rdi; int
0x18001fd7b  sub     rsp, 20h
0x18001fd7f  mov     rsi, rdx
0x18001fd82  mov     qword ptr [r8], 0
0x18001fd89  mov     rbx, rcx
0x18001fd8c  lea     rdx, stru_180056A88; HSTRING
0x18001fd93  mov     rcx, rsi; this
0x18001fd96  mov     rdi, r8
0x18001fd99  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18001fd9e  test    al, al
0x18001fda0  jz      short loc_18001FDD4
0x18001fda2  mov     rdx, rdi; struct IInspectable **
0x18001fda5  call    ?GetSupportedResolutionsList@CBatterySaverDynamicResolution@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJPEAPEAUIInspectable@@@Z; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::GetSupportedResolutionsList(IInspectable * *)
0x18001fdaa  mov     ebx, eax
0x18001fdac  test    eax, eax
0x18001fdae  jns     loc_18001FED5
0x18001fdb4  mov     edx, 0D0Eh; void *
0x18001fdb9  mov     rcx, [rsp+28h]; this
0x18001fdbe  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x18001fdc5  mov     r9d, ebx; char *
0x18001fdc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fdcd  mov     eax, ebx
0x18001fdcf  jmp     loc_18001FED7
0x18001fdd4  lea     rdx, stru_180056AA0; HSTRING
0x18001fddb  mov     rcx, rsi; this
0x18001fdde  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18001fde3  test    al, al
0x18001fde5  jz      short loc_18001FE14
0x18001fde7  mov     rdx, [rbx+0E0h]
0x18001fdee  test    rdx, rdx
0x18001fdf1  jz      loc_18001FED5
0x18001fdf7  mov     rdx, [rdx+8]; unsigned __int16 *
0x18001fdfb  mov     r8, rdi; struct IInspectable **
0x18001fdfe  call    ?GetDisplayTextForResolution@CBatterySaverDynamicResolution@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::GetDisplayTextForResolution(ushort const *,IInspectable * *)
0x18001fe03  mov     ebx, eax
0x18001fe05  test    eax, eax
0x18001fe07  jns     loc_18001FED5
0x18001fe0d  mov     edx, 0D16h
0x18001fe12  jmp     short loc_18001FDB9
0x18001fe14  lea     rdx, stru_180056AC8; HSTRING
0x18001fe1b  mov     rcx, rsi; this
0x18001fe1e  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18001fe23  test    al, al
0x18001fe25  jz      short loc_18001FE45
0x18001fe27  cmp     byte ptr [rbx+0E8h], 0
0x18001fe2e  mov     rdx, rdi; struct IInspectable **
0x18001fe31  setz    cl; unsigned __int8
0x18001fe34  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18001fe39  mov     byte ptr [rbx+0E8h], 0
0x18001fe40  jmp     loc_18001FED5
0x18001fe45  lea     rdx, stru_180056AF0; HSTRING
0x18001fe4c  mov     rcx, rsi; this
0x18001fe4f  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18001fe54  test    al, al
0x18001fe56  jz      short loc_18001FED5
0x18001fe58  mov     r8d, 3Eh ; '>'; unsigned int
0x18001fe5e  mov     [rsp+28h+string], 0
0x18001fe67  lea     rdx, aSystemsettings_14; "SystemSettings_BatterySaver_LandingPage"...
0x18001fe6e  lea     rcx, [rsp+28h+string]; this
0x18001fe73  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18001fe78  mov     ebx, eax
0x18001fe7a  test    eax, eax
0x18001fe7c  jns     short loc_18001FE85
0x18001fe7e  mov     edx, 0D25h
0x18001fe83  jmp     short loc_18001FEA6
0x18001fe85  mov     rcx, [rsp+28h+string]; HSTRING
0x18001fe8a  mov     rdx, rdi; struct IInspectable **
0x18001fe8d  mov     [rsp+28h+string], 0
0x18001fe96  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18001fe9b  mov     ebx, eax
0x18001fe9d  test    eax, eax
0x18001fe9f  jns     short loc_18001FECA
0x18001fea1  mov     edx, 0D26h; void *
0x18001fea6  mov     rcx, [rsp+28h]; this
0x18001feab  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x18001feb2  mov     r9d, eax; char *
0x18001feb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001feba  mov     rcx, [rsp+28h+string]; string
0x18001febf  call    cs:__imp_WindowsDeleteString
0x18001fec5  jmp     loc_18001FDCD
0x18001feca  mov     rcx, [rsp+28h+string]; string
0x18001fecf  call    cs:__imp_WindowsDeleteString
0x18001fed5  xor     eax, eax
0x18001fed7  mov     rbx, [rsp+28h+arg_0]
0x18001fedc  mov     rsi, [rsp+28h+arg_8]
0x18001fee1  add     rsp, 20h
0x18001fee5  pop     rdi
0x18001fee6  retn
```
