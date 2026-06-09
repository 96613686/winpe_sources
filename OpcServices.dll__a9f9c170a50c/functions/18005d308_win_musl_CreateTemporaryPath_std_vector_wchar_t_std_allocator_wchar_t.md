# win_musl::CreateTemporaryPath(std::vector<wchar_t,std::allocator<wchar_t>> &)

- ea: `0x18005d308`
- end: `0x18005d4cd`
- name: `?CreateTemporaryPath@win_musl@@YAXAEAV?$vector@_WV?$allocator@_W@std@@@std@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18005bb04`

## callees

- `0x18001a810`
- `0x18001f7c0`
- `0x1800460f0`
- `0x1800517a0`
- `0x18005d308`
- `0x18005d4d4`
- `0x1800654b0`
- `0x180079ca0`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18005d3cb`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18005d3cb`

## string_xrefs

- `0x18005d3db`: `GetTempPath returned.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall win_musl::CreateTemporaryPath(__int64 a1)
{
  DWORD v2; // esi
  DWORD TempPathW; // edi
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  win_musl::Formatter *v14; // rax
  struct win_musl::TStringEllipseBase *v15; // rbx
  win_musl::detail *v16; // rcx
  unsigned int LastErrorAsFailHR; // eax
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 result; // rax
  __int16 v28; // [rsp+40h] [rbp-158h] BYREF
  __int64 v29; // [rsp+48h] [rbp-150h]
  _BYTE v30[48]; // [rsp+50h] [rbp-148h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+80h] [rbp-118h] BYREF
  _BYTE v32[96]; // [rsp+120h] [rbp-78h] BYREF

  v29 = -2;
  v2 = 0;
  TempPathW = 0;
  while ( 1 )
  {
    v4 = TempPathW + 1;
    if ( TempPathW < v2 )
      break;
    if ( TempPathW + 1 <= 0x104 )
    {
      v4 = 260;
    }
    else if ( v4 >= 0x10000 )
    {
      v4 = 0x10000;
    }
    v28 = 0;
    v5 = std::vector<wchar_t>::size(a1, v4);
    if ( v5 >= v6 )
    {
      v12 = std::vector<wchar_t>::size(v7, v6);
      if ( v11 < v12 )
      {
        v13 = *(_QWORD *)(a1 + 8) + 2 * v11;
        if ( v13 != *(_QWORD *)(a1 + 16) )
          *(_QWORD *)(a1 + 16) = v13;
      }
    }
    else
    {
      v8 = std::vector<wchar_t>::size(v7, v6);
      std::vector<wchar_t>::_Insert_n(v10, *(_BYTE **)(a1 + 16), v9 - v8, &v28);
    }
    v2 = std::vector<wchar_t>::size(a1, v11);
    **(_WORD **)(a1 + 8) = 0;
    TempPathW = GetTempPathW(v2, *(LPWSTR *)(a1 + 8));
    if ( !TempPathW )
    {
      std::wstring::wstring(v30, L"GetTempPath returned.");
      v14 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v32, v30);
      v15 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v14);
      LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v16);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xA7u,
        LastErrorAsFailHR,
        v15);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  v28 = 0;
  v18 = std::vector<wchar_t>::size(a1, v4);
  if ( v18 >= v19 )
  {
    v24 = std::vector<wchar_t>::size(v20, v19);
    if ( v25 < v24 )
    {
      v26 = *(_QWORD *)(a1 + 8) + 2 * v25;
      if ( v26 != *(_QWORD *)(a1 + 16) )
        *(_QWORD *)(a1 + 16) = v26;
    }
  }
  else
  {
    v21 = std::vector<wchar_t>::size(v20, v19);
    std::vector<wchar_t>::_Insert_n(v23, *(_BYTE **)(a1 + 16), v22 - v21, &v28);
  }
  result = 0;
  *(_WORD *)(*(_QWORD *)(a1 + 8) + 2LL * TempPathW) = 0;
  return result;
}

```

## disassembly

