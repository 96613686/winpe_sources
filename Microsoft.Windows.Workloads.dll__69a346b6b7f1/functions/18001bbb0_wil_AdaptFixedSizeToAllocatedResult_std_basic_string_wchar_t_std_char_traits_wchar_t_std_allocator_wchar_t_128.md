# wil::AdaptFixedSizeToAllocatedResult<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,128>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x18001bbb0`
- end: `0x18001bf0d`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0IA@@wil@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `861`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017340`
- `0x18001c040`
- `0x180021b10`

## callees

- `0x1800027d0`
- `0x180002e40`
- `0x180010a50`
- `0x1800127c0`
- `0x18001b9a0`
- `0x18001bbb0`
- `0x180034ef0`
- `0x18003509c`
- `0x18003bed0`
- `0x18003c6e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001be7f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001be7f`

## string_xrefs

- `0x18001bcc9`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.2.162\inc\wil\opensource\wil\win32_helpers.h`
- `0x18001be98`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.2.162\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<std::wstring,128>(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  unsigned __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  int v12; // eax
  int v13; // edi
  unsigned __int64 *v14; // rax
  __int64 v15; // rcx
  bool v16; // cc
  __int128 *v17; // rax
  __int128 v18; // xmm6
  __m128i v19; // xmm7
  __m128i v20; // xmm0
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  _QWORD *v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  int Reserved; // [rsp+28h] [rbp-E0h]
  __int128 v27; // [rsp+38h] [rbp-D0h] BYREF
  __m128i v28; // [rsp+48h] [rbp-C0h]
  unsigned __int64 *v29; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 *v30; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int64 v31; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+70h] [rbp-98h] BYREF
  __m128i si128; // [rsp+80h] [rbp-88h]
  __int64 v34; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v35[256]; // [rsp+98h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F0h] [rbp+E8h]

  v32 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v32) = 0;
  memset(v35, 0, sizeof(v35));
  v31 = 0;
  v29 = &v31;
  v34 = 128;
  v30 = (unsigned __int64 *)v35;
  v4 = *(_QWORD *)(a2 + 112);
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 **, __int64 *, unsigned __int64 **))(*(_QWORD *)v4 + 32LL))(
         v4,
         &v30,
         &v34,
         &v29);
  if ( (v5 & 0x80000000) != 0 )
  {
    _mm_lfence();
    std::wstring::_Tidy_deallocate(&v32);
    v6 = *(_QWORD *)(a2 + 112);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
    return v5;
  }
  v8 = v31;
  if ( v31 > 0x80 )
  {
    while ( 1 )
    {
      v11 = v8;
      v12 = wil::details::string_maker<std::wstring>::make(&v32, 0, v8 - 1);
      v13 = v12;
      if ( v12 < 0 )
        break;
      v14 = (unsigned __int64 *)&v32;
      if ( si128.m128i_i64[1] > 7uLL )
        v14 = (unsigned __int64 *)v32;
      v29 = v14;
      v30 = &v31;
      v34 = v11;
      v15 = *(_QWORD *)(a2 + 112);
      if ( !v15 )
        wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
      v13 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 **, __int64 *, unsigned __int64 **))(*(_QWORD *)v15 + 32LL))(
              v15,
              &v29,
              &v34,
              &v30);
      if ( v13 < 0 )
      {
        _mm_lfence();
        goto LABEL_34;
      }
      v8 = v31;
      v16 = v31 <= v11;
      if ( v31 < v11 )
      {
        if ( si128.m128i_i64[0] < v31 - 1 )
          std::_String_val<std::_Simple_types<char>>::_Xran();
        si128.m128i_i64[0] = v31 - 1;
        v17 = &v32;
        if ( si128.m128i_i64[1] > 7uLL )
          v17 = (__int128 *)v32;
        *((_WORD *)v17 + v31 - 1) = 0;
        v8 = v31;
        v16 = v31 <= v11;
      }
      if ( v16 )
        goto LABEL_21;
    }
    _mm_lfence();
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x170,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.2.162\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      (const char *)(unsigned int)v12,
      Reserved);
