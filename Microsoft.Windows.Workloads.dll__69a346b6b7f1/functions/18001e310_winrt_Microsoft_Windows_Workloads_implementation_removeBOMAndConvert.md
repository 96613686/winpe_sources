# winrt::Microsoft::Windows::Workloads::implementation::removeBOMAndConvert

- ea: `0x18001e310`
- end: `0x18001e7cc`
- name: `winrt::Microsoft::Windows::Workloads::implementation::removeBOMAndConvert`
- size: `1212`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x180002860`
- `0x180002880`
- `0x1800029d0`
- `0x1800127c0`
- `0x180012c50`
- `0x1800154d0`
- `0x1800155c0`
- `0x18001e310`
- `0x18002b2e0`
- `0x18002c090`
- `0x180034ef0`
- `0x18003509c`
- `0x180036f4c`
- `0x18003bf20`
- `0x18003c020`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18001e627`
- `KERNEL32!WideCharToMultiByte` at `0x18001e679`
- `KERNEL32!WideCharToMultiByte` at `0x18001e627`
- `KERNEL32!WideCharToMultiByte` at `0x18001e679`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001e6fb`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001e6fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall winrt::Microsoft::Windows::Workloads::implementation::removeBOMAndConvert(__int64 a1, size_t *a2)
{
  size_t v4; // r15
  void **v5; // rdx
  size_t v6; // rdi
  size_t v7; // r14
  const void *v8; // rcx
  size_t v9; // r8
  size_t v10; // rax
  __int64 v11; // rax
  __int64 v12; // r8
  void **v13; // rdx
  size_t v14; // rdi
  size_t v15; // r14
  const void *v16; // rcx
  size_t v17; // r8
  unsigned __int64 v18; // r14
  const void *v19; // r15
  __int64 v20; // rbx
  __int64 v21; // rcx
  WCHAR *v22; // rcx
  const WCHAR *v23; // r8
  int cbMultiByte; // ebx
  CHAR *lpMultiByteStr; // rdx
  const WCHAR *v26; // r8
  void **v27; // rdx
  size_t v28; // rdi
  size_t v29; // r14
  const void *v30; // rcx
  size_t v31; // r8
  LPCWCH lpWideCharStr[2]; // [rsp+50h] [rbp-79h] BYREF
  int cchWideChar[2]; // [rsp+60h] [rbp-69h]
  unsigned __int64 v35; // [rsp+68h] [rbp-61h]
  void *v36[2]; // [rsp+70h] [rbp-59h] BYREF
  size_t v37; // [rsp+80h] [rbp-49h]
  unsigned __int64 v38; // [rsp+88h] [rbp-41h]
  void *v39[2]; // [rsp+90h] [rbp-39h] BYREF
  size_t v40; // [rsp+A0h] [rbp-29h]
  unsigned __int64 v41; // [rsp+A8h] [rbp-21h]
  void *Buf2[2]; // [rsp+B0h] [rbp-19h] BYREF
  size_t Size; // [rsp+C0h] [rbp-9h]
  unsigned __int64 v44; // [rsp+C8h] [rbp-1h]
  LPSTR v45[2]; // [rsp+D0h] [rbp+7h] BYREF
  __m128i si128; // [rsp+E0h] [rbp+17h]

  *(_OWORD *)Buf2 = 0;
  Size = 0;
  v44 = 0;
  std::string::_Construct<1,char const *>(Buf2, byte_180049B30, 3);
  *(_OWORD *)v39 = 0;
  v40 = 0;
  v41 = 0;
  std::string::_Construct<1,char const *>(v39, &dword_180049B34, 2);
  *(_OWORD *)v36 = 0;
  v37 = 0;
  v38 = 0;
  std::string::_Construct<1,char const *>(v36, &qword_180049B38, 2);
  v4 = a2[2];
  v5 = Buf2;
  if ( v44 > 0xF )
    v5 = (void **)Buf2[0];
  v6 = Size;
  v7 = Size;
  if ( v4 < Size )
    v7 = a2[2];
  v8 = a2;
  if ( a2[3] > 0xF )
    v8 = (const void *)*a2;
  v9 = v7;
  if ( Size < v7 )
    v9 = Size;
  if ( !memcmp(v8, v5, v9) && v7 >= v6 && v7 <= v6 )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v10 = a2[2];
    if ( v10 < v6 )
      std::_String_val<std::_Simple_types<char>>::_Xran();
    _mm_lfence();
    v11 = v10 - v6;
    v12 = -1;
    if ( v11 != -1 )
      v12 = v11;
    if ( a2[3] > 0xF )
      a2 = (size_t *)*a2;
    std::string::_Construct<1,char const *>(a1, (char *)a2 + v6, v12);
    goto LABEL_69;
  }
  v13 = v39;
  if ( v41 > 0xF )
    v13 = (void **)v39[0];
  v14 = v40;
  v15 = v40;
  if ( v4 < v40 )
    v15 = v4;
  v16 = a2;
  if ( a2[3] > 0xF )
    v16 = (const void *)*a2;
  v17 = v15;
  if ( v40 < v15 )
    v17 = v40;
  if ( !memcmp(v16, v13, v17) && v15 >= v14 && v15 <= v14 )
  {
    v18 = (v4 - 2) >> 1;
    if ( a2[3] > 0xF )
      a2 = (size_t *)*a2;
    v19 = (char *)a2 + 2;
    *(_OWORD *)lpWideCharStr = 0;
    *(_QWORD *)cchWideChar = 0;
    v35 = 0;
    v20 = 0x7FFFFFFFFFFFFFFELL;
    if ( v18 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v18 > 7 )
    {
      if ( (v18 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        v20 = v18 | 7;
        if ( (v18 | 7) < 0xA )
          v20 = 10;
        v21 = v20 + 1;
        if ( (unsigned __int64)(v20 + 1) > 0x7FFFFFFFFFFFFFFFLL )
          __scrt_throw_std_bad_array_new_length();
      }
      else
      {
        v21 = 0x7FFFFFFFFFFFFFFFLL;
      }
      _mm_lfence();
      lpWideCharStr[0] = (LPCWCH)std::_Allocate<16,std::_Default_allocate_traits>(2 * v21);
      *(_QWORD *)cchWideChar = v18;
      v35 = v20;
      memmove((void *)lpWideCharStr[0], v19, 2 * v18);
      lpWideCharStr[0][v18] = 0;
    }
    else
    {
      *(_QWORD *)cchWideChar = v18;
      v35 = 7;
      memmove(lpWideCharStr, v19, 2 * v18);
      *((_WORD *)lpWideCharStr + v18) = 0;
    }
    if ( *(_QWORD *)cchWideChar )
    {
      v23 = (const WCHAR *)lpWideCharStr;
      if ( v35 > 7 )
        v23 = lpWideCharStr[0];
      cbMultiByte = WideCharToMultiByte(0xFDE9u, 0, v23, cchWideChar[0], 0, 0, 0, 0);
      std::string::string(v45, cbMultiByte, 0);
      lpMultiByteStr = (CHAR *)v45;
      if ( si128.m128i_i64[1] > 0xFuLL )
        lpMultiByteStr = v45[0];
      v26 = (const WCHAR *)lpWideCharStr;
      if ( v35 > 7 )
        v26 = lpWideCharStr[0];
      WideCharToMultiByte(0xFDE9u, 0, v26, cchWideChar[0], lpMultiByteStr, cbMultiByte, 0, 0);
      *(_OWORD *)a1 = *(_OWORD *)v45;
      *(__m128i *)(a1 + 16) = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v45[0]) = 0;
      std::string::_Tidy_deallocate((__int64)v45);
      if ( v35 <= 7 )
        goto LABEL_42;
      v22 = (WCHAR *)lpWideCharStr[0];
      if ( 2 * v35 + 2 < 0x1000 )
        goto LABEL_41;
      v22 = (WCHAR *)*((_QWORD *)lpWideCharStr[0] - 1);
      if ( (unsigned __int64)((char *)lpWideCharStr[0] - (char *)v22 - 8) <= 0x1F )
        goto LABEL_41;
    }
    else
    {
      *(_OWORD *)a1 = 0;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 15;
      *(_BYTE *)a1 = 0;
      if ( v35 <= 7 )
      {
LABEL_42:
        *(_QWORD *)cchWideChar = 0;
        v35 = 7;
        LOWORD(lpWideCharStr[0]) = 0;
        goto LABEL_69;
      }
      v22 = (WCHAR *)lpWideCharStr[0];
      if ( 2 * v35 + 2 < 0x1000
        || (v22 = (WCHAR *)*((_QWORD *)lpWideCharStr[0] - 1),
            (unsigned __int64)((char *)lpWideCharStr[0] - (char *)v22 - 8) <= 0x1F) )
      {
LABEL_41:
        _mm_lfence();
        operator delete(v22);
        goto LABEL_42;
      }
    }
    _invoke_watson(0, 0, 0, 0, 0);
  }
  v27 = v36;
  if ( v38 > 0xF )
    v27 = (void **)v36[0];
  v28 = v37;
  v29 = v37;
  if ( v4 < v37 )
    v29 = v4;
  v30 = a2;
  if ( a2[3] > 0xF )
    v30 = (const void *)*a2;
  v31 = v29;
  if ( v37 < v29 )
    v31 = v37;
  if ( !memcmp(v30, v27, v31) && v29 >= v28 && v29 <= v28 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)lpWideCharStr, "BOM not supported");
    throw (std::runtime_error *)lpWideCharStr;
  }
  std::string::string(a1, a2);
LABEL_69:
  std::string::_Tidy_deallocate((__int64)v36);
  std::string::_Tidy_deallocate((__int64)v39);
  std::string::_Tidy_deallocate((__int64)Buf2);
  return a1;
}

```