```asm
0x18005d308  mov     rax, rsp
0x18005d30b  push    rdi
0x18005d30c  sub     rsp, 190h
0x18005d313  mov     [rsp+198h+var_150], 0FFFFFFFFFFFFFFFEh
0x18005d31c  mov     [rax+10h], rbx
0x18005d320  mov     [rax+18h], rsi
0x18005d324  mov     rax, cs:__security_cookie
0x18005d32b  xor     rax, rsp
0x18005d32e  mov     [rsp+198h+var_18], rax
0x18005d336  mov     rbx, rcx
0x18005d339  xor     esi, esi
0x18005d33b  xor     edi, edi
0x18005d33d  lea     eax, [rdi+1]
0x18005d340  mov     edx, eax
0x18005d342  cmp     edi, esi
0x18005d344  jb      loc_18005D451
0x18005d34a  cmp     eax, 104h
0x18005d34f  jbe     short loc_18005D361
0x18005d351  cmp     rdx, 10000h
0x18005d358  jb      short loc_18005D366
0x18005d35a  mov     edx, 10000h
0x18005d35f  jmp     short loc_18005D366
0x18005d361  mov     edx, 104h
0x18005d366  xor     eax, eax
0x18005d368  mov     [rsp+198h+var_158], ax
0x18005d36d  mov     rcx, rbx
0x18005d370  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x18005d375  cmp     rax, rdx
0x18005d378  jnb     short loc_18005D395
0x18005d37a  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x18005d37f  sub     rdx, rax
0x18005d382  lea     r9, [rsp+198h+var_158]
0x18005d387  mov     r8, rdx
0x18005d38a  mov     rdx, [rbx+10h]
0x18005d38e  call    ?_Insert_n@?$vector@_WV?$allocator@_W@std@@@std@@IEAAXV?$_Vector_iterator@_WV?$allocator@_W@std@@@2@_KAEB_W@Z; std::vector<wchar_t>::_Insert_n(std::_Vector_iterator<wchar_t>,unsigned __int64,wchar_t const &)
0x18005d393  jmp     short loc_18005D3B1
0x18005d395  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x18005d39a  cmp     rdx, rax
0x18005d39d  jnb     short loc_18005D3B1
0x18005d39f  mov     rax, [rbx+8]
0x18005d3a3  lea     rcx, [rax+rdx*2]
0x18005d3a7  cmp     rcx, [rbx+10h]
0x18005d3ab  jz      short loc_18005D3B1
0x18005d3ad  mov     [rbx+10h], rcx
0x18005d3b1  mov     rcx, rbx
0x18005d3b4  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x18005d3b9  mov     rsi, rax
0x18005d3bc  mov     rdx, [rbx+8]
0x18005d3c0  xor     ecx, ecx
0x18005d3c2  mov     [rdx], cx
0x18005d3c5  mov     rdx, [rbx+8]; lpBuffer
0x18005d3c9  mov     ecx, eax; nBufferLength
0x18005d3cb  call    cs:__imp_GetTempPathW
0x18005d3d1  mov     edi, eax
0x18005d3d3  test    eax, eax
0x18005d3d5  jnz     loc_18005D33D
0x18005d3db  lea     rdx, aGettemppathRet; "GetTempPath returned."
0x18005d3e2  lea     rcx, [rsp+198h+var_148]
0x18005d3e7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18005d3ec  nop
0x18005d3ed  lea     rdx, [rsp+198h+var_148]
0x18005d3f2  lea     rcx, [rsp+198h+var_78]
0x18005d3fa  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18005d3ff  nop
0x18005d400  mov     rcx, rax; this
0x18005d403  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18005d408  mov     rbx, rax
0x18005d40b  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18005d410  mov     [rsp+198h+var_168], rbx; struct win_musl::TStringEllipseBase *
0x18005d415  mov     [rsp+198h+var_170], eax; unsigned int
0x18005d419  mov     [rsp+198h+var_178], 0A7h; unsigned int
0x18005d421  lea     r9, word_18013A0B6
0x18005d428  lea     r8, aNoFilename; "(no filename)"
0x18005d42f  lea     rcx, [rsp+198h+pExceptionObject]; this
0x18005d437  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18005d43c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18005d443  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x18005d44b  call    _CxxThrowException_0
0x18005d451  xor     eax, eax
0x18005d453  mov     [rsp+198h+var_158], ax
0x18005d458  mov     rcx, rbx
0x18005d45b  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x18005d460  cmp     rax, rdx
0x18005d463  jnb     short loc_18005D480
0x18005d465  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x18005d46a  sub     rdx, rax
0x18005d46d  lea     r9, [rsp+198h+var_158]
0x18005d472  mov     r8, rdx
0x18005d475  mov     rdx, [rbx+10h]
0x18005d479  call    ?_Insert_n@?$vector@_WV?$allocator@_W@std@@@std@@IEAAXV?$_Vector_iterator@_WV?$allocator@_W@std@@@2@_KAEB_W@Z; std::vector<wchar_t>::_Insert_n(std::_Vector_iterator<wchar_t>,unsigned __int64,wchar_t const &)
0x18005d47e  jmp     short loc_18005D49C
0x18005d480  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x18005d485  cmp     rdx, rax
0x18005d488  jnb     short loc_18005D49C
0x18005d48a  mov     rax, [rbx+8]
0x18005d48e  lea     rcx, [rax+rdx*2]
0x18005d492  cmp     rcx, [rbx+10h]
0x18005d496  jz      short loc_18005D49C
0x18005d498  mov     [rbx+10h], rcx
0x18005d49c  mov     edx, edi
0x18005d49e  mov     rcx, [rbx+8]
0x18005d4a2  xor     eax, eax
0x18005d4a4  mov     [rcx+rdx*2], ax
0x18005d4a8  mov     rcx, [rsp+198h+var_18]
0x18005d4b0  xor     rcx, rsp; StackCookie
0x18005d4b3  call    __security_check_cookie
0x18005d4b8  lea     r11, [rsp+198h+var_8]
0x18005d4c0  mov     rbx, [r11+18h]
0x18005d4c4  mov     rsi, [r11+20h]
0x18005d4c8  mov     rsp, r11
0x18005d4cb  pop     rdi
0x18005d4cc  retn
```
