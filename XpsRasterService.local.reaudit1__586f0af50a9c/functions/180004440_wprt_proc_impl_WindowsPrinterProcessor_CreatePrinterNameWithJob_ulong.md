# wprt::proc::impl::WindowsPrinterProcessor::CreatePrinterNameWithJob(ulong)

- ea: `0x180004440`
- end: `0x1800046a7`
- name: `?CreatePrinterNameWithJob@WindowsPrinterProcessor@impl@proc@wprt@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180004b20`

## callees

- `0x180003180`
- `0x180003580`
- `0x180003fd0`
- `0x180004180`
- `0x180004440`
- `0x180005510`
- `0x1800055a0`
- `0x1800a02f7`
- `0x1800a031b`
- `0x1800b30ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180004666`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180004666`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void **__fastcall wprt::proc::impl::WindowsPrinterProcessor::CreatePrinterNameWithJob(
        __int64 a1,
        void **a2,
        unsigned int a3)
{
  void **v4; // rdi
  PCWSTR StringRawBuffer_0; // rax
  __int64 v6; // r8
  void **v7; // rdx
  void *v8; // rcx
  __int64 v9; // rdx
  void *v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 v12; // r14
  void **v13; // rsi
  _WORD *v14; // r10
  char v16[4]; // [rsp+30h] [rbp-A8h] BYREF
  int v17; // [rsp+34h] [rbp-A4h]
  void *Src[2]; // [rsp+38h] [rbp-A0h] BYREF
  __int128 v19; // [rsp+48h] [rbp-90h]
  void **v20; // [rsp+58h] [rbp-80h]
  void *Block; // [rsp+60h] [rbp-78h] BYREF
  unsigned __int64 v22; // [rsp+78h] [rbp-60h]
  _BYTE v23[6]; // [rsp+AAh] [rbp-2Eh] BYREF

  v4 = a2;
  v20 = a2;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = (void *)7;
  *(_WORD *)a2 = 0;
  v17 = 1;
  StringRawBuffer_0 = WindowsGetStringRawBuffer_0(*(HSTRING *)(a1 + 8), 0);
  *(_OWORD *)Src = 0;
  v19 = 0;
  v6 = -1;
  do
    ++v6;
  while ( StringRawBuffer_0[v6] );
  try
  {
    std::wstring::_Construct<1,wchar_t const *>(Src, StringRawBuffer_0);
    v17 = 3;
    if ( v4 != Src )
    {
      v7 = Src;
      if ( *((_QWORD *)&v19 + 1) >= 8u )
        v7 = (void **)Src[0];
      std::wstring::assign(v4, v7);
    }
    if ( *((_QWORD *)&v19 + 1) >= 8u )
    {
      v8 = Src[0];
      if ( (unsigned __int64)(2LL * *((_QWORD *)&v19 + 1) + 2) >= 0x1000 )
      {
        v9 = 2LL * *((_QWORD *)&v19 + 1) + 41;
        v8 = (void *)*((_QWORD *)Src[0] - 1);
        if ( (unsigned __int64)((char *)Src[0] - (char *)v8 - 8) > 0x1F )
        {
LABEL_22:
          _o__invalid_parameter_noinfo_noreturn(v8, v9);
          __debugbreak();
        }
      }
      operator delete(v8);
    }
    v10 = v4[2];
    v11 = (unsigned __int64)v4[3];
    if ( v11 - (unsigned __int64)v10 < 6 )
    {
      _mm_lfence();
      std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(
        v4,
        6);
    }
    else
    {
      v12 = (__int64)v10 + 6;
      v4[2] = (char *)v10 + 6;
      v13 = v4;
      if ( v11 >= 8 )
        v13 = (void **)*v4;
      memmove_0((char *)v13 + 2 * (_QWORD)v10, L", Job ", 0xCu);
      *((_WORD *)v13 + v12) = 0;
    }
    v14 = v23;
    do
    {
      *--v14 = a3 % 0xA + 48;
      a3 /= 0xAu;
    }
    while ( a3 );
    std::wstring::wstring(&Block, v14, v23, v16);
    v17 = 15;
    std::wstring::append(v4);
    if ( v22 >= 8 )
    {
      v8 = Block;
      if ( 2 * v22 + 2 >= 0x1000 )
      {
        v9 = 2 * v22 + 41;
        v8 = (void *)*((_QWORD *)Block - 1);
        if ( (unsigned __int64)((_BYTE *)Block - (_BYTE *)v8 - 8) > 0x1F )
          goto LABEL_22;
      }
      operator delete(v8);
    }
  }
  catch ( ... )
  {
    return v20;
  }
  return v4;
}

```

