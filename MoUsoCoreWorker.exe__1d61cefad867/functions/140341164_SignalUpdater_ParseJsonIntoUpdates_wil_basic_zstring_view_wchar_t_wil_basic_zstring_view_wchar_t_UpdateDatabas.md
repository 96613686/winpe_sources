# SignalUpdater::ParseJsonIntoUpdates(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,UpdateDatabase &)

- ea: `0x140341164`
- end: `0x14034196e`
- name: `?ParseJsonIntoUpdates@SignalUpdater@@KA?AV?$vector@V?$shared_ptr@VUpdate@@@std@@V?$allocator@V?$shared_ptr@VUpdate@@@std@@@2@@std@@V?$basic_zstring_view@_W@wil@@0AEAVUpdateDatabase@@@Z`
- size: `2058`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x1403401d0`

## callees

- `0x14002163c`
- `0x14002a108`
- `0x14002a848`
- `0x1400413a8`
- `0x140045404`
- `0x140241c8c`
- `0x1402c2b9c`
- `0x1402da538`
- `0x14033fd58`
- `0x14033fe5c`
- `0x140340b44`
- `0x140341164`
- `0x140342104`
- `0x140379070`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140341200`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140341200`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140341387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140341588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1403415c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140341387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140341588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1403415c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14034134c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1403414e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14034175d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1403417c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14034134c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1403414e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14034175d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1403417c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1403411db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1403411db`

## string_xrefs

