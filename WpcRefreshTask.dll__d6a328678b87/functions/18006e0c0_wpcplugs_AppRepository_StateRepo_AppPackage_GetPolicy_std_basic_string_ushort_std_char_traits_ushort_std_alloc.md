# wpcplugs::AppRepository::StateRepo::AppPackage::GetPolicy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18006e0c0`
- end: `0x18006e495`
- name: `?GetPolicy@AppPackage@StateRepo@AppRepository@wpcplugs@@UEBA?AV?$shared_ptr@UIAppPackagePolicy@AppRepository@wpcplugs@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@0@Z`
- size: `981`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800060a0`
- `0x1800093a0`
- `0x180009a80`
- `0x18001015c`
- `0x18001ccf0`
- `0x18002ca60`
- `0x18002eb3c`
- `0x18003e0c8`
- `0x18006d450`
- `0x18006e0c0`
- `0x18006e4f4`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006e12d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006e12d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006e167`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006e167`

## string_xrefs

- `0x18006e419`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006e43c`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006e459`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006e46e`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006e483`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 *__fastcall wpcplugs::AppRepository::StateRepo::AppPackage::GetPolicy(
        __int64 a1,
        __int64 *a2,
        char *a3,
        __int64 *a4)
{
  HRESULT StringReference; // eax
  int v9; // edx
  unsigned int v10; // r8d
  int ActivationFactory; // eax
  unsigned int v12; // r8d
  wil::details::in1diag3 *v13; // rcx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, _QWORD, PVOID); // r14
  __int64 *v16; // rax
  HSTRING_HEADER *v17; // rax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  const struct TickCount *v21; // rdx
  __int64 v22; // rdi
  __int64 *v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  void (*v27)(void); // rax
  __int64 *v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  unsigned int v33; // eax
  int v34; // [rsp+20h] [rbp-89h]
  __int64 v35; // [rsp+30h] [rbp-79h] BYREF
  __int64 *v36; // [rsp+38h] [rbp-71h] BYREF
  int v37[2]; // [rsp+40h] [rbp-69h] BYREF
  __int64 v38; // [rsp+48h] [rbp-61h] BYREF
  __int64 *v39; // [rsp+50h] [rbp-59h] BYREF
  int v40; // [rsp+58h] [rbp-51h] BYREF
  __int64 v41; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v42[16]; // [rsp+70h] [rbp-39h] BYREF
  _QWORD v43[2]; // [rsp+80h] [rbp-29h] BYREF
  __int128 hstringHeader; // [rsp+90h] [rbp-19h] BYREF
  __m128i hstringHeader_16; // [rsp+A0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v39 = a2;
  anonymous_namespace_::GetUserFromStateRepo(&v38, a3);
  if ( !v38 )
  {
    v33 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D1,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)v33,
      v34);
  }
  v35 = 0;
  hstringHeader_16.m128i_i64[1] = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.Internal.StateRepository.PackagePolicy",
                      0x2Eu,
                      (HSTRING_HEADER *)&hstringHeader,
                      (HSTRING *)&hstringHeader_16.m128i_i64[1]);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v9, v10);
LABEL_36:
    wil::details::in1diag3::Throw_Hr(
      v13,
      (void *)0x1D5,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v34);
  }
  ActivationFactory = RoGetActivationFactory(
                        hstringHeader_16.m128i_i64[1],
                        &GUID_93b105c2_0759_4c56_b8da_6e8f72ac464e,
                        &v35);
  v13 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_36;
  *(_QWORD *)v37 = 0;
  v14 = v35;
  v15 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, PVOID))(*(_QWORD *)v35 + 440LL);
  if ( (unsigned __int64)a4[3] <= 7 )
    v16 = a4;
  else
    v16 = (__int64 *)*a4;
  v39 = v16;
  v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          (HSTRING_HEADER *)&hstringHeader,
          (const WCHAR **)&v39,
          v12);
  v18 = v15(v14, v38, *(_QWORD *)(a1 + 8), v17[1].Reserved.Reserved1);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D8,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v18,
      (int)v37);
  v40 = 0;
  v19 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v37 + 56LL))(*(_QWORD *)v37, &v40);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DB,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v19,
      (int)v37);
  v36 = 0;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64 **))(**(_QWORD **)v37 + 48LL))(*(_QWORD *)v37, 0, &v36) < 0 )
  {
    *(_OWORD *)a2 = 0;
    *a2 = 0;
    a2[1] = 0;
    v28 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
    }
    v29 = *(_QWORD *)v37;
    if ( *(_QWORD *)v37 )
    {
      *(_QWORD *)v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v38;
    if ( v38 )
    {
      v38 = 0;
      v27 = *(void (**)(void))(*(_QWORD *)v31 + 16LL);
      goto LABEL_31;
    }
  }
  else
  {
    v41 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*v36 + 208))(v36, &v41);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1E4,
        (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
        (const char *)(unsigned int)v20,
        (int)v37);
    hstringHeader = 0;
    hstringHeader_16 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(hstringHeader) = 0;
    DateTime::DateTime((DateTime *)v42, v21);
    std::make_shared<wpcplugs::AppRepository::StateRepo::AppPackagePolicy,>(v43);
    v22 = v43[0];
    (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)v43[0] + 16LL))(v43[0], a3);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 32LL))(v22, a4);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 48LL))(v22, v41);
    v39 = v36;
    if ( v36 )
      (*(void (__fastcall **)(__int64 *))(*v36 + 8))(v36);
    if ( (int)wpcplugs::AppRepository::StateRepo::Private::GetMetaDataFromPolicy(
                (char **)&hstringHeader,
                (__int64)v42,
                &v39) >= 0 )
    {
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v22 + 64LL))(v22, &hstringHeader);
      (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v22 + 80LL))(v22, v42);
    }
    *a2 = v22;
    a2[1] = v43[1];
    std::wstring::~wstring((char **)&hstringHeader);
    v23 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
    }
    v24 = *(_QWORD *)v37;
    if ( *(_QWORD *)v37 )
    {
      *(_QWORD *)v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = v38;
    if ( v38 )
    {
      v38 = 0;
      v27 = *(void (**)(void))(*(_QWORD *)v26 + 16LL);
LABEL_31:
      v27();
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18006e0c0  push    rbp
0x18006e0c2  push    rbx
0x18006e0c3  push    rsi
0x18006e0c4  push    rdi
0x18006e0c5  push    r12
0x18006e0c7  push    r13
0x18006e0c9  push    r14
0x18006e0cb  push    r15
0x18006e0cd  lea     rbp, [rsp-1Fh]
0x18006e0d2  sub     rsp, 0C8h
0x18006e0d9  mov     rax, cs:__security_cookie
0x18006e0e0  xor     rax, rsp
0x18006e0e3  mov     [rbp+57h+var_50], rax
0x18006e0e7  mov     rsi, r9
0x18006e0ea  mov     r15, r8
0x18006e0ed  mov     rbx, rdx
0x18006e0f0  mov     r13, rcx
0x18006e0f3  mov     [rbp+57h+var_B0], rdx
0x18006e0f7  xor     r12d, r12d
0x18006e0fa  mov     rdx, r8
0x18006e0fd  lea     rcx, [rbp+57h+var_B8]
0x18006e101  call    _anonymous_namespace___GetUserFromStateRepo
0x18006e106  nop
0x18006e107  cmp     [rbp+57h+var_B8], r12
0x18006e10b  jz      loc_18006E42B
0x18006e111  mov     [rbp+57h+var_D0], r12
0x18006e115  mov     [rbp+57h+string], r12
0x18006e119  lea     r9, [rbp+57h+string]; string
0x18006e11d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006e121  lea     edx, [r12+2Eh]; length
0x18006e126  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackagePolicy@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18006e12d  call    cs:__imp_WindowsCreateStringReference
0x18006e133  test    eax, eax
0x18006e135  js      loc_18006E44E
0x18006e13b  mov     rdi, [rbp+57h+string]
0x18006e13f  mov     rcx, [rbp+57h+var_D0]
0x18006e143  test    rcx, rcx
0x18006e146  jz      short loc_18006E159
0x18006e148  mov     [rbp+57h+var_D0], r12
0x18006e14c  mov     rax, [rcx]
0x18006e14f  mov     rax, [rax+10h]
0x18006e153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e158  nop
0x18006e159  lea     r8, [rbp+57h+var_D0]
0x18006e15d  lea     rdx, _GUID_93b105c2_0759_4c56_b8da_6e8f72ac464e
0x18006e164  mov     rcx, rdi
0x18006e167  call    cs:__imp_RoGetActivationFactory
0x18006e16d  mov     rcx, [rbp+5Fh]
0x18006e171  test    eax, eax
0x18006e173  js      loc_18006E456
0x18006e179  mov     qword ptr [rbp+57h+var_C0], r12
0x18006e17d  mov     rdi, [rbp+57h+var_D0]
0x18006e181  mov     rax, [rdi]
0x18006e184  mov     r14, [rax+1B8h]
0x18006e18b  cmp     qword ptr [rsi+18h], 7
0x18006e190  jbe     short loc_18006E197
0x18006e192  mov     rax, [rsi]
0x18006e195  jmp     short loc_18006E19A
0x18006e197  mov     rax, rsi
0x18006e19a  mov     [rbp+57h+var_B0], rax
0x18006e19e  lea     rdx, [rbp+57h+var_B0]
0x18006e1a2  lea     rcx, [rbp+57h+hstringHeader]
0x18006e1a6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18006e1ab  nop
0x18006e1ac  lea     rcx, [rbp+57h+var_C0]
0x18006e1b0  mov     qword ptr [rsp+100h+var_E0], rcx; int
0x18006e1b5  mov     r9, [rax+18h]
0x18006e1b9  mov     r8, [r13+8]
0x18006e1bd  mov     rdx, [rbp+57h+var_B8]
0x18006e1c1  mov     rcx, rdi
0x18006e1c4  mov     rax, r14
0x18006e1c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1cc  mov     rcx, [rbp+5Fh]; this
0x18006e1d0  test    eax, eax
0x18006e1d2  js      loc_18006E46B
0x18006e1d8  mov     [rbp+57h+var_A8], r12d
0x18006e1dc  mov     rcx, qword ptr [rbp+57h+var_C0]
0x18006e1e0  mov     rax, [rcx]
0x18006e1e3  lea     rdx, [rbp+57h+var_A8]
0x18006e1e7  mov     rax, [rax+38h]
0x18006e1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1f0  mov     rcx, [rbp+5Fh]; this
0x18006e1f4  test    eax, eax
0x18006e1f6  js      loc_18006E480
0x18006e1fc  mov     [rbp+57h+var_C8], r12
0x18006e200  mov     rcx, qword ptr [rbp+57h+var_C0]
0x18006e204  mov     rax, [rcx]
0x18006e207  lea     r8, [rbp+57h+var_C8]
0x18006e20b  xor     edx, edx
0x18006e20d  mov     rax, [rax+30h]
0x18006e211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e216  test    eax, eax
0x18006e218  js      loc_18006E37E
0x18006e21e  mov     [rbp+57h+var_A0], r12
0x18006e222  mov     rcx, [rbp+57h+var_C8]
0x18006e226  mov     rax, [rcx]
0x18006e229  lea     rdx, [rbp+57h+var_A0]
0x18006e22d  mov     rax, [rax+0D0h]
0x18006e234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e239  mov     rcx, [rbp+5Fh]; this
0x18006e23d  test    eax, eax
0x18006e23f  js      loc_18006E416
0x18006e245  xorps   xmm0, xmm0
0x18006e248  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18006e24c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18006e254  movdqu  xmmword ptr [rbp-9], xmm1
0x18006e259  mov     word ptr [rbp+57h+hstringHeader.Reserved], r12w
0x18006e25e  lea     rcx, [rbp+57h+var_90]; this
0x18006e262  call    ??0DateTime@@QEAA@AEBVTickCount@@@Z; DateTime::DateTime(TickCount const &)
0x18006e267  lea     rcx, [rbp+57h+var_80]
0x18006e26b  call    ??$make_shared@VAppPackagePolicy@StateRepo@AppRepository@wpcplugs@@$$V@std@@YA?AV?$shared_ptr@VAppPackagePolicy@StateRepo@AppRepository@wpcplugs@@@0@XZ; std::make_shared<wpcplugs::AppRepository::StateRepo::AppPackagePolicy,>(void)
0x18006e270  nop
0x18006e271  mov     rdi, [rbp+57h+var_80]
0x18006e275  mov     rax, [rdi]
0x18006e278  mov     rdx, r15
0x18006e27b  mov     rcx, rdi
0x18006e27e  mov     rax, [rax+10h]
0x18006e282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e287  mov     rax, [rdi]
0x18006e28a  mov     rdx, rsi
0x18006e28d  mov     rcx, rdi
0x18006e290  mov     rax, [rax+20h]
0x18006e294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e299  mov     rax, [rdi]
0x18006e29c  mov     rdx, [rbp+57h+var_A0]
0x18006e2a0  mov     rcx, rdi
0x18006e2a3  mov     rax, [rax+30h]
0x18006e2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e2ac  mov     rcx, [rbp+57h+var_C8]
0x18006e2b0  mov     [rbp+57h+var_B0], rcx
0x18006e2b4  test    rcx, rcx
0x18006e2b7  jz      short loc_18006E2C6
0x18006e2b9  mov     rax, [rcx]
0x18006e2bc  mov     rax, [rax+8]
0x18006e2c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e2c5  nop
0x18006e2c6  lea     r8, [rbp+57h+var_B0]
0x18006e2ca  lea     rdx, [rbp+57h+var_90]
0x18006e2ce  lea     rcx, [rbp+57h+hstringHeader]
0x18006e2d2  call    ?GetMetaDataFromPolicy@Private@StateRepo@AppRepository@wpcplugs@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVDateTime@@V?$ComPtr@UIPackagePolicy@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z; wpcplugs::AppRepository::StateRepo::Private::GetMetaDataFromPolicy(std::wstring &,DateTime &,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackagePolicy>)
0x18006e2d7  test    eax, eax
0x18006e2d9  js      short loc_18006E301
0x18006e2db  mov     rax, [rdi]
0x18006e2de  lea     rdx, [rbp+57h+hstringHeader]
0x18006e2e2  mov     rcx, rdi
0x18006e2e5  mov     rax, [rax+40h]
0x18006e2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e2ee  mov     rax, [rdi]
0x18006e2f1  lea     rdx, [rbp+57h+var_90]
0x18006e2f5  mov     rcx, rdi
0x18006e2f8  mov     rax, [rax+50h]
0x18006e2fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e301  mov     [rbx], rdi
0x18006e304  mov     rax, [rbp+57h+var_78]
0x18006e308  mov     [rbx+8], rax
0x18006e30c  lea     rcx, [rbp+57h+hstringHeader]
0x18006e310  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006e315  nop
0x18006e316  mov     rcx, [rbp+57h+var_C8]
0x18006e31a  test    rcx, rcx
0x18006e31d  jz      short loc_18006E330
0x18006e31f  mov     [rbp+57h+var_C8], r12
0x18006e323  mov     rax, [rcx]
0x18006e326  mov     rax, [rax+10h]
0x18006e32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e32f  nop
0x18006e330  mov     rcx, qword ptr [rbp+57h+var_C0]
0x18006e334  test    rcx, rcx
0x18006e337  jz      short loc_18006E34A
0x18006e339  mov     qword ptr [rbp+57h+var_C0], r12
0x18006e33d  mov     rax, [rcx]
0x18006e340  mov     rax, [rax+10h]
0x18006e344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e349  nop
0x18006e34a  mov     rcx, [rbp+57h+var_D0]
0x18006e34e  test    rcx, rcx
0x18006e351  jz      short loc_18006E364
0x18006e353  mov     [rbp+57h+var_D0], r12
0x18006e357  mov     rax, [rcx]
0x18006e35a  mov     rax, [rax+10h]
0x18006e35e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e363  nop
0x18006e364  mov     rcx, [rbp+57h+var_B8]
0x18006e368  test    rcx, rcx
0x18006e36b  jz      loc_18006E3F3
0x18006e371  mov     [rbp+57h+var_B8], r12
0x18006e375  mov     rax, [rcx]
0x18006e378  mov     rax, [rax+10h]
0x18006e37c  jmp     short loc_18006E3ED
0x18006e37e  xorps   xmm0, xmm0
0x18006e381  movups  xmmword ptr [rbx], xmm0
0x18006e384  mov     [rbx], r12
0x18006e387  mov     [rbx+8], r12
0x18006e38b  mov     rcx, [rbp+57h+var_C8]
0x18006e38f  test    rcx, rcx
0x18006e392  jz      short loc_18006E3A5
0x18006e394  mov     [rbp+57h+var_C8], r12
0x18006e398  mov     rax, [rcx]
0x18006e39b  mov     rax, [rax+10h]
0x18006e39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3a4  nop
0x18006e3a5  mov     rcx, qword ptr [rbp+57h+var_C0]
0x18006e3a9  test    rcx, rcx
0x18006e3ac  jz      short loc_18006E3BF
0x18006e3ae  mov     qword ptr [rbp+57h+var_C0], r12
0x18006e3b2  mov     rax, [rcx]
0x18006e3b5  mov     rax, [rax+10h]
0x18006e3b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3be  nop
0x18006e3bf  mov     rcx, [rbp+57h+var_D0]
0x18006e3c3  test    rcx, rcx
0x18006e3c6  jz      short loc_18006E3D9
0x18006e3c8  mov     [rbp+57h+var_D0], r12
0x18006e3cc  mov     rax, [rcx]
0x18006e3cf  mov     rax, [rax+10h]
0x18006e3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3d8  nop
0x18006e3d9  mov     rcx, [rbp+57h+var_B8]
0x18006e3dd  test    rcx, rcx
0x18006e3e0  jz      short loc_18006E3F3
0x18006e3e2  mov     [rbp+57h+var_B8], r12
0x18006e3e6  mov     rdx, [rcx]
0x18006e3e9  mov     rax, [rdx+10h]
0x18006e3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3f2  nop
0x18006e3f3  mov     rax, rbx
0x18006e3f6  mov     rcx, [rbp+57h+var_50]
0x18006e3fa  xor     rcx, rsp; StackCookie
0x18006e3fd  call    __security_check_cookie
0x18006e402  add     rsp, 0C8h
0x18006e409  pop     r15
0x18006e40b  pop     r14
0x18006e40d  pop     r13
0x18006e40f  pop     r12
0x18006e411  pop     rdi
0x18006e412  pop     rsi
0x18006e413  pop     rbx
0x18006e414  pop     rbp
0x18006e415  retn
0x18006e416  mov     r9d, eax; char *
0x18006e419  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006e420  mov     edx, 1E4h; void *
0x18006e425  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006e42b  mov     ecx, 80070057h
0x18006e430  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18006e435  mov     r9d, eax; char *
0x18006e438  mov     rcx, [rbp+5Fh]; this
0x18006e43c  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006e443  mov     edx, 1D1h; void *
0x18006e448  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006e44e  mov     ecx, eax; this
0x18006e450  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18006e455  nop
0x18006e456  mov     r9d, eax; char *
0x18006e459  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006e460  mov     edx, 1D5h; void *
0x18006e465  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006e46b  mov     r9d, eax; char *
0x18006e46e  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006e475  mov     edx, 1D8h; void *
0x18006e47a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006e480  mov     r9d, eax; char *
0x18006e483  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006e48a  mov     edx, 1DBh; void *
0x18006e48f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
