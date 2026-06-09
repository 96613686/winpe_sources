# MultiString::InitializeFromStringArray(Windows::Foundation::Collections::IIterable<HSTRING__ *> *)

- ea: `0x180047fe4`
- end: `0x180048427`
- name: `?InitializeFromStringArray@MultiString@@QEAAJPEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z`
- size: `1091`
- prototype: `__int64 __fastcall(HSTRING *string)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180147fb0`
- `0x18016b8b0`

## callees

- `0x180006970`
- `0x180047fe4`
- `0x180048430`
- `0x1800484e0`
- `0x18006a4c8`
- `0x180083c4c`
- `0x180086228`
- `0x18009ab40`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180048063`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180048063`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004816d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004816d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18004836e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18004836e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048220`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048220`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800481a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800481a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800480fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048151`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048348`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800483a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800480fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048151`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048348`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800483a4`

## string_xrefs

- `0x1800480d8`: `onecore\private\com\inc\deployment\RegistrationStoreApiTypes.hpp`
- `0x18004812c`: `onecore\private\com\inc\deployment\RegistrationStoreApiTypes.hpp`
- `0x1800482e4`: `onecore\private\com\inc\deployment\RegistrationStoreApiTypes.hpp`
- `0x180048333`: `onecore\private\com\inc\deployment\RegistrationStoreApiTypes.hpp`
- `0x1800483e1`: `onecore\private\com\inc\deployment\RegistrationStoreApiTypes.hpp`
- `0x180048320`: `StringCchCopy(collectedCharacters + collectedCharaterOffset, collectedCharacterCount - collectedCharaterOffset, sourceCharacters)`
- `0x180048183`: `WindowsCreateString(firstNullTerminator, 1, GetAddressOf())`
- `0x1800483c9`: `wil::make_hstring_from_buffer_nothrow(wistd::move(multiStringBuffer), GetAddressOf())`

## pseudocode

```c
__int64 __fastcall MultiString::InitializeFromStringArray(HSTRING *string, __int64 a2)
{
  UINT32 v4; // esi
  WCHAR *v5; // rdx
  int v6; // ecx
  HSTRING v7; // rcx
  UINT32 StringLen; // eax
  UINT32 v9; // ecx
  unsigned int v10; // ebx
  const char *v11; // rax
  __int64 v12; // rdx
  const char *v14; // rax
  __int64 v15; // rdx
  HRESULT v16; // eax
  const char *v17; // rax
  __int64 v18; // rdx
  UINT32 v19; // r14d
  __int64 *v20; // r8
  int v21; // edx
  PCWSTR StringRawBuffer; // r10
  unsigned __int64 v23; // r8
  WCHAR *v24; // r9
  __int64 v25; // rcx
  WCHAR v26; // ax
  WCHAR *v27; // rcx
  int hstring_from_buffer_nothrow; // eax
  char *v29; // [rsp+28h] [rbp-58h]
  HSTRING_BUFFER bufferHandle; // [rsp+30h] [rbp-50h] BYREF
  WCHAR *charBuffer; // [rsp+38h] [rbp-48h] BYREF
  int v32; // [rsp+40h] [rbp-40h]
  __int64 *v33; // [rsp+48h] [rbp-38h] BYREF
  int v34; // [rsp+50h] [rbp-30h]
  __int64 v35; // [rsp+58h] [rbp-28h] BYREF
  HSTRING stringa; // [rsp+60h] [rbp-20h]
  wil::details::in1diag5 *retaddr; // [rsp+A8h] [rbp+28h]
  char *v38; // [rsp+C0h] [rbp+40h] BYREF
  UINT32 length; // [rsp+C8h] [rbp+48h] BYREF

  v4 = 0;
  LODWORD(v38) = 0;
  wil::iterable_range_nothrow<HSTRING__ *>::iterable_range_nothrow<HSTRING__ *>(&v35, a2, &v38);
  v5 = (WCHAR *)&v35;
  charBuffer = (WCHAR *)&v35;
  v6 = (v35 != 0) - 1;
  v32 = v6;
  while ( **((int **)v5 + 2) >= 0 && v6 != -1 )
  {
    v7 = (HSTRING)*((_QWORD *)v5 + 1);
    if ( !v7 )
    {
      v10 = -2147024809;
      v11 = "!current.IsValid()";
      v12 = 88;
LABEL_11:
      LODWORD(v29) = v10;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\private\\com\\inc\\deployment\\RegistrationStoreApiTypes.hpp",
        "MultiString::InitializeFromStringArray",
        v11,
        v29,
        (int)bufferHandle);
      wil::iterable_range_nothrow<HSTRING__ *>::~iterable_range_nothrow<HSTRING__ *>(&v35);
      return v10;
    }
    StringLen = WindowsGetStringLen(v7);
    v9 = StringLen + 1;
    if ( StringLen + 1 < StringLen )
    {
      v10 = -2147024362;
      v11 = "UInt32Add(lengthIncludingNullTerminator, 1, &lengthIncludingNullTerminator)";
      v12 = 91;
      goto LABEL_11;
    }
    if ( v9 + v4 < v4 )
    {
      v10 = -2147024362;
      v11 = "UInt32Add(collectedCharacterCount, lengthIncludingNullTerminator, &collectedCharacterCount)";
      v12 = 93;
      goto LABEL_11;
    }
    v4 += v9;
    wil::iterable_range_nothrow<HSTRING__ *>::iterable_iterator_nothrow::operator++(&charBuffer);
    v6 = v32;
    v5 = charBuffer;
  }
  WindowsDeleteString(stringa);
  stringa = 0;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v35);
  v10 = (unsigned int)v38;
  if ( (int)v38 < 0 )
  {
    v14 = "hr";
    v15 = 95;
LABEL_15:
    LODWORD(v29) = v10;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\com\\inc\\deployment\\RegistrationStoreApiTypes.hpp",
      "MultiString::InitializeFromStringArray",
      v14,
      v29,
      (int)bufferHandle);
    return v10;
  }
  if ( v4 )
  {
    charBuffer = 0;
    bufferHandle = 0;
    v16 = WindowsPreallocateStringBuffer(v4, &charBuffer, &bufferHandle);
    v10 = v16;
    if ( v16 < 0 )
    {
      LODWORD(v29) = v16;
      v17 = "WindowsPreallocateStringBuffer(collectedCharacterCount, &collectedCharacters, &multiStringBuffer)";
      v18 = 109;
LABEL_45:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\private\\com\\inc\\deployment\\RegistrationStoreApiTypes.hpp",
        "MultiString::InitializeFromStringArray",
        v17,
        v29,
        (int)bufferHandle);
LABEL_46:
      wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&bufferHandle);
      return v10;
    }
    v19 = 0;
    wil::iterable_range_nothrow<HSTRING__ *>::iterable_range_nothrow<HSTRING__ *>(&v35, a2, &v38);
    v20 = &v35;
    v33 = &v35;
    v21 = (v35 != 0) - 1;
    v34 = v21;
    while ( v21 != -1 && *(int *)v20[2] >= 0 )
    {
      length = 0;
      StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)v20[1], &length);
      v23 = v4 - v19;
      v24 = &charBuffer[v19];
      if ( v4 == v19 )
      {
        v10 = -2147024809;
        if ( v4 != v19 )
LABEL_38:
          *v24 = 0;
LABEL_39:
        LODWORD(v29) = v10;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x76,
          (unsigned int)"onecore\\private\\com\\inc\\deployment\\RegistrationStoreApiTypes.hpp",
          "MultiString::InitializeFromStringArray",
          "StringCchCopy(collectedCharacters + collectedCharaterOffset, collectedCharacterCount - collectedCharaterOffset"
          ", sourceCharacters)",
          v29,
          (int)bufferHandle);
        WindowsDeleteString(stringa);
        stringa = 0;
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v35);
        if ( bufferHandle )
          WindowsDeleteStringBuffer(bufferHandle);
        return v10;
      }
      if ( v23 > 0x7FFFFFFF )
      {
        v10 = -2147024809;
        goto LABEL_38;
      }
      v25 = 2147483646;
      do
      {
        if ( !v25 )
          break;
        v26 = *StringRawBuffer;
        if ( !*StringRawBuffer )
          break;
        ++StringRawBuffer;
        *v24++ = v26;
        --v25;
        --v23;
      }
      while ( v23 );
      v27 = v24 - 1;
      if ( v23 )
        v27 = v24;
      *v27 = 0;
      v10 = v23 == 0 ? 0x8007007A : 0;
      if ( !v23 )
        goto LABEL_39;
      if ( v19 + length + 1 < v19 )
      {
        v10 = -2147024362;
        LODWORD(v29) = -2147024362;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x7A,
          (unsigned int)"onecore\\private\\com\\inc\\deployment\\RegistrationStoreApiTypes.hpp",
          "MultiString::InitializeFromStringArray",
          "UInt32Add(collectedCharaterOffset, sourceLength + 1, &collectedCharaterOffset)",
          v29,
          (int)bufferHandle);
        wil::iterable_range_nothrow<HSTRING__ *>::~iterable_range_nothrow<HSTRING__ *>(&v35);
        goto LABEL_46;
      }
      v19 += length + 1;
      wil::iterable_range_nothrow<HSTRING__ *>::iterable_iterator_nothrow::operator++(&v33);
      v21 = v34;
      v20 = v33;
    }
    wil::iterable_range_nothrow<HSTRING__ *>::~iterable_range_nothrow<HSTRING__ *>(&v35);
    v10 = (unsigned int)v38;
    if ( (int)v38 < 0 )
    {
      LODWORD(v29) = (_DWORD)v38;
      v17 = "hr";
      v18 = 124;
      goto LABEL_45;
    }
    WindowsDeleteString(*string);
    *string = 0;
    hstring_from_buffer_nothrow = wil::make_hstring_from_buffer_nothrow(&bufferHandle, string);
    v10 = hstring_from_buffer_nothrow;
    if ( hstring_from_buffer_nothrow < 0 )
    {
      LODWORD(v29) = hstring_from_buffer_nothrow;
      v17 = "wil::make_hstring_from_buffer_nothrow(wistd::move(multiStringBuffer), GetAddressOf())";
      v18 = 126;
      goto LABEL_45;
    }
    wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&bufferHandle);
  }
  else
  {
    WindowsDeleteString(*string);
    *string = 0;
    v10 = WindowsCreateString(&`MultiString::InitializeFromStringArray'::`40'::firstNullTerminator, 1u, string);
    if ( (v10 & 0x80000000) != 0 )
    {
      v14 = "WindowsCreateString(firstNullTerminator, 1, GetAddressOf())";
      v15 = 102;
      goto LABEL_15;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180047fe4  mov     [rsp-28h+arg_0], rbx
0x180047fe9  mov     [rsp-28h+arg_8], rsi
0x180047fee  push    rbp
0x180047fef  push    rdi
0x180047ff0  push    r12
0x180047ff2  push    r14
0x180047ff4  push    r15
0x180047ff6  mov     rbp, rsp
0x180047ff9  sub     rsp, 80h
0x180048000  mov     r15, rdx
0x180048003  mov     rdi, rcx
0x180048006  xor     r12d, r12d
0x180048009  mov     esi, r12d
0x18004800c  mov     dword ptr [rbp+arg_10], r12d
0x180048010  lea     r8, [rbp+arg_10]
0x180048014  lea     rcx, [rbp+var_28]
0x180048018  call    ??0?$iterable_range_nothrow@PEAUHSTRING__@@@wil@@QEAA@PEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@@PEAJ@Z; wil::iterable_range_nothrow<HSTRING__ *>::iterable_range_nothrow<HSTRING__ *>(Windows::Foundation::Collections::IIterable<HSTRING__ *> *,long *)
0x18004801d  mov     rax, [rbp+var_28]
0x180048021  neg     rax
0x180048024  sbb     r8d, r8d
0x180048027  neg     r8d
0x18004802a  dec     r8d
0x18004802d  lea     rdx, [rbp+var_28]
0x180048031  mov     [rbp+charBuffer], rdx
0x180048035  mov     ecx, r12d
0x180048038  cmp     r8d, 0FFFFFFFFh
0x18004803c  setnz   cl
0x18004803f  dec     ecx
0x180048041  mov     [rbp+var_40], ecx
0x180048044  mov     rax, [rdx+10h]
0x180048048  cmp     [rax], r12d
0x18004804b  jl      loc_1800480F8
0x180048051  cmp     ecx, 0FFFFFFFFh
0x180048054  jz      loc_1800480F8
0x18004805a  mov     rcx, [rdx+8]; string
0x18004805e  test    rcx, rcx
0x180048061  jz      short loc_1800480B7
0x180048063  call    cs:__imp_WindowsGetStringLen
0x18004806a  nop     dword ptr [rax+rax+00h]
0x18004806f  lea     ecx, [rax+1]
0x180048072  cmp     ecx, eax
0x180048074  jb      short loc_1800480A4
0x180048076  lea     eax, [rcx+rsi]
0x180048079  cmp     eax, esi
0x18004807b  jb      short loc_180048091
0x18004807d  mov     esi, eax
0x18004807f  lea     rcx, [rbp+charBuffer]
0x180048083  call    ??Eiterable_iterator_nothrow@?$iterable_range_nothrow@PEAUHSTRING__@@@wil@@QEAAAEAV012@XZ; wil::iterable_range_nothrow<HSTRING__ *>::iterable_iterator_nothrow::operator++(void)
0x180048088  mov     ecx, [rbp+var_40]
0x18004808b  mov     rdx, [rbp+charBuffer]
0x18004808f  jmp     short loc_180048044
0x180048091  mov     ebx, 80070216h
0x180048096  lea     rax, aUint32addColle_0; "UInt32Add(collectedCharacterCount, leng"...
0x18004809d  mov     edx, 5Dh ; ']'
0x1800480a2  jmp     short loc_1800480C8
0x1800480a4  mov     ebx, 80070216h
0x1800480a9  lea     rax, aUint32addLengt; "UInt32Add(lengthIncludingNullTerminator"...
0x1800480b0  mov     edx, 5Bh ; '['
0x1800480b5  jmp     short loc_1800480C8
0x1800480b7  mov     ebx, 80070057h
0x1800480bc  lea     rax, aCurrentIsvalid; "!current.IsValid()"
0x1800480c3  mov     edx, 58h ; 'X'; void *
0x1800480c8  mov     dword ptr [rsp+80h+var_58], ebx; char *
0x1800480cc  mov     [rsp+80h+var_60], rax; char *
0x1800480d1  lea     r9, aMultistringIni; "MultiString::InitializeFromStringArray"
0x1800480d8  lea     r8, aOnecorePrivate_3; "onecore\\private\\com\\inc\\deployment"...
0x1800480df  mov     rcx, [rbp+28h]; this
0x1800480e3  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800480e8  lea     rcx, [rbp+var_28]
0x1800480ec  call    ??1?$iterable_range_nothrow@PEAUHSTRING__@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<HSTRING__ *>::~iterable_range_nothrow<HSTRING__ *>(void)
0x1800480f1  mov     eax, ebx
0x1800480f3  jmp     loc_18004840A
0x1800480f8  mov     rcx, [rbp+string]; string
0x1800480fc  call    cs:__imp_WindowsDeleteString
0x180048103  nop     dword ptr [rax+rax+00h]
0x180048108  mov     [rbp+string], r12
0x18004810c  lea     rcx, [rbp+var_28]
0x180048110  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180048115  mov     ebx, dword ptr [rbp+arg_10]
0x180048118  test    ebx, ebx
0x18004811a  jns     short loc_18004814A
0x18004811c  lea     rax, aHr; "hr"
0x180048123  mov     edx, 5Fh ; '_'; void *
0x180048128  mov     dword ptr [rsp+80h+var_58], ebx; char *
0x18004812c  lea     r8, aOnecorePrivate_3; "onecore\\private\\com\\inc\\deployment"...
0x180048133  lea     r9, aMultistringIni; "MultiString::InitializeFromStringArray"
0x18004813a  mov     [rsp+80h+var_60], rax; char *
0x18004813f  mov     rcx, [rbp+28h]; this
0x180048143  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180048148  jmp     short loc_1800480F1
0x18004814a  test    esi, esi
0x18004814c  jnz     short loc_18004818F
0x18004814e  mov     rcx, [rdi]; string
0x180048151  call    cs:__imp_WindowsDeleteString
0x180048158  nop     dword ptr [rax+rax+00h]
0x18004815d  mov     [rdi], r12
0x180048160  mov     r8, rdi; string
0x180048163  lea     edx, [rsi+1]; length
0x180048166  lea     rcx, ?firstNullTerminator@?CI@??InitializeFromStringArray@MultiString@@QEAAJPEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z@4QBGB; sourceString
0x18004816d  call    cs:__imp_WindowsCreateString
0x180048174  nop     dword ptr [rax+rax+00h]
0x180048179  mov     ebx, eax
0x18004817b  test    eax, eax
0x18004817d  jns     loc_180048408
0x180048183  lea     rax, aWindowscreates; "WindowsCreateString(firstNullTerminator"...
0x18004818a  lea     edx, [rsi+66h]
0x18004818d  jmp     short loc_180048128
0x18004818f  mov     [rbp+charBuffer], r12
0x180048193  mov     [rbp+bufferHandle], r12
0x180048197  lea     r8, [rbp+bufferHandle]; bufferHandle
0x18004819b  lea     rdx, [rbp+charBuffer]; charBuffer
0x18004819f  mov     ecx, esi; length
0x1800481a1  call    cs:__imp_WindowsPreallocateStringBuffer
0x1800481a8  nop     dword ptr [rax+rax+00h]
0x1800481ad  mov     ebx, eax
0x1800481af  test    eax, eax
0x1800481b1  jns     short loc_1800481C8
0x1800481b3  mov     dword ptr [rsp+80h+var_58], eax
0x1800481b7  lea     rax, aWindowspreallo; "WindowsPreallocateStringBuffer(collecte"...
0x1800481be  mov     edx, 6Dh ; 'm'
0x1800481c3  jmp     loc_1800483D5
0x1800481c8  mov     r14d, r12d
0x1800481cb  lea     r8, [rbp+arg_10]
0x1800481cf  mov     rdx, r15
0x1800481d2  lea     rcx, [rbp+var_28]
0x1800481d6  call    ??0?$iterable_range_nothrow@PEAUHSTRING__@@@wil@@QEAA@PEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@@PEAJ@Z; wil::iterable_range_nothrow<HSTRING__ *>::iterable_range_nothrow<HSTRING__ *>(Windows::Foundation::Collections::IIterable<HSTRING__ *> *,long *)
0x1800481db  mov     rax, [rbp+var_28]
0x1800481df  neg     rax
0x1800481e2  sbb     ecx, ecx
0x1800481e4  neg     ecx
0x1800481e6  dec     ecx
0x1800481e8  lea     r8, [rbp+var_28]
0x1800481ec  mov     [rbp+var_38], r8
0x1800481f0  mov     edx, r12d
0x1800481f3  cmp     ecx, 0FFFFFFFFh
0x1800481f6  setnz   dl
0x1800481f9  dec     edx
0x1800481fb  mov     [rbp+var_30], edx
0x1800481fe  mov     rax, [r8+10h]
0x180048202  cmp     edx, 0FFFFFFFFh
0x180048205  jz      loc_18004837F
0x18004820b  cmp     [rax], r12d
0x18004820e  jl      loc_18004837F
0x180048214  mov     [rbp+length], r12d
0x180048218  lea     rdx, [rbp+length]; length
0x18004821c  mov     rcx, [r8+8]; string
0x180048220  call    cs:__imp_WindowsGetStringRawBuffer
0x180048227  nop     dword ptr [rax+rax+00h]
0x18004822c  mov     r10, rax
0x18004822f  mov     r8d, esi
0x180048232  sub     r8d, r14d
0x180048235  mov     edx, r14d
0x180048238  mov     rcx, [rbp+charBuffer]
0x18004823c  lea     r9, [rcx+rdx*2]
0x180048240  jz      loc_18004830A
0x180048246  cmp     r8, 7FFFFFFFh
0x18004824d  ja      loc_180048303
0x180048253  mov     ecx, 7FFFFFFEh
0x180048258  test    rcx, rcx
0x18004825b  jz      short loc_18004827B
0x18004825d  movzx   eax, word ptr [r10]
0x180048261  test    ax, ax
0x180048264  jz      short loc_18004827B
0x180048266  add     r10, 2
0x18004826a  mov     [r9], ax
0x18004826e  add     r9, 2
0x180048272  dec     rcx
0x180048275  sub     r8, 1
0x180048279  jnz     short loc_180048258
0x18004827b  lea     rcx, [r9-2]
0x18004827f  test    r8, r8
0x180048282  cmovnz  rcx, r9
0x180048286  mov     [rcx], r12w
0x18004828a  mov     rax, r8
0x18004828d  neg     rax
0x180048290  sbb     ebx, ebx
0x180048292  not     ebx
0x180048294  and     ebx, 8007007Ah
0x18004829a  test    r8, r8
0x18004829d  jz      short loc_180048318
0x18004829f  mov     ecx, [rbp+length]
0x1800482a2  inc     ecx
0x1800482a4  add     ecx, r14d
0x1800482a7  cmp     ecx, r14d
0x1800482aa  jb      short loc_1800482C4
0x1800482ac  mov     r14d, ecx
0x1800482af  lea     rcx, [rbp+var_38]
0x1800482b3  call    ??Eiterable_iterator_nothrow@?$iterable_range_nothrow@PEAUHSTRING__@@@wil@@QEAAAEAV012@XZ; wil::iterable_range_nothrow<HSTRING__ *>::iterable_iterator_nothrow::operator++(void)
0x1800482b8  mov     edx, [rbp+var_30]
0x1800482bb  mov     r8, [rbp+var_38]
0x1800482bf  jmp     loc_1800481FE
0x1800482c4  mov     rcx, [rbp+28h]; this
0x1800482c8  mov     ebx, 80070216h
0x1800482cd  mov     dword ptr [rsp+80h+var_58], ebx; char *
0x1800482d1  lea     rax, aUint32addColle; "UInt32Add(collectedCharaterOffset, sour"...
0x1800482d8  mov     [rsp+80h+var_60], rax; char *
0x1800482dd  lea     r9, aMultistringIni; "MultiString::InitializeFromStringArray"
0x1800482e4  lea     r8, aOnecorePrivate_3; "onecore\\private\\com\\inc\\deployment"...
0x1800482eb  mov     edx, 7Ah ; 'z'; void *
0x1800482f0  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800482f5  lea     rcx, [rbp+var_28]
0x1800482f9  call    ??1?$iterable_range_nothrow@PEAUHSTRING__@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<HSTRING__ *>::~iterable_range_nothrow<HSTRING__ *>(void)
0x1800482fe  jmp     loc_1800483F1
0x180048303  mov     ebx, 80070057h
0x180048308  jmp     short loc_180048314
0x18004830a  mov     ebx, 80070057h
0x18004830f  test    r8, r8
0x180048312  jz      short loc_180048318
0x180048314  mov     [r9], r12w
0x180048318  mov     rcx, [rbp+28h]; this
0x18004831c  mov     dword ptr [rsp+80h+var_58], ebx; char *
0x180048320  lea     rax, aStringcchcopyC_0; "StringCchCopy(collectedCharacters + col"...
0x180048327  mov     [rsp+80h+var_60], rax; char *
0x18004832c  lea     r9, aMultistringIni; "MultiString::InitializeFromStringArray"
0x180048333  lea     r8, aOnecorePrivate_3; "onecore\\private\\com\\inc\\deployment"...
0x18004833a  mov     edx, 76h ; 'v'; void *
0x18004833f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180048344  mov     rcx, [rbp+string]; string
0x180048348  call    cs:__imp_WindowsDeleteString
0x18004834f  nop     dword ptr [rax+rax+00h]
0x180048354  mov     [rbp+string], r12
0x180048358  lea     rcx, [rbp+var_28]
0x18004835c  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180048361  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x180048365  test    rcx, rcx
0x180048368  jz      loc_1800480F1
0x18004836e  call    cs:__imp_WindowsDeleteStringBuffer
0x180048375  nop     dword ptr [rax+rax+00h]
0x18004837a  jmp     loc_1800480F1
0x18004837f  lea     rcx, [rbp+var_28]
0x180048383  call    ??1?$iterable_range_nothrow@PEAUHSTRING__@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<HSTRING__ *>::~iterable_range_nothrow<HSTRING__ *>(void)
0x180048388  mov     ebx, dword ptr [rbp+arg_10]
0x18004838b  test    ebx, ebx
0x18004838d  jns     short loc_1800483A1
0x18004838f  mov     dword ptr [rsp+80h+var_58], ebx
0x180048393  lea     rax, aHr; "hr"
0x18004839a  mov     edx, 7Ch ; '|'
0x18004839f  jmp     short loc_1800483D5
0x1800483a1  mov     rcx, [rdi]; string
0x1800483a4  call    cs:__imp_WindowsDeleteString
0x1800483ab  nop     dword ptr [rax+rax+00h]
0x1800483b0  mov     [rdi], r12
0x1800483b3  mov     rdx, rdi
0x1800483b6  lea     rcx, [rbp+bufferHandle]
0x1800483ba  call    ?make_hstring_from_buffer_nothrow@wil@@YAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAPEAUHSTRING__@@@Z; wil::make_hstring_from_buffer_nothrow(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&,HSTRING__ * *)
0x1800483bf  mov     ebx, eax
0x1800483c1  test    eax, eax
0x1800483c3  jns     short loc_1800483FF
0x1800483c5  mov     dword ptr [rsp+80h+var_58], eax; char *
0x1800483c9  lea     rax, aWilMakeHstring; "wil::make_hstring_from_buffer_nothrow(w"...
0x1800483d0  mov     edx, 7Eh ; '~'; void *
0x1800483d5  mov     [rsp+80h+var_60], rax; char *
0x1800483da  lea     r9, aMultistringIni; "MultiString::InitializeFromStringArray"
0x1800483e1  lea     r8, aOnecorePrivate_3; "onecore\\private\\com\\inc\\deployment"...
0x1800483e8  mov     rcx, [rbp+28h]; this
0x1800483ec  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800483f1  lea     rcx, [rbp+bufferHandle]
0x1800483f5  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x1800483fa  jmp     loc_1800480F1
0x1800483ff  lea     rcx, [rbp+bufferHandle]
0x180048403  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x180048408  xor     eax, eax
0x18004840a  lea     r11, [rsp+80h+var_s0]
0x180048412  mov     rbx, [r11+30h]
0x180048416  mov     rsi, [r11+38h]
0x18004841a  mov     rsp, r11
0x18004841d  pop     r15
0x18004841f  pop     r14
0x180048421  pop     r12
0x180048423  pop     rdi
0x180048424  pop     rbp
0x180048425  retn
```
