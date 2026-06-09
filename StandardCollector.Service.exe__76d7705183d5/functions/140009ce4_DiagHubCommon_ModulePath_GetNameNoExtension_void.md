# DiagHubCommon::ModulePath::GetNameNoExtension(void)

- ea: `0x140009ce4`
- end: `0x140009ed2`
- name: `?GetNameNoExtension@ModulePath@DiagHubCommon@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14000a42c`

## callees

- `0x140003010`
- `0x140003088`
- `0x140009ce4`
- `0x1400137e0`
- `0x14001382c`
- `0x140014950`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140009e48`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140009e48`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiagHubCommon::ModulePath::GetNameNoExtension(__int64 a1, __int64 a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  void **v5; // rsi
  char *v6; // rbx
  __int64 last_trivial_2; // rax
  unsigned __int64 v8; // rax
  void **v9; // rdx
  void *v10; // rcx
  __int128 v12; // [rsp+38h] [rbp-11h] BYREF
  __m128i si128; // [rsp+48h] [rbp-1h]
  __int64 v14; // [rsp+58h] [rbp+Fh]
  void *Block[2]; // [rsp+60h] [rbp+17h] BYREF
  __m128i v16; // [rsp+70h] [rbp+27h]

  v14 = a2;
  v3 = *(_QWORD *)(a1 + 32);
  if ( v3 )
  {
    *(_OWORD *)Block = 0;
    v16 = 0u;
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(v3 + 2 * v4) );
    std::wstring::_Construct<1,unsigned short const *>(Block, v3, v4);
    v5 = Block;
    if ( v16.m128i_i64[1] > 7uLL )
      v5 = (void **)Block[0];
    if ( v16.m128i_i64[0] )
    {
      v6 = (char *)v5 + 2 * v16.m128i_i64[0];
      last_trivial_2 = _std_find_last_trivial_2(v5, v6, 46);
      if ( (char *)last_trivial_2 != v6 )
      {
        v8 = (last_trivial_2 - (__int64)v5) >> 1;
        if ( v8 != -1 && v16.m128i_i64[0] > 1uLL )
        {
          _mm_lfence();
          v12 = 0;
          si128 = 0;
          if ( v16.m128i_i64[0] < v8 )
            v8 = v16.m128i_i64[0];
          v9 = Block;
          if ( v16.m128i_i64[1] > 7uLL )
            v9 = (void **)Block[0];
          std::wstring::_Construct<1,unsigned short const *>(&v12, v9, v8);
          if ( v16.m128i_i64[1] > 7uLL )
          {
            v10 = Block[0];
            if ( (unsigned __int64)(2 * v16.m128i_i64[1] + 2) >= 0x1000 )
            {
              v10 = (void *)*((_QWORD *)Block[0] - 1);
              if ( (unsigned __int64)((char *)Block[0] - (char *)v10 - 8) > 0x1F )
                _invoke_watson(0, 0, 0, 0, 0);
            }
            _mm_lfence();
            operator delete(v10);
          }
          *(_OWORD *)Block = v12;
          v16 = si128;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v12) = 0;
          std::wstring::~wstring(&v12);
        }
      }
    }
    *(_OWORD *)a2 = *(_OWORD *)Block;
    *(__m128i *)(a2 + 16) = v16;
    v16.m128i_i64[0] = 0;
    v16.m128i_i64[1] = 7;
    LOWORD(Block[0]) = 0;
    std::wstring::~wstring(Block);
  }
  else
  {
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    std::wstring::_Construct<1,unsigned short const *>(a2, &word_140019B74, 0);
  }
  return a2;
}

