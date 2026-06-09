# xpsutil::GetGuidXsId(void)

- ea: `0x1801007cc`
- end: `0x1801009e8`
- name: `?GetGuidXsId@xpsutil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `540`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801005a8`
- `0x180129b80`

## callees

- `0x180012450`
- `0x18003c7f8`
- `0x1800b76e8`
- `0x1800bed3c`
- `0x1800bed64`
- `0x1800c20c4`
- `0x1801007cc`
- `0x180134b70`
- `0x1801355e4`
- `0x1801359ce`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180100896`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180100896`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180100819`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180100819`

## string_xrefs

- `0x180100825`: `CoCreateGuid failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall xpsutil::GetGuidXsId(__int64 a1)
{
  HRESULT v2; // edi
  win_musl::Formatter *v3; // rax
  const wchar_t *v4; // rax
  __int64 v5; // rax
  GUID pguid; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v8[40]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v9[80]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+D0h] [rbp-30h] BYREF
  OLECHAR sz; // [rsp+170h] [rbp+70h] BYREF
  _WORD v12[36]; // [rsp+172h] [rbp+72h] BYREF
  __int16 v13; // [rsp+1BAh] [rbp+BAh]

  pguid = 0;
  memset_0(&sz, 0, 0x80u);
  v2 = CoCreateGuid(&pguid);
  if ( v2 < 0 )
  {
    std::wstring::wstring(v8, L"CoCreateGuid failed");
    v3 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v9, v8);
    v4 = win_musl::Formatter::c_str(v3);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x30u,
      v2,
      (__int64)v4);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( !StringFromGUID2(&pguid, &sz, 64) )
  {
    win_musl::DebugLogHelper(
      "(no filename)",
      &Src,
      53,
      1024,
      -2147418113,
      L"StringFromGUID2 fails when buffer is large enough!");
    std::logic_error::logic_error((std::logic_error *)v8, "Program has entered an unexpected state");
    throw (std::logic_error *)v8;
  }
  v5 = -1;
  do
    ++v5;
  while ( v12[v5 - 1] );
  if ( v5 != 38 || sz != 123 || v13 != 125 )
  {
    win_musl::DebugLogHelper(
      "(no filename)",
      &Src,
      61,
      1024,
      -2147418113,
      L"Unexpected result string from StringFromGUID2 function!");
    std::logic_error::logic_error((std::logic_error *)v8, "Program has entered an unexpected state");
    throw (std::logic_error *)v8;
  }
  if ( (unsigned __int16)(v12[0] - 48) <= 9u )
    v12[0] = (v12[0] - 48) % 6 + 65;
  v13 = 0;
  sz = 0;
  std::wstring::wstring(a1, v12);
  return a1;
}

```

## disassembly

