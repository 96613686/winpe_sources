# SignalState::RegisterSignalCollection(Update const &,wil::com_ptr_t<ABI::Windows::Data::Json::IJsonValue,wil::err_exception_policy> const &,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::optional<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,UpdateDatabase &)

- ea: `0x1403478c0`
- end: `0x140348077`
- name: `?RegisterSignalCollection@SignalState@@SAXAEBVUpdate@@AEBV?$com_ptr_t@UIJsonValue@Json@Data@Windows@ABI@@Uerr_exception_policy@wil@@@wil@@V?$basic_zstring_view@_W@4@22V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEAVUpdateDatabase@@@Z`
- size: `1975`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140345238`
- `0x1403469b8`

## callees

- `0x14002163c`
- `0x14002a108`
- `0x14002a848`
- `0x1400413a8`
- `0x1400430dc`
- `0x140043284`
- `0x140043354`
- `0x1400447ac`
- `0x140045404`
- `0x1400d697c`
- `0x14012d7d8`
- `0x140342104`
- `0x140347318`
- `0x140347558`
- `0x1403478c0`
- `0x1403781a4`
- `0x140379070`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140347d2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140347d78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140347daa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140347d2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140347d78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140347daa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140347c9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140347d00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140347e3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140347e60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140347c9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140347d00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140347e3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140347e60`

## string_xrefs

