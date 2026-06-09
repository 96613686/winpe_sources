# Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)

- ea: `0x180022fa0`
- end: `0x180023115`
- name: `?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z`
- size: `373`
- prototype: `__int64 __fastcall(HINTERNET *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180025958`

## callees

- `0x1800045d0`
- `0x180010744`
- `0x180013d68`
- `0x180017a20`
- `0x180022a80`
- `0x180022fa0`

## import_xrefs

- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800230aa`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800230aa`

## string_xrefs

- `0x1800230bf`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(
        HINTERNET *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned __int64 v9; // r14
  __int64 v10; // r8
  __int64 v11; // r8
  const WCHAR *v12; // rdx
  const char *v13; // r9
  unsigned int LastError; // ebx
  const char *v15; // r9
  __int64 result; // rax
  LPCWSTR lpszHeaders[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v18; // [rsp+30h] [rbp-48h]
  unsigned __int64 v19; // [rsp+38h] [rbp-40h]
  int v20; // [rsp+40h] [rbp-38h]
  __int16 v21; // [rsp+44h] [rbp-34h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  try
  {
    v20 = 2097210;
    v21 = 0;
    v9 = (unsigned int)(v7 + v8) + 2LL;
    *(_OWORD *)lpszHeaders = 0;
    v18 = 0;
    v19 = 7;
    LOWORD(lpszHeaders[0]) = 0;
    if ( v9 >= 8 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_7f96eb1dcf99da5daec8c2467d2d5499_,>(lpszHeaders);
      v18 = 0;
    }
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    std::wstring::_Append<unsigned short>(lpszHeaders);
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)&v20 + v11) );
    std::wstring::_Append<unsigned short>(lpszHeaders);
    do
      ++v6;
    while ( a3[v6] );
    std::wstring::_Append<unsigned short>(lpszHeaders);
    v12 = (const WCHAR *)lpszHeaders;
    if ( v19 > 7 )
      v12 = lpszHeaders[0];
    if ( WinHttpAddRequestHeaders(this[10], v12, v9, 0xA0000000) )
    {
      std::wstring::_Tidy_deallocate((char **)lpszHeaders);
      result = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1BA,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                    v13);
      std::wstring::_Tidy_deallocate((char **)lpszHeaders);
      result = LastError;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1BE,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x180022fa0  mov     [rsp+arg_18], rbx
0x180022fa5  push    rsi
0x180022fa6  push    rdi
0x180022fa7  push    r12
0x180022fa9  push    r14
0x180022fab  push    r15
0x180022fad  sub     rsp, 50h
0x180022fb1  mov     rax, cs:__security_cookie
0x180022fb8  xor     rax, rsp
0x180022fbb  mov     [rsp+78h+var_30], rax
0x180022fc0  mov     rsi, r8
0x180022fc3  mov     rdi, rdx
0x180022fc6  mov     r15, rcx
0x180022fc9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180022fcd  mov     rcx, rbx
0x180022fd0  xor     r12d, r12d
0x180022fd3  inc     rcx
0x180022fd6  cmp     [rdx+rcx*2], r12w
0x180022fdb  jnz     short loc_180022FD3
0x180022fdd  mov     rdx, rbx
0x180022fe0  inc     rdx
0x180022fe3  cmp     [r8+rdx*2], r12w
0x180022fe8  jnz     short loc_180022FE0
0x180022fea  mov     [rsp+78h+var_38], 20003Ah
0x180022ff2  mov     [rsp+78h+var_34], r12w
0x180022ff8  lea     r14, [rcx+rdx]
0x180022ffc  mov     r14d, r14d
0x180022fff  add     r14, 2
0x180023003  xorps   xmm0, xmm0
0x180023006  movups  xmmword ptr [rsp+78h+lpszHeaders], xmm0
0x18002300b  mov     [rsp+78h+var_48], r12
0x180023010  mov     [rsp+78h+var_40], 7
0x180023019  mov     word ptr [rsp+78h+lpszHeaders], r12w
0x18002301f  cmp     r14, 8
0x180023023  jb      short loc_180023037
0x180023025  mov     rdx, r14
0x180023028  lea     rcx, [rsp+78h+lpszHeaders]; Src
0x18002302d  call    ??$_Reallocate_grow_by@V_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_7f96eb1dcf99da5daec8c2467d2d5499_,>(unsigned __int64,_lambda_7f96eb1dcf99da5daec8c2467d2d5499_)
0x180023032  mov     [rsp+78h+var_48], r12
0x180023037  mov     r8, rbx
0x18002303a  inc     r8
0x18002303d  cmp     [rdi+r8*2], r12w
0x180023042  jnz     short loc_18002303A
0x180023044  mov     rdx, rdi
0x180023047  lea     rcx, [rsp+78h+lpszHeaders]; Src
0x18002304c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180023051  lea     rax, [rsp+78h+var_38]
0x180023056  mov     r8, rbx
0x180023059  inc     r8
0x18002305c  cmp     [rax+r8*2], r12w
0x180023061  jnz     short loc_180023059
0x180023063  lea     rdx, [rsp+78h+var_38]
0x180023068  lea     rcx, [rsp+78h+lpszHeaders]; Src
0x18002306d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180023072  inc     rbx
0x180023075  cmp     [rsi+rbx*2], r12w
0x18002307a  jnz     short loc_180023072
0x18002307c  mov     r8, rbx
0x18002307f  mov     rdx, rsi
0x180023082  lea     rcx, [rsp+78h+lpszHeaders]; Src
0x180023087  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002308c  lea     rdx, [rsp+78h+lpszHeaders]
0x180023091  cmp     [rsp+78h+var_40], 7
0x180023097  cmova   rdx, [rsp+78h+lpszHeaders]; lpszHeaders
0x18002309d  mov     r8d, r14d; dwHeadersLength
0x1800230a0  mov     r9d, 0A0000000h; dwModifiers
0x1800230a6  mov     rcx, [r15+50h]; hRequest
0x1800230aa  call    cs:__imp_WinHttpAddRequestHeaders
0x1800230b1  nop     dword ptr [rax+rax+00h]
0x1800230b6  test    eax, eax
0x1800230b8  jnz     short loc_1800230E0
0x1800230ba  mov     rcx, [rsp+78h]; this
0x1800230bf  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800230c6  mov     edx, 1BAh; void *
0x1800230cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800230d0  mov     ebx, eax
0x1800230d2  lea     rcx, [rsp+78h+lpszHeaders]
0x1800230d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800230dc  mov     eax, ebx
0x1800230de  jmp     short loc_1800230F2
0x1800230e0  lea     rcx, [rsp+78h+lpszHeaders]
0x1800230e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800230ea  xor     eax, eax
0x1800230ec  jmp     short loc_1800230F2
0x1800230ee  mov     eax, [rsp+78h+var_38]
0x1800230f2  mov     rcx, [rsp+78h+var_30]
0x1800230f7  xor     rcx, rsp; StackCookie
0x1800230fa  call    __security_check_cookie
0x1800230ff  mov     rbx, [rsp+78h+arg_18]
0x180023107  add     rsp, 50h
0x18002310b  pop     r15
0x18002310d  pop     r14
0x18002310f  pop     r12
0x180023111  pop     rdi
0x180023112  pop     rsi
0x180023113  retn
```
