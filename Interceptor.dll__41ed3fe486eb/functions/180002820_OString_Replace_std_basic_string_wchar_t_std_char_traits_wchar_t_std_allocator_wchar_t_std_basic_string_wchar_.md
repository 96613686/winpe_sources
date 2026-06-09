# OString::Replace(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,unsigned __int64)

- ea: `0x180002820`
- end: `0x180002b3d`
- name: `?Replace@OString@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@1_K@Z`
- size: `797`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180002b40`
- `0x180021358`

## callees

- `0x180002820`
- `0x180003708`
- `0x1800038c0`
- `0x180004044`
- `0x18000410c`
- `0x1800045ec`
- `0x18000465c`
- `0x18000ab0c`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002917`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002a69`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002ab5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002917`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002a69`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002ab5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180002877`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180002877`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000291e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002a70`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002abc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002af9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002b0b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000291e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002a70`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002abc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002af9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002b0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall OString::Replace(_QWORD *a1, __int64 a2)
{
  _QWORD *v4; // rax
  __int64 v5; // r8
  _QWORD *v6; // rdx
  void *v7; // rcx
  _QWORD *v8; // rbx
  _QWORD *v9; // rdx
  __int64 v10; // rbx
  void *v11; // rcx
  void *v12; // rcx
  _QWORD **v13; // rcx
  _QWORD *v14; // rsi
  _QWORD *v15; // rdi
  void *v16[2]; // [rsp+38h] [rbp-41h] BYREF
  void *Block[2]; // [rsp+48h] [rbp-31h] BYREF
  __m128i si128; // [rsp+58h] [rbp-21h]
  void *v19[2]; // [rsp+68h] [rbp-11h] BYREF
  __int128 v20; // [rsp+78h] [rbp-1h]
  _QWORD v21[2]; // [rsp+88h] [rbp+Fh] BYREF
  __m128i v22; // [rsp+98h] [rbp+1Fh]

  if ( a1[2] && *(_QWORD *)(a2 + 16) )
  {
    *(_OWORD *)v16 = 0;
    v4 = malloc(0x30u);
    if ( !v4 )
      std::_Xbad_alloc();
    *v4 = v4;
    v4[1] = v4;
    v16[0] = v4;
    *(_OWORD *)Block = 0;
    si128 = 0;
    v5 = -1;
    if ( a1[2] != -1 )
      v5 = a1[2];
    v6 = a1;
    if ( a1[3] > 7u )
      v6 = (_QWORD *)*a1;
    std::wstring::_Construct<1,wchar_t const *>(Block, v6, v5);
    OString::Split<std::list<std::wstring>>(Block, v16, a2);
    if ( si128.m128i_i64[1] > 7uLL )
    {
      v7 = Block[0];
      if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
      {
        v7 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v7 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v7);
    }
    *(_OWORD *)Block = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Block[0]) = 0;
    v8 = *(_QWORD **)v16[0];
    if ( *(void **)v16[0] != v16[0] )
    {
      std::wstring::operator=(Block);
      while ( 1 )
      {
        v8 = (_QWORD *)*v8;
        if ( v8 == v16[0] )
          break;
        std::wstring::append(Block);
        std::wstring::append(Block);
      }
    }
    *(_OWORD *)v19 = 0;
    v20 = 0;
    v9 = a1;
    if ( a1[3] > 7u )
      v9 = (_QWORD *)*a1;
    std::wstring::_Construct<1,wchar_t const *>(v19, v9, 0);
    v10 = std::operator+<wchar_t>(v21, v19, Block);
    if ( a1 != (_QWORD *)v10 )
    {
      std::wstring::_Tidy_deallocate(a1);
      *(_OWORD *)a1 = *(_OWORD *)v10;
      *((_OWORD *)a1 + 1) = *(_OWORD *)(v10 + 16);
      *(_QWORD *)(v10 + 16) = 0;
      *(_QWORD *)(v10 + 24) = 7;
      *(_WORD *)v10 = 0;
    }
    std::wstring::_Tidy_deallocate(v21);
    v21[0] = 19937;
    v22 = _mm_load_si128((const __m128i *)&_xmm);
    if ( *((_QWORD *)&v20 + 1) > 7u )
    {
      v11 = v19[0];
      if ( (unsigned __int64)(2LL * *((_QWORD *)&v20 + 1) + 2) >= 0x1000 )
      {
        v11 = (void *)*((_QWORD *)v19[0] - 1);
        if ( (unsigned __int64)((char *)v19[0] - (char *)v11 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v11);
    }
    if ( si128.m128i_i64[1] > 7uLL )
    {
      v12 = Block[0];
      if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
      {
        v12 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v12 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v12);
    }
    v13 = (_QWORD **)v16[0];
    **((_QWORD **)v16[0] + 1) = 0;
    v14 = *v13;
    if ( *v13 )
    {
      do
      {
        v15 = (_QWORD *)*v14;
        std::wstring::_Tidy_deallocate(v14 + 2);
        v14[2] = 19937;
        v14[4] = 0;
        v14[5] = 15;
        free(v14);
        v14 = v15;
      }
      while ( v15 );
    }
    free(v16[0]);
  }
}

```