- `0x140347fe7`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x140347fbd`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalState.cpp`
- `0x140347fd2`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalState.cpp`
- `0x140347ffc`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalState.cpp`
- `0x140348011`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalState.cpp`
- `0x140348026`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalState.cpp`
- `0x14034803b`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalState.cpp`
- `0x140348050`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalState.cpp`
- `0x140348065`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalState.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall SignalState::RegisterSignalCollection(
        __int64 a1,
        _QWORD *a2,
        const OLECHAR **a3,
        const wchar_t **a4,
        const wchar_t **a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v10; // rax
  __int64 System; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rax
  void *v14; // rax
  wchar_t **v15; // rax
  int v16; // ebx
  __int64 v17; // rdx
  char v18; // bl
  volatile signed __int32 *v19; // rdi
  volatile signed __int32 *v20; // rdi
  int v21; // eax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  const wchar_t *v26; // r12
  const wchar_t *v27; // rdi
  const wchar_t *v28; // r14
  const wchar_t *v29; // rbx
  const wchar_t *v30; // r15
  __int64 v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  __int64 *v34; // rbx
  __int64 (__fastcall *v35)(__int64 *, HSTRING *); // rdi
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // rbx
  __int64 (__fastcall *v40)(__int64, HSTRING *); // rdi
  int v41; // eax
  wchar_t **v42; // r12
  __int64 v43; // rbx
  __int64 v44; // r15
  __int64 v45; // rdi
  PCWSTR v46; // rax
  __int64 v47; // r14
  wchar_t *v48; // rax
  __int64 v49; // rcx
  int v50; // eax
  const wchar_t *v51; // r8
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 result; // rax
  __int64 v55; // rdx
  int v56; // [rsp+20h] [rbp-E0h]
  int v57; // [rsp+20h] [rbp-E0h]
  const OLECHAR *v58; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v59; // [rsp+38h] [rbp-C8h]
  const wchar_t *v60; // [rsp+40h] [rbp-C0h]
  PCWSTR StringRawBuffer; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v62[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v63; // [rsp+60h] [rbp-A0h]
  wchar_t *v64[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v65; // [rsp+80h] [rbp-80h]
  const wchar_t *v66; // [rsp+90h] [rbp-70h] BYREF
  volatile signed __int32 *v67; // [rsp+98h] [rbp-68h]
  const wchar_t *v68; // [rsp+A0h] [rbp-60h]
  __int64 v69; // [rsp+A8h] [rbp-58h]
  __int64 v70; // [rsp+B0h] [rbp-50h]
  _QWORD v71[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v72[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v73; // [rsp+E8h] [rbp-18h]
  _QWORD Src[5]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v75[8]; // [rsp+128h] [rbp+28h] BYREF
  HSTRING string; // [rsp+130h] [rbp+30h] BYREF
  __int64 *v77; // [rsp+138h] [rbp+38h] BYREF
  HSTRING v78; // [rsp+140h] [rbp+40h] BYREF
  __int64 *v79; // [rsp+148h] [rbp+48h] BYREF
  __int64 v80; // [rsp+150h] [rbp+50h] BYREF
  __int64 v81; // [rsp+158h] [rbp+58h] BYREF
  __int64 *v82; // [rsp+160h] [rbp+60h] BYREF
  wchar_t *v83[3]; // [rsp+168h] [rbp+68h] BYREF
  unsigned __int64 v84; // [rsp+180h] [rbp+80h]
  _QWORD v85[42]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  v69 = a1;
  Src[4] = a6;
  v70 = a7;
  LODWORD(string) = 0;
  if ( *(_BYTE *)(a6 + 32) )
  {
    v10 = -1;
    do
      ++v10;
    while ( (*a3)[v10] );
    v58 = *a3;
    v59 = v10;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v71, &v58);
    LODWORD(string) = 1025;
    System = SystemInterface::Providers::GetSystem(&v66);
    LODWORD(string) = 1027;
    v12 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
    v13 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v12 + 8LL))(v12, v62);
    LODWORD(string) = 1031;
    v14 = (void *)(*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v13 + 24LL))(*v13, v72);
    LODWORD(string) = 1039;
    v15 = (wchar_t **)std::filesystem::operator/(Src, v14, v71);
    v16 = 1055;
  }
  else
  {
    v58 = &psz;
    v59 = 0;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v64, &v58);
    v15 = v64;
    v16 = 2080;
  }
  LODWORD(string) = v16;
  std::wstring::wstring(v83, v15);
  v18 = v16 | 0x80;
  if ( (v18 & 0x20) != 0 )
  {
    v18 &= ~0x20u;
    std::wstring::~wstring(v64, v17);
  }
  if ( (v18 & 0x10) != 0 )
  {
    v18 &= ~0x10u;
    std::wstring::~wstring(Src, v17);
  }
  if ( (v18 & 8) != 0 )
  {
    v18 &= ~8u;
    std::wstring::~wstring(v72, v17);
  }
  if ( (v18 & 4) != 0 )
  {
    v18 &= ~4u;
    v19 = (volatile signed __int32 *)v62[1];
    if ( v62[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v62[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
  }
  if ( (v18 & 2) != 0 )
  {
    v18 &= ~2u;
    v20 = v67;
    if ( v67 )
    {
      if ( _InterlockedExchangeAdd(v67 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
  }
  if ( (v18 & 1) != 0 )
    std::wstring::~wstring(v71, v17);
  v81 = 0;
  v21 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 96LL))(*a2, &v81);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalState.cpp",
      (const char *)(unsigned int)v21,
      v56);
  v82 = 0;
  v22 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v81)(
          v81,
          &GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099,
          &v82);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v22,
      v56);
  v77 = 0;
  v23 = *v82;
  v77 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v23 + 48))(v82, &v77);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalState.cpp",
      (const char *)(unsigned int)v24,
      v56);
  v75[0] = 0;
  v25 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*v77 + 56))(v77, v75);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalState.cpp",
      (const char *)(unsigned int)v25,
      v56);
  memset(v85, 0, 0x148u);
  v26 = *a4;
  v58 = v26;
  v27 = (const wchar_t *)v83;
  if ( v84 > 7 )
    v27 = v83[0];
  v28 = *a5;
  v60 = *a5;
  if ( *(_BYTE *)(a6 + 32) )
  {
    std::wstring::wstring(v64, a6);
  }
  else
  {
    *(_OWORD *)v64 = 0;
    v65 = 0;
    std::wstring::_Construct<1,wchar_t const *>(v64, L"DefaultSignalId", 15);
  }
  v29 = (const wchar_t *)v64;
  if ( *((_QWORD *)&v65 + 1) > 7u )
    v29 = v64[0];
  v30 = *a3;
  v68 = v30;
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v85,
    "SignalCollectionRegistrationActivity");
  v85[0] = &Windows::Telemetry::ModelUpdater::SignalCollectionRegistrationActivity::`vftable';
  Windows::Telemetry::ModelUpdater::SignalCollectionRegistrationActivity::StartActivity(
    (Windows::Telemetry::ModelUpdater::SignalCollectionRegistrationActivity *)v85,
    v30,
    v29,
    v28,
    v27,
    v26);
  std::wstring::~wstring(v64, v31);
  if ( v75[0] )
  {
    do
    {
      v79 = 0;
      v32 = *v77;
      v79 = 0;
      v33 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v32 + 48))(v77, &v79);
      if ( v33 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x35,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalState.cpp",
          (const char *)(unsigned int)v33,
          v57);
      v78 = 0;
      v34 = v79;
      v35 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v79 + 48);
      WindowsDeleteString(0);
      v78 = 0;
      v36 = v35(v34, &v78);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x38,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalState.cpp",
          (const char *)(unsigned int)v36,
          v57);
      v80 = 0;
      v37 = *v79;
      v80 = 0;
      v38 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v37 + 56))(v79, &v80);
      if ( v38 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3B,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalState.cpp",
          (const char *)(unsigned int)v38,
          v57);
      string = 0;
      v39 = v80;
      v40 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v80 + 56LL);
      WindowsDeleteString(0);
      string = 0;
      v41 = v40(v39, &string);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3E,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalState.cpp",
          (const char *)(unsigned int)v41,
          v57);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      Windows::Telemetry::ModelUpdater::ModelUpdaterStatus<wchar_t const *,char const (&)[18]>(&StringRawBuffer);
      v42 = v83;
      if ( v84 > 7 )
        v42 = (wchar_t **)v83[0];
      v43 = -1;
      v44 = -1;
      do
        ++v44;
      while ( *((_WORD *)v42 + v44) );
      v45 = -1;
      do
        ++v45;
      while ( v28[v45] );
      v46 = WindowsGetStringRawBuffer(v78, 0);
      StringRawBuffer = v46;
      v47 = -1;
      do
        ++v47;
      while ( v46[v47] );
      do
        ++v43;
      while ( Signal::sc_windowsUpdateSignalRegistrationTag[v43] );
      v48 = (wchar_t *)WindowsGetStringRawBuffer(string, 0);
      v49 = -1;
      do
        ++v49;
      while ( v48[v49] );
      *(_QWORD *)v72 = v42;
      v73 = v44;
      Src[0] = v60;
      Src[1] = v45;
      v71[0] = StringRawBuffer;
      v71[1] = v47;
      v66 = Signal::sc_windowsUpdateSignalRegistrationTag;
      v67 = (volatile signed __int32 *)v43;
      v62[0] = v48;
      v62[1] = (wchar_t *)v49;
      Signal::RegisterSignal((unsigned int)v62, (unsigned int)&v66, (unsigned int)v71, (unsigned int)Src, (__int64)v72);
      v50 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*v77 + 64))(v77, v75);
      if ( v50 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4B,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalState.cpp",
          (const char *)(unsigned int)v50,
          v57);
      WindowsDeleteString(string);
      string = 0;
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      WindowsDeleteString(v78);
      v78 = 0;
      if ( v79 )
        (*(void (__fastcall **)(__int64 *))(*v79 + 16))(v79);
      v28 = v60;
    }
    while ( v75[0] );
    v30 = v68;
    v26 = v58;
  }
  if ( *(_BYTE *)(a6 + 32) )
  {
    std::wstring::wstring(v62, a6);
  }
  else
  {
    *(_OWORD *)v62 = 0;
    v63 = 0;
    std::wstring::_Construct<1,wchar_t const *>(v62, L"DefaultSignalId", 15);
  }
  v51 = (const wchar_t *)v62;
  if ( *((_QWORD *)&v63 + 1) > 7u )
    v51 = v62[0];
  Windows::Telemetry::ModelUpdater::SignalCollectionRegistrationActivity::Stop(
    (Windows::Telemetry::ModelUpdater::SignalCollectionRegistrationActivity *)v85,
    v30,
    v51,
    v28,
    v26);
  std::wstring::~wstring(v62, v52);
  UpdateDatabase::UpdateSignalState(v70, v69, 3);
  v85[0] = &Windows::Telemetry::ModelUpdater::SignalCollectionRegistrationActivity::`vftable';
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v85);
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v85);
  if ( v77 )
    (*(void (__fastcall **)(__int64 *))(*v77 + 16))(v77);
  if ( v82 )
    (*(void (__fastcall **)(__int64 *))(*v82 + 16))(v82);
  if ( v81 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
  result = std::wstring::~wstring(v83, v53);
  if ( *(_BYTE *)(a6 + 32) )
    return std::wstring::~wstring(a6, v55);
  return result;
}

