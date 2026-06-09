# SystemSettings::Personalization::ColorSetting_CustomColors::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x18012fc30`
- end: `0x18013013f`
- name: `?GetProperty@ColorSetting_CustomColors@Personalization@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `1295`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::ColorSetting_CustomColors *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x180020170`
- `0x1800201c4`
- `0x180020224`
- `0x180021398`
- `0x180032208`
- `0x180035680`
- `0x18004d1ac`
- `0x18012fc30`
- `0x1801337d4`
- `0x18019e468`
- `0x180262da0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012fdd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012fe38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012fe65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012fee3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012fff1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013005a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801300f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012fdd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012fe38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012fe65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012fee3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012fff1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013005a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801300f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::Personalization::ColorSetting_CustomColors::GetProperty(
        SystemSettings::Personalization::ColorSetting_CustomColors *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  int InitialColor; // ebx
  __int64 v8; // rdx
  const unsigned __int16 *v10; // r8
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r8
  HSTRING *v14; // r8
  int ResourceStringById; // eax
  unsigned int v16; // edi
  HSTRING v17; // rbx
  __int64 v18; // rdx
  HSTRING v19; // rcx
  const unsigned __int16 *v20; // r8
  HSTRING *v21; // r8
  const unsigned __int16 *v22; // r8
  HSTRING *v23; // r8
  const unsigned __int16 *v24; // r8
  const unsigned __int16 *v25; // r8
  int v26; // ecx
  int v27; // ecx
  HSTRING *v28; // r8
  int v29; // eax
  __int64 v30; // rdx
  HSTRING *v31; // r8
  int v32; // eax
  float *v33; // [rsp+20h] [rbp-50h]
  bool v34; // [rsp+20h] [rbp-50h]
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  float v36; // [rsp+38h] [rbp-38h] BYREF
  float v37; // [rsp+3Ch] [rbp-34h] BYREF
  unsigned int v38[8]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802F1BF0, (const unsigned __int16 *)a3) )
  {
    InitialColor = SystemSettings::Personalization::ColorSetting_CustomColors::_LoadInitialColor(this);
    if ( InitialColor < 0 )
    {
      v8 = 800;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\color.cpp",
        (const char *)(unsigned int)InitialColor,
        (int)v33);
      return (unsigned int)InitialColor;
    }
    InitialColor = SystemSettings::DataModel::PropValueHelper::CreateUInt32(*((_DWORD *)this + 63), a3);
    if ( InitialColor < 0 )
    {
      v8 = 801;
      goto LABEL_4;
    }
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802F1B98, v6) )
  {
    if ( *((_DWORD *)this + 63) == 195948557 )
    {
      InitialColor = SystemSettings::Personalization::ColorSetting_CustomColors::_LoadInitialColor(this);
      if ( InitialColor < 0 )
      {
        v8 = 807;
        goto LABEL_4;
      }
    }
    InitialColor = SystemSettings::DataModel::PropValueHelper::CreateUInt32(*((_DWORD *)this + 63), a3);
    if ( InitialColor < 0 )
    {
      v8 = 810;
      goto LABEL_4;
    }
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18030C848, v10) )
  {
    InitialColor = SystemSettings::DataModel::PropValueHelper::CreateUInt32(*((_DWORD *)this + 63), a3);
    if ( InitialColor < 0 )
    {
      v8 = 814;
      goto LABEL_4;
    }
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18030C6A0, v11) )
  {
    LODWORD(string) = 0;
    v37 = 0.0;
    v36 = 0.0;
    SystemSettings::Personalization::RGBtoHSL(
      (SystemSettings::Personalization *)*((unsigned int *)this + 63),
      (unsigned int)&string,
      &v37,
      &v36,
      v33);
    AccentColors::GetAccentVariants(*((_DWORD *)this + 63), *(float *)&string, v37, v36, v34, v38);
    InitialColor = SystemSettings::DataModel::PropValueHelper::CreateUInt32(v38[6], a3);
    if ( InitialColor < 0 )
    {
      v8 = 825;
      goto LABEL_4;
    }
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18030C6D0, v12) )
  {
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Personalize_Color_CustomColorDescription",
                           &string,
                           v14);
    v16 = ResourceStringById;
    v17 = string;
    if ( ResourceStringById < 0 )
    {
      v18 = 830;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\color.cpp",
        (const char *)(unsigned int)ResourceStringById,
        (int)v33);
LABEL_25:
      v19 = v17;
LABEL_26:
      WindowsDeleteString(v19);
      return v16;
    }
    ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
    v16 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      v18 = 831;
      goto LABEL_24;
    }
    goto LABEL_61;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18030C770, v13) )
  {
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Personalize_Color_CustomColorPreviewDescription",
                           &string,
                           v21);
    v16 = ResourceStringById;
    v17 = string;
    if ( ResourceStringById < 0 )
    {
      v18 = 836;
      goto LABEL_24;
    }
    ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
    v16 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      v18 = 837;
      goto LABEL_24;
    }
    goto LABEL_61;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18030C580, v20) )
  {
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Personalize_Color_CustomColorPreviewText",
                           &string,
                           v23);
    v16 = ResourceStringById;
    v17 = string;
    if ( ResourceStringById < 0 )
    {
      v18 = 842;
      goto LABEL_24;
    }
    ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
    v16 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      v18 = 843;
      goto LABEL_24;
    }
    goto LABEL_61;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18030C7E0, v22) )
  {
    InitialColor = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_DWORD *)this + 64) != 0, a3);
    if ( InitialColor < 0 )
    {
      v8 = 847;
      goto LABEL_4;
    }
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802F1B48, v24) )
  {
    InitialColor = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 248), a3);
    if ( InitialColor < 0 )
    {
      v8 = 851;
      goto LABEL_4;
    }
    return 0;
  }
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18030C810, v25) )
  {
    InitialColor = SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetProperty(
                     this,
                     a2,
                     a3);
    if ( InitialColor < 0 )
    {
      v8 = 874;
      goto LABEL_4;
    }
    return 0;
  }
  v17 = 0;
  v26 = *((_DWORD *)this + 64);
  if ( v26 )
  {
    v27 = v26 - 1;
    if ( v27 )
    {
      if ( v27 == 1 )
      {
        WindowsDeleteString(0);
        string = 0;
        v29 = SystemSettings::DataModel::GetResourceStringById(
                (SystemSettings::DataModel *)L"SystemSettings_Personalize_Color_CustomColorErrorDescription",
                &string,
                v28);
        v16 = v29;
        if ( v29 < 0 )
        {
          v30 = 867;
LABEL_52:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v30,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\color.cpp",
            (const char *)(unsigned int)v29,
            (int)v33);
          v17 = string;
          goto LABEL_25;
        }
        v17 = string;
        ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
        v16 = ResourceStringById;
        if ( ResourceStringById < 0 )
        {
          v18 = 868;
          goto LABEL_24;
        }
      }
    }
    else
    {
      WindowsDeleteString(0);
      string = 0;
      v29 = SystemSettings::DataModel::GetResourceStringById(
              (SystemSettings::DataModel *)L"SystemSettings_Personalize_Color_CustomColorLumErrorDescription",
              &string,
              v31);
      v16 = v29;
      if ( v29 < 0 )
      {
        v30 = 863;
        goto LABEL_52;
      }
      v17 = string;
      ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
      v16 = ResourceStringById;
      if ( ResourceStringById < 0 )
      {
        v18 = 864;
        goto LABEL_24;
      }
    }
  }
  else
  {
    v32 = SystemSettings::DataModel::PropValueHelper::CreateString(&LocaleName, a3);
    v16 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35C,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\color.cpp",
        (const char *)(unsigned int)v32,
        (int)v33);
      v19 = 0;
      goto LABEL_26;
    }
  }
LABEL_61:
  WindowsDeleteString(v17);
  return 0;
}

```

