# AttributeFetcher::GetValueFromParsedName(ushort,ushort const *,HSTRING__ * *)

- ea: `0x18003e030`
- end: `0x18003e3eb`
- name: `?GetValueFromParsedName@AttributeFetcher@@AEAAJGPEBGPEAPEAUHSTRING__@@@Z`
- size: `955`
- prototype: `int(AttributeFetcher *__hidden this, unsigned __int16, const unsigned __int16 *, HSTRING *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003e3f4`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800107b0`
- `0x18001c6f4`
- `0x18001ec48`
- `0x18001ec78`
- `0x18003b6c4`
- `0x18003de64`
- `0x18003e030`
- `0x18003f670`
- `0x1800466e0`
- `0x180049e14`
- `0x18004e2c8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e232`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e232`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18003e11a`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18003e11a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e133`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e3c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e133`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e3c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e182`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e182`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e377`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e377`

## string_xrefs

- `0x18003e26c`: `onecore\base\flighting\flightsettings\broker\libs\ctac\InternalAttributes.h`
- `0x18003e0ec`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x18003e38a`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AttributeFetcher::GetValueFromParsedName(
        AttributeFetcher *this,
        unsigned __int16 a2,
        TransformAttribute *a3,
        HSTRING *a4)
{
  const unsigned __int16 *v5; // r14
  unsigned __int16 v6; // r15
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v10; // rax
  int v11; // eax
  int Provider; // ebx
  void *p_lpsz; // rcx
  TransformAttribute *v14; // rbx
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, _QWORD, HSTRING *); // rdi
  __int64 v17; // rax
  const WCHAR *v18; // rsi
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned __int64 i; // rbx
  int v23; // eax
  ProviderManager *v24; // rbx
  struct ICtacProvider *v25; // rdi
  __int64 (__fastcall *v26)(struct ICtacProvider *, const unsigned __int16 *, PCNZWCH *); // rbx
  const unsigned __int16 *v27; // rbx
  UINT32 v28; // edi
  HRESULT v29; // eax
  PCNZWCH *bIgnoreCase; // [rsp+20h] [rbp-89h]
  unsigned __int16 v32; // [rsp+30h] [rbp-79h] BYREF
  TransformAttribute *v33; // [rsp+38h] [rbp-71h] BYREF
  PCNZWCH sourceString; // [rsp+40h] [rbp-69h] BYREF
  UINT32 length[2]; // [rsp+48h] [rbp-61h]
  __int64 v36; // [rsp+50h] [rbp-59h]
  HSTRING string; // [rsp+58h] [rbp-51h] BYREF
  struct ICtacProvider *v38; // [rsp+60h] [rbp-49h] BYREF
  TransformAttribute *v39; // [rsp+68h] [rbp-41h] BYREF
  __int64 v40; // [rsp+70h] [rbp-39h] BYREF
  LPWSTR lpsz; // [rsp+78h] [rbp-31h] BYREF
  DWORD cchLength[2]; // [rsp+80h] [rbp-29h]
  __int64 v43; // [rsp+88h] [rbp-21h]
  _BYTE v44[32]; // [rsp+98h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v5 = (const unsigned __int16 *)a3;
  v6 = a2;
  v32 = a2;
  v33 = a3;
  v39 = a3;
  string = 0;
  v8 = *(_QWORD *)(*((_QWORD *)this + 2) + 120LL);
  v9 = *(int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v8 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&lpsz, &v33);
  if ( v9(v8, *(_QWORD *)(v10 + 24), &string) >= 0 )
    goto LABEL_6;
  lpsz = 0;
  *(_QWORD *)cchLength = 0;
  v43 = 0;
  v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(&lpsz, v5, -1);
  Provider = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
      (const char *)(unsigned int)v11,
      (int)bIgnoreCase);
    p_lpsz = &lpsz;
