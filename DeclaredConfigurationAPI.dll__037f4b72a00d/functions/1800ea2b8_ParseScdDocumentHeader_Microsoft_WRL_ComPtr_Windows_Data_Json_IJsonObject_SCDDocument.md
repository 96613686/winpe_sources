# ParseScdDocumentHeader(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,SCDDocument &)

- ea: `0x1800ea2b8`
- end: `0x1800ea551`
- name: `?ParseScdDocumentHeader@@YAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAVSCDDocument@@@Z`
- size: `665`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ea038`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180019188`
- `0x180019d38`
- `0x1800ea2b8`
- `0x1800f3fec`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ea34f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ea3ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ea440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ea4b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ea34f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ea3ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ea440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ea4b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea2f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea381`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea3e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea46f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea4fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea524`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea2f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea381`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea3e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea46f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea4fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea524`

## string_xrefs

- `0x1800ea333`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`
- `0x1800ea424`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`
- `0x1800ea4e5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ParseScdDocumentHeader(__int64 *a1, char **a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // rsi
  __int64 v11; // r8
  __int64 v12; // rdi
  unsigned int (__fastcall *v13)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v14; // rax
  PCWSTR v15; // rax
  __int64 v16; // r8
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v19; // rax
  int v20; // eax
  PCWSTR v21; // rax
  __int64 v22; // r8
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rdx
  PCWSTR v28; // rax
  HSTRING v30; // [rsp+20h] [rbp-50h] BYREF
  HSTRING v31; // [rsp+28h] [rbp-48h] BYREF
  HSTRING v32; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v34[32]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  string = 0;
  v4 = *a1;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a1 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v34, &c_tagId);
  v7 = v5(v4, *(_QWORD *)(v6 + 24), &string);
  v8 = v7;
  if ( v7 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( StringRawBuffer[v11] );
    std::wstring::_Assign<unsigned short>(a2, StringRawBuffer, (char *)v11);
    v31 = 0;
    v12 = *a1;
    v13 = *(unsigned int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a1 + 80LL);
    WindowsDeleteString(0);
    v31 = 0;
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v34, &c_tagDescription);
    if ( !v13(v12, *(_QWORD *)(v14 + 24), &v31) )
    {
      v15 = WindowsGetStringRawBuffer(v31, 0);
      v16 = -1;
      do
        ++v16;
      while ( v15[v16] );
      std::wstring::_Assign<unsigned short>(a2 + 4, v15, (char *)v16);
    }
    v30 = 0;
    v17 = *a1;
    v18 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a1 + 80LL);
    WindowsDeleteString(0);
    v30 = 0;
    v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v34, &c_tagVersion);
    v20 = v18(v17, *(_QWORD *)(v19 + 24), &v30);
    v8 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x700,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
        (const char *)(unsigned int)v20,
        (int)v30);
LABEL_21:
      WindowsDeleteString(v30);
      v30 = 0;
      WindowsDeleteString(v31);
      v31 = 0;
      goto LABEL_22;
    }
    v21 = WindowsGetStringRawBuffer(v30, 0);
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    std::wstring::_Assign<unsigned short>(a2 + 8, v21, (char *)v22);
    v32 = 0;
    v23 = *a1;
    v24 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a1 + 80LL);
    WindowsDeleteString(0);
    v32 = 0;
    v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v34, &c_tagSchemaVersion);
    v26 = v24(v23, *(_QWORD *)(v25 + 24), &v32);
    v8 = v26;
    if ( v26 >= 0 )
    {
      v28 = WindowsGetStringRawBuffer(v32, 0);
      do
        ++v10;
      while ( v28[v10] );
      std::wstring::_Assign<unsigned short>(a2 + 12, v28, (char *)v10);
      v26 = ValidateScdDocumentHeader((const struct SCDDocument *)a2);
      v8 = v26;
      if ( v26 >= 0 )
        goto LABEL_20;
      v27 = 1799;
    }
    else
    {
      v27 = 1796;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
      (const char *)(unsigned int)v26,
      (int)v30);
LABEL_20:
    WindowsDeleteString(v32);
    v32 = 0;
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6F6,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
    (const char *)(unsigned int)v7,
    (int)v30);
LABEL_22:
  WindowsDeleteString(string);
  return v8;
}

```

## disassembly

