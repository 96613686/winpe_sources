# Mso::Logging::StructuredTraceCopier::ClassifiedStructuredObjectCopy<char const *>::ClassifiedStructuredObjectCopy<char const *>(Mso::Diagnostics::ClassifiedStructuredObject<char const *> const &)

- ea: `0x18000d364`
- end: `0x18000d56a`
- name: `??0?$ClassifiedStructuredObjectCopy@PEBD@StructuredTraceCopier@Logging@Mso@@QEAA@AEBU?$ClassifiedStructuredObject@PEBD@Diagnostics@3@@Z`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f0ec`

## callees

- `0x18000a208`
- `0x18000d364`
- `0x1800266e0`
- `0x18002b3c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000d4ca`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000d4ca`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000d482`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000d4d1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000d482`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000d4d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Mso::Logging::StructuredTraceCopier::ClassifiedStructuredObjectCopy<char const *>::ClassifiedStructuredObjectCopy<char const *>(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // rdx
  void **v9; // rax
  char v10; // di
  void *v11; // rcx
  void *v12; // rcx
  __int16 v13; // dx
  _QWORD *v14; // rcx
  _QWORD *v15; // rax
  __int128 v17; // [rsp+38h] [rbp-11h] BYREF
  __m128i si128; // [rsp+48h] [rbp-1h]
  __int64 v19; // [rsp+58h] [rbp+Fh]
  void *Block[2]; // [rsp+60h] [rbp+17h] BYREF
  __int128 v21; // [rsp+70h] [rbp+27h]

  v19 = a1;
  *(_QWORD *)a1 = &Mso::Logging::StructuredTraceCopier::ClassifiedStructuredObjectCopy<char const *>::`vftable';
  v4 = a1 + 8;
  v5 = a2[1];
  *(_OWORD *)v4 = 0;
  *(_QWORD *)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 24) = 0;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_BYTE *)(v5 + v7) );
  std::string::_Construct<1,char const *>(v4);
  v8 = a2[2];
  if ( v8 )
  {
    *(_OWORD *)Block = 0;
    v21 = 0;
    do
      ++v6;
    while ( *(_BYTE *)(v8 + v6) );
    std::string::_Construct<1,char const *>(Block);
    v9 = Block;
    v10 = 1;
  }
  else
  {
    v17 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v17) = 0;
    v9 = (void **)&v17;
    v10 = 2;
  }
  *(_OWORD *)(a1 + 40) = *(_OWORD *)v9;
  *(_OWORD *)(a1 + 56) = *((_OWORD *)v9 + 1);
  *(_BYTE *)v9 = 0;
  v9[2] = 0;
  v9[3] = (void *)15;
  if ( (v10 & 2) != 0 )
  {
    v10 &= ~2u;
    if ( si128.m128i_i64[1] > 0xFuLL )
    {
      v11 = (void *)v17;
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v11 = *(void **)(v17 - 8);
        if ( (unsigned __int64)(v17 - (_QWORD)v11 - 8) > 0x1F )
LABEL_17:
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v11);
    }
  }
  if ( (v10 & 1) != 0 && *((_QWORD *)&v21 + 1) > 0xFu )
  {
    v12 = Block[0];
    if ( (unsigned __int64)(*((_QWORD *)&v21 + 1) + 1LL) >= 0x1000 )
    {
      v12 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v12 - 8) > 0x1F )
        goto LABEL_17;
    }
    free(v12);
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD *))(*a2 + 24LL))(a2);
  if ( a2[2] )
  {
    v14 = (_QWORD *)(a1 + 40);
    if ( *(_QWORD *)(a1 + 64) > 0xFu )
      v14 = (_QWORD *)*v14;
  }
  else
  {
    v14 = 0;
  }
  v15 = (_QWORD *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 32) > 0xFu )
    v15 = (_QWORD *)*v15;
  *(_QWORD *)(a1 + 72) = &Mso::Diagnostics::ClassifiedStructuredObject<char const *>::`vftable';
  *(_QWORD *)(a1 + 80) = v15;
  *(_QWORD *)(a1 + 88) = v14;
  *(_WORD *)(a1 + 96) = v13;
  *(_OWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 7;
  *(_WORD *)(a1 + 104) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000d364  mov     [rsp-8+arg_10], rbx
0x18000d369  mov     [rsp-8+arg_18], rsi
0x18000d36e  push    rbp
0x18000d36f  push    rdi
0x18000d370  push    r14
0x18000d372  lea     rbp, [rsp-47h]
0x18000d377  sub     rsp, 90h
0x18000d37e  mov     rax, cs:__security_cookie
0x18000d385  xor     rax, rsp
0x18000d388  mov     [rbp+57h+var_20], rax
0x18000d38c  mov     rsi, rdx
0x18000d38f  mov     rbx, rcx
0x18000d392  mov     [rbp+57h+var_48], rcx
0x18000d396  xor     r14d, r14d
0x18000d399  mov     dword ptr [rbp+57h+var_70], r14d
0x18000d39d  lea     rax, ??_7?$ClassifiedStructuredObjectCopy@PEBD@StructuredTraceCopier@Logging@Mso@@6B@; const Mso::Logging::StructuredTraceCopier::ClassifiedStructuredObjectCopy<char const *>::`vftable'
0x18000d3a4  mov     [rcx], rax
0x18000d3a7  add     rcx, 8
0x18000d3ab  mov     [rbp+57h+var_70], rcx
0x18000d3af  mov     rdx, [rdx+8]
0x18000d3b3  xorps   xmm0, xmm0
0x18000d3b6  movups  xmmword ptr [rcx], xmm0
0x18000d3b9  mov     [rcx+10h], r14
0x18000d3bd  mov     [rcx+18h], r14
0x18000d3c1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000d3c5  mov     r8, rdi
0x18000d3c8  inc     r8
0x18000d3cb  cmp     [rdx+r8], r14b
0x18000d3cf  jnz     short loc_18000D3C8
0x18000d3d1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000d3d6  mov     rdx, [rsi+10h]
0x18000d3da  xorps   xmm0, xmm0
0x18000d3dd  test    rdx, rdx
0x18000d3e0  jz      short loc_18000D410
0x18000d3e2  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18000d3e6  xorps   xmm1, xmm1
0x18000d3e9  movdqu  [rbp+57h+var_30], xmm1
0x18000d3ee  inc     rdi
0x18000d3f1  cmp     [rdx+rdi], r14b
0x18000d3f5  jnz     short loc_18000D3EE
0x18000d3f7  mov     r8, rdi
0x18000d3fa  lea     rcx, [rbp+57h+Block]
0x18000d3fe  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000d403  lea     rax, [rbp+57h+Block]
0x18000d407  mov     edi, 1
0x18000d40c  jmp     short loc_18000D42E
0x18000d410  movups  [rbp+57h+var_68], xmm0
0x18000d414  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18000d41c  movdqu  [rbp+57h+var_58], xmm1
0x18000d421  mov     byte ptr [rbp+57h+var_68], r14b
0x18000d425  lea     rax, [rbp+57h+var_68]
0x18000d429  mov     edi, 2
0x18000d42e  movups  xmm0, xmmword ptr [rax]
0x18000d431  movups  xmmword ptr [rbx+28h], xmm0
0x18000d435  movups  xmm1, xmmword ptr [rax+10h]
0x18000d439  movups  xmmword ptr [rbx+38h], xmm1
0x18000d43d  mov     [rax], r14b
0x18000d440  mov     [rax+10h], r14
0x18000d444  mov     qword ptr [rax+18h], 0Fh
0x18000d44c  test    dil, 2
0x18000d450  jz      short loc_18000D488
0x18000d452  and     edi, 0FFFFFFFDh
0x18000d455  mov     rax, qword ptr [rbp+57h+var_58+8]
0x18000d459  cmp     rax, 0Fh
0x18000d45d  jbe     short loc_18000D488
0x18000d45f  mov     rcx, qword ptr [rbp+57h+var_68]
0x18000d463  mov     rdx, rcx
0x18000d466  inc     rax
0x18000d469  cmp     rax, 1000h
0x18000d46f  jb      short loc_18000D482
0x18000d471  mov     rcx, [rcx-8]; Block
0x18000d475  sub     rdx, rcx
0x18000d478  lea     rax, [rdx-8]
0x18000d47c  cmp     rax, 1Fh
0x18000d480  ja      short loc_18000D4BB
0x18000d482  call    cs:__imp_free
0x18000d488  test    dil, 1
0x18000d48c  jz      short loc_18000D4D7
0x18000d48e  mov     rax, qword ptr [rbp+57h+var_30+8]
0x18000d492  cmp     rax, 0Fh
0x18000d496  jbe     short loc_18000D4D7
0x18000d498  mov     rcx, [rbp+57h+Block]; Block
0x18000d49c  mov     rdx, rcx
0x18000d49f  inc     rax
0x18000d4a2  cmp     rax, 1000h
0x18000d4a8  jb      short loc_18000D4D1
0x18000d4aa  mov     rcx, [rcx-8]
0x18000d4ae  sub     rdx, rcx
0x18000d4b1  lea     rax, [rdx-8]
0x18000d4b5  cmp     rax, 1Fh
0x18000d4b9  jbe     short loc_18000D4D1
0x18000d4bb  mov     [rsp+0A0h+Reserved], r14; Reserved
0x18000d4c0  xor     r9d, r9d; LineNo
0x18000d4c3  xor     r8d, r8d; FileName
0x18000d4c6  xor     edx, edx; FunctionName
0x18000d4c8  xor     ecx, ecx; Expression
0x18000d4ca  call    cs:__imp__invoke_watson
0x18000d4d1  call    cs:__imp_free
0x18000d4d7  mov     rax, [rsi]
0x18000d4da  mov     rcx, rsi
0x18000d4dd  mov     rax, [rax+18h]
0x18000d4e1  call    cs:__guard_dispatch_icall_fptr
0x18000d4e7  movzx   edx, ax
0x18000d4ea  cmp     [rsi+10h], r14
0x18000d4ee  jz      short loc_18000D500
0x18000d4f0  lea     rcx, [rbx+28h]
0x18000d4f4  cmp     qword ptr [rcx+18h], 0Fh
0x18000d4f9  jbe     short loc_18000D503
0x18000d4fb  mov     rcx, [rcx]
0x18000d4fe  jmp     short loc_18000D503
0x18000d500  mov     rcx, r14
0x18000d503  lea     rax, [rbx+8]
0x18000d507  cmp     qword ptr [rax+18h], 0Fh
0x18000d50c  jbe     short loc_18000D511
0x18000d50e  mov     rax, [rax]
0x18000d511  lea     r8, ??_7?$ClassifiedStructuredObject@PEBD@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<char const *>::`vftable'
0x18000d518  mov     [rbx+48h], r8
0x18000d51c  mov     [rbx+50h], rax
0x18000d520  mov     [rbx+58h], rcx
0x18000d524  mov     [rbx+60h], dx
0x18000d528  xorps   xmm0, xmm0
0x18000d52b  movups  xmmword ptr [rbx+68h], xmm0
0x18000d52f  mov     [rbx+78h], r14
0x18000d533  mov     qword ptr [rbx+80h], 7
0x18000d53e  mov     [rbx+68h], r14w
0x18000d543  mov     rax, rbx
0x18000d546  mov     rcx, [rbp+57h+var_20]
0x18000d54a  xor     rcx, rsp; StackCookie
0x18000d54d  call    __security_check_cookie
0x18000d552  lea     r11, [rsp+0A0h+var_10]
0x18000d55a  mov     rbx, [r11+30h]
0x18000d55e  mov     rsi, [r11+38h]
0x18000d562  mov     rsp, r11
0x18000d565  pop     r14
0x18000d567  pop     rdi
0x18000d568  pop     rbp
0x18000d569  retn
```
