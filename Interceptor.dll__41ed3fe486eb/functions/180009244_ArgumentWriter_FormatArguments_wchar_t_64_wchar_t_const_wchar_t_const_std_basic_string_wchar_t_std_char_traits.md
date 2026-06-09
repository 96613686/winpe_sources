# ArgumentWriter::FormatArguments<wchar_t [64],>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,wchar_t const (&)[64])

- ea: `0x180009244`
- end: `0x180009465`
- name: `??$FormatArguments@$$BY0EA@_W$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEAY0EA@$$CB_W@Z`
- size: `545`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180008c48`
- `0x180008d34`
- `0x180009468`

## callees

- `0x180001db0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x18000465c`
- `0x180009244`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180009396`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000944f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180009396`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000944f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180009459`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180009459`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall ArgumentWriter::FormatArguments<wchar_t [64],>(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        __int64 a5)
{
  unsigned __int16 *v7; // r14
  unsigned __int16 v9; // r8
  unsigned __int16 *v10; // r13
  __int64 v11; // r8
  void **v13; // rax
  char *v14; // r14
  unsigned __int64 v15; // r12
  __int64 v16; // rsi
  char *v17; // rcx
  unsigned __int16 *v18; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int16 *v19; // [rsp+40h] [rbp-40h]
  unsigned __int64 v20; // [rsp+48h] [rbp-38h]
  void *Block[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v22; // [rsp+60h] [rbp-20h]
  unsigned __int64 v23; // [rsp+68h] [rbp-18h]

  v19 = a3;
  v7 = a2;
  v20 = a1;
  if ( a2 >= a3 )
  {
LABEL_11:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v11 = a4[2];
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    std::wstring::_Construct<2,wchar_t const *>(a1, a4, v11);
    return a1;
  }
  _mm_lfence();
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v22 = 0;
    v23 = 7;
    LOWORD(Block[0]) = 0;
    v9 = *v7;
    v10 = v7 + 1;
    v7 = v10;
    v18 = v10;
    if ( v9 == 37 )
      break;
    std::wstring::append(a4);
LABEL_10:
    std::wstring::_Tidy_deallocate(Block);
    if ( v7 >= a3 )
      goto LABEL_11;
  }
  if ( v10 != a3 && *v10 == 37 )
  {
    std::wstring::append(a4);
    v7 = v10 + 1;
    goto LABEL_10;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)&v18, a3, a4, (__int64)Block) )
  {
    v7 = v18;
    goto LABEL_10;
  }
  if ( !v22 )
    _invoke_watson(0, 0, 0, 0, 0);
  _mm_lfence();
  v13 = Block;
  v14 = (char *)Block[0];
  v15 = v23;
  if ( v23 > 7 )
    v13 = (void **)Block[0];
  if ( ((*((_WORD *)v13 + v22 - 1) - 83) & 0xFFDF) == 0 && a5 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)(a5 + 2 * v16) );
  }
  std::wstring::append(a4);
  ArgumentWriter::FormatArguments(a1, v18, v19, a4);
  if ( v15 > 7 )
  {
    v17 = v14;
    if ( 2 * v15 + 2 >= 0x1000 )
    {
      v14 = (char *)*((_QWORD *)v14 - 1);
      if ( (unsigned __int64)(v17 - v14 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v14);
  }
  return a1;
}

```

## disassembly