```asm
0x1800ea2b8  mov     [rsp-28h+arg_10], rbx
0x1800ea2bd  mov     [rsp-28h+arg_18], rsi
0x1800ea2c2  push    rbp
0x1800ea2c3  push    rdi
0x1800ea2c4  push    r12
0x1800ea2c6  push    r14
0x1800ea2c8  push    r15
0x1800ea2ca  mov     rbp, rsp
0x1800ea2cd  sub     rsp, 70h
0x1800ea2d1  mov     rax, cs:__security_cookie
0x1800ea2d8  xor     rax, rsp
0x1800ea2db  mov     [rbp+var_10], rax
0x1800ea2df  mov     r14, rdx
0x1800ea2e2  mov     r15, rcx
0x1800ea2e5  xor     r12d, r12d
0x1800ea2e8  mov     [rbp+string], r12
0x1800ea2ec  mov     rdi, [rcx]
0x1800ea2ef  mov     rax, [rdi]
0x1800ea2f2  mov     rbx, [rax+50h]
0x1800ea2f6  xor     ecx, ecx; string
0x1800ea2f8  call    cs:__imp_WindowsDeleteString
0x1800ea2fe  mov     [rbp+string], r12
0x1800ea302  lea     rdx, ?c_tagId@@3PEBGEB; ushort const * const c_tagId
0x1800ea309  lea     rcx, [rbp+var_30]
0x1800ea30d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ea312  nop
0x1800ea313  lea     r8, [rbp+string]
0x1800ea317  mov     rdx, [rax+18h]
0x1800ea31b  mov     rcx, rdi
0x1800ea31e  mov     rax, rbx
0x1800ea321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea326  mov     ebx, eax
0x1800ea328  test    eax, eax
0x1800ea32a  jns     short loc_1800EA349
0x1800ea32c  mov     rcx, [rbp+28h]; this
0x1800ea330  mov     r9d, eax; char *
0x1800ea333  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ea33a  mov     edx, 6F6h; void *
0x1800ea33f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea344  jmp     loc_1800EA520
0x1800ea349  xor     edx, edx; length
0x1800ea34b  mov     rcx, [rbp+string]; string
0x1800ea34f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ea355  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800ea359  mov     r8, rsi
0x1800ea35c  inc     r8
0x1800ea35f  cmp     [rax+r8*2], r12w
0x1800ea364  jnz     short loc_1800EA35C
0x1800ea366  mov     rdx, rax
0x1800ea369  mov     rcx, r14
0x1800ea36c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ea371  mov     [rbp+var_48], r12
0x1800ea375  mov     rdi, [r15]
0x1800ea378  mov     rax, [rdi]
0x1800ea37b  mov     rbx, [rax+50h]
0x1800ea37f  xor     ecx, ecx; string
0x1800ea381  call    cs:__imp_WindowsDeleteString
0x1800ea387  mov     [rbp+var_48], r12
0x1800ea38b  lea     rdx, ?c_tagDescription@@3PEBGEB; ushort const * const c_tagDescription
0x1800ea392  lea     rcx, [rbp+var_30]
0x1800ea396  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ea39b  nop
0x1800ea39c  lea     r8, [rbp+var_48]
0x1800ea3a0  mov     rdx, [rax+18h]
0x1800ea3a4  mov     rcx, rdi
0x1800ea3a7  mov     rax, rbx
0x1800ea3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea3af  nop
0x1800ea3b0  test    eax, eax
0x1800ea3b2  jnz     short loc_1800EA3D9
0x1800ea3b4  xor     edx, edx; length
0x1800ea3b6  mov     rcx, [rbp+var_48]; string
0x1800ea3ba  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ea3c0  mov     r8, rsi
0x1800ea3c3  inc     r8
0x1800ea3c6  cmp     [rax+r8*2], r12w
0x1800ea3cb  jnz     short loc_1800EA3C3
0x1800ea3cd  lea     rcx, [r14+20h]
0x1800ea3d1  mov     rdx, rax
0x1800ea3d4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ea3d9  mov     [rbp+var_50], r12
0x1800ea3dd  mov     rdi, [r15]
0x1800ea3e0  mov     rax, [rdi]
0x1800ea3e3  mov     rbx, [rax+50h]
0x1800ea3e7  xor     ecx, ecx; string
0x1800ea3e9  call    cs:__imp_WindowsDeleteString
0x1800ea3ef  mov     [rbp+var_50], r12
0x1800ea3f3  lea     rdx, ?c_tagVersion@@3PEBGEB; ushort const * const c_tagVersion
0x1800ea3fa  lea     rcx, [rbp+var_30]
0x1800ea3fe  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ea403  nop
0x1800ea404  lea     r8, [rbp+var_50]
0x1800ea408  mov     rdx, [rax+18h]
0x1800ea40c  mov     rcx, rdi
0x1800ea40f  mov     rax, rbx
0x1800ea412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea417  mov     ebx, eax
0x1800ea419  test    eax, eax
0x1800ea41b  jns     short loc_1800EA43A
0x1800ea41d  mov     rcx, [rbp+28h]; this
0x1800ea421  mov     r9d, eax; char *
0x1800ea424  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ea42b  mov     edx, 700h; void *
0x1800ea430  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea435  jmp     loc_1800EA504
0x1800ea43a  xor     edx, edx; length
0x1800ea43c  mov     rcx, [rbp+var_50]; string
0x1800ea440  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ea446  mov     r8, rsi
0x1800ea449  inc     r8
0x1800ea44c  cmp     [rax+r8*2], r12w
0x1800ea451  jnz     short loc_1800EA449
0x1800ea453  lea     rcx, [r14+40h]
0x1800ea457  mov     rdx, rax
0x1800ea45a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ea45f  mov     [rbp+var_40], r12
0x1800ea463  mov     rdi, [r15]
0x1800ea466  mov     rax, [rdi]
0x1800ea469  mov     rbx, [rax+50h]
0x1800ea46d  xor     ecx, ecx; string
0x1800ea46f  call    cs:__imp_WindowsDeleteString
0x1800ea475  mov     [rbp+var_40], r12
0x1800ea479  lea     rdx, ?c_tagSchemaVersion@@3PEBGEB; ushort const * const c_tagSchemaVersion
0x1800ea480  lea     rcx, [rbp+var_30]
0x1800ea484  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ea489  nop
0x1800ea48a  lea     r8, [rbp+var_40]
0x1800ea48e  mov     rdx, [rax+18h]
0x1800ea492  mov     rcx, rdi
0x1800ea495  mov     rax, rbx
0x1800ea498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea49d  mov     ebx, eax
0x1800ea49f  test    eax, eax
0x1800ea4a1  jns     short loc_1800EA4AA
0x1800ea4a3  mov     edx, 704h
0x1800ea4a8  jmp     short loc_1800EA4E2
0x1800ea4aa  xor     edx, edx; length
0x1800ea4ac  mov     rcx, [rbp+var_40]; string
0x1800ea4b0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ea4b6  inc     rsi
0x1800ea4b9  cmp     [rax+rsi*2], r12w
0x1800ea4be  jnz     short loc_1800EA4B6
0x1800ea4c0  lea     rcx, [r14+60h]
0x1800ea4c4  mov     r8, rsi
0x1800ea4c7  mov     rdx, rax
0x1800ea4ca  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ea4cf  mov     rcx, r14; struct SCDDocument *
0x1800ea4d2  call    ?ValidateScdDocumentHeader@@YAJAEBVSCDDocument@@@Z; ValidateScdDocumentHeader(SCDDocument const &)
0x1800ea4d7  mov     ebx, eax
0x1800ea4d9  test    eax, eax
0x1800ea4db  jns     short loc_1800EA4F6
0x1800ea4dd  mov     edx, 707h; void *
0x1800ea4e2  mov     r9d, eax; char *
0x1800ea4e5  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ea4ec  mov     rcx, [rbp+28h]; this
0x1800ea4f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea4f5  nop
0x1800ea4f6  mov     rcx, [rbp+var_40]; string
0x1800ea4fa  call    cs:__imp_WindowsDeleteString
0x1800ea500  mov     [rbp+var_40], r12
0x1800ea504  mov     rcx, [rbp+var_50]; string
0x1800ea508  call    cs:__imp_WindowsDeleteString
0x1800ea50e  mov     [rbp+var_50], r12
0x1800ea512  mov     rcx, [rbp+var_48]; string
0x1800ea516  call    cs:__imp_WindowsDeleteString
0x1800ea51c  mov     [rbp+var_48], r12
0x1800ea520  mov     rcx, [rbp+string]; string
0x1800ea524  call    cs:__imp_WindowsDeleteString
0x1800ea52a  mov     eax, ebx
0x1800ea52c  mov     rcx, [rbp+var_10]
0x1800ea530  xor     rcx, rsp; StackCookie
0x1800ea533  call    __security_check_cookie
0x1800ea538  lea     r11, [rsp+70h+var_s0]
0x1800ea53d  mov     rbx, [r11+40h]
0x1800ea541  mov     rsi, [r11+48h]
0x1800ea545  mov     rsp, r11
0x1800ea548  pop     r15
0x1800ea54a  pop     r14
0x1800ea54c  pop     r12
0x1800ea54e  pop     rdi
0x1800ea54f  pop     rbp
0x1800ea550  retn
```
