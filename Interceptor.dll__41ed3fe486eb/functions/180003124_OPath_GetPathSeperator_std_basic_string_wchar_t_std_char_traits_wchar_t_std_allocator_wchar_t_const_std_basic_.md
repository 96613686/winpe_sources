# OPath::GetPathSeperator(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,wchar_t &)

- ea: `0x180003124`
- end: `0x180003358`
- name: `?GetPathSeperator@OPath@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@AEA_W@Z`
- size: `564`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180002b40`
- `0x180020494`

## callees

- `0x180002358`
- `0x180003124`
- `0x180003e90`
- `0x180003fc4`
- `0x18000410c`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800031d0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000325a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800032f5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800031d0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000325a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800032f5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800031da`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180003264`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800032ff`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800031da`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180003264`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800032ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall OPath::GetPathSeperator(_QWORD *a1, void *a2, __int16 *a3)
{
  _BOOL8 v6; // rbx
  void *v7; // rdx
  __int64 v8; // rdi
  bool v9; // r14
  void *v10; // rdx
  __int64 v11; // rbx
  wchar_t *v12; // rdi
  __int64 v13; // rsi
  void *v14; // rdx
  __int16 v15; // cx
  void *Block[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v18; // [rsp+40h] [rbp-20h]

  *(_OWORD *)Block = 0;
  v18 = 0;
  std::wstring::_Construct<1,wchar_t const *>(Block, L"file://", 7);
  v6 = OString::StartsWith(a1, (__int64 *)Block);
  if ( *((_QWORD *)&v18 + 1) > 7u )
  {
    v7 = Block[0];
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v18 + 1) + 2) >= 0x1000 )
    {
      v7 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v7 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v7);
  }
  v8 = 16 * v6;
  *(_OWORD *)Block = 0;
  v18 = 0;
  std::wstring::_Construct<1,wchar_t const *>(Block, L"http://", 7);
  v9 = OString::StartsWith(a1, (__int64 *)Block);
  if ( *((_QWORD *)&v18 + 1) > 7u )
  {
    v10 = Block[0];
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v18 + 1) + 2) >= 0x1000 )
    {
      v10 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v10 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v10);
  }
  v11 = 16;
  if ( !v9 )
    v11 = v8;
  *(_OWORD *)Block = 0;
  v18 = 0;
  v12 = L"/";
  std::wstring::_Construct<1,wchar_t const *>(Block, L"/", 1);
  v13 = std::wstring::find(a1, Block, v11);
  if ( *((_QWORD *)&v18 + 1) > 7u )
  {
    v14 = Block[0];
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v18 + 1) + 2) >= 0x1000 )
    {
      v14 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v14 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v14);
  }
  v15 = 47;
  if ( v13 == -1 )
    v15 = 92;
  *a3 = v15;
  if ( v13 == -1 )
    v12 = L"\\";
  std::wstring::operator=(a2, v12);
  return v13 != -1;
}

