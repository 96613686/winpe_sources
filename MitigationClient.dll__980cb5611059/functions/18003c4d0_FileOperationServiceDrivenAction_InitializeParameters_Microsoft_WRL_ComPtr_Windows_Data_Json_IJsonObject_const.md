# FileOperationServiceDrivenAction::InitializeParameters(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x18003c4d0`
- end: `0x18003c792`
- name: `?InitializeParameters@FileOperationServiceDrivenAction@@MEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `706`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000a6e0`
- `0x18001208c`
- `0x18001e164`
- `0x18002407c`
- `0x1800253bc`
- `0x180026930`
- `0x18002c090`
- `0x18003c1ac`
- `0x18003c4d0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003c655`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003c655`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c688`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c6d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c688`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c6d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003c63c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003c63c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c582`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c582`

## string_xrefs

- `0x18003c539`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\fileoperationservicedrivenaction.cpp`
- `0x18003c59f`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\fileoperationservicedrivenaction.cpp`
- `0x18003c742`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\fileoperationservicedrivenaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FileOperationServiceDrivenAction::InitializeParameters(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, HSTRING, HSTRING *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  const unsigned __int16 *StringRawBuffer; // rax
  int FileName; // eax
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, HSTRING, __int64); // rdi
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, HSTRING, __int64); // rdi
  __int64 v19; // r9
  __int64 v21; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+28h] [rbp-48h] BYREF
  unsigned __int16 *v23; // [rsp+30h] [rbp-40h] BYREF
  __int64 v24; // [rsp+38h] [rbp-38h]
  __int64 v25; // [rsp+40h] [rbp-30h]
  HSTRING v26; // [rsp+48h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  string = 0;
  v4 = *a2;
  v5 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)*a2 + 80LL);
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)&v26,
    FileOperationServiceDrivenAction::s_fullPathTag);
  v6 = v5(v4, v26, &string);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v23 = 0;
    v24 = 0;
    v25 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v23);
    v24 = -1;
    v25 = -1;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    FileName = FileUtils::GetFileName(StringRawBuffer, &v23);
    v7 = FileName;
    if ( FileName < 0 )
    {
      v10 = 53;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\fileoperationservicedrivenaction.cpp",
        (const char *)(unsigned int)FileName,
        v21);
LABEL_21:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v23);
      goto LABEL_22;
    }
    FileName = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                 a1 + 56,
                 L"%s\\%s",
                 *(_QWORD *)(*(_QWORD *)(a1 + 136) + 88LL),
                 v23);
    v7 = FileName;
    if ( FileName < 0 )
    {
      v10 = 56;
      goto LABEL_5;
    }
    v21 = 0;
    v11 = *a2;
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)*a2 + 80LL);
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)&v26,
      FileOperationServiceDrivenAction::s_operationTag);
    v13 = v12(v11, v26, &v21);
    v7 = v13;
    if ( v13 >= 0 )
    {
      if ( WindowsCreateStringReference(L"DOWNLOAD", 8u, &hstringHeader, &v26) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      if ( (unsigned int)Windows::Internal::String::CompareOrdinal(
                           (Windows::Internal::String *)&v21,
                           (const struct Windows::Internal::String *)&v26) )
      {
        v7 = -2135164404;
        v19 = 2159802892LL;
        v14 = 69;
        goto LABEL_20;
      }
      *(_DWORD *)(a1 + 144) = 0;
      v15 = *a2;
      v16 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)*a2 + 80LL);
      WindowsDeleteString(*(HSTRING *)(a1 + 104));
      *(_QWORD *)(a1 + 104) = 0;
      Windows::Internal::StringReference::_ConstructorHelper(
        (Windows::Internal::StringReference *)&v26,
        FileOperationServiceDrivenAction::s_fileDcatDownloadUrlTag);
      v13 = v16(v15, v26, a1 + 104);
      v7 = v13;
      if ( v13 >= 0 )
      {
        v17 = *a2;
        v18 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)*a2 + 80LL);
        WindowsDeleteString(*(HSTRING *)(a1 + 112));
        *(_QWORD *)(a1 + 112) = 0;
        Windows::Internal::StringReference::_ConstructorHelper(
          (Windows::Internal::StringReference *)&v26,
          FileOperationServiceDrivenAction::s_fileSha256HashTag);
        v13 = v18(v17, v26, a1 + 112);
        v7 = v13;
        if ( v13 >= 0 )
        {
          Windows::Internal::String::~String((Windows::Internal::String *)&v21);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v23);
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
          return 0;
        }
        v14 = 65;
      }
      else
      {
        v14 = 64;
      }
    }
    else
    {
      v14 = 59;
    }
    v19 = (unsigned int)v13;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\fileoperationservicedrivenaction.cpp",
      (const char *)v19,
      v21);
    Windows::Internal::String::~String((Windows::Internal::String *)&v21);
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x32,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\fileoperationservicedrivenaction.cpp",
    (const char *)(unsigned int)v6,
    v21);
LABEL_22:
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  return v7;
}

```

