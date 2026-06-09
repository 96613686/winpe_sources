# Windows::Internal::CapabilityAccess::Private::PackageFamilyHasCapability(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const *,bool *)

- ea: `0x180044f4c`
- end: `0x1800451f7`
- name: `?PackageFamilyHasCapability@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@PEA_N@Z`
- size: `683`
- prototype: ``
- caller_count: `8`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180031ef0`
- `0x1800441b8`
- `0x1800447f8`
- `0x18006ae88`
- `0x180075d14`
- `0x180077930`
- `0x180077aec`
- `0x180079988`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001c3b4`
- `0x18001f5f4`
- `0x18002392c`
- `0x180029408`
- `0x18003e53c`
- `0x18003e660`
- `0x18003f62c`
- `0x1800430e8`
- `0x180044f4c`
- `0x180045434`
- `0x180045f78`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045135`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045135`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045175`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045175`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall Windows::Internal::CapabilityAccess::Private::PackageFamilyHasCapability(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        _BYTE *a5)
{
  const unsigned __int16 (*v8)[41]; // rdx
  __int64 *v9; // rax
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, HSTRING, __int64); // rbx
  const unsigned __int16 *v13; // rax
  int v14; // eax
  int v15; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  PCWSTR StringRawBuffer; // rax
  char HasCapability; // bl
  int v25; // [rsp+20h] [rbp-51h]
  HSTRING string; // [rsp+30h] [rbp-41h] BYREF
  int v27[2]; // [rsp+38h] [rbp-39h] BYREF
  int v28; // [rsp+40h] [rbp-31h] BYREF
  __int64 v29; // [rsp+48h] [rbp-29h] BYREF
  __int64 v30; // [rsp+50h] [rbp-21h] BYREF
  __int64 v31; // [rsp+58h] [rbp-19h] BYREF
  HSTRING v32[4]; // [rsp+60h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  v30 = 0;
  *(_QWORD *)v27 = 0;
  v29 = 0;
  v28 = 0;
  string = 0;
  Windows::Internal::CapabilityAccess::Private::GetSrUserFromSid(&v31, a1);
  v9 = (__int64 *)Windows::Internal::StringReference::StringReference(v32, v8);
  v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
          *v9,
          (__int64)&v30);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v10,
      v25);
  v11 = v30;
  v12 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64))(*(_QWORD *)v30 + 504LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
  v13 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v32, v13);
  v14 = v12(v11, v31, v32[0], 1);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x472,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v14,
      (int)v27);
  v15 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v27 + 56LL))(*(_QWORD *)v27, &v28);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x474,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v15,
      (int)v27);
  if ( !v28 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x475,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)0x80070490LL,
      (int)v27);
  if ( v28 == 1 )
  {
    v17 = *(_QWORD *)v27;
    v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v27 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    v19 = v18(v17, 0, &v29);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x47C,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)(unsigned int)v19,
        (int)v27);
    v20 = v29;
    v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 112LL);
    WindowsDeleteString(string);
    string = 0;
    v22 = v21(v20, &string);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x47F,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)(unsigned int)v22,
        (int)v27);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring(v32, StringRawBuffer);
    HasCapability = Windows::Internal::CapabilityAccess::Private::PackageHasCapability(v32, a3, a4, a5);
    std::wstring::_Tidy_deallocate(v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    return HasCapability;
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    return 0;
  }
}

