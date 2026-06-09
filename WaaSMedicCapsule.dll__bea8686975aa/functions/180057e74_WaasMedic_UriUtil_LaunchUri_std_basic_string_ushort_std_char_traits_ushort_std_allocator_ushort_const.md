# WaasMedic::UriUtil::LaunchUri(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180057e74`
- end: `0x180058240`
- name: `?LaunchUri@UriUtil@WaasMedic@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `972`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800408a0`
- `0x180044620`

## callees

- `0x180003bb0`
- `0x180009a54`
- `0x180023798`
- `0x180024980`
- `0x18003fe90`
- `0x180057880`
- `0x180057e74`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180057ed7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180057ff4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180057ed7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180057ff4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180057eba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180057fd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180057eba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180057fd7`

## string_xrefs

- `0x18005822e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180057eb3`: `Windows.Foundation.Uri`
- `0x180057eea`: `onecore\enduser\waasmedic\lib\util\uriutil.cpp`
- `0x180057f70`: `onecore\enduser\waasmedic\lib\util\uriutil.cpp`
- `0x180058007`: `onecore\enduser\waasmedic\lib\util\uriutil.cpp`
- `0x1800580f5`: `onecore\enduser\waasmedic\lib\util\uriutil.cpp`
- `0x180058209`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall WaasMedic::UriUtil::LaunchUri(_QWORD *a1)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // rsi
  __int64 v10; // rax
  int v11; // eax
  HRESULT v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  int v15; // eax
  int v16; // eax
  wil::details::in1diag3 *v17; // rcx
  _QWORD *v18; // rbx
  __int64 (__fastcall *v19)(_QWORD *, __int64, __int64 *); // rdi
  __int64 v20; // rcx
  __int64 v21; // rbx
  int v22; // eax
  int v23; // [rsp+20h] [rbp-29h] BYREF
  __int64 v24; // [rsp+28h] [rbp-21h] BYREF
  __int64 v25; // [rsp+30h] [rbp-19h] BYREF
  __int64 v26; // [rsp+38h] [rbp-11h] BYREF
  __int64 v27; // [rsp+40h] [rbp-9h] BYREF
  _QWORD *v28; // [rsp+48h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp+7h] BYREF
  HSTRING string; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v25 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
LABEL_52:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
    goto LABEL_53;
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v25);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\uriutil.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v23);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    return v6;
  }
  v24 = 0;
  v8 = v25;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 48LL);
  v24 = 0;
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  v28 = a1;
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v28);
  v11 = v9(v8, *(_QWORD *)(v10 + 24), &v24);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\uriutil.cpp",
      (const char *)(unsigned int)v11,
      v23);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    return v6;
  }
  v27 = 0;
  string = 0;
  v12 = WindowsCreateStringReference(L"Windows.System.Launcher", 0x17u, &hstringHeader, &string);
  if ( v12 < 0 )
    goto LABEL_52;
  v15 = RoGetActivationFactory(string, &GUID_00000035_0000_0000_c000_000000000046, &v27);
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\uriutil.cpp",
      (const char *)(unsigned int)v15,
      v23);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    return v6;
  }
  v26 = 0;
  v28 = 0;
  v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD **))v27)(
          v27,
          &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451,
          &v28);
  v17 = retaddr;
  if ( v16 < 0 )
LABEL_53:
    wil::details::in1diag3::_Throw_Hr(
      v17,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v16,
      v23);
  v18 = v28;
  v19 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(*v28 + 64LL);
  v20 = v26;
  v26 = 0;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v6 = v19(v18, v24, &v26);
  if ( v28 )
    (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\uriutil.cpp",
      (const char *)v6,
      v23);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    return v6;
  }
  v21 = v26;
  LOBYTE(v23) = 0;
  v22 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(v26);
  if ( v22 >= 0 )
    v22 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 64LL))(v21, &v23);
  if ( v22 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x71B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v22,
      v23);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  return 0;
}

```

## disassembly

