# GetDisplayLanguageNameHelper(ushort const *,Windows::Internal::DISPLAY_LANGUAGE_NAME_OPTIONS,DisplayNameFlags)

- ea: `0x180015030`
- end: `0x1800154d6`
- name: `?GetDisplayLanguageNameHelper@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGW4DISPLAY_LANGUAGE_NAME_OPTIONS@Internal@Windows@@W4DisplayNameFlags@@@Z`
- size: `1190`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fa30`
- `0x18001fad0`

## callees

- `0x180002380`
- `0x1800032dc`
- `0x18000c3cc`
- `0x18000f724`
- `0x180011448`
- `0x180011ac4`
- `0x180015030`
- `0x1800164c8`
- `0x180019554`
- `0x1800195b0`
- `0x18001b4e4`
- `0x18001d564`
- `0x18001de84`
- `0x18001e868`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015083`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015083`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800150c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800150c2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015106`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800151bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001523d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015106`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800151bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001523d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015174`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015174`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001511b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800151d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001511b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800151d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800150cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015188`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001520d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800150cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015188`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001520d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001528f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800152ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001528f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800152ed`
- `Bcp47Langs!Bcp47GetNeutralForm` at `0x1800151e0`
- `Bcp47Langs!Bcp47GetNeutralForm` at `0x1800151e0`
- `Bcp47Langs!Bcp47GetMuiForm` at `0x18001512b`
- `Bcp47Langs!Bcp47GetMuiForm` at `0x18001512b`
- `Bcp47Langs!Bcp47GetUnIsoRegionCode` at `0x180015262`
- `Bcp47Langs!Bcp47GetUnIsoRegionCode` at `0x180015262`
- `icu!uldn_openForContext` at `0x1800153b5`
- `icu!uldn_openForContext` at `0x1800153b5`
- `icu!uldn_localeDisplayName` at `0x180015429`
- `icu!uldn_localeDisplayName` at `0x180015429`

## string_xrefs

