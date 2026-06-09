# Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>::StructuredObjectCopy<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>(Mso::Logging::StructuredObject<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,0> const &)

- ea: `0x180011600`
- end: `0x18001179e`
- name: `??0?$StructuredObjectCopy@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@StructuredTraceCopier@Logging@Mso@@QEAA@AEBU?$StructuredObject@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@23@@Z`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000e6ec`

## callees

- `0x180001bac`
- `0x18000410c`
- `0x180005224`
- `0x18000a2ec`
- `0x18000ab0c`
- `0x180011600`
- `0x18002b3c0`
- `0x18002b780`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180011782`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180011782`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<std::string>::StructuredObjectCopy<std::string>(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v4; // rdi
  __int64 v5; // rdx
  void *v6; // rbx
  __int64 v7; // r8
  _QWORD *v8; // r15
  _QWORD *v9; // rdx
  __int16 v10; // r12
  _QWORD *v11; // rdi
  unsigned __int64 v12; // rbp
  __int64 v13; // rsi
  size_t v14; // rcx
  void *v15; // rax

  *(_QWORD *)a1 = &Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<std::string>::`vftable';
  v4 = (_QWORD *)(a1 + 8);
  v5 = a2[1];
  *(_OWORD *)(a1 + 8) = 0;
  v6 = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(v5 + 2 * v7) );
  std::wstring::_Construct<1,wchar_t const *>(a1 + 8, v5, v7);
  v8 = (_QWORD *)(a1 + 40);
  v9 = a2 + 2;
  *(_OWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  if ( a2[5] > 0xFu )
    v9 = (_QWORD *)*v9;
  std::string::_Construct<2,char const *>(a1 + 40, v9, a2[4]);
  v10 = (*(__int64 (__fastcall **)(_QWORD *))(*a2 + 24LL))(a2);
  if ( v4[3] > 7u )
    v4 = (_QWORD *)*v4;
  *(_QWORD *)(a1 + 72) = &Mso::Logging::StructuredObject<std::string,0>::`vftable';
  *(_QWORD *)(a1 + 80) = v4;
  v11 = (_QWORD *)(a1 + 88);
  *(_OWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  v12 = *(_QWORD *)(a1 + 56);
  if ( *(_QWORD *)(a1 + 64) > 0xFu )
    v8 = (_QWORD *)*v8;
  v13 = 0x7FFFFFFFFFFFFFFFLL;
  if ( v12 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlen_string();
  if ( v12 > 0xF )
  {
    if ( (v12 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      v13 = v12 | 0xF;
      if ( (v12 | 0xF) < 0x16 )
        v13 = 22;
    }
    v14 = v13 + 1;
    if ( v13 != -1 )
    {
      _mm_lfence();
      if ( v14 < 0x1000 )
      {
        v15 = malloc(v14);
        if ( !v15 )
          std::_Xbad_alloc();
      }
      else
      {
        v15 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v14);
      }
      v6 = v15;
    }
    *v11 = v6;
    *(_QWORD *)(a1 + 104) = v12;
    *(_QWORD *)(a1 + 112) = v13;
    memmove(v6, v8, v12 + 1);
  }
  else
  {
    *(_QWORD *)(a1 + 104) = v12;
    *(_QWORD *)(a1 + 112) = 15;
    *(_OWORD *)v11 = *(_OWORD *)v8;
  }
  *(_WORD *)(a1 + 120) = v10;
  return a1;
}

```

## disassembly

```asm
0x180011600  mov     r11, rsp
0x180011603  mov     [r11+18h], rbx
0x180011607  mov     [r11+20h], rbp
0x18001160b  mov     [r11+8], rcx
0x18001160f  push    rsi
0x180011610  push    rdi
0x180011611  push    r12
0x180011613  push    r14
0x180011615  push    r15
0x180011617  sub     rsp, 20h
0x18001161b  mov     rsi, rdx
0x18001161e  mov     r14, rcx
0x180011621  lea     rax, ??_7?$StructuredObjectCopy@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@StructuredTraceCopier@Logging@Mso@@6B@; const Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<std::string>::`vftable'
0x180011628  mov     [rcx], rax
0x18001162b  lea     rdi, [rcx+8]
0x18001162f  mov     [r11+10h], rdi
0x180011633  mov     rdx, [rdx+8]
0x180011637  xorps   xmm0, xmm0
0x18001163a  movups  xmmword ptr [rdi], xmm0
0x18001163d  xor     ebx, ebx
0x18001163f  mov     [rdi+10h], rbx
0x180011643  mov     [rdi+18h], rbx
0x180011647  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001164b  inc     r8
0x18001164e  cmp     [rdx+r8*2], bx
0x180011653  jnz     short loc_18001164B
0x180011655  mov     rcx, rdi
0x180011658  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001165d  lea     r15, [r14+28h]
0x180011661  mov     [rsp+48h+arg_8], r15
0x180011666  lea     rdx, [rsi+10h]
0x18001166a  xorps   xmm0, xmm0
0x18001166d  movups  xmmword ptr [r15], xmm0
0x180011671  mov     [r15+10h], rbx
0x180011675  mov     [r15+18h], rbx
0x180011679  mov     r8, [rdx+10h]
0x18001167d  cmp     qword ptr [rdx+18h], 0Fh
0x180011682  jbe     short loc_180011687
0x180011684  mov     rdx, [rdx]
0x180011687  mov     rcx, r15
0x18001168a  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x18001168f  mov     rax, [rsi]
0x180011692  mov     rcx, rsi
0x180011695  mov     rax, [rax+18h]
0x180011699  call    cs:__guard_dispatch_icall_fptr
0x18001169f  movzx   r12d, ax
0x1800116a3  cmp     qword ptr [rdi+18h], 7
0x1800116a8  jbe     short loc_1800116AD
0x1800116aa  mov     rdi, [rdi]
0x1800116ad  lea     rax, ??_7?$StructuredObject@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<std::string,0>::`vftable'
0x1800116b4  mov     [r14+48h], rax
0x1800116b8  mov     [r14+50h], rdi
0x1800116bc  lea     rdi, [r14+58h]
0x1800116c0  mov     [rsp+48h+arg_8], rdi
0x1800116c5  xorps   xmm0, xmm0
0x1800116c8  movups  xmmword ptr [rdi], xmm0
0x1800116cb  mov     [rdi+10h], rbx
0x1800116cf  mov     [rdi+18h], rbx
0x1800116d3  mov     rbp, [r15+10h]
0x1800116d7  cmp     qword ptr [r15+18h], 0Fh
0x1800116dc  jbe     short loc_1800116E1
0x1800116de  mov     r15, [r15]
0x1800116e1  mov     rsi, 7FFFFFFFFFFFFFFFh
0x1800116eb  cmp     rbp, rsi
0x1800116ee  ja      loc_180011792
0x1800116f4  cmp     rbp, 0Fh
0x1800116f8  ja      short loc_180011710
0x1800116fa  mov     [rdi+10h], rbp
0x1800116fe  mov     qword ptr [rdi+18h], 0Fh
0x180011706  movups  xmm0, xmmword ptr [r15]
0x18001170a  movdqu  xmmword ptr [rdi], xmm0
0x18001170e  jmp     short loc_180011763
0x180011710  mov     rax, rbp
0x180011713  or      rax, 0Fh
0x180011717  cmp     rax, rsi
0x18001171a  ja      short loc_18001172B
0x18001171c  mov     rsi, rax
0x18001171f  mov     ecx, 16h
0x180011724  cmp     rax, rcx
0x180011727  cmovb   rsi, rcx
0x18001172b  lea     rcx, [rsi+1]; Size
0x18001172f  test    rcx, rcx
0x180011732  jz      short loc_180011748
0x180011734  lfence
0x180011737  cmp     rcx, 1000h
0x18001173e  jb      short loc_180011782
0x180011740  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x180011745  mov     rbx, rax
0x180011748  mov     [rdi], rbx
0x18001174b  mov     [rdi+10h], rbp
0x18001174f  mov     [rdi+18h], rsi
0x180011753  lea     r8, [rbp+1]; Size
0x180011757  mov     rdx, r15; Src
0x18001175a  mov     rcx, rbx; void *
0x18001175d  call    memmove
0x180011762  nop
0x180011763  mov     [r14+78h], r12w
0x180011768  mov     rax, r14
0x18001176b  mov     rbx, [rsp+48h+arg_10]
0x180011770  mov     rbp, [rsp+48h+arg_18]
0x180011775  add     rsp, 20h
0x180011779  pop     r15
0x18001177b  pop     r14
0x18001177d  pop     r12
0x18001177f  pop     rdi
0x180011780  pop     rsi
0x180011781  retn
0x180011782  call    cs:__imp_malloc
0x180011788  test    rax, rax
0x18001178b  jz      short loc_180011798
0x18001178d  nop     dword ptr [rax]
0x180011790  jmp     short loc_180011745
0x180011792  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180011798  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
