# WOSCOneSettings::ParseJsonBlob(char const *)

- ea: `0x1800138d0`
- end: `0x180013dcc`
- name: `?ParseJsonBlob@WOSCOneSettings@@AEAAJPEBD@Z`
- size: `1276`
- prototype: `int(WOSCOneSettings *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012fc8`

## callees

- `0x1800069fc`
- `0x18000efcc`
- `0x18000efec`
- `0x18000f70c`
- `0x1800138d0`
- `0x1800161dc`
- `0x180019760`
- `0x18001b010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180013a24`
- `msvcrt!wcsstr` at `0x180013a24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013cdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013cdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800139a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800139a8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180013967`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800139f3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180013967`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800139f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013a6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013b27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013c4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013a6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013b27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013c4a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013aa4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013aa4`

## string_xrefs

- `0x180013a63`: `Windows.Data.Json.JsonValue`
- `0x180013d8c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall WOSCOneSettings::ParseJsonBlob(WOSCOneSettings *this, const char *a2)
{
  __int64 v3; // rcx
  const char *v4; // rax
  int v5; // esi
  unsigned int LastError; // ebx
  __int64 v7; // r12
  int v8; // eax
  const char *v9; // r9
  __int64 cchWideChar; // r15
  unsigned __int64 v12; // rbx
  void *v13; // rdx
  _WORD *v14; // rdi
  unsigned int v15; // r8d
  const char *v16; // r9
  const char *v17; // r9
  HRESULT v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  int ActivationFactory; // eax
  int v22; // edx
  unsigned int v23; // r8d
  _QWORD *v24; // rcx
  _QWORD *v25; // rsi
  __int64 v26; // r14
  HRESULT v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  int v30; // eax
  __int64 v31; // rcx
  _QWORD *v32; // rcx
  int v33; // eax
  _QWORD *v34; // rcx
  __int64 v35; // rcx
  _QWORD *v36; // rcx
  _QWORD *v37; // rbx
  __int64 v38; // rsi
  HRESULT v39; // eax
  int v40; // edx
  unsigned int v41; // r8d
  int v42; // eax
  _QWORD *v43; // rcx
  __int64 v44; // rcx
  _QWORD *v45; // rcx
  _QWORD *v46; // rcx
  __int64 v47; // rcx
  _QWORD *v48; // rcx
  int lpWideCharStr; // [rsp+20h] [rbp-49h]
  int lpWideCharStra; // [rsp+20h] [rbp-49h]
  _QWORD *v51; // [rsp+30h] [rbp-39h] BYREF
  __int64 v52; // [rsp+38h] [rbp-31h] BYREF
  _QWORD *v53; // [rsp+40h] [rbp-29h] BYREF
  int v54; // [rsp+48h] [rbp-21h]
  _WORD *v55; // [rsp+50h] [rbp-19h]
  WOSCOneSettings *v56; // [rsp+58h] [rbp-11h]
  _WORD *v57; // [rsp+60h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  HSTRING string; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v56 = this;
  v54 = 0;
  v55 = 0;
  if ( !a2 )
  {
    LastError = -2147024809;
LABEL_58:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
      (const char *)LastError,
      lpWideCharStr);
    return LastError;
  }
  v3 = 0x7FFFFFFF;
  v4 = a2;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v5 = -2147024809;
  LastError = v3 == 0 ? 0x80070057 : 0;
  v7 = (0x7FFFFFFF - v3) & -(__int64)(v3 != 0);
  if ( !v3 )
    goto LABEL_58;
  v8 = MultiByteToWideChar(0, 0, a2, v7, 0, 0);
  cchWideChar = v8;
  if ( !v8 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xD1,
             (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
             v9);
  v12 = -1;
  if ( v8 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v9);
  v14 = CoTaskMemAlloc(2LL * v8 + 2);
  if ( v14 )
  {
    *v14 = 0;
    v14[cchWideChar] = 0;
  }
  v57 = v14;
  v54 = 2;
  if ( !v14 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v13, v15, v16);
  v55 = v14;
  if ( MultiByteToWideChar(0, 0, a2, v7, v14, cchWideChar) != (_DWORD)cchWideChar )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xD6,
                  (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
                  v17);
LABEL_49:
    CoTaskMemFree(v14);
    return LastError;
  }
  if ( !wcsstr(v14, L"\"settings\":") )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
      (const char *)0x80070057LL,
      lpWideCharStra);
LABEL_16:
    LastError = v5;
    goto LABEL_49;
  }
  v51 = 0;
  string = 0;
  v18 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v18 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
LABEL_63:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v27, v28, v29);
LABEL_64:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v39, v40, v41);
    goto LABEL_65;
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v51);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
      (const char *)(unsigned int)ActivationFactory,
      lpWideCharStra);
    v24 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
    }
    goto LABEL_16;
  }
  v52 = 0;
  v25 = v51;
  v26 = *v51;
  string = 0;
  do
    ++v12;
  while ( v14[v12] );
  if ( v12 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v22, v23);
    JUMPOUT(0x180013DCBLL);
  }
  if ( (int)v12 + 1 < (unsigned int)v12 )
  {
LABEL_65:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v22, v23);
    __debugbreak();
  }
  v27 = WindowsCreateStringReference(v14, v12, &hstringHeader, &string);
  if ( v27 < 0 )
    goto LABEL_63;
  v30 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v26 + 48))(v25, string, &v52);
  LastError = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
      (const char *)(unsigned int)v30,
      lpWideCharStra);
    v31 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
    }
    goto LABEL_49;
  }
  v53 = 0;
  v33 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v52 + 96LL))(v52, &v53);
  LastError = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
      (const char *)(unsigned int)v33,
      lpWideCharStra);
    v34 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
    }
    v35 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
    }
    goto LABEL_49;
  }
  v37 = v53;
  v38 = *v53;
  string = 0;
  v39 = WindowsCreateStringReference(L"settings", 8u, &hstringHeader, &string);
  if ( v39 < 0 )
    goto LABEL_64;
  v42 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, WOSCOneSettings *))(v38 + 64))(v37, string, v56);
  LastError = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
      (const char *)(unsigned int)v42,
      lpWideCharStra);
    v43 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v43 + 16LL))(v43);
    }
    v44 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    v45 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
    }
    goto LABEL_49;
  }
  v46 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
  }
  v47 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v48 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
  }
  CoTaskMemFree(v14);
  return 0;
}

```