```

## disassembly

```asm
0x1403478c0  push    rbp
0x1403478c2  push    rbx
0x1403478c3  push    rsi
0x1403478c4  push    rdi
0x1403478c5  push    r12
0x1403478c7  push    r13
0x1403478c9  push    r14
0x1403478cb  push    r15
0x1403478cd  lea     rbp, [rsp-1F8h]
0x1403478d5  sub     rsp, 2F8h
0x1403478dc  mov     rax, cs:__security_cookie
0x1403478e3  xor     rax, rsp
0x1403478e6  mov     [rbp+230h+var_50], rax
0x1403478ed  mov     r12, r9
0x1403478f0  mov     r15, r8
0x1403478f3  mov     r14, rdx
0x1403478f6  mov     [rbp+230h+var_288], rcx
0x1403478fa  mov     r13, [rbp+230h+arg_20]
0x140347901  mov     rsi, [rbp+230h+arg_28]
0x140347908  mov     [rbp+230h+var_210], rsi
0x14034790c  mov     rax, [rbp+230h+arg_30]
0x140347913  mov     [rbp+230h+var_280], rax
0x140347917  xor     edx, edx
0x140347919  mov     dword ptr [rbp+230h+string], edx
0x14034791c  cmp     [rsi+20h], dl
0x14034791f  jz      loc_1403479C4
0x140347925  mov     rcx, [r8]
0x140347928  or      rax, 0FFFFFFFFFFFFFFFFh
0x14034792c  inc     rax
0x14034792f  cmp     [rcx+rax*2], dx
0x140347933  jnz     short loc_14034792C
0x140347935  mov     [rsp+330h+var_300], rcx
0x14034793a  mov     [rsp+330h+var_2F8], rax
0x14034793f  lea     rdx, [rsp+330h+var_300]
0x140347944  lea     rcx, [rbp+230h+var_270]
0x140347948  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x14034794d  nop
0x14034794e  mov     dword ptr [rbp+230h+string], 401h
0x140347955  lea     rcx, [rbp+230h+var_2A0]
0x140347959  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14034795e  nop
0x14034795f  mov     dword ptr [rbp+230h+string], 403h
0x140347966  mov     rdx, [rax]
0x140347969  mov     rax, [rdx+8]
0x14034796d  movsxd  rcx, dword ptr [rax+4]
0x140347971  add     rdx, 8
0x140347975  add     rcx, rdx
0x140347978  mov     rax, [rcx]
0x14034797b  lea     rdx, [rsp+330h+var_2E0]
0x140347980  mov     rax, [rax+8]
0x140347984  call    _guard_dispatch_icall
0x140347989  nop
0x14034798a  mov     dword ptr [rbp+230h+string], 407h
0x140347991  mov     rcx, [rax]
0x140347994  mov     rax, [rcx]
0x140347997  lea     rdx, [rbp+230h+var_250]
0x14034799b  mov     rax, [rax+18h]
0x14034799f  call    _guard_dispatch_icall
0x1403479a4  nop
0x1403479a5  mov     dword ptr [rbp+230h+string], 40Fh
0x1403479ac  lea     r8, [rbp+230h+var_270]; void *
0x1403479b0  mov     rdx, rax; void *
0x1403479b3  lea     rcx, [rbp+230h+Src]; Src
0x1403479b7  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1403479bc  nop
0x1403479bd  mov     ebx, 41Fh
0x1403479c2  jmp     short loc_1403479EE
0x1403479c4  lea     rax, psz
0x1403479cb  mov     [rsp+330h+var_300], rax
0x1403479d0  mov     [rsp+330h+var_2F8], rdx
0x1403479d5  lea     rdx, [rsp+330h+var_300]
0x1403479da  lea     rcx, [rsp+330h+var_2C0]
0x1403479df  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x1403479e4  lea     rax, [rsp+330h+var_2C0]
0x1403479e9  mov     ebx, 820h
0x1403479ee  mov     dword ptr [rbp+230h+string], ebx
0x1403479f1  mov     rdx, rax
0x1403479f4  lea     rcx, [rbp+230h+var_1C8]
0x1403479f8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1403479fd  bts     ebx, 7
0x140347a01  test    bl, 20h
0x140347a04  jz      short loc_140347A14
0x140347a06  and     ebx, 0FFFFFFDFh
0x140347a09  lea     rcx, [rsp+330h+var_2C0]
0x140347a0e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140347a13  nop
0x140347a14  test    bl, 10h
0x140347a17  jz      short loc_140347A26
0x140347a19  and     ebx, 0FFFFFFEFh
0x140347a1c  lea     rcx, [rbp+230h+Src]
0x140347a20  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140347a25  nop
0x140347a26  test    bl, 8
0x140347a29  jz      short loc_140347A38
0x140347a2b  and     ebx, 0FFFFFFF7h
0x140347a2e  lea     rcx, [rbp+230h+var_250]
0x140347a32  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140347a37  nop
0x140347a38  test    bl, 4
0x140347a3b  jz      short loc_140347A82
0x140347a3d  and     ebx, 0FFFFFFFBh
0x140347a40  mov     rdi, [rsp+330h+var_2E0+8]
0x140347a45  test    rdi, rdi
0x140347a48  jz      short loc_140347A82
0x140347a4a  or      eax, 0FFFFFFFFh
0x140347a4d  lock xadd [rdi+8], eax
0x140347a52  cmp     eax, 1
0x140347a55  jnz     short loc_140347A82
0x140347a57  mov     rax, [rdi]
0x140347a5a  mov     rcx, rdi
0x140347a5d  mov     rax, [rax]
0x140347a60  call    _guard_dispatch_icall
0x140347a65  or      eax, 0FFFFFFFFh
0x140347a68  lock xadd [rdi+0Ch], eax
0x140347a6d  cmp     eax, 1
0x140347a70  jnz     short loc_140347A82
0x140347a72  mov     rax, [rdi]
0x140347a75  mov     rcx, rdi
0x140347a78  mov     rax, [rax+8]
0x140347a7c  call    _guard_dispatch_icall
0x140347a81  nop
0x140347a82  test    bl, 2
0x140347a85  jz      short loc_140347ACB
0x140347a87  and     ebx, 0FFFFFFFDh
0x140347a8a  mov     rdi, [rbp+230h+var_298]
0x140347a8e  test    rdi, rdi
0x140347a91  jz      short loc_140347ACB
0x140347a93  or      eax, 0FFFFFFFFh
0x140347a96  lock xadd [rdi+8], eax
0x140347a9b  cmp     eax, 1
0x140347a9e  jnz     short loc_140347ACB
0x140347aa0  mov     rax, [rdi]
0x140347aa3  mov     rcx, rdi
0x140347aa6  mov     rax, [rax]
0x140347aa9  call    _guard_dispatch_icall
0x140347aae  or      eax, 0FFFFFFFFh
0x140347ab1  lock xadd [rdi+0Ch], eax
0x140347ab6  cmp     eax, 1
0x140347ab9  jnz     short loc_140347ACB
0x140347abb  mov     rax, [rdi]
0x140347abe  mov     rcx, rdi
0x140347ac1  mov     rax, [rax+8]
0x140347ac5  call    _guard_dispatch_icall
0x140347aca  nop
0x140347acb  test    bl, 1
0x140347ace  jz      short loc_140347AD9
0x140347ad0  lea     rcx, [rbp+230h+var_270]
0x140347ad4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140347ad9  xor     ebx, ebx
0x140347adb  mov     [rbp+230h+var_1D8], rbx
0x140347adf  mov     rcx, [r14]
0x140347ae2  mov     rax, [rcx]
0x140347ae5  mov     [rbp+230h+var_1D8], rbx
0x140347ae9  lea     rdx, [rbp+230h+var_1D8]
0x140347aed  mov     rax, [rax+60h]
0x140347af1  call    _guard_dispatch_icall
0x140347af6  mov     rcx, [rbp+238h]; this
0x140347afd  test    eax, eax
0x140347aff  js      loc_140347FCF
0x140347b05  mov     rcx, [rbp+230h+var_1D8]
0x140347b09  mov     [rbp+230h+var_1D0], rbx
0x140347b0d  mov     rax, [rcx]
0x140347b10  lea     r8, [rbp+230h+var_1D0]
0x140347b14  lea     rdx, _GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099
0x140347b1b  mov     rax, [rax]
0x140347b1e  call    _guard_dispatch_icall
0x140347b23  mov     rcx, [rbp+238h]; this
0x140347b2a  test    eax, eax
0x140347b2c  js      loc_140347FE4
0x140347b32  mov     [rbp+230h+var_1F8], rbx
0x140347b36  mov     rcx, [rbp+230h+var_1D0]
0x140347b3a  mov     rax, [rcx]
0x140347b3d  mov     [rbp+230h+var_1F8], rbx
0x140347b41  lea     rdx, [rbp+230h+var_1F8]
0x140347b45  mov     rax, [rax+30h]
0x140347b49  call    _guard_dispatch_icall
0x140347b4e  mov     rcx, [rbp+238h]; this
0x140347b55  test    eax, eax
0x140347b57  js      loc_140347FF9
0x140347b5d  mov     [rbp+230h+var_208], bl
0x140347b60  mov     rcx, [rbp+230h+var_1F8]
0x140347b64  mov     rax, [rcx]
0x140347b67  lea     rdx, [rbp+230h+var_208]
0x140347b6b  mov     rax, [rax+38h]
0x140347b6f  call    _guard_dispatch_icall
0x140347b74  mov     rcx, [rbp+238h]; this
0x140347b7b  test    eax, eax
0x140347b7d  js      loc_14034800E
0x140347b83  xor     edx, edx; Val
0x140347b85  mov     r8d, 148h; Size
0x140347b8b  lea     rcx, [rbp+230h+var_1A0]; void *
0x140347b92  call    memset
0x140347b97  mov     r12, [r12]
0x140347b9b  mov     [rsp+330h+var_300], r12
0x140347ba0  lea     rdi, [rbp+230h+var_1C8]
0x140347ba4  cmp     [rbp+230h+var_1B0], 7
0x140347bac  cmova   rdi, [rbp+230h+var_1C8]
0x140347bb1  mov     r14, [r13+0]
0x140347bb5  mov     [rsp+330h+var_2F0], r14
0x140347bba  xor     r13d, r13d
0x140347bbd  lea     rcx, [rsp+330h+var_2C0]
0x140347bc2  cmp     [rsi+20h], r13b
0x140347bc6  jz      short loc_140347BD2
0x140347bc8  mov     rdx, rsi
0x140347bcb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140347bd0  jmp     short loc_140347BF4
0x140347bd2  xorps   xmm0, xmm0
0x140347bd5  movups  xmmword ptr [rsp+330h+var_2C0], xmm0
0x140347bda  xorps   xmm1, xmm1
0x140347bdd  movdqu  [rbp+230h+var_2B0], xmm1
0x140347be2  mov     r8d, 0Fh
0x140347be8  lea     rdx, aDefaultsignali; "DefaultSignalId"
0x140347bef  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140347bf4  lea     rbx, [rsp+330h+var_2C0]
0x140347bf9  cmp     qword ptr [rbp+230h+var_2B0+8], 7
0x140347bfe  cmova   rbx, [rsp+330h+var_2C0]
0x140347c04  mov     r15, [r15]
0x140347c07  mov     [rbp+230h+var_290], r15
0x140347c0b  lea     rdx, aSignalcollecti_0; "SignalCollectionRegistrationActivity"
0x140347c12  lea     rcx, [rbp+230h+var_1A0]
0x140347c19  call    ??0?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140347c1e  lea     rax, ??_7SignalCollectionRegistrationActivity@ModelUpdater@Telemetry@Windows@@6B@; const Windows::Telemetry::ModelUpdater::SignalCollectionRegistrationActivity::`vftable'
0x140347c25  mov     [rbp+230h+var_1A0], rax
0x140347c2c  mov     [rsp+330h+var_308], r12; wchar_t *
0x140347c31  mov     [rsp+330h+var_310], rdi; int
0x140347c36  mov     r9, r14; wchar_t *
0x140347c39  mov     r8, rbx; wchar_t *
0x140347c3c  mov     rdx, r15; wchar_t *
0x140347c3f  lea     rcx, [rbp+230h+var_1A0]; this
0x140347c46  call    ?StartActivity@SignalCollectionRegistrationActivity@ModelUpdater@Telemetry@Windows@@QEAAXPEB_W0000@Z; Windows::Telemetry::ModelUpdater::SignalCollectionRegistrationActivity::StartActivity(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)
0x140347c4b  nop
0x140347c4c  lea     rcx, [rsp+330h+var_2C0]
0x140347c51  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140347c56  cmp     [rbp+230h+var_208], r13b
0x140347c5a  jz      loc_140347E98
0x140347c60  mov     [rbp+230h+var_1E8], r13
0x140347c64  mov     rcx, [rbp+230h+var_1F8]
0x140347c68  mov     rax, [rcx]
0x140347c6b  mov     [rbp+230h+var_1E8], r13
0x140347c6f  lea     rdx, [rbp+230h+var_1E8]
0x140347c73  mov     rax, [rax+30h]
0x140347c77  call    _guard_dispatch_icall
0x140347c7c  mov     rcx, [rbp+238h]; this
0x140347c83  test    eax, eax
0x140347c85  js      loc_140347FBA
0x140347c8b  mov     [rbp+230h+var_1F0], r13
0x140347c8f  mov     rbx, [rbp+230h+var_1E8]
0x140347c93  mov     rax, [rbx]
0x140347c96  mov     rdi, [rax+30h]
0x140347c9a  xor     ecx, ecx; string
0x140347c9c  call    cs:__imp_WindowsDeleteString
0x140347ca2  mov     [rbp+230h+var_1F0], r13
0x140347ca6  lea     rdx, [rbp+230h+var_1F0]
0x140347caa  mov     rcx, rbx
0x140347cad  mov     rax, rdi
0x140347cb0  call    _guard_dispatch_icall
0x140347cb5  mov     rcx, [rbp+238h]; this
0x140347cbc  test    eax, eax
0x140347cbe  js      loc_140348062
0x140347cc4  mov     [rbp+230h+var_1E0], r13
0x140347cc8  mov     rcx, [rbp+230h+var_1E8]
0x140347ccc  mov     rax, [rcx]
0x140347ccf  mov     [rbp+230h+var_1E0], r13
0x140347cd3  lea     rdx, [rbp+230h+var_1E0]
0x140347cd7  mov     rax, [rax+38h]
0x140347cdb  call    _guard_dispatch_icall
0x140347ce0  mov     rcx, [rbp+238h]; this
0x140347ce7  test    eax, eax
0x140347ce9  js      loc_14034804D
0x140347cef  mov     [rbp+230h+string], r13
0x140347cf3  mov     rbx, [rbp+230h+var_1E0]
0x140347cf7  mov     rax, [rbx]
0x140347cfa  mov     rdi, [rax+38h]
0x140347cfe  xor     ecx, ecx; string
0x140347d00  call    cs:__imp_WindowsDeleteString
0x140347d06  mov     [rbp+230h+string], r13
0x140347d0a  lea     rdx, [rbp+230h+string]
0x140347d0e  mov     rcx, rbx
0x140347d11  mov     rax, rdi
0x140347d14  call    _guard_dispatch_icall
0x140347d19  mov     rcx, [rbp+238h]; this
0x140347d20  test    eax, eax
0x140347d22  js      loc_140348038
0x140347d28  xor     edx, edx; length
0x140347d2a  mov     rcx, [rbp+230h+string]; string
0x140347d2e  call    cs:__imp_WindowsGetStringRawBuffer
0x140347d34  mov     [rsp+330h+var_2E8], rax
0x140347d39  lea     rcx, [rsp+330h+var_2E8]
0x140347d3e  call    ??$ModelUpdaterStatus@PEB_WAEAY0BC@$$CBD@ModelUpdater@Telemetry@Windows@@SAX$$QEAPEB_WAEAY0BC@$$CBD@Z; Windows::Telemetry::ModelUpdater::ModelUpdaterStatus<wchar_t const *,char const (&)[18]>(wchar_t const * &&,char const (&)[18])
0x140347d43  lea     r12, [rbp+230h+var_1C8]
0x140347d47  cmp     [rbp+230h+var_1B0], 7
0x140347d4f  cmova   r12, [rbp+230h+var_1C8]
0x140347d54  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140347d58  mov     r15, rbx
0x140347d5b  inc     r15
0x140347d5e  cmp     [r12+r15*2], r13w
0x140347d63  jnz     short loc_140347D5B
0x140347d65  mov     rdi, rbx
0x140347d68  inc     rdi
0x140347d6b  cmp     [r14+rdi*2], r13w
  ... truncated ...
```
