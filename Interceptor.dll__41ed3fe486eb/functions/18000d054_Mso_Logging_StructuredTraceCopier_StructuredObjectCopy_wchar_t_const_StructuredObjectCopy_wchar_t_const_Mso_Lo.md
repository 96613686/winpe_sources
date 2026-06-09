# Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>::StructuredObjectCopy<wchar_t const *>(Mso::Logging::StructuredObject<wchar_t const *,1> const &)

- ea: `0x18000d054`
- end: `0x18000d241`
- name: `??0?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@QEAA@AEBU?$StructuredObject@PEB_W$00@23@@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ea6c`

## callees

- `0x18000410c`
- `0x18000d054`
- `0x1800266e0`
- `0x18002b3c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000d1c1`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000d1c1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000d174`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000d1c8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000d174`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000d1c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>::StructuredObjectCopy<wchar_t const *>(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rsi
  __int64 v8; // r8
  __int64 v9; // rdx
  void **v10; // rax
  char v11; // si
  void *v12; // rcx
  void *v13; // rcx
  __int16 v14; // cx
  _QWORD *v15; // rax
  __int128 v17; // [rsp+38h] [rbp-11h] BYREF
  __m128i si128; // [rsp+48h] [rbp-1h]
  __int64 v19; // [rsp+58h] [rbp+Fh]
  void *Block[2]; // [rsp+60h] [rbp+17h] BYREF
  __int128 v21; // [rsp+70h] [rbp+27h]

  v19 = a1;
  v4 = 0;
  *(_QWORD *)a1 = &Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>::`vftable';
  v5 = a1 + 8;
  v6 = a2[1];
  *(_OWORD *)v5 = 0;
  *(_QWORD *)(v5 + 16) = 0;
  *(_QWORD *)(v5 + 24) = 0;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(v6 + 2 * v8) );
  std::wstring::_Construct<1,wchar_t const *>(v5, v6, v8);
  v9 = a2[2];
  if ( v9 )
  {
    *(_OWORD *)Block = 0;
    v21 = 0;
    do
      ++v7;
    while ( *(_WORD *)(v9 + 2 * v7) );
    std::wstring::_Construct<1,wchar_t const *>(Block, v9, v7);
    v10 = Block;
    v11 = 1;
  }
  else
  {
    v17 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v17) = 0;
    v10 = (void **)&v17;
    v11 = 2;
  }
  *(_OWORD *)(a1 + 40) = *(_OWORD *)v10;
  *(_OWORD *)(a1 + 56) = *((_OWORD *)v10 + 1);
  *(_WORD *)v10 = 0;
  v10[2] = 0;
  v10[3] = (void *)7;
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    if ( si128.m128i_i64[1] > 7uLL )
    {
      v12 = (void *)v17;
      if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
      {
        v12 = *(void **)(v17 - 8);
        if ( (unsigned __int64)(v17 - (_QWORD)v12 - 8) > 0x1F )
LABEL_17:
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v12);
    }
  }
  if ( (v11 & 1) != 0 && *((_QWORD *)&v21 + 1) > 7u )
  {
    v13 = Block[0];
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v21 + 1) + 2) >= 0x1000 )
    {
      v13 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v13 - 8) > 0x1F )
        goto LABEL_17;
    }
    free(v13);
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD *))(*a2 + 24LL))(a2);
  if ( a2[2] )
  {
    v4 = (_QWORD *)(a1 + 40);
    if ( *(_QWORD *)(a1 + 64) > 7u )
      v4 = (_QWORD *)*v4;
  }
  v15 = (_QWORD *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 32) > 7u )
    v15 = (_QWORD *)*v15;
  *(_QWORD *)(a1 + 72) = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
  *(_QWORD *)(a1 + 80) = v15;
  *(_QWORD *)(a1 + 88) = v4;
  *(_WORD *)(a1 + 96) = v14;
  return a1;
}

```

## disassembly

```asm
0x18000d054  mov     [rsp-8+arg_10], rbx
0x18000d059  mov     [rsp-8+arg_18], rsi
0x18000d05e  push    rbp
0x18000d05f  push    rdi
0x18000d060  push    r14
0x18000d062  lea     rbp, [rsp-47h]
0x18000d067  sub     rsp, 90h
0x18000d06e  mov     rax, cs:__security_cookie
0x18000d075  xor     rax, rsp
0x18000d078  mov     [rbp+57h+var_20], rax
0x18000d07c  mov     r14, rdx
0x18000d07f  mov     rdi, rcx
0x18000d082  mov     [rbp+57h+var_48], rcx
0x18000d086  xor     ebx, ebx
0x18000d088  mov     dword ptr [rbp+57h+var_70], ebx
0x18000d08b  lea     rax, ??_7?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@6B@; const Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>::`vftable'
0x18000d092  mov     [rcx], rax
0x18000d095  add     rcx, 8
0x18000d099  mov     [rbp+57h+var_70], rcx
0x18000d09d  mov     rdx, [rdx+8]
0x18000d0a1  xorps   xmm0, xmm0
0x18000d0a4  movups  xmmword ptr [rcx], xmm0
0x18000d0a7  mov     [rcx+10h], rbx
0x18000d0ab  mov     [rcx+18h], rbx
0x18000d0af  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000d0b3  mov     r8, rsi
0x18000d0b6  inc     r8
0x18000d0b9  cmp     [rdx+r8*2], bx
0x18000d0be  jnz     short loc_18000D0B6
0x18000d0c0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000d0c5  mov     rdx, [r14+10h]
0x18000d0c9  xorps   xmm0, xmm0
0x18000d0cc  test    rdx, rdx
0x18000d0cf  jz      short loc_18000D0FD
0x18000d0d1  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18000d0d5  xorps   xmm1, xmm1
0x18000d0d8  movdqu  [rbp+57h+var_30], xmm1
0x18000d0dd  inc     rsi
0x18000d0e0  cmp     [rdx+rsi*2], bx
0x18000d0e4  jnz     short loc_18000D0DD
0x18000d0e6  mov     r8, rsi
0x18000d0e9  lea     rcx, [rbp+57h+Block]
0x18000d0ed  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000d0f2  lea     rax, [rbp+57h+Block]
0x18000d0f6  mov     esi, 1
0x18000d0fb  jmp     short loc_18000D11B
0x18000d0fd  movups  [rbp+57h+var_68], xmm0
0x18000d101  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000d109  movdqu  [rbp+57h+var_58], xmm1
0x18000d10e  mov     word ptr [rbp+57h+var_68], bx
0x18000d112  lea     rax, [rbp+57h+var_68]
0x18000d116  mov     esi, 2
0x18000d11b  movups  xmm0, xmmword ptr [rax]
0x18000d11e  movups  xmmword ptr [rdi+28h], xmm0
0x18000d122  movups  xmm1, xmmword ptr [rax+10h]
0x18000d126  movups  xmmword ptr [rdi+38h], xmm1
0x18000d12a  mov     [rax], bx
0x18000d12d  mov     [rax+10h], rbx
0x18000d131  mov     qword ptr [rax+18h], 7
0x18000d139  test    sil, 2
0x18000d13d  jz      short loc_18000D17A
0x18000d13f  and     esi, 0FFFFFFFDh
0x18000d142  mov     rax, qword ptr [rbp+57h+var_58+8]
0x18000d146  cmp     rax, 7
0x18000d14a  jbe     short loc_18000D17A
0x18000d14c  mov     rcx, qword ptr [rbp+57h+var_68]
0x18000d150  mov     rdx, rcx
0x18000d153  lea     rax, ds:2[rax*2]
0x18000d15b  cmp     rax, 1000h
0x18000d161  jb      short loc_18000D174
0x18000d163  mov     rcx, [rcx-8]; Block
0x18000d167  sub     rdx, rcx
0x18000d16a  lea     rax, [rdx-8]
0x18000d16e  cmp     rax, 1Fh
0x18000d172  ja      short loc_18000D1B2
0x18000d174  call    cs:__imp_free
0x18000d17a  test    sil, 1
0x18000d17e  jz      short loc_18000D1CE
0x18000d180  mov     rax, qword ptr [rbp+57h+var_30+8]
0x18000d184  cmp     rax, 7
0x18000d188  jbe     short loc_18000D1CE
0x18000d18a  mov     rcx, [rbp+57h+Block]; Block
0x18000d18e  mov     rdx, rcx
0x18000d191  lea     rax, ds:2[rax*2]
0x18000d199  cmp     rax, 1000h
0x18000d19f  jb      short loc_18000D1C8
0x18000d1a1  mov     rcx, [rcx-8]
0x18000d1a5  sub     rdx, rcx
0x18000d1a8  lea     rax, [rdx-8]
0x18000d1ac  cmp     rax, 1Fh
0x18000d1b0  jbe     short loc_18000D1C8
0x18000d1b2  mov     [rsp+0A0h+Reserved], rbx; Reserved
0x18000d1b7  xor     r9d, r9d; LineNo
0x18000d1ba  xor     r8d, r8d; FileName
0x18000d1bd  xor     edx, edx; FunctionName
0x18000d1bf  xor     ecx, ecx; Expression
0x18000d1c1  call    cs:__imp__invoke_watson
0x18000d1c8  call    cs:__imp_free
0x18000d1ce  mov     rax, [r14]
0x18000d1d1  mov     rcx, r14
0x18000d1d4  mov     rax, [rax+18h]
0x18000d1d8  call    cs:__guard_dispatch_icall_fptr
0x18000d1de  movzx   ecx, ax
0x18000d1e1  cmp     [r14+10h], rbx
0x18000d1e5  jz      short loc_18000D1F5
0x18000d1e7  lea     rbx, [rdi+28h]
0x18000d1eb  cmp     qword ptr [rbx+18h], 7
0x18000d1f0  jbe     short loc_18000D1F5
0x18000d1f2  mov     rbx, [rbx]
0x18000d1f5  lea     rax, [rdi+8]
0x18000d1f9  cmp     qword ptr [rax+18h], 7
0x18000d1fe  jbe     short loc_18000D203
0x18000d200  mov     rax, [rax]
0x18000d203  lea     rdx, ??_7?$StructuredObject@PEB_W$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable'
0x18000d20a  mov     [rdi+48h], rdx
0x18000d20e  mov     [rdi+50h], rax
0x18000d212  mov     [rdi+58h], rbx
0x18000d216  mov     [rdi+60h], cx
0x18000d21a  mov     rax, rdi
0x18000d21d  mov     rcx, [rbp+57h+var_20]
0x18000d221  xor     rcx, rsp; StackCookie
0x18000d224  call    __security_check_cookie
0x18000d229  lea     r11, [rsp+0A0h+var_10]
0x18000d231  mov     rbx, [r11+30h]
0x18000d235  mov     rsi, [r11+38h]
0x18000d239  mov     rsp, r11
0x18000d23c  pop     r14
0x18000d23e  pop     rdi
0x18000d23f  pop     rbp
0x18000d240  retn
```