- `0x1403418de`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1403411d4`: `Windows.Data.Json.JsonObject`
- `0x140341591`: `ModelJsonParsingActivity`
- `0x140341875`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x14034188a`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x14034189f`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x1403418b4`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x1403418c9`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x1403418f3`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x140341908`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x14034191d`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x140341932`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x140341947`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x14034195c`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall SignalUpdater::ParseJsonIntoUpdates(__int64 a1, __int64 **a2, __int128 *a3, __int64 a4)
{
  __int64 v4; // r13
  __int128 *v5; // r12
  __int64 v7; // r14
  HRESULT StringReference; // eax
  int v9; // edx
  unsigned int v10; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v12; // rcx
  _QWORD *v13; // rbx
  __int64 (__fastcall *v14)(_QWORD *, _QWORD, __int64 *); // rdi
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rdi
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64 *); // rdi
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rdi
  int v27; // eax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  int v31; // eax
  __m128i si128; // xmm6
  __int64 v33; // rax
  int v34; // eax
  __int64 *v35; // rbx
  __int64 (__fastcall *v36)(__int64 *, HSTRING *); // rdi
  int v37; // eax
  __int64 v38; // rax
  int v39; // eax
  const wchar_t *v40; // rbx
  PCWSTR v41; // rcx
  __int64 v42; // rax
  WCHAR *v43; // rax
  const char *v44; // r9
  _QWORD *v45; // rdx
  volatile signed __int32 *v46; // rbx
  const wchar_t *v47; // rdx
  int v48; // eax
  __int64 v49; // rdx
  int v51; // [rsp+20h] [rbp-298h]
  __int128 v55; // [rsp+60h] [rbp-258h] BYREF
  __int128 v56; // [rsp+70h] [rbp-248h] BYREF
  WCHAR v57; // [rsp+80h] [rbp-238h] BYREF
  volatile signed __int32 *v58; // [rsp+88h] [rbp-230h]
  _BYTE v59[8]; // [rsp+90h] [rbp-228h] BYREF
  __int64 *StringRawBuffer; // [rsp+98h] [rbp-220h] BYREF
  HSTRING v61; // [rsp+A0h] [rbp-218h] BYREF
  __int64 *v62; // [rsp+A8h] [rbp-210h] BYREF
  __int64 *v63; // [rsp+B0h] [rbp-208h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-200h] BYREF
  __int64 v65; // [rsp+C0h] [rbp-1F8h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-1F0h] BYREF
  __int64 v67; // [rsp+D0h] [rbp-1E8h] BYREF
  __int64 *v68; // [rsp+D8h] [rbp-1E0h] BYREF
  _QWORD *v69; // [rsp+E0h] [rbp-1D8h] BYREF
  wchar_t *v70[2]; // [rsp+E8h] [rbp-1D0h] BYREF
  __m128i v71; // [rsp+F8h] [rbp-1C0h] BYREF
  _QWORD v72[42]; // [rsp+110h] [rbp-1A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  v4 = a4;
  v5 = a3;
  v7 = a1;
  v69 = 0;
  v71.m128i_i64[1] = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.Data.Json.JsonObject",
                      0x1Cu,
                      (HSTRING_HEADER *)v70,
                      (HSTRING *)&v71.m128i_i64[1]);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v9, v10);
LABEL_48:
    wil::details::in1diag3::Throw_Hr(
      v12,
      (void *)0xBE,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v51);
  }
  ActivationFactory = RoGetActivationFactory(v71.m128i_i64[1], &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v69);
  v12 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_48;
  v65 = 0;
  v13 = v69;
  v14 = *(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64 *))(*v69 + 48LL);
  v65 = 0;
  StringRawBuffer = *a2;
  v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v70, &StringRawBuffer);
  v16 = v14(v13, *(_QWORD *)(v15 + 24), &v65);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
      (const char *)(unsigned int)v16,
      v51);
  v67 = 0;
  v17 = v65;
  v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v65 + 64LL);
  v67 = 0;
  v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v70, &SignalState::sc_modelSettingsObjectName);
  v20 = v18(v17, *(_QWORD *)(v19 + 24), &v67);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
      (const char *)(unsigned int)v20,
      v51);
  v66 = 0;
  v21 = v65;
  v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v65 + 48LL);
  v66 = 0;
  v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v70, &SignalState::sc_modelSettingsObjectName);
  v24 = v22(v21, *(_QWORD *)(v23 + 24), &v66);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
      (const char *)(unsigned int)v24,
      v51);
  string = 0;
  v25 = v66;
  v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v66 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v27 = v26(v25, &string);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
      (const char *)(unsigned int)v27,
      v51);
  StringRawBuffer = (__int64 *)WindowsGetStringRawBuffer(string, 0);
  Windows::Telemetry::ModelUpdater::ModelUpdaterStatus<wchar_t const *,char const (&)[18]>(&StringRawBuffer);
  v68 = 0;
  v28 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v67)(
          v67,
          &GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099,
          &v68);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v28,
      v51);
  v62 = 0;
  v29 = *v68;
  v62 = 0;
  v30 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v29 + 48))(v68, &v62);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
      (const char *)(unsigned int)v30,
      v51);
  v59[0] = 0;
  v31 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*v62 + 56))(v62, v59);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
      (const char *)(unsigned int)v31,
      v51);
  *(_OWORD *)v7 = 0;
  *(_QWORD *)v7 = 0;
  *(_QWORD *)(v7 + 8) = 0;
  *(_QWORD *)(v7 + 16) = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( v59[0] )
  {
    v63 = 0;
    v33 = *v62;
    v63 = 0;
    v34 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v33 + 48))(v62, &v63);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDA,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
        (const char *)(unsigned int)v34,
        v51);
    v61 = 0;
    v35 = v63;
    v36 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v63 + 48);
    WindowsDeleteString(0);
    v61 = 0;
    v37 = v36(v35, &v61);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDD,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
        (const char *)(unsigned int)v37,
        v51);
    StringRawBuffer = 0;
    v38 = *v63;
    StringRawBuffer = 0;
    v39 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v38 + 56))(v63, &StringRawBuffer);
    if ( v39 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE0,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
        (const char *)(unsigned int)v39,
        v51);
    *(_OWORD *)v70 = 0;
    v71 = si128;
    LOWORD(v70[0]) = 0;
    memset(v72, 0, 0x148u);
    v40 = WindowsGetStringRawBuffer(v61, 0);
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v72,
      "ModelJsonParsingActivity");
    v72[0] = &Windows::Telemetry::ModelUpdater::ModelJsonParsingActivity::`vftable';
    Windows::Telemetry::ModelUpdater::ModelJsonParsingActivity::StartActivity(
      (Windows::Telemetry::ModelUpdater::ModelJsonParsingActivity *)v72,
      v40);
    v41 = WindowsGetStringRawBuffer(v61, 0);
    v42 = -1;
    do
      ++v42;
    while ( v41[v42] );
    try
    {
      *(_QWORD *)&v55 = v41;
      *((_QWORD *)&v55 + 1) = v42;
      v56 = *v5;
      v43 = SignalUpdater::ParseJsonValueIntoUpdate(&v57, &StringRawBuffer, &v56, &v55, v4);
      v45 = *(_QWORD **)(v7 + 8);
      if ( v45 == *(_QWORD **)(v7 + 16) )
      {
        std::vector<std::shared_ptr<Update>>::_Emplace_reallocate<std::shared_ptr<Windows::WU::CurrentVersionUpdate>>(
          v7,
          v45,
          v43);
      }
      else
      {
        *v45 = 0;
        v45[1] = 0;
        *v45 = *(_QWORD *)v43;
        v45[1] = *((_QWORD *)v43 + 1);
        *(_QWORD *)v43 = 0;
        *((_QWORD *)v43 + 1) = 0;
        *(_QWORD *)(v7 + 8) += 16LL;
      }
      v46 = v58;
      if ( v58 )
      {
        if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
          if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
        }
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xE9,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
        v44);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v7 = a1;
      v5 = a3;
      v4 = a4;
    }
    v47 = (const wchar_t *)v70;
    if ( v71.m128i_i64[1] > 7uLL )
      v47 = v70[0];
    Windows::Telemetry::ModelUpdater::ModelJsonParsingActivity::Stop(
      (Windows::Telemetry::ModelUpdater::ModelJsonParsingActivity *)v72,
      v47);
    v48 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*v62 + 64))(v62, v59);
    if ( v48 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xED,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
        (const char *)(unsigned int)v48,
        v51);
    v72[0] = &Windows::Telemetry::ModelUpdater::ModelJsonParsingActivity::`vftable';
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v72);
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v72);
    std::wstring::~wstring(v70, v49);
    if ( StringRawBuffer )
      (*(void (__fastcall **)(__int64 *))(*StringRawBuffer + 16))(StringRawBuffer);
    WindowsDeleteString(v61);
    v61 = 0;
    if ( v63 )
      (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
  }
  if ( v62 )
    (*(void (__fastcall **)(__int64 *))(*v62 + 16))(v62);
  if ( v68 )
    (*(void (__fastcall **)(__int64 *))(*v68 + 16))(v68);
  WindowsDeleteString(string);
  string = 0;
  if ( v66 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
  if ( v67 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
  if ( v65 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
  if ( v69 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))(*v69 + 16LL))(v69, *v69);
  return v7;
}

```

