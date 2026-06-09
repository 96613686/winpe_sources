# SystemSettings::StorageSenseHandlers::CBreakdownItemSetting::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x1800554d0`
- end: `0x180055aa2`
- name: `?GetProperty@CBreakdownItemSetting@StorageSenseHandlers@SystemSettings@@MEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `1490`
- prototype: `int(SystemSettings::StorageSenseHandlers::CBreakdownItemSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002260`
- `0x180006e50`
- `0x180007a00`
- `0x18000c964`
- `0x180019eb4`
- `0x18001f688`
- `0x18001fe08`
- `0x18002adf4`
- `0x18002bad4`
- `0x180036ae4`
- `0x1800379c8`
- `0x18003d408`
- `0x18003dbc4`
- `0x180043f48`
- `0x180045dc4`
- `0x18005190c`
- `0x180053fe0`
- `0x1800554d0`
- `0x18005cd78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800558f0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180055905`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180055917`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800558f0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180055905`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180055917`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005570f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005570f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055a27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055a27`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x180055837`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x180055894`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x1800558c5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x180055971`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x1800559a2`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x180055837`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x180055894`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x1800558c5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x180055971`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x1800559a2`

## string_xrefs

- `0x1800559bb`: `SystemSettings_StorageSense_Overview_Category_Space_Usage_Read`
- `0x1800559fe`: `StorageSenseCategoryIconTemplate`
- `0x1800559f5`: `StorageSenseCategoryIconTemplate2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::StorageSenseHandlers::CBreakdownItemSetting::GetProperty(
        SystemSettings::StorageSenseHandlers::CBreakdownItemSetting *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  HRESULT InprocSettingsDatabase; // ebx
  const unsigned __int16 *v7; // r8
  unsigned __int8 v8; // r15
  __int64 v9; // rax
  const unsigned __int16 *v10; // rcx
  const unsigned __int16 *v11; // r8
  __int64 v12; // rax
  WCHAR *v13; // rcx
  const unsigned __int16 *v14; // r8
  int UInt32; // eax
  const unsigned __int16 *v16; // r8
  __int64 v17; // rcx
  double v18; // xmm0_8
  __int64 v19; // rcx
  double v20; // xmm1_8
  const unsigned __int16 *v21; // r8
  __int64 v22; // rax
  const unsigned __int16 *v23; // r8
  int v24; // eax
  const unsigned __int16 *v25; // r8
  SystemSettings::StorageSenseHandlers::CAppSizesDriveSelectionSingleton *v26; // rcx
  struct IInspectable **v27; // rdx
  struct IInspectable *v28; // rax
  struct IInspectable *v29; // rax
  const unsigned __int16 *v30; // r8
  const unsigned __int16 *v31; // r8
  const unsigned __int16 *v32; // r8
  char IsEnabled; // al
  const struct _tlgProvider_t *v34; // rax
  int v35; // esi
  int v36; // r8d
  int v37; // r9d
  unsigned __int16 v39[4]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v42; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszBuf[64]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v44[64]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR v45[64]; // [rsp+160h] [rbp+60h] BYREF

  *a3 = 0;
  InprocSettingsDatabase = -2147024809;
  v8 = 1;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010CCF8, (const unsigned __int16 *)a3) )
  {
    v9 = *((int *)this + 82);
    if ( (unsigned int)v9 <= 0xE )
    {
      if ( (_DWORD)v9 == 1 )
      {
        v10 = L"SystemSettings_StorageSense_Category_Apps2";
      }
      else
      {
        v10 = off_180170070[6 * v9 + 1];
        if ( !v10 )
          goto LABEL_7;
      }
      InprocSettingsDatabase = SystemSettings::DataModel::PropValueHelper::CreateString(v10, a3);
    }
  }