```asm
0x1801007cc  push    rbp
0x1801007ce  push    rbx
0x1801007cf  push    rsi
0x1801007d0  push    rdi
0x1801007d1  lea     rbp, [rsp-108h]
0x1801007d9  sub     rsp, 208h
0x1801007e0  mov     rax, cs:__security_cookie
0x1801007e7  xor     rax, rsp
0x1801007ea  mov     [rbp+120h+var_30], rax
0x1801007f1  mov     rbx, rcx
0x1801007f4  mov     qword ptr [rsp+220h+pguid.Data1], rcx
0x1801007f9  xor     esi, esi
0x1801007fb  xorps   xmm0, xmm0
0x1801007fe  movups  xmmword ptr [rsp+220h+pguid.Data1], xmm0
0x180100803  xor     edx, edx; Val
0x180100805  mov     r8d, 80h; Size
0x18010080b  lea     rcx, [rbp+120h+sz]; void *
0x18010080f  call    memset_0
0x180100814  lea     rcx, [rsp+220h+pguid]; pguid
0x180100819  call    cs:__imp_CoCreateGuid
0x18010081f  mov     edi, eax
0x180100821  test    eax, eax
0x180100823  jns     short loc_180100887
0x180100825  lea     rdx, aCocreateguidFa; "CoCreateGuid failed"
0x18010082c  lea     rcx, [rsp+220h+var_1C8]
0x180100831  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180100836  nop
0x180100837  lea     rdx, [rsp+220h+var_1C8]
0x18010083c  lea     rcx, [rbp+120h+var_1A0]
0x180100840  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180100845  nop
0x180100846  mov     rcx, rax; this
0x180100849  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18010084e  mov     [rsp+220h+var_1F0], rax; __int64
0x180100853  mov     [rsp+220h+var_1F8], edi; int
0x180100857  mov     [rsp+220h+var_200], 30h ; '0'; unsigned int
0x18010085f  lea     r9, Src
0x180100866  lea     r8, aNoFilename; "(no filename)"
0x18010086d  lea     rcx, [rbp+120h+pExceptionObject]; this
0x180100871  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180100876  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010087d  lea     rcx, [rbp+120h+pExceptionObject]; pExceptionObject
0x180100881  call    _CxxThrowException_0
0x180100887  mov     r8d, 40h ; '@'; cchMax
0x18010088d  lea     rdx, [rbp+120h+sz]; lpsz
0x180100891  lea     rcx, [rsp+220h+pguid]; rguid
0x180100896  call    cs:__imp_StringFromGUID2
0x18010089c  test    eax, eax
0x18010089e  jnz     short loc_1801008F6
0x1801008a0  lea     rax, aStringfromguid; "StringFromGUID2 fails when buffer is la"...
0x1801008a7  mov     qword ptr [rsp+220h+var_1F8], rax
0x1801008ac  mov     [rsp+220h+var_200], 8000FFFFh
0x1801008b4  mov     r9d, 400h
0x1801008ba  mov     r8d, 35h ; '5'
0x1801008c0  lea     rdx, Src
0x1801008c7  lea     rcx, aNoFilename; "(no filename)"
0x1801008ce  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x1801008d3  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x1801008da  lea     rcx, [rsp+220h+var_1C8]; this
0x1801008df  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x1801008e4  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x1801008eb  lea     rcx, [rsp+220h+var_1C8]; pExceptionObject
0x1801008f0  call    _CxxThrowException_0
0x1801008f6  lea     rcx, [rbp+120h+sz]
0x1801008fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801008fe  inc     rax
0x180100901  cmp     [rcx+rax*2], si
0x180100905  jnz     short loc_1801008FE
0x180100907  cmp     rax, 26h ; '&'
0x18010090b  jnz     loc_180100992
0x180100911  cmp     [rbp+120h+sz], 7Bh ; '{'
0x180100916  jnz     short loc_180100992
0x180100918  cmp     [rbp+120h+var_66], 7Dh ; '}'
0x180100920  jnz     short loc_180100992
0x180100922  movzx   eax, [rbp+120h+var_AE]
0x180100926  mov     ecx, 30h ; '0'
0x18010092b  sub     ax, cx
0x18010092e  cmp     ax, 9
0x180100932  ja      short loc_18010095D
0x180100934  movzx   r8d, [rbp+120h+var_AE]
0x180100939  sub     r8d, ecx
0x18010093c  mov     eax, 2AAAAAABh
0x180100941  imul    r8d
0x180100944  mov     eax, edx
0x180100946  shr     eax, 1Fh
0x180100949  add     edx, eax
0x18010094b  lea     ecx, [rdx+rdx*2]
0x18010094e  add     ecx, ecx
0x180100950  sub     r8d, ecx
0x180100953  add     r8w, 41h ; 'A'
0x180100958  mov     [rbp+120h+var_AE], r8w
0x18010095d  mov     [rbp+120h+var_66], si
0x180100964  mov     [rbp+120h+sz], si
0x180100968  lea     rdx, [rbp+120h+var_AE]
0x18010096c  mov     rcx, rbx
0x18010096f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180100974  mov     rax, rbx
0x180100977  mov     rcx, [rbp+120h+var_30]
0x18010097e  xor     rcx, rsp; StackCookie
0x180100981  call    __security_check_cookie
0x180100986  add     rsp, 208h
0x18010098d  pop     rdi
0x18010098e  pop     rsi
0x18010098f  pop     rbx
0x180100990  pop     rbp
0x180100991  retn
0x180100992  lea     rax, aUnexpectedResu; "Unexpected result string from StringFro"...
0x180100999  mov     qword ptr [rsp+220h+var_1F8], rax
0x18010099e  mov     [rsp+220h+var_200], 8000FFFFh
0x1801009a6  mov     r9d, 400h
0x1801009ac  mov     r8d, 3Dh ; '='
0x1801009b2  lea     rdx, Src
0x1801009b9  lea     rcx, aNoFilename; "(no filename)"
0x1801009c0  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x1801009c5  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x1801009cc  lea     rcx, [rsp+220h+var_1C8]; this
0x1801009d1  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x1801009d6  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x1801009dd  lea     rcx, [rsp+220h+var_1C8]; pExceptionObject
0x1801009e2  call    _CxxThrowException_0
```
