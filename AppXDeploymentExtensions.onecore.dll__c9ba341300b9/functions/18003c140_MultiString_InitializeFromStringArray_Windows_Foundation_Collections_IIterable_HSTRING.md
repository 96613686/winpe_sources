# MultiString::InitializeFromStringArray(Windows::Foundation::Collections::IIterable<HSTRING__ *> *)

- ea: `0x18003c140`
- end: `0x18003c5da`
- name: `?InitializeFromStringArray@MultiString@@QEAAJPEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z`
- size: `1178`
- prototype: `__int64 __fastcall(HSTRING *string)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003aef0`
- `0x1801b355c`

## callees

- `0x18000b3bc`
- `0x18003c03c`
- `0x18003c140`
- `0x18003c5e0`
- `0x18003c688`
- `0x18009aff4`
- `0x1800b6c74`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18003c4e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18003c4e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18003c32e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18003c32e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18003c1eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18003c1eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003c365`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003c365`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003c57d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003c57d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c253`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c253`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c1b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c31e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c3b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c4c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c565`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c1b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c31e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c3b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c4c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c565`

## string_xrefs

- `0x18003c396`: `onecore\private\com\inc\deployment\RegistrationStoreApiTypes.hpp`
- `0x18003c407`: `onecore\private\com\inc\deployment\RegistrationStoreApiTypes.hpp`
- `0x18003c474`: `onecore\private\com\inc\deployment\RegistrationStoreApiTypes.hpp`
- `0x18003c4ae`: `onecore\private\com\inc\deployment\RegistrationStoreApiTypes.hpp`
- `0x18003c4fe`: `onecore\private\com\inc\deployment\RegistrationStoreApiTypes.hpp`
- `0x18003c541`: `onecore\private\com\inc\deployment\RegistrationStoreApiTypes.hpp`
- `0x18003c5c4`: `onecore\private\com\inc\deployment\RegistrationStoreApiTypes.hpp`
- `0x18003c49b`: `StringCchCopy(collectedCharacters + collectedCharaterOffset, collectedCharacterCount - collectedCharaterOffset, sourceCharacters)`
- `0x18003c33e`: `wil::make_hstring_from_buffer_nothrow(wistd::move(multiStringBuffer), GetAddressOf())`
- `0x18003c531`: `WindowsCreateString(firstNullTerminator, 1, GetAddressOf())`

## pseudocode