## disassembly

```asm
0x18001e310  mov     [rsp-8+arg_10], rbx
0x18001e315  mov     [rsp-8+arg_18], rsi
0x18001e31a  push    rbp
0x18001e31b  push    rdi
0x18001e31c  push    r13
0x18001e31e  push    r14
0x18001e320  push    r15
0x18001e322  lea     rbp, [rsp-37h]
0x18001e327  sub     rsp, 100h
0x18001e32e  mov     rax, cs:__security_cookie
0x18001e335  xor     rax, rsp
0x18001e338  mov     [rbp+57h+var_30], rax
0x18001e33c  mov     rbx, rdx
0x18001e33f  mov     rsi, rcx
0x18001e342  mov     [rsp+120h+var_D8], rcx
0x18001e347  xor     r13d, r13d
0x18001e34a  xorps   xmm0, xmm0
0x18001e34d  movups  xmmword ptr [rbp+57h+Buf2], xmm0
0x18001e351  mov     [rbp+57h+Size], r13
0x18001e355  mov     [rbp+57h+var_58], r13
0x18001e359  mov     r8d, 3
0x18001e35f  lea     rdx, byte_180049B30
0x18001e366  lea     rcx, [rbp+57h+Buf2]
0x18001e36a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18001e36f  nop
0x18001e370  xorps   xmm0, xmm0
0x18001e373  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18001e377  mov     [rbp+57h+var_80], r13
0x18001e37b  mov     [rbp+57h+var_78], r13
0x18001e37f  mov     r8d, 2
0x18001e385  lea     rdx, dword_180049B34
0x18001e38c  lea     rcx, [rbp+57h+var_90]
0x18001e390  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18001e395  nop
0x18001e396  xorps   xmm0, xmm0
0x18001e399  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x18001e39d  mov     [rbp+57h+var_A0], r13
0x18001e3a1  mov     [rbp+57h+var_98], r13
0x18001e3a5  mov     r8d, 2
0x18001e3ab  lea     rdx, qword_180049B38
0x18001e3b2  lea     rcx, [rbp+57h+var_B0]
0x18001e3b6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18001e3bb  nop
0x18001e3bc  mov     r15, [rbx+10h]
0x18001e3c0  lea     rdx, [rbp+57h+Buf2]
0x18001e3c4  cmp     [rbp+57h+var_58], 0Fh
0x18001e3c9  cmova   rdx, [rbp+57h+Buf2]; Buf2
0x18001e3ce  mov     rdi, [rbp+57h+Size]
0x18001e3d2  mov     r14, rdi
0x18001e3d5  cmp     r15, rdi
0x18001e3d8  cmovb   r14, r15
0x18001e3dc  mov     rcx, rbx
0x18001e3df  cmp     qword ptr [rbx+18h], 0Fh
0x18001e3e4  jbe     short loc_18001E3E9
0x18001e3e6  mov     rcx, [rbx]; Buf1
0x18001e3e9  mov     r8, r14
0x18001e3ec  cmp     rdi, r14
0x18001e3ef  cmovb   r8, rdi; Size
0x18001e3f3  call    memcmp
0x18001e3f8  test    eax, eax
0x18001e3fa  jnz     short loc_18001E44D
0x18001e3fc  cmp     r14, rdi
0x18001e3ff  jb      short loc_18001E44D
0x18001e401  ja      short loc_18001E44D
0x18001e403  xorps   xmm0, xmm0
0x18001e406  movups  xmmword ptr [rsi], xmm0
0x18001e409  mov     [rsi+10h], r13
0x18001e40d  mov     [rsi+18h], r13
0x18001e411  mov     rax, [rbx+10h]
0x18001e415  cmp     rax, rdi
0x18001e418  jb      loc_18001E7C0
0x18001e41e  lfence
0x18001e421  sub     rax, rdi
0x18001e424  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001e42b  cmp     rax, r8
0x18001e42e  cmovb   r8, rax
0x18001e432  cmp     qword ptr [rbx+18h], 0Fh
0x18001e437  jbe     short loc_18001E43C
0x18001e439  mov     rbx, [rbx]
0x18001e43c  lea     rdx, [rdi+rbx]
0x18001e440  mov     rcx, rsi
0x18001e443  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18001e448  jmp     loc_18001E751
0x18001e44d  lea     rdx, [rbp+57h+var_90]
0x18001e451  cmp     [rbp+57h+var_78], 0Fh
0x18001e456  cmova   rdx, [rbp+57h+var_90]; Buf2
0x18001e45b  mov     rdi, [rbp+57h+var_80]
0x18001e45f  mov     r14, rdi
0x18001e462  cmp     r15, rdi
0x18001e465  cmovb   r14, r15
0x18001e469  mov     rcx, rbx
0x18001e46c  cmp     qword ptr [rbx+18h], 0Fh
0x18001e471  jbe     short loc_18001E476
0x18001e473  mov     rcx, [rbx]; Buf1
0x18001e476  mov     r8, r14
0x18001e479  cmp     rdi, r14
0x18001e47c  cmovb   r8, rdi; Size
0x18001e480  call    memcmp
0x18001e485  test    eax, eax
0x18001e487  jnz     loc_18001E702
0x18001e48d  cmp     r14, rdi
0x18001e490  jb      loc_18001E702
0x18001e496  ja      loc_18001E702
0x18001e49c  mov     eax, r13d
0x18001e49f  test    eax, eax
0x18001e4a1  jnz     loc_18001E702
0x18001e4a7  lea     r14, [r15-2]
0x18001e4ab  shr     r14, 1
0x18001e4ae  cmp     qword ptr [rbx+18h], 0Fh
0x18001e4b3  jbe     short loc_18001E4B8
0x18001e4b5  mov     rbx, [rbx]
0x18001e4b8  lea     r15, [rbx+2]
0x18001e4bc  xorps   xmm0, xmm0
0x18001e4bf  movups  xmmword ptr [rbp+57h+lpWideCharStr], xmm0
0x18001e4c3  mov     qword ptr [rbp+57h+cchWideChar], r13
0x18001e4c7  mov     [rbp+57h+var_B8], r13
0x18001e4cb  mov     rbx, 7FFFFFFFFFFFFFFEh
0x18001e4d5  cmp     r14, rbx
0x18001e4d8  ja      loc_18001E7C6
0x18001e4de  cmp     r14, 7
0x18001e4e2  ja      short loc_18001E50B
0x18001e4e4  mov     qword ptr [rbp+57h+cchWideChar], r14
0x18001e4e8  mov     [rbp+57h+var_B8], 7
0x18001e4f0  lea     rbx, [r14+r14]
0x18001e4f4  mov     r8, rbx; Size
0x18001e4f7  mov     rdx, r15; Src
0x18001e4fa  lea     rcx, [rbp+57h+lpWideCharStr]; void *
0x18001e4fe  call    memmove
0x18001e503  mov     word ptr [rbp+rbx+57h+lpWideCharStr], r13w
0x18001e509  jmp     short loc_18001E556
0x18001e50b  mov     rax, r14
0x18001e50e  or      rax, 7
0x18001e512  cmp     rax, rbx
0x18001e515  jbe     loc_18001E5CF
0x18001e51b  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18001e525  lfence
0x18001e528  add     rcx, rcx
0x18001e52b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001e530  mov     rdi, rax
0x18001e533  mov     [rbp+57h+lpWideCharStr], rax
0x18001e537  mov     qword ptr [rbp+57h+cchWideChar], r14
0x18001e53b  mov     [rbp+57h+var_B8], rbx
0x18001e53f  lea     rbx, [r14+r14]
0x18001e543  mov     r8, rbx; Size
0x18001e546  mov     rdx, r15; Src
0x18001e549  mov     rcx, rax; void *
0x18001e54c  call    memmove
0x18001e551  mov     [rbx+rdi], r13w
0x18001e556  cmp     qword ptr [rbp+57h+cchWideChar], 0
0x18001e55b  jnz     loc_18001E5FA
0x18001e561  xorps   xmm0, xmm0
0x18001e564  movups  xmmword ptr [rsi], xmm0
0x18001e567  mov     [rsi+10h], r13
0x18001e56b  mov     qword ptr [rsi+18h], 0Fh
0x18001e573  mov     byte ptr [rsi], 0
0x18001e576  mov     rdx, [rbp+57h+var_B8]
0x18001e57a  cmp     rdx, 7
0x18001e57e  jbe     short loc_18001E5B9
0x18001e580  lea     rdx, ds:2[rdx*2]
0x18001e588  mov     rcx, [rbp+57h+lpWideCharStr]
0x18001e58c  mov     rax, rcx
0x18001e58f  cmp     rdx, 1000h
0x18001e596  jb      short loc_18001E5B1
0x18001e598  add     rdx, 27h ; '''; unsigned __int64
0x18001e59c  mov     rcx, [rcx-8]; void *
0x18001e5a0  sub     rax, rcx
0x18001e5a3  sub     rax, 8
0x18001e5a7  cmp     rax, 1Fh
0x18001e5ab  ja      loc_18001E6EC
0x18001e5b1  lfence
0x18001e5b4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e5b9  mov     qword ptr [rbp+57h+cchWideChar], r13
0x18001e5bd  mov     [rbp+57h+var_B8], 7
0x18001e5c5  mov     word ptr [rbp+57h+lpWideCharStr], r13w
0x18001e5ca  jmp     loc_18001E751
0x18001e5cf  mov     rbx, rax
0x18001e5d2  mov     ecx, 0Ah
0x18001e5d7  cmp     rax, rcx
0x18001e5da  cmovb   rbx, rcx
0x18001e5de  lea     rcx, [rbx+1]
0x18001e5e2  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001e5ec  cmp     rcx, rax
0x18001e5ef  ja      loc_18001E7BA
0x18001e5f5  jmp     loc_18001E525
0x18001e5fa  lea     r8, [rbp+57h+lpWideCharStr]
0x18001e5fe  cmp     [rbp+57h+var_B8], 7
0x18001e603  cmova   r8, [rbp+57h+lpWideCharStr]; lpWideCharStr
0x18001e608  mov     [rsp+120h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18001e60d  mov     [rsp+120h+lpDefaultChar], r13; lpDefaultChar
0x18001e612  mov     [rsp+120h+cbMultiByte], r13d; cbMultiByte
0x18001e617  mov     [rsp+120h+lpMultiByteStr], r13; lpMultiByteStr
0x18001e61c  mov     r9d, [rbp+57h+cchWideChar]; cchWideChar
0x18001e620  xor     edx, edx; dwFlags
0x18001e622  mov     ecx, 0FDE9h; CodePage
0x18001e627  call    cs:__imp_WideCharToMultiByte
0x18001e62d  movsxd  rbx, eax
0x18001e630  mov     rdx, rbx
0x18001e633  xor     r8d, r8d
0x18001e636  lea     rcx, [rbp+57h+var_50]
0x18001e63a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x18001e63f  lea     rdx, [rbp+57h+var_50]
0x18001e643  cmp     [rbp+57h+var_38], 0Fh
0x18001e648  cmova   rdx, [rbp+57h+var_50]
0x18001e64d  lea     r8, [rbp+57h+lpWideCharStr]
0x18001e651  cmp     [rbp+57h+var_B8], 7
0x18001e656  cmova   r8, [rbp+57h+lpWideCharStr]; lpWideCharStr
0x18001e65b  mov     [rsp+120h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18001e660  mov     [rsp+120h+lpDefaultChar], r13; lpDefaultChar
0x18001e665  mov     [rsp+120h+cbMultiByte], ebx; cbMultiByte
0x18001e669  mov     [rsp+120h+lpMultiByteStr], rdx; lpMultiByteStr
0x18001e66e  mov     r9d, [rbp+57h+cchWideChar]; cchWideChar
0x18001e672  xor     edx, edx; dwFlags
0x18001e674  mov     ecx, 0FDE9h; CodePage
0x18001e679  call    cs:__imp_WideCharToMultiByte
0x18001e67f  movups  xmm0, xmmword ptr [rbp+57h+var_50]
0x18001e683  movups  xmmword ptr [rsi], xmm0
0x18001e686  movups  xmm1, xmmword ptr [rbp+17h]
0x18001e68a  movups  xmmword ptr [rsi+10h], xmm1
0x18001e68e  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18001e696  movdqu  xmmword ptr [rbp+17h], xmm0
0x18001e69b  mov     byte ptr [rbp+57h+var_50], 0
0x18001e69f  lea     rcx, [rbp+57h+var_50]
0x18001e6a3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001e6a8  nop
0x18001e6a9  mov     rdx, [rbp+57h+var_B8]
0x18001e6ad  cmp     rdx, 7
0x18001e6b1  jbe     loc_18001E5B9
0x18001e6b7  lea     rdx, ds:2[rdx*2]
0x18001e6bf  mov     rcx, [rbp+57h+lpWideCharStr]
0x18001e6c3  mov     rax, rcx
0x18001e6c6  cmp     rdx, 1000h
0x18001e6cd  jb      loc_18001E5B1
0x18001e6d3  add     rdx, 27h ; '''
0x18001e6d7  mov     rcx, [rcx-8]
0x18001e6db  sub     rax, rcx
0x18001e6de  sub     rax, 8
0x18001e6e2  cmp     rax, 1Fh
0x18001e6e6  jbe     loc_18001E5B1
0x18001e6ec  mov     [rsp+120h+lpMultiByteStr], r13; Reserved
0x18001e6f1  xor     r9d, r9d; LineNo
0x18001e6f4  xor     r8d, r8d; FileName
0x18001e6f7  xor     edx, edx; FunctionName
0x18001e6f9  xor     ecx, ecx; Expression
0x18001e6fb  call    cs:__imp__invoke_watson
0x18001e702  lea     rdx, [rbp+57h+var_B0]
0x18001e706  cmp     [rbp+57h+var_98], 0Fh
0x18001e70b  cmova   rdx, [rbp+57h+var_B0]; Buf2
0x18001e710  mov     rdi, [rbp+57h+var_A0]
0x18001e714  mov     r14, rdi
0x18001e717  cmp     r15, rdi
0x18001e71a  cmovb   r14, r15
0x18001e71e  mov     rcx, rbx
0x18001e721  cmp     qword ptr [rbx+18h], 0Fh
0x18001e726  jbe     short loc_18001E72B
0x18001e728  mov     rcx, [rbx]; Buf1
0x18001e72b  mov     r8, r14
0x18001e72e  cmp     rdi, r14
0x18001e731  cmovb   r8, rdi; Size
0x18001e735  call    memcmp
0x18001e73a  test    eax, eax
0x18001e73c  jnz     short loc_18001E745
0x18001e73e  cmp     r14, rdi
0x18001e741  jb      short loc_18001E745
0x18001e743  jbe     short loc_18001E799
0x18001e745  mov     rdx, rbx
0x18001e748  mov     rcx, rsi
0x18001e74b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18001e750  nop
0x18001e751  lea     rcx, [rbp+57h+var_B0]
0x18001e755  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001e75a  nop
0x18001e75b  lea     rcx, [rbp+57h+var_90]
0x18001e75f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001e764  nop
0x18001e765  lea     rcx, [rbp+57h+Buf2]
0x18001e769  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001e76e  mov     rax, rsi
0x18001e771  mov     rcx, [rbp+57h+var_30]
0x18001e775  xor     rcx, rsp; StackCookie
0x18001e778  call    __security_check_cookie
0x18001e77d  lea     r11, [rsp+120h+var_20]
0x18001e785  mov     rbx, [r11+40h]
0x18001e789  mov     rsi, [r11+48h]
0x18001e78d  mov     rsp, r11
0x18001e790  pop     r15
0x18001e792  pop     r14
0x18001e794  pop     r13
0x18001e796  pop     rdi
0x18001e797  pop     rbp
0x18001e798  retn
0x18001e799  lea     rdx, aBomNotSupporte; "BOM not supported"
0x18001e7a0  lea     rcx, [rbp+57h+lpWideCharStr]; this
0x18001e7a4  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001e7a9  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001e7b0  lea     rcx, [rbp+57h+lpWideCharStr]; pExceptionObject
0x18001e7b4  call    _CxxThrowException
0x18001e7ba  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18001e7c0  call    ?_Xran@?$_String_val@U?$_Simple_types@D@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<char>>::_Xran(void)
0x18001e7c6  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
