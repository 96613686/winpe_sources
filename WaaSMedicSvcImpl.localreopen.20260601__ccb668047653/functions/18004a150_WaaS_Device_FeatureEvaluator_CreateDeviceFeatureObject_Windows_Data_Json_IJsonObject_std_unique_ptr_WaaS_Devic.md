# WaaS::Device::FeatureEvaluator::CreateDeviceFeatureObject(Windows::Data::Json::IJsonObject *,std::unique_ptr<WaaS::Device::DeviceFeature,std::default_delete<WaaS::Device::DeviceFeature>> &)

- ea: `0x18004a150`
- end: `0x18004a5bd`
- name: `?CreateDeviceFeatureObject@FeatureEvaluator@Device@WaaS@@AEAAJPEAUIJsonObject@Json@Data@Windows@@AEAV?$unique_ptr@VDeviceFeature@Device@WaaS@@U?$default_delete@VDeviceFeature@Device@WaaS@@@std@@@std@@@Z`
- size: `1133`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180054ebc`

## callees

- `0x1800050a0`
- `0x1800050c4`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000bbd4`
- `0x180024e48`
- `0x18004987c`
- `0x180049ce4`
- `0x18004a150`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a39e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a454`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a39e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a454`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a1b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a23c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a2b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a1b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a23c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a2b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a196`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a21a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a50f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a56f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a57d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a196`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a21a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a50f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a56f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a57d`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WaaS::Device::FeatureEvaluator::CreateDeviceFeatureObject(
        __int64 a1,
        __int64 *a2,
        void (__fastcall ****a3)(_QWORD, __int64))
{
  __int64 v6; // rbx
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rbx
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  int v16; // eax
  __int64 v17; // rbx
  HRESULT v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  int v21; // eax
  int v22; // eax
  int v23; // edi
  _QWORD *v24; // rdi
  PCWSTR StringRawBuffer; // rax
  __int64 v26; // rbx
  __int64 v27; // r8
  int v28; // esi
  PCWSTR v29; // rax
  void (__fastcall ***v31)(_QWORD, __int64); // rcx
  void (__fastcall ***v32)(_QWORD, __int64); // rcx
  __int64 v33; // [rsp+20h] [rbp-50h] BYREF
  HSTRING v34; // [rsp+28h] [rbp-48h] BYREF
  void (__fastcall ***v35)(_QWORD, __int64); // [rsp+30h] [rbp-40h] BYREF
  HSTRING v36; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v37; // [rsp+40h] [rbp-30h]
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v36 = 0;
  v34 = 0;
  v33 = 0;
  v35 = 0;
  v37 = 0;
  v6 = *a2;
  WindowsDeleteString(0);
  v36 = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"Version", 7u, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    __debugbreak();
  }
  v10 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING *))(v6 + 80))(a2, string, &v36);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x227,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v10,
      v33);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    goto LABEL_38;
  }
  v12 = *a2;
  WindowsDeleteString(v34);
  v34 = 0;
  string = 0;
  v13 = WindowsCreateStringReference(L"SchemaVersion", 0xDu, &hstringHeader, &string);
  if ( v13 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    JUMPOUT(0x18004A5BCLL);
  }
  v16 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING *))(v12 + 80))(a2, string, &v34);
  v11 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x228,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v16,
      v33);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    goto LABEL_38;
  }
  v17 = *a2;
  string = 0;
  v18 = WindowsCreateStringReference(L"Detect", 6u, &hstringHeader, &string);
  if ( v18 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
    __debugbreak();
  }
  v21 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v17 + 64))(a2, string, &v33);
  v11 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x229,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v21,
      v33);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    goto LABEL_38;
  }
  v22 = WaaS::Device::FeatureEvaluator::CreateDetectFeatureObject(a1, v33, &v35);
  v23 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22A,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v22,
      v33);
    if ( v35 )
      (**v35)(v35, 1);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v11 = v23;
    goto LABEL_38;
  }
  v24 = operator new(0x18u);
  *v24 = &WaaS::Device::DeviceFeature::`vftable';
  v24[2] = 0;
  v37 = v24;
  StringRawBuffer = WindowsGetStringRawBuffer(v36, 0);
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  string = 0;
  v26 = -1;
  v27 = -1;
  do
    ++v27;
  while ( StringRawBuffer[v27] );
  std::wstring::_Construct<1,unsigned short const *>(&hstringHeader, StringRawBuffer, v27);
  v28 = WaaS::Device::ConvertToUInt32((wchar_t *)&hstringHeader);
  std::wstring::~wstring(&hstringHeader);
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v28,
      v33);
    (*(void (__fastcall **)(_QWORD *, __int64))*v24)(v24, 1);
    if ( v35 )
      (**v35)(v35, 1);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
