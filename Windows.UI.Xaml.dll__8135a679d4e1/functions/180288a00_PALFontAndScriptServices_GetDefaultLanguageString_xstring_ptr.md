# PALFontAndScriptServices::GetDefaultLanguageString(xstring_ptr *)

- ea: `0x180288a00`
- end: `0x180288cb6`
- name: `?GetDefaultLanguageString@PALFontAndScriptServices@@UEAAJPEAVxstring_ptr@@@Z`
- size: `694`
- prototype: `HRESULT __fastcall(PALFontAndScriptServices *this, xstring_ptr *pstrDefaultLanguageString)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180288520`

## callees

- `0x180008428`
- `0x180091d20`
- `0x1800fdd4c`
- `0x1800fe130`
- `0x18018fa54`
- `0x1801e5458`
- `0x180288a00`
- `0x180289f24`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180288c80`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180288c80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180288b78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180288c8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180288b78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180288c8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180288b2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180288c4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180288c66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180288b2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180288c4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180288c66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180288a98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180288a98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180288b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180288b1c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180288ac1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180288ac1`

## pseudocode

```c
__int64 __fastcall PALFontAndScriptServices::GetDefaultLanguageString(
        PALFontAndScriptServices *this,
        xstring_ptr *pstrDefaultLanguageString)
{
  xstring_ptr *p_m_strDefaultLanguageString; // rsi
  const xstring_ptr_storage *Storage; // rax
  int v5; // edx
  HSTRING Buffer; // rcx
  HSTRING v7; // rbx
  Windows::Globalization::IApplicationLanguagesStatics *v8; // rdi
  HRESULT (__fastcall *get_Languages)(Windows::Globalization::IApplicationLanguagesStatics *, Windows::Foundation::Collections::IVectorView<HSTRING__ *> **); // rbx
  int v10; // eax
  Windows::Foundation::Collections::IVectorView<HSTRING__ *> *ptr; // rcx
  UINT32 StringLen; // ebx
  const wchar_t *StringRawBuffer; // rax
  Windows::Foundation::Collections::IVectorView<HSTRING__ *> *v14; // rcx
  Windows::Globalization::IApplicationLanguagesStatics *v15; // rcx
  Windows::Globalization::IApplicationLanguagesStatics *v17; // rcx
  xstring_ptr v18; // rax
  int v19; // edx
  HSTRING v20; // rcx
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<HSTRING__ *> > spLanguages; // [rsp+20h] [rbp-40h] BYREF
  Microsoft::WRL::ComPtr<Windows::Globalization::IApplicationLanguagesStatics> spApplicationLanguagesStatics; // [rsp+28h] [rbp-38h] BYREF
  Windows::Internal::String strPrimaryLanguage; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF

  p_m_strDefaultLanguageString = &this->m_strDefaultLanguageString;
  Storage = this->m_strDefaultLanguageString.m_encodedStorage.Storage;
  LODWORD(spLanguages.ptr_) = 0;
  if ( ((unsigned __int8)Storage & 1) != 0 )
  {
    Buffer = (HSTRING)((unsigned __int64)Storage & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v5 = *((_DWORD *)Storage + 2);
    Buffer = (HSTRING)Storage->Buffer;
    if ( v5 >= 0 )
    {
      LODWORD(spLanguages.ptr_) = v5 & 0x3FFFFFFF;
      goto LABEL_4;
    }
  }
  Buffer = (HSTRING)WindowsGetStringRawBuffer(Buffer, (UINT32 *)&spLanguages);
LABEL_4:
  if ( Buffer && LODWORD(spLanguages.ptr_) && *(_WORD *)Buffer || CQuirksMode2::XamlQuirkIsEnabled(0x20056u) )
    goto LABEL_27;
  strPrimaryLanguage._hstring = 0;
  spApplicationLanguagesStatics.ptr_ = 0;
  spLanguages.ptr_ = 0;
  if ( WindowsCreateStringReference(
         RuntimeClass_Windows_Globalization_ApplicationLanguages,
         0x2Au,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spApplicationLanguagesStatics);
  if ( (int)RoGetActivationFactory(v7, &GUID_75b40847_0a4c_4a92_9565_fd63c95f7aed, &spApplicationLanguagesStatics) < 0 )
  {
    ptr = spLanguages.ptr_;
    goto LABEL_21;
  }
  v8 = spApplicationLanguagesStatics.ptr_;
  get_Languages = spApplicationLanguagesStatics.ptr_->get_Languages;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spLanguages);
  v10 = get_Languages(v8, &spLanguages.ptr_);
  ptr = spLanguages.ptr_;
  if ( v10 < 0 )
  {
LABEL_21:
    if ( ptr )
    {
      spLanguages.ptr_ = 0;
      ptr->Release(ptr);
    }
    v17 = spApplicationLanguagesStatics.ptr_;
    if ( spApplicationLanguagesStatics.ptr_ )
    {
      spApplicationLanguagesStatics.ptr_ = 0;
      v17->Release(v17);
    }
    if ( strPrimaryLanguage._hstring )
      WindowsDeleteString(strPrimaryLanguage._hstring);
    goto LABEL_27;
  }
  if ( spLanguages.ptr_->GetAt(spLanguages.ptr_, 0, (HSTRING__ **)&strPrimaryLanguage) >= 0 )
  {
    StringLen = WindowsGetStringLen(strPrimaryLanguage._hstring);
    StringRawBuffer = WindowsGetStringRawBuffer(strPrimaryLanguage._hstring, 0);
    xstring_ptr::CloneBuffer(StringRawBuffer, StringLen, p_m_strDefaultLanguageString);
    v14 = spLanguages.ptr_;
    if ( spLanguages.ptr_ )
    {
      spLanguages.ptr_ = 0;
      v14->Release(v14);
    }
    v15 = spApplicationLanguagesStatics.ptr_;
    if ( spApplicationLanguagesStatics.ptr_ )
    {
      spApplicationLanguagesStatics.ptr_ = 0;
      v15->Release(v15);
    }
    if ( strPrimaryLanguage._hstring )
      WindowsDeleteString(strPrimaryLanguage._hstring);
    goto $Cleanup_1635;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spLanguages);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spApplicationLanguagesStatics);
  Windows::Internal::String::~String(&strPrimaryLanguage);
LABEL_27:
  v18.m_encodedStorage.Storage = (const xstring_ptr_storage *)p_m_strDefaultLanguageString->m_encodedStorage.RuntimeStringHandleMarker;
  LODWORD(spLanguages.ptr_) = 0;
  if ( ((__int64)v18.m_encodedStorage.Storage & 1) != 0 )
  {
    v20 = (HSTRING)(v18.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
    goto LABEL_37;
  }
  v19 = *((_DWORD *)v18.m_encodedStorage.Storage + 2);
  v20 = *(HSTRING *)v18.m_encodedStorage.Handle;
  if ( v19 < 0 )
  {
LABEL_37:
    v20 = (HSTRING)WindowsGetStringRawBuffer(v20, (UINT32 *)&spLanguages);
    goto LABEL_30;
  }
  LODWORD(spLanguages.ptr_) = v19 & 0x3FFFFFFF;
LABEL_30:
  if ( !v20 || !LODWORD(spLanguages.ptr_) || !*(_WORD *)v20 )
  {
    strPrimaryLanguage._hstring = (HSTRING__ *)&c_strDefaultLanguageString;
    xstring_ptr::operator=(p_m_strDefaultLanguageString, (xstring_ptr *)&strPrimaryLanguage);
    xstring_ptr::~xstring_ptr((xstring_ptr *)&strPrimaryLanguage);
  }
$Cleanup_1635:
  xstring_ptr::operator=(pstrDefaultLanguageString, p_m_strDefaultLanguageString);
  return 0;
}

```

