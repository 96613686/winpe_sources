# Windows::System::Diagnostics::DiagnosticInvoker::RunDiagnosticActionFromStringAsync(HSTRING__ *,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState> * *)

- ea: `0x18000e070`
- end: `0x18000e467`
- name: `?RunDiagnosticActionFromStringAsync@DiagnosticInvoker@Diagnostics@System@Windows@@UEAAJPEAUHSTRING__@@PEAPEAU?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@4@@Z`
- size: `1015`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000108c`
- `0x1800016a8`
- `0x180001e20`
- `0x18000d4f0`
- `0x18000e070`
- `0x18000f718`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e0ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e0ca`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000e108`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000e108`

## string_xrefs

- `0x18000e0c3`: `Windows.Data.Json.JsonObject`
- `0x18000e129`: `DiagnosticInvoker::RunDiagnosticActionFromStringAsync::Activating JsonObjectStatics`
- `0x18000e1e6`: `DiagnosticInvoker::RunDiagnosticActionFromStringAsync::Creating JsonObject`

## pseudocode

```c
__int64 __fastcall Windows::System::Diagnostics::DiagnosticInvoker::RunDiagnosticActionFromStringAsync(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  int ActivationFactory; // eax
  int v10; // r8d
  int v11; // r9d
  int v12; // ebx
  const char *v13; // rdx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64, __int64 *); // rsi
  __int64 v16; // rcx
  int v17; // ecx
  int v18; // ecx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v22; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+74h] [rbp-8Ch] BYREF
  const char *v24; // [rsp+78h] [rbp-88h] BYREF
  const char *v25; // [rsp+80h] [rbp-80h] BYREF
  const char *v26; // [rsp+88h] [rbp-78h] BYREF
  const char *v27; // [rsp+90h] [rbp-70h] BYREF
  __int64 v28; // [rsp+98h] [rbp-68h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-60h] BYREF
  __int128 *v30; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING_HEADER *p_hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v32; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING string; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v35; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v36; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v37; // [rsp+100h] [rbp+0h] BYREF

  v29 = 0;
  v28 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    JUMPOUT(0x18000E466LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v29);
  v12 = ActivationFactory;
  v13 = "Windows::System::Diagnostics::DiagnosticInvoker::RunDiagnosticActionFromStringAsync";
  if ( (unsigned int)dword_18001D000 > 5 )
  {
    v24 = "DiagnosticInvoker::RunDiagnosticActionFromStringAsync::Activating JsonObjectStatics";
    v22 = ActivationFactory;
    v23 = 316;
    v25 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
    v26 = "Windows::System::Diagnostics::DiagnosticInvoker::RunDiagnosticActionFromStringAsync";
    v27 = (const char *)(a1 + 56);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_18001D000,
      (unsigned int)&byte_180018997,
      v10,
      v11,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v24);
  }
  if ( v12 < 0 )
    goto LABEL_15;
  v14 = v29;
  v15 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v29 + 48LL);
  v16 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64, const char *))(*(_QWORD *)v16 + 16LL))(v16, v13);
  }
  v12 = v15(v14, a2, &v28);
  if ( (unsigned int)dword_18001D000 > 5 )
  {
    v27 = "DiagnosticInvoker::RunDiagnosticActionFromStringAsync::Creating JsonObject";
    v23 = v12;
    v22 = 321;
    v26 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
    v25 = "Windows::System::Diagnostics::DiagnosticInvoker::RunDiagnosticActionFromStringAsync";
    v24 = (const char *)(a1 + 56);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v17,
      (unsigned int)byte_180018931,
      v10,
      v11,
      (__int64)&v24,
      (__int64)&v25,
      (__int64)&v26,
      (__int64)&v22,
      (__int64)&v23,
      (__int64)&v27);
  }
  if ( v12 < 0 )
    goto LABEL_15;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)(a1 - 16) + 48LL))(a1 - 16, v28, a3);
  if ( (unsigned int)dword_18001D000 > 5 )
  {
    v27 = "DiagnosticInvoker::RunDiagnosticActionFromStringAsync::Calling RunDiagnosticActionAsync";
    v23 = v12;
    v22 = 327;
    v26 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
    v25 = "Windows::System::Diagnostics::DiagnosticInvoker::RunDiagnosticActionFromStringAsync";
    v24 = (const char *)(a1 + 56);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v18,
      (unsigned int)byte_1800188CB,
      v10,
      v11,
      (__int64)&v24,
      (__int64)&v25,
      (__int64)&v26,
      (__int64)&v22,
      (__int64)&v23,
      (__int64)&v27);
  }
  if ( v12 < 0 )
  {
LABEL_15:
    if ( (unsigned int)dword_18001D000 > 5
      && (qword_18001D010 & 0x800000000000LL) != 0
      && (qword_18001D018 & 0x800000000000LL) == qword_18001D018 )
    {
      v23 = v12;
      v27 = 0;
      v22 = -2147467259;
      v26 = 0;
      v35 = 0;
      v25 = (const char *)&v35;
      v36 = 0;
      v24 = (const char *)&v36;
      v37 = 0;
      v30 = &v37;
      *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0;
      p_hstringHeader = &hstringHeader;
      v32 = a1 + 56;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        qword_18001D018,
        (unsigned int)&word_180018826,
        v10,
        v11,
        (__int64)&v32,
        (__int64)&p_hstringHeader,
        (__int64)&v30,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v26,
        (__int64)&v22,
        (__int64)&v27,
        (__int64)&v23);
    }
    DiagInvokerEventProvider::LogErrorEvent(v12);
  }
  v19 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v20 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000e070  push    rbp
0x18000e072  push    rbx
0x18000e073  push    rsi
0x18000e074  push    rdi
0x18000e075  push    r13
0x18000e077  push    r14
0x18000e079  push    r15
0x18000e07b  lea     rbp, [rsp-20h]
0x18000e080  sub     rsp, 120h
0x18000e087  mov     rax, cs:__security_cookie
0x18000e08e  xor     rax, rsp
0x18000e091  mov     [rbp+50h+var_40], rax
0x18000e095  mov     r15, r8
0x18000e098  mov     r14, rdx
0x18000e09b  mov     rdi, rcx
0x18000e09e  mov     [rbp+50h+var_B0], 0
0x18000e0a6  mov     [rbp+50h+var_B8], 0
0x18000e0ae  mov     [rbp+50h+string], 0
0x18000e0b6  lea     r9, [rbp+50h+string]; string
0x18000e0ba  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x18000e0be  mov     edx, 1Ch; length
0x18000e0c3  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18000e0ca  call    cs:__imp_WindowsCreateStringReference
0x18000e0d0  test    eax, eax
0x18000e0d2  js      loc_18000E45F
0x18000e0d8  mov     rbx, [rbp+50h+string]
0x18000e0dc  mov     rcx, [rbp+50h+var_B0]
0x18000e0e0  test    rcx, rcx
0x18000e0e3  jz      short loc_18000E0FA
0x18000e0e5  mov     [rbp+50h+var_B0], 0
0x18000e0ed  mov     rax, [rcx]
0x18000e0f0  mov     rax, [rax+10h]
0x18000e0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0f9  nop
0x18000e0fa  lea     r8, [rbp+50h+var_B0]
0x18000e0fe  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18000e105  mov     rcx, rbx
0x18000e108  call    cs:__imp_RoGetActivationFactory
0x18000e10e  mov     ebx, eax
0x18000e110  mov     ecx, cs:dword_18001D000
0x18000e116  lea     r13, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\winrt\\dia"...
0x18000e11d  lea     rdx, aWindowsSystemD_2; "Windows::System::Diagnostics::Diagnosti"...
0x18000e124  cmp     ecx, 5
0x18000e127  jbe     short loc_18000E196
0x18000e129  lea     rax, aDiagnosticinvo_5; "DiagnosticInvoker::RunDiagnosticActionF"...
0x18000e130  mov     [rsp+150h+var_D8], rax
0x18000e135  mov     [rsp+150h+var_E0], ebx
0x18000e139  mov     [rsp+150h+var_DC], 13Ch
0x18000e141  mov     [rbp+50h+var_D0], r13
0x18000e145  mov     [rbp+50h+var_C8], rdx
0x18000e149  lea     rax, [rdi+38h]
0x18000e14d  mov     [rbp+50h+var_C0], rax
0x18000e151  lea     rax, [rsp+150h+var_D8]
0x18000e156  mov     [rsp+150h+var_108], rax
0x18000e15b  lea     rax, [rsp+150h+var_E0]
0x18000e160  mov     [rsp+150h+var_110], rax
0x18000e165  lea     rax, [rsp+150h+var_DC]
0x18000e16a  mov     [rsp+150h+var_118], rax
0x18000e16f  lea     rax, [rbp+50h+var_D0]
0x18000e173  mov     [rsp+150h+var_120], rax
0x18000e178  lea     rax, [rbp+50h+var_C8]
0x18000e17c  mov     [rsp+150h+var_128], rax
0x18000e181  lea     rax, [rbp+50h+var_C0]
0x18000e185  mov     [rsp+150h+var_130], rax
0x18000e18a  lea     rdx, byte_180018997
0x18000e191  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000e196  test    ebx, ebx
0x18000e198  js      loc_18000E304
0x18000e19e  mov     rbx, [rbp+50h+var_B0]
0x18000e1a2  mov     rax, [rbx]
0x18000e1a5  mov     rsi, [rax+30h]
0x18000e1a9  mov     rcx, [rbp+50h+var_B8]
0x18000e1ad  test    rcx, rcx
0x18000e1b0  jz      short loc_18000E1C7
0x18000e1b2  mov     [rbp+50h+var_B8], 0
0x18000e1ba  mov     r8, [rcx]
0x18000e1bd  mov     rax, [r8+10h]
0x18000e1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1c6  nop
0x18000e1c7  lea     r8, [rbp+50h+var_B8]
0x18000e1cb  mov     rdx, r14
0x18000e1ce  mov     rcx, rbx
0x18000e1d1  mov     rax, rsi
0x18000e1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1d9  mov     ebx, eax
0x18000e1db  mov     eax, cs:dword_18001D000
0x18000e1e1  cmp     eax, 5
0x18000e1e4  jbe     short loc_18000E25C
0x18000e1e6  lea     rax, aDiagnosticinvo_11; "DiagnosticInvoker::RunDiagnosticActionF"...
0x18000e1ed  mov     [rbp+50h+var_C0], rax
0x18000e1f1  mov     [rsp+150h+var_DC], ebx
0x18000e1f5  mov     [rsp+150h+var_E0], 141h
0x18000e1fd  mov     [rbp+50h+var_C8], r13
0x18000e201  lea     rsi, aWindowsSystemD_2; "Windows::System::Diagnostics::Diagnosti"...
0x18000e208  mov     [rbp+50h+var_D0], rsi
0x18000e20c  lea     rax, [rdi+38h]
0x18000e210  mov     [rsp+150h+var_D8], rax
0x18000e215  lea     rax, [rbp+50h+var_C0]
0x18000e219  mov     [rsp+150h+var_108], rax
0x18000e21e  lea     rax, [rsp+150h+var_DC]
0x18000e223  mov     [rsp+150h+var_110], rax
0x18000e228  lea     rax, [rsp+150h+var_E0]
0x18000e22d  mov     [rsp+150h+var_118], rax
0x18000e232  lea     rax, [rbp+50h+var_C8]
0x18000e236  mov     [rsp+150h+var_120], rax
0x18000e23b  lea     rax, [rbp+50h+var_D0]
0x18000e23f  mov     [rsp+150h+var_128], rax
0x18000e244  lea     rax, [rsp+150h+var_D8]
0x18000e249  mov     [rsp+150h+var_130], rax
0x18000e24e  lea     rdx, byte_180018931
0x18000e255  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000e25a  jmp     short loc_18000E263
0x18000e25c  lea     rsi, aWindowsSystemD_2; "Windows::System::Diagnostics::Diagnosti"...
0x18000e263  test    ebx, ebx
0x18000e265  js      loc_18000E304
0x18000e26b  lea     rcx, [rdi-10h]
0x18000e26f  mov     rax, [rcx]
0x18000e272  mov     r8, r15
0x18000e275  mov     rdx, [rbp+50h+var_B8]
0x18000e279  mov     rax, [rax+30h]
0x18000e27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e282  mov     ebx, eax
0x18000e284  mov     eax, cs:dword_18001D000
0x18000e28a  cmp     eax, 5
0x18000e28d  jbe     short loc_18000E2FC
0x18000e28f  lea     rax, aDiagnosticinvo_17; "DiagnosticInvoker::RunDiagnosticActionF"...
0x18000e296  mov     [rbp+50h+var_C0], rax
0x18000e29a  mov     [rsp+150h+var_DC], ebx
0x18000e29e  mov     [rsp+150h+var_E0], 147h
0x18000e2a6  mov     [rbp+50h+var_C8], r13
0x18000e2aa  mov     [rbp+50h+var_D0], rsi
0x18000e2ae  lea     rax, [rdi+38h]
0x18000e2b2  mov     [rsp+150h+var_D8], rax
0x18000e2b7  lea     rax, [rbp+50h+var_C0]
0x18000e2bb  mov     [rsp+150h+var_108], rax
0x18000e2c0  lea     rax, [rsp+150h+var_DC]
0x18000e2c5  mov     [rsp+150h+var_110], rax
0x18000e2ca  lea     rax, [rsp+150h+var_E0]
0x18000e2cf  mov     [rsp+150h+var_118], rax
0x18000e2d4  lea     rax, [rbp+50h+var_C8]
0x18000e2d8  mov     [rsp+150h+var_120], rax
0x18000e2dd  lea     rax, [rbp+50h+var_D0]
0x18000e2e1  mov     [rsp+150h+var_128], rax
0x18000e2e6  lea     rax, [rsp+150h+var_D8]
0x18000e2eb  mov     [rsp+150h+var_130], rax
0x18000e2f0  lea     rdx, byte_1800188CB
0x18000e2f7  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000e2fc  test    ebx, ebx
0x18000e2fe  jns     loc_18000E403
0x18000e304  mov     eax, cs:dword_18001D000
0x18000e30a  cmp     eax, 5
0x18000e30d  jbe     loc_18000E3FB
0x18000e313  mov     rcx, cs:qword_18001D018
0x18000e31a  mov     rax, cs:qword_18001D010
0x18000e321  mov     rdx, 800000000000h
0x18000e32b  test    rdx, rax
0x18000e32e  jz      loc_18000E3FB
0x18000e334  mov     rax, rcx
0x18000e337  and     rax, rdx
0x18000e33a  cmp     rax, rcx
0x18000e33d  jnz     loc_18000E3FB
0x18000e343  mov     [rsp+150h+var_DC], ebx
0x18000e347  mov     [rbp+50h+var_C0], 0
0x18000e34f  mov     [rsp+150h+var_E0], 80004005h
0x18000e357  mov     [rbp+50h+var_C8], 0
0x18000e35f  xorps   xmm0, xmm0
0x18000e362  movups  [rbp+50h+var_70], xmm0
0x18000e366  lea     rax, [rbp+50h+var_70]
0x18000e36a  mov     [rbp+50h+var_D0], rax
0x18000e36e  movups  [rbp+50h+var_60], xmm0
0x18000e372  lea     rax, [rbp+50h+var_60]
0x18000e376  mov     [rsp+150h+var_D8], rax
0x18000e37b  movups  [rbp+50h+var_50], xmm0
0x18000e37f  lea     rax, [rbp+50h+var_50]
0x18000e383  mov     [rbp+50h+var_A8], rax
0x18000e387  movups  xmmword ptr [rbp+50h+hstringHeader.Reserved], xmm0
0x18000e38b  lea     rax, [rbp+50h+hstringHeader]
0x18000e38f  mov     [rbp+50h+var_A0], rax
0x18000e393  lea     rax, [rdi+38h]
0x18000e397  mov     [rbp+50h+var_98], rax
0x18000e39b  lea     rax, [rsp+150h+var_DC]
0x18000e3a0  mov     [rsp+150h+var_F0], rax
0x18000e3a5  lea     rax, [rbp+50h+var_C0]
0x18000e3a9  mov     [rsp+150h+var_F8], rax
0x18000e3ae  lea     rax, [rsp+150h+var_E0]
0x18000e3b3  mov     [rsp+150h+var_100], rax
0x18000e3b8  lea     rax, [rbp+50h+var_C8]
0x18000e3bc  mov     [rsp+150h+var_108], rax
0x18000e3c1  lea     rax, [rbp+50h+var_D0]
0x18000e3c5  mov     [rsp+150h+var_110], rax
0x18000e3ca  lea     rax, [rsp+150h+var_D8]
0x18000e3cf  mov     [rsp+150h+var_118], rax
0x18000e3d4  lea     rax, [rbp+50h+var_A8]
0x18000e3d8  mov     [rsp+150h+var_120], rax
0x18000e3dd  lea     rax, [rbp+50h+var_A0]
0x18000e3e1  mov     [rsp+150h+var_128], rax
0x18000e3e6  lea     rax, [rbp+50h+var_98]
0x18000e3ea  mov     [rsp+150h+var_130], rax
0x18000e3ef  lea     rdx, word_180018826
0x18000e3f6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U2@U2@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@444AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e3fb  mov     ecx, ebx; int
0x18000e3fd  call    ?LogErrorEvent@DiagInvokerEventProvider@@SAXJ@Z; DiagInvokerEventProvider::LogErrorEvent(long)
0x18000e402  nop
0x18000e403  mov     rcx, [rbp+50h+var_B8]
0x18000e407  test    rcx, rcx
0x18000e40a  jz      short loc_18000E421
0x18000e40c  mov     [rbp+50h+var_B8], 0
0x18000e414  mov     rax, [rcx]
0x18000e417  mov     rax, [rax+10h]
0x18000e41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e420  nop
0x18000e421  mov     rcx, [rbp+50h+var_B0]
0x18000e425  test    rcx, rcx
0x18000e428  jz      short loc_18000E43F
0x18000e42a  mov     [rbp+50h+var_B0], 0
0x18000e432  mov     rax, [rcx]
0x18000e435  mov     rax, [rax+10h]
0x18000e439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e43e  nop
0x18000e43f  mov     eax, ebx
0x18000e441  mov     rcx, [rbp+50h+var_40]
0x18000e445  xor     rcx, rsp; StackCookie
0x18000e448  call    __security_check_cookie
0x18000e44d  add     rsp, 120h
0x18000e454  pop     r15
0x18000e456  pop     r14
0x18000e458  pop     r13
0x18000e45a  pop     rdi
0x18000e45b  pop     rsi
0x18000e45c  pop     rbx
0x18000e45d  pop     rbp
0x18000e45e  retn
0x18000e45f  mov     ecx, eax; this
0x18000e461  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
