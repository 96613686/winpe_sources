# CommandImpl::Analyze(std::filesystem::path const &)

- ea: `0x180048fe4`
- end: `0x1800491e9`
- name: `?Analyze@CommandImpl@@CAXAEBVpath@filesystem@std@@@Z`
- size: `517`
- prototype: `void __fastcall(const struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180048d58`

## callees

- `0x180009380`
- `0x1800338a4`
- `0x1800439a4`
- `0x180048978`
- `0x1800489c4`
- `0x180048fe4`
- `0x180049214`
- `0x1800498b0`
- `0x18004b3f0`
- `0x18004ba04`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049196`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800491a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049196`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800491a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800490b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004910d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004916c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800490b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004910d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004916c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CommandImpl::Analyze(const struct std::filesystem::path *a1)
{
  _QWORD *LoadFailureMessage; // rax
  __int64 v3; // r8
  HSTRING v4; // rbx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rdi
  HSTRING v7; // rdi
  __int64 v8; // r8
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // rax
  HSTRING string; // [rsp+20h] [rbp-60h] BYREF
  HSTRING v12; // [rsp+28h] [rbp-58h] BYREF
  UINT32 length; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v14[2]; // [rsp+38h] [rbp-48h] BYREF
  char v15; // [rsp+48h] [rbp-38h]
  __int128 v16; // [rsp+50h] [rbp-30h] BYREF
  __int128 v17; // [rsp+60h] [rbp-20h]

  v15 = 0;
  if ( UpdateDiagnosticsLoader::Load((UpdateDiagnosticsLoader *)v14) )
  {
    UpdateDiagnostics::update_diagnostics::GetUpdateStatusJson((unsigned __int64)v14 & -(__int64)(v15 != 0), &string);
    v4 = string;
    if ( *((_QWORD *)a1 + 2) )
    {
      v5 = (unsigned __int64)v14 & -(__int64)(v15 != 0);
      v16 = 0;
      v17 = 0;
      if ( string )
      {
        length = 0;
        WindowsGetStringRawBuffer(string, &length);
      }
      std::wstring::_Construct<1,wchar_t const *>(&v16);
      CommandImpl::WriteStatusToFile(&v16, v5, a1);
      std::wstring::~wstring(&v16);
    }
    else
    {
      v6 = (unsigned __int64)v14 & -(__int64)(v15 != 0);
      if ( string )
      {
        length = 0;
        WindowsGetStringRawBuffer(string, &length);
      }
      v16 = 0;
      v17 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v16);
      UpdateDiagnostics::update_diagnostics::FormatAsConsole(v6, &v12, &v16);
      std::wstring::~wstring(&v16);
      v7 = v12;
      if ( v12 )
      {
        length = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(v12, &length);
        v8 = length;
      }
      else
      {
        v8 = 0;
        StringRawBuffer = 0;
      }
      v10 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(&std::wcout, StringRawBuffer, v8);
      std::endl<wchar_t,std::char_traits<wchar_t>>(v10);
      if ( v7 )
        WindowsDeleteString(v7);
    }
    if ( v4 )
      WindowsDeleteString(v4);
  }
  else
  {
    LoadFailureMessage = (_QWORD *)UpdateDiagnosticsLoader::GetLoadFailureMessage(&v16);
    v3 = LoadFailureMessage[2];
    if ( LoadFailureMessage[3] > 7u )
      LoadFailureMessage = (_QWORD *)*LoadFailureMessage;
    std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(&std::wcerr, LoadFailureMessage, v3);
    std::wstring::~wstring(&v16);
  }
  if ( v15 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))v14[0])(v14, 0);
}

