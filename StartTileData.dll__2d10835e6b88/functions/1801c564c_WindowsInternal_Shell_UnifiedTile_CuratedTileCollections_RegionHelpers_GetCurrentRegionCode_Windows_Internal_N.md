# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::RegionHelpers::GetCurrentRegionCode(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::RegionLookupFallbackOptions)

- ea: `0x1801c564c`
- end: `0x1801c5848`
- name: `?GetCurrentRegionCode@RegionHelpers@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@YAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@W4RegionLookupFallbackOptions@2345@@Z`
- size: `508`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801c5398`
- `0x1801caee4`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18004ffc0`
- `0x1800c1508`
- `0x1800db710`
- `0x1801c564c`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801c5747`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801c57c2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801c5747`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801c57c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c56db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c5717`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c5778`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c580b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c56db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c5717`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c5778`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c580b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c5728`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c57a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c57e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c5728`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c57a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c57e3`

## string_xrefs

- `0x1801c56b5`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\helpers\regionhelpers.cpp`
- `0x1801c5706`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\helpers\regionhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::RegionHelpers::GetCurrentRegionCode(
        __int64 a1,
        char a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r9
  const WCHAR *StringRawBuffer; // rax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  const WCHAR *v14; // rax
  PCWSTR v15; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-50h]
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  __int64 v19; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v21; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v19 = 0;
  v21 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Globalization.GeographicRegion",
    0x27u,
    0x26u);
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>(
         v21,
         &v19);
  v5 = v4;
  if ( v4 >= 0 )
  {
    string = 0;
    v6 = v19;
    v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v8 = v7(v6, &string);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = 22;
LABEL_5:
      v10 = (unsigned int)v8;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\helpers\\regionhelpers.cpp",
        (const char *)v10,
        bIgnoreCase);
      WindowsDeleteString(string);
LABEL_17:
      string = 0;
      goto LABEL_18;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(StringRawBuffer, -1, L"ZZ", -1, 0) == 2 )
    {
      if ( (a2 & 1) == 0 )
      {
        v5 = -2147467259;
        v10 = 2147500037LL;
        v9 = 26;
        goto LABEL_6;
      }
      v12 = v19;
      v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 72LL);
      WindowsDeleteString(string);
      string = 0;
      v8 = v13(v12, &string);
      v5 = v8;
      if ( v8 < 0 )
      {
        v9 = 28;
        goto LABEL_5;
      }
      v14 = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(v14, -1, L"999", -1, 0) == 2 )
      {
        v5 = -2147467259;
        v10 = 2147500037LL;
        v9 = 31;
        goto LABEL_6;
      }
    }
    v15 = WindowsGetStringRawBuffer(string, 0);
    v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(a1, v15, -1);
    v5 = v8;
    if ( v8 >= 0 )
    {
      WindowsDeleteString(string);
      v5 = 0;
      goto LABEL_17;
    }
    v9 = 33;
    goto LABEL_5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x13,
    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\helpers\\regionhelpers.cpp",
    (const char *)(unsigned int)v4,
    bIgnoreCase);
LABEL_18:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  return v5;
}

