# OString::StartsWith(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)

- ea: `0x180002358`
- end: `0x1800025a6`
- name: `?StartsWith@OString@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0_N@Z`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003124`

## callees

- `0x1800022c8`
- `0x1800022f8`
- `0x180002358`
- `0x18000410c`
- `0x1800266e0`
- `0x1800282a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002581`
- `KERNEL32!GetLastError` at `0x180002581`
- `KERNEL32!CompareStringEx` at `0x18000248f`
- `KERNEL32!CompareStringEx` at `0x1800024c0`
- `KERNEL32!CompareStringEx` at `0x18000248f`
- `KERNEL32!CompareStringEx` at `0x1800024c0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000253c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000253c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002543`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002543`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall OString::StartsWith(_QWORD *a1, __int64 *a2)
{
  __int64 *lpString2; // rdi
  unsigned __int64 v3; // rsi
  const WCHAR *p_lpString1; // r14
  char *v5; // rcx
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rbp
  unsigned __int64 cchCount2; // rbx
  unsigned __int64 v9; // rax
  int v10; // eax
  int v11; // esi
  char *v12; // rdx
  DWORD LastError; // eax
  __int64 v15; // rdx
  _BYTE pExceptionObject[912]; // [rsp+60h] [rbp-3E8h] BYREF
  __int128 lpString1; // [rsp+3F0h] [rbp-58h] BYREF
  __int128 v18; // [rsp+400h] [rbp-48h]

  lpString2 = a2;
  v3 = a2[2];
  if ( v3 > a1[2] )
    return 0;
  lpString1 = 0;
  v18 = 0;
  _mm_lfence();
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  std::wstring::_Construct<1,wchar_t const *>(&lpString1, a1, v3);
  if ( (unsigned __int64)lpString2[3] > 7 )
    lpString2 = (__int64 *)*lpString2;
  p_lpString1 = (const WCHAR *)&lpString1;
  v5 = (char *)lpString1;
  v6 = *((_QWORD *)&v18 + 1);
  if ( *((_QWORD *)&v18 + 1) > 7u )
    p_lpString1 = (const WCHAR *)lpString1;
  if ( p_lpString1 && *p_lpString1 )
  {
    if ( lpString2 && *(_WORD *)lpString2 )
    {
      v7 = v3;
      cchCount2 = v3;
      if ( v3 )
      {
        cchCount2 = -1;
        v9 = -1;
        do
          ++v9;
        while ( p_lpString1[v9] );
        do
          ++cchCount2;
        while ( *((_WORD *)lpString2 + cchCount2) );
        v7 = v3;
        if ( v9 <= v3 )
          v7 = v9;
        if ( cchCount2 > v3 )
          cchCount2 = v3;
      }
      if ( cchCount2 > 0x7FFFFFFF || v7 > 0x7FFFFFFF )
        OcfxSafeIntExceptionPolicy::SafeIntOnOverflow();
      v10 = CompareStringEx(&Src, 1u, p_lpString1, v7, (LPCWCH)lpString2, cchCount2, 0, 0, 0);
      if ( !v10 )
      {
        v10 = CompareStringEx(L"en-US", 1u, p_lpString1, v7, (LPCWCH)lpString2, cchCount2, 0, 0, 0);
        if ( !v10 )
        {
          LastError = GetLastError();
          OException::OException(pExceptionObject, v15, LastError);
          throw (OException *)pExceptionObject;
        }
      }
      v11 = v10 - 2;
      v6 = *((_QWORD *)&v18 + 1);
      v5 = (char *)lpString1;
    }
    else
    {
      v11 = 1;
    }
  }
  else if ( lpString2 && *(_WORD *)lpString2 )
  {
    v11 = -1;
  }
  else
  {
    v11 = 0;
  }
  if ( v6 > 7 )
  {
    v12 = v5;
    if ( 2 * v6 + 2 >= 0x1000 )
    {
      v5 = (char *)*((_QWORD *)v5 - 1);
      if ( (unsigned __int64)(v12 - v5 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v5);
  }
  return v11 == 0;
}

```

## disassembly

```asm
0x180002358  mov     r11, rsp
0x18000235b  mov     [r11+18h], rbx
0x18000235f  push    rbp
0x180002360  push    rsi
0x180002361  push    rdi
0x180002362  push    r14
0x180002364  push    r15
0x180002366  sub     rsp, 420h
0x18000236d  mov     rax, cs:__security_cookie
0x180002374  xor     rax, rsp
0x180002377  mov     [rsp+448h+var_38], rax
0x18000237f  mov     rdi, rdx
0x180002382  xor     r15d, r15d
0x180002385  mov     rsi, [rdx+10h]
0x180002389  cmp     rsi, [rcx+10h]
0x18000238d  ja      loc_18000254D
0x180002393  xorps   xmm0, xmm0
0x180002396  movups  xmmword ptr [r11-58h], xmm0
0x18000239b  xorps   xmm1, xmm1
0x18000239e  movdqu  xmmword ptr [r11-48h], xmm1
0x1800023a4  lfence
0x1800023a7  cmp     qword ptr [rcx+18h], 7
0x1800023ac  jbe     short loc_1800023B1
0x1800023ae  mov     rcx, [rcx]
0x1800023b1  mov     r8, rsi
0x1800023b4  mov     rdx, rcx
0x1800023b7  lea     rcx, [rsp+448h+lpString1]
0x1800023bf  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800023c4  cmp     qword ptr [rdi+18h], 7
0x1800023c9  jbe     short loc_1800023CE
0x1800023cb  mov     rdi, [rdi]
0x1800023ce  lea     r14, [rsp+448h+lpString1]
0x1800023d6  mov     rcx, qword ptr [rsp+448h+lpString1]; Block
0x1800023de  mov     rax, [rsp+448h+var_40]
0x1800023e6  cmp     rax, 7
0x1800023ea  cmova   r14, rcx
0x1800023ee  test    r14, r14
0x1800023f1  jz      loc_1800024EA
0x1800023f7  cmp     r15w, [r14]
0x1800023fb  jz      loc_1800024EA
0x180002401  test    rdi, rdi
0x180002404  jz      loc_1800024E3
0x18000240a  cmp     r15w, [rdi]
0x18000240e  jz      loc_1800024E3
0x180002414  mov     rbp, rsi
0x180002417  mov     rbx, rsi
0x18000241a  test    rsi, rsi
0x18000241d  jz      short loc_18000244C
0x18000241f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002423  mov     rax, rbx
0x180002426  inc     rax
0x180002429  cmp     [r14+rax*2], r15w
0x18000242e  jnz     short loc_180002426
0x180002430  inc     rbx
0x180002433  cmp     [rdi+rbx*2], r15w
0x180002438  jnz     short loc_180002430
0x18000243a  mov     rbp, rsi
0x18000243d  cmp     rax, rsi
0x180002440  cmovbe  rbp, rax
0x180002444  cmp     rbx, rsi
0x180002447  jbe     short loc_18000244C
0x180002449  mov     rbx, rsi
0x18000244c  mov     eax, 7FFFFFFFh
0x180002451  cmp     rbx, rax
0x180002454  ja      loc_180002576
0x18000245a  cmp     rbp, rax
0x18000245d  ja      loc_180002576
0x180002463  mov     [rsp+448h+lParam], r15; lParam
0x180002468  mov     [rsp+448h+lpReserved], r15; lpReserved
0x18000246d  mov     [rsp+448h+lpVersionInformation], r15; lpVersionInformation
0x180002472  mov     [rsp+448h+cchCount2], ebx; cchCount2
0x180002476  mov     [rsp+448h+lpString2], rdi; lpString2
0x18000247b  mov     r9d, ebp; cchCount1
0x18000247e  mov     r8, r14; lpString1
0x180002481  mov     esi, 1
0x180002486  mov     edx, esi; dwCmpFlags
0x180002488  lea     rcx, Src; lpLocaleName
0x18000248f  call    cs:__imp_CompareStringEx
0x180002495  test    eax, eax
0x180002497  jnz     short loc_1800024CE
0x180002499  mov     [rsp+448h+lParam], r15; lParam
0x18000249e  mov     [rsp+448h+lpReserved], r15; lpReserved
0x1800024a3  mov     [rsp+448h+lpVersionInformation], r15; lpVersionInformation
0x1800024a8  mov     [rsp+448h+cchCount2], ebx; cchCount2
0x1800024ac  mov     [rsp+448h+lpString2], rdi; lpString2
0x1800024b1  mov     r9d, ebp; cchCount1
0x1800024b4  mov     r8, r14; lpString1
0x1800024b7  mov     edx, esi; dwCmpFlags
0x1800024b9  lea     rcx, aEnUs; "en-US"
0x1800024c0  call    cs:__imp_CompareStringEx
0x1800024c6  test    eax, eax
0x1800024c8  jz      loc_180002581
0x1800024ce  lea     esi, [rax-2]
0x1800024d1  mov     rax, [rsp+448h+var_40]
0x1800024d9  mov     rcx, qword ptr [rsp+448h+lpString1]
0x1800024e1  jmp     short loc_1800024FE
0x1800024e3  mov     esi, 1
0x1800024e8  jmp     short loc_1800024FE
0x1800024ea  test    rdi, rdi
0x1800024ed  jz      short loc_1800024FB
0x1800024ef  cmp     r15w, [rdi]
0x1800024f3  jz      short loc_1800024FB
0x1800024f5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800024f9  jmp     short loc_1800024FE
0x1800024fb  mov     esi, r15d
0x1800024fe  test    esi, esi
0x180002500  setz    bl
0x180002503  cmp     rax, 7
0x180002507  jbe     short loc_180002549
0x180002509  mov     rdx, rcx
0x18000250c  lea     rax, ds:2[rax*2]
0x180002514  cmp     rax, 1000h
0x18000251a  jb      short loc_180002543
0x18000251c  mov     rcx, [rcx-8]
0x180002520  sub     rdx, rcx
0x180002523  lea     rax, [rdx-8]
0x180002527  cmp     rax, 1Fh
0x18000252b  jbe     short loc_180002543
0x18000252d  mov     [rsp+448h+lpString2], r15; Reserved
0x180002532  xor     r9d, r9d; LineNo
0x180002535  xor     r8d, r8d; FileName
0x180002538  xor     edx, edx; FunctionName
0x18000253a  xor     ecx, ecx; Expression
0x18000253c  call    cs:__imp__invoke_watson
0x180002543  call    cs:__imp_free
0x180002549  mov     al, bl
0x18000254b  jmp     short loc_18000254F
0x18000254d  xor     al, al
0x18000254f  mov     rcx, [rsp+448h+var_38]
0x180002557  xor     rcx, rsp; StackCookie
0x18000255a  call    __security_check_cookie
0x18000255f  mov     rbx, [rsp+448h+arg_10]
0x180002567  add     rsp, 420h
0x18000256e  pop     r15
0x180002570  pop     r14
0x180002572  pop     rdi
0x180002573  pop     rsi
0x180002574  pop     rbp
0x180002575  retn
0x180002576  call    ?SafeIntOnOverflow@OcfxSafeIntExceptionPolicy@@SAXXZ; OcfxSafeIntExceptionPolicy::SafeIntOnOverflow(void)
0x180002581  call    cs:__imp_GetLastError
0x180002587  mov     r8d, eax
0x18000258a  lea     rcx, [rsp+448h+pExceptionObject]
0x18000258f  call    ??0OException@@QEAA@W4exceptionType@et@@I@Z; OException::OException(et::exceptionType,uint)
0x180002594  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18000259b  lea     rcx, [rsp+448h+pExceptionObject]; pExceptionObject
0x1800025a0  call    _CxxThrowException
```
