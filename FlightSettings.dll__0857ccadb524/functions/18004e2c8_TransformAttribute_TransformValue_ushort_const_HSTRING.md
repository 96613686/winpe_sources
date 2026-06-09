# TransformAttribute::TransformValue(ushort const *,HSTRING__ * *)

- ea: `0x18004e2c8`
- end: `0x18004e686`
- name: `?TransformValue@TransformAttribute@@QEAAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `958`
- prototype: `int(TransformAttribute *__hidden this, const unsigned __int16 *, HSTRING *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003e030`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18001c6f4`
- `0x18001ec48`
- `0x18001ec78`
- `0x18004d298`
- `0x18004d3a4`
- `0x18004d4e0`
- `0x18004d9b4`
- `0x18004e110`
- `0x18004e2c8`
- `0x18004e68c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e340`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e40e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e340`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e40e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e3d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e481`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e64a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e3d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e481`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e64a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004e4bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004e621`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004e4bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004e621`

## string_xrefs

- `0x18004e3a9`: `onecore\base\flighting\flightsettings\broker\libs\ctac\transformattribute.cpp`
- `0x18004e470`: `onecore\base\flighting\flightsettings\broker\libs\ctac\transformattribute.cpp`
- `0x18004e635`: `onecore\base\flighting\flightsettings\broker\libs\ctac\transformattribute.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TransformAttribute::TransformValue(
        TransformAttribute *this,
        const unsigned __int16 *a2,
        HSTRING *a3)
{
  __int64 v6; // r14
  int (__fastcall *v7)(__int64, HSTRING, int *); // r12
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rcx
  const ULONG_PTR *v10; // r9
  char v11; // r14
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // r15
  int (__fastcall *v15)(__int64, HSTRING, HSTRING *); // r12
  const ULONG_PTR *v16; // r9
  int v17; // eax
  unsigned int v18; // edi
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rdx
  int TokenValue; // eax
  char v23; // di
  char v24; // r14
  int v25; // eax
  __int64 v26; // r9
  int v27; // eax
  int v29; // [rsp+20h] [rbp-60h] BYREF
  HSTRING v30; // [rsp+28h] [rbp-58h] BYREF
  UINT32 length; // [rsp+30h] [rbp-50h] BYREF
  PCNZWCH sourceString; // [rsp+38h] [rbp-48h] BYREF
  UINT32 v33[2]; // [rsp+40h] [rbp-40h]
  __int64 v34; // [rsp+48h] [rbp-38h]
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  LOBYTE(v29) = 0;
  v6 = *((_QWORD *)this + 2);
  v7 = *(int (__fastcall **)(__int64, HSTRING, int *))(*(_QWORD *)v6 + 96LL);
  length = 0;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( TransformAttribute::s_pszJsonTagTrim[v9] );
  if ( (int)ULongLongToUInt(v9, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, v10);
  WindowsCreateStringReference(TransformAttribute::s_pszJsonTagTrim, length, &hstringHeader, &string);
  if ( v7(v6, string, &v29) >= 0 )
  {
    v11 = v29;
  }
  else
  {
    v11 = 0;
    LOBYTE(v29) = 0;
  }
  sourceString = 0;
  *(_QWORD *)v33 = 0;
  v34 = 0;
  v12 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          &sourceString,
          a2,
          -1);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v30 = 0;
    v14 = *((_QWORD *)this + 2);
    v15 = *(int (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v14 + 80LL);
    WindowsDeleteString(0);
    v30 = 0;
    length = 0;
    do
      ++v8;
    while ( TransformAttribute::s_pszJsonTagContains[v8] );
    if ( (int)ULongLongToUInt(v8, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, v16);
    WindowsCreateStringReference(TransformAttribute::s_pszJsonTagContains, length, &hstringHeader, &string);
    if ( v15(v14, string, &v30) < 0 )
    {
      if ( (_BYTE)v29 )
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::TrimWhitespace(&sourceString);
      TokenValue = TransformAttribute::Regex((__int64)this, &sourceString);
      v13 = TokenValue;
      v18 = -2147023727;
      if ( TokenValue == -2147023727 )
        goto LABEL_19;
      if ( TokenValue < 0 )
      {
        v21 = 141;
        goto LABEL_59;
      }
      v23 = v11;
      if ( TokenValue != 1 )
        v23 = 1;
      if ( (_BYTE)v29 )
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::TrimWhitespace(&sourceString);
      TokenValue = TransformAttribute::GetTokenValue(this, &sourceString);
      v13 = TokenValue;
      if ( TokenValue < 0 )
      {
        v21 = 155;
        goto LABEL_59;
      }
      if ( TokenValue != 1 )
        v23 = 1;
      if ( (_BYTE)v29 )
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::TrimWhitespace(&sourceString);
      TokenValue = TransformAttribute::SubString(this, &sourceString);
      v13 = TokenValue;
      if ( TokenValue < 0 )
      {
        v21 = 169;
        goto LABEL_59;
      }
      v24 = v23;
      if ( TokenValue != 1 )
        v24 = 1;
      if ( (_BYTE)v29 )
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::TrimWhitespace(&sourceString);
      v25 = TransformAttribute::CheckValue(this, &sourceString, L"Ignore", 0);
      v18 = v25;
      v13 = -2147024883;
      if ( v25 != -2147024883 )
      {
        if ( v25 < 0 )
        {
          v19 = 185;
          goto LABEL_18;
        }
        if ( v25 != 1 )
          v24 = 1;
        LOBYTE(v26) = 1;
        v27 = TransformAttribute::CheckValue(this, &sourceString, L"Allow", v26);
        v18 = v27;
        if ( v27 != -2147024883 )
        {
          if ( v27 < 0 )
          {
            v19 = 195;
            goto LABEL_18;
          }
          if ( v27 == 1 && !v24 )
          {
            v13 = -2147024809;
            v20 = 2147942487LL;
            v21 = 203;
            goto LABEL_60;
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
          TokenValue = WindowsCreateString(sourceString, v33[0], a3);
          v13 = TokenValue;
          if ( TokenValue < 0 )
          {
            v21 = 206;
            goto LABEL_59;
          }
        }
      }
    }
    else
    {
      v17 = TransformAttribute::Contains(this, &sourceString);
      v18 = v17;
      v13 = -2147024883;
      if ( v17 != -2147024883 )
      {
        if ( v17 < 0 )
        {
          v19 = 114;
LABEL_18:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\transformattribute.cpp",
            (const char *)v18,
            v29);
LABEL_19:
          WindowsDeleteString(v30);
          v13 = v18;
LABEL_62:
          v30 = 0;
          goto LABEL_63;
        }
        if ( v17 == 1 && !v11 )
        {
          v13 = -2147024809;
          v20 = 2147942487LL;
          v21 = 123;
LABEL_60:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v21,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\transformattribute.cpp",
            (const char *)v20,
            v29);
          goto LABEL_61;
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
        TokenValue = WindowsCreateString(sourceString, v33[0], a3);
        v13 = TokenValue;
        if ( TokenValue < 0 )
        {
          v21 = 126;
LABEL_59:
          v20 = (unsigned int)TokenValue;
          goto LABEL_60;
        }
      }
    }
LABEL_61:
    WindowsDeleteString(v30);
    goto LABEL_62;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x67,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\transformattribute.cpp",
    (const char *)(unsigned int)v12,
    v29);
LABEL_63:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
  return v13;
}

```

## disassembly

```asm
0x18004e2c8  mov     [rsp-38h+arg_18], rbx
0x18004e2cd  push    rbp
0x18004e2ce  push    rsi
0x18004e2cf  push    rdi
0x18004e2d0  push    r12
0x18004e2d2  push    r13
0x18004e2d4  push    r14
0x18004e2d6  push    r15
0x18004e2d8  mov     rbp, rsp
0x18004e2db  sub     rsp, 80h
0x18004e2e2  mov     rax, cs:__security_cookie
0x18004e2e9  xor     rax, rsp
0x18004e2ec  mov     [rbp+var_10], rax
0x18004e2f0  mov     r13, r8
0x18004e2f3  mov     r15, rdx
0x18004e2f6  mov     rsi, rcx
0x18004e2f9  xor     r9d, r9d
0x18004e2fc  mov     byte ptr [rbp+var_60], r9b
0x18004e300  mov     r14, [rcx+10h]
0x18004e304  mov     rax, [r14]
0x18004e307  mov     r12, [rax+60h]
0x18004e30b  mov     rbx, cs:?s_pszJsonTagTrim@TransformAttribute@@0QEBGEB; ushort const * const TransformAttribute::s_pszJsonTagTrim
0x18004e312  mov     [rbp+length], r9d
0x18004e316  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004e31a  mov     rcx, rdi
0x18004e31d  inc     rcx; unsigned __int64
0x18004e320  cmp     [rbx+rcx*2], r9w
0x18004e325  jnz     short loc_18004E31D
0x18004e327  lea     rdx, [rbp+length]; unsigned int *
0x18004e32b  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004e330  test    eax, eax
0x18004e332  jns     short loc_18004E346
0x18004e334  xor     r8d, r8d; nNumberOfArguments
0x18004e337  lea     edx, [r8+1]; dwExceptionFlags
0x18004e33b  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004e340  call    cs:__imp_RaiseException
0x18004e346  lea     r9, [rbp+string]; string
0x18004e34a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004e34e  mov     edx, [rbp+length]; length
0x18004e351  mov     rcx, rbx; sourceString
0x18004e354  call    cs:__imp_WindowsCreateStringReference
0x18004e35a  lea     r8, [rbp+var_60]
0x18004e35e  mov     rdx, [rbp+string]
0x18004e362  mov     rcx, r14
0x18004e365  mov     rax, r12
0x18004e368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e36d  xor     r12d, r12d
0x18004e370  test    eax, eax
0x18004e372  jns     short loc_18004E37D
0x18004e374  mov     r14b, r12b
0x18004e377  mov     byte ptr [rbp+var_60], r12b
0x18004e37b  jmp     short loc_18004E381
0x18004e37d  mov     r14b, byte ptr [rbp+var_60]
0x18004e381  mov     [rbp+sourceString], r12
0x18004e385  mov     qword ptr [rbp+var_40], r12
0x18004e389  mov     [rbp+var_38], r12
0x18004e38d  mov     r8, rdi
0x18004e390  mov     rdx, r15
0x18004e393  lea     rcx, [rbp+sourceString]
0x18004e397  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18004e39c  mov     ebx, eax
0x18004e39e  test    eax, eax
0x18004e3a0  jns     short loc_18004E3BF
0x18004e3a2  mov     rcx, [rbp+38h]; this
0x18004e3a6  mov     r9d, eax; char *
0x18004e3a9  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\flightsetting"...
0x18004e3b0  mov     edx, 67h ; 'g'; void *
0x18004e3b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e3ba  jmp     loc_18004E654
0x18004e3bf  mov     [rbp+var_58], r12
0x18004e3c3  mov     r15, [rsi+10h]
0x18004e3c7  mov     rax, [r15]
0x18004e3ca  mov     r12, [rax+50h]
0x18004e3ce  xor     ecx, ecx; string
0x18004e3d0  call    cs:__imp_WindowsDeleteString
0x18004e3d6  xor     r9d, r9d
0x18004e3d9  mov     [rbp+var_58], r9
0x18004e3dd  mov     rbx, cs:?s_pszJsonTagContains@TransformAttribute@@0QEBGEB; ushort const * const TransformAttribute::s_pszJsonTagContains
0x18004e3e4  mov     [rbp+length], r9d
0x18004e3e8  inc     rdi
0x18004e3eb  cmp     [rbx+rdi*2], r9w
0x18004e3f0  jnz     short loc_18004E3E8
0x18004e3f2  lea     rdx, [rbp+length]; unsigned int *
0x18004e3f6  mov     rcx, rdi; unsigned __int64
0x18004e3f9  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004e3fe  test    eax, eax
0x18004e400  jns     short loc_18004E414
0x18004e402  xor     r8d, r8d; nNumberOfArguments
0x18004e405  lea     edx, [r8+1]; dwExceptionFlags
0x18004e409  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004e40e  call    cs:__imp_RaiseException
0x18004e414  lea     r9, [rbp+string]; string
0x18004e418  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004e41c  mov     edx, [rbp+length]; length
0x18004e41f  mov     rcx, rbx; sourceString
0x18004e422  call    cs:__imp_WindowsCreateStringReference
0x18004e428  lea     r8, [rbp+var_58]
0x18004e42c  mov     rdx, [rbp+string]
0x18004e430  mov     rcx, r15
0x18004e433  mov     rax, r12
0x18004e436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e43b  xor     r15d, r15d
0x18004e43e  test    eax, eax
0x18004e440  js      loc_18004E4D5
0x18004e446  lea     rdx, [rbp+sourceString]
0x18004e44a  mov     rcx, rsi
0x18004e44d  call    ?Contains@TransformAttribute@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; TransformAttribute::Contains(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18004e452  mov     edi, eax
0x18004e454  mov     ebx, 8007000Dh
0x18004e459  cmp     eax, ebx
0x18004e45b  jz      loc_18004E646
0x18004e461  test    eax, eax
0x18004e463  jns     short loc_18004E48E
0x18004e465  lea     edx, [r15+72h]; void *
0x18004e469  mov     rcx, [rbp+38h]; this
0x18004e46d  mov     r9d, edi; char *
0x18004e470  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\flightsetting"...
0x18004e477  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e47c  nop
0x18004e47d  mov     rcx, [rbp+var_58]; string
0x18004e481  call    cs:__imp_WindowsDeleteString
0x18004e487  mov     ebx, edi
0x18004e489  jmp     loc_18004E650
0x18004e48e  cmp     edi, 1
0x18004e491  jnz     short loc_18004E4A8
0x18004e493  test    r14b, r14b
0x18004e496  jnz     short loc_18004E4A8
0x18004e498  mov     ebx, 80070057h
0x18004e49d  mov     r9d, ebx
0x18004e4a0  lea     edx, [rdi+7Ah]
0x18004e4a3  jmp     loc_18004E635
0x18004e4a8  lea     rcx, [rbp+sourceString]
0x18004e4ac  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18004e4b1  mov     r8, r13; string
0x18004e4b4  mov     edx, [rbp+var_40]; length
0x18004e4b7  mov     rcx, [rbp+sourceString]; sourceString
0x18004e4bb  call    cs:__imp_WindowsCreateString
0x18004e4c1  mov     ebx, eax
0x18004e4c3  test    eax, eax
0x18004e4c5  jns     loc_18004E646
0x18004e4cb  mov     edx, 7Eh ; '~'
0x18004e4d0  jmp     loc_18004E632
0x18004e4d5  cmp     byte ptr [rbp+var_60], r15b
0x18004e4d9  jz      short loc_18004E4E4
0x18004e4db  lea     rcx, [rbp+sourceString]
0x18004e4df  call    ?TrimWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::TrimWhitespace(void)
0x18004e4e4  lea     rdx, [rbp+sourceString]
0x18004e4e8  mov     rcx, rsi
0x18004e4eb  call    ?Regex@TransformAttribute@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; TransformAttribute::Regex(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18004e4f0  mov     ebx, eax
0x18004e4f2  mov     edi, 80070491h
0x18004e4f7  cmp     eax, edi
0x18004e4f9  jz      short loc_18004E47D
0x18004e4fb  test    eax, eax
0x18004e4fd  jns     short loc_18004E509
0x18004e4ff  mov     edx, 8Dh
0x18004e504  jmp     loc_18004E632
0x18004e509  movzx   edi, r14b
0x18004e50d  mov     r12d, 1
0x18004e513  cmp     eax, r12d
0x18004e516  cmovnz  edi, r12d
0x18004e51a  cmp     byte ptr [rbp+var_60], r15b
0x18004e51e  jz      short loc_18004E529
0x18004e520  lea     rcx, [rbp+sourceString]
0x18004e524  call    ?TrimWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::TrimWhitespace(void)
0x18004e529  lea     rdx, [rbp+sourceString]
0x18004e52d  mov     rcx, rsi
0x18004e530  call    ?GetTokenValue@TransformAttribute@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; TransformAttribute::GetTokenValue(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18004e535  mov     ebx, eax
0x18004e537  test    eax, eax
0x18004e539  jns     short loc_18004E545
0x18004e53b  mov     edx, 9Bh
0x18004e540  jmp     loc_18004E632
0x18004e545  cmp     eax, r12d
0x18004e548  cmovnz  edi, r12d
0x18004e54c  cmp     byte ptr [rbp+var_60], r15b
0x18004e550  jz      short loc_18004E55B
0x18004e552  lea     rcx, [rbp+sourceString]
0x18004e556  call    ?TrimWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::TrimWhitespace(void)
0x18004e55b  lea     rdx, [rbp+sourceString]
0x18004e55f  mov     rcx, rsi
0x18004e562  call    ?SubString@TransformAttribute@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; TransformAttribute::SubString(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18004e567  mov     ebx, eax
0x18004e569  test    eax, eax
0x18004e56b  jns     short loc_18004E577
0x18004e56d  mov     edx, 0A9h
0x18004e572  jmp     loc_18004E632
0x18004e577  movzx   r14d, dil
0x18004e57b  cmp     eax, r12d
0x18004e57e  cmovnz  r14d, r12d
0x18004e582  cmp     byte ptr [rbp+var_60], r15b
0x18004e586  jz      short loc_18004E591
0x18004e588  lea     rcx, [rbp+sourceString]
0x18004e58c  call    ?TrimWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::TrimWhitespace(void)
0x18004e591  xor     r9d, r9d
0x18004e594  lea     r8, aIgnore; "Ignore"
0x18004e59b  lea     rdx, [rbp+sourceString]
0x18004e59f  mov     rcx, rsi
0x18004e5a2  call    ?CheckValue@TransformAttribute@@AEAAJAEBV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBG_N@Z; TransformAttribute::CheckValue(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &,ushort const *,bool)
0x18004e5a7  mov     edi, eax
0x18004e5a9  mov     ebx, 8007000Dh
0x18004e5ae  cmp     eax, ebx
0x18004e5b0  jz      loc_18004E646
0x18004e5b6  test    eax, eax
0x18004e5b8  jns     short loc_18004E5C4
0x18004e5ba  mov     edx, 0B9h
0x18004e5bf  jmp     loc_18004E469
0x18004e5c4  cmp     edi, r12d
0x18004e5c7  cmovnz  r14d, r12d
0x18004e5cb  mov     r9b, r12b
0x18004e5ce  lea     r8, aAllow; "Allow"
0x18004e5d5  lea     rdx, [rbp+sourceString]
0x18004e5d9  mov     rcx, rsi
0x18004e5dc  call    ?CheckValue@TransformAttribute@@AEAAJAEBV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBG_N@Z; TransformAttribute::CheckValue(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &,ushort const *,bool)
0x18004e5e1  mov     edi, eax
0x18004e5e3  cmp     eax, ebx
0x18004e5e5  jz      short loc_18004E646
0x18004e5e7  test    eax, eax
0x18004e5e9  jns     short loc_18004E5F5
0x18004e5eb  mov     edx, 0C3h
0x18004e5f0  jmp     loc_18004E469
0x18004e5f5  cmp     edi, r12d
0x18004e5f8  jnz     short loc_18004E60E
0x18004e5fa  test    r14b, r14b
0x18004e5fd  jnz     short loc_18004E60E
0x18004e5ff  mov     ebx, 80070057h
0x18004e604  mov     r9d, ebx
0x18004e607  mov     edx, 0CBh
0x18004e60c  jmp     short loc_18004E635
0x18004e60e  lea     rcx, [rbp+sourceString]
0x18004e612  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18004e617  mov     r8, r13; string
0x18004e61a  mov     edx, [rbp+var_40]; length
0x18004e61d  mov     rcx, [rbp+sourceString]; sourceString
0x18004e621  call    cs:__imp_WindowsCreateString
0x18004e627  mov     ebx, eax
0x18004e629  test    eax, eax
0x18004e62b  jns     short loc_18004E646
0x18004e62d  mov     edx, 0CEh; void *
0x18004e632  mov     r9d, eax; char *
0x18004e635  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\flightsetting"...
0x18004e63c  mov     rcx, [rbp+38h]; this
0x18004e640  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e645  nop
0x18004e646  mov     rcx, [rbp+var_58]; string
0x18004e64a  call    cs:__imp_WindowsDeleteString
0x18004e650  mov     [rbp+var_58], r15
0x18004e654  lea     rcx, [rbp+sourceString]
0x18004e658  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004e65d  mov     eax, ebx
0x18004e65f  mov     rcx, [rbp+var_10]
0x18004e663  xor     rcx, rsp; StackCookie
0x18004e666  call    __security_check_cookie
0x18004e66b  mov     rbx, [rsp+80h+arg_18]
0x18004e673  add     rsp, 80h
0x18004e67a  pop     r15
0x18004e67c  pop     r14
0x18004e67e  pop     r13
0x18004e680  pop     r12
0x18004e682  pop     rdi
0x18004e683  pop     rsi
0x18004e684  pop     rbp
0x18004e685  retn
```
