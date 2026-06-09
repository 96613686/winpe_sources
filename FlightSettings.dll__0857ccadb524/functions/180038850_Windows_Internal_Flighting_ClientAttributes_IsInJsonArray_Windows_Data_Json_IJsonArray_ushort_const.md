# Windows::Internal::Flighting::ClientAttributes::IsInJsonArray(Windows::Data::Json::IJsonArray *,ushort const *)

- ea: `0x180038850`
- end: `0x180038a4a`
- name: `?IsInJsonArray@ClientAttributes@Flighting@Internal@Windows@@CAJPEAUIJsonArray@Json@Data@4@PEBG@Z`
- size: `506`
- prototype: `static int(struct Windows::Data::Json::IJsonArray *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038acc`

## callees

- `0x18000b19c`
- `0x18000cc8c`
- `0x1800335a4`
- `0x180034e30`
- `0x1800352d8`
- `0x1800352e8`
- `0x180038850`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180038979`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180038979`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038929`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038989`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800389a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800389dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038929`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038989`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800389a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800389dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003895e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003895e`

## string_xrefs

- `0x1800389c6`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`
- `0x180038a0d`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::Flighting::ClientAttributes::IsInJsonArray(
        __int64 (__fastcall ***a1)(struct Windows::Data::Json::IJsonArray *, GUID *, __int64 *),
        const unsigned __int16 *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Data::Json::IJsonArray *, GUID *, __int64 *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  _QWORD *v9; // rax
  int v10; // edx
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  const WCHAR *StringRawBuffer; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-50h]
  __int64 v18; // [rsp+30h] [rbp-40h] BYREF
  _QWORD *v19; // [rsp+38h] [rbp-38h] BYREF
  int v20; // [rsp+40h] [rbp-30h]
  _QWORD v21[5]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  int v23; // [rsp+90h] [rbp+20h]
  UINT32 length; // [rsp+A0h] [rbp+30h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+38h] BYREF

  if ( !a1 || !a2 )
    return 1;
  v18 = 0;
  v4 = **a1;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  v5 = v4((struct Windows::Data::Json::IJsonArray *)a1, &GUID_cb0492b6_4113_55cf_b2c5_99eb428ba493, &v18);
  v6 = v5;
  v23 = v5;
  if ( v5 < 0 )
  {
    v7 = (unsigned int)v5;
    v8 = 810;
    goto LABEL_15;
  }
  wil::GetRangeNoThrow<Windows::Data::Json::IJsonValue *>((__int64)v21);
  v9 = v21;
  v19 = v21;
  v10 = (v21[0] != 0) - 1;
  v20 = v10;
  while ( *(int *)v9[2] >= 0 && v10 != -1 )
  {
    v11 = wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::iterable_iterator_nothrow::operator*(&v19);
    string = 0;
    v12 = *(_QWORD *)v11;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v11 + 64LL);
    WindowsDeleteString(0);
    string = 0;
    v14 = v13(v12, &string);
    v6 = v14;
    v23 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x330,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
        (const char *)(unsigned int)v14,
        bIgnoreCase);
      WindowsDeleteString(string);
      string = 0;
      wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(v21);
      goto LABEL_16;
    }
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    if ( CompareStringOrdinal(a2, -1, StringRawBuffer, length, 1) == 2 )
    {
      WindowsDeleteString(string);
      string = 0;
      wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(v21);
      v6 = 0;
      goto LABEL_16;
    }
    WindowsDeleteString(string);
    wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::iterable_iterator_nothrow::operator++(&v19);
    v10 = v20;
    v9 = v19;
  }
  wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(v21);
  v6 = v23;
  if ( v23 >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
    return 1;
  }
  v7 = (unsigned int)v23;
  v8 = 825;
LABEL_15:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
    (const char *)v7,
    bIgnoreCase);
LABEL_16:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  return v6;
}

