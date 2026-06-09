# CtaHelpers::IsAppCapableLegacy(ushort const *,ushort const *)

- ea: `0x18005df3c`
- end: `0x18005e356`
- name: `?IsAppCapableLegacy@CtaHelpers@@YA_NPEBG0@Z`
- size: `1050`
- prototype: `bool(CtaHelpers *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005de8c`
- `0x1800b08cc`

## callees

- `0x180004e38`
- `0x18000de40`
- `0x18000e5f4`
- `0x180024614`
- `0x180024640`
- `0x180024844`
- `0x18005df3c`
- `0x18006a3f0`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005df78`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005df95`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005df78`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005df95`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18005dfb9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18005dfb9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005e0d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005e1bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005e33d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005e34f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005e0d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005e1bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005e33d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005e34f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e2ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e2ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005e01b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005e16a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005e01b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005e16a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005e046`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005e046`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e281`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e281`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005e07f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005e07f`

## string_xrefs

- `0x18005e0e3`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x18005e0fb`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x18005e113`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x18005e128`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x18005e13d`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x18005e2de`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x18005e2f3`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x18005e308`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x18005e320`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x18005e014`: `Windows.Internal.CapabilityAccess.CapabilityAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
bool __fastcall CtaHelpers::IsAppCapableLegacy(
        const WCHAR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  bool v5; // zf
  char v6; // al
  wil::details::in1diag3 *v7; // rcx
  wchar_t *v8; // rax
  int v9; // eax
  HRESULT v10; // eax
  HSTRING v11; // rbx
  int ActivationFactory; // eax
  unsigned int v13; // edx
  int UserSid; // eax
  _QWORD *v15; // r14
  __int64 v16; // r13
  WCHAR *v17; // rsi
  unsigned __int64 v18; // rdi
  unsigned __int64 v19; // rbx
  unsigned int v20; // eax
  UINT32 v21; // edx
  HRESULT v22; // eax
  HSTRING v23; // r15
  PVOID Reserved1; // r12
  const WCHAR *v25; // rbx
  unsigned int v26; // eax
  int v27; // eax
  __int64 v28; // rdx
  int v29; // eax
  int v30; // eax
  bool v31; // bl
  __int64 v32; // rcx
  _QWORD *v33; // rcx
  int v35; // [rsp+20h] [rbp-E0h]
  int v36[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v37; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v38; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  const WCHAR *v40; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR sourceString[3]; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-90h] BYREF
  HSTRING string; // [rsp+88h] [rbp-78h] BYREF
  HSTRING_HEADER v44; // [rsp+90h] [rbp-70h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-58h]
  HSTRING_HEADER v46; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE Sid[80]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v40 = this;
  if ( !(unsigned int)_o__wcsicmp(this, L"cellularData")
    || (v5 = (unsigned int)_o__wcsicmp(this, L"wifiData") == 0, v6 = 1, v5) )
  {
    v6 = 0;
  }
  v7 = retaddr;
  if ( v6 )
LABEL_15:
    wil::details::in1diag3::Throw_Hr(
      v7,
      (void *)0xE4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)0x80070057LL,
      v35);
  v8 = wcschr(a2, 0x21u);
  if ( !v8 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)0x80070057LL,
      v35);
  memset(sourceString, 0, sizeof(sourceString));
  v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         sourceString,
         a2,
         v8 - a2);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)v9,
      v35);
  v38 = 0;
  string = 0;
  v10 = WindowsCreateStringReference(
          L"Windows.Internal.CapabilityAccess.CapabilityAccess",
          0x32u,
          &hstringHeader,
          &string);
  if ( v10 < 0 )
  {
    RaiseException(v10, 1u, 0, 0);
    goto LABEL_44;
  }
  v11 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  ActivationFactory = RoGetActivationFactory(v11, &GUID_518f3880_4e5c_4524_ab03_cd01336b2178, &v38);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v35);
  UserSid = WpnGetUserSid(Sid, v13);
  if ( UserSid < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)UserSid,
      v35);
  StringSid = 0;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)0x8000FFFFLL,
      v35);
  *(_QWORD *)v36 = 0;
  v15 = v38;
  v16 = *v38;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v36);
  string = 0;
  v17 = (WCHAR *)sourceString[0];
  v18 = -1;
  v19 = -1;
  do
    ++v19;
  while ( sourceString[0][v19] );
  if ( v19 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_15;
  }
  v20 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v19);
  v21 = v20 - 1;
  if ( (unsigned int)v19 < v20 )
    v21 = v19;
  v22 = WindowsCreateStringReference(v17, v21, &hstringHeader, &string);
  if ( v22 < 0 )
  {
LABEL_44:
    RaiseException(v22, 1u, 0, 0);
    JUMPOUT(0x18005E355LL);
  }
  v23 = string;
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v46, &v40)[1].Reserved.Reserved1;
  v45 = 0;
  v25 = StringSid;
  do
    ++v18;
  while ( StringSid[v18] );
  if ( v18 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v26 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v18);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v44, v25, v26, v18);
  v27 = (*(__int64 (__fastcall **)(_QWORD *, __int64, PVOID, HSTRING))(v16 + 48))(v15, v45, Reserved1, v23);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)v27,
      (int)v36);
  LOBYTE(v28) = 1;
  v29 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v36 + 88LL))(*(_QWORD *)v36, v28);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)v29,
      (int)v36);
  v37 = 0;
  v30 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v36 + 152LL))(*(_QWORD *)v36, &v37);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)v30,
      (int)v36);
  v31 = v37 == 3;
  v32 = *(_QWORD *)v36;
  if ( *(_QWORD *)v36 )
  {
    *(_QWORD *)v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  if ( StringSid )
    LocalFree(StringSid);
  v33 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
  }
  if ( v17 )
    CoTaskMemFree(v17);
  return v31;
}

```

