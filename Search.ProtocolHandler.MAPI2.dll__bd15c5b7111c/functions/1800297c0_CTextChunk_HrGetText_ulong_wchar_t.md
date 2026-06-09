# CTextChunk::HrGetText(ulong *,wchar_t *)

- ea: `0x1800297c0`
- end: `0x180029955`
- name: `?HrGetText@CTextChunk@@QEAAJPEAKPEA_W@Z`
- size: `405`
- prototype: `int(CTextChunk *__hidden this, unsigned int *, wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180015dc0`

## callees

- `0x180002300`
- `0x180015024`
- `0x180017468`
- `0x1800297c0`
- `0x18003a060`
- `0x18003a0e4`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800298ea`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800298ea`

## string_xrefs

- `0x180029848`: `[UtilCommon] !!Stream read failed! 0x%08x`
- `0x180029854`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutill\\prothndlrhelp.cxx"`
- `0x1800298b8`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutill\\prothndlrhelp.cxx"`
- `0x1800298ac`: `[UtilCommon] Stream read failed! 0x%08x`

## pseudocode

```c
__int64 __fastcall CTextChunk::HrGetText(CTextChunk *this, unsigned int *a2, wchar_t *a3)
{
  unsigned __int64 v3; // rbx
  __int64 *v7; // r14
  __int64 v8; // r13
  int v9; // eax
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  int v14; // eax
  unsigned int v15; // esi
  unsigned int v17; // eax
  __int64 v18; // rcx
  unsigned int v19; // ebx
  CHAR MultiByteStr[80]; // [rsp+30h] [rbp+0h] BYREF

  v3 = *a2;
  if ( (_DWORD)v3 )
  {
    if ( !*((_BYTE *)this + 8232) )
    {
      v17 = *((_DWORD *)this + 2057);
      if ( v17 )
      {
        v18 = *((unsigned int *)this + 2056);
        v19 = (unsigned int)v3 >> 1;
        if ( v19 >= v17 )
          v19 = v17;
        memcpy_0(a3, (const void *)(*((_QWORD *)this + 1) + 2 * v18), 2LL * v19);
        *a2 = v19;
        *((_DWORD *)this + 2056) += v19;
        *((_DWORD *)this + 2057) -= v19;
        return 0;
      }
      return 2147751681LL;
    }
    v7 = (__int64 *)*((_QWORD *)this + 1030);
    v8 = *v7;
    if ( *((_BYTE *)this + 8233) )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD, unsigned int *))(v8 + 24))(
             *((_QWORD *)this + 1030),
             a3,
             (unsigned int)v3,
             a2);
      if ( v9 != 1 && *a2 )
      {
        if ( v9 < 0 )
          SearchIndexerTrace::Warning(
            (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutill\\\\prothndlrhelp.cxx\"",
            (const wchar_t *)0x4C,
            (unsigned int)L"[UtilCommon] !!Stream read failed! 0x%08x",
            (const wchar_t *)(unsigned int)v9);
        *a2 >>= 1;
        return 0;
      }
      return 2147751681LL;
    }
    v10 = v3 + 15;
    if ( v3 + 15 < v3 )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
    v12 = alloca(v11);
    v13 = alloca(v11);
    v14 = (*(__int64 (__fastcall **)(__int64 *, CHAR *, _QWORD, unsigned int *))(v8 + 24))(
            v7,
            MultiByteStr,
            (unsigned int)v3,
            a2);
    v15 = v14;
    if ( v14 < 0 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutill\\\\prothndlrhelp.cxx\"",
        (const wchar_t *)0x58,
        (unsigned int)L"[UtilCommon] Stream read failed! 0x%08x",
        (const wchar_t *)(unsigned int)v14);
      return v15;
    }
    if ( v14 == 1 || !*a2 )
      return 2147751681LL;
    *a2 = MultiByteToWideChar(0, 1u, MultiByteStr, *a2, a3, (unsigned int)v3 >> 1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800297c0  push    rbp
0x1800297c2  push    rbx
0x1800297c3  push    rsi
0x1800297c4  push    rdi
0x1800297c5  push    r12
0x1800297c7  push    r13
0x1800297c9  push    r14
0x1800297cb  push    r15
0x1800297cd  sub     rsp, 48h
0x1800297d1  lea     rbp, [rsp+30h]
0x1800297d6  mov     rax, cs:__security_cookie
0x1800297dd  xor     rax, rbp
0x1800297e0  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x1800297e4  mov     ebx, [rdx]
0x1800297e6  xor     r12d, r12d
0x1800297e9  mov     r15, r8
0x1800297ec  mov     rdi, rdx
0x1800297ef  mov     rsi, rcx
0x1800297f2  test    ebx, ebx
0x1800297f4  jz      loc_180029936
0x1800297fa  cmp     [rcx+2028h], r12b
0x180029801  jz      loc_1800298F4
0x180029807  mov     r14, [rcx+2030h]
0x18002980e  mov     r13, [r14]
0x180029811  cmp     [rcx+2029h], r12b
0x180029818  jz      short loc_180029867
0x18002981a  mov     rax, [r13+18h]
0x18002981e  mov     r9, rdx
0x180029821  mov     rdx, r15
0x180029824  mov     r8d, ebx
0x180029827  mov     rcx, r14
0x18002982a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002982f  cmp     eax, 1
0x180029832  jz      loc_1800298FE
0x180029838  cmp     [rdi], r12d
0x18002983b  jz      loc_1800298FE
0x180029841  test    eax, eax
0x180029843  jns     short loc_180029860
0x180029845  mov     r9d, eax; wchar_t *
0x180029848  lea     r8, aUtilcommonStre_0; "[UtilCommon] !!Stream read failed! 0x%0"...
0x18002984f  lea     edx, [r12+4Ch]; wchar_t *
0x180029854  lea     rcx, aOnecoreuapBase_10; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18002985b  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x180029860  shr     dword ptr [rdi], 1
0x180029862  jmp     loc_180029936
0x180029867  lea     rcx, [rbx+0Fh]
0x18002986b  cmp     rcx, rbx
0x18002986e  ja      short loc_18002987A
0x180029870  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002987a  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002987e  mov     rax, rcx
0x180029881  call    _alloca_probe
0x180029886  mov     rax, [r13+18h]
0x18002988a  sub     rsp, rcx
0x18002988d  mov     r9, rdi
0x180029890  mov     r8d, ebx
0x180029893  mov     rcx, r14
0x180029896  lea     r12, [rsp+80h+MultiByteStr]
0x18002989b  mov     rdx, r12
0x18002989e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298a3  mov     esi, eax
0x1800298a5  test    eax, eax
0x1800298a7  jns     short loc_1800298C8
0x1800298a9  mov     r9d, eax; wchar_t *
0x1800298ac  lea     r8, aUtilcommonStre; "[UtilCommon] Stream read failed! 0x%08x"
0x1800298b3  mov     edx, 58h ; 'X'; wchar_t *
0x1800298b8  lea     rcx, aOnecoreuapBase_10; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800298bf  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800298c4  mov     eax, esi
0x1800298c6  jmp     short loc_180029938
0x1800298c8  cmp     esi, 1
0x1800298cb  jz      short loc_1800298FE
0x1800298cd  mov     r9d, [rdi]; cbMultiByte
0x1800298d0  test    r9d, r9d
0x1800298d3  jz      short loc_1800298FE
0x1800298d5  shr     ebx, 1
0x1800298d7  mov     r8, r12; lpMultiByteStr
0x1800298da  mov     [rsp+80h+cchWideChar], ebx; cchWideChar
0x1800298de  mov     edx, 1; dwFlags
0x1800298e3  xor     ecx, ecx; CodePage
0x1800298e5  mov     [rsp+80h+lpWideCharStr], r15; lpWideCharStr
0x1800298ea  call    cs:__imp_MultiByteToWideChar
0x1800298f0  mov     [rdi], eax
0x1800298f2  jmp     short loc_180029936
0x1800298f4  mov     eax, [rcx+2024h]
0x1800298fa  test    eax, eax
0x1800298fc  jnz     short loc_180029905
0x1800298fe  mov     eax, 80041701h
0x180029903  jmp     short loc_180029938
0x180029905  mov     ecx, [rcx+2020h]
0x18002990b  shr     ebx, 1
0x18002990d  cmp     ebx, eax
0x18002990f  cmovnb  ebx, eax
0x180029912  mov     rax, [rsi+8]
0x180029916  mov     r8d, ebx
0x180029919  add     r8, r8; Size
0x18002991c  lea     rdx, [rax+rcx*2]; Src
0x180029920  mov     rcx, r15; void *
0x180029923  call    memcpy_0
0x180029928  mov     [rdi], ebx
0x18002992a  add     [rsi+2020h], ebx
0x180029930  sub     [rsi+2024h], ebx
0x180029936  xor     eax, eax
0x180029938  mov     rcx, qword ptr [rbp+50h+MultiByteStr]
0x18002993c  xor     rcx, rbp; StackCookie
0x18002993f  call    __security_check_cookie
0x180029944  lea     rsp, [rbp+18h]
0x180029948  pop     r15
0x18002994a  pop     r14
0x18002994c  pop     r13
0x18002994e  pop     r12
0x180029950  pop     rdi
0x180029951  pop     rsi
0x180029952  pop     rbx
0x180029953  pop     rbp
0x180029954  retn
```
