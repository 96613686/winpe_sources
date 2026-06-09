# GetPackageFullNameFromFamilyName(ushort const *,Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &)

- ea: `0x1800263e0`
- end: `0x18002690b`
- name: `?GetPackageFullNameFromFamilyName@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEBV?$ComPtr@UILicenseIdentityContext@@@WRL@Microsoft@@@Z`
- size: `1323`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180023420`

## callees

- `0x180004738`
- `0x1800171b0`
- `0x180017200`
- `0x1800263e0`
- `0x180026970`
- `0x1800593bc`
- `0x18008251f`
- `0x1800b8010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800267d1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800267d1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800264e3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180026528`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800264e3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180026528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002649e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002649e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026799`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026799`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026471`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026487`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002675d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800268cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026471`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026487`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002675d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800268cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
_QWORD *__fastcall GetPackageFullNameFromFamilyName(_QWORD *a1, const WCHAR *a2, __int64 *a3)
{
  __int64 v5; // rsi
  int v6; // eax
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // rbx
  UINT32 v9; // edx
  const WCHAR *v10; // rcx
  HRESULT v11; // eax
  HSTRING v12; // rbx
  int ActivationFactory; // eax
  HSTRING v14; // rbx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rbx
  unsigned int i; // edi
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rdi
  __int64 v25; // rcx
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rdi
  int v27; // eax
  PCWSTR StringRawBuffer; // rax
  PCWSTR v29; // r13
  __int64 v30; // r12
  __int64 v31; // rdi
  char *v32; // rsi
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v38; // [rsp+20h] [rbp-60h] BYREF
  HSTRING string; // [rsp+28h] [rbp-58h] BYREF
  HSTRING v40; // [rsp+30h] [rbp-50h] BYREF
  __int64 v41; // [rsp+38h] [rbp-48h] BYREF
  __int64 v42; // [rsp+40h] [rbp-40h] BYREF
  __int64 v43; // [rsp+48h] [rbp-38h] BYREF
  __int64 v44; // [rsp+50h] [rbp-30h] BYREF
  __int64 v45; // [rsp+58h] [rbp-28h]
  __int64 v46; // [rsp+68h] [rbp-18h]
  char v47; // [rsp+70h] [rbp-10h]
  __int64 v48; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int v50; // [rsp+D0h] [rbp+50h] BYREF
  unsigned int v51; // [rsp+D8h] [rbp+58h] BYREF

  v5 = *a3;
  v46 = v5;
  v47 = 0;
  v48 = v5;
  if ( !(unsigned __int8)ImpersonationScope<LicenseIdentityContextTraits>::AlreadyImpersonating() )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CF,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
        (const char *)(unsigned int)v6,
        v38);
    v47 = 1;
  }
  string = 0;
  v7 = -1;
  if ( !a2 )
  {
    WindowsDeleteString(0);
    v9 = 0;
    v10 = &LocaleName;
    goto LABEL_12;
  }
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( v8 <= 0xFFFFFFFF )
  {
    WindowsDeleteString(0);
    v9 = v8;
    v10 = a2;
LABEL_12:
    string = 0;
    v11 = WindowsCreateString(v10, v9, &string);
    goto LABEL_13;
  }
  v11 = -2147024362;
LABEL_13:
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
      (const char *)(unsigned int)v11,
      v38);
  v43 = 0;
  v12 = ::string;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
  ActivationFactory = RoGetActivationFactory(v12, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v43);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v38);
  v42 = 0;
  v14 = qword_1800F2B08;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
  v15 = RoGetActivationFactory(v14, &GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426, &v42);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
      (const char *)(unsigned int)v15,
      v38);
  v44 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v42 + 128LL))(v42, string, &v44);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
      (const char *)(unsigned int)v16,
      v38);
  v41 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v43 + 208LL))(v43, v44, &v41);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
      (const char *)(unsigned int)v17,
      v38);
  v51 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v41 + 56LL))(v41, &v51);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
      (const char *)(unsigned int)v18,
      v38);
  v19 = 0;
  v45 = 0;
  for ( i = 0; i < v51; ++i )
  {
    v38 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v41 + 48LL))(v41, i, &v38);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
        (const char *)(unsigned int)v21,
        v38);
    v50 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 128LL))(v38, &v50);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
        (const char *)(unsigned int)v22,
        v38);
    v23 = v38;
    if ( !v19 && v38 )
    {
      v19 = v38;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
      v23 = v38;
      v45 = v19;
    }
    if ( (v50 & 0xFFFFFFF3) != 0 || v50 == 12 )
    {
      if ( v19 != v23 )
      {
        v24 = v23;
        if ( v23 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
          v23 = v38;
        }
        v25 = v19;
        v19 = v24;
        v45 = v24;
        if ( v25 )
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 16LL))(v25, v23);
          v23 = v38;
        }
      }
      if ( v23 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      break;
    }
    if ( v23 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
  }
  if ( !v19 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
      (const char *)0x8000000BLL,
      v38);
  v40 = 0;
  v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 112LL);
  WindowsDeleteString(0);
  v40 = 0;
  v27 = v26(v19, &v40);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
      (const char *)(unsigned int)v27,
      v38);
  StringRawBuffer = WindowsGetStringRawBuffer(v40, 0);
  v29 = StringRawBuffer;
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  do
    ++v7;
  while ( StringRawBuffer[v7] );
  if ( v7 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  v30 = 2 * v7;
  if ( v7 > 7 )
  {
    v31 = std::wstring::_Calculate_growth(v7, 7);
    v32 = (char *)std::allocator<unsigned short>::allocate(a1, v31 + 1);
    *a1 = v32;
    a1[2] = v7;
    a1[3] = v31;
    memcpy_0(v32, v29, 2 * v7);
    *(_WORD *)&v32[v30] = 0;
    v5 = v46;
  }
  else
  {
    a1[2] = v7;
    a1[3] = 7;
    memcpy_0(a1, StringRawBuffer, 2 * v7);
    *(_WORD *)((char *)a1 + v30) = 0;
  }
  WindowsDeleteString(v40);
  v40 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v33 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  WindowsDeleteString(string);
  string = 0;
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
  return a1;
}

```