## disassembly

```asm
0x180002820  mov     [rsp-8+arg_18], rbx
0x180002825  push    rbp
0x180002826  push    rsi
0x180002827  push    rdi
0x180002828  push    r13
0x18000282a  push    r14
0x18000282c  lea     rbp, [rsp-37h]
0x180002831  sub     rsp, 0B0h
0x180002838  mov     rax, cs:__security_cookie
0x18000283f  xor     rax, rsp
0x180002842  mov     [rbp+57h+var_28], rax
0x180002846  mov     rsi, r8
0x180002849  mov     rbx, rdx
0x18000284c  mov     rdi, rcx
0x18000284f  xor     r14d, r14d
0x180002852  mov     [rbp+57h+var_A0], r14d
0x180002856  cmp     qword ptr [rcx+10h], 1
0x18000285b  jb      loc_180002B11
0x180002861  cmp     [rdx+10h], r14
0x180002865  jz      loc_180002B11
0x18000286b  xorps   xmm0, xmm0
0x18000286e  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x180002873  lea     ecx, [r14+30h]; Size
0x180002877  call    cs:__imp_malloc
0x18000287d  test    rax, rax
0x180002880  jz      loc_180002B34
0x180002886  mov     [rax], rax
0x180002889  mov     [rax+8], rax
0x18000288d  mov     [rbp+57h+var_98], rax
0x180002891  xorps   xmm0, xmm0
0x180002894  movups  xmmword ptr [rbp+57h+Block], xmm0
0x180002898  xorps   xmm1, xmm1
0x18000289b  movdqu  [rbp+57h+var_78], xmm1
0x1800028a0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800028a4  cmp     [rdi+10h], r8
0x1800028a8  cmovb   r8, [rdi+10h]
0x1800028ad  mov     rdx, rdi
0x1800028b0  cmp     qword ptr [rdi+18h], 7
0x1800028b5  jbe     short loc_1800028BA
0x1800028b7  mov     rdx, [rdi]
0x1800028ba  lea     rcx, [rbp+57h+Block]
0x1800028be  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800028c3  mov     r8, rbx
0x1800028c6  lea     rdx, [rbp+57h+var_98]
0x1800028ca  lea     rcx, [rbp+57h+Block]
0x1800028ce  call    ??$Split@V?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@OString@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@0@Z; OString::Split<std::list<std::wstring>>(std::wstring const &,std::list<std::wstring> &,std::wstring const &)
0x1800028d3  mov     r13d, 1000h
0x1800028d9  mov     rax, qword ptr [rbp+57h+var_78+8]
0x1800028dd  cmp     rax, 7
0x1800028e1  jbe     short loc_180002925
0x1800028e3  mov     rcx, [rbp+57h+Block]; Block
0x1800028e7  mov     rdx, rcx
0x1800028ea  lea     rax, ds:2[rax*2]
0x1800028f2  cmp     rax, r13
0x1800028f5  jb      short loc_18000291E
0x1800028f7  mov     rcx, [rcx-8]
0x1800028fb  sub     rdx, rcx
0x1800028fe  lea     rax, [rdx-8]
0x180002902  cmp     rax, 1Fh
0x180002906  jbe     short loc_18000291E
0x180002908  mov     [rsp+0D0h+Reserved], r14; Reserved
0x18000290d  xor     r9d, r9d; LineNo
0x180002910  xor     r8d, r8d; FileName
0x180002913  xor     edx, edx; FunctionName
0x180002915  xor     ecx, ecx; Expression
0x180002917  call    cs:__imp__invoke_watson
0x18000291e  call    cs:__imp_free
0x180002924  nop
0x180002925  xorps   xmm0, xmm0
0x180002928  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18000292c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180002934  movdqu  [rbp+57h+var_78], xmm1
0x180002939  mov     word ptr [rbp+57h+Block], r14w
0x18000293e  mov     [rbp+57h+var_A0], 3
0x180002945  mov     rax, [rbp+57h+var_98]
0x180002949  mov     rbx, [rax]
0x18000294c  cmp     rbx, rax
0x18000294f  jz      short loc_18000299E
0x180002951  lea     rdx, [rbx+10h]
0x180002955  lea     rcx, [rbp+57h+Block]; void *
0x180002959  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000295e  jmp     short loc_180002995
0x180002960  mov     rdx, rsi
0x180002963  cmp     qword ptr [rsi+18h], 7
0x180002968  jbe     short loc_18000296D
0x18000296a  mov     rdx, [rsi]
0x18000296d  mov     r8, [rsi+10h]
0x180002971  lea     rcx, [rbp+57h+Block]; Src
0x180002975  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18000297a  lea     rdx, [rbx+10h]
0x18000297e  cmp     qword ptr [rdx+18h], 7
0x180002983  jbe     short loc_180002988
0x180002985  mov     rdx, [rdx]
0x180002988  mov     r8, [rbx+20h]
0x18000298c  lea     rcx, [rbp+57h+Block]; Src
0x180002990  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180002995  mov     rbx, [rbx]
0x180002998  cmp     rbx, [rbp+57h+var_98]
0x18000299c  jnz     short loc_180002960
0x18000299e  xorps   xmm0, xmm0
0x1800029a1  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1800029a5  xorps   xmm1, xmm1
0x1800029a8  movdqu  [rbp+57h+var_58], xmm1
0x1800029ad  mov     rdx, rdi
0x1800029b0  cmp     qword ptr [rdi+18h], 7
0x1800029b5  jbe     short loc_1800029BA
0x1800029b7  mov     rdx, [rdi]
0x1800029ba  xor     r8d, r8d
0x1800029bd  lea     rcx, [rbp+57h+var_68]
0x1800029c1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800029c6  nop
0x1800029c7  mov     [rbp+57h+var_A0], 7
0x1800029ce  lea     r8, [rbp+57h+Block]
0x1800029d2  lea     rdx, [rbp+57h+var_68]
0x1800029d6  lea     rcx, [rbp+57h+var_48]
0x1800029da  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1800029df  mov     rbx, rax
0x1800029e2  cmp     rdi, rax
0x1800029e5  jz      short loc_180002A0D
0x1800029e7  mov     rcx, rdi
0x1800029ea  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800029ef  movups  xmm0, xmmword ptr [rbx]
0x1800029f2  movups  xmmword ptr [rdi], xmm0
0x1800029f5  movups  xmm1, xmmword ptr [rbx+10h]
0x1800029f9  movups  xmmword ptr [rdi+10h], xmm1
0x1800029fd  mov     [rbx+10h], r14
0x180002a01  mov     qword ptr [rbx+18h], 7
0x180002a09  mov     [rbx], r14w
0x180002a0d  lea     rcx, [rbp+57h+var_48]
0x180002a11  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180002a16  mov     [rbp+57h+var_48], 4DE1h
0x180002a1e  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180002a26  movdqu  [rbp+57h+var_38], xmm0
0x180002a2b  mov     rax, qword ptr [rbp+57h+var_58+8]
0x180002a2f  cmp     rax, 7
0x180002a33  jbe     short loc_180002A77
0x180002a35  mov     rcx, [rbp+57h+var_68]; Block
0x180002a39  mov     rdx, rcx
0x180002a3c  lea     rax, ds:2[rax*2]
0x180002a44  cmp     rax, r13
0x180002a47  jb      short loc_180002A70
0x180002a49  mov     rcx, [rcx-8]
0x180002a4d  sub     rdx, rcx
0x180002a50  lea     rax, [rdx-8]
0x180002a54  cmp     rax, 1Fh
0x180002a58  jbe     short loc_180002A70
0x180002a5a  mov     [rsp+0D0h+Reserved], r14; Reserved
0x180002a5f  xor     r9d, r9d; LineNo
0x180002a62  xor     r8d, r8d; FileName
0x180002a65  xor     edx, edx; FunctionName
0x180002a67  xor     ecx, ecx; Expression
0x180002a69  call    cs:__imp__invoke_watson
0x180002a70  call    cs:__imp_free
0x180002a76  nop
0x180002a77  mov     rax, qword ptr [rbp+57h+var_78+8]
0x180002a7b  cmp     rax, 7
0x180002a7f  jbe     short loc_180002AC3
0x180002a81  mov     rcx, [rbp+57h+Block]; Block
0x180002a85  mov     rdx, rcx
0x180002a88  lea     rax, ds:2[rax*2]
0x180002a90  cmp     rax, r13
0x180002a93  jb      short loc_180002ABC
0x180002a95  mov     rcx, [rcx-8]
0x180002a99  sub     rdx, rcx
0x180002a9c  lea     rax, [rdx-8]
0x180002aa0  cmp     rax, 1Fh
0x180002aa4  jbe     short loc_180002ABC
0x180002aa6  mov     [rsp+0D0h+Reserved], r14; Reserved
0x180002aab  xor     r9d, r9d; LineNo
0x180002aae  xor     r8d, r8d; FileName
0x180002ab1  xor     edx, edx; FunctionName
0x180002ab3  xor     ecx, ecx; Expression
0x180002ab5  call    cs:__imp__invoke_watson
0x180002abc  call    cs:__imp_free
0x180002ac2  nop
0x180002ac3  mov     rcx, [rbp+57h+var_98]
0x180002ac7  mov     rax, [rcx+8]
0x180002acb  mov     [rax], r14
0x180002ace  mov     rsi, [rcx]
0x180002ad1  test    rsi, rsi
0x180002ad4  jz      short loc_180002B07
0x180002ad6  mov     rdi, [rsi]
0x180002ad9  lea     rcx, [rsi+10h]
0x180002add  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180002ae2  mov     qword ptr [rsi+10h], 4DE1h
0x180002aea  mov     [rsi+20h], r14
0x180002aee  mov     qword ptr [rsi+28h], 0Fh
0x180002af6  mov     rcx, rsi; Block
0x180002af9  call    cs:__imp_free
0x180002aff  mov     rsi, rdi
0x180002b02  test    rdi, rdi
0x180002b05  jnz     short loc_180002AD6
0x180002b07  mov     rcx, [rbp+57h+var_98]; Block
0x180002b0b  call    cs:__imp_free
0x180002b11  mov     rcx, [rbp+57h+var_28]
0x180002b15  xor     rcx, rsp; StackCookie
0x180002b18  call    __security_check_cookie
0x180002b1d  mov     rbx, [rsp+0D0h+arg_18]
0x180002b25  add     rsp, 0B0h
0x180002b2c  pop     r14
0x180002b2e  pop     r13
0x180002b30  pop     rdi
0x180002b31  pop     rsi
0x180002b32  pop     rbp
0x180002b33  retn
0x180002b34  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180002b3a  jmp     short $+2
0x180002b3c  nop
```
