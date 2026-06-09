# Windows::Internal::Flighting::ClientAttributes::ShouldLogAttrState(CtacJsonData *,ushort const *)

- ea: `0x180039bc8`
- end: `0x180039daf`
- name: `?ShouldLogAttrState@ClientAttributes@Flighting@Internal@Windows@@CA_NPEAVCtacJsonData@@PEBG@Z`
- size: `487`
- prototype: `static bool(struct CtacJsonData *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032ba0`
- `0x180032e60`

## callees

- `0x18000b19c`
- `0x1800175b4`
- `0x18003286c`
- `0x1800335a4`
- `0x180034e30`
- `0x1800352e8`
- `0x180039bc8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180039cf1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180039cf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039cb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039cb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039cda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039cda`

## string_xrefs

- `0x180039d34`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`
- `0x180039d67`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`

## pseudocode

```c
char __fastcall Windows::Internal::Flighting::ClientAttributes::ShouldLogAttrState(
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

  if ( !*((_BYTE *)a1 + 72) || !a2 || !*a2 )
    return 0;
  v3 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)a1 + 10);
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
            (void *)0x18B,
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
        (void *)0x181,
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
0x180039bc8  mov     [rsp-28h+arg_8], rbx
0x180039bcd  push    rbp
0x180039bce  push    rsi
0x180039bcf  push    rdi
0x180039bd0  push    r14
0x180039bd2  push    r15
0x180039bd4  mov     rbp, rsp
0x180039bd7  sub     rsp, 70h
0x180039bdb  mov     r14, rdx
0x180039bde  xor     r15d, r15d
0x180039be1  cmp     [rcx+48h], r15b
0x180039be5  jz      loc_180039D99
0x180039beb  test    rdx, rdx
0x180039bee  jz      loc_180039D99
0x180039bf4  cmp     [rdx], r15w
0x180039bf8  jz      loc_180039D99
0x180039bfe  mov     rbx, [rcx+50h]
0x180039c02  mov     [rbp+var_40], rbx
0x180039c06  test    rbx, rbx
0x180039c09  jz      short loc_180039C1B
0x180039c0b  mov     rax, [rbx]
0x180039c0e  mov     rcx, rbx
0x180039c11  mov     rax, [rax+8]
0x180039c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c1a  nop
0x180039c1b  test    rbx, rbx
0x180039c1e  jnz     short loc_180039C28
0x180039c20  lea     esi, [rbx+1]
0x180039c23  jmp     loc_180039D80
0x180039c28  mov     [rbp+arg_18], r15
0x180039c2c  lea     rdx, [rbp+arg_18]
0x180039c30  lea     rcx, [rbp+var_40]
0x180039c34  call    ??$As@U?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *>>>)
0x180039c39  mov     rcx, [rbp+28h]
0x180039c3d  test    eax, eax
0x180039c3f  jns     short loc_180039C4E
0x180039c41  mov     r9d, eax
0x180039c44  mov     edx, 181h
0x180039c49  jmp     loc_180039D67
0x180039c4e  mov     dword ptr [rbp+arg_0], r15d
0x180039c52  lea     r8, [rbp+arg_0]
0x180039c56  mov     rdx, [rbp+arg_18]
0x180039c5a  lea     rcx, [rbp+var_28]
0x180039c5e  call    ??$GetRangeNoThrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@YA?AV?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@0@PEAU?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@PEAJ@Z; wil::GetRangeNoThrow<Windows::Data::Json::IJsonValue *>(Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *> *,long *)
0x180039c63  nop
0x180039c64  mov     rax, [rbp+var_28]
0x180039c68  neg     rax
0x180039c6b  sbb     ecx, ecx
0x180039c6d  neg     ecx
0x180039c6f  mov     esi, 1
0x180039c74  sub     ecx, esi
0x180039c76  lea     rdi, [rbp+var_28]
0x180039c7a  mov     [rbp+var_38], rdi
0x180039c7e  mov     edx, r15d
0x180039c81  cmp     ecx, 0FFFFFFFFh
0x180039c84  setnz   dl
0x180039c87  sub     edx, esi
0x180039c89  mov     [rbp+var_30], edx
0x180039c8c  mov     rax, [rdi+10h]
0x180039c90  cmp     [rax], r15d
0x180039c93  jl      loc_180039D4C
0x180039c99  cmp     edx, 0FFFFFFFFh
0x180039c9c  jz      loc_180039D4C
0x180039ca2  mov     [rbp+string], r15
0x180039ca6  mov     rdi, [rdi+8]
0x180039caa  mov     rax, [rdi]
0x180039cad  mov     rbx, [rax+40h]
0x180039cb1  xor     ecx, ecx; string
0x180039cb3  call    cs:__imp_WindowsDeleteString
0x180039cb9  mov     [rbp+string], r15
0x180039cbd  lea     rdx, [rbp+string]
0x180039cc1  mov     rcx, rdi
0x180039cc4  mov     rax, rbx
0x180039cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ccc  mov     rcx, [rbp+28h]; this
0x180039cd0  test    eax, eax
0x180039cd2  js      short loc_180039D31
0x180039cd4  xor     edx, edx; length
0x180039cd6  mov     rcx, [rbp+string]; string
0x180039cda  call    cs:__imp_WindowsGetStringRawBuffer
0x180039ce0  mov     [rsp+70h+bIgnoreCase], esi; bIgnoreCase
0x180039ce4  or      r9d, 0FFFFFFFFh; cchCount2
0x180039ce8  mov     r8, rax; lpString2
0x180039ceb  or      edx, r9d; cchCount1
0x180039cee  mov     rcx, r14; lpString1
0x180039cf1  call    cs:__imp_CompareStringOrdinal
0x180039cf7  nop
0x180039cf8  mov     rcx, [rbp+string]; string
0x180039cfc  cmp     eax, 2
0x180039cff  jz      short loc_180039D1C
0x180039d01  call    cs:__imp_WindowsDeleteString
0x180039d07  lea     rcx, [rbp+var_38]
0x180039d0b  call    ??Eiterable_iterator_nothrow@?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAAAEAV012@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::iterable_iterator_nothrow::operator++(void)
0x180039d10  mov     edx, [rbp+var_30]
0x180039d13  mov     rdi, [rbp+var_38]
0x180039d17  jmp     loc_180039C8C
0x180039d1c  call    cs:__imp_WindowsDeleteString
0x180039d22  mov     [rbp+string], r15
0x180039d26  lea     rcx, [rbp+var_28]
0x180039d2a  call    ??1?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(void)
0x180039d2f  jmp     short loc_180039D74
0x180039d31  mov     r9d, eax; char *
0x180039d34  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x180039d3b  mov     edx, 18Bh; void *
0x180039d40  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039d45  nop
0x180039d46  mov     rcx, [rbp+string]
0x180039d4a  jmp     short loc_180039D1C
0x180039d4c  lea     rcx, [rbp+var_28]
0x180039d50  call    ??1?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(void)
0x180039d55  mov     r9d, dword ptr [rbp+arg_0]; char *
0x180039d59  mov     rcx, [rbp+28h]; this
0x180039d5d  test    r9d, r9d
0x180039d60  jns     short loc_180039D8E
0x180039d62  mov     edx, 196h; void *
0x180039d67  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x180039d6e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039d73  nop
0x180039d74  lea     rcx, [rbp+arg_18]
0x180039d78  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039d7d  mov     sil, r15b
0x180039d80  lea     rcx, [rbp+var_40]
0x180039d84  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039d89  mov     al, sil
0x180039d8c  jmp     short loc_180039D9B
0x180039d8e  lea     rcx, [rbp+arg_18]
0x180039d92  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039d97  jmp     short loc_180039D80
0x180039d99  xor     al, al
0x180039d9b  mov     rbx, [rsp+70h+arg_8]
0x180039da3  add     rsp, 70h
0x180039da7  pop     r15
0x180039da9  pop     r14
0x180039dab  pop     rdi
0x180039dac  pop     rsi
0x180039dad  pop     rbp
0x180039dae  retn
```
