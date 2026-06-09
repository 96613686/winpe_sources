# UpdateDiagnostics::update_diagnostics::GetUpdateStatusJson(void)

- ea: `0x18004ba04`
- end: `0x18004bb49`
- name: `?GetUpdateStatusJson@update_diagnostics@UpdateDiagnostics@@QEAA?AUhstring_view@2@XZ`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180048fe4`

## callees

- `0x180034a30`
- `0x18004b74c`
- `0x18004b8b8`
- `0x18004b96c`
- `0x18004ba04`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004baee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bafe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004baee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bafe`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HSTRING __fastcall UpdateDiagnostics::update_diagnostics::GetUpdateStatusJson(__int64 a1, HSTRING a2)
{
  __int64 v4; // rbx
  int v5; // edx
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rax
  int v11; // [rsp+20h] [rbp-29h]
  __int64 v12[3]; // [rsp+40h] [rbp-9h] BYREF
  __int64 v13; // [rsp+58h] [rbp+Fh]
  HSTRING v14; // [rsp+60h] [rbp+17h] BYREF
  HSTRING string; // [rsp+68h] [rbp+1Fh] BYREF
  __int128 v16; // [rsp+70h] [rbp+27h] BYREF
  __int64 v17; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v14 = a2;
  v16 = 0;
  v17 = 0;
  *(_OWORD *)v12 = 0u;
  UpdateDiagnostics::update_diagnostics::_CreateHStringArray((__int64)&v16, v12);
  v14 = 0;
  *(_OWORD *)v12 = 0;
  v4 = UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(v12, &v14);
  string = 0;
  *(_OWORD *)v12 = 0;
  v5 = UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(v12, &string);
  v13 = 0;
  v6 = *(__int64 **)(a1 + 8);
  v7 = *v6;
  v13 = 0;
  v11 = v5;
  v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, __int64))(v7 + 64))(
         v6,
         0,
         (__int64)(*((_QWORD *)&v16 + 1) - v16) >> 3,
         v4);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
      (const char *)(unsigned int)v8,
      v11);
  v9 = v13;
  v13 = 0;
  *(_QWORD *)a2 = v9;
  if ( string )
    WindowsDeleteString(string);
  if ( v14 )
    WindowsDeleteString(v14);
  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&v16);
  return a2;
}

```

## disassembly

```asm
0x18004ba04  mov     [rsp-8+arg_10], rbx
0x18004ba09  push    rbp
0x18004ba0a  push    rsi
0x18004ba0b  push    rdi
0x18004ba0c  lea     rbp, [rsp-47h]
0x18004ba11  sub     rsp, 90h
0x18004ba18  mov     rax, cs:__security_cookie
0x18004ba1f  xor     rax, rsp
0x18004ba22  mov     [rbp+57h+var_18], rax
0x18004ba26  mov     rsi, rdx
0x18004ba29  mov     rdi, rcx
0x18004ba2c  mov     [rbp+57h+var_40], rdx
0x18004ba30  xorps   xmm0, xmm0
0x18004ba33  xor     eax, eax
0x18004ba35  movups  [rbp+57h+var_30], xmm0
0x18004ba39  mov     [rbp+57h+var_20], rax
0x18004ba3d  mov     [rbp+57h+var_60], rax
0x18004ba41  mov     [rbp+57h+var_60+8], rax
0x18004ba45  lea     rdx, [rbp+57h+var_60]
0x18004ba49  lea     rcx, [rbp+57h+var_30]
0x18004ba4d  call    ?_CreateHStringArray@update_diagnostics@UpdateDiagnostics@@CA?AV?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@V?$span@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@4@@Z; UpdateDiagnostics::update_diagnostics::_CreateHStringArray(std::span<std::wstring_view const,-1>)
0x18004ba52  nop
0x18004ba53  mov     [rbp+57h+var_40], 0
0x18004ba5b  xorps   xmm0, xmm0
0x18004ba5e  movdqa  xmmword ptr [rbp+57h+var_60], xmm0
0x18004ba63  lea     rdx, [rbp+57h+var_40]
0x18004ba67  lea     rcx, [rbp+57h+var_60]
0x18004ba6b  call    ?_CreateOptionalHString@update_diagnostics@UpdateDiagnostics@@CAPEAUHSTRING__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18004ba70  mov     rbx, rax
0x18004ba73  mov     [rbp+57h+string], 0
0x18004ba7b  xorps   xmm0, xmm0
0x18004ba7e  movdqa  xmmword ptr [rbp+57h+var_60], xmm0
0x18004ba83  lea     rdx, [rbp+57h+string]
0x18004ba87  lea     rcx, [rbp+57h+var_60]
0x18004ba8b  call    ?_CreateOptionalHString@update_diagnostics@UpdateDiagnostics@@CAPEAUHSTRING__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18004ba90  mov     rdx, rax
0x18004ba93  mov     [rbp+57h+var_48], 0
0x18004ba9b  mov     rcx, [rdi+8]
0x18004ba9f  mov     rax, [rcx]
0x18004baa2  mov     [rbp+57h+var_48], 0
0x18004baaa  mov     r8, qword ptr [rbp+57h+var_30+8]
0x18004baae  sub     r8, qword ptr [rbp+57h+var_30]
0x18004bab2  sar     r8, 3
0x18004bab6  lea     r9, [rbp+57h+var_48]
0x18004baba  mov     [rsp+0A0h+var_78], r9
0x18004babf  mov     qword ptr [rsp+0A0h+var_80], rdx; int
0x18004bac4  mov     r9, rbx
0x18004bac7  xor     edx, edx
0x18004bac9  mov     rax, [rax+40h]
0x18004bacd  call    _guard_dispatch_icall
0x18004bad2  test    eax, eax
0x18004bad4  js      short loc_18004BB30
0x18004bad6  mov     rax, [rbp+57h+var_48]
0x18004bada  mov     [rbp+57h+var_48], 0
0x18004bae2  mov     [rsi], rax
0x18004bae5  mov     rcx, [rbp+57h+string]; string
0x18004bae9  test    rcx, rcx
0x18004baec  jz      short loc_18004BAF5
0x18004baee  call    cs:__imp_WindowsDeleteString
0x18004baf4  nop
0x18004baf5  mov     rcx, [rbp+57h+var_40]; string
0x18004baf9  test    rcx, rcx
0x18004bafc  jz      short loc_18004BB05
0x18004bafe  call    cs:__imp_WindowsDeleteString
0x18004bb04  nop
0x18004bb05  lea     rcx, [rbp+57h+var_30]
0x18004bb09  call    ??1?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18004bb0e  mov     rax, rsi
0x18004bb11  mov     rcx, [rbp+57h+var_18]
0x18004bb15  xor     rcx, rsp; StackCookie
0x18004bb18  call    __security_check_cookie
0x18004bb1d  mov     rbx, [rsp+0A0h+arg_10]
0x18004bb25  add     rsp, 90h
0x18004bb2c  pop     rdi
0x18004bb2d  pop     rsi
0x18004bb2e  pop     rbp
0x18004bb2f  retn
0x18004bb30  mov     rcx, [rbp+5Fh]; this
0x18004bb34  mov     r9d, eax; char *
0x18004bb37  lea     r8, aCW1SSrcCalliop; "C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDi"...
0x18004bb3e  mov     edx, 138h; void *
0x18004bb43  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