LABEL_34:
    std::wstring::_Tidy_deallocate(&v32);
    v25 = *(_QWORD *)(a2 + 112);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 24LL))(v25);
    return (unsigned int)v13;
  }
  else
  {
    v9 = wil::details::string_maker<std::wstring>::make(&v32, v35, v31 - 1);
    v5 = v9;
    if ( v9 >= 0 )
    {
LABEL_21:
      v18 = v32;
      v27 = v32;
      v19 = si128;
      v28 = si128;
      v20 = _mm_load_si128((const __m128i *)&_xmm);
      si128 = v20;
      LOWORD(v32) = 0;
      if ( (__int128 *)a1 != &v27 )
      {
        v21 = *(_QWORD *)(a1 + 24);
        if ( v21 > 7 )
        {
          v22 = 2 * v21 + 2;
          v23 = *(_QWORD **)a1;
          if ( v22 >= 0x1000 )
          {
            v22 += 39LL;
            if ( (unsigned __int64)v23 - *(v23 - 1) - 8 > 0x1F )
              _invoke_watson(0, 0, 0, 0, 0);
            v23 = (_QWORD *)*(v23 - 1);
          }
          _mm_lfence();
          operator delete(v23, v22);
          v20 = _mm_load_si128((const __m128i *)&_xmm);
        }
        *(_OWORD *)a1 = v18;
        *(__m128i *)(a1 + 16) = v19;
        v28 = v20;
        LOWORD(v27) = 0;
      }
      std::wstring::_Tidy_deallocate(&v27);
      std::wstring::_Tidy_deallocate(&v32);
      v24 = *(_QWORD *)(a2 + 112);
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 24LL))(v24);
      return 0;
    }
    else
    {
      _mm_lfence();
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x165,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.2.162\\inc\\wil\\opensource\\wil\\win32_helpers.h",
        (const char *)(unsigned int)v9,
        Reserved);
      std::wstring::_Tidy_deallocate(&v32);
      v10 = *(_QWORD *)(a2 + 112);
      if ( !v10 )
        return v5;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 24LL))(v10);
      return v5;
    }
  }
}