```

## disassembly

```asm
0x180048fe4  mov     [rsp-8+arg_8], rbx
0x180048fe9  mov     [rsp-8+arg_10], rsi
0x180048fee  mov     [rsp-8+arg_18], rdi
0x180048ff3  push    rbp
0x180048ff4  mov     rbp, rsp
0x180048ff7  sub     rsp, 80h
0x180048ffe  mov     rax, cs:__security_cookie
0x180049005  xor     rax, rsp
0x180049008  mov     [rbp+var_10], rax
0x18004900c  mov     rsi, rcx
0x18004900f  mov     [rbp+var_38], 0
0x180049013  lea     rcx, [rbp+var_48]; this
0x180049017  call    ?Load@UpdateDiagnosticsLoader@@QEAA_NXZ; UpdateDiagnosticsLoader::Load(void)
0x18004901c  test    al, al
0x18004901e  jnz     short loc_180049056
0x180049020  lea     rcx, [rbp+var_30]
0x180049024  call    ?GetLoadFailureMessage@UpdateDiagnosticsLoader@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UpdateDiagnosticsLoader::GetLoadFailureMessage(void)
0x180049029  nop
0x18004902a  mov     r8, [rax+10h]
0x18004902e  cmp     qword ptr [rax+18h], 7
0x180049033  jbe     short loc_180049038
0x180049035  mov     rax, [rax]
0x180049038  mov     rdx, rax
0x18004903b  lea     rcx, ?wcerr@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcerr
0x180049042  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x180049047  nop
0x180049048  lea     rcx, [rbp+var_30]; void *
0x18004904c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049051  jmp     loc_1800491AC
0x180049056  mov     al, [rbp+var_38]
0x180049059  neg     al
0x18004905b  sbb     rcx, rcx
0x18004905e  lea     rax, [rbp+var_48]
0x180049062  and     rcx, rax
0x180049065  lea     rdx, [rbp+string]
0x180049069  call    ?GetUpdateStatusJson@update_diagnostics@UpdateDiagnostics@@QEAA?AUhstring_view@2@XZ; UpdateDiagnostics::update_diagnostics::GetUpdateStatusJson(void)
0x18004906e  nop
0x18004906f  mov     al, [rbp+var_38]
0x180049072  mov     rbx, [rbp+string]
0x180049076  cmp     qword ptr [rsi+10h], 0
0x18004907b  jz      short loc_1800490E7
0x18004907d  neg     al
0x18004907f  sbb     rdi, rdi
0x180049082  lea     rax, [rbp+var_48]
0x180049086  and     rdi, rax
0x180049089  xorps   xmm0, xmm0
0x18004908c  movups  [rbp+var_30], xmm0
0x180049090  xorps   xmm1, xmm1
0x180049093  movdqu  [rbp+var_20], xmm1
0x180049098  test    rbx, rbx
0x18004909b  jnz     short loc_1800490A4
0x18004909d  xor     eax, eax
0x18004909f  xor     r8d, r8d
0x1800490a2  jmp     short loc_1800490BC
0x1800490a4  mov     [rbp+length], 0
0x1800490ab  lea     rdx, [rbp+length]; length
0x1800490af  mov     rcx, rbx; string
0x1800490b2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800490b8  mov     r8d, [rbp+length]
0x1800490bc  mov     rdx, rax
0x1800490bf  lea     rcx, [rbp+var_30]
0x1800490c3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800490c8  nop
0x1800490c9  mov     r8, rsi
0x1800490cc  mov     rdx, rdi
0x1800490cf  lea     rcx, [rbp+var_30]
0x1800490d3  call    ?WriteStatusToFile@CommandImpl@@CAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUupdate_diagnostics@UpdateDiagnostics@@AEBVpath@filesystem@3@@Z; CommandImpl::WriteStatusToFile(std::wstring const &,UpdateDiagnostics::update_diagnostics *,std::filesystem::path const &)
0x1800490d8  nop
0x1800490d9  lea     rcx, [rbp+var_30]; void *
0x1800490dd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800490e2  jmp     loc_18004919D
0x1800490e7  neg     al
0x1800490e9  sbb     rdi, rdi
0x1800490ec  lea     rax, [rbp+var_48]
0x1800490f0  and     rdi, rax
0x1800490f3  test    rbx, rbx
0x1800490f6  jnz     short loc_1800490FF
0x1800490f8  xor     r8d, r8d
0x1800490fb  xor     eax, eax
0x1800490fd  jmp     short loc_180049117
0x1800490ff  mov     [rbp+length], 0
0x180049106  lea     rdx, [rbp+length]; length
0x18004910a  mov     rcx, rbx; string
0x18004910d  call    cs:__imp_WindowsGetStringRawBuffer
0x180049113  mov     r8d, [rbp+length]
0x180049117  xorps   xmm0, xmm0
0x18004911a  movups  [rbp+var_30], xmm0
0x18004911e  xorps   xmm1, xmm1
0x180049121  movdqu  [rbp+var_20], xmm1
0x180049126  mov     rdx, rax
0x180049129  lea     rcx, [rbp+var_30]
0x18004912d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180049132  nop
0x180049133  lea     r8, [rbp+var_30]
0x180049137  lea     rdx, [rbp+var_58]
0x18004913b  mov     rcx, rdi
0x18004913e  call    ?FormatAsConsole@update_diagnostics@UpdateDiagnostics@@QEAA?AUhstring_view@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UpdateDiagnostics::update_diagnostics::FormatAsConsole(std::wstring const &)
0x180049143  nop
0x180049144  lea     rcx, [rbp+var_30]; void *
0x180049148  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004914d  nop
0x18004914e  mov     rdi, [rbp+var_58]
0x180049152  test    rdi, rdi
0x180049155  jnz     short loc_18004915E
0x180049157  xor     r8d, r8d
0x18004915a  xor     eax, eax
0x18004915c  jmp     short loc_180049176
0x18004915e  mov     [rbp+length], 0
0x180049165  lea     rdx, [rbp+length]; length
0x180049169  mov     rcx, rdi; string
0x18004916c  call    cs:__imp_WindowsGetStringRawBuffer
0x180049172  mov     r8d, [rbp+length]
0x180049176  mov     rdx, rax
0x180049179  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x180049180  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x180049185  mov     rcx, rax
0x180049188  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x18004918d  nop
0x18004918e  test    rdi, rdi
0x180049191  jz      short loc_18004919D
0x180049193  mov     rcx, rdi; string
0x180049196  call    cs:__imp_WindowsDeleteString
0x18004919c  nop
0x18004919d  test    rbx, rbx
0x1800491a0  jz      short loc_1800491AC
0x1800491a2  mov     rcx, rbx; string
0x1800491a5  call    cs:__imp_WindowsDeleteString
0x1800491ab  nop
0x1800491ac  cmp     [rbp+var_38], 0
0x1800491b0  jz      short loc_1800491C4
0x1800491b2  mov     rax, [rbp+var_48]
0x1800491b6  xor     edx, edx
0x1800491b8  lea     rcx, [rbp+var_48]
0x1800491bc  mov     rax, [rax]
0x1800491bf  call    _guard_dispatch_icall
0x1800491c4  mov     rcx, [rbp+var_10]
0x1800491c8  xor     rcx, rsp; StackCookie
0x1800491cb  call    __security_check_cookie
0x1800491d0  lea     r11, [rsp+80h+var_s0]
0x1800491d8  mov     rbx, [r11+18h]
0x1800491dc  mov     rsi, [r11+20h]
0x1800491e0  mov     rdi, [r11+28h]
0x1800491e4  mov     rsp, r11
0x1800491e7  pop     rbp
0x1800491e8  retn
```