## disassembly

```asm
0x180004440  mov     [rsp+arg_10], rbx
0x180004445  mov     [rsp+arg_18], rsi
0x18000444a  push    rdi
0x18000444b  push    r14
0x18000444d  push    r15
0x18000444f  sub     rsp, 0C0h
0x180004456  mov     rax, cs:__security_cookie
0x18000445d  xor     rax, rsp
0x180004460  mov     [rsp+0D8h+var_28], rax
0x180004468  mov     ebx, r8d
0x18000446b  mov     rdi, rdx
0x18000446e  mov     [rsp+0D8h+var_80], rdx
0x180004473  xor     r15d, r15d
0x180004476  mov     [rsp+0D8h+var_A4], r15d
0x18000447b  xorps   xmm0, xmm0
0x18000447e  movups  xmmword ptr [rdx], xmm0
0x180004481  mov     [rdx+10h], r15
0x180004485  mov     qword ptr [rdx+18h], 7
0x18000448d  mov     [rdx], r15w
0x180004491  mov     [rsp+0D8h+var_A4], 1
0x180004499  xor     edx, edx; length
0x18000449b  mov     rcx, [rcx+8]; string
0x18000449f  call    WindowsGetStringRawBuffer_0
0x1800044a4  xorps   xmm0, xmm0
0x1800044a7  movups  xmmword ptr [rsp+0D8h+Src], xmm0
0x1800044ac  xorps   xmm1, xmm1
0x1800044af  movdqu  [rsp+0D8h+var_90], xmm1
0x1800044b5  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800044bc  nop     dword ptr [rax+00h]
0x1800044c0  inc     r8
0x1800044c3  cmp     word ptr [rax+r8*2], 0
0x1800044c9  jnz     short loc_1800044C0
0x1800044cb  mov     rdx, rax
0x1800044ce  lea     rcx, [rsp+0D8h+Src]
0x1800044d3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800044d8  mov     [rsp+0D8h+var_A4], 3
0x1800044e0  lea     rax, [rsp+0D8h+Src]
0x1800044e5  cmp     rdi, rax
0x1800044e8  jz      short loc_180004509
0x1800044ea  lea     rdx, [rsp+0D8h+Src]
0x1800044ef  cmp     qword ptr [rsp+0D8h+var_90+8], 8
0x1800044f5  cmovnb  rdx, [rsp+0D8h+Src]; Src
0x1800044fb  mov     r8, qword ptr [rsp+0D8h+var_90]
0x180004500  mov     rcx, rdi; void *
0x180004503  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180004508  nop
0x180004509  mov     rdx, qword ptr [rsp+0D8h+var_90+8]
0x18000450e  cmp     rdx, 8
0x180004512  jb      short loc_18000454B
0x180004514  lea     rdx, ds:2[rdx*2]
0x18000451c  mov     rcx, [rsp+0D8h+Src]
0x180004521  mov     rax, rcx
0x180004524  cmp     rdx, 1000h
0x18000452b  jb      short loc_180004546
0x18000452d  add     rdx, 27h ; '''
0x180004531  mov     rcx, [rcx-8]; Block
0x180004535  sub     rax, rcx
0x180004538  add     rax, 0FFFFFFFFFFFFFFF8h
0x18000453c  cmp     rax, 1Fh
0x180004540  ja      loc_180004666
0x180004546  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000454b  mov     rcx, [rdi+10h]
0x18000454f  mov     rdx, [rdi+18h]
0x180004553  mov     rax, rdx
0x180004556  sub     rax, rcx
0x180004559  cmp     rax, 6
0x18000455d  jb      short loc_180004590
0x18000455f  lea     r14, [rcx+6]
0x180004563  mov     [rdi+10h], r14
0x180004567  mov     rsi, rdi
0x18000456a  cmp     rdx, 8
0x18000456e  jb      short loc_180004573
0x180004570  mov     rsi, [rdi]
0x180004573  lea     rcx, [rsi+rcx*2]; void *
0x180004577  mov     r8d, 0Ch; Size
0x18000457d  lea     rdx, aJob; ", Job "
0x180004584  call    memmove_0
0x180004589  mov     [rsi+r14*2], r15w
0x18000458e  jmp     short loc_1800045B2
0x180004590  lfence
0x180004593  mov     [rsp+0D8h+var_B8], 6; __int64
0x18000459c  lea     r9, aJob; ", Job "
0x1800045a3  xor     r8d, r8d
0x1800045a6  lea     edx, [r8+6]
0x1800045aa  mov     rcx, rdi; Src
0x1800045ad  call    ??$_Reallocate_grow_by@V_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64)
0x1800045b2  lea     r10, [rsp+0D8h+var_2E]
0x1800045ba  nop     word ptr [rax+rax+00h]
0x1800045c0  sub     r10, 2
0x1800045c4  mov     eax, 0CCCCCCCDh
0x1800045c9  mul     ebx
0x1800045cb  shr     edx, 3
0x1800045ce  movzx   eax, dx
0x1800045d1  shl     ax, 2
0x1800045d5  lea     ecx, [rax+rdx]
0x1800045d8  add     cx, cx
0x1800045db  sub     bx, cx
0x1800045de  add     bx, 30h ; '0'
0x1800045e2  mov     [r10], bx
0x1800045e6  mov     ebx, edx
0x1800045e8  test    edx, edx
0x1800045ea  jnz     short loc_1800045C0
0x1800045ec  lea     r9, [rsp+0D8h+var_A8]
0x1800045f1  lea     r8, [rsp+0D8h+var_2E]
0x1800045f9  mov     rdx, r10
0x1800045fc  lea     rcx, [rsp+0D8h+Block]
0x180004601  call    ??$?0PEA_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEA_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t *,wchar_t *,std::allocator<wchar_t> const &)
0x180004606  mov     [rsp+0D8h+var_A4], 0Fh
0x18000460e  lea     rdx, [rsp+0D8h+Block]
0x180004613  cmp     [rsp+0D8h+var_60], 8
0x180004619  cmovnb  rdx, [rsp+0D8h+Block]
0x18000461f  mov     r8, [rsp+0D8h+var_68]
0x180004624  mov     rcx, rdi; Src
0x180004627  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18000462c  nop
0x18000462d  mov     rdx, [rsp+0D8h+var_60]
0x180004632  cmp     rdx, 8
0x180004636  jb      short loc_180004673
0x180004638  lea     rdx, ds:2[rdx*2]
0x180004640  mov     rcx, [rsp+0D8h+Block]; Block
0x180004645  mov     rax, rcx
0x180004648  cmp     rdx, 1000h
0x18000464f  jb      short loc_18000466D
0x180004651  add     rdx, 27h ; '''
0x180004655  mov     rcx, [rcx-8]
0x180004659  sub     rax, rcx
0x18000465c  add     rax, 0FFFFFFFFFFFFFFF8h
0x180004660  cmp     rax, 1Fh
0x180004664  jbe     short loc_18000466D
0x180004666  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x18000466c  int     3; Trap to Debugger
0x18000466d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004672  nop
0x180004673  jmp     short loc_18000467A
0x180004675  mov     rdi, [rsp+0D8h+var_80]
0x18000467a  mov     rax, rdi
0x18000467d  mov     rcx, [rsp+0D8h+var_28]
0x180004685  xor     rcx, rsp; StackCookie
0x180004688  call    __security_check_cookie
0x18000468d  lea     r11, [rsp+0D8h+var_18]
0x180004695  mov     rbx, [r11+30h]
0x180004699  mov     rsi, [r11+38h]
0x18000469d  mov     rsp, r11
0x1800046a0  pop     r15
0x1800046a2  pop     r14
0x1800046a4  pop     rdi
0x1800046a5  retn
```
