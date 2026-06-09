# MakeBulkHydrateUri(Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,ushort const *,uint,uint,ushort const *,ushort const *,TraceLoggingCorrelationVector *,Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180082ed0`
- end: `0x180083237`
- name: `?MakeBulkHydrateUri@@YAJPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@PEBGII11PEAVTraceLoggingCorrelationVector@@PEAPEAUIUriRuntimeClass@45@@Z`
- size: `871`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int16 *, HSTRING string, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180080808`

## callees

- `0x18000a34c`
- `0x18000a65c`
- `0x1800101f4`
- `0x18001c844`
- `0x18001df54`
- `0x180077c44`
- `0x180081834`
- `0x180082ed0`
- `0x1800db734`
- `0x1800ffe38`
- `0x180100014`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082fc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082fd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800830c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083204`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008321b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082fc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082fd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800830c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083204`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008321b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008311e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180083138`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180083152`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008311e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180083138`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180083152`

## string_xrefs

- `0x180082f07`: `InstallAgent`
- `0x180082fa1`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180083002`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x1800830f7`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x1800831bb`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180082f95`: `MakeBulkHydrateUri`
- `0x180082ff6`: `MakeBulkHydrateUri`
- `0x1800830eb`: `MakeBulkHydrateUri`
- `0x1800831af`: `MakeBulkHydrateUri`
- `0x1800830e4`: `StringHelpers::Join(batchProductIds.Get(), L',', productIdsWithCommas.GetAddressOf())`
- `0x18008310d`: `productIdsWithCommas`
- `0x18008315c`: `fieldsTemplate`
- `0x1800831a8`: `GetSLSUri(slsBulkHydrate, rgAnnotationValues, ARRAYSIZE(rgAnnotationValues), szAdditionalQueryParams, pCV, &spUri)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MakeBulkHydrateUri(
        __int64 a1,
        _WORD *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        HSTRING string,
        __int64 a7,
        _QWORD *a8)
{
  const unsigned __int16 *v11; // rcx
  unsigned __int64 v12; // rbx
  wchar_t *v13; // r12
  unsigned __int16 *v14; // rcx
  int v15; // eax
  int ExclusivityIds; // eax
  HSTRING v17; // rbx
  HSTRING v18; // rdi
  int LanguageAndRegion; // eax
  __int64 v20; // rcx
  const struct std::nothrow_t *v21; // rdx
  int v22; // esi
  unsigned int v23; // r15d
  int v24; // eax
  int SLSUri; // eax
  __int64 v26; // rax
  int v28; // [rsp+28h] [rbp-89h]
  int v29[2]; // [rsp+40h] [rbp-71h] BYREF
  HSTRING v30; // [rsp+48h] [rbp-69h] BYREF
  HSTRING v31; // [rsp+50h] [rbp-61h] BYREF
  __int64 v32; // [rsp+58h] [rbp-59h] BYREF
  const unsigned __int16 *v33; // [rsp+60h] [rbp-51h]
  _QWORD v34[16]; // [rsp+70h] [rbp-41h] BYREF
  unsigned int v35; // [rsp+118h] [rbp+67h] BYREF

  v35 = a4;
  *a8 = 0;
  v11 = L"InstallAgent";
  if ( string )
    v11 = (const unsigned __int16 *)string;
  v33 = v11;
  v12 = 1024;
  v31 = (HSTRING)1024;
  v13 = (wchar_t *)operator new[](0x800u, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v13;
  v30 = (HSTRING)v13;
  if ( v13 )
  {
    if ( a2 && *a2 )
    {
      v15 = StringCchPrintfExW(v13, 0x400u, (unsigned __int16 **)&v30, (unsigned __int64 *)&v31, 0, L"&catalogId=%s");
      if ( v15 < 0 )
        goto LABEL_10;
      v12 = (unsigned __int64)v31;
      v14 = (unsigned __int16 *)v30;
    }
    ExclusivityIds = GetExclusivityIds(v14, v12, a5);
    v15 = TraceHR(
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
            0x2BDu,
            "MakeBulkHydrateUri",
            "GetExclusivityIds(pszAdditionalQueryParamsEnd, cchAdditionalQueryParams, pszMoId)",
            ExclusivityIds,
            v28);
  }
  else
  {
    v15 = -2147024882;
  }
LABEL_10:
  v17 = 0;
  v30 = 0;
  v18 = 0;
  v31 = 0;
  if ( v15 >= 0 )
  {
    WindowsDeleteString(0);
    v31 = 0;
    WindowsDeleteString(0);
    v30 = 0;
    LanguageAndRegion = GetLanguageAndRegion(&v30, &v31);
    TraceHR(
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
      0x2C4u,
      "MakeBulkHydrateUri",
      "GetLanguageAndRegion(language.GetAddressOf(), region.GetAddressOf())",
      LanguageAndRegion,
      v28);
    v17 = v30;
    v18 = v31;
  }
  string = 0;
  v32 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
  v22 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
          v20,
          &v32);
  if ( v22 >= 0 )
  {
    v35 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 56LL))(a1, &v35);
    if ( v22 >= 0 )
    {
      v23 = a3 + 100;
      if ( a3 + 100 > v35 )
        v23 = v35;
      if ( a3 >= v23 )
        goto LABEL_21;
      do
      {
        *(_QWORD *)v29 = 0;
        v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)a1 + 48LL))(a1, a3, v29);
        if ( v22 >= 0 )
          v22 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 104LL))(v32, *(_QWORD *)v29);
        ++a3;
      }
      while ( a3 < v23 );
      if ( v22 >= 0 )
      {
LABEL_21:
        WindowsDeleteString(string);
        string = 0;
        v24 = StringHelpers::Join(v32, 44, &string);
        v22 = TraceHR(
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
                0x2DEu,
                "MakeBulkHydrateUri",
                "StringHelpers::Join(batchProductIds.Get(), L',', productIdsWithCommas.GetAddressOf())",
                v24,
                v28);
        if ( v22 >= 0 )
        {
          v34[0] = L"productIdsWithCommas";
          v34[1] = WindowsGetStringRawBuffer(string, 0);
          v34[2] = L"languages";
          v34[3] = WindowsGetStringRawBuffer(v17, 0);
          v34[4] = L"marketCode";
          v34[5] = WindowsGetStringRawBuffer(v18, 0);
          v34[6] = L"fieldsTemplate";
          v34[7] = v33;
          *(_QWORD *)v29 = 0;
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v29);
          SLSUri = GetSLSUri(1, v34, 4);
          v22 = TraceHR(
                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
                  0x2ECu,
                  "MakeBulkHydrateUri",
                  "GetSLSUri(slsBulkHydrate, rgAnnotationValues, ARRAYSIZE(rgAnnotationValues), szAdditionalQueryParams, pCV, &spUri)",
                  SLSUri,
                  (int)v29);
          if ( v22 >= 0 )
          {
            v26 = *(_QWORD *)v29;
            *(_QWORD *)v29 = 0;
            *a8 = v26;
          }
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v29);
        }
      }
    }
  }
  if ( v13 )
    operator delete(v13, v21);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v18);
  WindowsDeleteString(v17);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180082ed0  mov     [rsp-8+arg_18], r9d