```

## disassembly

```asm
0x18001bbb0  mov     rax, rsp
0x18001bbb3  mov     [rax+18h], rbx
0x18001bbb7  push    rbp
0x18001bbb8  push    rsi
0x18001bbb9  push    rdi
0x18001bbba  push    r14
0x18001bbbc  push    r15
0x18001bbbe  lea     rbp, [rax-0E8h]
0x18001bbc5  sub     rsp, 1C0h
0x18001bbcc  movaps  xmmword ptr [rax-38h], xmm6
0x18001bbd0  movaps  xmmword ptr [rax-48h], xmm7
0x18001bbd4  mov     rax, cs:__security_cookie
0x18001bbdb  xor     rax, rsp
0x18001bbde  mov     [rbp+0E0h+var_50], rax
0x18001bbe5  mov     rsi, rdx
0x18001bbe8  mov     r14, rcx
0x18001bbeb  xorps   xmm0, xmm0
0x18001bbee  movups  [rsp+1E0h+var_180+8], xmm0
0x18001bbf3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001bbfb  movdqu  [rsp+1E0h+var_170+8], xmm1
0x18001bc01  xor     r15d, r15d
0x18001bc04  mov     word ptr [rsp+1E0h+var_180+8], r15w
0x18001bc0a  xor     edx, edx; Val
0x18001bc0c  mov     r8d, 100h; Size
0x18001bc12  lea     rcx, [rbp+0E0h+var_150]; void *
0x18001bc16  call    memset
0x18001bc1b  mov     qword ptr [rsp+1E0h+var_180], r15
0x18001bc20  lea     rax, [rsp+1E0h+var_180]
0x18001bc25  mov     [rsp+1E0h+var_190], rax
0x18001bc2a  mov     [rbp+0E0h+var_158], 80h
0x18001bc32  lea     rax, [rbp+0E0h+var_150]
0x18001bc36  mov     [rsp+1E0h+var_188], rax
0x18001bc3b  mov     rcx, [rsi+70h]; this
0x18001bc3f  test    rcx, rcx
0x18001bc42  jz      loc_18001BF01
0x18001bc48  mov     rax, [rcx]
0x18001bc4b  lea     r9, [rsp+1E0h+var_190]
0x18001bc50  lea     r8, [rbp+0E0h+var_158]
0x18001bc54  lea     rdx, [rsp+1E0h+var_188]
0x18001bc59  mov     rax, [rax+20h]
0x18001bc5d  call    cs:__guard_dispatch_icall_fptr
0x18001bc63  mov     ebx, eax
0x18001bc65  test    eax, eax
0x18001bc67  jns     short loc_18001BC93
0x18001bc69  lfence
0x18001bc6c  lea     rcx, [rsp+1E0h+var_180+8]
0x18001bc71  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bc76  mov     rcx, [rsi+70h]
0x18001bc7a  test    rcx, rcx
0x18001bc7d  jz      short loc_18001BC8C
0x18001bc7f  mov     rdx, [rcx]
0x18001bc82  mov     rax, [rdx+18h]
0x18001bc86  call    cs:__guard_dispatch_icall_fptr
0x18001bc8c  mov     eax, ebx
0x18001bc8e  jmp     loc_18001BECB
0x18001bc93  mov     rax, qword ptr [rsp+1E0h+var_180]
0x18001bc98  cmp     rax, 80h
0x18001bc9e  ja      short loc_18001BD01
0x18001bca0  lea     r8, [rax-1]
0x18001bca4  lea     rdx, [rbp+0E0h+var_150]
0x18001bca8  lea     rcx, [rsp+1E0h+var_180+8]
0x18001bcad  call    ?make@?$string_maker@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<std::wstring>::make(wchar_t const *,unsigned __int64)
0x18001bcb2  mov     ebx, eax
0x18001bcb4  test    eax, eax
0x18001bcb6  jns     loc_18001BDB4
0x18001bcbc  lfence
0x18001bcbf  mov     rcx, [rbp+0E8h]; this
0x18001bcc6  mov     r9d, eax; char *
0x18001bcc9  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18001bcd0  mov     edx, 165h; void *
0x18001bcd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bcda  lea     rcx, [rsp+1E0h+var_180+8]
0x18001bcdf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bce4  mov     rcx, [rsi+70h]
0x18001bce8  test    rcx, rcx
0x18001bceb  jz      short loc_18001BC8C
0x18001bced  mov     rax, [rcx]
0x18001bcf0  mov     rax, [rax+18h]
0x18001bcf4  call    cs:__guard_dispatch_icall_fptr
0x18001bcfa  mov     eax, ebx
0x18001bcfc  jmp     loc_18001BECB
0x18001bd01  mov     rbx, rax
0x18001bd04  lea     r8, [rax-1]
0x18001bd08  xor     edx, edx
0x18001bd0a  lea     rcx, [rsp+1E0h+var_180+8]
0x18001bd0f  call    ?make@?$string_maker@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<std::wstring>::make(wchar_t const *,unsigned __int64)
0x18001bd14  mov     edi, eax
0x18001bd16  test    eax, eax
0x18001bd18  js      loc_18001BE8B
0x18001bd1e  lea     rax, [rsp+1E0h+var_180+8]
0x18001bd23  cmp     [rbp+0E0h+var_160], 7
0x18001bd28  cmova   rax, qword ptr [rsp+1E0h+var_180+8]
0x18001bd2e  mov     [rsp+1E0h+var_190], rax
0x18001bd33  lea     rax, [rsp+1E0h+var_180]
0x18001bd38  mov     [rsp+1E0h+var_188], rax
0x18001bd3d  mov     [rbp+0E0h+var_158], rbx
0x18001bd41  mov     rcx, [rsi+70h]; this
0x18001bd45  test    rcx, rcx
0x18001bd48  jz      loc_18001BEFB
0x18001bd4e  mov     rax, [rcx]
0x18001bd51  lea     r9, [rsp+1E0h+var_188]
0x18001bd56  lea     r8, [rbp+0E0h+var_158]
0x18001bd5a  lea     rdx, [rsp+1E0h+var_190]
0x18001bd5f  mov     rax, [rax+20h]
0x18001bd63  call    cs:__guard_dispatch_icall_fptr
0x18001bd69  mov     edi, eax
0x18001bd6b  test    eax, eax
0x18001bd6d  js      loc_18001BE86
0x18001bd73  mov     rax, qword ptr [rsp+1E0h+var_180]
0x18001bd78  cmp     rax, rbx
0x18001bd7b  jnb     short loc_18001BDAE
0x18001bd7d  lea     rcx, [rax-1]
0x18001bd81  cmp     qword ptr [rsp+1E0h+var_170+8], rcx
0x18001bd86  jb      loc_18001BF07
0x18001bd8c  mov     qword ptr [rsp+1E0h+var_170+8], rcx
0x18001bd91  lea     rax, [rsp+1E0h+var_180+8]
0x18001bd96  cmp     [rbp+0E0h+var_160], 7
0x18001bd9b  cmova   rax, qword ptr [rsp+1E0h+var_180+8]
0x18001bda1  mov     [rax+rcx*2], r15w
0x18001bda6  mov     rax, qword ptr [rsp+1E0h+var_180]
0x18001bdab  cmp     rax, rbx
0x18001bdae  ja      loc_18001BD01
0x18001bdb4  movups  xmm6, [rsp+1E0h+var_180+8]
0x18001bdb9  movups  [rsp+1E0h+var_1B8+8], xmm6
0x18001bdbe  movups  xmm7, [rsp+1E0h+var_170+8]
0x18001bdc3  movdqu  xmmword ptr [rsp+1E0h+var_1A8+8], xmm7
0x18001bdc9  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001bdd1  movdqu  [rsp+1E0h+var_170+8], xmm0
0x18001bdd7  mov     word ptr [rsp+1E0h+var_180+8], r15w
0x18001bddd  lea     rax, [rsp+1E0h+var_1B8+8]
0x18001bde2  cmp     r14, rax
0x18001bde5  jz      short loc_18001BE42
0x18001bde7  mov     rdx, [r14+18h]
0x18001bdeb  cmp     rdx, 7
0x18001bdef  jbe     short loc_18001BE2D
0x18001bdf1  lea     rdx, ds:2[rdx*2]
0x18001bdf9  mov     rcx, [r14]
0x18001bdfc  cmp     rdx, 1000h
0x18001be03  jb      short loc_18001BE1D
0x18001be05  add     rdx, 27h ; '''; unsigned __int64
0x18001be09  mov     rax, [rcx-8]
0x18001be0d  sub     rcx, rax
0x18001be10  sub     rcx, 8
0x18001be14  cmp     rcx, 1Fh
0x18001be18  ja      short loc_18001BE70
0x18001be1a  mov     rcx, rax; void *
0x18001be1d  lfence
0x18001be20  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001be25  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001be2d  movups  xmmword ptr [r14], xmm6
0x18001be31  movups  xmmword ptr [r14+10h], xmm7
0x18001be36  movdqu  xmmword ptr [rsp+1E0h+var_1A8+8], xmm0
0x18001be3c  mov     word ptr [rsp+1E0h+var_1B8+8], r15w
0x18001be42  lea     rcx, [rsp+1E0h+var_1B8+8]
0x18001be47  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001be4c  lea     rcx, [rsp+1E0h+var_180+8]
0x18001be51  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001be56  mov     rcx, [rsi+70h]
0x18001be5a  test    rcx, rcx
0x18001be5d  jz      short loc_18001BE6C
0x18001be5f  mov     rax, [rcx]
0x18001be62  mov     rax, [rax+18h]
0x18001be66  call    cs:__guard_dispatch_icall_fptr
0x18001be6c  xor     eax, eax
0x18001be6e  jmp     short loc_18001BECB
0x18001be70  mov     [rsp+1E0h+Reserved], r15; Reserved
0x18001be75  xor     r9d, r9d; LineNo
0x18001be78  xor     r8d, r8d; FileName
0x18001be7b  xor     edx, edx; FunctionName
0x18001be7d  xor     ecx, ecx; Expression
0x18001be7f  call    cs:__imp__invoke_watson
0x18001be86  lfence
0x18001be89  jmp     short loc_18001BEA9
0x18001be8b  lfence
0x18001be8e  mov     rcx, [rbp+0E8h]; this
0x18001be95  mov     r9d, edi; char *
0x18001be98  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18001be9f  mov     edx, 170h; void *
0x18001bea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bea9  lea     rcx, [rsp+1E0h+var_180+8]
0x18001beae  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001beb3  mov     rcx, [rsi+70h]
0x18001beb7  test    rcx, rcx
0x18001beba  jz      short loc_18001BEC9
0x18001bebc  mov     rax, [rcx]
0x18001bebf  mov     rax, [rax+18h]
0x18001bec3  call    cs:__guard_dispatch_icall_fptr
0x18001bec9  mov     eax, edi
0x18001becb  mov     rcx, [rbp+0E0h+var_50]
0x18001bed2  xor     rcx, rsp; StackCookie
0x18001bed5  call    __security_check_cookie
0x18001beda  lea     r11, [rsp+1E0h+var_20]
0x18001bee2  mov     rbx, [r11+40h]
0x18001bee6  movaps  xmm6, xmmword ptr [r11-10h]
0x18001beeb  movaps  xmm7, xmmword ptr [r11-20h]
0x18001bef0  mov     rsp, r11
0x18001bef3  pop     r15
0x18001bef5  pop     r14
0x18001bef7  pop     rdi
0x18001bef8  pop     rsi
0x18001bef9  pop     rbp
0x18001befa  retn
0x18001befb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001bf01  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001bf07  call    ?_Xran@?$_String_val@U?$_Simple_types@D@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<char>>::_Xran(void)
```
