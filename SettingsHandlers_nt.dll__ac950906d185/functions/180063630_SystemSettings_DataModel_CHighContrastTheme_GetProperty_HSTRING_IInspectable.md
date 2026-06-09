# SystemSettings::DataModel::CHighContrastTheme::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x180063630`
- end: `0x18006393d`
- name: `?GetProperty@CHighContrastTheme@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `781`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CHighContrastTheme *__hidden this, HSTRING string, struct IInspectable **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180011bb0`
- `0x1800201c4`
- `0x180020224`
- `0x180025884`
- `0x180032208`
- `0x180062dfc`
- `0x180063630`
- `0x180065e94`
- `0x18006610c`
- `0x180066200`
- `0x180066350`
- `0x1800668f4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063681`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800636af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800636e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063711`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063743`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063772`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800637a3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800637e1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063842`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800638a1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063681`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800636af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800636e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063711`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063743`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063772`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800637a3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800637e1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063842`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800638a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063655`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063655`

## string_xrefs

- `0x180063895`: `DeleteAction`
- `0x180063797`: `CanDelete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CHighContrastTheme::GetProperty(
        SystemSettings::DataModel::CHighContrastTheme *this,
        HSTRING string,
        struct IInspectable **a3)
{
  const WCHAR *StringRawBuffer; // r14
  const unsigned __int16 *v6; // rcx
  bool IsModified; // al
  unsigned __int8 v9; // cl
  int SureThemeLoaded; // ebx
  SystemSettings::DataModel::CHighContrastTheme *v11; // rcx
  int HCColorIndex; // eax
  __int64 v14; // [rsp+80h] [rbp+48h] BYREF

  *a3 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"HighContrastName", -1, 1) != 2 )
  {
    if ( CompareStringOrdinal(StringRawBuffer, -1, L"HighContrastId", -1, 1) == 2 )
    {
      v6 = (const unsigned __int16 *)*((_QWORD *)this + 32);
      return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateString(v6, a3);
    }
    if ( CompareStringOrdinal(StringRawBuffer, -1, L"IsCustomTheme", -1, 1) != 2 )
    {
      if ( CompareStringOrdinal(StringRawBuffer, -1, L"IsModified", -1, 1) == 2 )
      {
        IsModified = SystemSettings::DataModel::CHighContrastTheme::_IsModified(this);
LABEL_15:
        v9 = IsModified;
        return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateBoolean(v9, a3);
      }
      if ( CompareStringOrdinal(StringRawBuffer, -1, L"CanApply", -1, 1) == 2 )
      {
        IsModified = SystemSettings::DataModel::CHighContrastTheme::_CanApply(this);
        goto LABEL_15;
      }
      if ( CompareStringOrdinal(StringRawBuffer, -1, L"CanEdit", -1, 1) == 2 )
      {
        v9 = *((_DWORD *)this + 62) != 0;
        return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateBoolean(v9, a3);
      }
      if ( CompareStringOrdinal(StringRawBuffer, -1, L"CanDelete", -1, 1) != 2 )
      {
        if ( CompareStringOrdinal(StringRawBuffer, -1, L"ApplyAction", -1, 1) == 2 )
        {
          v14 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
          SureThemeLoaded = SystemSettings::DataModel::CHighContrastThemeAction::CreateInstance(
                              *((_QWORD *)this + 32),
                              0,
                              &v14);
          if ( SureThemeLoaded >= 0 )
            SureThemeLoaded = Microsoft::WRL::ComPtr<SystemSettings::Personalization::TextInput_CustomTheme_BackgroundPicture_ChoosePicture_Browse>::CopyTo<IInspectable>(
                                &v14,
                                a3);
        }
        else if ( CompareStringOrdinal(StringRawBuffer, -1, L"CancelAction", -1, 1) == 2 )
        {
          v14 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
          SureThemeLoaded = SystemSettings::DataModel::CHighContrastThemeAction::CreateInstance(
                              *((_QWORD *)this + 32),
                              1,
                              &v14);
          if ( SureThemeLoaded >= 0 )
            SureThemeLoaded = Microsoft::WRL::ComPtr<SystemSettings::Personalization::TextInput_CustomTheme_BackgroundPicture_ChoosePicture_Browse>::CopyTo<IInspectable>(
                                &v14,
                                a3);
        }
        else
        {
          if ( CompareStringOrdinal(StringRawBuffer, -1, L"DeleteAction", -1, 1) != 2 )
          {
            SureThemeLoaded = SystemSettings::DataModel::CHighContrastTheme::_MakeSureThemeLoaded(this);
            if ( SureThemeLoaded < 0 )
              return (unsigned int)SureThemeLoaded;
            HCColorIndex = SystemSettings::DataModel::CHighContrastTheme::_GetHCColorIndex(v11, StringRawBuffer);
            if ( HCColorIndex < 0 )
              return (unsigned int)-2147024809;
            return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateUInt32(
                                   *((_DWORD *)this + 2 * HCColorIndex + 70),
                                   a3);
          }
          v14 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
          SureThemeLoaded = SystemSettings::DataModel::CHighContrastThemeAction::CreateInstance(
                              *((_QWORD *)this + 32),
                              2,
                              &v14);
          if ( SureThemeLoaded >= 0 )
            SureThemeLoaded = Microsoft::WRL::ComPtr<SystemSettings::Personalization::TextInput_CustomTheme_BackgroundPicture_ChoosePicture_Browse>::CopyTo<IInspectable>(
                                &v14,
                                a3);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
        return (unsigned int)SureThemeLoaded;
      }
    }
    IsModified = SystemSettings::DataModel::CHighContrastTheme::_IsCustomTheme(this);
    goto LABEL_15;
  }
  v6 = (const unsigned __int16 *)*((_QWORD *)this + 33);
  return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateString(v6, a3);
}