## disassembly

```asm
0x1800263e0  mov     [rsp-38h+arg_0], rbx
0x1800263e5  push    rbp
0x1800263e6  push    rsi
0x1800263e7  push    rdi
0x1800263e8  push    r12
0x1800263ea  push    r13
0x1800263ec  push    r14
0x1800263ee  push    r15
0x1800263f0  mov     rbp, rsp
0x1800263f3  sub     rsp, 80h
0x1800263fa  mov     rdi, rdx
0x1800263fd  mov     r15, rcx
0x180026400  xor     r12d, r12d
0x180026403  mov     rsi, [r8]
0x180026406  mov     [rbp+var_18], rsi
0x18002640a  mov     [rbp+var_10], r12b
0x18002640e  mov     [rbp+var_8], rsi
0x180026412  call    ?AlreadyImpersonating@?$ImpersonationScope@ULicenseIdentityContextTraits@@@@CA_NXZ; ImpersonationScope<LicenseIdentityContextTraits>::AlreadyImpersonating(void)
0x180026417  test    al, al
0x180026419  jnz     short loc_18002644B
0x18002641b  mov     rax, [rsi]
0x18002641e  mov     rcx, rsi
0x180026421  mov     rax, [rax+18h]
0x180026425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002642a  mov     rcx, [rbp+38h]; this
0x18002642e  test    eax, eax
0x180026430  jns     short loc_180026447
0x180026432  mov     r9d, eax; char *
0x180026435  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\licensem"...
0x18002643c  mov     edx, 1CFh; void *
0x180026441  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026447  mov     [rbp+var_10], 1
0x18002644b  mov     [rbp+string], r12
0x18002644f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180026453  test    rdi, rdi
0x180026456  jz      short loc_180026485
0x180026458  mov     rbx, r14
0x18002645b  inc     rbx
0x18002645e  cmp     [rdi+rbx*2], r12w
0x180026463  jnz     short loc_18002645B
0x180026465  mov     eax, 0FFFFFFFFh
0x18002646a  cmp     rbx, rax
0x18002646d  ja      short loc_18002647E
0x18002646f  xor     ecx, ecx; string
0x180026471  call    cs:__imp_WindowsDeleteString
0x180026477  mov     edx, ebx
0x180026479  mov     rcx, rdi
0x18002647c  jmp     short loc_180026496
0x18002647e  mov     eax, 80070216h
0x180026483  jmp     short loc_1800264A4
0x180026485  xor     ecx, ecx; string
0x180026487  call    cs:__imp_WindowsDeleteString
0x18002648d  xor     edx, edx; length
0x18002648f  lea     rcx, LocaleName; sourceString
0x180026496  mov     [rbp+string], r12
0x18002649a  lea     r8, [rbp+string]; string
0x18002649e  call    cs:__imp_WindowsCreateString
0x1800264a4  mov     rcx, [rbp+38h]; this
0x1800264a8  test    eax, eax
0x1800264aa  jns     short loc_1800264C1
0x1800264ac  mov     r9d, eax; char *
0x1800264af  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800264b6  mov     edx, 28h ; '('; void *
0x1800264bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800264c1  mov     [rbp+var_38], r12
0x1800264c5  mov     rbx, cs:string
0x1800264cc  lea     rcx, [rbp+var_38]
0x1800264d0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800264d5  lea     r8, [rbp+var_38]
0x1800264d9  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x1800264e0  mov     rcx, rbx
0x1800264e3  call    cs:__imp_RoGetActivationFactory
0x1800264e9  mov     rcx, [rbp+38h]; this
0x1800264ed  test    eax, eax
0x1800264ef  jns     short loc_180026506
0x1800264f1  mov     r9d, eax; char *
0x1800264f4  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800264fb  mov     edx, 2Bh ; '+'; void *
0x180026500  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026506  mov     [rbp+var_40], r12
0x18002650a  mov     rbx, cs:qword_1800F2B08
0x180026511  lea     rcx, [rbp+var_40]
0x180026515  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002651a  lea     r8, [rbp+var_40]
0x18002651e  lea     rdx, _GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426
0x180026525  mov     rcx, rbx
0x180026528  call    cs:__imp_RoGetActivationFactory
0x18002652e  mov     rcx, [rbp+38h]; this
0x180026532  test    eax, eax
0x180026534  jns     short loc_18002654B
0x180026536  mov     r9d, eax; char *
0x180026539  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x180026540  mov     edx, 2Eh ; '.'; void *
0x180026545  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002654b  mov     [rbp+var_30], r12
0x18002654f  mov     rcx, [rbp+var_40]
0x180026553  mov     rax, [rcx]
0x180026556  lea     r8, [rbp+var_30]
0x18002655a  mov     rdx, [rbp+string]
0x18002655e  mov     rax, [rax+80h]
0x180026565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002656a  mov     rcx, [rbp+38h]; this
0x18002656e  test    eax, eax
0x180026570  jns     short loc_180026587
0x180026572  mov     r9d, eax; char *
0x180026575  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x18002657c  mov     edx, 31h ; '1'; void *
0x180026581  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026587  mov     [rbp+var_48], r12
0x18002658b  mov     rcx, [rbp+var_38]
0x18002658f  mov     rax, [rcx]
0x180026592  lea     r8, [rbp+var_48]
0x180026596  mov     rdx, [rbp+var_30]
0x18002659a  mov     rax, [rax+0D0h]
0x1800265a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265a6  mov     rcx, [rbp+38h]; this
0x1800265aa  test    eax, eax
0x1800265ac  jns     short loc_1800265C3
0x1800265ae  mov     r9d, eax; char *
0x1800265b1  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800265b8  mov     edx, 34h ; '4'; void *
0x1800265bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800265c3  mov     [rbp+arg_18], r12d
0x1800265c7  mov     rcx, [rbp+var_48]
0x1800265cb  mov     rax, [rcx]
0x1800265ce  lea     rdx, [rbp+arg_18]
0x1800265d2  mov     rax, [rax+38h]
0x1800265d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265db  mov     rcx, [rbp+38h]; this
0x1800265df  test    eax, eax
0x1800265e1  jns     short loc_1800265F8
0x1800265e3  mov     r9d, eax; char *
0x1800265e6  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800265ed  mov     edx, 3Ah ; ':'; void *
0x1800265f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800265f8  mov     rbx, r12
0x1800265fb  mov     [rbp+var_28], rbx
0x1800265ff  mov     edi, r12d
0x180026602  cmp     edi, [rbp+arg_18]
0x180026605  jnb     loc_180026707
0x18002660b  mov     [rbp+var_60], r12
0x18002660f  mov     rcx, [rbp+var_48]
0x180026613  mov     rax, [rcx]
0x180026616  lea     r8, [rbp+var_60]
0x18002661a  mov     edx, edi
0x18002661c  mov     rax, [rax+30h]
0x180026620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026625  mov     rcx, [rbp+38h]; this
0x180026629  test    eax, eax
0x18002662b  js      loc_18002673B
0x180026631  mov     [rbp+arg_10], r12d
0x180026635  mov     rcx, [rbp+var_60]
0x180026639  mov     rax, [rcx]
0x18002663c  lea     rdx, [rbp+arg_10]
0x180026640  mov     rax, [rax+80h]
0x180026647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002664c  mov     rcx, [rbp+38h]; this
0x180026650  test    eax, eax
0x180026652  js      loc_180026726
0x180026658  mov     rdx, [rbp+var_60]
0x18002665c  test    rbx, rbx
0x18002665f  jnz     short loc_180026680
0x180026661  test    rdx, rdx
0x180026664  jz      short loc_180026680
0x180026666  mov     rbx, rdx
0x180026669  mov     rax, [rdx]
0x18002666c  mov     rcx, rdx
0x18002666f  mov     rax, [rax+8]
0x180026673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026678  mov     rdx, [rbp+var_60]
0x18002667c  mov     [rbp+var_28], rbx
0x180026680  test    [rbp+arg_10], 0FFFFFFF3h
0x180026687  jnz     short loc_1800266AF
0x180026689  cmp     [rbp+arg_10], 0Ch
0x18002668d  jz      short loc_1800266AF
0x18002668f  test    rdx, rdx
0x180026692  jz      short loc_1800266A8
0x180026694  mov     [rbp+var_60], r12
0x180026698  mov     rax, [rdx]
0x18002669b  mov     rcx, rdx
0x18002669e  mov     rax, [rax+10h]
0x1800266a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266a7  nop
0x1800266a8  inc     edi
0x1800266aa  jmp     loc_180026602
0x1800266af  cmp     rbx, rdx
0x1800266b2  jz      short loc_1800266EE
0x1800266b4  mov     rdi, rdx
0x1800266b7  test    rdx, rdx
0x1800266ba  jz      short loc_1800266CF
0x1800266bc  mov     rax, [rdx]
0x1800266bf  mov     rcx, rdx
0x1800266c2  mov     rax, [rax+8]
0x1800266c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266cb  mov     rdx, [rbp+var_60]
0x1800266cf  mov     rcx, rbx
0x1800266d2  mov     rbx, rdi
0x1800266d5  mov     [rbp+var_28], rbx
0x1800266d9  test    rcx, rcx
0x1800266dc  jz      short loc_1800266EE
0x1800266de  mov     rax, [rcx]
0x1800266e1  mov     rax, [rax+10h]
0x1800266e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266ea  mov     rdx, [rbp+var_60]
0x1800266ee  test    rdx, rdx
0x1800266f1  jz      short loc_180026707
0x1800266f3  mov     [rbp+var_60], r12
0x1800266f7  mov     rax, [rdx]
0x1800266fa  mov     rcx, rdx
0x1800266fd  mov     rax, [rax+10h]
0x180026701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026706  nop
0x180026707  test    rbx, rbx
0x18002670a  jnz     short loc_180026750
0x18002670c  mov     rcx, [rbp+38h]; this
0x180026710  mov     r9d, 8000000Bh; char *
0x180026716  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x18002671d  lea     edx, [rbx+55h]; void *
0x180026720  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026726  mov     r9d, eax; char *
0x180026729  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x180026730  mov     edx, 43h ; 'C'; void *
0x180026735  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002673b  mov     r9d, eax; char *
0x18002673e  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x180026745  mov     edx, 40h ; '@'; void *
0x18002674a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026750  mov     [rbp+var_50], r12
0x180026754  mov     rax, [rbx]
0x180026757  mov     rdi, [rax+70h]
0x18002675b  xor     ecx, ecx; string
0x18002675d  call    cs:__imp_WindowsDeleteString
0x180026763  mov     [rbp+var_50], r12
0x180026767  lea     rdx, [rbp+var_50]
0x18002676b  mov     rcx, rbx
0x18002676e  mov     rax, rdi
0x180026771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026776  mov     rcx, [rbp+38h]; this
0x18002677a  test    eax, eax
0x18002677c  jns     short loc_180026793
0x18002677e  mov     r9d, eax; char *
0x180026781  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x180026788  mov     edx, 59h ; 'Y'; void *
0x18002678d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026793  xor     edx, edx; length
0x180026795  mov     rcx, [rbp+var_50]; string
0x180026799  call    cs:__imp_WindowsGetStringRawBuffer
0x18002679f  mov     r13, rax
0x1800267a2  xorps   xmm0, xmm0
0x1800267a5  movups  xmmword ptr [r15], xmm0
0x1800267a9  mov     [r15+10h], r12
0x1800267ad  mov     [r15+18h], r12
0x1800267b1  inc     r14
0x1800267b4  cmp     [rax+r14*2], r12w
0x1800267b9  jnz     short loc_1800267B1
0x1800267bb  mov     r8, 7FFFFFFFFFFFFFFEh
0x1800267c5  cmp     r14, r8
0x1800267c8  jbe     short loc_1800267D8
0x1800267ca  lea     rcx, aStringTooLong; "string too long"
0x1800267d1  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800267d8  lea     r12, [r14+r14]
0x1800267dc  mov     edx, 7
0x1800267e1  cmp     r14, rdx
0x1800267e4  ja      short loc_180026805
0x1800267e6  mov     [r15+10h], r14
0x1800267ea  mov     [r15+18h], rdx
0x1800267ee  mov     r8, r12; Size
0x1800267f1  mov     rdx, r13; Src
0x1800267f4  mov     rcx, r15; void *
0x1800267f7  call    memcpy_0
0x1800267fc  xor     edi, edi
0x1800267fe  mov     [r12+r15], di
0x180026803  jmp     short loc_180026843
0x180026805  mov     rcx, r14
0x180026808  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18002680d  mov     rdi, rax
0x180026810  lea     rdx, [rax+1]
0x180026814  mov     rcx, r15
0x180026817  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x18002681c  mov     rsi, rax
0x18002681f  mov     [r15], rax
0x180026822  mov     [r15+10h], r14
0x180026826  mov     [r15+18h], rdi
0x18002682a  mov     r8, r12; Size
0x18002682d  mov     rdx, r13; Src
0x180026830  mov     rcx, rax; void *
0x180026833  call    memcpy_0
0x180026838  xor     edi, edi
0x18002683a  mov     [r12+rsi], di
0x18002683f  mov     rsi, [rbp+var_18]
0x180026843  mov     rcx, [rbp+var_50]; string
0x180026847  call    cs:__imp_WindowsDeleteString
0x18002684d  mov     [rbp+var_50], rdi
0x180026851  mov     rax, [rbx]
0x180026854  mov     rcx, rbx
0x180026857  mov     rax, [rax+10h]
0x18002685b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026860  nop
0x180026861  mov     rcx, [rbp+var_48]
0x180026865  test    rcx, rcx
  ... truncated ...
```