```c
__int64 __fastcall MultiString::InitializeFromStringArray(HSTRING *string, __int64 a2)
{
  UINT32 v4; // esi
  WCHAR *v5; // rdx
  int v6; // ecx
  HRESULT v7; // ebx
  UINT32 v8; // r14d
  __int64 *v9; // r8
  int v10; // edx
  PCWSTR StringRawBuffer; // r10
  unsigned __int64 v12; // r8
  WCHAR *v13; // r9
  __int64 v14; // rcx
  WCHAR v15; // ax
  WCHAR *v16; // rcx
  const char *v17; // rax
  __int64 v18; // rdx
  HSTRING v19; // rcx
  UINT32 StringLen; // eax
  UINT32 v21; // ecx
  const char *v22; // rax
  __int64 v23; // rdx
  const char *v25; // rax
  __int64 v26; // rdx
  char *v27; // [rsp+28h] [rbp-31h]
  HSTRING_BUFFER bufferHandle; // [rsp+30h] [rbp-29h] BYREF
  WCHAR *charBuffer; // [rsp+38h] [rbp-21h] BYREF
  int v30; // [rsp+40h] [rbp-19h]
  __int64 *v31; // [rsp+48h] [rbp-11h] BYREF
  HSTRING stringa; // [rsp+50h] [rbp-9h]
  __int64 v33; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING v34; // [rsp+70h] [rbp+17h]
  wil::details::in1diag5 *retaddr; // [rsp+B8h] [rbp+5Fh]
  char *v36; // [rsp+D0h] [rbp+77h] BYREF
  UINT32 length; // [rsp+D8h] [rbp+7Fh] BYREF

  v4 = 0;
  LODWORD(v36) = 0;
  wil::iterable_range_nothrow<HSTRING__ *>::iterable_range_nothrow<HSTRING__ *>(&v31, a2, &v36);
  v5 = (WCHAR *)&v31;
  charBuffer = (WCHAR *)&v31;
  v6 = (v31 != 0) - 1;
  v30 = v6;
  while ( v6 != -1 && **((int **)v5 + 2) >= 0 )
  {
    v19 = (HSTRING)*((_QWORD *)v5 + 1);
    if ( !v19 )
    {
      v7 = -2147024809;
      LODWORD(v27) = -2147024809;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecore\\private\\com\\inc\\deployment\\RegistrationStoreApiTypes.hpp",
        "MultiString::InitializeFromStringArray",
        "!current.IsValid()",
        v27,
        (int)bufferHandle);
      wil::iterable_range_nothrow<HSTRING__ *>::~iterable_range_nothrow<HSTRING__ *>(&v31);
      return (unsigned int)v7;
    }
    StringLen = WindowsGetStringLen(v19);
    v21 = StringLen + 1;
    if ( StringLen + 1 < StringLen )
    {
      v22 = "UInt32Add(lengthIncludingNullTerminator, 1, &lengthIncludingNullTerminator)";
      v23 = 91;
LABEL_28:
      v7 = -2147024362;
      LODWORD(v27) = -2147024362;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\private\\com\\inc\\deployment\\RegistrationStoreApiTypes.hpp",
        "MultiString::InitializeFromStringArray",
        v22,
        v27,
        (int)bufferHandle);
      WindowsDeleteString(stringa);
      stringa = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      return (unsigned int)v7;
    }
    if ( v21 + v4 < v4 )
    {
      v22 = "UInt32Add(collectedCharacterCount, lengthIncludingNullTerminator, &collectedCharacterCount)";
      v23 = 93;
      goto LABEL_28;
    }
    v4 += v21;
    wil::iterable_range_nothrow<HSTRING__ *>::iterable_iterator_nothrow::operator++(&charBuffer);
    v6 = v30;
    v5 = charBuffer;
  }
  WindowsDeleteString(stringa);
  stringa = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  v7 = (int)v36;
  if ( (int)v36 < 0 )
  {
    v25 = "hr";
    v26 = 95;
LABEL_42:
    LODWORD(v27) = v7;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\private\\com\\inc\\deployment\\RegistrationStoreApiTypes.hpp",
      "MultiString::InitializeFromStringArray",
      v25,
      v27,
      (int)bufferHandle);
    return (unsigned int)v7;
  }
  if ( v4 )
  {
    charBuffer = 0;
    bufferHandle = 0;
    v7 = WindowsPreallocateStringBuffer(v4, &charBuffer, &bufferHandle);
    if ( v7 < 0 )
    {
      v17 = "WindowsPreallocateStringBuffer(collectedCharacterCount, &collectedCharacters, &multiStringBuffer)";
      v18 = 109;
    }
    else
    {
      v8 = 0;
      wil::iterable_range_nothrow<HSTRING__ *>::iterable_range_nothrow<HSTRING__ *>(&v33, a2, &v36);
      v9 = &v33;
      v31 = &v33;
      v10 = (v33 != 0) - 1;
      LODWORD(stringa) = v10;
      while ( v10 != -1 && *(int *)v9[2] >= 0 )
      {
        length = 0;
        StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)v9[1], &length);
        v12 = v4 - v8;
        v13 = &charBuffer[v8];
        if ( v4 == v8 )
        {
          v7 = -2147024809;
          if ( v4 != v8 )
LABEL_47:
            *v13 = 0;
LABEL_35:
          LODWORD(v27) = v7;
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)0x76,
            (unsigned int)"onecore\\private\\com\\inc\\deployment\\RegistrationStoreApiTypes.hpp",
            "MultiString::InitializeFromStringArray",
            "StringCchCopy(collectedCharacters + collectedCharaterOffset, collectedCharacterCount - collectedCharaterOffs"
            "et, sourceCharacters)",
            v27,
            (int)bufferHandle);
          WindowsDeleteString(v34);
          v34 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
          goto LABEL_36;
        }
        if ( v12 > 0x7FFFFFFF )
        {
          v7 = -2147024809;
          goto LABEL_47;
        }
        v14 = 2147483646;
        do
        {
          if ( !v14 )
            break;
          v15 = *StringRawBuffer;
          if ( !*StringRawBuffer )
            break;
          ++StringRawBuffer;
          *v13++ = v15;
          --v14;
          --v12;
        }
        while ( v12 );
        v16 = v13 - 1;
        if ( v12 )
          v16 = v13;
        *v16 = 0;
        v7 = v12 == 0 ? 0x8007007A : 0;
        if ( !v12 )
          goto LABEL_35;
        if ( v8 + length + 1 < v8 )
        {
          v7 = -2147024362;
          LODWORD(v27) = -2147024362;
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)0x7A,
            (unsigned int)"onecore\\private\\com\\inc\\deployment\\RegistrationStoreApiTypes.hpp",
            "MultiString::InitializeFromStringArray",
            "UInt32Add(collectedCharaterOffset, sourceLength + 1, &collectedCharaterOffset)",
            v27,
            (int)bufferHandle);
          wil::iterable_range_nothrow<HSTRING__ *>::~iterable_range_nothrow<HSTRING__ *>(&v33);
LABEL_31:
          wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&bufferHandle);
          return (unsigned int)v7;
        }
        v8 += length + 1;
        wil::iterable_range_nothrow<HSTRING__ *>::iterable_iterator_nothrow::operator++(&v31);
        v10 = (int)stringa;
        v9 = v31;
      }
      WindowsDeleteString(v34);
      v34 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      v7 = (int)v36;
      if ( (int)v36 < 0 )
      {
        LODWORD(v27) = (_DWORD)v36;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x7C,
          (unsigned int)"onecore\\private\\com\\inc\\deployment\\RegistrationStoreApiTypes.hpp",
          "MultiString::InitializeFromStringArray",
          "hr",
          v27,
          (int)bufferHandle);
        goto LABEL_31;
      }
      WindowsDeleteString(*string);
      *string = 0;
      v7 = WindowsPromoteStringBuffer(bufferHandle, string);
      if ( v7 >= 0 )
        return 0;
      v17 = "wil::make_hstring_from_buffer_nothrow(wistd::move(multiStringBuffer), GetAddressOf())";
      v18 = 126;
    }
    LODWORD(v27) = v7;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\com\\inc\\deployment\\RegistrationStoreApiTypes.hpp",
      "MultiString::InitializeFromStringArray",
      v17,
      v27,
      (int)bufferHandle);
LABEL_36:
    if ( bufferHandle )
      WindowsDeleteStringBuffer(bufferHandle);
    return (unsigned int)v7;
  }
  WindowsDeleteString(*string);
  *string = 0;
  v7 = WindowsCreateString(&`MultiString::InitializeFromStringArray'::`40'::firstNullTerminator, 1u, string);
  if ( v7 < 0 )
  {
    v25 = "WindowsCreateString(firstNullTerminator, 1, GetAddressOf())";
    v26 = 102;
    goto LABEL_42;
  }
  return 0;
}