## disassembly

```asm
0x140341164  mov     r11, rsp
0x140341167  mov     [r11+8], rcx
0x14034116b  push    rbx
0x14034116c  push    rsi
0x14034116d  push    rdi
0x14034116e  push    r12
0x140341170  push    r13
0x140341172  push    r14
0x140341174  push    r15
0x140341176  sub     rsp, 280h
0x14034117d  movaps  xmmword ptr [r11-48h], xmm6
0x140341182  mov     rax, cs:__security_cookie
0x140341189  xor     rax, rsp
0x14034118c  mov     [rsp+2B8h+var_58], rax
0x140341194  mov     r13, r9
0x140341197  mov     r12, r8
0x14034119a  mov     r15, rdx
0x14034119d  mov     r14, rcx
0x1403411a0  mov     [rsp+2B8h+var_280], rcx
0x1403411a5  mov     [rsp+2B8h+var_278], r8
0x1403411aa  mov     [rsp+2B8h+var_268], r9
0x1403411af  xor     esi, esi
0x1403411b1  mov     [rsp+2B8h+var_288], esi
0x1403411b5  mov     [r11-1D8h], rsi
0x1403411bc  mov     [r11-1B8h], rsi
0x1403411c3  lea     r9, [r11-1B8h]; string
0x1403411ca  lea     r8, [r11-1D0h]; hstringHeader
0x1403411d1  lea     edx, [rsi+1Ch]; length
0x1403411d4  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x1403411db  call    cs:__imp_WindowsCreateStringReference
0x1403411e1  test    eax, eax
0x1403411e3  js      loc_14034186A
0x1403411e9  lea     r8, [rsp+2B8h+var_1D8]
0x1403411f1  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x1403411f8  mov     rcx, [rsp+2B8h+var_1B8]
0x140341200  call    cs:__imp_RoGetActivationFactory
0x140341206  mov     rcx, [rsp+2B8h]
0x14034120e  test    eax, eax
0x140341210  js      loc_140341872
0x140341216  mov     [rsp+2B8h+var_1F8], rsi
0x14034121e  mov     rbx, [rsp+2B8h+var_1D8]
0x140341226  mov     rax, [rbx]
0x140341229  mov     rdi, [rax+30h]
0x14034122d  mov     [rsp+2B8h+var_1F8], rsi
0x140341235  mov     rax, [r15]
0x140341238  mov     [rsp+2B8h+var_220], rax
0x140341240  lea     rdx, [rsp+2B8h+var_220]
0x140341248  lea     rcx, [rsp+2B8h+var_1D0]
0x140341250  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x140341255  nop
0x140341256  lea     r8, [rsp+2B8h+var_1F8]
0x14034125e  mov     rdx, [rax+18h]
0x140341262  mov     rcx, rbx
0x140341265  mov     rax, rdi
0x140341268  call    _guard_dispatch_icall
0x14034126d  mov     rcx, [rsp+2B8h]; this
0x140341275  test    eax, eax
0x140341277  js      loc_140341887
0x14034127d  mov     [rsp+2B8h+var_1E8], rsi
0x140341285  mov     rbx, [rsp+2B8h+var_1F8]
0x14034128d  mov     rax, [rbx]
0x140341290  mov     rdi, [rax+40h]
0x140341294  mov     [rsp+2B8h+var_1E8], rsi
0x14034129c  lea     rdx, ?sc_modelSettingsObjectName@SignalState@@2QEB_WEB; wchar_t const * const SignalState::sc_modelSettingsObjectName
0x1403412a3  lea     rcx, [rsp+2B8h+var_1D0]
0x1403412ab  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1403412b0  nop
0x1403412b1  lea     r8, [rsp+2B8h+var_1E8]
0x1403412b9  mov     rdx, [rax+18h]
0x1403412bd  mov     rcx, rbx
0x1403412c0  mov     rax, rdi
0x1403412c3  call    _guard_dispatch_icall
0x1403412c8  mov     rcx, [rsp+2B8h]; this
0x1403412d0  test    eax, eax
0x1403412d2  js      loc_14034189C
0x1403412d8  mov     [rsp+2B8h+var_1F0], rsi
0x1403412e0  mov     rbx, [rsp+2B8h+var_1F8]
0x1403412e8  mov     rax, [rbx]
0x1403412eb  mov     rdi, [rax+30h]
0x1403412ef  mov     [rsp+2B8h+var_1F0], rsi
0x1403412f7  lea     rdx, ?sc_modelSettingsObjectName@SignalState@@2QEB_WEB; wchar_t const * const SignalState::sc_modelSettingsObjectName
0x1403412fe  lea     rcx, [rsp+2B8h+var_1D0]
0x140341306  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x14034130b  nop
0x14034130c  lea     r8, [rsp+2B8h+var_1F0]
0x140341314  mov     rdx, [rax+18h]
0x140341318  mov     rcx, rbx
0x14034131b  mov     rax, rdi
0x14034131e  call    _guard_dispatch_icall
0x140341323  mov     rcx, [rsp+2B8h]; this
0x14034132b  test    eax, eax
0x14034132d  js      loc_1403418B1
0x140341333  mov     [rsp+2B8h+string], rsi
0x14034133b  mov     rbx, [rsp+2B8h+var_1F0]
0x140341343  mov     rax, [rbx]
0x140341346  mov     rdi, [rax+38h]
0x14034134a  xor     ecx, ecx; string
0x14034134c  call    cs:__imp_WindowsDeleteString
0x140341352  mov     [rsp+2B8h+string], rsi
0x14034135a  lea     rdx, [rsp+2B8h+string]
0x140341362  mov     rcx, rbx
0x140341365  mov     rax, rdi
0x140341368  call    _guard_dispatch_icall
0x14034136d  mov     rcx, [rsp+2B8h]; this
0x140341375  test    eax, eax
0x140341377  js      loc_1403418C6
0x14034137d  xor     edx, edx; length
0x14034137f  mov     rcx, [rsp+2B8h+string]; string
0x140341387  call    cs:__imp_WindowsGetStringRawBuffer
0x14034138d  mov     [rsp+2B8h+var_220], rax
0x140341395  lea     rcx, [rsp+2B8h+var_220]
0x14034139d  call    ??$ModelUpdaterStatus@PEB_WAEAY0BC@$$CBD@ModelUpdater@Telemetry@Windows@@SAX$$QEAPEB_WAEAY0BC@$$CBD@Z; Windows::Telemetry::ModelUpdater::ModelUpdaterStatus<wchar_t const *,char const (&)[18]>(wchar_t const * &&,char const (&)[18])
0x1403413a2  mov     rcx, [rsp+2B8h+var_1E8]
0x1403413aa  mov     [rsp+2B8h+var_1E0], rsi
0x1403413b2  mov     rax, [rcx]
0x1403413b5  lea     r8, [rsp+2B8h+var_1E0]
0x1403413bd  lea     rdx, _GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099
0x1403413c4  mov     rax, [rax]
0x1403413c7  call    _guard_dispatch_icall
0x1403413cc  mov     rcx, [rsp+2B8h]; this
0x1403413d4  test    eax, eax
0x1403413d6  js      loc_1403418DB
0x1403413dc  mov     [rsp+2B8h+var_288], 2
0x1403413e4  mov     [rsp+2B8h+var_210], rsi
0x1403413ec  mov     rcx, [rsp+2B8h+var_1E0]
0x1403413f4  mov     rax, [rcx]
0x1403413f7  mov     [rsp+2B8h+var_210], rsi
0x1403413ff  lea     rdx, [rsp+2B8h+var_210]
0x140341407  mov     rax, [rax+30h]
0x14034140b  call    _guard_dispatch_icall
0x140341410  mov     rcx, [rsp+2B8h]; this
0x140341418  test    eax, eax
0x14034141a  js      loc_1403418F0
0x140341420  mov     [rsp+2B8h+var_228], sil
0x140341428  mov     rcx, [rsp+2B8h+var_210]
0x140341430  mov     rax, [rcx]
0x140341433  lea     rdx, [rsp+2B8h+var_228]
0x14034143b  mov     rax, [rax+38h]
0x14034143f  call    _guard_dispatch_icall
0x140341444  mov     rcx, [rsp+2B8h]; this
0x14034144c  test    eax, eax
0x14034144e  js      loc_140341905
0x140341454  xorps   xmm0, xmm0
0x140341457  movups  xmmword ptr [r14], xmm0
0x14034145b  mov     [r14], rsi
0x14034145e  mov     [r14+8], rsi
0x140341462  mov     [r14+10h], rsi
0x140341466  mov     [rsp+2B8h+var_288], 3
0x14034146e  lea     r15, ??_7ModelJsonParsingActivity@ModelUpdater@Telemetry@Windows@@6B@; const Windows::Telemetry::ModelUpdater::ModelJsonParsingActivity::`vftable'
0x140341475  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14034147d  cmp     [rsp+2B8h+var_228], sil
0x140341485  jz      loc_14034178A
0x14034148b  mov     [rsp+2B8h+var_208], rsi
0x140341493  mov     rcx, [rsp+2B8h+var_210]
0x14034149b  mov     rax, [rcx]
0x14034149e  mov     [rsp+2B8h+var_208], rsi
0x1403414a6  lea     rdx, [rsp+2B8h+var_208]
0x1403414ae  mov     rax, [rax+30h]
0x1403414b2  call    _guard_dispatch_icall
0x1403414b7  mov     rcx, [rsp+2B8h]; this
0x1403414bf  test    eax, eax
0x1403414c1  js      loc_14034191A
0x1403414c7  mov     [rsp+2B8h+var_218], rsi
0x1403414cf  mov     rbx, [rsp+2B8h+var_208]
0x1403414d7  mov     rax, [rbx]
0x1403414da  mov     rdi, [rax+30h]
0x1403414de  xor     ecx, ecx; string
0x1403414e0  call    cs:__imp_WindowsDeleteString
0x1403414e6  mov     [rsp+2B8h+var_218], rsi
0x1403414ee  lea     rdx, [rsp+2B8h+var_218]
0x1403414f6  mov     rcx, rbx
0x1403414f9  mov     rax, rdi
0x1403414fc  call    _guard_dispatch_icall
0x140341501  mov     rcx, [rsp+2B8h]; this
0x140341509  test    eax, eax
0x14034150b  js      loc_14034192F
0x140341511  mov     [rsp+2B8h+var_220], rsi
0x140341519  mov     rcx, [rsp+2B8h+var_208]
0x140341521  mov     rax, [rcx]
0x140341524  mov     [rsp+2B8h+var_220], rsi
0x14034152c  lea     rdx, [rsp+2B8h+var_220]
0x140341534  mov     rax, [rax+38h]
0x140341538  call    _guard_dispatch_icall
0x14034153d  mov     rcx, [rsp+2B8h]; this
0x140341545  test    eax, eax
0x140341547  js      loc_140341944
0x14034154d  xorps   xmm0, xmm0
0x140341550  movups  xmmword ptr [rsp+2B8h+var_1D0], xmm0
0x140341558  movdqu  xmmword ptr [rsp+0F8h], xmm6
0x140341561  mov     word ptr [rsp+2B8h+var_1D0], si
0x140341569  xor     edx, edx; Val
0x14034156b  mov     r8d, 148h; Size
0x140341571  lea     rcx, [rsp+2B8h+var_1A8]; void *
0x140341579  call    memset
0x14034157e  xor     edx, edx; length
0x140341580  mov     rcx, [rsp+2B8h+var_218]; string
0x140341588  call    cs:__imp_WindowsGetStringRawBuffer
0x14034158e  mov     rbx, rax
0x140341591  lea     rdx, aModeljsonparsi; "ModelJsonParsingActivity"
0x140341598  lea     rcx, [rsp+2B8h+var_1A8]
0x1403415a0  call    ??0?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1403415a5  mov     [rsp+2B8h+var_1A8], r15
0x1403415ad  mov     rdx, rbx; wchar_t *
0x1403415b0  lea     rcx, [rsp+2B8h+var_1A8]; this
0x1403415b8  call    ?StartActivity@ModelJsonParsingActivity@ModelUpdater@Telemetry@Windows@@QEAAXPEB_W@Z; Windows::Telemetry::ModelUpdater::ModelJsonParsingActivity::StartActivity(wchar_t const *)
0x1403415bd  nop
0x1403415be  xor     edx, edx; length
0x1403415c0  mov     rcx, [rsp+2B8h+var_218]; string
0x1403415c8  call    cs:__imp_WindowsGetStringRawBuffer
0x1403415ce  mov     rcx, rax
0x1403415d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1403415d5  inc     rax
0x1403415d8  cmp     [rcx+rax*2], si
0x1403415dc  jnz     short loc_1403415D5
0x1403415de  mov     [rsp+2B8h+var_258], rcx
0x1403415e3  mov     [rsp+2B8h+var_250], rax
0x1403415e8  movaps  xmm0, xmmword ptr [r12]
0x1403415ed  movdqa  [rsp+2B8h+var_248], xmm0
0x1403415f3  mov     qword ptr [rsp+2B8h+var_298], r13
0x1403415f8  lea     r9, [rsp+2B8h+var_258]
0x1403415fd  lea     r8, [rsp+2B8h+var_248]
0x140341602  lea     rdx, [rsp+2B8h+var_220]
0x14034160a  lea     rcx, [rsp+2B8h+var_238]
0x140341612  call    ?ParseJsonValueIntoUpdate@SignalUpdater@@CA?AV?$shared_ptr@VUpdate@@@std@@AEBV?$com_ptr_t@UIJsonValue@Json@Data@Windows@ABI@@Uerr_exception_policy@wil@@@wil@@V?$basic_zstring_view@_W@5@1AEAVUpdateDatabase@@@Z; SignalUpdater::ParseJsonValueIntoUpdate(wil::com_ptr_t<ABI::Windows::Data::Json::IJsonValue,wil::err_exception_policy> const &,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,UpdateDatabase &)
0x140341617  mov     r8, rax
0x14034161a  mov     rdx, [r14+8]
0x14034161e  cmp     rdx, [r14+10h]
0x140341622  jz      short loc_140341647
0x140341624  mov     [rdx], rsi
0x140341627  mov     [rdx+8], rsi
0x14034162b  mov     rax, [rax]
0x14034162e  mov     [rdx], rax
0x140341631  mov     rax, [r8+8]
0x140341635  mov     [rdx+8], rax
0x140341639  mov     [r8], rsi
0x14034163c  mov     [r8+8], rsi
0x140341640  add     qword ptr [r14+8], 10h
0x140341645  jmp     short loc_140341650
0x140341647  mov     rcx, r14
0x14034164a  call    ??$_Emplace_reallocate@V?$shared_ptr@VCurrentVersionUpdate@WU@Windows@@@std@@@?$vector@V?$shared_ptr@VUpdate@@@std@@V?$allocator@V?$shared_ptr@VUpdate@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VUpdate@@@1@QEAV21@$$QEAV?$shared_ptr@VCurrentVersionUpdate@WU@Windows@@@1@@Z; std::vector<std::shared_ptr<Update>>::_Emplace_reallocate<std::shared_ptr<Windows::WU::CurrentVersionUpdate>>(std::shared_ptr<Update> * const,std::shared_ptr<Windows::WU::CurrentVersionUpdate> &&)
0x14034164f  nop
0x140341650  mov     rbx, [rsp+2B8h+var_230]
0x140341658  test    rbx, rbx
0x14034165b  jz      short loc_140341695
0x14034165d  or      eax, 0FFFFFFFFh
0x140341660  lock xadd [rbx+8], eax
0x140341665  cmp     eax, 1
0x140341668  jnz     short loc_140341695
0x14034166a  mov     rax, [rbx]
0x14034166d  mov     rcx, rbx
0x140341670  mov     rax, [rax]
0x140341673  call    _guard_dispatch_icall
0x140341678  or      eax, 0FFFFFFFFh
0x14034167b  lock xadd [rbx+0Ch], eax
0x140341680  cmp     eax, 1
0x140341683  jnz     short loc_140341695
0x140341685  mov     rax, [rbx]
0x140341688  mov     rcx, rbx
0x14034168b  mov     rax, [rax+8]
0x14034168f  call    _guard_dispatch_icall
0x140341694  nop
0x140341695  jmp     short loc_1403416B7
0x140341697  xor     esi, esi
0x140341699  lea     r15, ??_7ModelJsonParsingActivity@ModelUpdater@Telemetry@Windows@@6B@; const Windows::Telemetry::ModelUpdater::ModelJsonParsingActivity::`vftable'
0x1403416a0  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1403416a8  mov     r14, [rsp+2B8h+var_280]
0x1403416ad  mov     r12, [rsp+2B8h+var_278]
0x1403416b2  mov     r13, [rsp+2B8h+var_268]
0x1403416b7  lea     rdx, [rsp+2B8h+var_1D0]
0x1403416bf  cmp     [rsp+2B8h+var_1B8], 7
0x1403416c8  cmova   rdx, [rsp+2B8h+var_1D0]; wchar_t *
0x1403416d1  lea     rcx, [rsp+2B8h+var_1A8]; this
0x1403416d9  call    ?Stop@ModelJsonParsingActivity@ModelUpdater@Telemetry@Windows@@QEAAXPEB_W@Z; Windows::Telemetry::ModelUpdater::ModelJsonParsingActivity::Stop(wchar_t const *)
0x1403416de  mov     rcx, [rsp+2B8h+var_210]
0x1403416e6  mov     rax, [rcx]
0x1403416e9  lea     rdx, [rsp+2B8h+var_228]
0x1403416f1  mov     rax, [rax+40h]
0x1403416f5  call    _guard_dispatch_icall
0x1403416fa  mov     rcx, [rsp+2B8h]; this
0x140341702  test    eax, eax
0x140341704  js      loc_140341959
0x14034170a  mov     [rsp+2B8h+var_1A8], r15
0x140341712  lea     rcx, [rsp+2B8h+var_1A8]
0x14034171a  call    ?Destroy@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14034171f  lea     rcx, [rsp+2B8h+var_1A8]
0x140341727  call    ??1?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x14034172c  nop
0x14034172d  lea     rcx, [rsp+2B8h+var_1D0]
0x140341735  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14034173a  nop
0x14034173b  mov     rcx, [rsp+2B8h+var_220]
0x140341743  test    rcx, rcx
0x140341746  jz      short loc_140341755
0x140341748  mov     rax, [rcx]
0x14034174b  mov     rax, [rax+10h]
0x14034174f  call    _guard_dispatch_icall
0x140341754  nop
0x140341755  mov     rcx, [rsp+2B8h+var_218]; string
0x14034175d  call    cs:__imp_WindowsDeleteString
0x140341763  mov     [rsp+2B8h+var_218], rsi
  ... truncated ...
```
