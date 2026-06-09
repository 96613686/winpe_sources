# Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)

- ea: `0x1800224d4`
- end: `0x180022643`
- name: `?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z`
- size: `367`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::DdsNetworkWrapper *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180024c34`

## callees

- `0x1800045b0`
- `0x1800105d4`
- `0x1800139c4`
- `0x1800174f0`
- `0x180021fd4`
- `0x1800224d4`

## import_xrefs

- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800225de`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800225de`

## string_xrefs

- `0x1800225ed`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      std::wstring::_Tidy_deallocate(lpszHeaders);
      result = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1BA,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                    v13);
      std::wstring::_Tidy_deallocate(lpszHeaders);
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
0x1800224d4  mov     [rsp+arg_18], rbx
0x1800224d9  push    rsi
0x1800224da  push    rdi
0x1800224db  push    r12
0x1800224dd  push    r14
0x1800224df  push    r15
0x1800224e1  sub     rsp, 50h
0x1800224e5  mov     rax, cs:__security_cookie
0x1800224ec  xor     rax, rsp
0x1800224ef  mov     [rsp+78h+var_30], rax
0x1800224f4  mov     rsi, r8
0x1800224f7  mov     rdi, rdx
0x1800224fa  mov     r15, rcx
0x1800224fd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180022501  mov     rcx, rbx
0x180022504  xor     r12d, r12d
0x180022507  inc     rcx
0x18002250a  cmp     [rdx+rcx*2], r12w
0x18002250f  jnz     short loc_180022507
0x180022511  mov     rdx, rbx
0x180022514  inc     rdx
0x180022517  cmp     [r8+rdx*2], r12w
0x18002251c  jnz     short loc_180022514
0x18002251e  mov     [rsp+78h+var_38], 20003Ah
0x180022526  mov     [rsp+78h+var_34], r12w
0x18002252c  lea     r14, [rcx+rdx]
0x180022530  mov     r14d, r14d
0x180022533  add     r14, 2
0x180022537  xorps   xmm0, xmm0
0x18002253a  movups  xmmword ptr [rsp+78h+lpszHeaders], xmm0
0x18002253f  mov     [rsp+78h+var_48], r12
0x180022544  mov     [rsp+78h+var_40], 7
0x18002254d  mov     word ptr [rsp+78h+lpszHeaders], r12w
0x180022553  cmp     r14, 8
0x180022557  jb      short loc_18002256B
0x180022559  mov     rdx, r14
0x18002255c  lea     rcx, [rsp+78h+lpszHeaders]; Src
0x180022561  call    ??$_Reallocate_grow_by@V_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_7f96eb1dcf99da5daec8c2467d2d5499_,>(unsigned __int64,_lambda_7f96eb1dcf99da5daec8c2467d2d5499_)
0x180022566  mov     [rsp+78h+var_48], r12
0x18002256b  mov     r8, rbx
0x18002256e  inc     r8
0x180022571  cmp     [rdi+r8*2], r12w
0x180022576  jnz     short loc_18002256E
0x180022578  mov     rdx, rdi
0x18002257b  lea     rcx, [rsp+78h+lpszHeaders]; Src
0x180022580  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180022585  lea     rax, [rsp+78h+var_38]
0x18002258a  mov     r8, rbx
0x18002258d  inc     r8
0x180022590  cmp     [rax+r8*2], r12w
0x180022595  jnz     short loc_18002258D
0x180022597  lea     rdx, [rsp+78h+var_38]
0x18002259c  lea     rcx, [rsp+78h+lpszHeaders]; Src
0x1800225a1  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800225a6  inc     rbx
0x1800225a9  cmp     [rsi+rbx*2], r12w
0x1800225ae  jnz     short loc_1800225A6
0x1800225b0  mov     r8, rbx
0x1800225b3  mov     rdx, rsi
0x1800225b6  lea     rcx, [rsp+78h+lpszHeaders]; Src
0x1800225bb  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800225c0  lea     rdx, [rsp+78h+lpszHeaders]
0x1800225c5  cmp     [rsp+78h+var_40], 7
0x1800225cb  cmova   rdx, [rsp+78h+lpszHeaders]; lpszHeaders
0x1800225d1  mov     r8d, r14d; dwHeadersLength
0x1800225d4  mov     r9d, 0A0000000h; dwModifiers
0x1800225da  mov     rcx, [r15+50h]; hRequest
0x1800225de  call    cs:__imp_WinHttpAddRequestHeaders
0x1800225e4  test    eax, eax
0x1800225e6  jnz     short loc_18002260E
0x1800225e8  mov     rcx, [rsp+78h]; this
0x1800225ed  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800225f4  mov     edx, 1BAh; void *
0x1800225f9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800225fe  mov     ebx, eax
0x180022600  lea     rcx, [rsp+78h+lpszHeaders]
0x180022605  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002260a  mov     eax, ebx
0x18002260c  jmp     short loc_180022620
0x18002260e  lea     rcx, [rsp+78h+lpszHeaders]
0x180022613  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022618  xor     eax, eax
0x18002261a  jmp     short loc_180022620
0x18002261c  mov     eax, [rsp+78h+var_38]
0x180022620  mov     rcx, [rsp+78h+var_30]
0x180022625  xor     rcx, rsp; StackCookie
0x180022628  call    __security_check_cookie
0x18002262d  mov     rbx, [rsp+78h+arg_18]
0x180022635  add     rsp, 50h
0x180022639  pop     r15
0x18002263b  pop     r14
0x18002263d  pop     r12
0x18002263f  pop     rdi
0x180022640  pop     rsi
0x180022641  retn
```
