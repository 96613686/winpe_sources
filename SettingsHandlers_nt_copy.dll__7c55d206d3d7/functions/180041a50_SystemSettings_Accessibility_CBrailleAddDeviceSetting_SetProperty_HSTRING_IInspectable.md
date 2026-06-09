# SystemSettings::Accessibility::CBrailleAddDeviceSetting::SetProperty(HSTRING__ *,IInspectable *)

- ea: `0x180041a50`
- end: `0x180041e92`
- name: `?SetProperty@CBrailleAddDeviceSetting@Accessibility@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `1090`
- prototype: `__int64 __fastcall(SystemSettings::Accessibility::CBrailleAddDeviceSetting *__hidden this, HSTRING, struct IInspectable *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180019a20`
- `0x18001ecfc`
- `0x180021398`
- `0x180021640`
- `0x180022610`
- `0x18002373c`
- `0x18002395c`
- `0x18002f25c`
- `0x180040aa0`
- `0x180041a50`
- `0x180044010`
- `0x180045ce4`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041af3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041b35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041bb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041bf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041d10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041d55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041e31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041af3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041b35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041bb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041bf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041d10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041d55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041e31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041b50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041c13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041db2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041b50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041c13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041db2`

## string_xrefs

- `0x180041ab2`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`
- `0x180041b1f`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`
- `0x180041be3`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`
- `0x180041d82`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::Accessibility::CBrailleAddDeviceSetting::SetProperty(
        SystemSettings::Accessibility::CBrailleAddDeviceSetting *this,
        SystemSettings::DataModel *a2,
        struct IInspectable *a3)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v7; // eax
  const unsigned __int16 *v8; // r8
  unsigned int v9; // ebx
  const unsigned __int16 *v10; // r8
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  PCWSTR StringRawBuffer; // rax
  HSTRING v15; // rcx
  const unsigned __int16 *v16; // r8
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  __int64 v20; // r9
  __int64 v21; // rdx
  PCWSTR v22; // rax
  const unsigned __int16 *v23; // r8
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  __int64 v27; // r9
  __int64 v28; // rdx
  PCWSTR v29; // rax
  HSTRING v31; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+28h] [rbp-48h] BYREF
  HSTRING v33; // [rsp+30h] [rbp-40h] BYREF
  __int64 v34; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v35[32]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v34 = 0;
  QueryInterface = a3->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  v7 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
         a3,
         &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
         &v34);
  v9 = v7;
  if ( v7 >= 0 )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802EDCF0, v8) )
    {
      string = 0;
      v11 = v34;
      v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 152LL);
      WindowsDeleteString(0);
      string = 0;
      v13 = v12(v11, &string);
      v9 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x953,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
          (const char *)(unsigned int)v13,
          (int)v31);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_30;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      std::wstring::assign((char *)this + 216, StringRawBuffer);
      *((_BYTE *)this + 312) = 1;
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_1802EDD78);
      v15 = string;
      goto LABEL_26;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802EDD38, v10) )
    {
      v31 = 0;
      v17 = v34;
      v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 152LL);
      WindowsDeleteString(0);
      v31 = 0;
      v19 = v18(v17, &v31);
      v9 = v19;
      if ( v19 < 0 )
      {
        v20 = (unsigned int)v19;
        v21 = 2395;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
          (const char *)v20,
          (int)v31);
        WindowsDeleteString(v31);
        v31 = 0;
        goto LABEL_30;
      }
      v22 = WindowsGetStringRawBuffer(v31, 0);
      std::wstring::wstring(v35, v22);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
        &unk_18039C818,
        &string,
        v35);
      std::wstring::_Tidy_deallocate(v35);
      if ( string == (HSTRING)qword_18039C820 )
      {
        v9 = -2147418113;
        v20 = 2147549183LL;
        v21 = 2398;
        goto LABEL_10;
      }
      std::wstring::operator=((char *)this + 248, string + 12);
      if ( (unsigned __int8)std::wstring::_Equal((char *)this + 248, L"USB") )
      {
        *(_WORD *)((char *)this + 313) = 1;
        *((_BYTE *)this + 315) = 1;
        std::wstring::assign((char *)this + 280, &LocaleName);
        SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_1802EDDE0);
      }
      else
      {
        if ( !(unsigned __int8)std::wstring::_Equal((char *)this + 248, L"Serial") )
        {
          WindowsDeleteString(v31);
          v31 = 0;
          v9 = -2147418113;
          goto LABEL_30;
        }
        *(_WORD *)((char *)this + 313) = 256;
        *((_BYTE *)this + 315) = 0;
      }
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_1802EDDB8);
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_1802EDE28);
      v15 = v31;
LABEL_26:
      WindowsDeleteString(v15);
LABEL_29:
      v9 = SystemSettings::DataModel::CSettingBase::SetProperty(this, (HSTRING)a2, a3);
      goto LABEL_30;
    }
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802EDDE0, v16) )
    {
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802EDE08, v23) )
        SystemSettings::Accessibility::CBrailleAddDeviceSetting::ResetFields((SystemSettings::Accessibility::CBrailleAddDeviceSetting *)((char *)this - 32));
      goto LABEL_29;
    }
    v33 = 0;
    v24 = v34;
    v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 152LL);
    WindowsDeleteString(0);
    v33 = 0;
    v26 = v25(v24, &v33);
    v9 = v26;
    if ( v26 >= 0 )
    {
      v29 = WindowsGetStringRawBuffer(v33, 0);
      std::wstring::wstring(v35, v29);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
        &unk_18039C880,
        &string,
        v35);
      std::wstring::_Tidy_deallocate(v35);
      if ( string != (HSTRING)qword_18039C888 )
      {
        std::wstring::operator=((char *)this + 280, string + 12);
        *((_BYTE *)this + 315) = 1;
        SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_1802EDE28);
        v15 = v33;
        goto LABEL_26;
      }
      v9 = -2147418113;
      v27 = 2147549183LL;
      v28 = 2435;
    }
    else
    {
      v27 = (unsigned int)v26;
      v28 = 2431;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
      (const char *)v27,
      (int)v31);
    WindowsDeleteString(v33);
    v33 = 0;
    goto LABEL_30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x94E,
    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
    (const char *)(unsigned int)v7,
    (int)v31);
LABEL_30:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  return v9;
}

```

## disassembly

```asm
0x180041a50  push    rbp
0x180041a52  push    rbx
0x180041a53  push    rsi
0x180041a54  push    rdi
0x180041a55  push    r12
0x180041a57  push    r14
0x180041a59  push    r15
0x180041a5b  mov     rbp, rsp
0x180041a5e  sub     rsp, 70h
0x180041a62  mov     rax, cs:__security_cookie
0x180041a69  xor     rax, rsp
0x180041a6c  mov     [rbp+var_10], rax
0x180041a70  mov     r15, r8
0x180041a73  mov     r14, rdx
0x180041a76  mov     rsi, rcx
0x180041a79  xor     r12d, r12d
0x180041a7c  mov     [rbp+var_38], r12
0x180041a80  mov     rax, [r8]
0x180041a83  mov     rbx, [rax]
0x180041a86  lea     rcx, [rbp+var_38]
0x180041a8a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041a8f  lea     r8, [rbp+var_38]
0x180041a93  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180041a9a  mov     rcx, r15
0x180041a9d  mov     rax, rbx
0x180041aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041aa5  mov     ebx, eax
0x180041aa7  test    eax, eax
0x180041aa9  jns     short loc_180041AC8
0x180041aab  mov     rcx, [rbp+38h]; this
0x180041aaf  mov     r9d, eax; char *
0x180041ab2  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x180041ab9  mov     edx, 94Eh; void *
0x180041abe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041ac3  jmp     loc_180041E6B
0x180041ac8  lea     rdx, stru_1802EDCF0; HSTRING
0x180041acf  mov     rcx, r14; this
0x180041ad2  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041ad7  test    al, al
0x180041ad9  jz      loc_180041B8B
0x180041adf  mov     [rbp+string], r12
0x180041ae3  mov     rdi, [rbp+var_38]
0x180041ae7  mov     rax, [rdi]
0x180041aea  mov     rbx, [rax+98h]
0x180041af1  xor     ecx, ecx; string
0x180041af3  call    cs:__imp_WindowsDeleteString
0x180041afa  nop     dword ptr [rax+rax+00h]
0x180041aff  mov     [rbp+string], r12
0x180041b03  lea     rdx, [rbp+string]
0x180041b07  mov     rcx, rdi
0x180041b0a  mov     rax, rbx
0x180041b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b12  mov     ebx, eax
0x180041b14  test    eax, eax
0x180041b16  jns     short loc_180041B4A
0x180041b18  mov     rcx, [rbp+38h]; this
0x180041b1c  mov     r9d, eax; char *
0x180041b1f  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x180041b26  mov     edx, 953h; void *
0x180041b2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041b30  nop
0x180041b31  mov     rcx, [rbp+string]; string
0x180041b35  call    cs:__imp_WindowsDeleteString
0x180041b3c  nop     dword ptr [rax+rax+00h]
0x180041b41  mov     [rbp+string], r12
0x180041b45  jmp     loc_180041E6B
0x180041b4a  xor     edx, edx; length
0x180041b4c  mov     rcx, [rbp+string]; string
0x180041b50  call    cs:__imp_WindowsGetStringRawBuffer
0x180041b57  nop     dword ptr [rax+rax+00h]
0x180041b5c  lea     rcx, [rsi+0D8h]
0x180041b63  mov     rdx, rax
0x180041b66  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180041b6b  mov     byte ptr [rsi+138h], 1
0x180041b72  lea     rdx, stru_1802EDD78; unsigned __int16 *
0x180041b79  mov     rcx, rsi; this
0x180041b7c  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180041b81  nop
0x180041b82  mov     rcx, [rbp+string]
0x180041b86  jmp     loc_180041E31
0x180041b8b  lea     rdx, stru_1802EDD38; HSTRING
0x180041b92  mov     rcx, r14; this
0x180041b95  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041b9a  test    al, al
0x180041b9c  jz      loc_180041D2A
0x180041ba2  mov     [rbp+var_50], r12
0x180041ba6  mov     rdi, [rbp+var_38]
0x180041baa  mov     rax, [rdi]
0x180041bad  mov     rbx, [rax+98h]
0x180041bb4  xor     ecx, ecx; string
0x180041bb6  call    cs:__imp_WindowsDeleteString
0x180041bbd  nop     dword ptr [rax+rax+00h]
0x180041bc2  mov     [rbp+var_50], r12
0x180041bc6  lea     rdx, [rbp+var_50]
0x180041bca  mov     rcx, rdi
0x180041bcd  mov     rax, rbx
0x180041bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041bd5  mov     ebx, eax
0x180041bd7  test    eax, eax
0x180041bd9  jns     short loc_180041C0D
0x180041bdb  mov     r9d, eax; char *
0x180041bde  mov     edx, 95Bh; void *
0x180041be3  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x180041bea  mov     rcx, [rbp+38h]; this
0x180041bee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041bf3  nop
0x180041bf4  mov     rcx, [rbp+var_50]; string
0x180041bf8  call    cs:__imp_WindowsDeleteString
0x180041bff  nop     dword ptr [rax+rax+00h]
0x180041c04  mov     [rbp+var_50], r12
0x180041c08  jmp     loc_180041E6B
0x180041c0d  xor     edx, edx; length
0x180041c0f  mov     rcx, [rbp+var_50]; string
0x180041c13  call    cs:__imp_WindowsGetStringRawBuffer
0x180041c1a  nop     dword ptr [rax+rax+00h]
0x180041c1f  mov     rdx, rax
0x180041c22  lea     rcx, [rbp+var_30]
0x180041c26  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180041c2b  lea     r8, [rbp+var_30]
0x180041c2f  lea     rdx, [rbp+string]
0x180041c33  lea     rcx, unk_18039C818
0x180041c3a  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180041c3f  lea     rcx, [rbp+var_30]
0x180041c43  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041c48  mov     rdx, [rbp+string]
0x180041c4c  cmp     rdx, cs:qword_18039C820
0x180041c53  jnz     short loc_180041C67
0x180041c55  mov     ebx, 8000FFFFh
0x180041c5a  mov     r9d, ebx
0x180041c5d  mov     edx, 95Eh
0x180041c62  jmp     loc_180041BE3
0x180041c67  lea     rbx, [rsi+0F8h]
0x180041c6e  add     rdx, 30h ; '0'
0x180041c72  mov     rcx, rbx
0x180041c75  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180041c7a  lea     rdx, aUsb; "USB"
0x180041c81  mov     rcx, rbx
0x180041c84  call    ?_Equal@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_NQEBG@Z; std::wstring::_Equal(ushort const * const)
0x180041c89  test    al, al
0x180041c8b  jz      short loc_180041CC1
0x180041c8d  mov     word ptr [rsi+139h], 1
0x180041c96  mov     byte ptr [rsi+13Bh], 1
0x180041c9d  lea     rcx, [rsi+118h]
0x180041ca4  lea     rdx, LocaleName
0x180041cab  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180041cb0  lea     rdx, stru_1802EDDE0; unsigned __int16 *
0x180041cb7  mov     rcx, rsi; this
0x180041cba  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180041cbf  jmp     short loc_180041CE4
0x180041cc1  lea     rdx, aSerial; "Serial"
0x180041cc8  mov     rcx, rbx
0x180041ccb  call    ?_Equal@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_NQEBG@Z; std::wstring::_Equal(ushort const * const)
0x180041cd0  test    al, al
0x180041cd2  jz      short loc_180041D0C
0x180041cd4  mov     word ptr [rsi+139h], 100h
0x180041cdd  mov     [rsi+13Bh], r12b
0x180041ce4  lea     rdx, stru_1802EDDB8; unsigned __int16 *
0x180041ceb  mov     rcx, rsi; this
0x180041cee  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180041cf3  lea     rdx, stru_1802EDE28; unsigned __int16 *
0x180041cfa  mov     rcx, rsi; this
0x180041cfd  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180041d02  nop
0x180041d03  mov     rcx, [rbp+var_50]
0x180041d07  jmp     loc_180041E31
0x180041d0c  mov     rcx, [rbp+var_50]; string
0x180041d10  call    cs:__imp_WindowsDeleteString
0x180041d17  nop     dword ptr [rax+rax+00h]
0x180041d1c  mov     [rbp+var_50], r12
0x180041d20  mov     ebx, 8000FFFFh
0x180041d25  jmp     loc_180041E6B
0x180041d2a  lea     rdx, stru_1802EDDE0; HSTRING
0x180041d31  mov     rcx, r14; this
0x180041d34  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041d39  test    al, al
0x180041d3b  jz      loc_180041E3F
0x180041d41  mov     [rbp+var_40], r12
0x180041d45  mov     rdi, [rbp+var_38]
0x180041d49  mov     rax, [rdi]
0x180041d4c  mov     rbx, [rax+98h]
0x180041d53  xor     ecx, ecx; string
0x180041d55  call    cs:__imp_WindowsDeleteString
0x180041d5c  nop     dword ptr [rax+rax+00h]
0x180041d61  mov     [rbp+var_40], r12
0x180041d65  lea     rdx, [rbp+var_40]
0x180041d69  mov     rcx, rdi
0x180041d6c  mov     rax, rbx
0x180041d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d74  mov     ebx, eax
0x180041d76  test    eax, eax
0x180041d78  jns     short loc_180041DAC
0x180041d7a  mov     r9d, eax; char *
0x180041d7d  mov     edx, 97Fh; void *
0x180041d82  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x180041d89  mov     rcx, [rbp+38h]; this
0x180041d8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041d92  nop
0x180041d93  mov     rcx, [rbp+var_40]; string
0x180041d97  call    cs:__imp_WindowsDeleteString
0x180041d9e  nop     dword ptr [rax+rax+00h]
0x180041da3  mov     [rbp+var_40], r12
0x180041da7  jmp     loc_180041E6B
0x180041dac  xor     edx, edx; length
0x180041dae  mov     rcx, [rbp+var_40]; string
0x180041db2  call    cs:__imp_WindowsGetStringRawBuffer
0x180041db9  nop     dword ptr [rax+rax+00h]
0x180041dbe  mov     rdx, rax
0x180041dc1  lea     rcx, [rbp+var_30]
0x180041dc5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180041dca  lea     r8, [rbp+var_30]
0x180041dce  lea     rdx, [rbp+string]
0x180041dd2  lea     rcx, unk_18039C880
0x180041dd9  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180041dde  lea     rcx, [rbp+var_30]
0x180041de2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041de7  mov     rdx, [rbp+string]
0x180041deb  cmp     rdx, cs:qword_18039C888
0x180041df2  jnz     short loc_180041E06
0x180041df4  mov     ebx, 8000FFFFh
0x180041df9  mov     r9d, ebx
0x180041dfc  mov     edx, 983h
0x180041e01  jmp     loc_180041D82
0x180041e06  add     rdx, 30h ; '0'
0x180041e0a  lea     rcx, [rsi+118h]
0x180041e11  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180041e16  mov     byte ptr [rsi+13Bh], 1
0x180041e1d  lea     rdx, stru_1802EDE28; unsigned __int16 *
0x180041e24  mov     rcx, rsi; this
0x180041e27  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180041e2c  nop
0x180041e2d  mov     rcx, [rbp+var_40]; string
0x180041e31  call    cs:__imp_WindowsDeleteString
0x180041e38  nop     dword ptr [rax+rax+00h]
0x180041e3d  jmp     short loc_180041E5B
0x180041e3f  lea     rdx, stru_1802EDE08; HSTRING
0x180041e46  mov     rcx, r14; this
0x180041e49  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041e4e  test    al, al
0x180041e50  jz      short loc_180041E5B
0x180041e52  lea     rcx, [rsi-20h]; this
0x180041e56  call    ?ResetFields@CBrailleAddDeviceSetting@Accessibility@SystemSettings@@AEAAXXZ; SystemSettings::Accessibility::CBrailleAddDeviceSetting::ResetFields(void)
0x180041e5b  mov     r8, r15; struct IInspectable *
0x180041e5e  mov     rdx, r14; HSTRING
0x180041e61  mov     rcx, rsi; this
0x180041e64  call    ?SetProperty@CSettingBase@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z; SystemSettings::DataModel::CSettingBase::SetProperty(HSTRING__ *,IInspectable *)
0x180041e69  mov     ebx, eax
0x180041e6b  lea     rcx, [rbp+var_38]
0x180041e6f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041e74  mov     eax, ebx
0x180041e76  mov     rcx, [rbp+var_10]
0x180041e7a  xor     rcx, rsp; StackCookie
0x180041e7d  call    __security_check_cookie
0x180041e82  add     rsp, 70h
0x180041e86  pop     r15
0x180041e88  pop     r14
0x180041e8a  pop     r12
0x180041e8c  pop     rdi
0x180041e8d  pop     rsi
0x180041e8e  pop     rbx
0x180041e8f  pop     rbp
0x180041e90  retn
```