```

## disassembly

```asm
0x180044f4c  push    rbp
0x180044f4e  push    rbx
0x180044f4f  push    rsi
0x180044f50  push    rdi
0x180044f51  push    r12
0x180044f53  push    r14
0x180044f55  push    r15
0x180044f57  lea     rbp, [rsp-1Fh]
0x180044f5c  sub     rsp, 90h
0x180044f63  mov     rax, cs:__security_cookie
0x180044f6a  xor     rax, rsp
0x180044f6d  mov     [rbp+4Fh+var_40], rax
0x180044f71  mov     r15, r9
0x180044f74  mov     r14, r8
0x180044f77  mov     rsi, rdx
0x180044f7a  mov     r12, [rbp+4Fh+arg_20]
0x180044f7e  mov     [rbp+4Fh+var_70], 0
0x180044f86  mov     qword ptr [rbp+4Fh+var_88], 0
0x180044f8e  mov     [rbp+4Fh+var_78], 0
0x180044f96  mov     [rbp+4Fh+var_80], 0
0x180044f9d  mov     [rbp+4Fh+string], 0
0x180044fa5  mov     rdx, rcx
0x180044fa8  lea     rcx, [rbp+4Fh+var_68]
0x180044fac  call    ?GetSrUserFromSid@Private@CapabilityAccess@Internal@Windows@@YA?AV?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::GetSrUserFromSid(std::wstring const &)
0x180044fb1  nop
0x180044fb2  lea     rcx, [rbp+4Fh+var_60]; string
0x180044fb6  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x180044fbb  lea     rdx, [rbp+4Fh+var_70]
0x180044fbf  mov     rcx, [rax]
0x180044fc2  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x180044fc7  mov     rcx, [rbp+57h]; this
0x180044fcb  test    eax, eax
0x180044fcd  jns     short loc_180044FE4
0x180044fcf  mov     r9d, eax; char *
0x180044fd2  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180044fd9  mov     edx, 46Ch; void *
0x180044fde  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044fe4  mov     rdi, [rbp+4Fh+var_70]
0x180044fe8  mov     rax, [rdi]
0x180044feb  mov     rbx, [rax+1F8h]
0x180044ff2  lea     rcx, [rbp+4Fh+var_88]
0x180044ff6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044ffb  mov     rcx, rsi
0x180044ffe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045003  mov     rdx, rax; unsigned __int16 *
0x180045006  lea     rcx, [rbp+4Fh+var_60]; this
0x18004500a  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18004500f  lea     rax, [rbp+4Fh+var_88]
0x180045013  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180045018  mov     r9d, 1
0x18004501e  mov     r8, [rbp+4Fh+var_60]
0x180045022  mov     rdx, [rbp+4Fh+var_68]
0x180045026  mov     rcx, rdi
0x180045029  mov     rax, rbx
0x18004502c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045031  mov     rcx, [rbp+57h]; this
0x180045035  test    eax, eax
0x180045037  jns     short loc_18004504E
0x180045039  mov     r9d, eax; char *
0x18004503c  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180045043  mov     edx, 472h; void *
0x180045048  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004504e  mov     rcx, qword ptr [rbp+4Fh+var_88]
0x180045052  mov     rax, [rcx]
0x180045055  lea     rdx, [rbp+4Fh+var_80]
0x180045059  mov     rax, [rax+38h]
0x18004505d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045062  mov     rcx, [rbp+57h]; this
0x180045066  test    eax, eax
0x180045068  jns     short loc_18004507F
0x18004506a  mov     r9d, eax; char *
0x18004506d  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180045074  mov     edx, 474h; void *
0x180045079  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004507f  mov     edx, [rbp+4Fh+var_80]
0x180045082  test    edx, edx
0x180045084  setz    al
0x180045087  mov     rcx, [rbp+57h]; this
0x18004508b  test    al, al
0x18004508d  jz      short loc_1800450A7
0x18004508f  mov     r9d, 80070490h; char *
0x180045095  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004509c  mov     edx, 475h; void *
0x1800450a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800450a7  cmp     edx, 1
0x1800450aa  jz      short loc_1800450E4
0x1800450ac  lea     rcx, [rbp+4Fh+var_68]
0x1800450b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800450b5  nop
0x1800450b6  lea     rcx, [rbp+4Fh+string]; this
0x1800450ba  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800450bf  nop
0x1800450c0  lea     rcx, [rbp+4Fh+var_78]
0x1800450c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800450c9  nop
0x1800450ca  lea     rcx, [rbp+4Fh+var_88]
0x1800450ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800450d3  nop
0x1800450d4  lea     rcx, [rbp+4Fh+var_70]
0x1800450d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800450dd  xor     al, al
0x1800450df  jmp     loc_1800451D9
0x1800450e4  mov     rdi, qword ptr [rbp+4Fh+var_88]
0x1800450e8  mov     rax, [rdi]
0x1800450eb  mov     rbx, [rax+30h]
0x1800450ef  lea     rcx, [rbp+4Fh+var_78]
0x1800450f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800450f8  lea     r8, [rbp+4Fh+var_78]
0x1800450fc  xor     edx, edx
0x1800450fe  mov     rcx, rdi
0x180045101  mov     rax, rbx
0x180045104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045109  mov     rcx, [rbp+57h]; this
0x18004510d  test    eax, eax
0x18004510f  jns     short loc_180045126
0x180045111  mov     r9d, eax; char *
0x180045114  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004511b  mov     edx, 47Ch; void *
0x180045120  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045126  mov     rdi, [rbp+4Fh+var_78]
0x18004512a  mov     rax, [rdi]
0x18004512d  mov     rbx, [rax+70h]
0x180045131  mov     rcx, [rbp+4Fh+string]; string
0x180045135  call    cs:__imp_WindowsDeleteString
0x18004513b  mov     [rbp+4Fh+string], 0
0x180045143  lea     rdx, [rbp+4Fh+string]
0x180045147  mov     rcx, rdi
0x18004514a  mov     rax, rbx
0x18004514d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045152  mov     rcx, [rbp+57h]; this
0x180045156  test    eax, eax
0x180045158  jns     short loc_18004516F
0x18004515a  mov     r9d, eax; char *
0x18004515d  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180045164  mov     edx, 47Fh; void *
0x180045169  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004516f  xor     edx, edx; length
0x180045171  mov     rcx, [rbp+4Fh+string]; string
0x180045175  call    cs:__imp_WindowsGetStringRawBuffer
0x18004517b  mov     rdx, rax
0x18004517e  lea     rcx, [rbp+4Fh+var_60]
0x180045182  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180045187  nop
0x180045188  mov     r9, r12
0x18004518b  mov     r8, r15
0x18004518e  mov     rdx, r14
0x180045191  lea     rcx, [rbp+4Fh+var_60]
0x180045195  call    ?PackageHasCapability@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@PEA_N@Z; Windows::Internal::CapabilityAccess::Private::PackageHasCapability(std::wstring const &,std::wstring const &,std::vector<std::wstring> const *,bool *)
0x18004519a  mov     bl, al
0x18004519c  lea     rcx, [rbp+4Fh+var_60]
0x1800451a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800451a5  nop
0x1800451a6  lea     rcx, [rbp+4Fh+var_68]
0x1800451aa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800451af  nop
0x1800451b0  lea     rcx, [rbp+4Fh+string]; this
0x1800451b4  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800451b9  nop
0x1800451ba  lea     rcx, [rbp+4Fh+var_78]
0x1800451be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800451c3  nop
0x1800451c4  lea     rcx, [rbp+4Fh+var_88]
0x1800451c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800451cd  nop
0x1800451ce  lea     rcx, [rbp+4Fh+var_70]
0x1800451d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800451d7  mov     al, bl
0x1800451d9  mov     rcx, [rbp+4Fh+var_40]
0x1800451dd  xor     rcx, rsp; StackCookie
0x1800451e0  call    __security_check_cookie
0x1800451e5  add     rsp, 90h
0x1800451ec  pop     r15
0x1800451ee  pop     r14
0x1800451f0  pop     r12
0x1800451f2  pop     rdi
0x1800451f3  pop     rsi
0x1800451f4  pop     rbx
0x1800451f5  pop     rbp
0x1800451f6  retn
```