## disassembly

```asm
0x18003c4d0  mov     [rsp-28h+arg_10], rbx
0x18003c4d5  push    rbp
0x18003c4d6  push    rsi
0x18003c4d7  push    rdi
0x18003c4d8  push    r14
0x18003c4da  push    r15
0x18003c4dc  mov     rbp, rsp
0x18003c4df  sub     rsp, 70h
0x18003c4e3  mov     rax, cs:__security_cookie
0x18003c4ea  xor     rax, rsp
0x18003c4ed  mov     [rbp+var_8], rax
0x18003c4f1  mov     r15, rdx
0x18003c4f4  mov     r14, rcx
0x18003c4f7  mov     [rbp+string], 0
0x18003c4ff  mov     rdi, [rdx]
0x18003c502  mov     rax, [rdi]
0x18003c505  mov     rbx, [rax+50h]
0x18003c509  mov     rdx, cs:?s_fullPathTag@FileOperationServiceDrivenAction@@0QEBGEB; unsigned __int16 *
0x18003c510  lea     rcx, [rbp+var_28]; this
0x18003c514  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003c519  lea     r8, [rbp+string]
0x18003c51d  mov     rdx, [rbp+var_28]
0x18003c521  mov     rcx, rdi
0x18003c524  mov     rax, rbx
0x18003c527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c52c  mov     ebx, eax
0x18003c52e  test    eax, eax
0x18003c530  jns     short loc_18003C54F
0x18003c532  mov     rcx, [rbp+28h]; this
0x18003c536  mov     r9d, eax; char *
0x18003c539  lea     r8, aOnecoreBaseDia_22; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003c540  mov     edx, 32h ; '2'; void *
0x18003c545  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c54a  jmp     loc_18003C767
0x18003c54f  mov     [rbp+var_40], 0
0x18003c557  mov     [rbp+var_38], 0
0x18003c55f  mov     [rbp+var_30], 0
0x18003c567  lea     rcx, [rbp+var_40]
0x18003c56b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003c570  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003c574  mov     [rbp+var_38], rax
0x18003c578  mov     [rbp+var_30], rax
0x18003c57c  xor     edx, edx; length
0x18003c57e  mov     rcx, [rbp+string]; string
0x18003c582  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c588  lea     rdx, [rbp+var_40]; unsigned __int16 **
0x18003c58c  mov     rcx, rax; unsigned __int16 *
0x18003c58f  call    ?GetFileName@FileUtils@@SAJPEBGPEAPEAG@Z; FileUtils::GetFileName(ushort const *,ushort * *)
0x18003c594  mov     ebx, eax
0x18003c596  test    eax, eax
0x18003c598  jns     short loc_18003C5B7
0x18003c59a  mov     edx, 35h ; '5'; void *
0x18003c59f  lea     r8, aOnecoreBaseDia_22; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003c5a6  mov     r9d, eax; char *
0x18003c5a9  mov     rcx, [rbp+28h]; this
0x18003c5ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c5b2  jmp     loc_18003C75D
0x18003c5b7  mov     r8, [r14+88h]
0x18003c5be  lea     rcx, [r14+38h]
0x18003c5c2  mov     r9, [rbp+var_40]
0x18003c5c6  mov     r8, [r8+58h]
0x18003c5ca  lea     rdx, aSS_0; "%s\\%s"
0x18003c5d1  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18003c5d6  mov     ebx, eax
0x18003c5d8  test    eax, eax
0x18003c5da  jns     short loc_18003C5E3
0x18003c5dc  mov     edx, 38h ; '8'
0x18003c5e1  jmp     short loc_18003C59F
0x18003c5e3  mov     [rbp+var_50], 0
0x18003c5eb  mov     rdi, [r15]
0x18003c5ee  mov     rax, [rdi]
0x18003c5f1  mov     rbx, [rax+50h]
0x18003c5f5  mov     rdx, cs:?s_operationTag@FileOperationServiceDrivenAction@@0QEBGEB; unsigned __int16 *
0x18003c5fc  lea     rcx, [rbp+var_28]; this
0x18003c600  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003c605  lea     r8, [rbp+var_50]
0x18003c609  mov     rdx, [rbp+var_28]
0x18003c60d  mov     rcx, rdi
0x18003c610  mov     rax, rbx
0x18003c613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c618  mov     ebx, eax
0x18003c61a  test    eax, eax
0x18003c61c  jns     short loc_18003C628
0x18003c61e  mov     edx, 3Bh ; ';'
0x18003c623  jmp     loc_18003C70F
0x18003c628  lea     r9, [rbp+var_28]; string
0x18003c62c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003c630  mov     edx, 8; length
0x18003c635  lea     rcx, sourceString; "DOWNLOAD"
0x18003c63c  call    cs:__imp_WindowsCreateStringReference
0x18003c642  test    eax, eax
0x18003c644  jns     short loc_18003C65B
0x18003c646  xor     r9d, r9d; lpArguments
0x18003c649  xor     r8d, r8d; nNumberOfArguments
0x18003c64c  lea     edx, [r9+1]; dwExceptionFlags
0x18003c650  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003c655  call    cs:__imp_RaiseException
0x18003c65b  lea     rdx, [rbp+var_28]; struct Windows::Internal::String *
0x18003c65f  lea     rcx, [rbp+var_50]; this
0x18003c663  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x18003c668  test    eax, eax
0x18003c66a  jnz     loc_18003C735
0x18003c670  mov     [r14+90h], eax
0x18003c677  mov     rsi, [r15]
0x18003c67a  mov     rax, [rsi]
0x18003c67d  mov     rdi, [rax+50h]
0x18003c681  lea     rbx, [r14+68h]
0x18003c685  mov     rcx, [rbx]; string
0x18003c688  call    cs:__imp_WindowsDeleteString
0x18003c68e  mov     qword ptr [rbx], 0
0x18003c695  mov     rdx, cs:?s_fileDcatDownloadUrlTag@FileOperationServiceDrivenAction@@0QEBGEB; unsigned __int16 *
0x18003c69c  lea     rcx, [rbp+var_28]; this
0x18003c6a0  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003c6a5  mov     r8, rbx
0x18003c6a8  mov     rdx, [rbp+var_28]
0x18003c6ac  mov     rcx, rsi
0x18003c6af  mov     rax, rdi
0x18003c6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6b7  mov     ebx, eax
0x18003c6b9  test    eax, eax
0x18003c6bb  jns     short loc_18003C6C4
0x18003c6bd  mov     edx, 40h ; '@'
0x18003c6c2  jmp     short loc_18003C70F
0x18003c6c4  mov     rsi, [r15]
0x18003c6c7  mov     rax, [rsi]
0x18003c6ca  mov     rdi, [rax+50h]
0x18003c6ce  lea     rbx, [r14+70h]
0x18003c6d2  mov     rcx, [rbx]; string
0x18003c6d5  call    cs:__imp_WindowsDeleteString
0x18003c6db  mov     qword ptr [rbx], 0
0x18003c6e2  mov     rdx, cs:?s_fileSha256HashTag@FileOperationServiceDrivenAction@@0QEBGEB; unsigned __int16 *
0x18003c6e9  lea     rcx, [rbp+var_28]; this
0x18003c6ed  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003c6f2  mov     r8, rbx
0x18003c6f5  mov     rdx, [rbp+var_28]
0x18003c6f9  mov     rcx, rsi
0x18003c6fc  mov     rax, rdi
0x18003c6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c704  mov     ebx, eax
0x18003c706  test    eax, eax
0x18003c708  jns     short loc_18003C714
0x18003c70a  mov     edx, 41h ; 'A'
0x18003c70f  mov     r9d, eax
0x18003c712  jmp     short loc_18003C742
0x18003c714  lea     rcx, [rbp+var_50]; this
0x18003c718  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003c71d  nop
0x18003c71e  lea     rcx, [rbp+var_40]
0x18003c722  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003c727  nop
0x18003c728  lea     rcx, [rbp+string]; this
0x18003c72c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003c731  xor     eax, eax
0x18003c733  jmp     short loc_18003C772
0x18003c735  mov     ebx, 80BBFA0Ch
0x18003c73a  mov     r9d, ebx; char *
0x18003c73d  mov     edx, 45h ; 'E'; void *
0x18003c742  lea     r8, aOnecoreBaseDia_22; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003c749  mov     rcx, [rbp+28h]; this
0x18003c74d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c752  nop
0x18003c753  lea     rcx, [rbp+var_50]; this
0x18003c757  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003c75c  nop
0x18003c75d  lea     rcx, [rbp+var_40]
0x18003c761  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003c766  nop
0x18003c767  lea     rcx, [rbp+string]; this
0x18003c76b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003c770  mov     eax, ebx
0x18003c772  mov     rcx, [rbp+var_8]
0x18003c776  xor     rcx, rsp; StackCookie
0x18003c779  call    __security_check_cookie
0x18003c77e  mov     rbx, [rsp+70h+arg_10]
0x18003c786  add     rsp, 70h
0x18003c78a  pop     r15
0x18003c78c  pop     r14
0x18003c78e  pop     rdi
0x18003c78f  pop     rsi
0x18003c790  pop     rbp
0x18003c791  retn
```