LABEL_37:
    v11 = v28;
LABEL_38:
    WindowsDeleteString(v34);
    v34 = 0;
    WindowsDeleteString(v36);
    return v11;
  }
  v29 = WindowsGetStringRawBuffer(v34, 0);
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  string = 0;
  do
    ++v26;
  while ( v29[v26] );
  std::wstring::_Construct<1,unsigned short const *>(&hstringHeader, v29, v26);
  v28 = WaaS::Device::ConvertToUInt32((wchar_t *)&hstringHeader);
  std::wstring::~wstring(&hstringHeader);
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x230,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v28,
      v33);
    (*(void (__fastcall **)(_QWORD *, __int64))*v24)(v24, 1);
    if ( v35 )
      (**v35)(v35, 1);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    goto LABEL_37;
  }
  v31 = (void (__fastcall ***)(_QWORD, __int64))v24[2];
  v24[2] = v35;
  if ( v31 )
    (**v31)(v31, 1);
  v32 = *a3;
  *a3 = (void (__fastcall ***)(_QWORD, __int64))v24;
  if ( v32 )
    (**v32)(v32, 1);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  WindowsDeleteString(v34);
  v34 = 0;
  WindowsDeleteString(v36);
  return 0;
}

```

## disassembly

```asm
0x18004a150  mov     [rsp-28h+arg_18], rbx
0x18004a155  push    rbp
0x18004a156  push    rsi
0x18004a157  push    rdi
0x18004a158  push    r14
0x18004a15a  push    r15
0x18004a15c  mov     rbp, rsp
0x18004a15f  sub     rsp, 70h
0x18004a163  mov     rax, cs:__security_cookie
0x18004a16a  xor     rax, rsp
0x18004a16d  mov     [rbp+var_8], rax
0x18004a171  mov     r14, r8
0x18004a174  mov     rdi, rdx
0x18004a177  mov     rsi, rcx
0x18004a17a  xor     r15d, r15d
0x18004a17d  mov     [rbp+var_38], r15
0x18004a181  mov     [rbp+var_48], r15
0x18004a185  mov     [rbp+var_50], r15
0x18004a189  mov     [rbp+var_40], r15
0x18004a18d  mov     [rbp+var_30], r15
0x18004a191  mov     rbx, [rdx]
0x18004a194  xor     ecx, ecx; string
0x18004a196  call    cs:__imp_WindowsDeleteString
0x18004a19c  mov     [rbp+var_38], r15
0x18004a1a0  mov     [rbp+string], r15
0x18004a1a4  lea     r9, [rbp+string]; string
0x18004a1a8  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004a1ac  lea     edx, [r15+7]; length
0x18004a1b0  lea     rcx, aVersion; "Version"
0x18004a1b7  call    cs:__imp_WindowsCreateStringReference
0x18004a1bd  test    eax, eax
0x18004a1bf  js      loc_18004A5AD
0x18004a1c5  lea     r8, [rbp+var_38]
0x18004a1c9  mov     rdx, [rbp+string]
0x18004a1cd  mov     rcx, rdi
0x18004a1d0  mov     rax, [rbx+50h]
0x18004a1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1d9  mov     ebx, eax
0x18004a1db  test    eax, eax
0x18004a1dd  jns     short loc_18004A213
0x18004a1df  mov     rcx, [rbp+28h]; this
0x18004a1e3  mov     r9d, eax; char *
0x18004a1e6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18004a1ed  mov     edx, 227h; void *
0x18004a1f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a1f7  nop
0x18004a1f8  mov     rcx, [rbp+var_50]
0x18004a1fc  test    rcx, rcx
0x18004a1ff  jz      short loc_18004A20E
0x18004a201  mov     rax, [rcx]
0x18004a204  mov     rax, [rax+10h]
0x18004a208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a20d  nop
0x18004a20e  jmp     loc_18004A4FD
0x18004a213  mov     rbx, [rdi]
0x18004a216  mov     rcx, [rbp+var_48]; string
0x18004a21a  call    cs:__imp_WindowsDeleteString
0x18004a220  mov     [rbp+var_48], r15
0x18004a224  mov     [rbp+string], r15
0x18004a228  lea     r9, [rbp+string]; string
0x18004a22c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004a230  mov     edx, 0Dh; length
0x18004a235  lea     rcx, aSchemaversion; "SchemaVersion"
0x18004a23c  call    cs:__imp_WindowsCreateStringReference
0x18004a242  test    eax, eax
0x18004a244  js      loc_18004A5B5
0x18004a24a  lea     r8, [rbp+var_48]
0x18004a24e  mov     rdx, [rbp+string]
0x18004a252  mov     rcx, rdi
0x18004a255  mov     rax, [rbx+50h]
0x18004a259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a25e  mov     ebx, eax
0x18004a260  test    eax, eax
0x18004a262  jns     short loc_18004A298
0x18004a264  mov     rcx, [rbp+28h]; this
0x18004a268  mov     r9d, eax; char *
0x18004a26b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18004a272  mov     edx, 228h; void *
0x18004a277  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a27c  nop
0x18004a27d  mov     rcx, [rbp+var_50]
0x18004a281  test    rcx, rcx
0x18004a284  jz      short loc_18004A293
0x18004a286  mov     rax, [rcx]
0x18004a289  mov     rax, [rax+10h]
0x18004a28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a292  nop
0x18004a293  jmp     loc_18004A4FD
0x18004a298  mov     rbx, [rdi]
0x18004a29b  mov     [rbp+string], r15
0x18004a29f  lea     r9, [rbp+string]; string
0x18004a2a3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004a2a7  mov     edx, 6; length
0x18004a2ac  lea     rcx, aDetect; "Detect"
0x18004a2b3  call    cs:__imp_WindowsCreateStringReference
0x18004a2b9  test    eax, eax
0x18004a2bb  js      loc_18004A5A5
0x18004a2c1  lea     r8, [rbp+var_50]
0x18004a2c5  mov     rdx, [rbp+string]
0x18004a2c9  mov     rcx, rdi
0x18004a2cc  mov     rax, [rbx+40h]
0x18004a2d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a2d5  mov     ebx, eax
0x18004a2d7  test    eax, eax
0x18004a2d9  jns     short loc_18004A30F
0x18004a2db  mov     rcx, [rbp+28h]; this
0x18004a2df  mov     r9d, eax; char *
0x18004a2e2  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18004a2e9  mov     edx, 229h; void *
0x18004a2ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a2f3  nop
0x18004a2f4  mov     rcx, [rbp+var_50]
0x18004a2f8  test    rcx, rcx
0x18004a2fb  jz      short loc_18004A30A
0x18004a2fd  mov     rax, [rcx]
0x18004a300  mov     rax, [rax+10h]
0x18004a304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a309  nop
0x18004a30a  jmp     loc_18004A4FD
0x18004a30f  lea     r8, [rbp+var_40]
0x18004a313  mov     rdx, [rbp+var_50]
0x18004a317  mov     rcx, rsi
0x18004a31a  call    ?CreateDetectFeatureObject@FeatureEvaluator@Device@WaaS@@AEAAJPEAUIJsonObject@Json@Data@Windows@@AEAV?$unique_ptr@VDetectFeature@Device@WaaS@@U?$default_delete@VDetectFeature@Device@WaaS@@@std@@@std@@@Z; WaaS::Device::FeatureEvaluator::CreateDetectFeatureObject(Windows::Data::Json::IJsonObject *,std::unique_ptr<WaaS::Device::DetectFeature> &)
0x18004a31f  mov     edi, eax
0x18004a321  test    eax, eax
0x18004a323  jns     short loc_18004A375
0x18004a325  mov     rcx, [rbp+28h]; this
0x18004a329  mov     r9d, eax; char *
0x18004a32c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18004a333  mov     edx, 22Ah; void *
0x18004a338  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a33d  nop
0x18004a33e  mov     rcx, [rbp+var_40]
0x18004a342  test    rcx, rcx
0x18004a345  jz      short loc_18004A358
0x18004a347  mov     rax, [rcx]
0x18004a34a  mov     edx, 1
0x18004a34f  mov     rax, [rax]
0x18004a352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a357  nop
0x18004a358  mov     rcx, [rbp+var_50]
0x18004a35c  test    rcx, rcx
0x18004a35f  jz      short loc_18004A36E
0x18004a361  mov     rax, [rcx]
0x18004a364  mov     rax, [rax+10h]
0x18004a368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a36d  nop
0x18004a36e  mov     ebx, edi
0x18004a370  jmp     loc_18004A4FD
0x18004a375  mov     ecx, 18h; Size
0x18004a37a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004a37f  mov     rdi, rax
0x18004a382  mov     [rbp+var_30], rax
0x18004a386  lea     rax, ??_7DeviceFeature@Device@WaaS@@6B@; const WaaS::Device::DeviceFeature::`vftable'
0x18004a38d  mov     [rdi], rax
0x18004a390  mov     [rdi+10h], r15
0x18004a394  mov     [rbp+var_30], rdi
0x18004a398  xor     edx, edx; length
0x18004a39a  mov     rcx, [rbp+var_38]; string
0x18004a39e  call    cs:__imp_WindowsGetStringRawBuffer
0x18004a3a4  xorps   xmm0, xmm0
0x18004a3a7  movups  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x18004a3ab  mov     qword ptr [rbp+hstringHeader.Reserved+10h], r15
0x18004a3af  mov     [rbp+string], r15
0x18004a3b3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004a3b7  mov     r8, rbx
0x18004a3ba  inc     r8
0x18004a3bd  cmp     [rax+r8*2], r15w
0x18004a3c2  jnz     short loc_18004A3BA
0x18004a3c4  mov     rdx, rax
0x18004a3c7  lea     rcx, [rbp+hstringHeader]
0x18004a3cb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004a3d0  nop
0x18004a3d1  lea     rdx, [rdi+8]
0x18004a3d5  lea     rcx, [rbp+hstringHeader]; String
0x18004a3d9  call    WaaS__Device__ConvertToUInt32
0x18004a3de  mov     esi, eax
0x18004a3e0  lea     rcx, [rbp+hstringHeader]; void *
0x18004a3e4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004a3e9  test    esi, esi
0x18004a3eb  jns     short loc_18004A44E
0x18004a3ed  mov     rcx, [rbp+28h]; this
0x18004a3f1  mov     r9d, esi; char *
0x18004a3f4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18004a3fb  mov     edx, 22Fh; void *
0x18004a400  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a405  nop
0x18004a406  mov     rcx, [rdi]
0x18004a409  mov     rax, [rcx]
0x18004a40c  mov     ebx, 1
0x18004a411  mov     edx, ebx
0x18004a413  mov     rcx, rdi
0x18004a416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a41b  nop
0x18004a41c  mov     rcx, [rbp+var_40]
0x18004a420  test    rcx, rcx
0x18004a423  jz      short loc_18004A433
0x18004a425  mov     rax, [rcx]
0x18004a428  mov     edx, ebx
0x18004a42a  mov     rax, [rax]
0x18004a42d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a432  nop
0x18004a433  mov     rcx, [rbp+var_50]
0x18004a437  test    rcx, rcx
0x18004a43a  jz      short loc_18004A449
0x18004a43c  mov     rax, [rcx]
0x18004a43f  mov     rax, [rax+10h]
0x18004a443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a448  nop
0x18004a449  jmp     loc_18004A4FB
0x18004a44e  xor     edx, edx; length
0x18004a450  mov     rcx, [rbp+var_48]; string
0x18004a454  call    cs:__imp_WindowsGetStringRawBuffer
0x18004a45a  xorps   xmm0, xmm0
0x18004a45d  movups  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x18004a461  mov     qword ptr [rbp+hstringHeader.Reserved+10h], r15
0x18004a465  mov     [rbp+string], r15
0x18004a469  inc     rbx
0x18004a46c  cmp     [rax+rbx*2], r15w
0x18004a471  jnz     short loc_18004A469
0x18004a473  mov     r8, rbx
0x18004a476  mov     rdx, rax
0x18004a479  lea     rcx, [rbp+hstringHeader]
0x18004a47d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004a482  nop
0x18004a483  lea     rdx, [rdi+0Ch]
0x18004a487  lea     rcx, [rbp+hstringHeader]; String
0x18004a48b  call    WaaS__Device__ConvertToUInt32
0x18004a490  mov     esi, eax
0x18004a492  lea     rcx, [rbp+hstringHeader]; void *
0x18004a496  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004a49b  test    esi, esi
0x18004a49d  jns     short loc_18004A519
0x18004a49f  mov     rcx, [rbp+28h]; this
0x18004a4a3  mov     r9d, esi; char *
0x18004a4a6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18004a4ad  mov     edx, 230h; void *
0x18004a4b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a4b7  nop
0x18004a4b8  mov     rcx, [rdi]
0x18004a4bb  mov     rax, [rcx]
0x18004a4be  mov     ebx, 1
0x18004a4c3  mov     edx, ebx
0x18004a4c5  mov     rcx, rdi
0x18004a4c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4cd  nop
0x18004a4ce  mov     rcx, [rbp+var_40]
0x18004a4d2  test    rcx, rcx
0x18004a4d5  jz      short loc_18004A4E5
0x18004a4d7  mov     rax, [rcx]
0x18004a4da  mov     edx, ebx
0x18004a4dc  mov     rax, [rax]
0x18004a4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4e4  nop
0x18004a4e5  mov     rcx, [rbp+var_50]
0x18004a4e9  test    rcx, rcx
0x18004a4ec  jz      short loc_18004A4FB
0x18004a4ee  mov     rax, [rcx]
0x18004a4f1  mov     rax, [rax+10h]
0x18004a4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4fa  nop
0x18004a4fb  mov     ebx, esi
0x18004a4fd  mov     rcx, [rbp+var_48]; string
0x18004a501  call    cs:__imp_WindowsDeleteString
0x18004a507  mov     [rbp+var_48], r15
0x18004a50b  mov     rcx, [rbp+var_38]; string
0x18004a50f  call    cs:__imp_WindowsDeleteString
0x18004a515  mov     eax, ebx
0x18004a517  jmp     short loc_18004A585
0x18004a519  mov     rax, [rbp+var_40]
0x18004a51d  mov     rcx, [rdi+10h]
0x18004a521  mov     [rdi+10h], rax
0x18004a525  mov     ebx, 1
0x18004a52a  test    rcx, rcx
0x18004a52d  jz      short loc_18004A53C
0x18004a52f  mov     rax, [rcx]
0x18004a532  mov     edx, ebx
0x18004a534  mov     rax, [rax]
0x18004a537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a53c  mov     rcx, [r14]
0x18004a53f  mov     [r14], rdi
0x18004a542  test    rcx, rcx
0x18004a545  jz      short loc_18004A555
0x18004a547  mov     rax, [rcx]
0x18004a54a  mov     edx, ebx
0x18004a54c  mov     rax, [rax]
0x18004a54f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a554  nop
0x18004a555  mov     rcx, [rbp+var_50]
0x18004a559  test    rcx, rcx
0x18004a55c  jz      short loc_18004A56B
0x18004a55e  mov     rax, [rcx]
0x18004a561  mov     rax, [rax+10h]
0x18004a565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a56a  nop
0x18004a56b  mov     rcx, [rbp+var_48]; string
0x18004a56f  call    cs:__imp_WindowsDeleteString
0x18004a575  mov     [rbp+var_48], r15
0x18004a579  mov     rcx, [rbp+var_38]; string
0x18004a57d  call    cs:__imp_WindowsDeleteString
  ... truncated ...
```