```

## disassembly

```asm
0x140009ce4  mov     [rsp-8+arg_10], rbx
0x140009ce9  mov     [rsp-8+arg_18], rsi
0x140009cee  push    rbp
0x140009cef  push    rdi
0x140009cf0  push    r14
0x140009cf2  lea     rbp, [rsp-47h]
0x140009cf7  sub     rsp, 90h
0x140009cfe  mov     rax, cs:__security_cookie
0x140009d05  xor     rax, rsp
0x140009d08  mov     [rbp+57h+var_20], rax
0x140009d0c  mov     rdi, rdx
0x140009d0f  mov     [rbp+57h+var_48], rdx
0x140009d13  xor     r14d, r14d
0x140009d16  mov     rdx, [rcx+20h]
0x140009d1a  xorps   xmm0, xmm0
0x140009d1d  test    rdx, rdx
0x140009d20  jnz     short loc_140009D44
0x140009d22  movups  xmmword ptr [rdi], xmm0
0x140009d25  mov     [rdi+10h], r14
0x140009d29  mov     [rdi+18h], r14
0x140009d2d  xor     r8d, r8d
0x140009d30  lea     rdx, word_140019B74
0x140009d37  mov     rcx, rdi
0x140009d3a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140009d3f  jmp     loc_140009EAB
0x140009d44  movups  xmmword ptr [rbp+57h+Block], xmm0
0x140009d48  mov     qword ptr [rbp+57h+var_30], r14
0x140009d4c  mov     qword ptr [rbp+57h+var_30+8], r14
0x140009d50  or      r8, 0FFFFFFFFFFFFFFFFh
0x140009d54  inc     r8
0x140009d57  cmp     [rdx+r8*2], r14w
0x140009d5c  jnz     short loc_140009D54
0x140009d5e  lea     rcx, [rbp+57h+Block]
0x140009d62  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140009d67  nop
0x140009d68  lea     rsi, [rbp+57h+Block]
0x140009d6c  cmp     qword ptr [rbp+57h+var_30+8], 7
0x140009d71  cmova   rsi, [rbp+57h+Block]
0x140009d76  mov     rcx, qword ptr [rbp+57h+var_30]
0x140009d7a  test    rcx, rcx
0x140009d7d  jz      loc_140009E82
0x140009d83  dec     rcx
0x140009d86  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009d8a  cmp     rcx, rax
0x140009d8d  cmovb   rax, rcx
0x140009d91  inc     rax
0x140009d94  lea     rbx, [rsi+rax*2]
0x140009d98  mov     r8d, 2Eh ; '.'
0x140009d9e  mov     rdx, rbx
0x140009da1  mov     rcx, rsi
0x140009da4  call    __std_find_last_trivial_2
0x140009da9  cmp     rax, rbx
0x140009dac  jz      loc_140009E82
0x140009db2  sub     rax, rsi
0x140009db5  sar     rax, 1
0x140009db8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140009dbc  jz      loc_140009E82
0x140009dc2  cmp     qword ptr [rbp+57h+var_30], 1
0x140009dc7  jbe     loc_140009E82
0x140009dcd  lfence
0x140009dd0  xorps   xmm0, xmm0
0x140009dd3  movups  [rbp+57h+var_68], xmm0
0x140009dd7  xorps   xmm1, xmm1
0x140009dda  movdqu  [rbp+57h+var_58], xmm1
0x140009ddf  cmp     qword ptr [rbp+57h+var_30], rax
0x140009de3  cmovb   rax, qword ptr [rbp+57h+var_30]
0x140009de8  lea     rdx, [rbp+57h+Block]
0x140009dec  cmp     qword ptr [rbp+57h+var_30+8], 7
0x140009df1  cmova   rdx, [rbp+57h+Block]
0x140009df6  mov     r8, rax
0x140009df9  lea     rcx, [rbp+57h+var_68]
0x140009dfd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140009e02  mov     rdx, qword ptr [rbp+57h+var_30+8]
0x140009e06  cmp     rdx, 7
0x140009e0a  jbe     short loc_140009E57
0x140009e0c  lea     rdx, ds:2[rdx*2]
0x140009e14  mov     rcx, [rbp+57h+Block]; Block
0x140009e18  mov     rax, rcx
0x140009e1b  cmp     rdx, 1000h
0x140009e22  jb      short loc_140009E4F
0x140009e24  add     rdx, 27h ; '''
0x140009e28  mov     rcx, [rcx-8]
0x140009e2c  sub     rax, rcx
0x140009e2f  sub     rax, 8
0x140009e33  cmp     rax, 1Fh
0x140009e37  jbe     short loc_140009E4F
0x140009e39  mov     [rsp+0A0h+Reserved], r14; Reserved
0x140009e3e  xor     r9d, r9d; LineNo
0x140009e41  xor     r8d, r8d; FileName
0x140009e44  xor     edx, edx; FunctionName
0x140009e46  xor     ecx, ecx; Expression
0x140009e48  call    cs:__imp__invoke_watson
0x140009e4f  lfence
0x140009e52  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009e57  movups  xmm0, [rbp+57h+var_68]
0x140009e5b  movups  xmmword ptr [rbp+57h+Block], xmm0
0x140009e5f  movups  xmm1, [rbp+57h+var_58]
0x140009e63  movups  [rbp+57h+var_30], xmm1
0x140009e67  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140009e6f  movdqu  [rbp+57h+var_58], xmm0
0x140009e74  mov     word ptr [rbp+57h+var_68], r14w
0x140009e79  lea     rcx, [rbp+57h+var_68]
0x140009e7d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009e82  movups  xmm0, xmmword ptr [rbp+57h+Block]
0x140009e86  movups  xmmword ptr [rdi], xmm0
0x140009e89  movups  xmm1, [rbp+57h+var_30]
0x140009e8d  movups  xmmword ptr [rdi+10h], xmm1
0x140009e91  mov     qword ptr [rbp+57h+var_30], r14
0x140009e95  mov     qword ptr [rbp+57h+var_30+8], 7
0x140009e9d  mov     word ptr [rbp+57h+Block], r14w
0x140009ea2  lea     rcx, [rbp+57h+Block]
0x140009ea6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009eab  mov     rax, rdi
0x140009eae  mov     rcx, [rbp+57h+var_20]
0x140009eb2  xor     rcx, rsp; StackCookie
0x140009eb5  call    __security_check_cookie
0x140009eba  lea     r11, [rsp+0A0h+var_10]
0x140009ec2  mov     rbx, [r11+30h]
0x140009ec6  mov     rsi, [r11+38h]
0x140009eca  mov     rsp, r11
0x140009ecd  pop     r14
0x140009ecf  pop     rdi
0x140009ed0  pop     rbp
0x140009ed1  retn
```