## disassembly

```asm
0x1800138d0  mov     [rsp-8+arg_10], rbx
0x1800138d5  push    rbp
0x1800138d6  push    rsi
0x1800138d7  push    rdi
0x1800138d8  push    r12
0x1800138da  push    r13
0x1800138dc  push    r14
0x1800138de  push    r15
0x1800138e0  lea     rbp, [rsp-27h]
0x1800138e5  sub     rsp, 90h
0x1800138ec  mov     rax, cs:__security_cookie
0x1800138f3  xor     rax, rsp
0x1800138f6  mov     [rbp+57h+var_38], rax
0x1800138fa  mov     r14, rdx
0x1800138fd  mov     [rbp+57h+var_68], rcx
0x180013901  xor     edi, edi
0x180013903  mov     [rbp+57h+var_78], edi
0x180013906  mov     [rbp+57h+var_70], rdi
0x18001390a  test    rdx, rdx
0x18001390d  jz      loc_180013D3F
0x180013913  mov     edx, 7FFFFFFFh
0x180013918  mov     ecx, edx
0x18001391a  mov     rax, r14
0x18001391d  cmp     [rax], dil
0x180013920  jz      short loc_18001392B
0x180013922  inc     rax
0x180013925  sub     rcx, 1
0x180013929  jnz     short loc_18001391D
0x18001392b  mov     rax, rcx
0x18001392e  neg     rax
0x180013931  sbb     ebx, ebx
0x180013933  not     ebx
0x180013935  mov     esi, 80070057h
0x18001393a  and     ebx, esi
0x18001393c  mov     rax, rcx
0x18001393f  sub     rdx, rcx
0x180013942  neg     rax
0x180013945  sbb     r12, r12
0x180013948  and     r12, rdx
0x18001394b  test    rcx, rcx
0x18001394e  jz      loc_180013D44
0x180013954  mov     [rsp+0C0h+cchWideChar], edi; cchWideChar
0x180013958  mov     [rsp+0C0h+lpWideCharStr], rdi; lpWideCharStr
0x18001395d  mov     r9d, r12d; cbMultiByte
0x180013960  mov     r8, r14; lpMultiByteStr
0x180013963  xor     edx, edx; dwFlags
0x180013965  xor     ecx, ecx; CodePage
0x180013967  call    cs:__imp_MultiByteToWideChar
0x18001396d  movsxd  r15, eax
0x180013970  test    eax, eax
0x180013972  jnz     short loc_18001398F
0x180013974  mov     rcx, [rbp+5Fh]; this
0x180013978  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasassessment\\woscs"...
0x18001397f  mov     edx, 0D1h; void *
0x180013984  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013989  nop
0x18001398a  jmp     loc_180013D5F
0x18001398f  mov     rcx, [rbp+5Fh]; this
0x180013993  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013997  cmp     r15d, ebx
0x18001399a  jz      loc_180013D8C
0x1800139a0  lea     rcx, ds:2[r15*2]; cb
0x1800139a8  call    cs:__imp_CoTaskMemAlloc
0x1800139ae  mov     rdi, rax
0x1800139b1  test    rax, rax
0x1800139b4  jz      short loc_1800139C0
0x1800139b6  xor     eax, eax
0x1800139b8  mov     [rdi], ax
0x1800139bb  mov     [rdi+r15*2], ax
0x1800139c0  mov     [rbp+57h+var_60], rdi
0x1800139c4  mov     [rbp+57h+var_78], 2
0x1800139cb  mov     rcx, [rbp+5Fh]; this
0x1800139cf  xor     r13d, r13d
0x1800139d2  test    rdi, rdi
0x1800139d5  jz      loc_180013D86
0x1800139db  mov     [rbp+57h+var_70], rdi
0x1800139df  mov     [rsp+0C0h+cchWideChar], r15d; cchWideChar
0x1800139e4  mov     [rsp+0C0h+lpWideCharStr], rdi; int
0x1800139e9  mov     r9d, r12d; cbMultiByte
0x1800139ec  mov     r8, r14; lpMultiByteStr
0x1800139ef  xor     edx, edx; dwFlags
0x1800139f1  xor     ecx, ecx; CodePage
0x1800139f3  call    cs:__imp_MultiByteToWideChar
0x1800139f9  cmp     eax, r15d
0x1800139fc  jz      short loc_180013A1A
0x1800139fe  mov     rcx, [rbp+5Fh]; this
0x180013a02  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasassessment\\woscs"...
0x180013a09  mov     edx, 0D6h; void *
0x180013a0e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013a13  mov     ebx, eax
0x180013a15  jmp     loc_180013CD9
0x180013a1a  lea     rdx, aSettings_0; "\"settings\":"
0x180013a21  mov     rcx, rdi; Str
0x180013a24  call    cs:__imp_wcsstr
0x180013a2a  test    rax, rax
0x180013a2d  jnz     short loc_180013A4E
0x180013a2f  mov     rcx, [rbp+5Fh]; this
0x180013a33  mov     r9d, esi; char *
0x180013a36  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasassessment\\woscs"...
0x180013a3d  mov     edx, 0D9h; void *
0x180013a42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013a47  mov     ebx, esi
0x180013a49  jmp     loc_180013CD9
0x180013a4e  mov     [rbp+57h+var_90], r13
0x180013a52  mov     [rbp+57h+string], r13
0x180013a56  lea     r9, [rbp+57h+string]; string
0x180013a5a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180013a5e  mov     edx, 1Bh; length
0x180013a63  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180013a6a  call    cs:__imp_WindowsCreateStringReference
0x180013a70  test    eax, eax
0x180013a72  js      loc_180013D9E
0x180013a78  mov     rsi, [rbp+57h+string]
0x180013a7c  mov     rcx, [rbp+57h+var_90]
0x180013a80  test    rcx, rcx
0x180013a83  jz      short loc_180013A96
0x180013a85  mov     [rbp+57h+var_90], r13
0x180013a89  mov     rax, [rcx]
0x180013a8c  mov     rax, [rax+10h]
0x180013a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a95  nop
0x180013a96  lea     r8, [rbp+57h+var_90]
0x180013a9a  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180013aa1  mov     rcx, rsi
0x180013aa4  call    cs:__imp_RoGetActivationFactory
0x180013aaa  mov     esi, eax
0x180013aac  test    eax, eax
0x180013aae  jns     short loc_180013AE8
0x180013ab0  mov     rcx, [rbp+5Fh]; this
0x180013ab4  mov     r9d, eax; char *
0x180013ab7  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasassessment\\woscs"...
0x180013abe  mov     edx, 0DDh; void *
0x180013ac3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ac8  nop
0x180013ac9  mov     rcx, [rbp+57h+var_90]
0x180013acd  test    rcx, rcx
0x180013ad0  jz      short loc_180013AE3
0x180013ad2  mov     [rbp+57h+var_90], r13
0x180013ad6  mov     rax, [rcx]
0x180013ad9  mov     rax, [rax+10h]
0x180013add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ae2  nop
0x180013ae3  jmp     loc_180013A47
0x180013ae8  mov     [rbp+57h+var_88], r13
0x180013aec  mov     rsi, [rbp+57h+var_90]
0x180013af0  mov     r14, [rsi]
0x180013af3  mov     [rbp+57h+string], r13
0x180013af7  inc     rbx
0x180013afa  cmp     [rdi+rbx*2], r13w
0x180013aff  jnz     short loc_180013AF7
0x180013b01  mov     eax, 0FFFFFFFFh
0x180013b06  cmp     rbx, rax
0x180013b09  ja      loc_180013DC1
0x180013b0f  lea     eax, [rbx+1]
0x180013b12  cmp     eax, ebx
0x180013b14  jb      loc_180013DB6
0x180013b1a  lea     r9, [rbp+57h+string]; string
0x180013b1e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180013b22  mov     edx, ebx; length
0x180013b24  mov     rcx, rdi; sourceString
0x180013b27  call    cs:__imp_WindowsCreateStringReference
0x180013b2d  test    eax, eax
0x180013b2f  js      loc_180013DA6
0x180013b35  lea     r8, [rbp+57h+var_88]
0x180013b39  mov     rdx, [rbp+57h+string]
0x180013b3d  mov     rcx, rsi
0x180013b40  mov     rax, [r14+30h]
0x180013b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b49  mov     ebx, eax
0x180013b4b  test    eax, eax
0x180013b4d  jns     short loc_180013BA1
0x180013b4f  mov     rcx, [rbp+5Fh]; this
0x180013b53  mov     r9d, eax; char *
0x180013b56  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasassessment\\woscs"...
0x180013b5d  mov     edx, 0E0h; void *
0x180013b62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013b67  nop
0x180013b68  mov     rcx, [rbp+57h+var_88]
0x180013b6c  test    rcx, rcx
0x180013b6f  jz      short loc_180013B82
0x180013b71  mov     [rbp+57h+var_88], r13
0x180013b75  mov     rax, [rcx]
0x180013b78  mov     rax, [rax+10h]
0x180013b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b81  nop
0x180013b82  mov     rcx, [rbp+57h+var_90]
0x180013b86  test    rcx, rcx
0x180013b89  jz      short loc_180013B9C
0x180013b8b  mov     [rbp+57h+var_90], r13
0x180013b8f  mov     rax, [rcx]
0x180013b92  mov     rax, [rax+10h]
0x180013b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b9b  nop
0x180013b9c  jmp     loc_180013CD9
0x180013ba1  mov     [rbp+57h+var_80], r13
0x180013ba5  mov     rcx, [rbp+57h+var_88]
0x180013ba9  mov     rax, [rcx]
0x180013bac  lea     rdx, [rbp+57h+var_80]
0x180013bb0  mov     rax, [rax+60h]
0x180013bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bb9  mov     ebx, eax
0x180013bbb  test    eax, eax
0x180013bbd  jns     short loc_180013C2B
0x180013bbf  mov     rcx, [rbp+5Fh]; this
0x180013bc3  mov     r9d, eax; char *
0x180013bc6  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasassessment\\woscs"...
0x180013bcd  mov     edx, 0E3h; void *
0x180013bd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013bd7  nop
0x180013bd8  mov     rcx, [rbp+57h+var_80]
0x180013bdc  test    rcx, rcx
0x180013bdf  jz      short loc_180013BF2
0x180013be1  mov     [rbp+57h+var_80], r13
0x180013be5  mov     rax, [rcx]
0x180013be8  mov     rax, [rax+10h]
0x180013bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bf1  nop
0x180013bf2  mov     rcx, [rbp+57h+var_88]
0x180013bf6  test    rcx, rcx
0x180013bf9  jz      short loc_180013C0C
0x180013bfb  mov     [rbp+57h+var_88], r13
0x180013bff  mov     rax, [rcx]
0x180013c02  mov     rax, [rax+10h]
0x180013c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c0b  nop
0x180013c0c  mov     rcx, [rbp+57h+var_90]
0x180013c10  test    rcx, rcx
0x180013c13  jz      short loc_180013C26
0x180013c15  mov     [rbp+57h+var_90], r13
0x180013c19  mov     rax, [rcx]
0x180013c1c  mov     rax, [rax+10h]
0x180013c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c25  nop
0x180013c26  jmp     loc_180013CD9
0x180013c2b  mov     rbx, [rbp+57h+var_80]
0x180013c2f  mov     rsi, [rbx]
0x180013c32  mov     [rbp+57h+string], r13
0x180013c36  lea     r9, [rbp+57h+string]; string
0x180013c3a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180013c3e  mov     edx, 8; length
0x180013c43  lea     rcx, aSettings; "settings"
0x180013c4a  call    cs:__imp_WindowsCreateStringReference
0x180013c50  test    eax, eax
0x180013c52  js      loc_180013DAE
0x180013c58  mov     r8, [rbp+57h+var_68]
0x180013c5c  mov     rdx, [rbp+57h+string]
0x180013c60  mov     rcx, rbx
0x180013c63  mov     rax, [rsi+40h]
0x180013c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c6c  mov     ebx, eax
0x180013c6e  test    eax, eax
0x180013c70  jns     short loc_180013CE4
0x180013c72  mov     rcx, [rbp+5Fh]; this
0x180013c76  mov     r9d, eax; char *
0x180013c79  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasassessment\\woscs"...
0x180013c80  mov     edx, 0E6h; void *
0x180013c85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013c8a  nop
0x180013c8b  mov     rcx, [rbp+57h+var_80]
0x180013c8f  test    rcx, rcx
0x180013c92  jz      short loc_180013CA5
0x180013c94  mov     [rbp+57h+var_80], r13
0x180013c98  mov     rax, [rcx]
0x180013c9b  mov     rax, [rax+10h]
0x180013c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ca4  nop
0x180013ca5  mov     rcx, [rbp+57h+var_88]
0x180013ca9  test    rcx, rcx
0x180013cac  jz      short loc_180013CBF
0x180013cae  mov     [rbp+57h+var_88], r13
0x180013cb2  mov     rax, [rcx]
0x180013cb5  mov     rax, [rax+10h]
0x180013cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cbe  nop
0x180013cbf  mov     rcx, [rbp+57h+var_90]
0x180013cc3  test    rcx, rcx
0x180013cc6  jz      short loc_180013CD9
0x180013cc8  mov     [rbp+57h+var_90], r13
0x180013ccc  mov     rax, [rcx]
0x180013ccf  mov     rax, [rax+10h]
0x180013cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cd8  nop
0x180013cd9  mov     rcx, rdi; pv
0x180013cdc  call    cs:__imp_CoTaskMemFree
0x180013ce2  jmp     short loc_180013D5D
0x180013ce4  mov     rcx, [rbp+57h+var_80]
0x180013ce8  test    rcx, rcx
0x180013ceb  jz      short loc_180013CFE
0x180013ced  mov     [rbp+57h+var_80], r13
0x180013cf1  mov     rax, [rcx]
0x180013cf4  mov     rax, [rax+10h]
0x180013cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cfd  nop
0x180013cfe  mov     rcx, [rbp+57h+var_88]
0x180013d02  test    rcx, rcx
0x180013d05  jz      short loc_180013D18
0x180013d07  mov     [rbp+57h+var_88], r13
0x180013d0b  mov     rax, [rcx]
0x180013d0e  mov     rax, [rax+10h]
0x180013d12  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