LABEL_31:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(p_lpsz);
    goto LABEL_32;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpsz);
  v14 = (TransformAttribute *)lpsz;
  CharLowerBuffW(lpsz, cchLength[0]);
  v15 = *(_QWORD *)(*((_QWORD *)this + 2) + 120LL);
  v16 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v15 + 80LL);
  WindowsDeleteString(string);
  string = 0;
  v33 = v14;
  v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v44, &v33);
  LODWORD(v14) = v16(v15, *(_QWORD *)(v17 + 24), &string);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
  if ( (int)v14 >= 0 )
  {
LABEL_6:
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = AttributeFetcher::ParseNamespace(StringRawBuffer, &v32);
    v18 = v5;
    v6 = v32;
  }
  else
  {
    v18 = v5;
  }
  sourceString = 0;
  *(_QWORD *)length = 0;
  v36 = 0;
  if ( v6 )
  {
    v38 = 0;
    v24 = (ProviderManager *)*((_QWORD *)this + 3);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
    Provider = ProviderManager::GetProvider(v24, v6, &v38);
    if ( Provider < 0 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
LABEL_30:
      p_lpsz = &sourceString;
      goto LABEL_31;
    }
    v25 = v38;
    v26 = *(__int64 (__fastcall **)(struct ICtacProvider *, const unsigned __int16 *, PCNZWCH *))(*(_QWORD *)v38 + 24LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
    *(_QWORD *)length = -1;
    v36 = -1;
    Provider = v26(v25, v5, &sourceString);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
    *(_QWORD *)length = -1;
    v36 = -1;
    bIgnoreCase = &sourceString;
    Provider = InternalAttributes::FromInstance<AttributeFetcher>::GetPropertyAlloc(this, v20, v21, v5);
    if ( Provider == -2147217118 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
      *(_QWORD *)length = -1;
      v36 = -1;
      sourceString = 0;
      for ( i = 0; ; ++i )
      {
        if ( i >= 5 )
        {
          Provider = -2147217118;
          goto LABEL_19;
        }
        if ( CompareStringOrdinal(v18, -1, *((LPCWCH *)&AttributeFetcher::s_aAttributesFromStatic + 2 * i), -1, 1) == 2 )
          break;
      }
      v23 = (*(&funcs_18003E256 + 2 * i))((unsigned __int16 **)&sourceString);
      Provider = v23;
      if ( v23 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\InternalAttributes.h",
          (const char *)(unsigned int)v23,
          (int)bIgnoreCase);
    }
  }
LABEL_19:
  if ( Provider < 0 )
    goto LABEL_30;
  v27 = sourceString;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
  v28 = length[0];
  if ( (v6 != 99 || length[0] != 1 || *v27 != 35) && v27 )
  {
    v33 = 0;
    v40 = *(_QWORD *)(*((_QWORD *)this + 2) + 144LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
    if ( (int)Microsoft::WRL::Details::MakeAndInitialize<TransformAttribute,TransformAttribute,Windows::Data::Json::IJsonObject *,unsigned short const * const &>(
                &v33,
                &v40,
                &v39) >= 0 )
    {
      Provider = TransformAttribute::TransformValue(v33, v27, a4);
    }
    else
    {
      v29 = WindowsCreateString(v27, v28, a4);
      Provider = v29;
      if ( v29 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x299,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
          (const char *)(unsigned int)v29,
          (int)bIgnoreCase);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
    goto LABEL_30;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
  Provider = -2147024894;
LABEL_32:
  WindowsDeleteString(string);
  return (unsigned int)Provider;
}

```

## disassembly

```asm
0x18003e030  push    rbp
0x18003e032  push    rbx
0x18003e033  push    rsi
0x18003e034  push    rdi
0x18003e035  push    r12
0x18003e037  push    r13
0x18003e039  push    r14
0x18003e03b  push    r15
0x18003e03d  lea     rbp, [rsp-1Fh]
0x18003e042  sub     rsp, 0C8h
0x18003e049  mov     rax, cs:__security_cookie
0x18003e050  xor     rax, rsp
0x18003e053  mov     [rbp+57h+var_48], rax
0x18003e057  mov     r12, r9
0x18003e05a  mov     r14, r8
0x18003e05d  movzx   r15d, dx
0x18003e061  mov     r13, rcx
0x18003e064  mov     [rbp+57h+var_D0], dx
0x18003e068  mov     [rbp+57h+var_C8], r8
0x18003e06c  mov     [rbp+57h+var_98], r8
0x18003e070  mov     [rbp+57h+string], 0
0x18003e078  mov     rax, [rcx+10h]
0x18003e07c  mov     rdi, [rax+78h]
0x18003e080  mov     rax, [rdi]
0x18003e083  mov     rbx, [rax+50h]
0x18003e087  xor     ecx, ecx; string
0x18003e089  call    cs:__imp_WindowsDeleteString
0x18003e08f  mov     [rbp+57h+string], 0
0x18003e097  lea     rdx, [rbp+57h+var_C8]
0x18003e09b  lea     rcx, [rbp+57h+lpsz]
0x18003e09f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003e0a4  nop
0x18003e0a5  lea     r8, [rbp+57h+string]
0x18003e0a9  mov     rdx, [rax+18h]
0x18003e0ad  mov     rcx, rdi
0x18003e0b0  mov     rax, rbx
0x18003e0b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e0b8  nop
0x18003e0b9  xor     edi, edi
0x18003e0bb  test    eax, eax
0x18003e0bd  jns     loc_18003E17C
0x18003e0c3  mov     [rbp+57h+lpsz], rdi
0x18003e0c7  mov     qword ptr [rbp+57h+cchLength], rdi
0x18003e0cb  mov     [rbp+57h+var_78], rdi
0x18003e0cf  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003e0d3  mov     rdx, r14
0x18003e0d6  lea     rcx, [rbp+57h+lpsz]
0x18003e0da  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003e0df  mov     ebx, eax
0x18003e0e1  test    eax, eax
0x18003e0e3  jns     short loc_18003E107
0x18003e0e5  mov     rcx, [rbp+5Fh]; this
0x18003e0e9  mov     r9d, eax; char *
0x18003e0ec  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003e0f3  mov     edx, 24Fh; void *
0x18003e0f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e0fd  nop
0x18003e0fe  lea     rcx, [rbp+57h+lpsz]
0x18003e102  jmp     loc_18003E3B9
0x18003e107  lea     rcx, [rbp+57h+lpsz]
0x18003e10b  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18003e110  mov     edx, [rbp+57h+cchLength]; cchLength
0x18003e113  mov     rbx, [rbp+57h+lpsz]
0x18003e117  mov     rcx, rbx; lpsz
0x18003e11a  call    cs:__imp_CharLowerBuffW
0x18003e120  mov     rax, [r13+10h]
0x18003e124  mov     rsi, [rax+78h]
0x18003e128  mov     rax, [rsi]
0x18003e12b  mov     rdi, [rax+50h]
0x18003e12f  mov     rcx, [rbp+57h+string]; string
0x18003e133  call    cs:__imp_WindowsDeleteString
0x18003e139  mov     [rbp+57h+string], 0
0x18003e141  mov     [rbp+57h+var_C8], rbx
0x18003e145  lea     rdx, [rbp+57h+var_C8]
0x18003e149  lea     rcx, [rbp+57h+var_68]
0x18003e14d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003e152  nop
0x18003e153  lea     r8, [rbp+57h+string]
0x18003e157  mov     rdx, [rax+18h]
0x18003e15b  mov     rcx, rsi
0x18003e15e  mov     rax, rdi
0x18003e161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e166  mov     ebx, eax
0x18003e168  lea     rcx, [rbp+57h+lpsz]
0x18003e16c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003e171  xor     edi, edi
0x18003e173  test    ebx, ebx
0x18003e175  jns     short loc_18003E17C
0x18003e177  mov     rsi, r14
0x18003e17a  jmp     short loc_18003E19F
0x18003e17c  xor     edx, edx; length
0x18003e17e  mov     rcx, [rbp+57h+string]; string
0x18003e182  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e188  lea     rdx, [rbp+57h+var_D0]; unsigned __int16 *
0x18003e18c  mov     rcx, rax; unsigned __int16 *
0x18003e18f  call    ?ParseNamespace@AttributeFetcher@@CAPEBGPEBGPEAG@Z; AttributeFetcher::ParseNamespace(ushort const *,ushort *)
0x18003e194  mov     r14, rax
0x18003e197  mov     rsi, rax
0x18003e19a  movzx   r15d, [rbp+57h+var_D0]
0x18003e19f  mov     [rbp+57h+sourceString], rdi
0x18003e1a3  mov     qword ptr [rbp+57h+length], rdi
0x18003e1a7  mov     [rbp+57h+var_B0], rdi
0x18003e1ab  cmp     di, r15w
0x18003e1af  jnz     loc_18003E284
0x18003e1b5  lea     rcx, [rbp+57h+sourceString]
0x18003e1b9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003e1be  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003e1c2  mov     qword ptr [rbp+57h+length], rax
0x18003e1c6  mov     [rbp+57h+var_B0], rax
0x18003e1ca  lea     rax, [rbp+57h+sourceString]
0x18003e1ce  mov     qword ptr [rsp+100h+bIgnoreCase], rax
0x18003e1d3  mov     r9, r14
0x18003e1d6  mov     rcx, r13
0x18003e1d9  call    ?GetPropertyAlloc@?$FromInstance@VAttributeFetcher@@@InternalAttributes@@SAJPEAVAttributeFetcher@@QEBU12@_KPEBGPEAPEAG@Z; InternalAttributes::FromInstance<AttributeFetcher>::GetPropertyAlloc(AttributeFetcher *,InternalAttributes::FromInstance<AttributeFetcher> const * const,unsigned __int64,ushort const *,ushort * *)
0x18003e1de  mov     ebx, eax
0x18003e1e0  mov     r14d, 80041122h
0x18003e1e6  cmp     eax, r14d
0x18003e1e9  jnz     loc_18003E2F6
0x18003e1ef  lea     rcx, [rbp+57h+sourceString]
0x18003e1f3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003e1f8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003e1fc  mov     qword ptr [rbp+57h+length], rax
0x18003e200  mov     [rbp+57h+var_B0], rax
0x18003e204  mov     [rbp+57h+sourceString], rdi
0x18003e208  mov     rbx, rdi
0x18003e20b  lea     rcx, ?s_aAttributesFromStatic@AttributeFetcher@@0QBUFromStatic@InternalAttributes@@B; InternalAttributes::FromStatic const near * const AttributeFetcher::s_aAttributesFromStatic
0x18003e212  cmp     rbx, 5
0x18003e216  jnb     short loc_18003E27F
0x18003e218  mov     rdi, rbx
0x18003e21b  add     rdi, rdi
0x18003e21e  mov     [rsp+100h+bIgnoreCase], 1; int
0x18003e226  mov     r9d, eax; cchCount2
0x18003e229  mov     r8, [rcx+rdi*8]; lpString2
0x18003e22d  mov     edx, eax; cchCount1
0x18003e22f  mov     rcx, rsi; lpString1
0x18003e232  call    cs:__imp_CompareStringOrdinal
0x18003e238  cmp     eax, 2
0x18003e23b  jz      short loc_18003E246
0x18003e23d  inc     rbx
0x18003e240  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003e244  jmp     short loc_18003E20B
0x18003e246  lea     rcx, [rbp+57h+sourceString]; unsigned __int16 **
0x18003e24a  lea     rax, ?s_aAttributesFromStatic@AttributeFetcher@@0QBUFromStatic@InternalAttributes@@B; InternalAttributes::FromStatic const near * const AttributeFetcher::s_aAttributesFromStatic
0x18003e251  mov     rax, ds:(funcs_18003E256 - 1800CAD90h)[rax+rdi*8]
0x18003e256  call    _guard_dispatch_icall$thunk$10345483385596137414; TempHomelessAttr::get_DeviceFamily(ushort * *) ...
0x18003e25b  mov     ebx, eax
0x18003e25d  test    eax, eax
0x18003e25f  jns     loc_18003E2F6
0x18003e265  mov     rcx, [rbp+5Fh]; this
0x18003e269  mov     r9d, eax; char *
0x18003e26c  lea     r8, aOnecoreBaseFli_28; "onecore\\base\\flighting\\flightsetting"...
0x18003e273  mov     edx, 1Ch; void *
0x18003e278  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e27d  jmp     short loc_18003E2F6
0x18003e27f  mov     ebx, r14d
0x18003e282  jmp     short loc_18003E2F6
0x18003e284  mov     [rbp+57h+var_A0], rdi
0x18003e288  mov     rbx, [r13+18h]
0x18003e28c  lea     rcx, [rbp+57h+var_A0]
0x18003e290  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003e295  lea     r8, [rbp+57h+var_A0]; struct ICtacProvider **
0x18003e299  movzx   edx, r15w; unsigned __int16
0x18003e29d  mov     rcx, rbx; this
0x18003e2a0  call    ?GetProvider@ProviderManager@@QEAAJGPEAPEAUICtacProvider@@@Z; ProviderManager::GetProvider(ushort,ICtacProvider * *)
0x18003e2a5  mov     ebx, eax
0x18003e2a7  test    eax, eax
0x18003e2a9  jns     short loc_18003E2B9
0x18003e2ab  lea     rcx, [rbp+57h+var_A0]
0x18003e2af  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003e2b4  jmp     loc_18003E3B5
0x18003e2b9  mov     rdi, [rbp+57h+var_A0]
0x18003e2bd  mov     rax, [rdi]
0x18003e2c0  mov     rbx, [rax+18h]
0x18003e2c4  lea     rcx, [rbp+57h+sourceString]
0x18003e2c8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003e2cd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003e2d1  mov     qword ptr [rbp+57h+length], rax
0x18003e2d5  mov     [rbp+57h+var_B0], rax
0x18003e2d9  lea     r8, [rbp+57h+sourceString]
0x18003e2dd  mov     rdx, r14
0x18003e2e0  mov     rcx, rdi
0x18003e2e3  mov     rax, rbx
0x18003e2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2eb  mov     ebx, eax
0x18003e2ed  lea     rcx, [rbp+57h+var_A0]
0x18003e2f1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003e2f6  test    ebx, ebx
0x18003e2f8  js      loc_18003E3B5
0x18003e2fe  mov     rbx, [rbp+57h+sourceString]
0x18003e302  lea     rcx, [rbp+57h+sourceString]
0x18003e306  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18003e30b  mov     edi, [rbp+57h+length]
0x18003e30e  cmp     r15w, 63h ; 'c'
0x18003e313  jnz     short loc_18003E335
0x18003e315  cmp     edi, 1
0x18003e318  jnz     short loc_18003E335
0x18003e31a  lea     eax, [rdi+22h]
0x18003e31d  cmp     ax, [rbx]
0x18003e320  jnz     short loc_18003E335
0x18003e322  lea     rcx, [rbp+57h+sourceString]
0x18003e326  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003e32b  mov     ebx, 80070002h
0x18003e330  jmp     loc_18003E3BF
0x18003e335  test    rbx, rbx
0x18003e338  jz      short loc_18003E322
0x18003e33a  mov     [rbp+57h+var_C8], 0
0x18003e342  mov     rax, [r13+10h]
0x18003e346  mov     r9, [rax+90h]
0x18003e34d  mov     [rbp+57h+var_90], r9
0x18003e351  lea     rcx, [rbp+57h+var_C8]
0x18003e355  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003e35a  lea     r8, [rbp+57h+var_98]
0x18003e35e  lea     rdx, [rbp+57h+var_90]
0x18003e362  lea     rcx, [rbp+57h+var_C8]
0x18003e366  call    ??$MakeAndInitialize@VTransformAttribute@@V1@PEAUIJsonObject@Json@Data@Windows@@AEBQEBG@Details@WRL@Microsoft@@YAJPEAPEAVTransformAttribute@@$$QEAPEAUIJsonObject@Json@Data@Windows@@AEBQEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<TransformAttribute,TransformAttribute,Windows::Data::Json::IJsonObject *,ushort const * const &>(TransformAttribute * *,Windows::Data::Json::IJsonObject * &&,ushort const * const &)
0x18003e36b  mov     r8, r12; HSTRING *
0x18003e36e  test    eax, eax
0x18003e370  jns     short loc_18003E39D
0x18003e372  mov     edx, edi; length
0x18003e374  mov     rcx, rbx; sourceString
0x18003e377  call    cs:__imp_WindowsCreateString
0x18003e37d  mov     ebx, eax
0x18003e37f  test    eax, eax
0x18003e381  jns     short loc_18003E3AB
0x18003e383  mov     rcx, [rbp+5Fh]; this
0x18003e387  mov     r9d, eax; char *
0x18003e38a  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003e391  mov     edx, 299h; void *
0x18003e396  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e39b  jmp     short loc_18003E3AB
0x18003e39d  mov     rdx, rbx; unsigned __int16 *
0x18003e3a0  mov     rcx, [rbp+57h+var_C8]; this
0x18003e3a4  call    ?TransformValue@TransformAttribute@@QEAAJPEBGPEAPEAUHSTRING__@@@Z; TransformAttribute::TransformValue(ushort const *,HSTRING__ * *)
0x18003e3a9  mov     ebx, eax
0x18003e3ab  lea     rcx, [rbp+57h+var_C8]
0x18003e3af  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003e3b4  nop
0x18003e3b5  lea     rcx, [rbp+57h+sourceString]
0x18003e3b9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003e3be  nop
0x18003e3bf  mov     rcx, [rbp+57h+string]; string
0x18003e3c3  call    cs:__imp_WindowsDeleteString
0x18003e3c9  mov     eax, ebx
0x18003e3cb  mov     rcx, [rbp+57h+var_48]
0x18003e3cf  xor     rcx, rsp; StackCookie
0x18003e3d2  call    __security_check_cookie
0x18003e3d7  add     rsp, 0C8h
0x18003e3de  pop     r15
0x18003e3e0  pop     r14
0x18003e3e2  pop     r13
0x18003e3e4  pop     r12
0x18003e3e6  pop     rdi
0x18003e3e7  pop     rsi
0x18003e3e8  pop     rbx
0x18003e3e9  pop     rbp
0x18003e3ea  retn
```