```asm
0x180009244  mov     [rsp-38h+arg_10], rbx
0x180009249  push    rbp
0x18000924a  push    rsi
0x18000924b  push    rdi
0x18000924c  push    r12
0x18000924e  push    r13
0x180009250  push    r14
0x180009252  push    r15
0x180009254  mov     rbp, rsp
0x180009257  sub     rsp, 80h
0x18000925e  mov     rax, cs:__security_cookie
0x180009265  xor     rax, rsp
0x180009268  mov     [rbp+var_10], rax
0x18000926c  mov     rbx, r9
0x18000926f  mov     r12, r8
0x180009272  mov     [rbp+var_40], r8
0x180009276  mov     r14, rdx
0x180009279  mov     rdi, rcx
0x18000927c  mov     r15, [rbp+arg_20]
0x180009280  mov     [rbp+var_38], rcx
0x180009284  xor     r13d, r13d
0x180009287  cmp     rdx, r8
0x18000928a  jnb     loc_180009328
0x180009290  lfence
0x180009293  lea     esi, [r13+25h]
0x180009297  xorps   xmm0, xmm0
0x18000929a  movups  xmmword ptr [rbp+Block], xmm0
0x18000929e  mov     [rbp+var_20], r13
0x1800092a2  mov     [rbp+var_18], 7
0x1800092aa  mov     word ptr [rbp+Block], r13w
0x1800092af  movzx   r8d, word ptr [r14]
0x1800092b3  lea     r13, [r14+2]
0x1800092b7  mov     r14, r13
0x1800092ba  mov     [rbp+var_50], r13
0x1800092be  cmp     r8w, si
0x1800092c2  jz      short loc_1800092D6
0x1800092c4  mov     edx, 1
0x1800092c9  mov     rcx, rbx; Src
0x1800092cc  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x1800092d1  xor     r13d, r13d
0x1800092d4  jmp     short loc_180009316
0x1800092d6  cmp     r13, r12
0x1800092d9  jz      short loc_1800092F8
0x1800092db  cmp     [r13+0], si
0x1800092e0  jnz     short loc_1800092F8
0x1800092e2  mov     r8d, esi
0x1800092e5  mov     edx, 1
0x1800092ea  mov     rcx, rbx; Src
0x1800092ed  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x1800092f2  lea     r14, [r13+2]
0x1800092f6  jmp     short loc_1800092D1
0x1800092f8  lea     r9, [rbp+Block]
0x1800092fc  mov     r8, rbx
0x1800092ff  mov     rdx, r12
0x180009302  lea     rcx, [rbp+var_50]
0x180009306  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x18000930b  xor     r13d, r13d
0x18000930e  test    al, al
0x180009310  jnz     short loc_18000937A
0x180009312  mov     r14, [rbp+var_50]
0x180009316  lea     rcx, [rbp+Block]
0x18000931a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000931f  cmp     r14, r12
0x180009322  jb      loc_180009297
0x180009328  xorps   xmm0, xmm0
0x18000932b  movups  xmmword ptr [rdi], xmm0
0x18000932e  mov     [rdi+10h], r13
0x180009332  mov     [rdi+18h], r13
0x180009336  mov     r8, [rbx+10h]
0x18000933a  cmp     qword ptr [rbx+18h], 7
0x18000933f  jbe     short loc_180009344
0x180009341  mov     rbx, [rbx]
0x180009344  mov     rdx, rbx
0x180009347  mov     rcx, rdi
0x18000934a  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000934f  nop
0x180009350  mov     rax, rdi
0x180009353  mov     rcx, [rbp+var_10]
0x180009357  xor     rcx, rsp; StackCookie
0x18000935a  call    __security_check_cookie
0x18000935f  mov     rbx, [rsp+80h+arg_10]
0x180009367  add     rsp, 80h
0x18000936e  pop     r15
0x180009370  pop     r14
0x180009372  pop     r13
0x180009374  pop     r12
0x180009376  pop     rdi
0x180009377  pop     rsi
0x180009378  pop     rbp
0x180009379  retn
0x18000937a  mov     rax, [rbp+var_20]
0x18000937e  lea     rcx, [rax-1]
0x180009382  cmp     rcx, rax
0x180009385  jbe     short loc_18000939D
0x180009387  mov     [rsp+80h+Reserved], r13; Reserved
0x18000938c  xor     r9d, r9d; LineNo
0x18000938f  xor     r8d, r8d; FileName
0x180009392  xor     edx, edx; FunctionName
0x180009394  xor     ecx, ecx; Expression
0x180009396  call    cs:__imp__invoke_watson
0x18000939d  lfence
0x1800093a0  lea     rax, [rbp+Block]
0x1800093a4  mov     r14, [rbp+Block]
0x1800093a8  mov     r12, [rbp+var_18]
0x1800093ac  cmp     r12, 7
0x1800093b0  cmova   rax, r14
0x1800093b4  movzx   eax, word ptr [rax+rcx*2]
0x1800093b8  sub     ax, 53h ; 'S'
0x1800093bc  mov     ecx, 0FFDFh
0x1800093c1  test    cx, ax
0x1800093c4  jz      short loc_1800093CF
0x1800093c6  lea     r15, aErrorWrongForm_0; "!error: wrong format for wide string!"
0x1800093cd  jmp     short loc_1800093F0
0x1800093cf  test    r15, r15
0x1800093d2  jnz     short loc_1800093E2
0x1800093d4  lea     r15, aNull_1; "<NULL>"
0x1800093db  mov     esi, 6
0x1800093e0  jmp     short loc_1800093F0
0x1800093e2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800093e6  inc     rsi
0x1800093e9  cmp     [r15+rsi*2], r13w
0x1800093ee  jnz     short loc_1800093E6
0x1800093f0  mov     r8, rsi
0x1800093f3  mov     rdx, r15
0x1800093f6  mov     rcx, rbx; Src
0x1800093f9  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800093fe  mov     r9, rbx
0x180009401  mov     r8, [rbp+var_40]
0x180009405  mov     rdx, [rbp+var_50]
0x180009409  mov     rcx, rdi
0x18000940c  call    ?FormatArguments@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV23@@Z; ArgumentWriter::FormatArguments(wchar_t const *,wchar_t const *,std::wstring &)
0x180009411  nop
0x180009412  cmp     r12, 7
0x180009416  jbe     loc_180009350
0x18000941c  mov     rcx, r14
0x18000941f  lea     rax, ds:2[r12*2]
0x180009427  cmp     rax, 1000h
0x18000942d  jb      short loc_180009456
0x18000942f  mov     r14, [r14-8]
0x180009433  sub     rcx, r14
0x180009436  lea     rax, [rcx-8]
0x18000943a  cmp     rax, 1Fh
0x18000943e  jbe     short loc_180009456
0x180009440  mov     [rsp+80h+Reserved], r13; Reserved
0x180009445  xor     r9d, r9d; LineNo
0x180009448  xor     r8d, r8d; FileName
0x18000944b  xor     edx, edx; FunctionName
0x18000944d  xor     ecx, ecx; Expression
0x18000944f  call    cs:__imp__invoke_watson
0x180009456  mov     rcx, r14; Block
0x180009459  call    cs:__imp_free
0x18000945f  jmp     loc_180009350
```