0x180082ed5  push    rbp
0x180082ed6  push    rbx
0x180082ed7  push    rsi
0x180082ed8  push    rdi
0x180082ed9  push    r12
0x180082edb  push    r13
0x180082edd  push    r14
0x180082edf  push    r15
0x180082ee1  lea     rbp, [rsp-7]
0x180082ee6  sub     rsp, 0B8h
0x180082eed  mov     r14d, r8d
0x180082ef0  mov     rdi, rdx
0x180082ef3  mov     r13, rcx
0x180082ef6  xor     r15d, r15d
0x180082ef9  mov     rax, [rbp+3Fh+arg_38]
0x180082f00  mov     [rax], r15
0x180082f03  mov     rax, [rbp+3Fh+string]
0x180082f07  lea     rcx, aInstallagent; "InstallAgent"
0x180082f0e  test    rax, rax
0x180082f11  cmovnz  rcx, rax
0x180082f15  mov     [rbp+3Fh+var_90], rcx
0x180082f19  mov     ebx, 400h
0x180082f1e  mov     [rbp+3Fh+var_A0], rbx
0x180082f22  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180082f29  mov     ecx, 800h; unsigned __int64
0x180082f2e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180082f33  mov     r12, rax
0x180082f36  mov     rcx, rax; pszDest
0x180082f39  mov     [rbp+3Fh+var_A8], rax
0x180082f3d  test    rax, rax
0x180082f40  jz      short loc_180082FAF
0x180082f42  test    rdi, rdi
0x180082f45  jz      short loc_180082F7E
0x180082f47  cmp     [rdi], r15w
0x180082f4b  jz      short loc_180082F7E
0x180082f4d  mov     [rsp+0F0h+var_C0], rdi
0x180082f52  lea     rax, aCatalogidS; "&catalogId=%s"
0x180082f59  mov     [rsp+0F0h+var_C8], rax; int
0x180082f5e  mov     qword ptr [rsp+0F0h+var_D0], r15; unsigned int
0x180082f63  lea     r9, [rbp+3Fh+var_A0]; unsigned __int64 *
0x180082f67  lea     r8, [rbp+3Fh+var_A8]; unsigned __int16 **
0x180082f6b  mov     edx, ebx; unsigned __int64
0x180082f6d  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180082f72  test    eax, eax
0x180082f74  js      short loc_180082FB4
0x180082f76  mov     rbx, [rbp+3Fh+var_A0]
0x180082f7a  mov     rcx, [rbp+3Fh+var_A8]; unsigned __int16 *
0x180082f7e  mov     r8, [rbp+3Fh+arg_20]; unsigned __int16 *
0x180082f82  mov     rdx, rbx; unsigned __int64
0x180082f85  call    ?GetExclusivityIds@@YAJPEAG_KPEBG@Z; GetExclusivityIds(ushort *,unsigned __int64,ushort const *)
0x180082f8a  mov     [rsp+0F0h+var_D0], eax; int
0x180082f8e  lea     r9, aGetexclusivity_0; "GetExclusivityIds(pszAdditionalQueryPar"...
0x180082f95  lea     r8, aMakebulkhydrat; "MakeBulkHydrateUri"
0x180082f9c  mov     edx, 2BDh; unsigned int
0x180082fa1  lea     rcx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x180082fa8  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180082fad  jmp     short loc_180082FB4
0x180082faf  mov     eax, 8007000Eh
0x180082fb4  mov     rbx, r15
0x180082fb7  mov     [rbp+3Fh+var_A8], rbx
0x180082fbb  mov     rdi, r15
0x180082fbe  mov     [rbp+3Fh+var_A0], r15
0x180082fc2  test    eax, eax
0x180082fc4  js      short loc_180083016
0x180082fc6  xor     ecx, ecx; string
0x180082fc8  call    cs:__imp_WindowsDeleteString
0x180082fce  mov     [rbp+3Fh+var_A0], r15
0x180082fd2  xor     ecx, ecx; string
0x180082fd4  call    cs:__imp_WindowsDeleteString
0x180082fda  mov     [rbp+3Fh+var_A8], r15
0x180082fde  lea     rdx, [rbp+3Fh+var_A0]; HSTRING *
0x180082fe2  lea     rcx, [rbp+3Fh+var_A8]; HSTRING *
0x180082fe6  call    ?GetLanguageAndRegion@@YAJPEAPEAUHSTRING__@@0@Z; GetLanguageAndRegion(HSTRING__ * *,HSTRING__ * *)
0x180082feb  mov     [rsp+0F0h+var_D0], eax; int
0x180082fef  lea     r9, aGetlanguageand; "GetLanguageAndRegion(language.GetAddres"...
0x180082ff6  lea     r8, aMakebulkhydrat; "MakeBulkHydrateUri"
0x180082ffd  mov     edx, 2C4h; unsigned int
0x180083002  lea     rcx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x180083009  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18008300e  mov     rbx, [rbp+3Fh+var_A8]
0x180083012  mov     rdi, [rbp+3Fh+var_A0]
0x180083016  mov     [rbp+3Fh+string], r15
0x18008301a  mov     [rbp+3Fh+var_98], r15
0x18008301e  lea     rcx, [rbp+3Fh+var_98]
0x180083022  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180083027  lea     rdx, [rbp+3Fh+var_98]
0x18008302b  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x180083030  mov     esi, eax
0x180083032  test    eax, eax
0x180083034  js      loc_1800831E8
0x18008303a  mov     [rbp+3Fh+arg_18], r15d
0x18008303e  mov     rax, [r13+0]
0x180083042  lea     rdx, [rbp+3Fh+arg_18]
0x180083046  mov     rcx, r13
0x180083049  mov     rax, [rax+38h]
0x18008304d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083052  mov     esi, eax
0x180083054  test    eax, eax
0x180083056  js      loc_1800831E8
0x18008305c  lea     r15d, [r14+64h]
0x180083060  cmp     r15d, [rbp+3Fh+arg_18]
0x180083064  cmova   r15d, [rbp+3Fh+arg_18]
0x180083069  cmp     r14d, r15d
0x18008306c  jnb     short loc_1800830BD
0x18008306e  mov     qword ptr [rbp+3Fh+var_B0], 0
0x180083076  mov     rax, [r13+0]
0x18008307a  lea     r8, [rbp+3Fh+var_B0]
0x18008307e  mov     edx, r14d
0x180083081  mov     rcx, r13
0x180083084  mov     rax, [rax+30h]
0x180083088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008308d  mov     esi, eax
0x18008308f  test    eax, eax
0x180083091  js      short loc_1800830A9
0x180083093  mov     rcx, [rbp+3Fh+var_98]
0x180083097  mov     rax, [rcx]
0x18008309a  mov     rdx, qword ptr [rbp+3Fh+var_B0]
0x18008309e  mov     rax, [rax+68h]
0x1800830a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800830a7  mov     esi, eax
0x1800830a9  inc     r14d
0x1800830ac  cmp     r14d, r15d
0x1800830af  jb      short loc_18008306E
0x1800830b1  xor     r15d, r15d
0x1800830b4  test    esi, esi
0x1800830b6  jns     short loc_1800830C0
0x1800830b8  jmp     loc_1800831E8
0x1800830bd  xor     r15d, r15d
0x1800830c0  mov     rcx, [rbp+3Fh+string]; string
0x1800830c4  call    cs:__imp_WindowsDeleteString
0x1800830ca  mov     [rbp+3Fh+string], r15
0x1800830ce  mov     edx, 2Ch ; ','
0x1800830d3  lea     r8, [rbp+3Fh+string]
0x1800830d7  mov     rcx, [rbp+3Fh+var_98]
0x1800830db  call    ?Join@StringHelpers@@SAJPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@GPEAPEAUHSTRING__@@@Z; StringHelpers::Join(Windows::Foundation::Collections::IVector<HSTRING__ *> *,ushort,HSTRING__ * *)
0x1800830e0  mov     [rsp+0F0h+var_D0], eax; int
0x1800830e4  lea     r9, aStringhelpersJ; "StringHelpers::Join(batchProductIds.Get"...
0x1800830eb  lea     r8, aMakebulkhydrat; "MakeBulkHydrateUri"
0x1800830f2  mov     edx, 2DEh; unsigned int
0x1800830f7  lea     rcx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x1800830fe  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180083103  mov     esi, eax
0x180083105  test    eax, eax
0x180083107  js      loc_1800831E8
0x18008310d  lea     rax, aProductidswith; "productIdsWithCommas"
0x180083114  mov     [rbp+3Fh+var_80], rax
0x180083118  xor     edx, edx; length
0x18008311a  mov     rcx, [rbp+3Fh+string]; string
0x18008311e  call    cs:__imp_WindowsGetStringRawBuffer
0x180083124  mov     [rbp+3Fh+var_78], rax
0x180083128  lea     rax, aLanguages; "languages"
0x18008312f  mov     [rbp+3Fh+var_70], rax
0x180083133  xor     edx, edx; length
0x180083135  mov     rcx, rbx; string
0x180083138  call    cs:__imp_WindowsGetStringRawBuffer
0x18008313e  mov     [rbp+3Fh+var_68], rax
0x180083142  lea     rax, aMarketcode; "marketCode"
0x180083149  mov     [rbp+3Fh+var_60], rax
0x18008314d  xor     edx, edx; length
0x18008314f  mov     rcx, rdi; string
0x180083152  call    cs:__imp_WindowsGetStringRawBuffer
0x180083158  mov     [rbp+3Fh+var_58], rax
0x18008315c  lea     rax, aFieldstemplate; "fieldsTemplate"
0x180083163  mov     [rbp+3Fh+var_50], rax
0x180083167  mov     rax, [rbp+3Fh+var_90]
0x18008316b  mov     [rbp+3Fh+var_48], rax
0x18008316f  mov     qword ptr [rbp+3Fh+var_B0], r15
0x180083173  lea     rcx, [rbp+3Fh+var_B0]
0x180083177  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18008317c  lea     rax, [rbp+3Fh+var_B0]
0x180083180  mov     [rsp+0F0h+var_C8], rax; int
0x180083185  mov     rax, [rbp+3Fh+arg_30]
0x180083189  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18008318e  mov     r9, r12
0x180083191  mov     r8d, 4
0x180083197  lea     rdx, [rbp+3Fh+var_80]
0x18008319b  lea     ecx, [r8-3]
0x18008319f  call    ?GetSLSUri@@YAJW4SLSIndex@@PEBUANNOTATION_VALUE@@_KPEBGPEAVTraceLoggingCorrelationVector@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; GetSLSUri(SLSIndex,ANNOTATION_VALUE const *,unsigned __int64,ushort const *,TraceLoggingCorrelationVector *,Windows::Foundation::IUriRuntimeClass * *)
0x1800831a4  mov     [rsp+0F0h+var_D0], eax; int
0x1800831a8  lea     r9, aGetslsuriSlsbu; "GetSLSUri(slsBulkHydrate, rgAnnotationV"...
0x1800831af  lea     r8, aMakebulkhydrat; "MakeBulkHydrateUri"
0x1800831b6  mov     edx, 2ECh; unsigned int
0x1800831bb  lea     rcx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x1800831c2  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800831c7  mov     esi, eax
0x1800831c9  test    eax, eax
0x1800831cb  js      short loc_1800831DF
0x1800831cd  mov     rax, qword ptr [rbp+3Fh+var_B0]
0x1800831d1  mov     qword ptr [rbp+3Fh+var_B0], r15
0x1800831d5  mov     rcx, [rbp+3Fh+arg_38]
0x1800831dc  mov     [rcx], rax
0x1800831df  lea     rcx, [rbp+3Fh+var_B0]
0x1800831e3  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800831e8  test    r12, r12
0x1800831eb  jz      short loc_1800831F6
0x1800831ed  mov     rcx, r12; void *
0x1800831f0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800831f5  nop
0x1800831f6  lea     rcx, [rbp+3Fh+var_98]
0x1800831fa  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800831ff  nop
0x180083200  mov     rcx, [rbp+3Fh+string]; string
0x180083204  call    cs:__imp_WindowsDeleteString
0x18008320a  mov     [rbp+3Fh+string], r15
0x18008320e  mov     rcx, rdi; string
0x180083211  call    cs:__imp_WindowsDeleteString
0x180083217  nop
0x180083218  mov     rcx, rbx; string
0x18008321b  call    cs:__imp_WindowsDeleteString
0x180083221  mov     eax, esi
0x180083223  add     rsp, 0B8h
0x18008322a  pop     r15
0x18008322c  pop     r14
0x18008322e  pop     r13
0x180083230  pop     r12
0x180083232  pop     rdi
0x180083233  pop     rsi
0x180083234  pop     rbx
0x180083235  pop     rbp
0x180083236  retn
```