- `0x1800150ad`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18001513f`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x1800151f4`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180015276`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18001532d`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180015371`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x1800153ee`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180015455`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetDisplayLanguageNameHelper(__int64 a1, const WCHAR *a2, int a3, int a4)
{
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // rbx
  int MuiForm; // eax
  const WCHAR *StringRawBuffer; // rbx
  unsigned __int64 v12; // rbx
  int NeutralForm; // eax
  int UnIsoRegionCode; // eax
  PCWSTR v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  PCWSTR v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned __int64 i; // rdx
  __int64 v22; // rax
  __int64 v23; // rdx
  _BYTE *v24; // rcx
  __int64 v25; // rbx
  __int64 v26; // rdx
  signed int v27; // eax
  char v28; // dl
  __int64 v29; // rdx
  signed int v30; // eax
  char v31; // dl
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v36; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v37; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v38; // [rsp+48h] [rbp-B8h] BYREF
  RTL_SRWLOCK *v39; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v42[16]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v43; // [rsp+90h] [rbp-70h]
  _DWORD v44[4]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v45[96]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v46[512]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v39 = &stru_180032FB8;
  AcquireSRWLockShared(&stru_180032FB8);
  if ( a3 == 1 && qword_180032FA0 == qword_180032FA8 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
  ReleaseSRWLockShared(&stru_180032FB8);
  WindowsDeleteString(0);
  v38 = 0;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  if ( v9 > 0xFFFFFFFF )
  {
    LODWORD(v9) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a2, v9, &hstringHeader, &string);
  MuiForm = Bcp47GetMuiForm(string, &v38);
  if ( MuiForm < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C3,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(unsigned int)MuiForm,
      bIgnoreCase);
  StringRawBuffer = WindowsGetStringRawBuffer(v38, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, a2, -1, 1) != 2 )
    a2 = StringRawBuffer;
  WindowsDeleteString(0);
  v37 = 0;
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  if ( v12 > 0xFFFFFFFF )
  {
    LODWORD(v12) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a2, v12, &hstringHeader, &string);
  NeutralForm = Bcp47GetNeutralForm(string, &v37);
  if ( NeutralForm < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D4,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(unsigned int)NeutralForm,
      bIgnoreCasea);
  WindowsDeleteString(0);
  v36 = 0;
  do
    ++v8;
  while ( a2[v8] );
  if ( v8 > 0xFFFFFFFF )
  {
    LODWORD(v8) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a2, v8, &hstringHeader, &string);
  UnIsoRegionCode = Bcp47GetUnIsoRegionCode(string, &v36);
  if ( UnIsoRegionCode < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D8,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(unsigned int)UnIsoRegionCode,
      bIgnoreCasea);
  v15 = WindowsGetStringRawBuffer(v37, 0);
  std::wstring::wstring((__int64)v42, (__int64)v15);
  if ( a3 == 2
    || !a3 && ShouldIncludeRegionNameBasedOnUILanguageInfo(a2)
    || a3 == 1 && ShouldIncludeRegionNameIfAmbiguous(a2) )
  {
    v16 = std::_WChar_traits<unsigned short>::length(L"-");
    std::wstring::_Append<unsigned short>(v42, v17, v16);
    v18 = WindowsGetStringRawBuffer(v36, 0);
    v19 = std::_WChar_traits<unsigned short>::length(v18);
    std::wstring::_Append<unsigned short>(v42, v20, v19);
  }
  memset_0(v45, 0, 0x55u);
  if ( v43 >= 0x55 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)0x80070057LL,
      bIgnoreCasea);
  for ( i = 0; i < v43; i = v23 + 1 )
  {
    v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    if ( *(_WORD *)(v22 + 2 * v23) > 0x7Fu )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F3,
        (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
        (const char *)0x80070057LL,
        bIgnoreCasea);
    v45[v23] = *(_BYTE *)(v22 + 2 * v23);
  }
  v44[0] = 0;
  v44[1] = 259;
  v44[2] = 512;
  v35 = 0;
  v24 = v45;
  if ( a4 )
    v24 = 0;
  v25 = uldn_openForContext(v24, v44, 3, &v35);
  v39 = (RTL_SRWLOCK *)v25;
  LOBYTE(v26) = v35 > 0;
  v27 = MapIcuErrorToWin32Error((unsigned int)v35, v26);
  if ( v27 > 0 )
    v27 = (unsigned __int16)v27 | 0x80070000;
  if ( v28 == 1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(unsigned int)v27,
      bIgnoreCasea);
  memset_0(v46, 0, sizeof(v46));
  uldn_localeDisplayName(v25, v45, v46, 256);
  LOBYTE(v29) = v35 > 0;
  v30 = MapIcuErrorToWin32Error((unsigned int)v35, v29);
  if ( v30 > 0 )
    v30 = (unsigned __int16)v30 | 0x80070000;
  if ( v31 == 1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x213,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(unsigned int)v30,
      (int)&v35);
  std::wstring::wstring(a1, (__int64)v46);
  wil::details::unique_storage<wil::details::resource_policy<ULocaleDisplayNames *,void (*)(ULocaleDisplayNames *),&void uldn_close(ULocaleDisplayNames *),wistd::integral_constant<unsigned __int64,0>,ULocaleDisplayNames *,ULocaleDisplayNames *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ULocaleDisplayNames *,void (*)(ULocaleDisplayNames *),&void uldn_close(ULocaleDisplayNames *),wistd::integral_constant<unsigned __int64,0>,ULocaleDisplayNames *,ULocaleDisplayNames *,0,std::nullptr_t>>(&v39);
  std::wstring::_Tidy_deallocate(v42);
  Windows::Internal::String::~String(&v36);
  Windows::Internal::String::~String(&v37);
  Windows::Internal::String::~String(&v38);
  return a1;
}

```

## disassembly

