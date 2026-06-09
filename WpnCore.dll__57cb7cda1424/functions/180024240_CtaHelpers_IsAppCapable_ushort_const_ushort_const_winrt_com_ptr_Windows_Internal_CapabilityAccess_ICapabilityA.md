# CtaHelpers::IsAppCapable(ushort const *,ushort const *,winrt::com_ptr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics> const &)

- ea: `0x180024240`
- end: `0x18002460d`
- name: `?IsAppCapable@CtaHelpers@@YA_NPEBG0AEBU?$com_ptr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@winrt@@@Z`
- size: `973`
- prototype: `__int64 __fastcall(PCWSTR sourceString, wchar_t *Str)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180023f84`
- `0x1800d6c10`

## callees

- `0x18000de40`
- `0x18000e5f4`
- `0x180021d30`
- `0x180024240`
- `0x180024614`
- `0x180024640`
- `0x180024844`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002427a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800243c8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002427a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800243c8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800242a2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800242a2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002435a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024431`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024493`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800245f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024606`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002435a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024431`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024493`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800245f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024606`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024561`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024561`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800243f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800243f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024457`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024552`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024552`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002430d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002430d`

## string_xrefs

- `0x180024367`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x18002437f`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x180024397`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x1800243ac`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x180024593`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x1800245a8`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x1800245bd`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x1800245d5`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
bool __fastcall CtaHelpers::IsAppCapable(PCWSTR sourceString, wchar_t *Str, __int64 **a3)
{
  char v6; // al
  wil::details::in1diag3 *v7; // rcx
  wchar_t *v8; // rax
  int v9; // eax
  unsigned int v10; // edx
  int UserSid; // eax
  __int64 *v12; // r15
  __int64 v13; // r13
  WCHAR *v14; // rsi
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rbx
  bool v17; // zf
  unsigned int v18; // eax
  UINT32 v19; // edx
  HRESULT v20; // eax
  unsigned __int64 v21; // rbx
  HSTRING v22; // r12
  unsigned int v23; // eax
  UINT32 v24; // edx
  HRESULT v25; // eax
  const WCHAR *v26; // r14
  HSTRING v27; // rbx
  unsigned int v28; // eax
  int v29; // eax
  __int64 v30; // rdx
  int v31; // eax
  int v32; // eax
  bool v33; // bl
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+30h] [rbp-D0h] BYREF
  int v37[2]; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR sourceStringa[3]; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+78h] [rbp-88h] BYREF
  HSTRING_HEADER v42; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v43; // [rsp+98h] [rbp-68h] BYREF
  HSTRING_HEADER v44; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-48h]
  _BYTE Sid[80]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  if ( !(unsigned int)_o__wcsicmp(sourceString, L"cellularData")
    || (v17 = (unsigned int)_o__wcsicmp(sourceString, L"wifiData") == 0, v6 = 1, v17) )
  {
    v6 = 0;
  }
  v7 = retaddr;
  if ( v6 )
LABEL_12:
    wil::details::in1diag3::Throw_Hr(
      v7,
      (void *)0xBE,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)0x80070057LL,
      v35);
  v8 = wcschr(Str, 0x21u);
  if ( !v8 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)0x80070057LL,
      v35);
  memset(sourceStringa, 0, sizeof(sourceStringa));
  v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         sourceStringa,
         Str,
         v8 - Str);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)v9,
      v35);
  UserSid = WpnGetUserSid(Sid, v10);
  if ( UserSid < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)UserSid,
      v35);
  StringSid = 0;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)0x8000FFFFLL,
      v35);
  *(_QWORD *)v37 = 0;
  v12 = *a3;
  v13 = **a3;
  string = 0;
  v14 = (WCHAR *)sourceStringa[0];
  v15 = -1;
  v16 = -1;
  do
    ++v16;
  while ( sourceStringa[0][v16] );
  if ( v16 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_12;
  }
  v18 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v16);
  v19 = v18 - 1;
  if ( (unsigned int)v16 < v18 )
    v19 = v16;
  v20 = WindowsCreateStringReference(v14, v19, &hstringHeader, &string);
  if ( v20 < 0 )
  {
    RaiseException(v20, 1u, 0, 0);
    goto LABEL_47;
  }
  v43 = 0;
  v21 = -1;
  do
    ++v21;
  while ( sourceString[v21] );
  if ( v21 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v22 = string;
  v23 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v21);
  v24 = v23 - 1;
  if ( (unsigned int)v21 < v23 )
    v24 = v21;
  v25 = WindowsCreateStringReference(sourceString, v24, &v42, &v43);
  if ( v25 < 0 )
  {
LABEL_47:
    RaiseException(v25, 1u, 0, 0);
    JUMPOUT(0x18002460CLL);
  }
  v45 = 0;
  v26 = StringSid;
  do
    ++v15;
  while ( StringSid[v15] );
  if ( v15 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v27 = v43;
  v28 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v15);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v44, v26, v28, v15);
  v29 = (*(__int64 (__fastcall **)(__int64 *, __int64, HSTRING, HSTRING))(v13 + 48))(v12, v45, v27, v22);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)v29,
      (int)v37);
  LOBYTE(v30) = 1;
  v31 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v37 + 88LL))(*(_QWORD *)v37, v30);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)v31,
      (int)v37);
  v36 = 0;
  v32 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v37 + 152LL))(*(_QWORD *)v37, &v36);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)v32,
      (int)v37);
  v33 = v36 == 3;
  if ( *(_QWORD *)v37 )
    winrt::com_ptr<ThreadPool>::unconditional_release_ref(v37);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v14 )
    CoTaskMemFree(v14);
  return v33;
}

```