```asm
0x180057e74  push    rbp
0x180057e76  push    rbx
0x180057e77  push    rsi
0x180057e78  push    rdi
0x180057e79  lea     rbp, [rsp-3Fh]
0x180057e7e  sub     rsp, 88h
0x180057e85  mov     rax, cs:__security_cookie
0x180057e8c  xor     rax, rsp
0x180057e8f  mov     [rbp+57h+var_30], rax
0x180057e93  mov     rdi, rcx
0x180057e96  mov     [rbp+57h+var_70], 0
0x180057e9e  mov     [rbp+57h+string], 0
0x180057ea6  lea     r9, [rbp+57h+string]; string
0x180057eaa  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180057eae  mov     edx, 16h; length
0x180057eb3  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180057eba  call    cs:__imp_WindowsCreateStringReference
0x180057ec0  test    eax, eax
0x180057ec2  js      loc_18005821B
0x180057ec8  lea     r8, [rbp+57h+var_70]
0x180057ecc  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x180057ed3  mov     rcx, [rbp+57h+string]
0x180057ed7  call    cs:__imp_RoGetActivationFactory
0x180057edd  mov     ebx, eax
0x180057edf  test    eax, eax
0x180057ee1  jns     short loc_180057F19
0x180057ee3  mov     rcx, [rbp+5Fh]; this
0x180057ee7  mov     r9d, eax; char *
0x180057eea  lea     r8, aOnecoreEnduser_36; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180057ef1  mov     edx, 13h; void *
0x180057ef6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057efb  nop
0x180057efc  mov     rcx, [rbp+57h+var_70]
0x180057f00  test    rcx, rcx
0x180057f03  jz      short loc_180057F12
0x180057f05  mov     rax, [rcx]
0x180057f08  mov     rax, [rax+10h]
0x180057f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f11  nop
0x180057f12  mov     eax, ebx
0x180057f14  jmp     loc_1800581EE
0x180057f19  mov     [rbp+57h+var_78], 0
0x180057f21  mov     rbx, [rbp+57h+var_70]
0x180057f25  mov     rax, [rbx]
0x180057f28  mov     rsi, [rax+30h]
0x180057f2c  mov     [rbp+57h+var_78], 0
0x180057f34  cmp     qword ptr [rdi+18h], 7
0x180057f39  jbe     short loc_180057F3E
0x180057f3b  mov     rdi, [rdi]
0x180057f3e  mov     [rbp+57h+var_58], rdi
0x180057f42  lea     rdx, [rbp+57h+var_58]
0x180057f46  lea     rcx, [rbp+57h+hstringHeader]
0x180057f4a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180057f4f  nop
0x180057f50  lea     r8, [rbp+57h+var_78]
0x180057f54  mov     rdx, [rax+18h]
0x180057f58  mov     rcx, rbx
0x180057f5b  mov     rax, rsi
0x180057f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f63  mov     ebx, eax
0x180057f65  test    eax, eax
0x180057f67  jns     short loc_180057FB3
0x180057f69  mov     rcx, [rbp+5Fh]; this
0x180057f6d  mov     r9d, eax; char *
0x180057f70  lea     r8, aOnecoreEnduser_36; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180057f77  mov     edx, 16h; void *
0x180057f7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057f81  nop
0x180057f82  mov     rcx, [rbp+57h+var_78]
0x180057f86  test    rcx, rcx
0x180057f89  jz      short loc_180057F98
0x180057f8b  mov     rax, [rcx]
0x180057f8e  mov     rax, [rax+10h]
0x180057f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f97  nop
0x180057f98  mov     rcx, [rbp+57h+var_70]
0x180057f9c  test    rcx, rcx
0x180057f9f  jz      short loc_180057FAE
0x180057fa1  mov     rax, [rcx]
0x180057fa4  mov     rax, [rax+10h]
0x180057fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057fad  nop
0x180057fae  jmp     loc_180057F12
0x180057fb3  mov     [rbp+57h+var_60], 0
0x180057fbb  mov     [rbp+57h+string], 0
0x180057fc3  lea     r9, [rbp+57h+string]; string
0x180057fc7  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180057fcb  mov     edx, 17h; length
0x180057fd0  lea     rcx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x180057fd7  call    cs:__imp_WindowsCreateStringReference
0x180057fdd  test    eax, eax
0x180057fdf  js      loc_180058223
0x180057fe5  lea     r8, [rbp+57h+var_60]
0x180057fe9  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180057ff0  mov     rcx, [rbp+57h+string]
0x180057ff4  call    cs:__imp_RoGetActivationFactory
0x180057ffa  mov     ebx, eax
0x180057ffc  test    eax, eax
0x180057ffe  jns     short loc_180058060
0x180058000  mov     rcx, [rbp+5Fh]; this
0x180058004  mov     r9d, eax; char *
0x180058007  lea     r8, aOnecoreEnduser_36; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005800e  mov     edx, 19h; void *
0x180058013  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058018  nop
0x180058019  mov     rcx, [rbp+57h+var_60]
0x18005801d  test    rcx, rcx
0x180058020  jz      short loc_18005802F
0x180058022  mov     rax, [rcx]
0x180058025  mov     rax, [rax+10h]
0x180058029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005802e  nop
0x18005802f  mov     rcx, [rbp+57h+var_78]
0x180058033  test    rcx, rcx
0x180058036  jz      short loc_180058045
0x180058038  mov     rax, [rcx]
0x18005803b  mov     rax, [rax+10h]
0x18005803f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058044  nop
0x180058045  mov     rcx, [rbp+57h+var_70]
0x180058049  test    rcx, rcx
0x18005804c  jz      short loc_18005805B
0x18005804e  mov     rax, [rcx]
0x180058051  mov     rax, [rax+10h]
0x180058055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005805a  nop
0x18005805b  jmp     loc_180057F12
0x180058060  mov     [rbp+57h+var_68], 0
0x180058068  mov     rcx, [rbp+57h+var_60]
0x18005806c  mov     [rbp+57h+var_58], 0
0x180058074  mov     rax, [rcx]
0x180058077  lea     r8, [rbp+57h+var_58]
0x18005807b  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x180058082  mov     rax, [rax]
0x180058085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005808a  mov     rcx, [rbp+5Fh]
0x18005808e  test    eax, eax
0x180058090  js      loc_18005822B
0x180058096  mov     rbx, [rbp+57h+var_58]
0x18005809a  mov     rax, [rbx]
0x18005809d  mov     rdi, [rax+40h]
0x1800580a1  mov     rcx, [rbp+57h+var_68]
0x1800580a5  mov     [rbp+57h+var_68], 0
0x1800580ad  test    rcx, rcx
0x1800580b0  jz      short loc_1800580BF
0x1800580b2  mov     rdx, [rcx]
0x1800580b5  mov     rax, [rdx+10h]
0x1800580b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800580be  nop
0x1800580bf  lea     r8, [rbp+57h+var_68]
0x1800580c3  mov     rdx, [rbp+57h+var_78]
0x1800580c7  mov     rcx, rbx
0x1800580ca  mov     rax, rdi
0x1800580cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800580d2  mov     ebx, eax
0x1800580d4  mov     rcx, [rbp+57h+var_58]
0x1800580d8  test    rcx, rcx
0x1800580db  jz      short loc_1800580EA
0x1800580dd  mov     rdx, [rcx]
0x1800580e0  mov     rax, [rdx+10h]
0x1800580e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800580e9  nop
0x1800580ea  test    ebx, ebx
0x1800580ec  jns     short loc_180058164
0x1800580ee  mov     rcx, [rbp+5Fh]; this
0x1800580f2  mov     r9d, ebx; char *
0x1800580f5  lea     r8, aOnecoreEnduser_36; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800580fc  mov     edx, 1Ch; void *
0x180058101  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058106  nop
0x180058107  mov     rcx, [rbp+57h+var_68]
0x18005810b  test    rcx, rcx
0x18005810e  jz      short loc_18005811D
0x180058110  mov     rax, [rcx]
0x180058113  mov     rax, [rax+10h]
0x180058117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005811c  nop
0x18005811d  mov     rcx, [rbp+57h+var_60]
0x180058121  test    rcx, rcx
0x180058124  jz      short loc_180058133
0x180058126  mov     rax, [rcx]
0x180058129  mov     rax, [rax+10h]
0x18005812d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058132  nop
0x180058133  mov     rcx, [rbp+57h+var_78]
0x180058137  test    rcx, rcx
0x18005813a  jz      short loc_180058149
0x18005813c  mov     rax, [rcx]
0x18005813f  mov     rax, [rax+10h]
0x180058143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058148  nop
0x180058149  mov     rcx, [rbp+57h+var_70]
0x18005814d  test    rcx, rcx
0x180058150  jz      short loc_18005815F
0x180058152  mov     rax, [rcx]
0x180058155  mov     rax, [rax+10h]
0x180058159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005815e  nop
0x18005815f  jmp     loc_180057F12
0x180058164  mov     rbx, [rbp+57h+var_68]
0x180058168  mov     byte ptr [rbp+57h+var_80], 0
0x18005816c  mov     rcx, rbx
0x18005816f  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180058174  test    eax, eax
0x180058176  js      short loc_18005818C
0x180058178  mov     rax, [rbx]
0x18005817b  lea     rdx, [rbp+57h+var_80]
0x18005817f  mov     rcx, rbx
0x180058182  mov     rax, [rax+40h]
0x180058186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005818b  nop
0x18005818c  mov     rcx, [rbp+5Fh]; this
0x180058190  test    eax, eax
0x180058192  js      short loc_180058206
0x180058194  mov     rcx, [rbp+57h+var_68]
0x180058198  test    rcx, rcx
0x18005819b  jz      short loc_1800581AA
0x18005819d  mov     rax, [rcx]
0x1800581a0  mov     rax, [rax+10h]
0x1800581a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581a9  nop
0x1800581aa  mov     rcx, [rbp+57h+var_60]
0x1800581ae  test    rcx, rcx
0x1800581b1  jz      short loc_1800581C0
0x1800581b3  mov     rax, [rcx]
0x1800581b6  mov     rax, [rax+10h]
0x1800581ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581bf  nop
0x1800581c0  mov     rcx, [rbp+57h+var_78]
0x1800581c4  test    rcx, rcx
0x1800581c7  jz      short loc_1800581D6
0x1800581c9  mov     rax, [rcx]
0x1800581cc  mov     rax, [rax+10h]
0x1800581d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581d5  nop
0x1800581d6  mov     rcx, [rbp+57h+var_70]
0x1800581da  test    rcx, rcx
0x1800581dd  jz      short loc_1800581EC
0x1800581df  mov     rax, [rcx]
0x1800581e2  mov     rax, [rax+10h]
0x1800581e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581eb  nop
0x1800581ec  xor     eax, eax
0x1800581ee  mov     rcx, [rbp+57h+var_30]
0x1800581f2  xor     rcx, rsp; StackCookie
0x1800581f5  call    __security_check_cookie
0x1800581fa  add     rsp, 88h
0x180058201  pop     rdi
0x180058202  pop     rsi
0x180058203  pop     rbx
0x180058204  pop     rbp
0x180058205  retn
0x180058206  mov     r9d, eax; char *
0x180058209  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180058210  mov     edx, 71Bh; void *
0x180058215  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18005821b  mov     ecx, eax; this
0x18005821d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180058222  nop
0x180058223  mov     ecx, eax; this
0x180058225  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18005822a  nop
0x18005822b  mov     r9d, eax; char *
0x18005822e  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180058235  mov     edx, 1CBEh; void *
0x18005823a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
