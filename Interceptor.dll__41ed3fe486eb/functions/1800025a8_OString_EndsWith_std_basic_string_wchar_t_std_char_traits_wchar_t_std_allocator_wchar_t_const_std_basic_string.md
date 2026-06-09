# OString::EndsWith(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)

- ea: `0x1800025a8`
- end: `0x180002818`
- name: `?EndsWith@OString@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0_N@Z`
- size: `624`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002b40`

## callees

- `0x1800022c8`
- `0x1800022f8`
- `0x1800025a8`
- `0x18000410c`
- `0x180004b44`
- `0x1800266e0`
- `0x1800282a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800027f3`
- `KERNEL32!GetLastError` at `0x1800027f3`
- `KERNEL32!CompareStringEx` at `0x1800026fb`
- `KERNEL32!CompareStringEx` at `0x18000272c`
- `KERNEL32!CompareStringEx` at `0x1800026fb`
- `KERNEL32!CompareStringEx` at `0x18000272c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800027a2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800027a2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800027a9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800027a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall OString::EndsWith(_QWORD *a1, __int64 *a2)
{
  __int64 *lpString2; // rbx
  unsigned __int64 v3; // r14
  unsigned __int64 v4; // rax
  int v5; // esi
  __int64 v6; // r8
  const WCHAR *p_lpString1; // r15
  char *v8; // rcx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rbp
  unsigned __int64 cchCount2; // rdi
  unsigned __int64 v12; // rax
  int v13; // eax
  char *v14; // rdx
  DWORD LastError; // eax
  __int64 v17; // rdx
  _BYTE pExceptionObject[912]; // [rsp+60h] [rbp-3E8h] BYREF
  __int128 lpString1; // [rsp+3F0h] [rbp-58h] BYREF
  __int128 v20; // [rsp+400h] [rbp-48h]

  lpString2 = a2;
  v3 = a2[2];
  if ( v3 > a1[2] )
    return 0;
  v4 = a1[2] - v3;
  lpString1 = 0;
  v20 = 0;
  if ( a1[2] < v4 )
    std::_String_val<std::_Simple_types<wchar_t>>::_Xran();
  _mm_lfence();
  v5 = -1;
  v6 = -1;
  if ( v3 != -1 )
    v6 = v3;
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  std::wstring::_Construct<1,wchar_t const *>(&lpString1, (char *)a1 + 2 * v4, v6);
  if ( (unsigned __int64)lpString2[3] > 7 )
    lpString2 = (__int64 *)*lpString2;
  p_lpString1 = (const WCHAR *)&lpString1;
  v8 = (char *)lpString1;
  v9 = *((_QWORD *)&v20 + 1);
  if ( *((_QWORD *)&v20 + 1) > 7u )
    p_lpString1 = (const WCHAR *)lpString1;
  if ( p_lpString1 && *p_lpString1 )
  {
    if ( lpString2 && *(_WORD *)lpString2 )
    {
      v10 = v3;
      cchCount2 = v3;
      if ( v3 )
      {
        v12 = -1;
        do
          ++v12;
        while ( p_lpString1[v12] );
        cchCount2 = -1;
        do
          ++cchCount2;
        while ( *((_WORD *)lpString2 + cchCount2) );
        v10 = v3;
        if ( v12 <= v3 )
          v10 = v12;
        if ( cchCount2 > v3 )
          cchCount2 = v3;
      }
      if ( cchCount2 > 0x7FFFFFFF || v10 > 0x7FFFFFFF )
        OcfxSafeIntExceptionPolicy::SafeIntOnOverflow();
      v13 = CompareStringEx(&Src, 0, p_lpString1, v10, (LPCWCH)lpString2, cchCount2, 0, 0, 0);
      if ( !v13 )
      {
        v13 = CompareStringEx(L"en-US", 0, p_lpString1, v10, (LPCWCH)lpString2, cchCount2, 0, 0, 0);
        if ( !v13 )
        {
          LastError = GetLastError();
          OException::OException(pExceptionObject, v17, LastError);
          throw (OException *)pExceptionObject;
        }
      }
      v5 = v13 - 2;
      v9 = *((_QWORD *)&v20 + 1);
      v8 = (char *)lpString1;
    }
    else
    {
      v5 = 1;
    }
  }
  else if ( !lpString2 || !*(_WORD *)lpString2 )
  {
    v5 = 0;
  }
  if ( v9 > 7 )
  {
    v14 = v8;
    if ( 2 * v9 + 2 >= 0x1000 )
    {
      v8 = (char *)*((_QWORD *)v8 - 1);
      if ( (unsigned __int64)(v14 - v8 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v8);
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x1800025a8  mov     r11, rsp
0x1800025ab  mov     [r11+18h], rbx
0x1800025af  mov     [r11+20h], rbp
0x1800025b3  push    rsi
0x1800025b4  push    rdi
0x1800025b5  push    r12
0x1800025b7  push    r14
0x1800025b9  push    r15
0x1800025bb  sub     rsp, 420h
0x1800025c2  mov     rax, cs:__security_cookie
0x1800025c9  xor     rax, rsp
0x1800025cc  mov     [rsp+448h+var_38], rax
0x1800025d4  mov     rbx, rdx
0x1800025d7  xor     r12d, r12d
0x1800025da  mov     r14, [rdx+10h]
0x1800025de  cmp     r14, [rcx+10h]
0x1800025e2  ja      loc_1800027B3
0x1800025e8  mov     rax, [rcx+10h]
0x1800025ec  sub     rax, r14
0x1800025ef  xorps   xmm0, xmm0
0x1800025f2  movups  xmmword ptr [r11-58h], xmm0
0x1800025f7  xorps   xmm1, xmm1
0x1800025fa  movdqu  xmmword ptr [r11-48h], xmm1
0x180002600  cmp     [rcx+10h], rax
0x180002604  jb      loc_1800027EA
0x18000260a  lfence
0x18000260d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002611  mov     r8, rsi
0x180002614  cmp     r14, rsi
0x180002617  cmovb   r8, r14
0x18000261b  cmp     qword ptr [rcx+18h], 7
0x180002620  jbe     short loc_180002625
0x180002622  mov     rcx, [rcx]
0x180002625  lea     rdx, [rcx+rax*2]
0x180002629  lea     rcx, [rsp+448h+lpString1]
0x180002631  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002636  cmp     qword ptr [rbx+18h], 7
0x18000263b  jbe     short loc_180002640
0x18000263d  mov     rbx, [rbx]
0x180002640  lea     r15, [rsp+448h+lpString1]
0x180002648  mov     rcx, qword ptr [rsp+448h+lpString1]; Block
0x180002650  mov     rax, [rsp+448h+var_40]
0x180002658  cmp     rax, 7
0x18000265c  cmova   r15, rcx
0x180002660  test    r15, r15
0x180002663  jz      loc_180002756
0x180002669  cmp     r12w, [r15]
0x18000266d  jz      loc_180002756
0x180002673  test    rbx, rbx
0x180002676  jz      loc_18000274F
0x18000267c  cmp     r12w, [rbx]
0x180002680  jz      loc_18000274F
0x180002686  mov     rbp, r14
0x180002689  mov     rdi, r14
0x18000268c  test    r14, r14
0x18000268f  jz      short loc_1800026BD
0x180002691  mov     rax, rsi
0x180002694  inc     rax
0x180002697  cmp     [r15+rax*2], r12w
0x18000269c  jnz     short loc_180002694
0x18000269e  mov     rdi, rsi
0x1800026a1  inc     rdi
0x1800026a4  cmp     [rbx+rdi*2], r12w
0x1800026a9  jnz     short loc_1800026A1
0x1800026ab  mov     rbp, r14
0x1800026ae  cmp     rax, r14
0x1800026b1  cmovbe  rbp, rax
0x1800026b5  cmp     rdi, r14
0x1800026b8  jbe     short loc_1800026BD
0x1800026ba  mov     rdi, r14
0x1800026bd  mov     eax, 7FFFFFFFh
0x1800026c2  cmp     rdi, rax
0x1800026c5  ja      loc_1800027E1
0x1800026cb  cmp     rbp, rax
0x1800026ce  ja      loc_1800027E1
0x1800026d4  mov     [rsp+448h+lParam], r12; lParam
0x1800026d9  mov     [rsp+448h+lpReserved], r12; lpReserved
0x1800026de  mov     [rsp+448h+lpVersionInformation], r12; lpVersionInformation
0x1800026e3  mov     [rsp+448h+cchCount2], edi; cchCount2
0x1800026e7  mov     [rsp+448h+lpString2], rbx; lpString2
0x1800026ec  mov     r9d, ebp; cchCount1
0x1800026ef  mov     r8, r15; lpString1
0x1800026f2  xor     edx, edx; dwCmpFlags
0x1800026f4  lea     rcx, Src; lpLocaleName
0x1800026fb  call    cs:__imp_CompareStringEx
0x180002701  test    eax, eax
0x180002703  jnz     short loc_18000273A
0x180002705  mov     [rsp+448h+lParam], r12; lParam
0x18000270a  mov     [rsp+448h+lpReserved], r12; lpReserved
0x18000270f  mov     [rsp+448h+lpVersionInformation], r12; lpVersionInformation
0x180002714  mov     [rsp+448h+cchCount2], edi; cchCount2
0x180002718  mov     [rsp+448h+lpString2], rbx; lpString2
0x18000271d  mov     r9d, ebp; cchCount1
0x180002720  mov     r8, r15; lpString1
0x180002723  xor     edx, edx; dwCmpFlags
0x180002725  lea     rcx, aEnUs; "en-US"
0x18000272c  call    cs:__imp_CompareStringEx
0x180002732  test    eax, eax
0x180002734  jz      loc_1800027F3
0x18000273a  lea     esi, [rax-2]
0x18000273d  mov     rax, [rsp+448h+var_40]
0x180002745  mov     rcx, qword ptr [rsp+448h+lpString1]
0x18000274d  jmp     short loc_180002764
0x18000274f  mov     esi, 1
0x180002754  jmp     short loc_180002764
0x180002756  test    rbx, rbx
0x180002759  jz      short loc_180002761
0x18000275b  cmp     r12w, [rbx]
0x18000275f  jnz     short loc_180002764
0x180002761  mov     esi, r12d
0x180002764  test    esi, esi
0x180002766  setz    bl
0x180002769  cmp     rax, 7
0x18000276d  jbe     short loc_1800027AF
0x18000276f  mov     rdx, rcx
0x180002772  lea     rax, ds:2[rax*2]
0x18000277a  cmp     rax, 1000h
0x180002780  jb      short loc_1800027A9
0x180002782  mov     rcx, [rcx-8]
0x180002786  sub     rdx, rcx
0x180002789  lea     rax, [rdx-8]
0x18000278d  cmp     rax, 1Fh
0x180002791  jbe     short loc_1800027A9
0x180002793  mov     [rsp+448h+lpString2], r12; Reserved
0x180002798  xor     r9d, r9d; LineNo
0x18000279b  xor     r8d, r8d; FileName
0x18000279e  xor     edx, edx; FunctionName
0x1800027a0  xor     ecx, ecx; Expression
0x1800027a2  call    cs:__imp__invoke_watson
0x1800027a9  call    cs:__imp_free
0x1800027af  mov     al, bl
0x1800027b1  jmp     short loc_1800027B5
0x1800027b3  xor     al, al
0x1800027b5  mov     rcx, [rsp+448h+var_38]
0x1800027bd  xor     rcx, rsp; StackCookie
0x1800027c0  call    __security_check_cookie
0x1800027c5  lea     r11, [rsp+448h+var_28]
0x1800027cd  mov     rbx, [r11+40h]
0x1800027d1  mov     rbp, [r11+48h]
0x1800027d5  mov     rsp, r11
0x1800027d8  pop     r15
0x1800027da  pop     r14
0x1800027dc  pop     r12
0x1800027de  pop     rdi
0x1800027df  pop     rsi
0x1800027e0  retn
0x1800027e1  call    ?SafeIntOnOverflow@OcfxSafeIntExceptionPolicy@@SAXXZ; OcfxSafeIntExceptionPolicy::SafeIntOnOverflow(void)
0x1800027e7  jmp     short $+2
0x1800027e9  nop
0x1800027ea  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
0x1800027f0  jmp     short $+2
0x1800027f2  nop
0x1800027f3  call    cs:__imp_GetLastError
0x1800027f9  mov     r8d, eax
0x1800027fc  lea     rcx, [rsp+448h+pExceptionObject]
0x180002801  call    ??0OException@@QEAA@W4exceptionType@et@@I@Z; OException::OException(et::exceptionType,uint)
0x180002806  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18000280d  lea     rcx, [rsp+448h+pExceptionObject]; pExceptionObject
0x180002812  call    _CxxThrowException
```
