# ArgumentWriter::FormatArguments<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180023028`
- end: `0x18002327c`
- name: `??$FormatArguments@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBV12@AEBK2@Z`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180022824`

## callees

- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x18000465c`
- `0x180023028`
- `0x180023b40`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002319a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023266`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002319a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023266`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180023270`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180023270`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ArgumentWriter::FormatArguments<std::wstring,unsigned long,std::wstring>(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD *v10; // r14
  const wchar_t *v11; // rsi
  wchar_t v12; // r8
  unsigned __int16 *v13; // r13
  __int64 v14; // r8
  void **v16; // rax
  char *v17; // rsi
  unsigned __int64 v18; // r12
  __int64 v19; // r15
  char *v20; // rcx
  const wchar_t *v21; // [rsp+30h] [rbp-51h] BYREF
  __int64 v22; // [rsp+40h] [rbp-41h]
  __int64 v23; // [rsp+48h] [rbp-39h]
  unsigned __int16 *v24; // [rsp+50h] [rbp-31h]
  __int64 v25; // [rsp+58h] [rbp-29h]
  void *Block[2]; // [rsp+60h] [rbp-21h] BYREF
  __int64 v27; // [rsp+70h] [rbp-11h]
  unsigned __int64 v28; // [rsp+78h] [rbp-9h]

  v24 = a3;
  v10 = a5;
  v25 = a1;
  v23 = a6;
  v22 = a7;
  v11 = L"%s::[%d] %s";
  if ( L"%s::[%d] %s" >= a3 )
  {
LABEL_11:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v14 = a4[2];
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    std::wstring::_Construct<2,wchar_t const *>(a1, a4, v14);
    return a1;
  }
  _mm_lfence();
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v27 = 0;
    v28 = 7;
    LOWORD(Block[0]) = 0;
    v12 = *v11;
    v13 = (unsigned __int16 *)(v11 + 1);
    v11 = v13;
    v21 = v13;
    if ( v12 == 37 )
      break;
    std::wstring::append(a4);
LABEL_10:
    std::wstring::_Tidy_deallocate(Block);
    if ( v11 >= a3 )
      goto LABEL_11;
  }
  if ( v13 != a3 && *v13 == 37 )
  {
    std::wstring::append(a4);
    v11 = v13 + 1;
    goto LABEL_10;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)&v21, a3, a4, (__int64)Block) )
  {
    v11 = v21;
    goto LABEL_10;
  }
  if ( a5[3] > 7u )
    v10 = (_QWORD *)*a5;
  if ( !v27 )
    _invoke_watson(0, 0, 0, 0, 0);
  _mm_lfence();
  v16 = Block;
  v17 = (char *)Block[0];
  v18 = v28;
  if ( v28 > 7 )
    v16 = (void **)Block[0];
  if ( ((*((_WORD *)v16 + v27 - 1) - 83) & 0xFFDF) == 0 && v10 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v10 + v19) );
  }
  std::wstring::append(a4);
  ArgumentWriter::FormatArguments<unsigned long,std::wstring>(a1, v21, v24, a4, v23, v22);
  if ( v18 > 7 )
  {
    v20 = v17;
    if ( 2 * v18 + 2 >= 0x1000 )
    {
      v17 = (char *)*((_QWORD *)v17 - 1);
      if ( (unsigned __int64)(v20 - v17 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v17);
  }
  return a1;
}

```

## disassembly

```asm
0x180023028  mov     [rsp-8+arg_8], rbx
0x18002302d  push    rbp
0x18002302e  push    rsi
0x18002302f  push    rdi
0x180023030  push    r12
0x180023032  push    r13
0x180023034  push    r14
0x180023036  push    r15
0x180023038  lea     rbp, [rsp-0Fh]
0x18002303d  sub     rsp, 90h
0x180023044  mov     rax, cs:__security_cookie
0x18002304b  xor     rax, rsp
0x18002304e  mov     [rbp+3Fh+var_40], rax
0x180023052  mov     rbx, r9
0x180023055  mov     r12, r8
0x180023058  mov     [rbp+3Fh+var_70], r8
0x18002305c  mov     rdi, rcx
0x18002305f  mov     r14, [rbp+3Fh+arg_20]
0x180023063  mov     [rbp+3Fh+var_68], rcx
0x180023067  mov     rax, [rbp+3Fh+arg_28]
0x18002306b  mov     [rbp+3Fh+var_78], rax
0x18002306f  mov     rax, [rbp+3Fh+arg_30]
0x180023073  mov     [rbp+3Fh+var_80], rax
0x180023077  xor     r13d, r13d
0x18002307a  lea     rsi, aSDS; "%s::[%d] %s"
0x180023081  cmp     rsi, r8
0x180023084  jnb     loc_180023122
0x18002308a  lfence
0x18002308d  lea     r15d, [r13+25h]
0x180023091  xorps   xmm0, xmm0
0x180023094  movups  xmmword ptr [rbp+3Fh+Block], xmm0
0x180023098  mov     [rbp+3Fh+var_50], r13
0x18002309c  mov     [rbp+3Fh+var_48], 7
0x1800230a4  mov     word ptr [rbp+3Fh+Block], r13w
0x1800230a9  movzx   r8d, word ptr [rsi]
0x1800230ad  lea     r13, [rsi+2]
0x1800230b1  mov     rsi, r13
0x1800230b4  mov     [rbp+3Fh+var_90], r13
0x1800230b8  cmp     r8w, r15w
0x1800230bc  jz      short loc_1800230D0
0x1800230be  mov     edx, 1
0x1800230c3  mov     rcx, rbx; Src
0x1800230c6  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x1800230cb  xor     r13d, r13d
0x1800230ce  jmp     short loc_180023110
0x1800230d0  cmp     r13, r12
0x1800230d3  jz      short loc_1800230F2
0x1800230d5  cmp     [r13+0], r15w
0x1800230da  jnz     short loc_1800230F2
0x1800230dc  mov     r8d, r15d
0x1800230df  mov     edx, 1
0x1800230e4  mov     rcx, rbx; Src
0x1800230e7  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x1800230ec  lea     rsi, [r13+2]
0x1800230f0  jmp     short loc_1800230CB
0x1800230f2  lea     r9, [rbp+3Fh+Block]
0x1800230f6  mov     r8, rbx
0x1800230f9  mov     rdx, r12
0x1800230fc  lea     rcx, [rbp+3Fh+var_90]
0x180023100  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180023105  xor     r13d, r13d
0x180023108  test    al, al
0x18002310a  jnz     short loc_180023174
0x18002310c  mov     rsi, [rbp+3Fh+var_90]
0x180023110  lea     rcx, [rbp+3Fh+Block]
0x180023114  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023119  cmp     rsi, r12
0x18002311c  jb      loc_180023091
0x180023122  xorps   xmm0, xmm0
0x180023125  movups  xmmword ptr [rdi], xmm0
0x180023128  mov     [rdi+10h], r13
0x18002312c  mov     [rdi+18h], r13
0x180023130  mov     r8, [rbx+10h]
0x180023134  cmp     qword ptr [rbx+18h], 7
0x180023139  jbe     short loc_18002313E
0x18002313b  mov     rbx, [rbx]
0x18002313e  mov     rdx, rbx
0x180023141  mov     rcx, rdi
0x180023144  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180023149  nop
0x18002314a  mov     rax, rdi
0x18002314d  mov     rcx, [rbp+3Fh+var_40]
0x180023151  xor     rcx, rsp; StackCookie
0x180023154  call    __security_check_cookie
0x180023159  mov     rbx, [rsp+0C0h+arg_8]
0x180023161  add     rsp, 90h
0x180023168  pop     r15
0x18002316a  pop     r14
0x18002316c  pop     r13
0x18002316e  pop     r12
0x180023170  pop     rdi
0x180023171  pop     rsi
0x180023172  pop     rbp
0x180023173  retn
0x180023174  cmp     qword ptr [r14+18h], 7
0x180023179  jbe     short loc_18002317E
0x18002317b  mov     r14, [r14]
0x18002317e  mov     rax, [rbp+3Fh+var_50]
0x180023182  lea     rcx, [rax-1]
0x180023186  cmp     rcx, rax
0x180023189  jbe     short loc_1800231A1
0x18002318b  mov     [rsp+0C0h+Reserved], r13; Reserved
0x180023190  xor     r9d, r9d; LineNo
0x180023193  xor     r8d, r8d; FileName
0x180023196  xor     edx, edx; FunctionName
0x180023198  xor     ecx, ecx; Expression
0x18002319a  call    cs:__imp__invoke_watson
0x1800231a1  lfence
0x1800231a4  lea     rax, [rbp+3Fh+Block]
0x1800231a8  mov     rsi, [rbp+3Fh+Block]
0x1800231ac  mov     r12, [rbp+3Fh+var_48]
0x1800231b0  cmp     r12, 7
0x1800231b4  cmova   rax, rsi
0x1800231b8  movzx   eax, word ptr [rax+rcx*2]
0x1800231bc  sub     ax, 53h ; 'S'
0x1800231c0  mov     ecx, 0FFDFh
0x1800231c5  test    cx, ax
0x1800231c8  jz      short loc_1800231D3
0x1800231ca  lea     r14, aErrorWrongForm_0; "!error: wrong format for wide string!"
0x1800231d1  jmp     short loc_1800231F5
0x1800231d3  test    r14, r14
0x1800231d6  jnz     short loc_1800231E7
0x1800231d8  lea     r14, aNull_1; "<NULL>"
0x1800231df  mov     r15d, 6
0x1800231e5  jmp     short loc_1800231F5
0x1800231e7  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800231eb  inc     r15
0x1800231ee  cmp     [r14+r15*2], r13w
0x1800231f3  jnz     short loc_1800231EB
0x1800231f5  mov     r8, r15
0x1800231f8  mov     rdx, r14
0x1800231fb  mov     rcx, rbx; Src
0x1800231fe  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180023203  mov     rax, [rbp+3Fh+var_80]
0x180023207  mov     [rsp+0C0h+var_98], rax
0x18002320c  mov     rax, [rbp+3Fh+var_78]
0x180023210  mov     [rsp+0C0h+Reserved], rax
0x180023215  mov     r9, rbx
0x180023218  mov     r8, [rbp+3Fh+var_70]
0x18002321c  mov     rdx, [rbp+3Fh+var_90]
0x180023220  mov     rcx, rdi
0x180023223  call    ??$FormatArguments@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBKAEBV12@@Z; ArgumentWriter::FormatArguments<ulong,std::wstring>(wchar_t const *,wchar_t const *,std::wstring &,ulong const &,std::wstring const &)
0x180023228  nop
0x180023229  cmp     r12, 7
0x18002322d  jbe     loc_18002314A
0x180023233  mov     rcx, rsi
0x180023236  lea     rax, ds:2[r12*2]
0x18002323e  cmp     rax, 1000h
0x180023244  jb      short loc_18002326D
0x180023246  mov     rsi, [rsi-8]
0x18002324a  sub     rcx, rsi
0x18002324d  lea     rax, [rcx-8]
0x180023251  cmp     rax, 1Fh
0x180023255  jbe     short loc_18002326D
0x180023257  mov     [rsp+0C0h+Reserved], r13; Reserved
0x18002325c  xor     r9d, r9d; LineNo
0x18002325f  xor     r8d, r8d; FileName
0x180023262  xor     edx, edx; FunctionName
0x180023264  xor     ecx, ecx; Expression
0x180023266  call    cs:__imp__invoke_watson
0x18002326d  mov     rcx, rsi; Block
0x180023270  call    cs:__imp_free
0x180023276  jmp     loc_18002314A
```