```

## disassembly

```asm
0x1801c564c  mov     [rsp-28h+arg_8], rbx
0x1801c5651  mov     [rsp-28h+arg_10], rsi
0x1801c5656  push    rbp
0x1801c5657  push    rdi
0x1801c5658  push    r12
0x1801c565a  push    r14
0x1801c565c  push    r15
0x1801c565e  mov     rbp, rsp
0x1801c5661  sub     rsp, 70h
0x1801c5665  mov     rax, cs:__security_cookie
0x1801c566c  xor     rax, rsp
0x1801c566f  mov     [rbp+var_10], rax
0x1801c5673  mov     esi, edx
0x1801c5675  mov     r14, rcx
0x1801c5678  xor     r15d, r15d
0x1801c567b  mov     [rbp+var_38], r15
0x1801c567f  mov     [rbp+var_18], r15
0x1801c5683  lea     r9d, [r15+26h]; unsigned int
0x1801c5687  lea     r8d, [r15+27h]; unsigned int
0x1801c568b  lea     rdx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x1801c5692  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1801c5696  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801c569b  lea     rdx, [rbp+var_38]
0x1801c569f  mov     rcx, [rbp+var_18]
0x1801c56a3  call    ??$ActivateInstance@V?$ComPtr@UIGeographicRegion@Globalization@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIGeographicRegion@Globalization@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>)
0x1801c56a8  mov     ebx, eax
0x1801c56aa  test    eax, eax
0x1801c56ac  jns     short loc_1801C56CA
0x1801c56ae  mov     rcx, [rbp+28h]; this
0x1801c56b2  mov     r9d, eax; char *
0x1801c56b5  lea     r8, aShellcommonShe_93; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801c56bc  lea     edx, [r15+13h]; void *
0x1801c56c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c56c5  jmp     loc_1801C5818
0x1801c56ca  mov     [rbp+string], r15
0x1801c56ce  mov     rdi, [rbp+var_38]
0x1801c56d2  mov     rax, [rdi]
0x1801c56d5  mov     rbx, [rax+38h]
0x1801c56d9  xor     ecx, ecx; string
0x1801c56db  call    cs:__imp_WindowsDeleteString
0x1801c56e1  mov     [rbp+string], r15
0x1801c56e5  lea     rdx, [rbp+string]
0x1801c56e9  mov     rcx, rdi
0x1801c56ec  mov     rax, rbx
0x1801c56ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c56f4  mov     ebx, eax
0x1801c56f6  test    eax, eax
0x1801c56f8  jns     short loc_1801C5722
0x1801c56fa  mov     edx, 16h; void *
0x1801c56ff  mov     r9d, eax; char *
0x1801c5702  mov     rcx, [rbp+28h]; this
0x1801c5706  lea     r8, aShellcommonShe_93; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801c570d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c5712  nop
0x1801c5713  mov     rcx, [rbp+string]; string
0x1801c5717  call    cs:__imp_WindowsDeleteString
0x1801c571d  jmp     loc_1801C5814
0x1801c5722  xor     edx, edx; length
0x1801c5724  mov     rcx, [rbp+string]; string
0x1801c5728  call    cs:__imp_WindowsGetStringRawBuffer
0x1801c572e  mov     [rsp+70h+bIgnoreCase], r15d; bIgnoreCase
0x1801c5733  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801c5737  mov     r9d, r12d; cchCount2
0x1801c573a  lea     r8, aZz; "ZZ"
0x1801c5741  mov     edx, r12d; cchCount1
0x1801c5744  mov     rcx, rax; lpString1
0x1801c5747  call    cs:__imp_CompareStringOrdinal
0x1801c574d  cmp     eax, 2
0x1801c5750  jnz     loc_1801C57DD
0x1801c5756  test    sil, 1
0x1801c575a  jnz     short loc_1801C5769
0x1801c575c  mov     ebx, 80004005h
0x1801c5761  mov     r9d, ebx
0x1801c5764  lea     edx, [rax+18h]
0x1801c5767  jmp     short loc_1801C5702
0x1801c5769  mov     rdi, [rbp+var_38]
0x1801c576d  mov     rax, [rdi]
0x1801c5770  mov     rbx, [rax+48h]
0x1801c5774  mov     rcx, [rbp+string]; string
0x1801c5778  call    cs:__imp_WindowsDeleteString
0x1801c577e  mov     [rbp+string], r15
0x1801c5782  lea     rdx, [rbp+string]
0x1801c5786  mov     rcx, rdi
0x1801c5789  mov     rax, rbx
0x1801c578c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c5791  mov     ebx, eax
0x1801c5793  test    eax, eax
0x1801c5795  jns     short loc_1801C57A1
0x1801c5797  mov     edx, 1Ch
0x1801c579c  jmp     loc_1801C56FF
0x1801c57a1  xor     edx, edx; length
0x1801c57a3  mov     rcx, [rbp+string]; string
0x1801c57a7  call    cs:__imp_WindowsGetStringRawBuffer
0x1801c57ad  mov     [rsp+70h+bIgnoreCase], r15d; bIgnoreCase
0x1801c57b2  mov     r9d, r12d; cchCount2
0x1801c57b5  lea     r8, a999; "999"
0x1801c57bc  mov     edx, r12d; cchCount1
0x1801c57bf  mov     rcx, rax; lpString1
0x1801c57c2  call    cs:__imp_CompareStringOrdinal
0x1801c57c8  cmp     eax, 2
0x1801c57cb  jnz     short loc_1801C57DD
0x1801c57cd  mov     ebx, 80004005h
0x1801c57d2  mov     r9d, ebx
0x1801c57d5  lea     edx, [rax+1Dh]
0x1801c57d8  jmp     loc_1801C5702
0x1801c57dd  xor     edx, edx; length
0x1801c57df  mov     rcx, [rbp+string]; string
0x1801c57e3  call    cs:__imp_WindowsGetStringRawBuffer
0x1801c57e9  mov     r8, r12
0x1801c57ec  mov     rdx, rax
0x1801c57ef  mov     rcx, r14
0x1801c57f2  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1801c57f7  mov     ebx, eax
0x1801c57f9  test    eax, eax
0x1801c57fb  jns     short loc_1801C5807
0x1801c57fd  mov     edx, 21h ; '!'
0x1801c5802  jmp     loc_1801C56FF
0x1801c5807  mov     rcx, [rbp+string]; string
0x1801c580b  call    cs:__imp_WindowsDeleteString
0x1801c5811  mov     ebx, r15d
0x1801c5814  mov     [rbp+string], r15
0x1801c5818  lea     rcx, [rbp+var_38]
0x1801c581c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c5821  mov     eax, ebx
0x1801c5823  mov     rcx, [rbp+var_10]
0x1801c5827  xor     rcx, rsp; StackCookie
0x1801c582a  call    __security_check_cookie
0x1801c582f  lea     r11, [rsp+70h+var_s0]
0x1801c5834  mov     rbx, [r11+38h]
0x1801c5838  mov     rsi, [r11+40h]
0x1801c583c  mov     rsp, r11
0x1801c583f  pop     r15
0x1801c5841  pop     r14
0x1801c5843  pop     r12
0x1801c5845  pop     rdi
0x1801c5846  pop     rbp
0x1801c5847  retn
```