## disassembly

```asm
0x180024240  mov     [rsp-8+arg_18], rbx
0x180024245  push    rbp
0x180024246  push    rsi
0x180024247  push    rdi
0x180024248  push    r12
0x18002424a  push    r13
0x18002424c  push    r14
0x18002424e  push    r15
0x180024250  lea     rbp, [rsp-20h]
0x180024255  sub     rsp, 120h
0x18002425c  mov     rax, cs:__security_cookie
0x180024263  xor     rax, rsp
0x180024266  mov     [rbp+50h+var_40], rax
0x18002426a  mov     rdi, r8
0x18002426d  mov     rbx, rdx
0x180024270  mov     r14, rcx
0x180024273  lea     rdx, aCellulardata; "cellularData"
0x18002427a  call    cs:__imp__o__wcsicmp
0x180024280  xor     r12d, r12d
0x180024283  test    eax, eax
0x180024285  jnz     loc_1800243BE
0x18002428b  mov     al, r12b
0x18002428e  mov     rcx, [rbp+58h]
0x180024292  test    al, al
0x180024294  jnz     loc_180024361
0x18002429a  mov     edx, 21h ; '!'; Ch
0x18002429f  mov     rcx, rbx; Str
0x1800242a2  call    cs:__imp_wcschr
0x1800242a8  mov     rcx, [rbp+58h]; this
0x1800242ac  test    rax, rax
0x1800242af  jz      loc_1800245CF
0x1800242b5  mov     [rsp+150h+sourceString], r12
0x1800242ba  mov     [rsp+150h+var_100], r12
0x1800242bf  mov     [rsp+150h+var_F8], r12
0x1800242c4  sub     rax, rbx
0x1800242c7  sar     rax, 1
0x1800242ca  mov     r8, rax
0x1800242cd  mov     rdx, rbx
0x1800242d0  lea     rcx, [rsp+150h+sourceString]
0x1800242d5  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800242da  mov     rcx, [rbp+58h]; this
0x1800242de  test    eax, eax
0x1800242e0  js      loc_180024394
0x1800242e6  lea     rcx, [rbp+50h+Sid]; void *
0x1800242ea  call    ?WpnGetUserSid@@YAJPEAXK@Z; WpnGetUserSid(void *,ulong)
0x1800242ef  mov     rcx, [rbp+58h]; this
0x1800242f3  test    eax, eax
0x1800242f5  js      loc_1800243A9
0x1800242fb  mov     [rsp+150h+StringSid], r12
0x180024300  mov     rbx, [rbp+58h]
0x180024304  lea     rdx, [rsp+150h+StringSid]; StringSid
0x180024309  lea     rcx, [rbp+50h+Sid]; Sid
0x18002430d  call    cs:__imp_ConvertSidToStringSidW
0x180024313  test    eax, eax
0x180024315  jz      short loc_180024379
0x180024317  mov     qword ptr [rsp+150h+var_118], r12
0x18002431c  mov     r15, [rdi]
0x18002431f  mov     r13, [r15]
0x180024322  mov     [rsp+150h+string], r12
0x180024327  mov     rsi, [rsp+150h+sourceString]
0x18002432c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180024330  mov     rbx, rdi
0x180024333  inc     rbx
0x180024336  cmp     [rsi+rbx*2], r12w
0x18002433b  jnz     short loc_180024333
0x18002433d  mov     eax, 0FFFFFFFFh
0x180024342  cmp     rbx, rax
0x180024345  jbe     loc_1800243DD
0x18002434b  xor     r9d, r9d; lpArguments
0x18002434e  xor     r8d, r8d; nNumberOfArguments
0x180024351  lea     edx, [r9+1]; dwExceptionFlags
0x180024355  mov     ecx, 80070216h; dwExceptionCode
0x18002435a  call    cs:__imp_RaiseException
0x180024360  nop
0x180024361  mov     r9d, 80070057h; char *
0x180024367  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002436e  mov     edx, 0BEh; void *
0x180024373  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024379  mov     r9d, 8000FFFFh; char *
0x18002437f  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180024386  mov     edx, 0CAh; void *
0x18002438b  mov     rcx, rbx; this
0x18002438e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024394  mov     r9d, eax; char *
0x180024397  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002439e  mov     edx, 0C5h; void *
0x1800243a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800243a9  mov     r9d, eax; char *
0x1800243ac  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800243b3  mov     edx, 0C8h; void *
0x1800243b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800243be  lea     rdx, aWifidata; "wifiData"
0x1800243c5  mov     rcx, r14
0x1800243c8  call    cs:__imp__o__wcsicmp
0x1800243ce  test    eax, eax
0x1800243d0  mov     al, 1
0x1800243d2  jz      loc_18002428B
0x1800243d8  jmp     loc_18002428E
0x1800243dd  mov     ecx, ebx; unsigned int
0x1800243df  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800243e4  lea     edx, [rax-1]
0x1800243e7  cmp     ebx, eax
0x1800243e9  cmovb   edx, ebx; length
0x1800243ec  lea     r9, [rsp+150h+string]; string
0x1800243f1  lea     r8, [rsp+150h+hstringHeader]; hstringHeader
0x1800243f6  mov     rcx, rsi; sourceString
0x1800243f9  call    cs:__imp_WindowsCreateStringReference
0x1800243ff  test    eax, eax
0x180024401  js      loc_1800245E7
0x180024407  mov     [rbp+50h+var_B8], r12
0x18002440b  mov     rbx, rdi
0x18002440e  inc     rbx
0x180024411  cmp     [r14+rbx*2], r12w
0x180024416  jnz     short loc_18002440E
0x180024418  mov     eax, 0FFFFFFFFh
0x18002441d  cmp     rbx, rax
0x180024420  jbe     short loc_180024438
0x180024422  xor     r9d, r9d; lpArguments
0x180024425  xor     r8d, r8d; nNumberOfArguments
0x180024428  lea     edx, [r9+1]; dwExceptionFlags
0x18002442c  mov     ecx, 80070216h; dwExceptionCode
0x180024431  call    cs:__imp_RaiseException
0x180024437  int     3; Trap to Debugger
0x180024438  mov     r12, [rsp+150h+string]
0x18002443d  mov     ecx, ebx; unsigned int
0x18002443f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180024444  lea     edx, [rax-1]
0x180024447  cmp     ebx, eax
0x180024449  cmovb   edx, ebx; length
0x18002444c  lea     r9, [rbp+50h+var_B8]; string
0x180024450  lea     r8, [rbp+50h+var_D0]; hstringHeader
0x180024454  mov     rcx, r14; sourceString
0x180024457  call    cs:__imp_WindowsCreateStringReference
0x18002445d  xor     ecx, ecx
0x18002445f  test    eax, eax
0x180024461  js      loc_1800245FA
0x180024467  mov     [rbp+50h+var_98], rcx
0x18002446b  mov     r14, [rsp+150h+StringSid]
0x180024470  inc     rdi
0x180024473  cmp     [r14+rdi*2], cx
0x180024478  jnz     short loc_180024470
0x18002447a  mov     eax, 0FFFFFFFFh
0x18002447f  cmp     rdi, rax
0x180024482  jbe     short loc_18002449A
0x180024484  xor     r9d, r9d; lpArguments
0x180024487  xor     r8d, r8d; nNumberOfArguments
0x18002448a  lea     edx, [r9+1]; dwExceptionFlags
0x18002448e  mov     ecx, 80070216h; dwExceptionCode
0x180024493  call    cs:__imp_RaiseException
0x180024499  int     3; Trap to Debugger
0x18002449a  mov     rbx, [rbp+50h+var_B8]
0x18002449e  mov     ecx, edi; unsigned int
0x1800244a0  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800244a5  mov     r9d, edi; unsigned int
0x1800244a8  mov     r8d, eax; unsigned int
0x1800244ab  mov     rdx, r14; sourceString
0x1800244ae  lea     rcx, [rbp+50h+var_B0]; hstringHeader
0x1800244b2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800244b7  nop
0x1800244b8  lea     rax, [rsp+150h+var_118]
0x1800244bd  mov     qword ptr [rsp+150h+var_130], rax; int
0x1800244c2  mov     r9, r12
0x1800244c5  mov     r8, rbx
0x1800244c8  mov     rdx, [rbp+50h+var_98]
0x1800244cc  mov     rcx, r15
0x1800244cf  mov     rax, [r13+30h]
0x1800244d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244d8  mov     rcx, [rbp+58h]; this
0x1800244dc  xor     edi, edi
0x1800244de  test    eax, eax
0x1800244e0  js      loc_180024590
0x1800244e6  mov     rcx, qword ptr [rsp+150h+var_118]
0x1800244eb  mov     rax, [rcx]
0x1800244ee  mov     dl, 1
0x1800244f0  mov     rax, [rax+58h]
0x1800244f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244f9  mov     rcx, [rbp+58h]; this
0x1800244fd  test    eax, eax
0x1800244ff  js      loc_1800245A5
0x180024505  mov     [rsp+150h+var_120], edi
0x180024509  mov     rcx, qword ptr [rsp+150h+var_118]
0x18002450e  mov     rax, [rcx]
0x180024511  lea     rdx, [rsp+150h+var_120]
0x180024516  mov     rax, [rax+98h]
0x18002451d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024522  mov     rcx, [rbp+58h]; this
0x180024526  test    eax, eax
0x180024528  js      loc_1800245BA
0x18002452e  cmp     [rsp+150h+var_120], 3
0x180024533  setz    bl
0x180024536  cmp     qword ptr [rsp+150h+var_118], rdi
0x18002453b  jz      short loc_180024548
0x18002453d  lea     rcx, [rsp+150h+var_118]
0x180024542  call    ?unconditional_release_ref@?$com_ptr@VThreadPool@@@winrt@@AEAAXXZ; winrt::com_ptr<ThreadPool>::unconditional_release_ref(void)
0x180024547  nop
0x180024548  mov     rcx, [rsp+150h+StringSid]; hMem
0x18002454d  test    rcx, rcx
0x180024550  jz      short loc_180024559
0x180024552  call    cs:__imp_LocalFree
0x180024558  nop
0x180024559  test    rsi, rsi
0x18002455c  jz      short loc_180024567
0x18002455e  mov     rcx, rsi; pv
0x180024561  call    cs:__imp_CoTaskMemFree
0x180024567  mov     al, bl
0x180024569  mov     rcx, [rbp+50h+var_40]
0x18002456d  xor     rcx, rsp; StackCookie
0x180024570  call    __security_check_cookie
0x180024575  mov     rbx, [rsp+150h+arg_18]
0x18002457d  add     rsp, 120h
0x180024584  pop     r15
0x180024586  pop     r14
0x180024588  pop     r13
0x18002458a  pop     r12
0x18002458c  pop     rdi
0x18002458d  pop     rsi
0x18002458e  pop     rbp
0x18002458f  retn
0x180024590  mov     r9d, eax; char *
0x180024593  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002459a  mov     edx, 0CEh; void *
0x18002459f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800245a5  mov     r9d, eax; char *
0x1800245a8  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800245af  mov     edx, 0D1h; void *
0x1800245b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800245ba  mov     r9d, eax; char *
0x1800245bd  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800245c4  mov     edx, 0D3h; void *
0x1800245c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800245cf  mov     r9d, 80070057h; char *
0x1800245d5  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800245dc  mov     edx, 0C2h; void *
0x1800245e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800245e7  xor     r9d, r9d; lpArguments
0x1800245ea  xor     r8d, r8d; nNumberOfArguments
0x1800245ed  lea     edx, [r9+1]; dwExceptionFlags
0x1800245f1  mov     ecx, eax; dwExceptionCode
0x1800245f3  call    cs:__imp_RaiseException
0x1800245f9  nop
0x1800245fa  xor     r9d, r9d; lpArguments
0x1800245fd  xor     r8d, r8d; nNumberOfArguments
0x180024600  lea     edx, [r9+1]; dwExceptionFlags
0x180024604  mov     ecx, eax; dwExceptionCode
0x180024606  call    cs:__imp_RaiseException
```
