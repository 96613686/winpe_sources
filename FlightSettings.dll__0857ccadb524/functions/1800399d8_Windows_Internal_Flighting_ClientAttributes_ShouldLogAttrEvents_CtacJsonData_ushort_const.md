# Windows::Internal::Flighting::ClientAttributes::ShouldLogAttrEvents(CtacJsonData *,ushort const *)

- ea: `0x1800399d8`
- end: `0x180039bbf`
- name: `?ShouldLogAttrEvents@ClientAttributes@Flighting@Internal@Windows@@CA_NPEAVCtacJsonData@@PEBG@Z`
- size: `487`
- prototype: `static bool(struct CtacJsonData *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035388`

## callees

- `0x18000b19c`
- `0x1800175b4`
- `0x18003286c`
- `0x1800335a4`
- `0x180034e30`
- `0x1800352e8`
- `0x1800399d8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180039b01`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180039b01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039ac3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039ac3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039aea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039aea`

## string_xrefs

- `0x180039b44`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`
- `0x180039b77`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall Windows::Internal::Flighting::ClientAttributes::ShouldLogAttrEvents(
        struct CtacJsonData *a1,
        const unsigned __int16 *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64); // rbx
  char v4; // si
  int v5; // eax
  _QWORD *v6; // rdi
  int v7; // edx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  const WCHAR *StringRawBuffer; // rax
  int v12; // eax
  HSTRING v13; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-50h]
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-40h] BYREF
  _QWORD *v17; // [rsp+38h] [rbp-38h] BYREF
  int v18; // [rsp+40h] [rbp-30h]
  _QWORD v19[5]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  HSTRING string; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v22; // [rsp+B8h] [rbp+48h] BYREF

  if ( !*((_BYTE *)a1 + 56) || !a2 || !*a2 )
    return 0;
  v3 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)a1 + 8);
  v16 = v3;
  if ( v3 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v3)[1])(v3);
    v22 = 0;
    v5 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *>>(
           &v16,
           (__int64)&v22);
    if ( v5 >= 0 )
    {
      wil::GetRangeNoThrow<Windows::Data::Json::IJsonValue *>((__int64)v19);
      v4 = 1;
      v6 = v19;
      v17 = v19;
      v7 = (v19[0] != 0) - 1;
      v18 = v7;
      while ( *(int *)v6[2] >= 0 && v7 != -1 )
      {
        string = 0;
        v8 = v6[1];
        v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v8 + 64LL);
        WindowsDeleteString(0);
        string = 0;
        v10 = v9(v8, &string);
        if ( v10 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x155,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
            (const char *)(unsigned int)v10,
            bIgnoreCase);
          v13 = string;
LABEL_15:
          WindowsDeleteString(v13);
          string = 0;
          wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(v19);
          goto LABEL_18;
        }
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v12 = CompareStringOrdinal(a2, -1, StringRawBuffer, -1, 1);
        v13 = string;
        if ( v12 == 2 )
          goto LABEL_15;
        WindowsDeleteString(string);
        wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::iterable_iterator_nothrow::operator++(&v17);
        v7 = v18;
        v6 = v17;
      }
      wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(v19);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
        (const char *)(unsigned int)v5,
        bIgnoreCase);
LABEL_18:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
      v4 = 0;
    }
  }
  else
  {
    v4 = 1;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
  return v4;
}