## disassembly

```asm
0x18012fc30  mov     [rsp-18h+arg_18], rbx
0x18012fc35  push    rbp
0x18012fc36  push    rsi
0x18012fc37  push    rdi
0x18012fc38  mov     rbp, rsp
0x18012fc3b  sub     rsp, 70h
0x18012fc3f  mov     rax, cs:__security_cookie
0x18012fc46  xor     rax, rsp
0x18012fc49  mov     [rbp+var_10], rax
0x18012fc4d  mov     rsi, r8
0x18012fc50  mov     rbx, rdx
0x18012fc53  mov     rdi, rcx
0x18012fc56  lea     rdx, stru_1802F1BF0; HSTRING
0x18012fc5d  mov     rcx, rbx; this
0x18012fc60  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18012fc65  test    al, al
0x18012fc67  jz      short loc_18012FCB5
0x18012fc69  mov     rcx, rdi; this
0x18012fc6c  call    ?_LoadInitialColor@ColorSetting_CustomColors@Personalization@SystemSettings@@AEAAJXZ; SystemSettings::Personalization::ColorSetting_CustomColors::_LoadInitialColor(void)
0x18012fc71  mov     ebx, eax
0x18012fc73  test    eax, eax
0x18012fc75  jns     short loc_18012FC96
0x18012fc77  mov     edx, 320h; void *
0x18012fc7c  mov     rcx, [rbp+18h]; this
0x18012fc80  mov     r9d, ebx; char *
0x18012fc83  lea     r8, aShellSystemset_33; "shell\\systemsettingsthreshold\\handler"...
0x18012fc8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012fc8f  mov     eax, ebx
0x18012fc91  jmp     loc_180130104
0x18012fc96  mov     rdx, rsi; struct IInspectable **
0x18012fc99  mov     ecx, [rdi+0FCh]; unsigned int
0x18012fc9f  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x18012fca4  mov     ebx, eax
0x18012fca6  test    eax, eax
0x18012fca8  jns     loc_180130102
0x18012fcae  mov     edx, 321h
0x18012fcb3  jmp     short loc_18012FC7C
0x18012fcb5  lea     rdx, stru_1802F1B98; HSTRING
0x18012fcbc  mov     rcx, rbx; this
0x18012fcbf  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18012fcc4  test    al, al
0x18012fcc6  jz      short loc_18012FD0B
0x18012fcc8  cmp     dword ptr [rdi+0FCh], 0BADF00Dh
0x18012fcd2  jnz     short loc_18012FCE9
0x18012fcd4  mov     rcx, rdi; this
0x18012fcd7  call    ?_LoadInitialColor@ColorSetting_CustomColors@Personalization@SystemSettings@@AEAAJXZ; SystemSettings::Personalization::ColorSetting_CustomColors::_LoadInitialColor(void)
0x18012fcdc  mov     ebx, eax
0x18012fcde  test    eax, eax
0x18012fce0  jns     short loc_18012FCE9
0x18012fce2  mov     edx, 327h
0x18012fce7  jmp     short loc_18012FC7C
0x18012fce9  mov     rdx, rsi; struct IInspectable **
0x18012fcec  mov     ecx, [rdi+0FCh]; unsigned int
0x18012fcf2  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x18012fcf7  mov     ebx, eax
0x18012fcf9  test    eax, eax
0x18012fcfb  jns     loc_180130102
0x18012fd01  mov     edx, 32Ah
0x18012fd06  jmp     loc_18012FC7C
0x18012fd0b  lea     rdx, stru_18030C848; HSTRING
0x18012fd12  mov     rcx, rbx; this
0x18012fd15  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18012fd1a  test    al, al
0x18012fd1c  jz      short loc_18012FD40
0x18012fd1e  mov     rdx, rsi; struct IInspectable **
0x18012fd21  mov     ecx, [rdi+0FCh]; unsigned int
0x18012fd27  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x18012fd2c  mov     ebx, eax
0x18012fd2e  test    eax, eax
0x18012fd30  jns     loc_180130102
0x18012fd36  mov     edx, 32Eh
0x18012fd3b  jmp     loc_18012FC7C
0x18012fd40  lea     rdx, stru_18030C6A0; HSTRING
0x18012fd47  mov     rcx, rbx; this
0x18012fd4a  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18012fd4f  test    al, al
0x18012fd51  jz      short loc_18012FDC1
0x18012fd53  mov     dword ptr [rbp+string], 0
0x18012fd5a  mov     [rbp+var_34], 0
0x18012fd61  mov     [rbp+var_38], 0
0x18012fd68  lea     r9, [rbp+var_38]; float *
0x18012fd6c  lea     r8, [rbp+var_34]; float *
0x18012fd70  lea     rdx, [rbp+string]; unsigned int
0x18012fd74  mov     ecx, [rdi+0FCh]; this
0x18012fd7a  call    ?RGBtoHSL@Personalization@SystemSettings@@YAXKPEAM00@Z; SystemSettings::Personalization::RGBtoHSL(ulong,float *,float *,float *)
0x18012fd7f  lea     rcx, [rbp+var_30]
0x18012fd83  mov     [rsp+70h+var_48], rcx; unsigned int *
0x18012fd88  movss   xmm3, [rbp+var_38]; float
0x18012fd8d  movss   xmm2, [rbp+var_34]; float
0x18012fd92  movss   xmm1, dword ptr [rbp+string]; float
0x18012fd97  mov     ecx, [rdi+0FCh]; unsigned int
0x18012fd9d  call    ?GetAccentVariants@AccentColors@@SAXKMMM_NQEAK@Z; AccentColors::GetAccentVariants(ulong,float,float,float,bool,ulong * const)
0x18012fda2  mov     rdx, rsi; struct IInspectable **
0x18012fda5  mov     ecx, [rbp+var_18]; unsigned int
0x18012fda8  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x18012fdad  mov     ebx, eax
0x18012fdaf  test    eax, eax
0x18012fdb1  jns     loc_180130102
0x18012fdb7  mov     edx, 339h
0x18012fdbc  jmp     loc_18012FC7C
0x18012fdc1  lea     rdx, stru_18030C6D0; HSTRING
0x18012fdc8  mov     rcx, rbx; this
0x18012fdcb  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18012fdd0  test    al, al
0x18012fdd2  jz      short loc_18012FE50
0x18012fdd4  xor     ecx, ecx; string
0x18012fdd6  call    cs:__imp_WindowsDeleteString
0x18012fddd  nop     dword ptr [rax+rax+00h]
0x18012fde2  mov     [rbp+string], 0
0x18012fdea  lea     rdx, [rbp+string]; HSTRING *
0x18012fdee  lea     rcx, aSystemsettings_69; "SystemSettings_Personalize_Color_Custom"...
0x18012fdf5  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18012fdfa  mov     edi, eax
0x18012fdfc  mov     rbx, [rbp+string]
0x18012fe00  test    eax, eax
0x18012fe02  jns     short loc_18012FE0B
0x18012fe04  mov     edx, 33Eh
0x18012fe09  jmp     short loc_18012FE21
0x18012fe0b  mov     rdx, rsi; struct IInspectable **
0x18012fe0e  mov     rcx, rbx; HSTRING
0x18012fe11  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18012fe16  mov     edi, eax
0x18012fe18  test    eax, eax
0x18012fe1a  jns     short loc_18012FE4B
0x18012fe1c  mov     edx, 33Fh; void *
0x18012fe21  mov     r9d, eax; char *
0x18012fe24  lea     r8, aShellSystemset_33; "shell\\systemsettingsthreshold\\handler"...
0x18012fe2b  mov     rcx, [rbp+18h]; this
0x18012fe2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012fe34  nop
0x18012fe35  mov     rcx, rbx; string
0x18012fe38  call    cs:__imp_WindowsDeleteString
0x18012fe3f  nop     dword ptr [rax+rax+00h]
0x18012fe44  mov     eax, edi
0x18012fe46  jmp     loc_180130104
0x18012fe4b  jmp     loc_1801300F3
0x18012fe50  lea     rdx, stru_18030C770; HSTRING
0x18012fe57  mov     rcx, rbx; this
0x18012fe5a  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18012fe5f  test    al, al
0x18012fe61  jz      short loc_18012FECE
0x18012fe63  xor     ecx, ecx; string
0x18012fe65  call    cs:__imp_WindowsDeleteString
0x18012fe6c  nop     dword ptr [rax+rax+00h]
0x18012fe71  mov     [rbp+string], 0
0x18012fe79  lea     rdx, [rbp+string]; HSTRING *
0x18012fe7d  lea     rcx, aSystemsettings_1370; "SystemSettings_Personalize_Color_Custom"...
0x18012fe84  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18012fe89  mov     edi, eax
0x18012fe8b  mov     rbx, [rbp+string]
0x18012fe8f  test    eax, eax
0x18012fe91  jns     short loc_18012FE9A
0x18012fe93  mov     edx, 344h
0x18012fe98  jmp     short loc_18012FEB0
0x18012fe9a  mov     rdx, rsi; struct IInspectable **
0x18012fe9d  mov     rcx, rbx; HSTRING
0x18012fea0  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18012fea5  mov     edi, eax
0x18012fea7  test    eax, eax
0x18012fea9  jns     short loc_18012FEC9
0x18012feab  mov     edx, 345h; void *
0x18012feb0  mov     r9d, eax; char *
0x18012feb3  lea     r8, aShellSystemset_33; "shell\\systemsettingsthreshold\\handler"...
0x18012feba  mov     rcx, [rbp+18h]; this
0x18012febe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012fec3  nop
0x18012fec4  jmp     loc_18012FE35
0x18012fec9  jmp     loc_1801300F3
0x18012fece  lea     rdx, stru_18030C580; HSTRING
0x18012fed5  mov     rcx, rbx; this
0x18012fed8  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18012fedd  test    al, al
0x18012fedf  jz      short loc_18012FF4C
0x18012fee1  xor     ecx, ecx; string
0x18012fee3  call    cs:__imp_WindowsDeleteString
0x18012feea  nop     dword ptr [rax+rax+00h]
0x18012feef  mov     [rbp+string], 0
0x18012fef7  lea     rdx, [rbp+string]; HSTRING *
0x18012fefb  lea     rcx, aSystemsettings_481; "SystemSettings_Personalize_Color_Custom"...
0x18012ff02  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18012ff07  mov     edi, eax
0x18012ff09  mov     rbx, [rbp+string]
0x18012ff0d  test    eax, eax
0x18012ff0f  jns     short loc_18012FF18
0x18012ff11  mov     edx, 34Ah
0x18012ff16  jmp     short loc_18012FF2E
0x18012ff18  mov     rdx, rsi; struct IInspectable **
0x18012ff1b  mov     rcx, rbx; HSTRING
0x18012ff1e  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18012ff23  mov     edi, eax
0x18012ff25  test    eax, eax
0x18012ff27  jns     short loc_18012FF47
0x18012ff29  mov     edx, 34Bh; void *
0x18012ff2e  mov     r9d, eax; char *
0x18012ff31  lea     r8, aShellSystemset_33; "shell\\systemsettingsthreshold\\handler"...
0x18012ff38  mov     rcx, [rbp+18h]; this
0x18012ff3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012ff41  nop
0x18012ff42  jmp     loc_18012FE35
0x18012ff47  jmp     loc_1801300F3
0x18012ff4c  lea     rdx, stru_18030C7E0; HSTRING
0x18012ff53  mov     rcx, rbx; this
0x18012ff56  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18012ff5b  test    al, al
0x18012ff5d  jz      short loc_18012FF85
0x18012ff5f  cmp     dword ptr [rdi+100h], 0
0x18012ff66  setnz   cl; unsigned __int8
0x18012ff69  mov     rdx, rsi; struct IInspectable **
0x18012ff6c  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18012ff71  mov     ebx, eax
0x18012ff73  test    eax, eax
0x18012ff75  jns     loc_180130102
0x18012ff7b  mov     edx, 34Fh
0x18012ff80  jmp     loc_18012FC7C
0x18012ff85  lea     rdx, stru_1802F1B48; HSTRING
0x18012ff8c  mov     rcx, rbx; this
0x18012ff8f  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18012ff94  test    al, al
0x18012ff96  jz      short loc_18012FFBA
0x18012ff98  mov     rdx, rsi; struct IInspectable **
0x18012ff9b  mov     cl, [rdi+0F8h]; unsigned __int8
0x18012ffa1  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18012ffa6  mov     ebx, eax
0x18012ffa8  test    eax, eax
0x18012ffaa  jns     loc_180130102
0x18012ffb0  mov     edx, 353h
0x18012ffb5  jmp     loc_18012FC7C
0x18012ffba  lea     rdx, stru_18030C810; HSTRING
0x18012ffc1  mov     rcx, rbx; this
0x18012ffc4  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18012ffc9  test    al, al
0x18012ffcb  jz      loc_180130121
0x18012ffd1  xor     ebx, ebx
0x18012ffd3  mov     ecx, [rdi+100h]
0x18012ffd9  test    ecx, ecx
0x18012ffdb  jz      loc_1801300BE
0x18012ffe1  sub     ecx, 1
0x18012ffe4  jz      short loc_180130058
0x18012ffe6  cmp     ecx, 1
0x18012ffe9  jnz     loc_1801300F3
0x18012ffef  xor     ecx, ecx; string
0x18012fff1  call    cs:__imp_WindowsDeleteString
0x18012fff8  nop     dword ptr [rax+rax+00h]
0x18012fffd  mov     [rbp+string], rbx
0x180130001  lea     rdx, [rbp+string]; HSTRING *
0x180130005  lea     rcx, aSystemsettings_1439; "SystemSettings_Personalize_Color_Custom"...
0x18013000c  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180130011  mov     edi, eax
0x180130013  test    eax, eax
0x180130015  jns     short loc_180130038
0x180130017  mov     edx, 363h; void *
0x18013001c  lea     r8, aShellSystemset_33; "shell\\systemsettingsthreshold\\handler"...
0x180130023  mov     r9d, eax; char *
0x180130026  mov     rcx, [rbp+18h]; this
0x18013002a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013002f  mov     rbx, [rbp+string]
0x180130033  jmp     loc_1801300B9
0x180130038  mov     rdx, rsi; struct IInspectable **
0x18013003b  mov     rbx, [rbp+string]
0x18013003f  mov     rcx, rbx; HSTRING
0x180130042  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180130047  mov     edi, eax
0x180130049  test    eax, eax
0x18013004b  jns     loc_1801300F3
0x180130051  mov     edx, 364h
0x180130056  jmp     short loc_1801300A5
0x180130058  xor     ecx, ecx; string
0x18013005a  call    cs:__imp_WindowsDeleteString
0x180130061  nop     dword ptr [rax+rax+00h]
0x180130066  mov     [rbp+string], 0
0x18013006e  lea     rdx, [rbp+string]; HSTRING *
0x180130072  lea     rcx, aSystemsettings_1201; "SystemSettings_Personalize_Color_Custom"...
0x180130079  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18013007e  mov     edi, eax
0x180130080  test    eax, eax
0x180130082  jns     short loc_18013008B
0x180130084  mov     edx, 35Fh
0x180130089  jmp     short loc_18013001C
0x18013008b  mov     rdx, rsi; struct IInspectable **
0x18013008e  mov     rbx, [rbp+string]
0x180130092  mov     rcx, rbx; HSTRING
0x180130095  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18013009a  mov     edi, eax
0x18013009c  test    eax, eax
0x18013009e  jns     short loc_1801300F3
0x1801300a0  mov     edx, 360h; void *
0x1801300a5  mov     r9d, eax; char *
0x1801300a8  lea     r8, aShellSystemset_33; "shell\\systemsettingsthreshold\\handler"...
0x1801300af  mov     rcx, [rbp+18h]; this
0x1801300b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801300b8  nop
0x1801300b9  jmp     loc_18012FE35
0x1801300be  mov     rdx, rsi; struct IInspectable **
0x1801300c1  lea     rcx, LocaleName; unsigned __int16 *
0x1801300c8  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801300cd  mov     edi, eax
0x1801300cf  test    eax, eax
0x1801300d1  jns     short loc_1801300F3
0x1801300d3  mov     rcx, [rbp+18h]; this
0x1801300d7  mov     r9d, eax; char *
  ... truncated ...
```
