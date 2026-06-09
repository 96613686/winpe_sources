# ArgumentWriter::FormatArguments<wchar_t *,wchar_t [256]>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,wchar_t * const &,wchar_t const (&)[256])

- ea: `0x180009468`
- end: `0x18000969c`
- name: `??$FormatArguments@PEA_W$$BY0BAA@_W@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBQEA_WAEAY0BAA@$$CB_W@Z`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180007e5c`

## callees

- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x18000465c`
- `0x180009244`
- `0x180009468`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800095c5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180009686`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800095c5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180009686`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180009690`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180009690`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall ArgumentWriter::FormatArguments<wchar_t *,wchar_t [256]>(
        unsigned __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        __int64 *a5,
        __int64 a6)
{
  const wchar_t *v9; // r14
  wchar_t v10; // r8
  unsigned __int16 *v11; // r15
  __int64 v12; // r8
  __int64 v14; // rdx
  void **v15; // rax
  char *v16; // r14
  unsigned __int64 v17; // r15
  __int64 v18; // rsi
  char *v19; // rcx
  unsigned __int16 *v20; // [rsp+30h] [rbp-50h] BYREF
  __int64 v21; // [rsp+48h] [rbp-38h]
  unsigned __int64 v22; // [rsp+50h] [rbp-30h]
  void *Block[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v24; // [rsp+68h] [rbp-18h]
  unsigned __int64 v25; // [rsp+70h] [rbp-10h]

  v22 = a1;
  v21 = a6;
  v9 = L"    InterceptInterface() Interception Failed for Interface %s : %s";
  if ( L"    InterceptInterface() Interception Failed for Interface %s : %s" >= a3 )
  {
LABEL_11:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v12 = a4[2];
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    std::wstring::_Construct<2,wchar_t const *>(a1, a4, v12);
    return a1;
  }
  _mm_lfence();
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v24 = 0;
    v25 = 7;
    LOWORD(Block[0]) = 0;
    v10 = *v9;
    v11 = (unsigned __int16 *)(v9 + 1);
    v9 = v11;
    v20 = v11;
    if ( v10 == 37 )
      break;
    std::wstring::append(a4);
LABEL_10:
    std::wstring::_Tidy_deallocate(Block);
    if ( v9 >= a3 )
      goto LABEL_11;
  }
  if ( v11 != a3 && *v11 == 37 )
  {
    std::wstring::append(a4);
    v9 = v11 + 1;
    goto LABEL_10;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)&v20, a3, a4, (__int64)Block) )
  {
    v9 = v20;
    goto LABEL_10;
  }
  v14 = *a5;
  if ( !v24 )
    _invoke_watson(0, 0, 0, 0, 0);
  _mm_lfence();
  v15 = Block;
  v16 = (char *)Block[0];
  v17 = v25;
  if ( v25 > 7 )
    v15 = (void **)Block[0];
  if ( ((*((_WORD *)v15 + v24 - 1) - 83) & 0xFFDF) == 0 && v14 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)(v14 + 2 * v18) );
  }
  std::wstring::append(a4);
  ArgumentWriter::FormatArguments<wchar_t [64],>(a1, v20, a3, a4, v21);
  if ( v17 > 7 )
  {
    v19 = v16;
    if ( 2 * v17 + 2 >= 0x1000 )
    {
      v16 = (char *)*((_QWORD *)v16 - 1);
      if ( (unsigned __int64)(v19 - v16 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v16);
  }
  return a1;
}

```

## disassembly

```asm
0x180009468  mov     [rsp-38h+arg_8], rbx
0x18000946d  push    rbp
0x18000946e  push    rsi
0x18000946f  push    rdi
0x180009470  push    r12
0x180009472  push    r13
0x180009474  push    r14
0x180009476  push    r15
0x180009478  mov     rbp, rsp
0x18000947b  sub     rsp, 80h
0x180009482  mov     rax, cs:__security_cookie
0x180009489  xor     rax, rsp
0x18000948c  mov     [rbp+var_8], rax
0x180009490  mov     rbx, r9
0x180009493  mov     r12, r8
0x180009496  mov     rdi, rcx
0x180009499  mov     [rbp+var_30], rcx
0x18000949d  mov     r13, [rbp+arg_20]
0x1800094a1  mov     rax, [rbp+arg_28]
0x1800094a5  mov     [rbp+var_38], rax
0x1800094a9  xor     r15d, r15d
0x1800094ac  lea     r14, aInterceptinter_0; "    InterceptInterface() Interception F"...
0x1800094b3  cmp     r14, r8
0x1800094b6  jnb     loc_180009553
0x1800094bc  lfence
0x1800094bf  lea     esi, [r15+25h]
0x1800094c3  xorps   xmm0, xmm0
0x1800094c6  movups  xmmword ptr [rbp+Block], xmm0
0x1800094ca  mov     [rbp+var_18], r15
0x1800094ce  mov     [rbp+var_10], 7
0x1800094d6  mov     word ptr [rbp+Block], r15w
0x1800094db  movzx   r8d, word ptr [r14]
0x1800094df  lea     r15, [r14+2]
0x1800094e3  mov     r14, r15
0x1800094e6  mov     [rbp+var_50], r15
0x1800094ea  cmp     r8w, si
0x1800094ee  jz      short loc_180009502
0x1800094f0  mov     edx, 1
0x1800094f5  mov     rcx, rbx; Src
0x1800094f8  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x1800094fd  xor     r15d, r15d
0x180009500  jmp     short loc_180009541
0x180009502  cmp     r15, r12
0x180009505  jz      short loc_180009523
0x180009507  cmp     [r15], si
0x18000950b  jnz     short loc_180009523
0x18000950d  mov     r8d, esi
0x180009510  mov     edx, 1
0x180009515  mov     rcx, rbx; Src
0x180009518  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x18000951d  lea     r14, [r15+2]
0x180009521  jmp     short loc_1800094FD
0x180009523  lea     r9, [rbp+Block]
0x180009527  mov     r8, rbx
0x18000952a  mov     rdx, r12
0x18000952d  lea     rcx, [rbp+var_50]
0x180009531  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180009536  xor     r15d, r15d
0x180009539  test    al, al
0x18000953b  jnz     short loc_1800095A5
0x18000953d  mov     r14, [rbp+var_50]
0x180009541  lea     rcx, [rbp+Block]
0x180009545  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000954a  cmp     r14, r12
0x18000954d  jb      loc_1800094C3
0x180009553  xorps   xmm0, xmm0
0x180009556  movups  xmmword ptr [rdi], xmm0
0x180009559  mov     [rdi+10h], r15
0x18000955d  mov     [rdi+18h], r15
0x180009561  mov     r8, [rbx+10h]
0x180009565  cmp     qword ptr [rbx+18h], 7
0x18000956a  jbe     short loc_18000956F
0x18000956c  mov     rbx, [rbx]
0x18000956f  mov     rdx, rbx
0x180009572  mov     rcx, rdi
0x180009575  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000957a  nop
0x18000957b  mov     rax, rdi
0x18000957e  mov     rcx, [rbp+var_8]
0x180009582  xor     rcx, rsp; StackCookie
0x180009585  call    __security_check_cookie
0x18000958a  mov     rbx, [rsp+80h+arg_8]
0x180009592  add     rsp, 80h
0x180009599  pop     r15
0x18000959b  pop     r14
0x18000959d  pop     r13
0x18000959f  pop     r12
0x1800095a1  pop     rdi
0x1800095a2  pop     rsi
0x1800095a3  pop     rbp
0x1800095a4  retn
0x1800095a5  mov     rdx, [r13+0]
0x1800095a9  mov     rax, [rbp+var_18]
0x1800095ad  lea     rcx, [rax-1]
0x1800095b1  cmp     rcx, rax
0x1800095b4  jbe     short loc_1800095CC
0x1800095b6  mov     [rsp+80h+Reserved], r15; Reserved
0x1800095bb  xor     r9d, r9d; LineNo
0x1800095be  xor     r8d, r8d; FileName
0x1800095c1  xor     edx, edx; FunctionName
0x1800095c3  xor     ecx, ecx; Expression
0x1800095c5  call    cs:__imp__invoke_watson
0x1800095cc  lfence
0x1800095cf  lea     rax, [rbp+Block]
0x1800095d3  mov     r14, [rbp+Block]
0x1800095d7  mov     r15, [rbp+var_10]
0x1800095db  cmp     r15, 7
0x1800095df  cmova   rax, r14
0x1800095e3  movzx   eax, word ptr [rax+rcx*2]
0x1800095e7  sub     ax, 53h ; 'S'
0x1800095eb  mov     ecx, 0FFDFh
0x1800095f0  xor     r13d, r13d
0x1800095f3  test    cx, ax
0x1800095f6  jz      short loc_180009601
0x1800095f8  lea     rdx, aErrorWrongForm_0; "!error: wrong format for wide string!"
0x1800095ff  jmp     short loc_180009622
0x180009601  test    rdx, rdx
0x180009604  jnz     short loc_180009614
0x180009606  lea     rdx, aNull_1; "<NULL>"
0x18000960d  mov     esi, 6
0x180009612  jmp     short loc_180009622
0x180009614  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009618  inc     rsi
0x18000961b  cmp     [rdx+rsi*2], r13w
0x180009620  jnz     short loc_180009618
0x180009622  mov     r8, rsi
0x180009625  mov     rcx, rbx; Src
0x180009628  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18000962d  mov     rax, [rbp+var_38]
0x180009631  mov     [rsp+80h+Reserved], rax
0x180009636  mov     r9, rbx
0x180009639  mov     r8, r12
0x18000963c  mov     rdx, [rbp+var_50]
0x180009640  mov     rcx, rdi
0x180009643  call    ??$FormatArguments@$$BY0EA@_W$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEAY0EA@$$CB_W@Z; ArgumentWriter::FormatArguments<wchar_t [64],>(wchar_t const *,wchar_t const *,std::wstring &,wchar_t const (&)[64])
0x180009648  nop
0x180009649  cmp     r15, 7
0x18000964d  jbe     loc_18000957B
0x180009653  mov     rcx, r14
0x180009656  lea     rax, ds:2[r15*2]
0x18000965e  cmp     rax, 1000h
0x180009664  jb      short loc_18000968D
0x180009666  mov     r14, [r14-8]
0x18000966a  sub     rcx, r14
0x18000966d  lea     rax, [rcx-8]
0x180009671  cmp     rax, 1Fh
0x180009675  jbe     short loc_18000968D
0x180009677  mov     [rsp+80h+Reserved], r13; Reserved
0x18000967c  xor     r9d, r9d; LineNo
0x18000967f  xor     r8d, r8d; FileName
0x180009682  xor     edx, edx; FunctionName
0x180009684  xor     ecx, ecx; Expression
0x180009686  call    cs:__imp__invoke_watson
0x18000968d  mov     rcx, r14; Block
0x180009690  call    cs:__imp_free
0x180009696  jmp     loc_18000957B
```