LABEL_7:
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010CCD0, v7) )
  {
    v12 = *((int *)this + 82);
    if ( (unsigned int)v12 > 0xE )
      goto LABEL_60;
    v13 = off_180170070[6 * v12 + 2];
LABEL_10:
    if ( !v13 )
      goto LABEL_60;
    goto LABEL_58;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010CD50, v11) )
  {
    UInt32 = SystemSettings::DataModel::PropValueHelper::CreateUInt32(*((_DWORD *)this + 82), a3);
LABEL_59:
    InprocSettingsDatabase = UInt32;
    goto LABEL_60;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010CD18, v14) )
  {
    v17 = *((_QWORD *)this + 39);
    if ( v17 < 0 )
      v18 = (double)(int)(v17 & 1 | ((unsigned __int64)v17 >> 1))
          + (double)(int)(v17 & 1 | ((unsigned __int64)v17 >> 1));
    else
      v18 = (double)(int)v17;
    v19 = *((_QWORD *)this + 40);
    if ( v19 < 0 )
      v20 = (double)(int)(v19 & 1 | ((unsigned __int64)v19 >> 1))
          + (double)(int)(v19 & 1 | ((unsigned __int64)v19 >> 1));
    else
      v20 = (double)(int)v19;
    UInt32 = SystemSettings::DataModel::PropValueHelper::CreateDouble(v18 / v20 * 100.0, a3);
    goto LABEL_59;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010CD88, v16) )
  {
    v22 = *((int *)this + 82);
    if ( (unsigned int)v22 > 0xE )
      goto LABEL_60;
    v13 = off_180170070[6 * v22 + 3];
    goto LABEL_10;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010AD68, v21) )
  {
    v24 = *((_DWORD *)this + 72);
    if ( v24 && (v24 != 1 || !*((_BYTE *)this + 868)) )
      v8 = 0;
    UInt32 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v8, a3);
    goto LABEL_59;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180108C70, v23) )
  {
    if ( *((_DWORD *)this + 82) == 1 )
    {
      if ( IsDesktopSKU() )
      {
        string = 0;
        Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string, (char *)this + 304);
        SystemSettings::StorageSenseHandlers::CAppSizesDriveSelectionSingleton::SetVolumeGuid(v26, string);
        WindowsDeleteString(string);
      }
      *(_QWORD *)v39 = 0;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v39);
      InprocSettingsDatabase = SystemSettings::DataModel::GetInprocSettingsDatabase(
                                 (SystemSettings::DataModel *)v39,
                                 v27);
      if ( InprocSettingsDatabase >= 0 )
      {
        v28 = *(struct IInspectable **)v39;
        *(_QWORD *)v39 = 0;
        *a3 = v28;
      }
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v39);
    }
    else
    {
      string = 0;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&string);
      InprocSettingsDatabase = SystemSettings::StorageSenseHandlers::CStorageSenseDynamicDatabase::CreateInstance(
                                 *((_QWORD *)this + 35),
                                 *((unsigned int *)this + 73),
                                 *((unsigned int *)this + 74),
                                 *((_QWORD *)this + 38),
                                 *((_QWORD *)this + 39),
                                 *((_QWORD *)this + 40),
                                 &string);
      if ( InprocSettingsDatabase >= 0 )
      {
        *(_QWORD *)v39 = 0;
        InprocSettingsDatabase = Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CStorageSenseDynamicDatabase>::As<IInspectable>(
                                   &string,
                                   v39);
        if ( InprocSettingsDatabase >= 0 )
        {
          v29 = *(struct IInspectable **)v39;
          *(_QWORD *)v39 = 0;
          *a3 = v29;
        }
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v39);
      }
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&string);
    }
    goto LABEL_60;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010CD68, v25) )
  {
    memset_0(pszBuf, 0, sizeof(pszBuf));
    InprocSettingsDatabase = StrFormatByteSizeEx(*((_QWORD *)this + 39), 2, pszBuf, 0x40u);
    if ( InprocSettingsDatabase < 0 )
      goto LABEL_60;
LABEL_45:
    v13 = pszBuf;
LABEL_58:
    UInt32 = SystemSettings::DataModel::PropValueHelper::CreateString(v13, a3);
    goto LABEL_59;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010CDF8, v30) )
  {
    memset_0(v45, 0, sizeof(v45));
    InprocSettingsDatabase = StrFormatByteSizeEx(*((_QWORD *)this + 40), 2, v45, 0x40u);
    if ( InprocSettingsDatabase < 0 )
      goto LABEL_60;
    memset_0(v44, 0, sizeof(v44));
    InprocSettingsDatabase = StrFormatByteSizeEx(*((_QWORD *)this + 39), 2, v44, 0x40u);
    if ( InprocSettingsDatabase < 0 )
      goto LABEL_60;
    memset_0(pszBuf, 0, sizeof(pszBuf));
    _o_wcscat_s(pszBuf, 64, v44);
    _o_wcscat_s(pszBuf, 64, L"/");
    _o_wcscat_s(pszBuf, 64, v45);
    goto LABEL_45;
  }
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010CDB0, v31) )
  {
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010CE20, v32) )
      goto LABEL_60;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_46956793>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_46956793>::GetImpl'::`2'::impl);
    v13 = L"StorageSenseCategoryIconTemplate2";
    if ( !IsEnabled )
      v13 = (WCHAR *)L"StorageSenseCategoryIconTemplate";
    goto LABEL_58;
  }
  *(_QWORD *)v39 = &word_180106450;
  memset_0(v45, 0, sizeof(v45));
  InprocSettingsDatabase = StrFormatByteSizeEx(*((_QWORD *)this + 40), 2, v45, 0x40u);
  if ( InprocSettingsDatabase >= 0 )
  {
    memset_0(v44, 0, sizeof(v44));
    InprocSettingsDatabase = StrFormatByteSizeEx(*((_QWORD *)this + 39), 2, v44, 0x40u);
    if ( InprocSettingsDatabase >= 0 )
    {
      InprocSettingsDatabase = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
                                 (SystemSettings::DataModel *)L"SystemSettings_StorageSense_Overview_Category_Space_Usage_Read",
                                 v39,
                                 (unsigned __int16 **)v44,
                                 v45);
      if ( InprocSettingsDatabase >= 0 )
      {
        v13 = *(WCHAR **)v39;
        goto LABEL_58;
      }
    }
  }