```

## disassembly

```asm
0x180038850  mov     [rsp-18h+arg_8], rbx
0x180038855  push    rbp
0x180038856  push    rdi
0x180038857  push    r14
0x180038859  mov     rbp, rsp
0x18003885c  sub     rsp, 70h
0x180038860  mov     r14, rdx
0x180038863  mov     rdi, rcx
0x180038866  mov     dword ptr [rbp+arg_0], 0
0x18003886d  test    rcx, rcx
0x180038870  jz      loc_180038A34
0x180038876  test    rdx, rdx
0x180038879  jz      loc_180038A34
0x18003887f  mov     [rbp+var_40], 0
0x180038887  mov     rax, [rcx]
0x18003888a  mov     rbx, [rax]
0x18003888d  lea     rcx, [rbp+var_40]
0x180038891  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180038896  lea     r8, [rbp+var_40]
0x18003889a  lea     rdx, _GUID_cb0492b6_4113_55cf_b2c5_99eb428ba493
0x1800388a1  mov     rcx, rdi
0x1800388a4  mov     rax, rbx
0x1800388a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388ac  mov     ebx, eax
0x1800388ae  mov     dword ptr [rbp+arg_0], eax
0x1800388b1  test    eax, eax
0x1800388b3  jns     short loc_1800388C2
0x1800388b5  mov     r9d, eax
0x1800388b8  mov     edx, 32Ah
0x1800388bd  jmp     loc_180038A0D
0x1800388c2  lea     r8, [rbp+arg_0]
0x1800388c6  mov     rdx, [rbp+var_40]
0x1800388ca  lea     rcx, [rbp+var_28]
0x1800388ce  call    ??$GetRangeNoThrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@YA?AV?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@0@PEAU?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@PEAJ@Z; wil::GetRangeNoThrow<Windows::Data::Json::IJsonValue *>(Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *> *,long *)
0x1800388d3  nop
0x1800388d4  mov     rax, [rbp+var_28]
0x1800388d8  neg     rax
0x1800388db  sbb     ecx, ecx
0x1800388dd  neg     ecx
0x1800388df  dec     ecx
0x1800388e1  lea     rax, [rbp+var_28]
0x1800388e5  mov     [rbp+var_38], rax
0x1800388e9  xor     edx, edx
0x1800388eb  cmp     ecx, 0FFFFFFFFh
0x1800388ee  setnz   dl
0x1800388f1  dec     edx
0x1800388f3  mov     [rbp+var_30], edx
0x1800388f6  mov     rax, [rax+10h]
0x1800388fa  cmp     dword ptr [rax], 0
0x1800388fd  jl      loc_1800389F5
0x180038903  cmp     edx, 0FFFFFFFFh
0x180038906  jz      loc_1800389F5
0x18003890c  lea     rcx, [rbp+var_38]
0x180038910  call    ??Diterable_iterator_nothrow@?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEBAAEBV?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::iterable_iterator_nothrow::operator*(void)
0x180038915  mov     [rbp+string], 0
0x18003891d  mov     rdi, [rax]
0x180038920  mov     rax, [rdi]
0x180038923  mov     rbx, [rax+40h]
0x180038927  xor     ecx, ecx; string
0x180038929  call    cs:__imp_WindowsDeleteString
0x18003892f  mov     [rbp+string], 0
0x180038937  lea     rdx, [rbp+string]
0x18003893b  mov     rcx, rdi
0x18003893e  mov     rax, rbx
0x180038941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038946  mov     ebx, eax
0x180038948  mov     dword ptr [rbp+arg_0], eax
0x18003894b  test    eax, eax
0x18003894d  js      short loc_1800389BF
0x18003894f  mov     [rbp+length], 0
0x180038956  lea     rdx, [rbp+length]; length
0x18003895a  mov     rcx, [rbp+string]; string
0x18003895e  call    cs:__imp_WindowsGetStringRawBuffer
0x180038964  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x18003896c  mov     r9d, [rbp+length]; cchCount2
0x180038970  mov     r8, rax; lpString2
0x180038973  or      edx, 0FFFFFFFFh; cchCount1
0x180038976  mov     rcx, r14; lpString1
0x180038979  call    cs:__imp_CompareStringOrdinal
0x18003897f  nop
0x180038980  mov     rcx, [rbp+string]; string
0x180038984  cmp     eax, 2
0x180038987  jz      short loc_1800389A4
0x180038989  call    cs:__imp_WindowsDeleteString
0x18003898f  lea     rcx, [rbp+var_38]
0x180038993  call    ??Eiterable_iterator_nothrow@?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAAAEAV012@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::iterable_iterator_nothrow::operator++(void)
0x180038998  mov     edx, [rbp+var_30]
0x18003899b  mov     rax, [rbp+var_38]
0x18003899f  jmp     loc_1800388F6
0x1800389a4  call    cs:__imp_WindowsDeleteString
0x1800389aa  mov     [rbp+string], 0
0x1800389b2  lea     rcx, [rbp+var_28]
0x1800389b6  call    ??1?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(void)
0x1800389bb  xor     ebx, ebx
0x1800389bd  jmp     short loc_180038A1E
0x1800389bf  mov     rcx, [rbp+18h]; this
0x1800389c3  mov     r9d, eax; char *
0x1800389c6  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x1800389cd  mov     edx, 330h; void *
0x1800389d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800389d7  nop
0x1800389d8  mov     rcx, [rbp+string]; string
0x1800389dc  call    cs:__imp_WindowsDeleteString
0x1800389e2  mov     [rbp+string], 0
0x1800389ea  lea     rcx, [rbp+var_28]
0x1800389ee  call    ??1?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(void)
0x1800389f3  jmp     short loc_180038A1E
0x1800389f5  lea     rcx, [rbp+var_28]
0x1800389f9  call    ??1?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(void)
0x1800389fe  mov     ebx, dword ptr [rbp+arg_0]
0x180038a01  test    ebx, ebx
0x180038a03  jns     short loc_180038A2B
0x180038a05  mov     r9d, ebx; char *
0x180038a08  mov     edx, 339h; void *
0x180038a0d  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x180038a14  mov     rcx, [rbp+18h]; this
0x180038a18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038a1d  nop
0x180038a1e  lea     rcx, [rbp+var_40]
0x180038a22  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180038a27  mov     eax, ebx
0x180038a29  jmp     short loc_180038A39
0x180038a2b  lea     rcx, [rbp+var_40]
0x180038a2f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180038a34  mov     eax, 1
0x180038a39  mov     rbx, [rsp+70h+arg_8]
0x180038a41  add     rsp, 70h
0x180038a45  pop     r14
0x180038a47  pop     rdi
0x180038a48  pop     rbp
0x180038a49  retn
```