```

## disassembly

```asm
0x180063630  push    rbp
0x180063632  push    rbx
0x180063633  push    rsi
0x180063634  push    rdi
0x180063635  push    r12
0x180063637  push    r14
0x180063639  mov     rbp, rsp
0x18006363c  sub     rsp, 38h
0x180063640  mov     rsi, r8
0x180063643  mov     rax, rdx
0x180063646  mov     rdi, rcx
0x180063649  mov     qword ptr [r8], 0
0x180063650  xor     edx, edx; length
0x180063652  mov     rcx, rax; string
0x180063655  call    cs:__imp_WindowsGetStringRawBuffer
0x18006365c  nop     dword ptr [rax+rax+00h]
0x180063661  mov     r14, rax
0x180063664  mov     r12d, 1
0x18006366a  mov     [rsp+38h+bIgnoreCase], r12d; bIgnoreCase
0x18006366f  or      ebx, 0FFFFFFFFh
0x180063672  mov     r9d, ebx; cchCount2
0x180063675  lea     r8, aHighcontrastna; "HighContrastName"
0x18006367c  mov     edx, ebx; cchCount1
0x18006367e  mov     rcx, rax; lpString1
0x180063681  call    cs:__imp_CompareStringOrdinal
0x180063688  nop     dword ptr [rax+rax+00h]
0x18006368d  cmp     eax, 2
0x180063690  jnz     short loc_18006369B
0x180063692  mov     rcx, [rdi+108h]
0x180063699  jmp     short loc_1800636C7
0x18006369b  mov     [rsp+38h+bIgnoreCase], r12d; bIgnoreCase
0x1800636a0  mov     r9d, ebx; cchCount2
0x1800636a3  lea     r8, aHighcontrastid; "HighContrastId"
0x1800636aa  mov     edx, ebx; cchCount1
0x1800636ac  mov     rcx, r14; lpString1
0x1800636af  call    cs:__imp_CompareStringOrdinal
0x1800636b6  nop     dword ptr [rax+rax+00h]
0x1800636bb  cmp     eax, 2
0x1800636be  jnz     short loc_1800636D4
0x1800636c0  mov     rcx, [rdi+100h]; unsigned __int16 *
0x1800636c7  mov     rdx, rsi; struct IInspectable **
0x1800636ca  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1800636cf  jmp     loc_1800637C6
0x1800636d4  mov     [rsp+38h+bIgnoreCase], r12d; bIgnoreCase
0x1800636d9  mov     r9d, ebx; cchCount2
0x1800636dc  lea     r8, aIscustomtheme; "IsCustomTheme"
0x1800636e3  mov     edx, ebx; cchCount1
0x1800636e5  mov     rcx, r14; lpString1
0x1800636e8  call    cs:__imp_CompareStringOrdinal
0x1800636ef  nop     dword ptr [rax+rax+00h]
0x1800636f4  cmp     eax, 2
0x1800636f7  jz      loc_1800637B4
0x1800636fd  mov     [rsp+38h+bIgnoreCase], r12d; bIgnoreCase
0x180063702  mov     r9d, ebx; cchCount2
0x180063705  lea     r8, aIsmodified; "IsModified"
0x18006370c  mov     edx, ebx; cchCount1
0x18006370e  mov     rcx, r14; lpString1
0x180063711  call    cs:__imp_CompareStringOrdinal
0x180063718  nop     dword ptr [rax+rax+00h]
0x18006371d  cmp     eax, 2
0x180063720  jnz     short loc_18006372F
0x180063722  mov     rcx, rdi; this
0x180063725  call    ?_IsModified@CHighContrastTheme@DataModel@SystemSettings@@AEAA_NXZ; SystemSettings::DataModel::CHighContrastTheme::_IsModified(void)
0x18006372a  jmp     loc_1800637BC
0x18006372f  mov     [rsp+38h+bIgnoreCase], r12d; bIgnoreCase
0x180063734  mov     r9d, ebx; cchCount2
0x180063737  lea     r8, aCanapply; "CanApply"
0x18006373e  mov     edx, ebx; cchCount1
0x180063740  mov     rcx, r14; lpString1
0x180063743  call    cs:__imp_CompareStringOrdinal
0x18006374a  nop     dword ptr [rax+rax+00h]
0x18006374f  cmp     eax, 2
0x180063752  jnz     short loc_18006375E
0x180063754  mov     rcx, rdi; this
0x180063757  call    ?_CanApply@CHighContrastTheme@DataModel@SystemSettings@@AEAA_NXZ; SystemSettings::DataModel::CHighContrastTheme::_CanApply(void)
0x18006375c  jmp     short loc_1800637BC
0x18006375e  mov     [rsp+38h+bIgnoreCase], r12d; bIgnoreCase
0x180063763  mov     r9d, ebx; cchCount2
0x180063766  lea     r8, aCanedit; "CanEdit"
0x18006376d  mov     edx, ebx; cchCount1
0x18006376f  mov     rcx, r14; lpString1
0x180063772  call    cs:__imp_CompareStringOrdinal
0x180063779  nop     dword ptr [rax+rax+00h]
0x18006377e  cmp     eax, 2
0x180063781  jnz     short loc_18006378F
0x180063783  cmp     dword ptr [rdi+0F8h], 0
0x18006378a  setnz   cl
0x18006378d  jmp     short loc_1800637BE
0x18006378f  mov     [rsp+38h+bIgnoreCase], r12d; bIgnoreCase
0x180063794  mov     r9d, ebx; cchCount2
0x180063797  lea     r8, aCandelete; "CanDelete"
0x18006379e  mov     edx, ebx; cchCount1
0x1800637a0  mov     rcx, r14; lpString1
0x1800637a3  call    cs:__imp_CompareStringOrdinal
0x1800637aa  nop     dword ptr [rax+rax+00h]
0x1800637af  cmp     eax, 2
0x1800637b2  jnz     short loc_1800637CD
0x1800637b4  mov     rcx, rdi; this
0x1800637b7  call    ?_IsCustomTheme@CHighContrastTheme@DataModel@SystemSettings@@AEAA_NXZ; SystemSettings::DataModel::CHighContrastTheme::_IsCustomTheme(void)
0x1800637bc  mov     cl, al; unsigned __int8
0x1800637be  mov     rdx, rsi; struct IInspectable **
0x1800637c1  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1800637c6  mov     ebx, eax
0x1800637c8  jmp     loc_18006392D
0x1800637cd  mov     [rsp+38h+bIgnoreCase], r12d; bIgnoreCase
0x1800637d2  mov     r9d, ebx; cchCount2
0x1800637d5  lea     r8, aApplyaction; "ApplyAction"
0x1800637dc  mov     edx, ebx; cchCount1
0x1800637de  mov     rcx, r14; lpString1
0x1800637e1  call    cs:__imp_CompareStringOrdinal
0x1800637e8  nop     dword ptr [rax+rax+00h]
0x1800637ed  cmp     eax, 2
0x1800637f0  jnz     short loc_18006382E
0x1800637f2  mov     [rbp+arg_10], 0
0x1800637fa  lea     rcx, [rbp+arg_10]
0x1800637fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063803  lea     r8, [rbp+arg_10]
0x180063807  xor     edx, edx
0x180063809  mov     rcx, [rdi+100h]
0x180063810  call    ?CreateInstance@CHighContrastThemeAction@DataModel@SystemSettings@@SAJPEBGW4EThemeAction@23@PEAPEAV123@@Z; SystemSettings::DataModel::CHighContrastThemeAction::CreateInstance(ushort const *,SystemSettings::DataModel::EThemeAction,SystemSettings::DataModel::CHighContrastThemeAction * *)
0x180063815  mov     ebx, eax
0x180063817  test    eax, eax
0x180063819  js      short loc_180063829
0x18006381b  mov     rdx, rsi
0x18006381e  lea     rcx, [rbp+arg_10]
0x180063822  call    ??$CopyTo@UIInspectable@@@?$ComPtr@VTextInput_CustomTheme_BackgroundPicture_ChoosePicture_Browse@Personalization@SystemSettings@@@WRL@Microsoft@@QEBAJPEAPEAUIInspectable@@@Z; Microsoft::WRL::ComPtr<SystemSettings::Personalization::TextInput_CustomTheme_BackgroundPicture_ChoosePicture_Browse>::CopyTo<IInspectable>(IInspectable * *)
0x180063827  mov     ebx, eax
0x180063829  jmp     loc_1800638EC
0x18006382e  mov     [rsp+38h+bIgnoreCase], r12d; bIgnoreCase
0x180063833  mov     r9d, ebx; cchCount2
0x180063836  lea     r8, aCancelaction; "CancelAction"
0x18006383d  mov     edx, ebx; cchCount1
0x18006383f  mov     rcx, r14; lpString1
0x180063842  call    cs:__imp_CompareStringOrdinal
0x180063849  nop     dword ptr [rax+rax+00h]
0x18006384e  cmp     eax, 2
0x180063851  jnz     short loc_18006388D
0x180063853  mov     [rbp+arg_10], 0
0x18006385b  lea     rcx, [rbp+arg_10]
0x18006385f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063864  lea     r8, [rbp+arg_10]
0x180063868  mov     edx, r12d
0x18006386b  mov     rcx, [rdi+100h]
0x180063872  call    ?CreateInstance@CHighContrastThemeAction@DataModel@SystemSettings@@SAJPEBGW4EThemeAction@23@PEAPEAV123@@Z; SystemSettings::DataModel::CHighContrastThemeAction::CreateInstance(ushort const *,SystemSettings::DataModel::EThemeAction,SystemSettings::DataModel::CHighContrastThemeAction * *)
0x180063877  mov     ebx, eax
0x180063879  test    eax, eax
0x18006387b  js      short loc_18006388B
0x18006387d  mov     rdx, rsi
0x180063880  lea     rcx, [rbp+arg_10]
0x180063884  call    ??$CopyTo@UIInspectable@@@?$ComPtr@VTextInput_CustomTheme_BackgroundPicture_ChoosePicture_Browse@Personalization@SystemSettings@@@WRL@Microsoft@@QEBAJPEAPEAUIInspectable@@@Z; Microsoft::WRL::ComPtr<SystemSettings::Personalization::TextInput_CustomTheme_BackgroundPicture_ChoosePicture_Browse>::CopyTo<IInspectable>(IInspectable * *)
0x180063889  mov     ebx, eax
0x18006388b  jmp     short loc_1800638EC
0x18006388d  mov     [rsp+38h+bIgnoreCase], r12d; bIgnoreCase
0x180063892  mov     r9d, ebx; cchCount2
0x180063895  lea     r8, aDeleteaction; "DeleteAction"
0x18006389c  mov     edx, ebx; cchCount1
0x18006389e  mov     rcx, r14; lpString1
0x1800638a1  call    cs:__imp_CompareStringOrdinal
0x1800638a8  nop     dword ptr [rax+rax+00h]
0x1800638ad  cmp     eax, 2
0x1800638b0  jnz     short loc_1800638F7
0x1800638b2  mov     [rbp+arg_10], 0
0x1800638ba  lea     rcx, [rbp+arg_10]
0x1800638be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800638c3  lea     r8, [rbp+arg_10]
0x1800638c7  mov     edx, 2
0x1800638cc  mov     rcx, [rdi+100h]
0x1800638d3  call    ?CreateInstance@CHighContrastThemeAction@DataModel@SystemSettings@@SAJPEBGW4EThemeAction@23@PEAPEAV123@@Z; SystemSettings::DataModel::CHighContrastThemeAction::CreateInstance(ushort const *,SystemSettings::DataModel::EThemeAction,SystemSettings::DataModel::CHighContrastThemeAction * *)
0x1800638d8  mov     ebx, eax
0x1800638da  test    eax, eax
0x1800638dc  js      short loc_1800638EC
0x1800638de  mov     rdx, rsi
0x1800638e1  lea     rcx, [rbp+arg_10]
0x1800638e5  call    ??$CopyTo@UIInspectable@@@?$ComPtr@VTextInput_CustomTheme_BackgroundPicture_ChoosePicture_Browse@Personalization@SystemSettings@@@WRL@Microsoft@@QEBAJPEAPEAUIInspectable@@@Z; Microsoft::WRL::ComPtr<SystemSettings::Personalization::TextInput_CustomTheme_BackgroundPicture_ChoosePicture_Browse>::CopyTo<IInspectable>(IInspectable * *)
0x1800638ea  mov     ebx, eax
0x1800638ec  lea     rcx, [rbp+arg_10]
0x1800638f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800638f5  jmp     short loc_18006392D
0x1800638f7  mov     rcx, rdi; this
0x1800638fa  call    ?_MakeSureThemeLoaded@CHighContrastTheme@DataModel@SystemSettings@@AEAAJXZ; SystemSettings::DataModel::CHighContrastTheme::_MakeSureThemeLoaded(void)
0x1800638ff  mov     ebx, eax
0x180063901  test    eax, eax
0x180063903  js      short loc_18006392D
0x180063905  mov     rdx, r14; unsigned __int16 *
0x180063908  call    ?_GetHCColorIndex@CHighContrastTheme@DataModel@SystemSettings@@AEAAHPEBG@Z; SystemSettings::DataModel::CHighContrastTheme::_GetHCColorIndex(ushort const *)
0x18006390d  test    eax, eax
0x18006390f  js      short loc_180063928
0x180063911  movsxd  rcx, eax
0x180063914  mov     rdx, rsi; struct IInspectable **
0x180063917  mov     ecx, [rdi+rcx*8+118h]; unsigned int
0x18006391e  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x180063923  jmp     loc_1800637C6
0x180063928  mov     ebx, 80070057h
0x18006392d  mov     eax, ebx
0x18006392f  add     rsp, 38h
0x180063933  pop     r14
0x180063935  pop     r12
0x180063937  pop     rdi
0x180063938  pop     rsi
0x180063939  pop     rbx
0x18006393a  pop     rbp
0x18006393b  retn
```