```

## disassembly

```asm
0x18003c140  mov     [rsp-8+arg_0], rbx
0x18003c145  mov     [rsp-8+arg_8], rsi
0x18003c14a  push    rbp
0x18003c14b  push    rdi
0x18003c14c  push    r12
0x18003c14e  push    r14
0x18003c150  push    r15
0x18003c152  lea     rbp, [rsp-37h]
0x18003c157  sub     rsp, 90h
0x18003c15e  mov     r15, rdx
0x18003c161  mov     rdi, rcx
0x18003c164  xor     r12d, r12d
0x18003c167  mov     esi, r12d
0x18003c16a  mov     dword ptr [rbp+57h+arg_10], r12d
0x18003c16e  lea     r8, [rbp+57h+arg_10]
0x18003c172  lea     rcx, [rbp+57h+var_68]
0x18003c176  call    ??0?$iterable_range_nothrow@PEAUHSTRING__@@@wil@@QEAA@PEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@@PEAJ@Z; wil::iterable_range_nothrow<HSTRING__ *>::iterable_range_nothrow<HSTRING__ *>(Windows::Foundation::Collections::IIterable<HSTRING__ *> *,long *)
0x18003c17b  mov     rax, [rbp+57h+var_68]
0x18003c17f  neg     rax
0x18003c182  sbb     r8d, r8d
0x18003c185  neg     r8d
0x18003c188  dec     r8d
0x18003c18b  lea     rdx, [rbp+57h+var_68]
0x18003c18f  mov     [rbp+57h+charBuffer], rdx
0x18003c193  mov     ecx, r12d
0x18003c196  cmp     r8d, 0FFFFFFFFh
0x18003c19a  setnz   cl
0x18003c19d  dec     ecx
0x18003c19f  mov     [rbp+57h+var_70], ecx
0x18003c1a2  mov     rax, [rdx+10h]
0x18003c1a6  cmp     ecx, 0FFFFFFFFh
0x18003c1a9  jnz     loc_18003C34F
0x18003c1af  mov     rcx, [rbp+57h+string]; string
0x18003c1b3  call    cs:__imp_WindowsDeleteString
0x18003c1b9  mov     [rbp+57h+string], r12
0x18003c1bd  lea     rcx, [rbp+57h+var_68]
0x18003c1c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c1c6  mov     ebx, dword ptr [rbp+57h+arg_10]
0x18003c1c9  test    ebx, ebx
0x18003c1cb  js      loc_18003C523
0x18003c1d1  test    esi, esi
0x18003c1d3  jz      loc_18003C562
0x18003c1d9  mov     [rbp+57h+charBuffer], r12
0x18003c1dd  mov     [rbp+57h+bufferHandle], r12
0x18003c1e1  lea     r8, [rbp+57h+bufferHandle]; bufferHandle
0x18003c1e5  lea     rdx, [rbp+57h+charBuffer]; charBuffer
0x18003c1e9  mov     ecx, esi; length
0x18003c1eb  call    cs:__imp_WindowsPreallocateStringBuffer
0x18003c1f1  mov     ebx, eax
0x18003c1f3  test    eax, eax
0x18003c1f5  js      loc_18003C4EE
0x18003c1fb  mov     r14d, r12d
0x18003c1fe  lea     r8, [rbp+57h+arg_10]
0x18003c202  mov     rdx, r15
0x18003c205  lea     rcx, [rbp+57h+var_48]
0x18003c209  call    ??0?$iterable_range_nothrow@PEAUHSTRING__@@@wil@@QEAA@PEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@@PEAJ@Z; wil::iterable_range_nothrow<HSTRING__ *>::iterable_range_nothrow<HSTRING__ *>(Windows::Foundation::Collections::IIterable<HSTRING__ *> *,long *)
0x18003c20e  mov     rax, [rbp+57h+var_48]
0x18003c212  neg     rax
0x18003c215  sbb     ecx, ecx
0x18003c217  neg     ecx
0x18003c219  dec     ecx
0x18003c21b  lea     r8, [rbp+57h+var_48]
0x18003c21f  mov     [rbp+57h+var_68], r8
0x18003c223  mov     edx, r12d
0x18003c226  cmp     ecx, 0FFFFFFFFh
0x18003c229  setnz   dl
0x18003c22c  dec     edx
0x18003c22e  mov     dword ptr [rbp+57h+string], edx
0x18003c231  mov     rax, [r8+10h]
0x18003c235  cmp     edx, 0FFFFFFFFh
0x18003c238  jz      loc_18003C2F9
0x18003c23e  cmp     [rax], r12d
0x18003c241  jl      loc_18003C2F9
0x18003c247  mov     [rbp+57h+length], r12d
0x18003c24b  lea     rdx, [rbp+57h+length]; length
0x18003c24f  mov     rcx, [r8+8]; string
0x18003c253  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c259  mov     r10, rax
0x18003c25c  mov     r8d, esi
0x18003c25f  sub     r8d, r14d
0x18003c262  mov     edx, r14d
0x18003c265  mov     rcx, [rbp+57h+charBuffer]
0x18003c269  lea     r9, [rcx+rdx*2]
0x18003c26d  jz      loc_18003C592
0x18003c273  cmp     r8, 7FFFFFFFh
0x18003c27a  ja      loc_18003C58B
0x18003c280  mov     ecx, 7FFFFFFEh
0x18003c285  test    rcx, rcx
0x18003c288  jz      short loc_18003C2A8
0x18003c28a  movzx   eax, word ptr [r10]
0x18003c28e  test    ax, ax
0x18003c291  jz      short loc_18003C2A8
0x18003c293  add     r10, 2
0x18003c297  mov     [r9], ax
0x18003c29b  add     r9, 2
0x18003c29f  dec     rcx
0x18003c2a2  sub     r8, 1
0x18003c2a6  jnz     short loc_18003C285
0x18003c2a8  lea     rcx, [r9-2]
0x18003c2ac  test    r8, r8
0x18003c2af  cmovnz  rcx, r9
0x18003c2b3  mov     [rcx], r12w
0x18003c2b7  mov     rax, r8
0x18003c2ba  neg     rax
0x18003c2bd  sbb     ebx, ebx
0x18003c2bf  not     ebx
0x18003c2c1  and     ebx, 8007007Ah
0x18003c2c7  test    r8, r8
0x18003c2ca  jz      loc_18003C493
0x18003c2d0  mov     ecx, [rbp+57h+length]
0x18003c2d3  inc     ecx
0x18003c2d5  add     ecx, r14d
0x18003c2d8  cmp     ecx, r14d
0x18003c2db  jb      loc_18003C3E7
0x18003c2e1  mov     r14d, ecx
0x18003c2e4  lea     rcx, [rbp+57h+var_68]
0x18003c2e8  call    ??Eiterable_iterator_nothrow@?$iterable_range_nothrow@PEAUHSTRING__@@@wil@@QEAAAEAV012@XZ; wil::iterable_range_nothrow<HSTRING__ *>::iterable_iterator_nothrow::operator++(void)
0x18003c2ed  mov     edx, dword ptr [rbp+57h+string]
0x18003c2f0  mov     r8, [rbp+57h+var_68]
0x18003c2f4  jmp     loc_18003C231
0x18003c2f9  mov     rcx, [rbp+57h+var_40]; string
0x18003c2fd  call    cs:__imp_WindowsDeleteString
0x18003c303  mov     [rbp+57h+var_40], r12
0x18003c307  lea     rcx, [rbp+57h+var_48]
0x18003c30b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c310  mov     ebx, dword ptr [rbp+57h+arg_10]
0x18003c313  test    ebx, ebx
0x18003c315  js      loc_18003C5A9
0x18003c31b  mov     rcx, [rdi]; string
0x18003c31e  call    cs:__imp_WindowsDeleteString
0x18003c324  mov     [rdi], r12
0x18003c327  mov     rdx, rdi; string
0x18003c32a  mov     rcx, [rbp+57h+bufferHandle]; bufferHandle
0x18003c32e  call    cs:__imp_WindowsPromoteStringBuffer
0x18003c334  mov     ebx, eax
0x18003c336  test    eax, eax
0x18003c338  jns     loc_18003C51C
0x18003c33e  lea     rax, aWilMakeHstring_0; "wil::make_hstring_from_buffer_nothrow(w"...
0x18003c345  mov     edx, 7Eh ; '~'
0x18003c34a  jmp     loc_18003C4FA
0x18003c34f  cmp     [rax], r12d
0x18003c352  jl      loc_18003C1AF
0x18003c358  mov     rcx, [rdx+8]; string
0x18003c35c  test    rcx, rcx
0x18003c35f  jz      loc_18003C454
0x18003c365  call    cs:__imp_WindowsGetStringLen
0x18003c36b  lea     ecx, [rax+1]
0x18003c36e  cmp     ecx, eax
0x18003c370  jb      loc_18003C443
0x18003c376  lea     eax, [rcx+rsi]
0x18003c379  cmp     eax, esi
0x18003c37b  jnb     loc_18003C42C
0x18003c381  lea     rax, aUint32addColle_0; "UInt32Add(collectedCharacterCount, leng"...
0x18003c388  mov     edx, 5Dh ; ']'; void *
0x18003c38d  mov     ebx, 80070216h
0x18003c392  mov     dword ptr [rsp+0B0h+var_88], ebx; char *
0x18003c396  lea     r8, aOnecorePrivate_12; "onecore\\private\\com\\inc\\deployment"...
0x18003c39d  lea     r9, aMultistringIni; "MultiString::InitializeFromStringArray"
0x18003c3a4  mov     [rsp+0B0h+var_90], rax; char *
0x18003c3a9  mov     rcx, [rbp+5Fh]; this
0x18003c3ad  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003c3b2  mov     rcx, [rbp+57h+string]; string
0x18003c3b6  call    cs:__imp_WindowsDeleteString
0x18003c3bc  mov     [rbp+57h+string], r12
0x18003c3c0  lea     rcx, [rbp+57h+var_68]
0x18003c3c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c3c9  mov     eax, ebx
0x18003c3cb  lea     r11, [rsp+0B0h+var_20]
0x18003c3d3  mov     rbx, [r11+30h]
0x18003c3d7  mov     rsi, [r11+38h]
0x18003c3db  mov     rsp, r11
0x18003c3de  pop     r15
0x18003c3e0  pop     r14
0x18003c3e2  pop     r12
0x18003c3e4  pop     rdi
0x18003c3e5  pop     rbp
0x18003c3e6  retn
0x18003c3e7  mov     rcx, [rbp+5Fh]; this
0x18003c3eb  mov     ebx, 80070216h
0x18003c3f0  mov     dword ptr [rsp+0B0h+var_88], ebx; char *
0x18003c3f4  lea     rax, aUint32addColle; "UInt32Add(collectedCharaterOffset, sour"...
0x18003c3fb  mov     [rsp+0B0h+var_90], rax; char *
0x18003c400  lea     r9, aMultistringIni; "MultiString::InitializeFromStringArray"
0x18003c407  lea     r8, aOnecorePrivate_12; "onecore\\private\\com\\inc\\deployment"...
0x18003c40e  mov     edx, 7Ah ; 'z'; void *
0x18003c413  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003c418  lea     rcx, [rbp+57h+var_48]
0x18003c41c  call    ??1?$iterable_range_nothrow@PEAUHSTRING__@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<HSTRING__ *>::~iterable_range_nothrow<HSTRING__ *>(void)
0x18003c421  lea     rcx, [rbp+57h+bufferHandle]
0x18003c425  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x18003c42a  jmp     short loc_18003C3C9
0x18003c42c  mov     esi, eax
0x18003c42e  lea     rcx, [rbp+57h+charBuffer]
0x18003c432  call    ??Eiterable_iterator_nothrow@?$iterable_range_nothrow@PEAUHSTRING__@@@wil@@QEAAAEAV012@XZ; wil::iterable_range_nothrow<HSTRING__ *>::iterable_iterator_nothrow::operator++(void)
0x18003c437  mov     ecx, [rbp+57h+var_70]
0x18003c43a  mov     rdx, [rbp+57h+charBuffer]
0x18003c43e  jmp     loc_18003C1A2
0x18003c443  lea     rax, aUint32addLengt; "UInt32Add(lengthIncludingNullTerminator"...
0x18003c44a  mov     edx, 5Bh ; '['
0x18003c44f  jmp     loc_18003C38D
0x18003c454  mov     rcx, [rbp+5Fh]; this
0x18003c458  mov     ebx, 80070057h
0x18003c45d  mov     dword ptr [rsp+0B0h+var_88], ebx; char *
0x18003c461  lea     rax, aCurrentIsvalid; "!current.IsValid()"
0x18003c468  mov     [rsp+0B0h+var_90], rax; char *
0x18003c46d  lea     r9, aMultistringIni; "MultiString::InitializeFromStringArray"
0x18003c474  lea     r8, aOnecorePrivate_12; "onecore\\private\\com\\inc\\deployment"...
0x18003c47b  mov     edx, 58h ; 'X'; void *
0x18003c480  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003c485  lea     rcx, [rbp+57h+var_68]
0x18003c489  call    ??1?$iterable_range_nothrow@PEAUHSTRING__@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<HSTRING__ *>::~iterable_range_nothrow<HSTRING__ *>(void)
0x18003c48e  jmp     loc_18003C3C9
0x18003c493  mov     rcx, [rbp+5Fh]; this
0x18003c497  mov     dword ptr [rsp+0B0h+var_88], ebx; char *
0x18003c49b  lea     rax, aStringcchcopyC; "StringCchCopy(collectedCharacters + col"...
0x18003c4a2  mov     [rsp+0B0h+var_90], rax; char *
0x18003c4a7  lea     r9, aMultistringIni; "MultiString::InitializeFromStringArray"
0x18003c4ae  lea     r8, aOnecorePrivate_12; "onecore\\private\\com\\inc\\deployment"...
0x18003c4b5  mov     edx, 76h ; 'v'; void *
0x18003c4ba  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003c4bf  mov     rcx, [rbp+57h+var_40]; string
0x18003c4c3  call    cs:__imp_WindowsDeleteString
0x18003c4c9  mov     [rbp+57h+var_40], r12
0x18003c4cd  lea     rcx, [rbp+57h+var_48]
0x18003c4d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c4d6  mov     rcx, [rbp+57h+bufferHandle]; bufferHandle
0x18003c4da  test    rcx, rcx
0x18003c4dd  jz      loc_18003C3C9
0x18003c4e3  call    cs:__imp_WindowsDeleteStringBuffer
0x18003c4e9  jmp     loc_18003C3C9
0x18003c4ee  lea     rax, aWindowspreallo_0; "WindowsPreallocateStringBuffer(collecte"...
0x18003c4f5  mov     edx, 6Dh ; 'm'; void *
0x18003c4fa  mov     dword ptr [rsp+0B0h+var_88], ebx; char *
0x18003c4fe  lea     r8, aOnecorePrivate_12; "onecore\\private\\com\\inc\\deployment"...
0x18003c505  lea     r9, aMultistringIni; "MultiString::InitializeFromStringArray"
0x18003c50c  mov     [rsp+0B0h+var_90], rax; char *
0x18003c511  mov     rcx, [rbp+5Fh]; this
0x18003c515  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003c51a  jmp     short loc_18003C4D6
0x18003c51c  xor     eax, eax
0x18003c51e  jmp     loc_18003C3CB
0x18003c523  lea     rax, aHr; "hr"
0x18003c52a  mov     edx, 5Fh ; '_'
0x18003c52f  jmp     short loc_18003C53D
0x18003c531  lea     rax, aWindowscreates_2; "WindowsCreateString(firstNullTerminator"...
0x18003c538  mov     edx, 66h ; 'f'; void *
0x18003c53d  mov     dword ptr [rsp+0B0h+var_88], ebx; char *
0x18003c541  lea     r8, aOnecorePrivate_12; "onecore\\private\\com\\inc\\deployment"...
0x18003c548  lea     r9, aMultistringIni; "MultiString::InitializeFromStringArray"
0x18003c54f  mov     [rsp+0B0h+var_90], rax; char *
0x18003c554  mov     rcx, [rbp+5Fh]; this
0x18003c558  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003c55d  jmp     loc_18003C3C9
0x18003c562  mov     rcx, [rdi]; string
0x18003c565  call    cs:__imp_WindowsDeleteString
0x18003c56b  mov     [rdi], r12
0x18003c56e  mov     r8, rdi; string
0x18003c571  mov     edx, 1; length
0x18003c576  lea     rcx, ?firstNullTerminator@?CI@??InitializeFromStringArray@MultiString@@QEAAJPEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z@4QBGB; sourceString
0x18003c57d  call    cs:__imp_WindowsCreateString
0x18003c583  mov     ebx, eax
0x18003c585  test    eax, eax
0x18003c587  jns     short loc_18003C51C
0x18003c589  jmp     short loc_18003C531
0x18003c58b  mov     ebx, 80070057h
0x18003c590  jmp     short loc_18003C5A0
0x18003c592  mov     ebx, 80070057h
0x18003c597  test    r8, r8
0x18003c59a  jz      loc_18003C493
0x18003c5a0  mov     [r9], r12w
0x18003c5a4  jmp     loc_18003C493
0x18003c5a9  mov     rcx, [rbp+5Fh]; this
0x18003c5ad  mov     dword ptr [rsp+0B0h+var_88], ebx; char *
0x18003c5b1  lea     rax, aHr; "hr"
0x18003c5b8  mov     [rsp+0B0h+var_90], rax; char *
0x18003c5bd  lea     r9, aMultistringIni; "MultiString::InitializeFromStringArray"
0x18003c5c4  lea     r8, aOnecorePrivate_12; "onecore\\private\\com\\inc\\deployment"...
0x18003c5cb  mov     edx, 7Ch ; '|'; void *
0x18003c5d0  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003c5d5  jmp     loc_18003C421
```