LABEL_60:
  v34 = SettingsHandlersStorageSenseLogging::Provider();
  v35 = (int)v34;
  if ( *(_DWORD *)v34 > 3u )
  {
    LODWORD(string) = InprocSettingsDatabase;
    StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)a2, 0);
    *(_DWORD *)v39 = *((_DWORD *)this + 82);
    v42 = *((_QWORD *)this + 38);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned int)&unk_180151249,
      v36,
      v37,
      (__int64)&v42,
      (__int64)v39,
      (__int64)&StringRawBuffer,
      (__int64)&string);
  }
  return (unsigned int)InprocSettingsDatabase;
}

```

## disassembly

```asm
0x1800554d0  push    rbp
0x1800554d2  push    rbx
0x1800554d3  push    rsi
0x1800554d4  push    rdi
0x1800554d5  push    r12
0x1800554d7  push    r14
0x1800554d9  push    r15
0x1800554db  lea     rbp, [rsp-0F0h]
0x1800554e3  sub     rsp, 1F0h
0x1800554ea  mov     rax, cs:__security_cookie
0x1800554f1  xor     rax, rsp
0x1800554f4  mov     [rbp+120h+var_40], rax
0x1800554fb  mov     rsi, r8
0x1800554fe  mov     r14, rdx
0x180055501  mov     rdi, rcx
0x180055504  mov     qword ptr [r8], 0
0x18005550b  mov     ebx, 80070057h
0x180055510  lea     rdx, stru_18010CCF8; HSTRING
0x180055517  mov     rcx, r14; this
0x18005551a  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18005551f  mov     r15d, 1
0x180055525  lea     r12, off_180170070; "System"
0x18005552c  test    al, al
0x18005552e  jz      short loc_180055565
0x180055530  movsxd  rax, dword ptr [rdi+148h]
0x180055537  cmp     eax, 0Eh
0x18005553a  ja      short loc_180055565
0x18005553c  cmp     eax, r15d
0x18005553f  jnz     short loc_18005554A
0x180055541  lea     rcx, aSystemsettings_107; "SystemSettings_StorageSense_Category_Ap"...
0x180055548  jmp     short loc_18005555B
0x18005554a  lea     rcx, [rax+rax*2]
0x18005554e  add     rcx, rcx
0x180055551  mov     rcx, [r12+rcx*8+8]; unsigned __int16 *
0x180055556  test    rcx, rcx
0x180055559  jz      short loc_180055565
0x18005555b  mov     rdx, rsi; struct IInspectable **
0x18005555e  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180055563  mov     ebx, eax
0x180055565  lea     rdx, stru_18010CCD0; HSTRING
0x18005556c  mov     rcx, r14; this
0x18005556f  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180055574  test    al, al
0x180055576  jz      short loc_1800555A2
0x180055578  movsxd  rax, dword ptr [rdi+148h]
0x18005557f  cmp     eax, 0Eh
0x180055582  ja      loc_180055A0F
0x180055588  lea     rax, [rax+rax*2]
0x18005558c  add     rax, rax
0x18005558f  mov     rcx, [r12+rax*8+10h]
0x180055594  test    rcx, rcx
0x180055597  jz      loc_180055A0F
0x18005559d  jmp     loc_180055A05
0x1800555a2  lea     rdx, stru_18010CD50; HSTRING
0x1800555a9  mov     rcx, r14; this
0x1800555ac  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800555b1  test    al, al
0x1800555b3  jz      short loc_1800555C8
0x1800555b5  mov     rdx, rsi; struct IInspectable **
0x1800555b8  mov     ecx, [rdi+148h]; unsigned int
0x1800555be  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x1800555c3  jmp     loc_180055A0D
0x1800555c8  lea     rdx, stru_18010CD18; HSTRING
0x1800555cf  mov     rcx, r14; this
0x1800555d2  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800555d7  test    al, al
0x1800555d9  jz      short loc_18005564A
0x1800555db  mov     rcx, [rdi+138h]
0x1800555e2  xorps   xmm0, xmm0
0x1800555e5  test    rcx, rcx
0x1800555e8  js      short loc_1800555F1
0x1800555ea  cvtsi2sd xmm0, rcx
0x1800555ef  jmp     short loc_180055606
0x1800555f1  mov     rax, rcx
0x1800555f4  shr     rax, 1
0x1800555f7  and     rcx, r15
0x1800555fa  or      rax, rcx
0x1800555fd  cvtsi2sd xmm0, rax
0x180055602  addsd   xmm0, xmm0
0x180055606  mov     rcx, [rdi+140h]
0x18005560d  xorps   xmm1, xmm1
0x180055610  test    rcx, rcx
0x180055613  js      short loc_18005561C
0x180055615  cvtsi2sd xmm1, rcx
0x18005561a  jmp     short loc_180055631
0x18005561c  mov     rax, rcx
0x18005561f  shr     rax, 1
0x180055622  and     rcx, r15
0x180055625  or      rax, rcx
0x180055628  cvtsi2sd xmm1, rax
0x18005562d  addsd   xmm1, xmm1
0x180055631  divsd   xmm0, xmm1
0x180055635  mulsd   xmm0, cs:__real@4059000000000000; double
0x18005563d  mov     rdx, rsi; struct IInspectable **
0x180055640  call    ?CreateDouble@PropValueHelper@DataModel@SystemSettings@@SAJNPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateDouble(double,IInspectable * *)
0x180055645  jmp     loc_180055A0D
0x18005564a  lea     rdx, stru_18010CD88; HSTRING
0x180055651  mov     rcx, r14; this
0x180055654  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180055659  test    al, al
0x18005565b  jz      short loc_18005567E
0x18005565d  movsxd  rax, dword ptr [rdi+148h]
0x180055664  cmp     eax, 0Eh
0x180055667  ja      loc_180055A0F
0x18005566d  lea     rcx, [rax+rax*2]
0x180055671  add     rcx, rcx
0x180055674  mov     rcx, [r12+rcx*8+18h]
0x180055679  jmp     loc_180055594
0x18005567e  lea     rdx, stru_18010AD68; HSTRING
0x180055685  mov     rcx, r14; this
0x180055688  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18005568d  test    al, al
0x18005568f  jz      short loc_1800556BC
0x180055691  mov     eax, [rdi+120h]
0x180055697  test    eax, eax
0x180055699  jz      short loc_1800556AC
0x18005569b  cmp     eax, r15d
0x18005569e  jnz     short loc_1800556A9
0x1800556a0  cmp     byte ptr [rdi+364h], 0
0x1800556a7  jnz     short loc_1800556AC
0x1800556a9  xor     r15b, r15b
0x1800556ac  mov     rdx, rsi; struct IInspectable **
0x1800556af  mov     cl, r15b; unsigned __int8
0x1800556b2  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1800556b7  jmp     loc_180055A0D
0x1800556bc  lea     rdx, stru_180108C70; HSTRING
0x1800556c3  mov     rcx, r14; this
0x1800556c6  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800556cb  test    al, al
0x1800556cd  jz      loc_1800557FC
0x1800556d3  cmp     [rdi+148h], r15d
0x1800556da  jnz     short loc_180055758
0x1800556dc  call    ?IsDesktopSKU@@YA_NXZ; IsDesktopSKU(void)
0x1800556e1  test    al, al
0x1800556e3  jz      short loc_180055715
0x1800556e5  mov     [rsp+220h+string], 0
0x1800556ee  lea     rdx, [rdi+130h]
0x1800556f5  lea     rcx, [rsp+220h+string]
0x1800556fa  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800556ff  mov     rdx, [rsp+220h+string]; HSTRING
0x180055704  call    ?SetVolumeGuid@CAppSizesDriveSelectionSingleton@StorageSenseHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppSizesDriveSelectionSingleton::SetVolumeGuid(HSTRING__ *)
0x180055709  nop
0x18005570a  mov     rcx, [rsp+220h+string]; string
0x18005570f  call    cs:__imp_WindowsDeleteString
0x180055715  mov     qword ptr [rsp+220h+var_1E0], 0
0x18005571e  lea     rcx, [rsp+220h+var_1E0]
0x180055723  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180055728  lea     rcx, [rsp+220h+var_1E0]; this
0x18005572d  call    ?GetInprocSettingsDatabase@DataModel@SystemSettings@@YAJPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::GetInprocSettingsDatabase(IInspectable * *)
0x180055732  mov     ebx, eax
0x180055734  test    eax, eax
0x180055736  js      short loc_180055749
0x180055738  mov     rax, qword ptr [rsp+220h+var_1E0]
0x18005573d  mov     qword ptr [rsp+220h+var_1E0], 0
0x180055746  mov     [rsi], rax
0x180055749  lea     rcx, [rsp+220h+var_1E0]
0x18005574e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180055753  jmp     loc_180055A0F
0x180055758  mov     [rsp+220h+string], 0
0x180055761  lea     rcx, [rsp+220h+string]
0x180055766  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18005576b  lea     rax, [rsp+220h+string]
0x180055770  mov     [rsp+220h+var_1F0], rax
0x180055775  mov     rax, [rdi+140h]
0x18005577c  mov     [rsp+220h+var_1F8], rax
0x180055781  mov     rax, [rdi+138h]
0x180055788  mov     [rsp+220h+var_200], rax
0x18005578d  mov     r9, [rdi+130h]
0x180055794  mov     r8d, [rdi+128h]
0x18005579b  mov     edx, [rdi+124h]
0x1800557a1  mov     rcx, [rdi+118h]
0x1800557a8  call    ?CreateInstance@CStorageSenseDynamicDatabase@StorageSenseHandlers@SystemSettings@@SAJPEAUIUser@System@Windows@@W4_STORAGE_DEVICE_TYPE@@KPEBG_K3PEAPEAV123@@Z; SystemSettings::StorageSenseHandlers::CStorageSenseDynamicDatabase::CreateInstance(Windows::System::IUser *,_STORAGE_DEVICE_TYPE,ulong,ushort const *,unsigned __int64,unsigned __int64,SystemSettings::StorageSenseHandlers::CStorageSenseDynamicDatabase * *)
0x1800557ad  mov     ebx, eax
0x1800557af  test    eax, eax
0x1800557b1  js      short loc_1800557ED
0x1800557b3  mov     qword ptr [rsp+220h+var_1E0], 0
0x1800557bc  lea     rdx, [rsp+220h+var_1E0]
0x1800557c1  lea     rcx, [rsp+220h+string]
0x1800557c6  call    ??$As@UIInspectable@@@?$ComPtr@VCStorageSenseDynamicDatabase@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CStorageSenseDynamicDatabase>::As<IInspectable>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>)
0x1800557cb  mov     ebx, eax
0x1800557cd  test    eax, eax
0x1800557cf  js      short loc_1800557E2
0x1800557d1  mov     rax, qword ptr [rsp+220h+var_1E0]
0x1800557d6  mov     qword ptr [rsp+220h+var_1E0], 0
0x1800557df  mov     [rsi], rax
0x1800557e2  lea     rcx, [rsp+220h+var_1E0]
0x1800557e7  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800557ec  nop
0x1800557ed  lea     rcx, [rsp+220h+string]
0x1800557f2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800557f7  jmp     loc_180055A0F
0x1800557fc  lea     rdx, stru_18010CD68; HSTRING
0x180055803  mov     rcx, r14; this
0x180055806  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18005580b  test    al, al
0x18005580d  jz      short loc_180055851
0x18005580f  xor     edx, edx; Val
0x180055811  mov     r8d, 80h; Size
0x180055817  lea     rcx, [rsp+220h+pszBuf]; void *
0x18005581c  call    memset_0
0x180055821  mov     r9d, 40h ; '@'; cchBuf
0x180055827  lea     r8, [rsp+220h+pszBuf]; pszBuf
0x18005582c  lea     edx, [r9-3Eh]; flags
0x180055830  mov     rcx, [rdi+138h]; ull
0x180055837  call    cs:__imp_StrFormatByteSizeEx
0x18005583d  mov     ebx, eax
0x18005583f  test    eax, eax
0x180055841  js      loc_180055A0F
0x180055847  lea     rcx, [rsp+220h+pszBuf]
0x18005584c  jmp     loc_180055A05
0x180055851  lea     rdx, stru_18010CDF8; HSTRING
0x180055858  mov     rcx, r14; this
0x18005585b  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180055860  test    al, al
0x180055862  jz      loc_180055922
0x180055868  mov     r12d, 80h
0x18005586e  mov     r8d, r12d; Size
0x180055871  xor     edx, edx; Val
0x180055873  lea     rcx, [rbp+120h+var_C0]; void *
0x180055877  call    memset_0
0x18005587c  lea     r15d, [r12-40h]
0x180055881  mov     r9d, r15d; cchBuf
0x180055884  lea     r8, [rbp+120h+var_C0]; pszBuf
0x180055888  lea     edx, [r12-7Eh]; flags
0x18005588d  mov     rcx, [rdi+140h]; ull
0x180055894  call    cs:__imp_StrFormatByteSizeEx
0x18005589a  mov     ebx, eax
0x18005589c  test    eax, eax
0x18005589e  js      loc_180055A0F
0x1800558a4  mov     r8d, r12d; Size
0x1800558a7  xor     edx, edx; Val
0x1800558a9  lea     rcx, [rbp+120h+var_140]; void *
0x1800558ad  call    memset_0
0x1800558b2  mov     r9d, r15d; cchBuf
0x1800558b5  lea     r8, [rbp+120h+var_140]; pszBuf
0x1800558b9  lea     edx, [r12-7Eh]; flags
0x1800558be  mov     rcx, [rdi+138h]; ull
0x1800558c5  call    cs:__imp_StrFormatByteSizeEx
0x1800558cb  mov     ebx, eax
0x1800558cd  test    eax, eax
0x1800558cf  js      loc_180055A0F
0x1800558d5  mov     r8d, r12d; Size
0x1800558d8  xor     edx, edx; Val
0x1800558da  lea     rcx, [rsp+220h+pszBuf]; void *
0x1800558df  call    memset_0
0x1800558e4  lea     r8, [rbp+120h+var_140]
0x1800558e8  mov     edx, r15d
0x1800558eb  lea     rcx, [rsp+220h+pszBuf]
0x1800558f0  call    cs:__imp__o_wcscat_s
0x1800558f6  lea     r8, asc_180104384; "/"
0x1800558fd  mov     edx, r15d
0x180055900  lea     rcx, [rsp+220h+pszBuf]
0x180055905  call    cs:__imp__o_wcscat_s
0x18005590b  lea     r8, [rbp+120h+var_C0]
0x18005590f  mov     edx, r15d
0x180055912  lea     rcx, [rsp+220h+pszBuf]
0x180055917  call    cs:__imp__o_wcscat_s
0x18005591d  jmp     loc_180055847
0x180055922  lea     rdx, stru_18010CDB0; HSTRING
0x180055929  mov     rcx, r14; this
0x18005592c  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180055931  test    al, al
0x180055933  jz      loc_1800559D4
0x180055939  lea     rax, word_180106450
0x180055940  mov     qword ptr [rsp+220h+var_1E0], rax
0x180055945  mov     r12d, 80h
0x18005594b  mov     r8d, r12d; Size
0x18005594e  xor     edx, edx; Val
0x180055950  lea     rcx, [rbp+120h+var_C0]; void *
0x180055954  call    memset_0
0x180055959  lea     r15d, [r12-40h]
0x18005595e  mov     r9d, r15d; cchBuf
0x180055961  lea     r8, [rbp+120h+var_C0]; pszBuf
0x180055965  lea     edx, [r12-7Eh]; flags
0x18005596a  mov     rcx, [rdi+140h]; ull
0x180055971  call    cs:__imp_StrFormatByteSizeEx
0x180055977  mov     ebx, eax
0x180055979  test    eax, eax
0x18005597b  js      loc_180055A0F
0x180055981  mov     r8d, r12d; Size
0x180055984  xor     edx, edx; Val
0x180055986  lea     rcx, [rbp+120h+var_140]; void *
0x18005598a  call    memset_0
0x18005598f  mov     r9d, r15d; cchBuf
0x180055992  lea     r8, [rbp+120h+var_140]; pszBuf
0x180055996  lea     edx, [r12-7Eh]; flags
0x18005599b  mov     rcx, [rdi+138h]; ull
0x1800559a2  call    cs:__imp_StrFormatByteSizeEx
0x1800559a8  mov     ebx, eax
0x1800559aa  test    eax, eax
0x1800559ac  js      short loc_180055A0F
0x1800559ae  lea     r9, [rbp+120h+var_C0]
0x1800559b2  lea     r8, [rbp+120h+var_140]; unsigned __int16 **
0x1800559b6  lea     rdx, [rsp+220h+var_1E0]; unsigned __int16 *
0x1800559bb  lea     rcx, aSystemsettings_106; "SystemSettings_StorageSense_Overview_Ca"...
0x1800559c2  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x1800559c7  mov     ebx, eax
0x1800559c9  test    eax, eax
0x1800559cb  js      short loc_180055A0F
0x1800559cd  mov     rcx, qword ptr [rsp+220h+var_1E0]
  ... truncated ...
```
