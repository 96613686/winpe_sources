# ArgumentWriter::FormatArguments<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong const &)

- ea: `0x180004fd0`
- end: `0x180005224`
- name: `??$FormatArguments@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@K@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBV12@2AEBK@Z`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180003c70`

## callees

- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x18000465c`
- `0x180004d84`
- `0x180004fd0`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180005142`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000520e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180005142`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000520e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180005218`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180005218`

## string_xrefs

- `0x180005022`: `Failed to create registry key "%s\%s": %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ArgumentWriter::FormatArguments<std::wstring,std::wstring,unsigned long>(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD *v10; // r14
  const wchar_t *v11; // rsi
  wchar_t v12; // r8
  const wchar_t *v13; // r13
  __int64 v14; // r8
  void **v16; // rax
  char *v17; // rsi
  unsigned __int64 v18; // r12
  __int64 v19; // r15
  char *v20; // rcx
  const wchar_t *v21; // [rsp+30h] [rbp-51h] BYREF
  __int64 v22; // [rsp+48h] [rbp-39h]
  __int64 v23; // [rsp+50h] [rbp-31h]
  const wchar_t *v24; // [rsp+58h] [rbp-29h]
  __int64 v25; // [rsp+60h] [rbp-21h]
  void *Block[2]; // [rsp+68h] [rbp-19h] BYREF
  __int64 v27; // [rsp+78h] [rbp-9h]
  unsigned __int64 v28; // [rsp+80h] [rbp-1h]

  v24 = a3;
  v10 = a5;
  v25 = a1;
  v23 = a6;
  v22 = a7;
  v11 = L"Failed to create registry key \"%s\\%s\": %d";
  if ( L"Failed to create registry key \"%s\\%s\": %d" >= a3 )
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
    v13 = v11 + 1;
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
  if ( !(unsigned __int8)ArgumentWriter::TryParseFormatSpecificationField(&v21, a3, a4, Block) )
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
  ArgumentWriter::FormatArguments<std::wstring,unsigned long>(a1, v21, v24, a4, v23, v22);
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
0x180004fd0  mov     [rsp-8+arg_8], rbx
0x180004fd5  push    rbp
0x180004fd6  push    rsi
0x180004fd7  push    rdi
0x180004fd8  push    r12
0x180004fda  push    r13
0x180004fdc  push    r14
0x180004fde  push    r15
0x180004fe0  lea     rbp, [rsp-0Fh]
0x180004fe5  sub     rsp, 90h
0x180004fec  mov     rax, cs:__security_cookie
0x180004ff3  xor     rax, rsp
0x180004ff6  mov     [rbp+3Fh+var_38], rax
0x180004ffa  mov     rbx, r9
0x180004ffd  mov     r12, r8
0x180005000  mov     [rbp+3Fh+var_68], r8
0x180005004  mov     rdi, rcx
0x180005007  mov     r14, [rbp+3Fh+arg_20]
0x18000500b  mov     [rbp+3Fh+var_60], rcx
0x18000500f  mov     rax, [rbp+3Fh+arg_28]
0x180005013  mov     [rbp+3Fh+var_70], rax
0x180005017  mov     rax, [rbp+3Fh+arg_30]
0x18000501b  mov     [rbp+3Fh+var_78], rax
0x18000501f  xor     r13d, r13d
0x180005022  lea     rsi, aFailedToCreate_0; "Failed to create registry key \"%s\\%s"...
0x180005029  cmp     rsi, r8
0x18000502c  jnb     loc_1800050CA
0x180005032  lfence
0x180005035  lea     r15d, [r13+25h]
0x180005039  xorps   xmm0, xmm0
0x18000503c  movups  xmmword ptr [rbp+3Fh+Block], xmm0
0x180005040  mov     [rbp+3Fh+var_48], r13
0x180005044  mov     [rbp+3Fh+var_40], 7
0x18000504c  mov     word ptr [rbp+3Fh+Block], r13w
0x180005051  movzx   r8d, word ptr [rsi]
0x180005055  lea     r13, [rsi+2]
0x180005059  mov     rsi, r13
0x18000505c  mov     [rbp+3Fh+var_90], r13
0x180005060  cmp     r8w, r15w
0x180005064  jz      short loc_180005078
0x180005066  mov     edx, 1
0x18000506b  mov     rcx, rbx; Src
0x18000506e  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180005073  xor     r13d, r13d
0x180005076  jmp     short loc_1800050B8
0x180005078  cmp     r13, r12
0x18000507b  jz      short loc_18000509A
0x18000507d  cmp     [r13+0], r15w
0x180005082  jnz     short loc_18000509A
0x180005084  mov     r8d, r15d
0x180005087  mov     edx, 1
0x18000508c  mov     rcx, rbx; Src
0x18000508f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180005094  lea     rsi, [r13+2]
0x180005098  jmp     short loc_180005073
0x18000509a  lea     r9, [rbp+3Fh+Block]
0x18000509e  mov     r8, rbx
0x1800050a1  mov     rdx, r12
0x1800050a4  lea     rcx, [rbp+3Fh+var_90]
0x1800050a8  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x1800050ad  xor     r13d, r13d
0x1800050b0  test    al, al
0x1800050b2  jnz     short loc_18000511C
0x1800050b4  mov     rsi, [rbp+3Fh+var_90]
0x1800050b8  lea     rcx, [rbp+3Fh+Block]
0x1800050bc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800050c1  cmp     rsi, r12
0x1800050c4  jb      loc_180005039
0x1800050ca  xorps   xmm0, xmm0
0x1800050cd  movups  xmmword ptr [rdi], xmm0
0x1800050d0  mov     [rdi+10h], r13
0x1800050d4  mov     [rdi+18h], r13
0x1800050d8  mov     r8, [rbx+10h]
0x1800050dc  cmp     qword ptr [rbx+18h], 7
0x1800050e1  jbe     short loc_1800050E6
0x1800050e3  mov     rbx, [rbx]
0x1800050e6  mov     rdx, rbx
0x1800050e9  mov     rcx, rdi
0x1800050ec  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800050f1  nop
0x1800050f2  mov     rax, rdi
0x1800050f5  mov     rcx, [rbp+3Fh+var_38]
0x1800050f9  xor     rcx, rsp; StackCookie
0x1800050fc  call    __security_check_cookie
0x180005101  mov     rbx, [rsp+0C0h+arg_8]
0x180005109  add     rsp, 90h
0x180005110  pop     r15
0x180005112  pop     r14
0x180005114  pop     r13
0x180005116  pop     r12
0x180005118  pop     rdi
0x180005119  pop     rsi
0x18000511a  pop     rbp
0x18000511b  retn
0x18000511c  cmp     qword ptr [r14+18h], 7
0x180005121  jbe     short loc_180005126
0x180005123  mov     r14, [r14]
0x180005126  mov     rax, [rbp+3Fh+var_48]
0x18000512a  lea     rcx, [rax-1]
0x18000512e  cmp     rcx, rax
0x180005131  jbe     short loc_180005149
0x180005133  mov     [rsp+0C0h+Reserved], r13; Reserved
0x180005138  xor     r9d, r9d; LineNo
0x18000513b  xor     r8d, r8d; FileName
0x18000513e  xor     edx, edx; FunctionName
0x180005140  xor     ecx, ecx; Expression
0x180005142  call    cs:__imp__invoke_watson
0x180005149  lfence
0x18000514c  lea     rax, [rbp+3Fh+Block]
0x180005150  mov     rsi, [rbp+3Fh+Block]
0x180005154  mov     r12, [rbp+3Fh+var_40]
0x180005158  cmp     r12, 7
0x18000515c  cmova   rax, rsi
0x180005160  movzx   eax, word ptr [rax+rcx*2]
0x180005164  sub     ax, 53h ; 'S'
0x180005168  mov     ecx, 0FFDFh
0x18000516d  test    cx, ax
0x180005170  jz      short loc_18000517B
0x180005172  lea     r14, aErrorWrongForm_0; "!error: wrong format for wide string!"
0x180005179  jmp     short loc_18000519D
0x18000517b  test    r14, r14
0x18000517e  jnz     short loc_18000518F
0x180005180  lea     r14, aNull_1; "<NULL>"
0x180005187  mov     r15d, 6
0x18000518d  jmp     short loc_18000519D
0x18000518f  or      r15, 0FFFFFFFFFFFFFFFFh
0x180005193  inc     r15
0x180005196  cmp     [r14+r15*2], r13w
0x18000519b  jnz     short loc_180005193
0x18000519d  mov     r8, r15
0x1800051a0  mov     rdx, r14
0x1800051a3  mov     rcx, rbx; Src
0x1800051a6  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800051ab  mov     rax, [rbp+3Fh+var_78]
0x1800051af  mov     [rsp+0C0h+var_98], rax
0x1800051b4  mov     rax, [rbp+3Fh+var_70]
0x1800051b8  mov     [rsp+0C0h+Reserved], rax
0x1800051bd  mov     r9, rbx
0x1800051c0  mov     r8, [rbp+3Fh+var_68]
0x1800051c4  mov     rdx, [rbp+3Fh+var_90]
0x1800051c8  mov     rcx, rdi
0x1800051cb  call    ??$FormatArguments@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBV12@AEBK@Z; ArgumentWriter::FormatArguments<std::wstring,ulong>(wchar_t const *,wchar_t const *,std::wstring &,std::wstring const &,ulong const &)
0x1800051d0  nop
0x1800051d1  cmp     r12, 7
0x1800051d5  jbe     loc_1800050F2
0x1800051db  mov     rcx, rsi
0x1800051de  lea     rax, ds:2[r12*2]
0x1800051e6  cmp     rax, 1000h
0x1800051ec  jb      short loc_180005215
0x1800051ee  mov     rsi, [rsi-8]
0x1800051f2  sub     rcx, rsi
0x1800051f5  lea     rax, [rcx-8]
0x1800051f9  cmp     rax, 1Fh
0x1800051fd  jbe     short loc_180005215
0x1800051ff  mov     [rsp+0C0h+Reserved], r13; Reserved
0x180005204  xor     r9d, r9d; LineNo
0x180005207  xor     r8d, r8d; FileName
0x18000520a  xor     edx, edx; FunctionName
0x18000520c  xor     ecx, ecx; Expression
0x18000520e  call    cs:__imp__invoke_watson
0x180005215  mov     rcx, rsi; Block
0x180005218  call    cs:__imp_free
0x18000521e  jmp     loc_1800050F2
```