```

## disassembly

```asm
0x180003124  mov     [rsp-38h+arg_18], rbx
0x180003129  push    rbp
0x18000312a  push    rsi
0x18000312b  push    rdi
0x18000312c  push    r12
0x18000312e  push    r13
0x180003130  push    r14
0x180003132  push    r15
0x180003134  mov     rbp, rsp
0x180003137  sub     rsp, 60h
0x18000313b  mov     rax, cs:__security_cookie
0x180003142  xor     rax, rsp
0x180003145  mov     [rbp+var_10], rax
0x180003149  mov     r15, r8
0x18000314c  mov     r12, rdx
0x18000314f  mov     rsi, rcx
0x180003152  xorps   xmm0, xmm0
0x180003155  movups  xmmword ptr [rbp+Block], xmm0
0x180003159  xorps   xmm1, xmm1
0x18000315c  movdqu  [rbp+var_20], xmm1
0x180003161  mov     r14d, 7
0x180003167  mov     r8d, r14d
0x18000316a  lea     rdx, aFile; "file://"
0x180003171  lea     rcx, [rbp+Block]
0x180003175  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000317a  lea     rdx, [rbp+Block]
0x18000317e  mov     rcx, rsi
0x180003181  call    ?StartsWith@OString@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0_N@Z; OString::StartsWith(std::wstring const &,std::wstring const &,bool)
0x180003186  movzx   ebx, al
0x180003189  mov     r13d, 1000h
0x18000318f  mov     rcx, qword ptr [rbp+var_20+8]
0x180003193  cmp     rcx, r14
0x180003196  jbe     short loc_1800031E0
0x180003198  mov     rdx, [rbp+Block]
0x18000319c  mov     rax, rdx
0x18000319f  lea     rcx, ds:2[rcx*2]
0x1800031a7  cmp     rcx, r13
0x1800031aa  jb      short loc_1800031D7
0x1800031ac  mov     rdx, [rdx-8]
0x1800031b0  sub     rax, rdx
0x1800031b3  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800031b7  cmp     rax, 1Fh
0x1800031bb  jbe     short loc_1800031D7
0x1800031bd  mov     [rsp+60h+Reserved], 0; Reserved
0x1800031c6  xor     r9d, r9d; LineNo
0x1800031c9  xor     r8d, r8d; FileName
0x1800031cc  xor     edx, edx; FunctionName
0x1800031ce  xor     ecx, ecx; Expression
0x1800031d0  call    cs:__imp__invoke_watson
0x1800031d7  mov     rcx, rdx; Block
0x1800031da  call    cs:__imp_free
0x1800031e0  mov     rdi, rbx
0x1800031e3  shl     rdi, 4
0x1800031e7  xorps   xmm0, xmm0
0x1800031ea  movups  xmmword ptr [rbp+Block], xmm0
0x1800031ee  xorps   xmm1, xmm1
0x1800031f1  movdqu  [rbp+var_20], xmm1
0x1800031f6  mov     r8, r14
0x1800031f9  lea     rdx, aHttp; "http://"
0x180003200  lea     rcx, [rbp+Block]
0x180003204  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180003209  lea     rdx, [rbp+Block]
0x18000320d  mov     rcx, rsi
0x180003210  call    ?StartsWith@OString@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0_N@Z; OString::StartsWith(std::wstring const &,std::wstring const &,bool)
0x180003215  mov     r14b, al
0x180003218  mov     rcx, qword ptr [rbp+var_20+8]
0x18000321c  cmp     rcx, 7
0x180003220  jbe     short loc_18000326A
0x180003222  mov     rdx, [rbp+Block]
0x180003226  mov     rax, rdx
0x180003229  lea     rcx, ds:2[rcx*2]
0x180003231  cmp     rcx, r13
0x180003234  jb      short loc_180003261
0x180003236  mov     rdx, [rdx-8]
0x18000323a  sub     rax, rdx
0x18000323d  add     rax, 0FFFFFFFFFFFFFFF8h
0x180003241  cmp     rax, 1Fh
0x180003245  jbe     short loc_180003261
0x180003247  mov     [rsp+60h+Reserved], 0; Reserved
0x180003250  xor     r9d, r9d; LineNo
0x180003253  xor     r8d, r8d; FileName
0x180003256  xor     edx, edx; FunctionName
0x180003258  xor     ecx, ecx; Expression
0x18000325a  call    cs:__imp__invoke_watson
0x180003261  mov     rcx, rdx; Block
0x180003264  call    cs:__imp_free
0x18000326a  mov     ebx, 10h
0x18000326f  test    r14b, r14b
0x180003272  cmovz   rbx, rdi
0x180003276  xorps   xmm0, xmm0
0x180003279  movups  xmmword ptr [rbp+Block], xmm0
0x18000327d  xorps   xmm1, xmm1
0x180003280  movdqu  [rbp+var_20], xmm1
0x180003285  mov     r8d, 1
0x18000328b  lea     rdi, asc_18002F444; "/"
0x180003292  mov     rdx, rdi
0x180003295  lea     rcx, [rbp+Block]
0x180003299  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000329e  mov     r8, rbx
0x1800032a1  lea     rdx, [rbp+Block]
0x1800032a5  mov     rcx, rsi
0x1800032a8  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x1800032ad  nop     dword ptr [rax]
0x1800032b0  mov     rsi, rax
0x1800032b3  mov     rcx, qword ptr [rbp+var_20+8]
0x1800032b7  cmp     rcx, 7
0x1800032bb  jbe     short loc_180003305
0x1800032bd  mov     rdx, [rbp+Block]
0x1800032c1  mov     rax, rdx
0x1800032c4  lea     rcx, ds:2[rcx*2]
0x1800032cc  cmp     rcx, r13
0x1800032cf  jb      short loc_1800032FC
0x1800032d1  mov     rdx, [rdx-8]
0x1800032d5  sub     rax, rdx
0x1800032d8  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800032dc  cmp     rax, 1Fh
0x1800032e0  jbe     short loc_1800032FC
0x1800032e2  mov     [rsp+60h+Reserved], 0; Reserved
0x1800032eb  xor     r9d, r9d; LineNo
0x1800032ee  xor     r8d, r8d; FileName
0x1800032f1  xor     edx, edx; FunctionName
0x1800032f3  xor     ecx, ecx; Expression
0x1800032f5  call    cs:__imp__invoke_watson
0x1800032fc  mov     rcx, rdx; Block
0x1800032ff  call    cs:__imp_free
0x180003305  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180003309  setnz   bl
0x18000330c  mov     ecx, 2Fh ; '/'
0x180003311  lea     eax, [rcx+2Dh]
0x180003314  cmovz   cx, ax
0x180003318  mov     [r15], cx
0x18000331c  lea     rax, asc_18002F1F4; "\\"
0x180003323  cmovz   rdi, rax
0x180003327  mov     rdx, rdi; Src
0x18000332a  mov     rcx, r12; void *
0x18000332d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x180003332  mov     al, bl
0x180003334  mov     rcx, [rbp+var_10]
0x180003338  xor     rcx, rsp; StackCookie
0x18000333b  call    __security_check_cookie
0x180003340  mov     rbx, [rsp+60h+arg_18]
0x180003348  add     rsp, 60h
0x18000334c  pop     r15
0x18000334e  pop     r14
0x180003350  pop     r13
0x180003352  pop     r12
0x180003354  pop     rdi
0x180003355  pop     rsi
0x180003356  pop     rbp
0x180003357  retn
```