```

## disassembly

```asm
0x1800399d8  mov     [rsp-28h+arg_8], rbx
0x1800399dd  push    rbp
0x1800399de  push    rsi
0x1800399df  push    rdi
0x1800399e0  push    r14
0x1800399e2  push    r15
0x1800399e4  mov     rbp, rsp
0x1800399e7  sub     rsp, 70h
0x1800399eb  mov     r14, rdx
0x1800399ee  xor     r15d, r15d
0x1800399f1  cmp     [rcx+38h], r15b
0x1800399f5  jz      loc_180039BA9
0x1800399fb  test    rdx, rdx
0x1800399fe  jz      loc_180039BA9
0x180039a04  cmp     [rdx], r15w
0x180039a08  jz      loc_180039BA9
0x180039a0e  mov     rbx, [rcx+40h]
0x180039a12  mov     [rbp+var_40], rbx
0x180039a16  test    rbx, rbx
0x180039a19  jz      short loc_180039A2B
0x180039a1b  mov     rax, [rbx]
0x180039a1e  mov     rcx, rbx
0x180039a21  mov     rax, [rax+8]
0x180039a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a2a  nop
0x180039a2b  test    rbx, rbx
0x180039a2e  jnz     short loc_180039A38
0x180039a30  lea     esi, [rbx+1]
0x180039a33  jmp     loc_180039B90
0x180039a38  mov     [rbp+arg_18], r15
0x180039a3c  lea     rdx, [rbp+arg_18]
0x180039a40  lea     rcx, [rbp+var_40]
0x180039a44  call    ??$As@U?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *>>>)
0x180039a49  mov     rcx, [rbp+28h]
0x180039a4d  test    eax, eax
0x180039a4f  jns     short loc_180039A5E
0x180039a51  mov     r9d, eax
0x180039a54  mov     edx, 14Bh
0x180039a59  jmp     loc_180039B77
0x180039a5e  mov     dword ptr [rbp+arg_0], r15d
0x180039a62  lea     r8, [rbp+arg_0]
0x180039a66  mov     rdx, [rbp+arg_18]
0x180039a6a  lea     rcx, [rbp+var_28]
0x180039a6e  call    ??$GetRangeNoThrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@YA?AV?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@0@PEAU?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@PEAJ@Z; wil::GetRangeNoThrow<Windows::Data::Json::IJsonValue *>(Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *> *,long *)
0x180039a73  nop
0x180039a74  mov     rax, [rbp+var_28]
0x180039a78  neg     rax
0x180039a7b  sbb     ecx, ecx
0x180039a7d  neg     ecx
0x180039a7f  mov     esi, 1
0x180039a84  sub     ecx, esi
0x180039a86  lea     rdi, [rbp+var_28]
0x180039a8a  mov     [rbp+var_38], rdi
0x180039a8e  mov     edx, r15d
0x180039a91  cmp     ecx, 0FFFFFFFFh
0x180039a94  setnz   dl
0x180039a97  sub     edx, esi
0x180039a99  mov     [rbp+var_30], edx
0x180039a9c  mov     rax, [rdi+10h]
0x180039aa0  cmp     [rax], r15d
0x180039aa3  jl      loc_180039B5C
0x180039aa9  cmp     edx, 0FFFFFFFFh
0x180039aac  jz      loc_180039B5C
0x180039ab2  mov     [rbp+string], r15
0x180039ab6  mov     rdi, [rdi+8]
0x180039aba  mov     rax, [rdi]
0x180039abd  mov     rbx, [rax+40h]
0x180039ac1  xor     ecx, ecx; string
0x180039ac3  call    cs:__imp_WindowsDeleteString
0x180039ac9  mov     [rbp+string], r15
0x180039acd  lea     rdx, [rbp+string]
0x180039ad1  mov     rcx, rdi
0x180039ad4  mov     rax, rbx
0x180039ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039adc  mov     rcx, [rbp+28h]; this
0x180039ae0  test    eax, eax
0x180039ae2  js      short loc_180039B41
0x180039ae4  xor     edx, edx; length
0x180039ae6  mov     rcx, [rbp+string]; string
0x180039aea  call    cs:__imp_WindowsGetStringRawBuffer
0x180039af0  mov     [rsp+70h+bIgnoreCase], esi; bIgnoreCase
0x180039af4  or      r9d, 0FFFFFFFFh; cchCount2
0x180039af8  mov     r8, rax; lpString2
0x180039afb  or      edx, r9d; cchCount1
0x180039afe  mov     rcx, r14; lpString1
0x180039b01  call    cs:__imp_CompareStringOrdinal
0x180039b07  nop
0x180039b08  mov     rcx, [rbp+string]; string
0x180039b0c  cmp     eax, 2
0x180039b0f  jz      short loc_180039B2C
0x180039b11  call    cs:__imp_WindowsDeleteString
0x180039b17  lea     rcx, [rbp+var_38]
0x180039b1b  call    ??Eiterable_iterator_nothrow@?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAAAEAV012@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::iterable_iterator_nothrow::operator++(void)
0x180039b20  mov     edx, [rbp+var_30]
0x180039b23  mov     rdi, [rbp+var_38]
0x180039b27  jmp     loc_180039A9C
0x180039b2c  call    cs:__imp_WindowsDeleteString
0x180039b32  mov     [rbp+string], r15
0x180039b36  lea     rcx, [rbp+var_28]
0x180039b3a  call    ??1?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(void)
0x180039b3f  jmp     short loc_180039B84
0x180039b41  mov     r9d, eax; char *
0x180039b44  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x180039b4b  mov     edx, 155h; void *
0x180039b50  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039b55  nop
0x180039b56  mov     rcx, [rbp+string]
0x180039b5a  jmp     short loc_180039B2C
0x180039b5c  lea     rcx, [rbp+var_28]
0x180039b60  call    ??1?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(void)
0x180039b65  mov     r9d, dword ptr [rbp+arg_0]; char *
0x180039b69  mov     rcx, [rbp+28h]; this
0x180039b6d  test    r9d, r9d
0x180039b70  jns     short loc_180039B9E
0x180039b72  mov     edx, 160h; void *
0x180039b77  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x180039b7e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039b83  nop
0x180039b84  lea     rcx, [rbp+arg_18]
0x180039b88  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039b8d  mov     sil, r15b
0x180039b90  lea     rcx, [rbp+var_40]
0x180039b94  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039b99  mov     al, sil
0x180039b9c  jmp     short loc_180039BAB
0x180039b9e  lea     rcx, [rbp+arg_18]
0x180039ba2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039ba7  jmp     short loc_180039B90
0x180039ba9  xor     al, al
0x180039bab  mov     rbx, [rsp+70h+arg_8]
0x180039bb3  add     rsp, 70h
0x180039bb7  pop     r15
0x180039bb9  pop     r14
0x180039bbb  pop     rdi
0x180039bbc  pop     rsi
0x180039bbd  pop     rbp
0x180039bbe  retn
```