## disassembly

```asm
0x180288a00  mov     [rsp-28h+arg_10], rbx
0x180288a05  push    rbp
0x180288a06  push    rsi
0x180288a07  push    rdi
0x180288a08  push    r14
0x180288a0a  push    r15
0x180288a0c  mov     rbp, rsp
0x180288a0f  sub     rsp, 60h
0x180288a13  mov     rax, cs:__security_cookie
0x180288a1a  xor     rax, rsp
0x180288a1d  mov     [rbp+var_8], rax
0x180288a21  xor     r15d, r15d
0x180288a24  lea     rsi, [this+20h]
0x180288a28  mov     rax, [rsi]
0x180288a2b  mov     r14, pstrDefaultLanguageString
0x180288a2e  mov     dword ptr [rbp+spLanguages.ptr_], r15d
0x180288a32  test    al, 1
0x180288a34  jnz     loc_180288C42
0x180288a3a  mov     edx, [rax+8]
0x180288a3d  mov     this, [rax]
0x180288a40  test    edx, edx
0x180288a42  js      loc_180288C49
0x180288a48  and     edx, 3FFFFFFFh
0x180288a4e  mov     dword ptr [rbp+spLanguages.ptr_], edx
0x180288a51  test    this, this
0x180288a54  jz      short loc_180288A66
0x180288a56  cmp     dword ptr [rbp+spLanguages.ptr_], r15d
0x180288a5a  jz      short loc_180288A66
0x180288a5c  cmp     r15w, [this]
0x180288a60  jnz     loc_180288BEA
0x180288a66  mov     ecx, 20056h; quirk
0x180288a6b  call    ?XamlQuirkIsEnabled@CQuirksMode2@@SA_NK@Z; CQuirksMode2::XamlQuirkIsEnabled(ulong)
0x180288a70  test    al, al
0x180288a72  jnz     loc_180288BEA
0x180288a78  lea     r9, [rbp+string]; string
0x180288a7c  mov     [rbp+strPrimaryLanguage._hstring], r15
0x180288a80  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180288a84  mov     [rbp+spApplicationLanguagesStatics.ptr_], r15
0x180288a88  mov     edx, 2Ah ; '*'; length
0x180288a8d  mov     [rbp+spLanguages.ptr_], r15
0x180288a91  lea     this, ?RuntimeClass_Windows_Globalization_ApplicationLanguages@@3QBGB; sourceString
0x180288a98  call    cs:__imp_WindowsCreateStringReference
0x180288a9e  test    eax, eax
0x180288aa0  js      loc_180288C71
0x180288aa6  mov     rbx, [rbp+string]
0x180288aaa  lea     this, [rbp+spApplicationLanguagesStatics]; this
0x180288aae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180288ab3  lea     r8, [rbp+spApplicationLanguagesStatics]
0x180288ab7  mov     this, rbx
0x180288aba  lea     pstrDefaultLanguageString, _GUID_75b40847_0a4c_4a92_9565_fd63c95f7aed
0x180288ac1  call    cs:__imp_RoGetActivationFactory
0x180288ac7  test    eax, eax
0x180288ac9  js      loc_180288BAB
0x180288acf  mov     rdi, [rbp+spApplicationLanguagesStatics.ptr_]
0x180288ad3  lea     this, [rbp+spLanguages]; this
0x180288ad7  mov     rax, [rdi]
0x180288ada  mov     rbx, [rax+40h]
0x180288ade  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180288ae3  lea     pstrDefaultLanguageString, [rbp+spLanguages]
0x180288ae7  mov     this, rdi
0x180288aea  mov     rax, rbx
0x180288aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180288af2  mov     this, [rbp+spLanguages.ptr_]
0x180288af6  test    eax, eax
0x180288af8  js      loc_180288BAF
0x180288afe  mov     rax, [this]
0x180288b01  lea     r8, [rbp+strPrimaryLanguage]
0x180288b05  xor     edx, edx
0x180288b07  mov     rax, [rax+30h]
0x180288b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180288b10  test    eax, eax
0x180288b12  js      loc_180288C96
0x180288b18  mov     this, [rbp+strPrimaryLanguage._hstring]; string
0x180288b1c  call    cs:__imp_WindowsGetStringLen
0x180288b22  mov     this, [rbp+strPrimaryLanguage._hstring]; string
0x180288b26  xor     edx, edx; length
0x180288b28  mov     ebx, eax
0x180288b2a  call    cs:__imp_WindowsGetStringRawBuffer
0x180288b30  mov     r8, rsi; pstrCloned
0x180288b33  mov     edx, ebx; count
0x180288b35  mov     this, rax; buffer
0x180288b38  call    ?CloneBuffer@xstring_ptr@@SAJPEBGIPEAV1@@Z; xstring_ptr::CloneBuffer(ushort const *,uint,xstring_ptr *)
0x180288b3d  mov     this, [rbp+spLanguages.ptr_]
0x180288b41  test    this, this
0x180288b44  jz      short loc_180288B56
0x180288b46  mov     [rbp+spLanguages.ptr_], r15
0x180288b4a  mov     rax, [this]
0x180288b4d  mov     rax, [rax+10h]
0x180288b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180288b56  mov     this, [rbp+spApplicationLanguagesStatics.ptr_]
0x180288b5a  test    this, this
0x180288b5d  jz      short loc_180288B6F
0x180288b5f  mov     [rbp+spApplicationLanguagesStatics.ptr_], r15
0x180288b63  mov     rax, [this]
0x180288b66  mov     rax, [rax+10h]
0x180288b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180288b6f  mov     this, [rbp+strPrimaryLanguage._hstring]; string
0x180288b73  test    this, this
0x180288b76  jz      short $Cleanup_1635
0x180288b78  call    cs:__imp_WindowsDeleteString
0x180288b7e  mov     pstrDefaultLanguageString, rsi; other
0x180288b81  mov     this, r14; this
0x180288b84  call    ??4xstring_ptr@@QEAAAEAV0@AEBV0@@Z; xstring_ptr::operator=(xstring_ptr const &)
0x180288b89  xor     eax, eax
0x180288b8b  mov     this, [rbp+var_8]
0x180288b8f  xor     this, rsp; StackCookie
0x180288b92  call    __security_check_cookie
0x180288b97  mov     rbx, [rsp+60h+arg_10]
0x180288b9f  add     rsp, 60h
0x180288ba3  pop     r15
0x180288ba5  pop     r14
0x180288ba7  pop     rdi
0x180288ba8  pop     rsi
0x180288ba9  pop     rbp
0x180288baa  retn
0x180288bab  mov     this, [rbp+spLanguages.ptr_]
0x180288baf  test    this, this
0x180288bb2  jz      short loc_180288BC4
0x180288bb4  mov     [rbp+spLanguages.ptr_], r15
0x180288bb8  mov     rax, [this]
0x180288bbb  mov     rax, [rax+10h]
0x180288bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180288bc4  mov     this, [rbp+spApplicationLanguagesStatics.ptr_]
0x180288bc8  test    this, this
0x180288bcb  jz      short loc_180288BDD
0x180288bcd  mov     [rbp+spApplicationLanguagesStatics.ptr_], r15
0x180288bd1  mov     rax, [this]
0x180288bd4  mov     rax, [rax+10h]
0x180288bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180288bdd  mov     this, [rbp+strPrimaryLanguage._hstring]; string
0x180288be1  test    this, this
0x180288be4  jnz     loc_180288C8B
0x180288bea  mov     rax, [rsi]
0x180288bed  mov     dword ptr [rbp+spLanguages.ptr_], r15d
0x180288bf1  test    al, 1
0x180288bf3  jnz     short loc_180288C5B
0x180288bf5  mov     edx, [rax+8]
0x180288bf8  mov     this, [rax]
0x180288bfb  test    edx, edx
0x180288bfd  js      short loc_180288C62
0x180288bff  and     edx, 3FFFFFFFh
0x180288c05  mov     dword ptr [rbp+spLanguages.ptr_], edx
0x180288c08  test    this, this
0x180288c0b  jz      short loc_180288C1D
0x180288c0d  cmp     dword ptr [rbp+spLanguages.ptr_], r15d
0x180288c11  jz      short loc_180288C1D
0x180288c13  cmp     r15w, [this]
0x180288c17  jnz     $Cleanup_1635
0x180288c1d  lea     rax, c_strDefaultLanguageString
0x180288c24  mov     this, rsi; this
0x180288c27  lea     pstrDefaultLanguageString, [rbp+strPrimaryLanguage]; other
0x180288c2b  mov     [rbp+strPrimaryLanguage._hstring], rax
0x180288c2f  call    ??4xstring_ptr@@QEAAAEAV0@$$QEAV0@@Z; xstring_ptr::operator=(xstring_ptr &&)
0x180288c34  lea     this, [rbp+strPrimaryLanguage]; this
0x180288c38  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180288c3d  jmp     $Cleanup_1635
0x180288c42  and     rax, 0FFFFFFFFFFFFFFFEh
0x180288c46  mov     this, rax; string
0x180288c49  lea     pstrDefaultLanguageString, [rbp+spLanguages]; length
0x180288c4d  call    cs:__imp_WindowsGetStringRawBuffer
0x180288c53  mov     this, rax
0x180288c56  jmp     loc_180288A51
0x180288c5b  and     rax, 0FFFFFFFFFFFFFFFEh
0x180288c5f  mov     this, rax; string
0x180288c62  lea     pstrDefaultLanguageString, [rbp+spLanguages]; length
0x180288c66  call    cs:__imp_WindowsGetStringRawBuffer
0x180288c6c  mov     this, rax
0x180288c6f  jmp     short loc_180288C08
0x180288c71  xor     r9d, r9d; lpArguments
0x180288c74  xor     r8d, r8d; nNumberOfArguments
0x180288c77  mov     ecx, 0C000000Dh; dwExceptionCode
0x180288c7c  lea     edx, [r9+1]; dwExceptionFlags
0x180288c80  call    cs:__imp_RaiseException
0x180288c86  jmp     loc_180288AA6
0x180288c8b  call    cs:__imp_WindowsDeleteString
0x180288c91  jmp     loc_180288BEA
0x180288c96  lea     this, [rbp+spLanguages]; this
0x180288c9a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180288c9f  lea     this, [rbp+spApplicationLanguagesStatics]; this
0x180288ca3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180288ca8  lea     this, [rbp+strPrimaryLanguage]; this
0x180288cac  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180288cb1  jmp     loc_180288BEA
```