```asm
0x180015030  mov     [rsp-8+arg_10], rbx
0x180015035  push    rbp
0x180015036  push    rsi
0x180015037  push    rdi
0x180015038  push    r12
0x18001503a  push    r13
0x18001503c  push    r14
0x18001503e  push    r15
0x180015040  lea     rbp, [rsp-220h]
0x180015048  sub     rsp, 320h
0x18001504f  mov     rax, cs:__security_cookie
0x180015056  xor     rax, rsp
0x180015059  mov     [rbp+250h+var_40], rax
0x180015060  mov     r12d, r9d
0x180015063  mov     r14d, r8d
0x180015066  mov     rdi, rdx
0x180015069  mov     r15, rcx
0x18001506c  mov     [rsp+350h+var_300], rcx
0x180015071  xor     r13d, r13d
0x180015074  lea     rbx, stru_180032FB8
0x18001507b  mov     [rsp+350h+var_300], rbx
0x180015080  mov     rcx, rbx; SRWLock
0x180015083  call    cs:__imp_AcquireSRWLockShared
0x180015089  nop
0x18001508a  cmp     r14d, 1
0x18001508e  jnz     short loc_1800150BF
0x180015090  mov     rax, cs:qword_180032FA8
0x180015097  cmp     cs:qword_180032FA0, rax
0x18001509e  jnz     short loc_1800150BF
0x1800150a0  mov     rcx, [rbp+258h]; this
0x1800150a7  mov     r9d, 80070057h; char *
0x1800150ad  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x1800150b4  mov     edx, 1BCh; void *
0x1800150b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800150bf  mov     rcx, rbx; SRWLock
0x1800150c2  call    cs:__imp_ReleaseSRWLockShared
0x1800150c8  mov     [rsp+350h+var_308], r13
0x1800150cd  xor     ecx, ecx; string
0x1800150cf  call    cs:__imp_WindowsDeleteString
0x1800150d5  mov     [rsp+350h+var_308], r13
0x1800150da  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800150de  mov     rbx, rsi
0x1800150e1  inc     rbx
0x1800150e4  cmp     [rdi+rbx*2], r13w
0x1800150e9  jnz     short loc_1800150E1
0x1800150eb  mov     eax, 0FFFFFFFFh
0x1800150f0  cmp     rbx, rax
0x1800150f3  jbe     short loc_18001510C
0x1800150f5  mov     ebx, eax
0x1800150f7  xor     r9d, r9d; lpArguments
0x1800150fa  xor     r8d, r8d; nNumberOfArguments
0x1800150fd  lea     edx, [r9+1]; dwExceptionFlags
0x180015101  mov     ecx, 0C000000Dh; dwExceptionCode
0x180015106  call    cs:__imp_RaiseException
0x18001510c  lea     r9, [rsp+350h+string]; string
0x180015111  lea     r8, [rsp+350h+hstringHeader]; hstringHeader
0x180015116  mov     edx, ebx; length
0x180015118  mov     rcx, rdi; sourceString
0x18001511b  call    cs:__imp_WindowsCreateStringReference
0x180015121  lea     rdx, [rsp+350h+var_308]
0x180015126  mov     rcx, [rsp+350h+string]
0x18001512b  call    cs:__imp_Bcp47GetMuiForm
0x180015131  mov     rcx, [rbp+258h]; this
0x180015138  test    eax, eax
0x18001513a  jns     short loc_180015151
0x18001513c  mov     r9d, eax; char *
0x18001513f  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180015146  mov     edx, 1C3h; void *
0x18001514b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015151  xor     edx, edx; length
0x180015153  mov     rcx, [rsp+350h+var_308]; string
0x180015158  call    cs:__imp_WindowsGetStringRawBuffer
0x18001515e  mov     rbx, rax
0x180015161  mov     [rsp+350h+bIgnoreCase], 1; int
0x180015169  mov     r9d, esi; cchCount2
0x18001516c  mov     r8, rdi; lpString2
0x18001516f  mov     edx, esi; cchCount1
0x180015171  mov     rcx, rax; lpString1
0x180015174  call    cs:__imp_CompareStringOrdinal
0x18001517a  cmp     eax, 2
0x18001517d  cmovnz  rdi, rbx
0x180015181  mov     [rsp+350h+var_310], r13
0x180015186  xor     ecx, ecx; string
0x180015188  call    cs:__imp_WindowsDeleteString
0x18001518e  mov     [rsp+350h+var_310], r13
0x180015193  mov     rbx, rsi
0x180015196  inc     rbx
0x180015199  cmp     [rdi+rbx*2], r13w
0x18001519e  jnz     short loc_180015196
0x1800151a0  mov     eax, 0FFFFFFFFh
0x1800151a5  cmp     rbx, rax
0x1800151a8  jbe     short loc_1800151C1
0x1800151aa  mov     ebx, eax
0x1800151ac  xor     r9d, r9d; lpArguments
0x1800151af  xor     r8d, r8d; nNumberOfArguments
0x1800151b2  lea     edx, [r9+1]; dwExceptionFlags
0x1800151b6  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800151bb  call    cs:__imp_RaiseException
0x1800151c1  lea     r9, [rsp+350h+string]; string
0x1800151c6  lea     r8, [rsp+350h+hstringHeader]; hstringHeader
0x1800151cb  mov     edx, ebx; length
0x1800151cd  mov     rcx, rdi; sourceString
0x1800151d0  call    cs:__imp_WindowsCreateStringReference
0x1800151d6  lea     rdx, [rsp+350h+var_310]
0x1800151db  mov     rcx, [rsp+350h+string]
0x1800151e0  call    cs:__imp_Bcp47GetNeutralForm
0x1800151e6  mov     rcx, [rbp+258h]; this
0x1800151ed  test    eax, eax
0x1800151ef  jns     short loc_180015206
0x1800151f1  mov     r9d, eax; char *
0x1800151f4  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x1800151fb  mov     edx, 1D4h; void *
0x180015200  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015206  mov     [rsp+350h+var_318], r13
0x18001520b  xor     ecx, ecx; string
0x18001520d  call    cs:__imp_WindowsDeleteString
0x180015213  mov     [rsp+350h+var_318], r13
0x180015218  inc     rsi
0x18001521b  cmp     [rdi+rsi*2], r13w
0x180015220  jnz     short loc_180015218
0x180015222  mov     eax, 0FFFFFFFFh
0x180015227  cmp     rsi, rax
0x18001522a  jbe     short loc_180015243
0x18001522c  mov     esi, eax
0x18001522e  xor     r9d, r9d; lpArguments
0x180015231  xor     r8d, r8d; nNumberOfArguments
0x180015234  lea     edx, [r9+1]; dwExceptionFlags
0x180015238  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001523d  call    cs:__imp_RaiseException
0x180015243  lea     r9, [rsp+350h+string]; string
0x180015248  lea     r8, [rsp+350h+hstringHeader]; hstringHeader
0x18001524d  mov     edx, esi; length
0x18001524f  mov     rcx, rdi; sourceString
0x180015252  call    cs:__imp_WindowsCreateStringReference
0x180015258  lea     rdx, [rsp+350h+var_318]
0x18001525d  mov     rcx, [rsp+350h+string]
0x180015262  call    cs:__imp_Bcp47GetUnIsoRegionCode
0x180015268  mov     rcx, [rbp+258h]; this
0x18001526f  test    eax, eax
0x180015271  jns     short loc_180015288
0x180015273  mov     r9d, eax; char *
0x180015276  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001527d  mov     edx, 1D8h; void *
0x180015282  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015288  xor     edx, edx; length
0x18001528a  mov     rcx, [rsp+350h+var_310]; string
0x18001528f  call    cs:__imp_WindowsGetStringRawBuffer
0x180015295  mov     rdx, rax
0x180015298  lea     rcx, [rbp+250h+var_2D0]
0x18001529c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800152a1  nop
0x1800152a2  cmp     r14d, 2
0x1800152a6  jz      short loc_1800152CB
0x1800152a8  test    r14d, r14d
0x1800152ab  jnz     short loc_1800152B9
0x1800152ad  mov     rcx, rdi; unsigned __int16 *
0x1800152b0  call    ?ShouldIncludeRegionNameBasedOnUILanguageInfo@@YA_NPEBG@Z; ShouldIncludeRegionNameBasedOnUILanguageInfo(ushort const *)
0x1800152b5  test    al, al
0x1800152b7  jnz     short loc_1800152CB
0x1800152b9  cmp     r14d, 1
0x1800152bd  jnz     short loc_18001530A
0x1800152bf  mov     rcx, rdi; sourceString
0x1800152c2  call    ?ShouldIncludeRegionNameIfAmbiguous@@YA_NPEBG@Z; ShouldIncludeRegionNameIfAmbiguous(ushort const *)
0x1800152c7  test    al, al
0x1800152c9  jz      short loc_18001530A
0x1800152cb  lea     rcx, asc_180028714; "-"
0x1800152d2  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800152d7  mov     r8, rax
0x1800152da  mov     rdx, rcx
0x1800152dd  lea     rcx, [rbp+250h+var_2D0]
0x1800152e1  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800152e6  xor     edx, edx; length
0x1800152e8  mov     rcx, [rsp+350h+var_318]; string
0x1800152ed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800152f3  mov     rcx, rax
0x1800152f6  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800152fb  mov     r8, rax
0x1800152fe  mov     rdx, rcx
0x180015301  lea     rcx, [rbp+250h+var_2D0]
0x180015305  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001530a  xor     edx, edx; Val
0x18001530c  lea     r8d, [rdx+55h]; Size
0x180015310  lea     rcx, [rbp+250h+var_2A0]; void *
0x180015314  call    memset_0
0x180015319  cmp     [rbp+250h+var_2C0], 55h ; 'U'
0x18001531e  jb      short loc_18001533F
0x180015320  mov     rcx, [rbp+258h]; this
0x180015327  mov     r9d, 80070057h; char *
0x18001532d  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180015334  mov     edx, 1EAh; void *
0x180015339  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001533f  mov     rdx, r13
0x180015342  cmp     rdx, [rbp+250h+var_2C0]
0x180015346  jnb     short loc_180015383
0x180015348  lea     rcx, [rbp+250h+var_2D0]
0x18001534c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015351  cmp     word ptr [rax+rdx*2], 7Fh
0x180015356  ja      short loc_180015364
0x180015358  mov     al, [rax+rdx*2]
0x18001535b  mov     [rbp+rdx+250h+var_2A0], al
0x18001535f  inc     rdx
0x180015362  jmp     short loc_180015342
0x180015364  mov     rcx, [rbp+258h]; this
0x18001536b  mov     r9d, 80070057h; char *
0x180015371  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180015378  mov     edx, 1F3h; void *
0x18001537d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015383  mov     [rbp+250h+var_2B0], r13d
0x180015387  mov     [rbp+250h+var_2AC], 103h
0x18001538e  mov     esi, 200h
0x180015393  mov     [rbp+250h+var_2A8], esi
0x180015396  mov     [rsp+350h+var_320], r13d
0x18001539b  lea     rcx, [rbp+250h+var_2A0]
0x18001539f  test    r12d, r12d
0x1800153a2  cmovnz  rcx, r13
0x1800153a6  lea     r9, [rsp+350h+var_320]
0x1800153ab  mov     r8d, 3
0x1800153b1  lea     rdx, [rbp+250h+var_2B0]
0x1800153b5  call    cs:__imp_uldn_openForContext
0x1800153bb  mov     rbx, rax
0x1800153be  mov     [rsp+350h+var_300], rax
0x1800153c3  mov     ecx, [rsp+350h+var_320]
0x1800153c7  test    ecx, ecx
0x1800153c9  setnle  dl
0x1800153cc  call    ?MapIcuErrorToWin32Error@@YAKW4UErrorCode@@K@Z; MapIcuErrorToWin32Error(UErrorCode,ulong)
0x1800153d1  mov     edi, 80070000h
0x1800153d6  test    eax, eax
0x1800153d8  jle     short loc_1800153DF
0x1800153da  movzx   eax, ax
0x1800153dd  or      eax, edi
0x1800153df  mov     rcx, [rbp+258h]; this
0x1800153e6  cmp     dl, 1
0x1800153e9  jnz     short loc_180015400
0x1800153eb  mov     r9d, eax; char *
0x1800153ee  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x1800153f5  mov     edx, 20Ch; void *
0x1800153fa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015400  mov     r8, rsi; Size
0x180015403  xor     edx, edx; Val
0x180015405  lea     rcx, [rbp+250h+var_240]; void *
0x180015409  call    memset_0
0x18001540e  lea     rax, [rsp+350h+var_320]
0x180015413  mov     qword ptr [rsp+350h+bIgnoreCase], rax; int
0x180015418  mov     r9d, 100h
0x18001541e  lea     r8, [rbp+250h+var_240]
0x180015422  lea     rdx, [rbp+250h+var_2A0]
0x180015426  mov     rcx, rbx
0x180015429  call    cs:__imp_uldn_localeDisplayName
0x18001542f  mov     ecx, [rsp+350h+var_320]
0x180015433  test    ecx, ecx
0x180015435  setnle  dl
0x180015438  call    ?MapIcuErrorToWin32Error@@YAKW4UErrorCode@@K@Z; MapIcuErrorToWin32Error(UErrorCode,ulong)
0x18001543d  test    eax, eax
0x18001543f  jle     short loc_180015446
0x180015441  movzx   eax, ax
0x180015444  or      eax, edi
0x180015446  mov     rcx, [rbp+258h]; this
0x18001544d  cmp     dl, 1
0x180015450  jnz     short loc_180015467
0x180015452  mov     r9d, eax; char *
0x180015455  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001545c  mov     edx, 213h; void *
0x180015461  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015467  lea     rdx, [rbp+250h+var_240]
0x18001546b  mov     rcx, r15
0x18001546e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015473  nop
0x180015474  lea     rcx, [rsp+350h+var_300]
0x180015479  call    ??1?$unique_storage@U?$resource_policy@PEAUULocaleDisplayNames@@P6AXPEAU1@@Z$1?uldn_close@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ULocaleDisplayNames *,void (*)(ULocaleDisplayNames *),&uldn_close(ULocaleDisplayNames *),wistd::integral_constant<unsigned __int64,0>,ULocaleDisplayNames *,ULocaleDisplayNames *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ULocaleDisplayNames *,void (*)(ULocaleDisplayNames *),&uldn_close(ULocaleDisplayNames *),wistd::integral_constant<unsigned __int64,0>,ULocaleDisplayNames *,ULocaleDisplayNames *,0,std::nullptr_t>>(void)
0x18001547e  nop
0x18001547f  lea     rcx, [rbp+250h+var_2D0]
0x180015483  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015488  nop
0x180015489  lea     rcx, [rsp+350h+var_318]; this
0x18001548e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180015493  nop
0x180015494  lea     rcx, [rsp+350h+var_310]; this
0x180015499  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001549e  nop
0x18001549f  lea     rcx, [rsp+350h+var_308]; this
0x1800154a4  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800154a9  mov     rax, r15
0x1800154ac  mov     rcx, [rbp+250h+var_40]
0x1800154b3  xor     rcx, rsp; StackCookie
0x1800154b6  call    __security_check_cookie
0x1800154bb  mov     rbx, [rsp+350h+arg_10]
0x1800154c3  add     rsp, 320h
0x1800154ca  pop     r15
0x1800154cc  pop     r14
0x1800154ce  pop     r13
0x1800154d0  pop     r12
0x1800154d2  pop     rdi
0x1800154d3  pop     rsi
0x1800154d4  pop     rbp
0x1800154d5  retn
```
