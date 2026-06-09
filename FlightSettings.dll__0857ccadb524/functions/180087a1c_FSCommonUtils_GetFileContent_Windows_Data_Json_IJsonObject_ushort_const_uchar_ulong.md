# FSCommonUtils::GetFileContent(Windows::Data::Json::IJsonObject *,ushort const *,uchar * *,ulong *)

- ea: `0x180087a1c`
- end: `0x180087dd1`
- name: `?GetFileContent@FSCommonUtils@@SAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAPEAEPEAK@Z`
- size: `949`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800a6b80`
- `0x1800a95d0`

## callees

- `0x180004b80`
- `0x180005020`
- `0x18000b19c`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800168c8`
- `0x1800328bc`
- `0x180087560`
- `0x180087a1c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180087a8c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180087c0b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180087a8c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180087c0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180087aa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180087c23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180087aa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180087c23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180087c6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180087c6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180087c8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180087c8c`
- `CRYPT32!CryptStringToBinaryW` at `0x180087cc6`
- `CRYPT32!CryptStringToBinaryW` at `0x180087d23`
- `CRYPT32!CryptStringToBinaryW` at `0x180087cc6`
- `CRYPT32!CryptStringToBinaryW` at `0x180087d23`

## string_xrefs

- `0x180087b06`: `onecore\base\flighting\flightsettings\broker\libs\common\fscommonutils.cpp`
- `0x180087b90`: `onecore\base\flighting\flightsettings\broker\libs\common\fscommonutils.cpp`
- `0x180087bbf`: `onecore\base\flighting\flightsettings\broker\libs\common\fscommonutils.cpp`
- `0x180087c4a`: `onecore\base\flighting\flightsettings\broker\libs\common\fscommonutils.cpp`
- `0x180087d51`: `onecore\base\flighting\flightsettings\broker\libs\common\fscommonutils.cpp`
- `0x180087d83`: `onecore\base\flighting\flightsettings\broker\libs\common\fscommonutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FSCommonUtils::GetFileContent(
        struct Windows::Data::Json::IJsonObject *a1,
        const unsigned __int16 *a2,
        HSTRING *a3,
        unsigned int *a4)
{
  int (__fastcall *v7)(struct Windows::Data::Json::IJsonObject *, HSTRING, _QWORD); // rdi
  int v8; // ecx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  HSTRING v12; // rbx
  UINT32 v13; // edi
  UINT32 v14; // eax
  int v15; // eax
  unsigned int v16; // esi
  const struct std::nothrow_t *v17; // rdx
  __int64 (__fastcall *v18)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // rdi
  int v19; // ecx
  int v20; // eax
  __int64 v21; // r9
  __int64 v22; // rdx
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v24; // rsi
  __int64 v25; // rdi
  const char *v26; // r9
  void **unique; // rax
  const struct std::nothrow_t *v28; // rdx
  HSTRING v29; // rbx
  void *v30; // rcx
  const char *v31; // r9
  const struct std::nothrow_t *v33; // rdx
  unsigned int LastError; // edi
  int pcbBinary; // [rsp+28h] [rbp-59h]
  UINT32 v36; // [rsp+48h] [rbp-39h] BYREF
  UINT32 length; // [rsp+4Ch] [rbp-35h] BYREF
  HSTRING v38; // [rsp+50h] [rbp-31h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp-29h] BYREF
  void *v40; // [rsp+60h] [rbp-21h] BYREF
  __int64 v41; // [rsp+68h] [rbp-19h] BYREF
  HSTRING string; // [rsp+70h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  v39 = 0;
  v7 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, _QWORD))(*(_QWORD *)a1 + 72LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
  length = 0;
  if ( (int)ULongLongToUInt(7u, &length) < 0 )
    RaiseException(0xC000000D, v8 - 6, 0, 0);
  WindowsCreateStringReference(L"Content", length, &hstringHeader, &string);
  if ( v7(a1, string, &v39) < 0 )
  {
    v38 = 0;
    v18 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(*(_QWORD *)a1 + 80LL);
    v36 = 0;
    if ( (int)ULongLongToUInt(7u, &v36) < 0 )
      RaiseException(0xC000000D, v19 - 6, 0, 0);
    WindowsCreateStringReference(L"Content", v36, &hstringHeader, &string);
    v20 = v18(a1, string, &v38);
    v10 = v20;
    if ( v20 >= 0 )
    {
      v36 = 0;
      WindowsStringHasEmbeddedNull(v38, (BOOL *)&v36);
      if ( !v36 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v38, 0);
        v24 = StringRawBuffer;
        v25 = -1;
        do
          ++v25;
        while ( StringRawBuffer[v25] );
        length = 0;
        if ( CryptStringToBinaryW(StringRawBuffer, v25, 7u, 0, &length, 0, 0) && length )
        {
          unique = (void **)wil::make_unique_nothrow<unsigned char [0]>(&v40, length);
          v29 = (HSTRING)*unique;
          *unique = 0;
          v30 = v40;
          *(double *)&v40 = 0.0;
          if ( v30 )
            operator delete(v30, v28);
          if ( !CryptStringToBinaryW(v24, v25, 7u, (BYTE *)v29, &length, 0, 0) )
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0xB0,
                          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\fscommonutils.cpp",
                          v31);
            if ( v29 )
              operator delete(v29, v33);
            Windows::Internal::String::~String((Windows::Internal::String *)&v38);
            v10 = LastError;
            goto LABEL_40;
          }
          *a3 = v29;
          *a4 = length;
          Windows::Internal::String::~String((Windows::Internal::String *)&v38);
          goto LABEL_34;
        }
        v10 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0xB5,
                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\fscommonutils.cpp",
                v26);
LABEL_39:
        Windows::Internal::String::~String((Windows::Internal::String *)&v38);
        goto LABEL_40;
      }
      v10 = -2147024809;
      v21 = 2147942487LL;
      v22 = 159;
    }
    else
    {
      v21 = (unsigned int)v20;
      v22 = 157;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\fscommonutils.cpp",
      (const char *)v21,
      pcbBinary);
    goto LABEL_39;
  }
  v41 = 0;
  v9 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
         &v39,
         (__int64)&v41);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v36 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v41 + 56LL))(v41, &v36);
    v10 = v9;
    if ( v9 < 0 )
    {
      v11 = 139;
      goto LABEL_8;
    }
    wil::make_unique_nothrow<unsigned char [0]>(&v38, v36);
    v12 = v38;
    if ( !v38 )
    {
      v10 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\fscommonutils.cpp",
        (const char *)0x8007000ELL,
        pcbBinary);
      goto LABEL_18;
    }
    v13 = 0;
    v14 = v36;
    if ( v36 )
    {
      while ( 1 )
      {
        *(double *)&v40 = 0.0;
        v15 = (*v39)[9](v39, (GUID *)v13, (__int64)&v40);
        v16 = v15;
        if ( v15 < 0 )
          break;
        *((_BYTE *)v12 + v13++) = (int)*(double *)&v40;
        v14 = v36;
        if ( v13 >= v36 )
          goto LABEL_13;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\fscommonutils.cpp",
        (const char *)(unsigned int)v15,
        pcbBinary);
      if ( v12 )
        operator delete(v12, v17);
      v10 = v16;
      goto LABEL_18;
    }
LABEL_13:
    *a3 = v12;
    *a4 = v14;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
LABEL_34:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
    return 0;
  }
  v11 = 136;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\fscommonutils.cpp",
    (const char *)(unsigned int)v9,
    pcbBinary);
LABEL_18:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
LABEL_40:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
  return v10;
}

```

