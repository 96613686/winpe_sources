# Mso::Logging::StructuredTraceCopier::ClassifiedStructuredObjectCopy<wchar_t const *>::ClassifiedStructuredObjectCopy<wchar_t const *>(Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> const &)

- ea: `0x18000d588`
- end: `0x18000d799`
- name: `??0?$ClassifiedStructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@QEAA@AEBU?$ClassifiedStructuredObject@PEB_W@Diagnostics@3@@Z`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f3ec`

## callees

- `0x18000410c`
- `0x18000a208`
- `0x18000d588`
- `0x1800266e0`
- `0x18002b3c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000d6f9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000d6f9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000d6ac`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000d700`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000d6ac`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000d700`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Mso::Logging::StructuredTraceCopier::ClassifiedStructuredObjectCopy<wchar_t const *>::ClassifiedStructuredObjectCopy<wchar_t const *>(
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
  *(_QWORD *)a1 = &Mso::Logging::StructuredTraceCopier::ClassifiedStructuredObjectCopy<wchar_t const *>::`vftable';
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
    while ( *(_WORD *)(v8 + 2 * v6) );
    std::wstring::_Construct<1,wchar_t const *>(Block, v8, v6);
    v9 = Block;
    v10 = 1;
  }
  else
  {
    v17 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v17) = 0;
    v9 = (void **)&v17;
    v10 = 2;
  }
  *(_OWORD *)(a1 + 40) = *(_OWORD *)v9;
  *(_OWORD *)(a1 + 56) = *((_OWORD *)v9 + 1);
  *(_WORD *)v9 = 0;
  v9[2] = 0;
  v9[3] = (void *)7;
  if ( (v10 & 2) != 0 )
  {
    v10 &= ~2u;
    if ( si128.m128i_i64[1] > 7uLL )
    {
      v11 = (void *)v17;
      if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
      {
        v11 = *(void **)(v17 - 8);
        if ( (unsigned __int64)(v17 - (_QWORD)v11 - 8) > 0x1F )
LABEL_17:
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v11);
    }
  }
  if ( (v10 & 1) != 0 && *((_QWORD *)&v21 + 1) > 7u )
  {
    v12 = Block[0];
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v21 + 1) + 2) >= 0x1000 )
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
    if ( *(_QWORD *)(a1 + 64) > 7u )
      v14 = (_QWORD *)*v14;
  }
  else
  {
    v14 = 0;
  }
  v15 = (_QWORD *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 32) > 0xFu )
    v15 = (_QWORD *)*v15;
  *(_QWORD *)(a1 + 72) = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
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
0x18000d588  mov     [rsp-8+arg_10], rbx
0x18000d58d  mov     [rsp-8+arg_18], rsi
0x18000d592  push    rbp
0x18000d593  push    rdi
0x18000d594  push    r14
0x18000d596  lea     rbp, [rsp-47h]
0x18000d59b  sub     rsp, 90h
0x18000d5a2  mov     rax, cs:__security_cookie
0x18000d5a9  xor     rax, rsp
0x18000d5ac  mov     [rbp+57h+var_20], rax
0x18000d5b0  mov     rsi, rdx
0x18000d5b3  mov     rbx, rcx
0x18000d5b6  mov     [rbp+57h+var_48], rcx
0x18000d5ba  xor     r14d, r14d
0x18000d5bd  mov     dword ptr [rbp+57h+var_70], r14d
0x18000d5c1  lea     rax, ??_7?$ClassifiedStructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@6B@; const Mso::Logging::StructuredTraceCopier::ClassifiedStructuredObjectCopy<wchar_t const *>::`vftable'
0x18000d5c8  mov     [rcx], rax
0x18000d5cb  add     rcx, 8
0x18000d5cf  mov     [rbp+57h+var_70], rcx
0x18000d5d3  mov     rdx, [rdx+8]
0x18000d5d7  xorps   xmm0, xmm0
0x18000d5da  movups  xmmword ptr [rcx], xmm0
0x18000d5dd  mov     [rcx+10h], r14
0x18000d5e1  mov     [rcx+18h], r14
0x18000d5e5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000d5e9  mov     r8, rdi
0x18000d5ec  inc     r8
0x18000d5ef  cmp     [rdx+r8], r14b
0x18000d5f3  jnz     short loc_18000D5EC
0x18000d5f5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000d5fa  mov     rdx, [rsi+10h]
0x18000d5fe  xorps   xmm0, xmm0
0x18000d601  test    rdx, rdx
0x18000d604  jz      short loc_18000D633
0x18000d606  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18000d60a  xorps   xmm1, xmm1
0x18000d60d  movdqu  [rbp+57h+var_30], xmm1
0x18000d612  inc     rdi
0x18000d615  cmp     [rdx+rdi*2], r14w
0x18000d61a  jnz     short loc_18000D612
0x18000d61c  mov     r8, rdi
0x18000d61f  lea     rcx, [rbp+57h+Block]
0x18000d623  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000d628  lea     rax, [rbp+57h+Block]
0x18000d62c  mov     edi, 1
0x18000d631  jmp     short loc_18000D652
0x18000d633  movups  [rbp+57h+var_68], xmm0
0x18000d637  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000d63f  movdqu  [rbp+57h+var_58], xmm1
0x18000d644  mov     word ptr [rbp+57h+var_68], r14w
0x18000d649  lea     rax, [rbp+57h+var_68]
0x18000d64d  mov     edi, 2
0x18000d652  movups  xmm0, xmmword ptr [rax]
0x18000d655  movups  xmmword ptr [rbx+28h], xmm0
0x18000d659  movups  xmm1, xmmword ptr [rax+10h]
0x18000d65d  movups  xmmword ptr [rbx+38h], xmm1
0x18000d661  mov     [rax], r14w
0x18000d665  mov     [rax+10h], r14
0x18000d669  mov     qword ptr [rax+18h], 7
0x18000d671  test    dil, 2
0x18000d675  jz      short loc_18000D6B2
0x18000d677  and     edi, 0FFFFFFFDh
0x18000d67a  mov     rax, qword ptr [rbp+57h+var_58+8]
0x18000d67e  cmp     rax, 7
0x18000d682  jbe     short loc_18000D6B2
0x18000d684  mov     rcx, qword ptr [rbp+57h+var_68]
0x18000d688  mov     rdx, rcx
0x18000d68b  lea     rax, ds:2[rax*2]
0x18000d693  cmp     rax, 1000h
0x18000d699  jb      short loc_18000D6AC
0x18000d69b  mov     rcx, [rcx-8]; Block
0x18000d69f  sub     rdx, rcx
0x18000d6a2  lea     rax, [rdx-8]
0x18000d6a6  cmp     rax, 1Fh
0x18000d6aa  ja      short loc_18000D6EA
0x18000d6ac  call    cs:__imp_free
0x18000d6b2  test    dil, 1
0x18000d6b6  jz      short loc_18000D706
0x18000d6b8  mov     rax, qword ptr [rbp+57h+var_30+8]
0x18000d6bc  cmp     rax, 7
0x18000d6c0  jbe     short loc_18000D706
0x18000d6c2  mov     rcx, [rbp+57h+Block]; Block
0x18000d6c6  mov     rdx, rcx
0x18000d6c9  lea     rax, ds:2[rax*2]
0x18000d6d1  cmp     rax, 1000h
0x18000d6d7  jb      short loc_18000D700
0x18000d6d9  mov     rcx, [rcx-8]
0x18000d6dd  sub     rdx, rcx
0x18000d6e0  lea     rax, [rdx-8]
0x18000d6e4  cmp     rax, 1Fh
0x18000d6e8  jbe     short loc_18000D700
0x18000d6ea  mov     [rsp+0A0h+Reserved], r14; Reserved
0x18000d6ef  xor     r9d, r9d; LineNo
0x18000d6f2  xor     r8d, r8d; FileName
0x18000d6f5  xor     edx, edx; FunctionName
0x18000d6f7  xor     ecx, ecx; Expression
0x18000d6f9  call    cs:__imp__invoke_watson
0x18000d700  call    cs:__imp_free
0x18000d706  mov     rax, [rsi]
0x18000d709  mov     rcx, rsi
0x18000d70c  mov     rax, [rax+18h]
0x18000d710  call    cs:__guard_dispatch_icall_fptr
0x18000d716  movzx   edx, ax
0x18000d719  cmp     [rsi+10h], r14
0x18000d71d  jz      short loc_18000D72F
0x18000d71f  lea     rcx, [rbx+28h]
0x18000d723  cmp     qword ptr [rcx+18h], 7
0x18000d728  jbe     short loc_18000D732
0x18000d72a  mov     rcx, [rcx]
0x18000d72d  jmp     short loc_18000D732
0x18000d72f  mov     rcx, r14
0x18000d732  lea     rax, [rbx+8]
0x18000d736  cmp     qword ptr [rax+18h], 0Fh
0x18000d73b  jbe     short loc_18000D740
0x18000d73d  mov     rax, [rax]
0x18000d740  lea     r8, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x18000d747  mov     [rbx+48h], r8
0x18000d74b  mov     [rbx+50h], rax
0x18000d74f  mov     [rbx+58h], rcx
0x18000d753  mov     [rbx+60h], dx
0x18000d757  xorps   xmm0, xmm0
0x18000d75a  movups  xmmword ptr [rbx+68h], xmm0
0x18000d75e  mov     [rbx+78h], r14
0x18000d762  mov     qword ptr [rbx+80h], 7
0x18000d76d  mov     [rbx+68h], r14w
0x18000d772  mov     rax, rbx
0x18000d775  mov     rcx, [rbp+57h+var_20]
0x18000d779  xor     rcx, rsp; StackCookie
0x18000d77c  call    __security_check_cookie
0x18000d781  lea     r11, [rsp+0A0h+var_10]
0x18000d789  mov     rbx, [r11+30h]
0x18000d78d  mov     rsi, [r11+38h]
0x18000d791  mov     rsp, r11
0x18000d794  pop     r14
0x18000d796  pop     rdi
0x18000d797  pop     rbp
0x18000d798  retn
```