## disassembly

```asm
0x18005df3c  mov     [rsp-8+arg_10], rbx
0x18005df41  push    rbp
0x18005df42  push    rsi
0x18005df43  push    rdi
0x18005df44  push    r12
0x18005df46  push    r13
0x18005df48  push    r14
0x18005df4a  push    r15
0x18005df4c  lea     rbp, [rsp-30h]
0x18005df51  sub     rsp, 130h
0x18005df58  mov     rax, cs:__security_cookie
0x18005df5f  xor     rax, rsp
0x18005df62  mov     [rbp+60h+var_40], rax
0x18005df66  mov     rdi, rdx
0x18005df69  mov     rbx, rcx
0x18005df6c  mov     [rsp+160h+var_110], rcx
0x18005df71  lea     rdx, aCellulardata; "cellularData"
0x18005df78  call    cs:__imp__o__wcsicmp
0x18005df7e  mov     r12d, 1
0x18005df84  xor     r15d, r15d
0x18005df87  test    eax, eax
0x18005df89  jz      short loc_18005DFA2
0x18005df8b  lea     rdx, aWifidata; "wifiData"
0x18005df92  mov     rcx, rbx
0x18005df95  call    cs:__imp__o__wcsicmp
0x18005df9b  test    eax, eax
0x18005df9d  mov     al, r12b
0x18005dfa0  jnz     short loc_18005DFA5
0x18005dfa2  mov     al, r15b
0x18005dfa5  mov     rcx, [rbp+68h]
0x18005dfa9  test    al, al
0x18005dfab  jnz     loc_18005E0DD
0x18005dfb1  mov     edx, 21h ; '!'; Ch
0x18005dfb6  mov     rcx, rdi; Str
0x18005dfb9  call    cs:__imp_wcschr
0x18005dfbf  mov     rcx, [rbp+68h]; this
0x18005dfc3  test    rax, rax
0x18005dfc6  jz      loc_18005E31A
0x18005dfcc  mov     [rsp+160h+sourceString], r15
0x18005dfd1  mov     [rsp+160h+var_100], r15
0x18005dfd6  mov     [rsp+160h+var_F8], r15
0x18005dfdb  sub     rax, rdi
0x18005dfde  sar     rax, 1
0x18005dfe1  mov     r8, rax
0x18005dfe4  mov     rdx, rdi
0x18005dfe7  lea     rcx, [rsp+160h+sourceString]
0x18005dfec  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18005dff1  mov     rcx, [rbp+68h]; this
0x18005dff5  test    eax, eax
0x18005dff7  js      loc_18005E110
0x18005dffd  mov     [rsp+160h+var_120], r15
0x18005e002  mov     [rbp+60h+string], r15
0x18005e006  lea     r9, [rbp+60h+string]; string
0x18005e00a  lea     r8, [rsp+160h+hstringHeader]; hstringHeader
0x18005e00f  mov     edx, 32h ; '2'; length
0x18005e014  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x18005e01b  call    cs:__imp_WindowsCreateStringReference
0x18005e021  test    eax, eax
0x18005e023  js      loc_18005E332
0x18005e029  mov     rbx, [rbp+60h+string]
0x18005e02d  lea     rcx, [rsp+160h+var_120]
0x18005e032  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005e037  lea     r8, [rsp+160h+var_120]
0x18005e03c  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x18005e043  mov     rcx, rbx
0x18005e046  call    cs:__imp_RoGetActivationFactory
0x18005e04c  mov     rcx, [rbp+68h]; this
0x18005e050  test    eax, eax
0x18005e052  js      loc_18005E125
0x18005e058  lea     rcx, [rbp+60h+Sid]; void *
0x18005e05c  call    ?WpnGetUserSid@@YAJPEAXK@Z; WpnGetUserSid(void *,ulong)
0x18005e061  mov     rcx, [rbp+68h]; this
0x18005e065  test    eax, eax
0x18005e067  js      loc_18005E13A
0x18005e06d  mov     [rsp+160h+StringSid], r15
0x18005e072  mov     rbx, [rbp+68h]
0x18005e076  lea     rdx, [rsp+160h+StringSid]; StringSid
0x18005e07b  lea     rcx, [rbp+60h+Sid]; Sid
0x18005e07f  call    cs:__imp_ConvertSidToStringSidW
0x18005e085  test    eax, eax
0x18005e087  jz      short loc_18005E0F5
0x18005e089  mov     qword ptr [rsp+160h+var_130], r15
0x18005e08e  mov     r14, [rsp+160h+var_120]
0x18005e093  mov     r13, [r14]
0x18005e096  lea     rcx, [rsp+160h+var_130]
0x18005e09b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005e0a0  mov     [rbp+60h+string], r15
0x18005e0a4  mov     rsi, [rsp+160h+sourceString]
0x18005e0a9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005e0ad  mov     rbx, rdi
0x18005e0b0  inc     rbx
0x18005e0b3  cmp     [rsi+rbx*2], r15w
0x18005e0b8  jnz     short loc_18005E0B0
0x18005e0ba  mov     eax, 0FFFFFFFFh
0x18005e0bf  cmp     rbx, rax
0x18005e0c2  jbe     loc_18005E14F
0x18005e0c8  xor     r9d, r9d; lpArguments
0x18005e0cb  xor     r8d, r8d; nNumberOfArguments
0x18005e0ce  mov     edx, r12d; dwExceptionFlags
0x18005e0d1  mov     ecx, 80070216h; dwExceptionCode
0x18005e0d6  call    cs:__imp_RaiseException
0x18005e0dc  nop
0x18005e0dd  mov     r9d, 80070057h; char *
0x18005e0e3  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005e0ea  mov     edx, 0E4h; void *
0x18005e0ef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e0f5  mov     r9d, 8000FFFFh; char *
0x18005e0fb  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005e102  mov     edx, 0F4h; void *
0x18005e107  mov     rcx, rbx; this
0x18005e10a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e110  mov     r9d, eax; char *
0x18005e113  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005e11a  mov     edx, 0EBh; void *
0x18005e11f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e125  mov     r9d, eax; char *
0x18005e128  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005e12f  mov     edx, 0EFh; void *
0x18005e134  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e13a  mov     r9d, eax; char *
0x18005e13d  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005e144  mov     edx, 0F2h; void *
0x18005e149  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e14f  mov     ecx, ebx; unsigned int
0x18005e151  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005e156  lea     edx, [rax-1]
0x18005e159  cmp     ebx, eax
0x18005e15b  cmovb   edx, ebx; length
0x18005e15e  lea     r9, [rbp+60h+string]; string
0x18005e162  lea     r8, [rsp+160h+hstringHeader]; hstringHeader
0x18005e167  mov     rcx, rsi; sourceString
0x18005e16a  call    cs:__imp_WindowsCreateStringReference
0x18005e170  test    eax, eax
0x18005e172  js      loc_18005E344
0x18005e178  mov     r15, [rbp+60h+string]
0x18005e17c  lea     rdx, [rsp+160h+var_110]
0x18005e181  lea     rcx, [rbp+60h+var_B0]
0x18005e185  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18005e18a  nop
0x18005e18b  mov     r12, [rax+18h]
0x18005e18f  xor     eax, eax
0x18005e191  mov     [rbp+60h+var_B8], rax
0x18005e195  mov     rbx, [rsp+160h+StringSid]
0x18005e19a  inc     rdi
0x18005e19d  cmp     [rbx+rdi*2], ax
0x18005e1a1  jnz     short loc_18005E19A
0x18005e1a3  mov     eax, 0FFFFFFFFh
0x18005e1a8  cmp     rdi, rax
0x18005e1ab  jbe     short loc_18005E1C3
0x18005e1ad  xor     r9d, r9d; lpArguments
0x18005e1b0  xor     r8d, r8d; nNumberOfArguments
0x18005e1b3  lea     edx, [r9+1]; dwExceptionFlags
0x18005e1b7  mov     ecx, 80070216h; dwExceptionCode
0x18005e1bc  call    cs:__imp_RaiseException
0x18005e1c2  int     3; Trap to Debugger
0x18005e1c3  mov     ecx, edi; unsigned int
0x18005e1c5  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005e1ca  mov     r9d, edi; unsigned int
0x18005e1cd  mov     r8d, eax; unsigned int
0x18005e1d0  mov     rdx, rbx; sourceString
0x18005e1d3  lea     rcx, [rbp+60h+var_D0]; hstringHeader
0x18005e1d7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005e1dc  nop
0x18005e1dd  lea     rax, [rsp+160h+var_130]
0x18005e1e2  mov     qword ptr [rsp+160h+var_140], rax; int
0x18005e1e7  mov     r9, r15
0x18005e1ea  mov     r8, r12
0x18005e1ed  mov     rdx, [rbp+60h+var_B8]
0x18005e1f1  mov     rcx, r14
0x18005e1f4  mov     rax, [r13+30h]
0x18005e1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e1fd  mov     rcx, [rbp+68h]; this
0x18005e201  xor     edi, edi
0x18005e203  test    eax, eax
0x18005e205  js      loc_18005E2DB
0x18005e20b  mov     rcx, qword ptr [rsp+160h+var_130]
0x18005e210  mov     rax, [rcx]
0x18005e213  mov     dl, 1
0x18005e215  mov     rax, [rax+58h]
0x18005e219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e21e  mov     rcx, [rbp+68h]; this
0x18005e222  test    eax, eax
0x18005e224  js      loc_18005E2F0
0x18005e22a  mov     [rsp+160h+var_128], edi
0x18005e22e  mov     rcx, qword ptr [rsp+160h+var_130]
0x18005e233  mov     rax, [rcx]
0x18005e236  lea     rdx, [rsp+160h+var_128]
0x18005e23b  mov     rax, [rax+98h]
0x18005e242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e247  mov     rcx, [rbp+68h]; this
0x18005e24b  test    eax, eax
0x18005e24d  js      loc_18005E305
0x18005e253  cmp     [rsp+160h+var_128], 3
0x18005e258  setz    bl
0x18005e25b  mov     rcx, qword ptr [rsp+160h+var_130]
0x18005e260  test    rcx, rcx
0x18005e263  jz      short loc_18005E277
0x18005e265  mov     qword ptr [rsp+160h+var_130], rdi
0x18005e26a  mov     rax, [rcx]
0x18005e26d  mov     rax, [rax+10h]
0x18005e271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e276  nop
0x18005e277  mov     rcx, [rsp+160h+StringSid]; hMem
0x18005e27c  test    rcx, rcx
0x18005e27f  jz      short loc_18005E288
0x18005e281  call    cs:__imp_LocalFree
0x18005e287  nop
0x18005e288  mov     rcx, [rsp+160h+var_120]
0x18005e28d  test    rcx, rcx
0x18005e290  jz      short loc_18005E2A4
0x18005e292  mov     [rsp+160h+var_120], rdi
0x18005e297  mov     rax, [rcx]
0x18005e29a  mov     rax, [rax+10h]
0x18005e29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e2a3  nop
0x18005e2a4  test    rsi, rsi
0x18005e2a7  jz      short loc_18005E2B2
0x18005e2a9  mov     rcx, rsi; pv
0x18005e2ac  call    cs:__imp_CoTaskMemFree
0x18005e2b2  mov     al, bl
0x18005e2b4  mov     rcx, [rbp+60h+var_40]
0x18005e2b8  xor     rcx, rsp; StackCookie
0x18005e2bb  call    __security_check_cookie
0x18005e2c0  mov     rbx, [rsp+160h+arg_10]
0x18005e2c8  add     rsp, 130h
0x18005e2cf  pop     r15
0x18005e2d1  pop     r14
0x18005e2d3  pop     r13
0x18005e2d5  pop     r12
0x18005e2d7  pop     rdi
0x18005e2d8  pop     rsi
0x18005e2d9  pop     rbp
0x18005e2da  retn
0x18005e2db  mov     r9d, eax; char *
0x18005e2de  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005e2e5  mov     edx, 0F8h; void *
0x18005e2ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e2f0  mov     r9d, eax; char *
0x18005e2f3  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005e2fa  mov     edx, 0FBh; void *
0x18005e2ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e305  mov     r9d, eax; char *
0x18005e308  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005e30f  mov     edx, 0FDh; void *
0x18005e314  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e31a  mov     r9d, 80070057h; char *
0x18005e320  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005e327  mov     edx, 0E8h; void *
0x18005e32c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e332  xor     r9d, r9d; lpArguments
0x18005e335  xor     r8d, r8d; nNumberOfArguments
0x18005e338  mov     edx, r12d; dwExceptionFlags
0x18005e33b  mov     ecx, eax; dwExceptionCode
0x18005e33d  call    cs:__imp_RaiseException
0x18005e343  nop
0x18005e344  xor     r9d, r9d; lpArguments
0x18005e347  xor     r8d, r8d; nNumberOfArguments
0x18005e34a  mov     edx, r12d; dwExceptionFlags
0x18005e34d  mov     ecx, eax; dwExceptionCode
0x18005e34f  call    cs:__imp_RaiseException
```