## disassembly

```asm
0x180087a1c  mov     rax, rsp
0x180087a1f  push    rbp
0x180087a20  push    rbx
0x180087a21  push    rsi
0x180087a22  push    rdi
0x180087a23  push    r12
0x180087a25  push    r14
0x180087a27  push    r15
0x180087a29  lea     rbp, [rax-5Fh]
0x180087a2d  sub     rsp, 0A0h
0x180087a34  movaps  xmmword ptr [rax-48h], xmm6
0x180087a38  mov     rax, cs:__security_cookie
0x180087a3f  xor     rax, rsp
0x180087a42  mov     qword ptr [rbp+57h+var_48], rax
0x180087a46  mov     r15, r9
0x180087a49  mov     r14, r8
0x180087a4c  mov     rbx, rcx
0x180087a4f  xor     r12d, r12d
0x180087a52  mov     [rbp+57h+var_80], r12
0x180087a56  mov     rax, [rcx]
0x180087a59  mov     rdi, [rax+48h]
0x180087a5d  lea     rcx, [rbp+57h+var_80]
0x180087a61  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180087a66  mov     [rbp+57h+length], r12d
0x180087a6a  lea     rdx, [rbp+57h+length]; unsigned int *
0x180087a6e  lea     ecx, [r12+7]; unsigned __int64
0x180087a73  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180087a78  mov     esi, 0C000000Dh
0x180087a7d  test    eax, eax
0x180087a7f  jns     short loc_180087A92
0x180087a81  xor     r9d, r9d; lpArguments
0x180087a84  xor     r8d, r8d; nNumberOfArguments
0x180087a87  lea     edx, [rcx-6]; dwExceptionFlags
0x180087a8a  mov     ecx, esi; dwExceptionCode
0x180087a8c  call    cs:__imp_RaiseException
0x180087a92  lea     r9, [rbp+57h+string]; string
0x180087a96  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180087a9a  mov     edx, [rbp+57h+length]; length
0x180087a9d  lea     rcx, sourceString; "Content"
0x180087aa4  call    cs:__imp_WindowsCreateStringReference
0x180087aaa  lea     r8, [rbp+57h+var_80]
0x180087aae  mov     rdx, [rbp+57h+string]
0x180087ab2  mov     rcx, rbx
0x180087ab5  mov     rax, rdi
0x180087ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087abd  test    eax, eax
0x180087abf  js      loc_180087BDF
0x180087ac5  mov     [rbp+57h+var_70], r12
0x180087ac9  lea     rdx, [rbp+57h+var_70]
0x180087acd  lea     rcx, [rbp+57h+var_80]
0x180087ad1  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x180087ad6  mov     ebx, eax
0x180087ad8  test    eax, eax
0x180087ada  jns     short loc_180087AE3
0x180087adc  mov     edx, 88h
0x180087ae1  jmp     short loc_180087B06
0x180087ae3  mov     [rbp+57h+var_90], r12d
0x180087ae7  mov     rcx, [rbp+57h+var_70]
0x180087aeb  mov     rax, [rcx]
0x180087aee  lea     rdx, [rbp+57h+var_90]
0x180087af2  mov     rax, [rax+38h]
0x180087af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087afb  mov     ebx, eax
0x180087afd  test    eax, eax
0x180087aff  jns     short loc_180087B1E
0x180087b01  mov     edx, 8Bh; void *
0x180087b06  lea     r8, aOnecoreBaseFli_61; "onecore\\base\\flighting\\flightsetting"...
0x180087b0d  mov     r9d, eax; char *
0x180087b10  mov     rcx, [rbp+5Fh]; this
0x180087b14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087b19  jmp     loc_180087BD1
0x180087b1e  mov     edx, [rbp+57h+var_90]
0x180087b21  lea     rcx, [rbp+57h+var_88]
0x180087b25  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180087b2a  nop
0x180087b2b  mov     rbx, [rbp+57h+var_88]
0x180087b2f  test    rbx, rbx
0x180087b32  jz      short loc_180087BB3
0x180087b34  mov     edi, r12d
0x180087b37  mov     eax, [rbp+57h+var_90]
0x180087b3a  test    eax, eax
0x180087b3c  jz      short loc_180087B75
0x180087b3e  xorps   xmm6, xmm6
0x180087b41  movsd   [rbp+57h+var_78], xmm6
0x180087b46  mov     rcx, [rbp+57h+var_80]
0x180087b4a  mov     rax, [rcx]
0x180087b4d  lea     r8, [rbp+57h+var_78]
0x180087b51  mov     edx, edi
0x180087b53  mov     rax, [rax+48h]
0x180087b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087b5c  mov     esi, eax
0x180087b5e  test    eax, eax
0x180087b60  js      short loc_180087B89
0x180087b62  cvttsd2si ecx, [rbp+57h+var_78]
0x180087b67  mov     eax, edi
0x180087b69  mov     [rax+rbx], cl
0x180087b6c  inc     edi
0x180087b6e  mov     eax, [rbp+57h+var_90]
0x180087b71  cmp     edi, eax
0x180087b73  jb      short loc_180087B41
0x180087b75  mov     [r14], rbx
0x180087b78  mov     [r15], eax
0x180087b7b  lea     rcx, [rbp+57h+var_70]
0x180087b7f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180087b84  jmp     loc_180087D40
0x180087b89  mov     rcx, [rbp+5Fh]; this
0x180087b8d  mov     r9d, esi; char *
0x180087b90  lea     r8, aOnecoreBaseFli_61; "onecore\\base\\flighting\\flightsetting"...
0x180087b97  mov     edx, 92h; void *
0x180087b9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087ba1  nop
0x180087ba2  test    rbx, rbx
0x180087ba5  jz      short loc_180087BAF
0x180087ba7  mov     rcx, rbx; void *
0x180087baa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180087baf  mov     ebx, esi
0x180087bb1  jmp     short loc_180087BD1
0x180087bb3  mov     rcx, [rbp+5Fh]; this
0x180087bb7  mov     ebx, 8007000Eh
0x180087bbc  mov     r9d, ebx; char *
0x180087bbf  lea     r8, aOnecoreBaseFli_61; "onecore\\base\\flighting\\flightsetting"...
0x180087bc6  mov     edx, 8Eh; void *
0x180087bcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087bd0  nop
0x180087bd1  lea     rcx, [rbp+57h+var_70]
0x180087bd5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180087bda  jmp     loc_180087DA0
0x180087bdf  mov     [rbp+57h+var_88], r12
0x180087be3  mov     rax, [rbx]
0x180087be6  mov     rdi, [rax+50h]
0x180087bea  mov     [rbp+57h+var_90], r12d
0x180087bee  lea     rdx, [rbp+57h+var_90]; unsigned int *
0x180087bf2  mov     ecx, 7; unsigned __int64
0x180087bf7  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180087bfc  test    eax, eax
0x180087bfe  jns     short loc_180087C11
0x180087c00  xor     r9d, r9d; lpArguments
0x180087c03  xor     r8d, r8d; nNumberOfArguments
0x180087c06  lea     edx, [rcx-6]; dwExceptionFlags
0x180087c09  mov     ecx, esi; dwExceptionCode
0x180087c0b  call    cs:__imp_RaiseException
0x180087c11  lea     r9, [rbp+57h+string]; string
0x180087c15  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180087c19  mov     edx, [rbp+57h+var_90]; length
0x180087c1c  lea     rcx, sourceString; "Content"
0x180087c23  call    cs:__imp_WindowsCreateStringReference
0x180087c29  lea     r8, [rbp+57h+var_88]
0x180087c2d  mov     rdx, [rbp+57h+string]
0x180087c31  mov     rcx, rbx
0x180087c34  mov     rax, rdi
0x180087c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087c3c  mov     ebx, eax
0x180087c3e  test    eax, eax
0x180087c40  jns     short loc_180087C5F
0x180087c42  mov     r9d, eax; char *
0x180087c45  mov     edx, 9Dh; void *
0x180087c4a  lea     r8, aOnecoreBaseFli_61; "onecore\\base\\flighting\\flightsetting"...
0x180087c51  mov     rcx, [rbp+5Fh]; this
0x180087c55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087c5a  jmp     loc_180087D96
0x180087c5f  mov     [rbp+57h+var_90], r12d
0x180087c63  lea     rdx, [rbp+57h+var_90]; hasEmbedNull
0x180087c67  mov     rcx, [rbp+57h+var_88]; string
0x180087c6b  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180087c71  cmp     [rbp+57h+var_90], r12d
0x180087c75  jz      short loc_180087C86
0x180087c77  mov     ebx, 80070057h
0x180087c7c  mov     r9d, ebx
0x180087c7f  mov     edx, 9Fh
0x180087c84  jmp     short loc_180087C4A
0x180087c86  xor     edx, edx; length
0x180087c88  mov     rcx, [rbp+57h+var_88]; string
0x180087c8c  call    cs:__imp_WindowsGetStringRawBuffer
0x180087c92  mov     rsi, rax
0x180087c95  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180087c99  inc     rdi
0x180087c9c  cmp     [rax+rdi*2], r12w
0x180087ca1  jnz     short loc_180087C99
0x180087ca3  mov     [rbp+57h+length], r12d
0x180087ca7  mov     [rsp+30h], r12; pdwFlags
0x180087cac  mov     [rsp+0D0h+pdwSkip], r12; pdwSkip
0x180087cb1  lea     rax, [rbp+57h+length]
0x180087cb5  mov     [rsp+0D0h+pcbBinary], rax; pcbBinary
0x180087cba  xor     r9d, r9d; pbBinary
0x180087cbd  lea     r8d, [r9+7]; dwFlags
0x180087cc1  mov     edx, edi; cchString
0x180087cc3  mov     rcx, rsi; pszString
0x180087cc6  call    cs:__imp_CryptStringToBinaryW
0x180087ccc  test    eax, eax
0x180087cce  jz      loc_180087D7F
0x180087cd4  mov     eax, [rbp+57h+length]
0x180087cd7  test    eax, eax
0x180087cd9  jz      loc_180087D7F
0x180087cdf  mov     edx, eax
0x180087ce1  lea     rcx, [rbp+57h+var_78]
0x180087ce5  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180087cea  mov     rbx, [rax]
0x180087ced  mov     [rax], r12
0x180087cf0  mov     rcx, [rbp+57h+var_78]; void *
0x180087cf4  mov     [rbp+57h+var_78], r12
0x180087cf8  test    rcx, rcx
0x180087cfb  jz      short loc_180087D02
0x180087cfd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180087d02  mov     [rsp+30h], r12; pdwFlags
0x180087d07  mov     [rsp+0D0h+pdwSkip], r12; pdwSkip
0x180087d0c  lea     rax, [rbp+57h+length]
0x180087d10  mov     [rsp+0D0h+pcbBinary], rax; pcbBinary
0x180087d15  mov     r9, rbx; pbBinary
0x180087d18  mov     r8d, 7; dwFlags
0x180087d1e  mov     edx, edi; cchString
0x180087d20  mov     rcx, rsi; pszString
0x180087d23  call    cs:__imp_CryptStringToBinaryW
0x180087d29  test    eax, eax
0x180087d2b  jz      short loc_180087D4D
0x180087d2d  mov     [r14], rbx
0x180087d30  mov     eax, [rbp+57h+length]
0x180087d33  mov     [r15], eax
0x180087d36  lea     rcx, [rbp+57h+var_88]; this
0x180087d3a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180087d3f  nop
0x180087d40  lea     rcx, [rbp+57h+var_80]
0x180087d44  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180087d49  xor     eax, eax
0x180087d4b  jmp     short loc_180087DAB
0x180087d4d  mov     rcx, [rbp+5Fh]; this
0x180087d51  lea     r8, aOnecoreBaseFli_61; "onecore\\base\\flighting\\flightsetting"...
0x180087d58  mov     edx, 0B0h; void *
0x180087d5d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180087d62  mov     edi, eax
0x180087d64  test    rbx, rbx
0x180087d67  jz      short loc_180087D72
0x180087d69  mov     rcx, rbx; void *
0x180087d6c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180087d71  nop
0x180087d72  lea     rcx, [rbp+57h+var_88]; this
0x180087d76  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180087d7b  mov     ebx, edi
0x180087d7d  jmp     short loc_180087DA0
0x180087d7f  mov     rcx, [rbp+5Fh]; this
0x180087d83  lea     r8, aOnecoreBaseFli_61; "onecore\\base\\flighting\\flightsetting"...
0x180087d8a  mov     edx, 0B5h; void *
0x180087d8f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180087d94  mov     ebx, eax
0x180087d96  lea     rcx, [rbp+57h+var_88]; this
0x180087d9a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180087d9f  nop
0x180087da0  lea     rcx, [rbp+57h+var_80]
0x180087da4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180087da9  mov     eax, ebx
0x180087dab  mov     rcx, qword ptr [rbp+57h+var_48]
0x180087daf  xor     rcx, rsp; StackCookie
0x180087db2  call    __security_check_cookie
0x180087db7  movaps  xmm6, [rsp+0D0h+var_48+8]
0x180087dbf  add     rsp, 0A0h
0x180087dc6  pop     r15
0x180087dc8  pop     r14
0x180087dca  pop     r12
0x180087dcc  pop     rdi
0x180087dcd  pop     rsi
0x180087dce  pop     rbx
0x180087dcf  pop     rbp
0x180087dd0  retn
```
